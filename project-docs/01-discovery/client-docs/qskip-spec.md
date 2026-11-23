Here is a **fully detailed, nothing-missing, developer-grade specification** for Q Skip. This includes apps, website, payments, admin, data, APIs, security, compliance, and operations. You can hand this over directly.

**1. PRODUCTS**

- Q Skip (Customer App, iOS/Android)

- Q Skip for Business (Business App, tablet/mobile)

- Website (Marketing + Business onboarding + Business dashboard)

- Admin Dashboard (Internal control)

**2. USER ROLES**

- Customer (end user)

- Business Owner

- Business Staff (roles: manager, scanner, queue updater)

- Admin (internal team)

**3. CORE USER FLOWS**

**Customer**

Discover venue → View queue → Join queue / Reserve / Buy pass → Show passcode → Visit → Earn points (if subscribed) → Rate accuracy → Chat if needed

**Business**

Sign up → Configure business → Choose plan + contract → Connect payments → Await approval → Go live → Manage queue → Verify codes → View analytics → Handle refunds → Manage staff

**Admin**

Review applications → Approve/reject → Monitor system → Handle disputes → Manage fraud → Configure platform rules

**4. CUSTOMER APP (Q Skip)**

**Screens**

**Welcome**

- Logo

- Tagline

- Rotating “queue fun fact”

- Buttons: Sign up, Log in

**Home (Map-first)**

- Full-screen map (Google Maps)

- User location (blue dot)

- Pins:

  - Green (\<10 min)

  - Orange (10–25 min)

  - Red (\>25 min)

- Optional label above pin: “10 min”

- Top bar: search, filters

- Bottom sheet (collapsed/expandable)

- List toggle view

**Venue Page**

- Header image

- Name, rating, distance, open/closed

- Live card:

  - Wait time (large)

  - Queue size

  - Occupancy bar

- Actions:

  - Join queue

  - Reserve (if enabled)

  - Buy pass

  - Contact business

- Sections:

  - Discounts

  - Reviews

  - Opening hours

  - Report issue

**Queue Tracker**

- Countdown timer

- Queue position

- Estimated entry time

- Buttons: Message business, Leave queue

**Checkout**

- Price breakdown

- Confirm payment

**My Passes**

- Tabs: Active, Used, Expired

- Active shows passcode + expiry timer

**Points Card (Subscription only)**

- Points balance

- Progress bar

- Rewards list

- Activity history

- Passcode for visit verification

**Chat**

- Business chat

- Support chat

- AI chatbot entry

**Profile**

- Account info

- Subscription

- Payment methods

- Delete account

- Policies

**Customer Features**

- Notifications:

  - Queue updates

  - Pass expiring

  - Points earned

  - Refund updates

  - Messages

- Ratings:

  - “Was wait time accurate?”

  - Stored per visit

- Refunds:

  - Request → Business → Admin → Result

- Errors:

  - Payment failed

  - Code expired

  - Queue full

  - Business closed

  - No internet

  - Location denied

**5. BUSINESS APP (Q Skip for Business)**

**Onboarding (App + Website)**

Steps (with progress bar):

1.  Account

2.  Business details

3.  Map pin

4.  Opening hours

5.  Plan selection

6.  Contract selection

7.  Queue setup

8.  Payment (Stripe Connect)

9.  Terms acceptance

10. Submit (pending approval)

**Plans**

**Basic (£10/month)**

- Manual queue updates

- Sell passes

- Basic dashboard

- Standard support

**Pro (£30/month)**

- Sensors included

- Auto queue updates

- Smart pricing

- Advanced analytics

- Marketing tools

- Priority visibility

- Faster payouts

- Priority support

**Contract**

- 12 or 24 months

- Exclusivity during contract only

- Extension options with benefits (lower fees, better ranking)

**Core Screens**

**Dashboard**

- Queue size

- Wait time

- Occupancy

- Passes sold

- Revenue

- Alerts

**Queue Control**

- Update queue size

- Update wait time

- Occupancy slider

- Toggles:

  - Queue visible

  - Accept passes

  - Accept reservations

**Verify Screen (Passcode)**

- Input code

- Validate

- Result:

  - Valid / Invalid

- Mark used

**Inbox**

- Customer chats

- Support chats

- Quick replies

- Escalate

**Analytics**

- Revenue

- Conversion rate

- Peak hours

- Repeat customers

- Drop-off rate

- Charts

**Marketing**

- Discounts

- Boost visibility

- Promotions

**Staff Management**

- Add staff

- Roles:

  - Manager

  - Scanner

  - Queue updater

- Permissions

**Finance**

- Subscription

- Payouts

- Transactions

- VAT summary

**Support**

- Contact Q Skip

- Refund requests

- Disputes

**Business Features**

- Subscription management:

  - Upgrade (instant)

  - Downgrade (next billing cycle)

  - Cancel (end of contract)

- Refund handling:

  - Approve / Reject / Add note

- Audit logs:

  - Queue updates

  - Verifications

  - Pricing changes

  - Refund actions

- Notifications:

  - New pass

  - Queue join

  - Message

  - Payment issue

- Accuracy score:

  - Based on user feedback

  - Affects ranking

- Sensor management (Pro):

  - Status (online/offline)

  - Install date

  - Last active

  - Return status

**6. WEBSITE**

**Purpose**

- Marketing

- Business onboarding

- Business dashboard access

**Pages**

- Home

- How it works

- Pricing

- Business signup

- Customer app info

- Book demo

- Contact

- Legal pages (Terms, Privacy, Refund, Cookie, Sensor disclosure)

**Business Dashboard (Web)**

- Subscription

- Billing

- Invoices

- Analytics

- Staff

- Profile

- Cancel / upgrade / downgrade

**7. ADMIN DASHBOARD**

**Sections**

**Main Dashboard**

- Users

- Businesses

- Revenue

- Active queues

- Passes sold

- Support tickets

- Fraud alerts

**Business Management**

- Approve / Reject / Suspend

- View contract

- View payments

- View sensors

- View accuracy

- Add notes

**User Management**

- View user

- Block user

- View passes

- View points

- Export data

- Delete account

**Payments**

- All transactions

- Commission (15%)

- Refunds

- Chargebacks

- Failed payments

- VAT

**Refunds**

- Pending / Approved / Rejected / Escalated

- Admin override

**Support**

- Chats

- Tickets

- Escalations

**Fraud**

- Repeated invalid codes

- Fake visits

- Abuse patterns

- Multi-account detection

**Sensors**

- Status

- Alerts

- Install tracking

- Returns

**Analytics**

- Top businesses

- Worst accuracy

- Conversion rates

- Heatmaps

**Settings**

- Commission %

- Points rules

- Plan prices

- Passcode expiry

- Notification templates

**8. PAYMENTS**

**Customer**

- Pass purchases (Stripe)

- Subscription (£5.99)

- iOS uses Apple IAP

**Business**

- Subscription (£10 / £30)

- Stripe Connect onboarding

- Monthly billing

**Revenue Split**

- Q Skip: 15%

- Business: 85%

**Webhooks (Stripe)**

- Payment success/failure

- Subscription updates

- Refunds

- Payouts

**9. VERIFICATION SYSTEM**

**MVP (Passcodes)**

- 4–6 digit code

- Expires 30–60 sec

- One-time use

- Business-specific

**Future (QR)**

- Same token encoded as QR

- Uses same verification API

**10. SECURITY**

- Rate limiting

- Token validation

- Location checks (optional)

- Fraud detection rules

- Secure storage (hashed passwords, encrypted sensitive data)

**11. BACKEND STRUCTURE**

**Core Tables**

Users  
Businesses  
Queues  
Passes  
Points  
Visits  
VerificationTokens  
Messages  
RefundRequests  
Notifications  
AuditLogs  
QueueRatings  
Subscriptions

**APIs**

Auth  
Venues  
Queue  
Passes  
Points  
Verification  
Messages  
Refunds  
Business  
Admin

**12. REALTIME**

- WebSockets for:

  - Queue updates

  - Chat

  - Notifications

**13. TEST MODE**

- Fake users

- Fake businesses

- Fake queues

- Fake passcodes

- Fake payments

ENV toggle: TEST / LIVE

**14. COMPLIANCE**

- Account deletion in-app

- Data export

- Privacy policy

- Cookie policy

- Refund policy

- App store billing rules

- Data safety disclosures

**15. DEPLOYMENT**

- Staging environment

- Production environment

- CI/CD pipeline

- Monitoring + logging

**FINAL STATUS**

Complete apps  
Complete website  
Full backend  
Payments  
Admin system  
Fraud protection  
Compliance  
Scalable architecture
