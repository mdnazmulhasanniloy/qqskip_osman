# Glossary

| Term | Meaning |
| --- | --- |
| Venue / Business | A place customers queue for (restaurant, cafe, bar, food truck, event) |
| Queue | Live line at a venue. Has size, estimated wait, status Open/Closed, visible on/off |
| Queue size | Per Figma comment #26: equals the venue's maximum capacity setting (confirm, B-013) |
| Queue entry | One customer's place in a queue: position, people ahead, estimated serve time (comment #37) |
| Occupancy | People inside the venue as % of capacity |
| Wait time | Estimated minutes until entry |
| Accuracy score | How correct a venue's wait times are, from "Was wait time accurate?" ratings; affects ranking |
| Q Skip Pass | Paid one-time pass to skip the line at one venue, valid that day, e.g. £2.99 |
| Passcode | 4–6 digit one-time code, expires in 30–60 s, business-specific, shown by customer, verified by business. Later also as QR |
| Points | Rewards for subscribed customers: earned by joining queues, visits, buying passes; redeemed for rewards |
| Reservation | Booking a date, time slot and party size |
| Basic / Pro plan | Business subscriptions £10 / £30 per month |
| Contract | 12 or 24 month business commitment with exclusivity and extension benefits |
| Business Kit | Android tablet, stand, charger, queue sensor; stays Qskip property |
| Sensor | FootfallCam people counter that updates the queue automatically (Pro) |
| sensor-gateway | Backend module that receives FootfallCam WebSocket pushes |
| Scanner | Business staff role that verifies passcodes |
| Queue updater | Business staff role that only updates the queue |
| Commission | Qskip share of pass revenue: 15% (business gets 85%) |
| Payout | Money sent to the business via Stripe Connect |
| Test mode | ENV toggle TEST / LIVE with fake users, businesses, queues, passcodes, payments |
