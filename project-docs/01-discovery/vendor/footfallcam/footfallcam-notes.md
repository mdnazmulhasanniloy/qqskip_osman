# FootfallCam — sensor notes for Qskip

Collected 2026-11-23 from the vendor pages linked by the client. Confirm open points with FootfallCam.
Product pages given by the client:
- Pro3: https://www.footfallcam.com/Product/FootfallCam-Pro3
- Pro1: https://www.footfallcam.com/Product/FootfallCam-Pro1
- 3D Pro2: https://www.footfallcam.com/Product/FootfallCam-3D-Pro2
- Pro2 datasheet (PDF, not yet read — download and place it in this folder): https://www.footfallcam.com/Content/data/documents/Download-Page/Spec-Sheet/FootfallCam-Pro2-Datasheet.pdf

Integration docs:
- WebSocket data push guide (3D Pro2 2025): https://www.footfallcam.com/people-counting/knowledge-base/footfallcam-people-counter-websocket-integration-guide/
- Export data from device (MQTT, REST, WebSocket, BACnet): https://www.footfallcam.com/people-counting/knowledge-base/chapter-2-export-data-from-device/
- V9 Server (cloud) API: https://www.footfallcam.com/people-counting/knowledge-base/v9-server-api/

## What the devices are

They are people counters, not video cameras for our apps. They send IN/OUT counts (and some
models occupancy / queue metrics). No API for streaming video into our apps was found.

| Model | Does | Fit for Qskip |
| --- | --- | --- |
| 3D Pro2 | Entrance counter, on-device AI, up to 99.8% accuracy claimed, staff exclusion, privacy mode. Complete system USD 650 (hardware, hosting, shipping, tuning, install support); on-site install extra | Occupancy (people inside). Does not measure queue length |
| Pro3 | Stereo 3D counter + hub for up to 8 cameras (Pro1 or IP). Metrics include queue counting and occupancy dwell. Price on quote | Queue length if queue metric is available to us |
| Pro1 | Add-on cameras for Pro3: fisheye, dome (also works as CCTV), carpark. Covers queues, aisles, dwell zones | Long or bent queue lines |

## Data access options

| Method | Direction | Notes | Use in Qskip |
| --- | --- | --- | --- |
| Device WebSocket push | Device → our server | Device is the WS client; we are the server. Bearer token header. Granularity: per event, 1 min, 15 min, hourly. Keepalive every 30 s, auto reconnect with backoff. We must answer Ping with Pong and ACK every message. If our server is down the device buffers up to 10,000 IN/OUT records (~2 weeks), then the module turns off | **Primary** |
| MQTT | Device → broker | QoS 0 only, topic /status/{ChipSerial}, occupancy (ObjectCount) + counting events | Fallback |
| Device REST | We → device internal IP | `/cgi-bin/access_token.cgi`, `/cgi-bin/apiCount.cgi`; needs local network | Not usable from cloud |
| V9 cloud REST | We → cube.footfallcam.com | POST /API/v1/load with bearer token, aggregated metrics (footfall, occupancy) | Analytics, backfill |
| Pulsar WebSocket | FootfallCam → us | Live occupancy per branch/area; address supplied by FootfallCam | Option if devices are on V9 |

## Payloads (WebSocket push)

Per event message:
```json
{
  "UUID": "unique message id",
  "DeviceSerial": "…",
  "RoiId": 1,
  "MetricId": 1,              // 1 = IN, 2 = OUT
  "PeopleTypeId": 1,
  "CombineObjectTypeId": 11,  // 11 = visitor, 21 = staff
  "PeopleId": 123,
  "EventStartTime": 1763870000,
  "EventEndTime": 1763870001
  // + local and UTC string versions of the times
}
```
Aggregated message (minute / 15 min / hourly):
```json
{
  "uuid": "…", "device_serial": "…", "date_requested": "local datetime", "offset": "+00:00",
  "output": [ { "datetime": "local", "invalue": 4, "outvalue": 2, "timestamp": 1763870000 } ]
}
```
ACK: the 2025 guide says reply `{ "status": "ack", "uuid": "<uuid>" }`; the older device chapter says reply `OK`.
Test with the real firmware (blocker B-028).

## Proposed Qskip design (to be confirmed in ADR-004)

1. Admin registers a sensor: serial, model, business, install date → backend issues a per-device token.
2. Installer sets Data Push on the device: `wss://api.<domain>/sensors/ws`, token, per-event mode.
3. sensor-gateway authenticates token → device, dedupes by UUID, stores raw event, then ACKs.
4. Occupancy = IN − OUT since opening time, staff excluded, never below 0, reset daily.
5. Queue size / wait: Pro3 queue metric if available, else formula in ADR-003.
6. Pro plan auto-update writes the queue, emits a socket event, logs AuditLog source=sensor. Business can override.
7. Health: last keepalive/event → online/offline; offline too long → alert business + admin and fall back to manual ("Queue info outdated").
8. A sensor simulator script sends the same JSON so all of this is built and tested without hardware (fits client "Test mode").

Live View video: not supported by these docs. MVP Live View shows numbers only (blocker B-029).
