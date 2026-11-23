# Figma screen inventory

Captured from the Figma file on 2026-11-23 by reading frame names and zooming into key screens.
Frame names are exactly as in Figma. Check `figma-comments.md` before building any of these.

## Customer app (mobile, 440×960)

Bottom tabs: Home · Passes · Points · Inbox · Profile

| Module | Frames | What is on screen |
| --- | --- | --- |
| Onboarding | Splash, Onboarding 1–6, Location Permisson | Intro slides with venue photos, ask for location |
| Auth | Sign Up, Sign In, Forgot password?, OTP Verify, OTP Verify 2, Create New Password | Email + password, 6-box OTP |
| Discover | Home (5 variants), Filters, map pin guide sheet | Map with venue pins + wait badge; category chips All / Restaurant / Cafe / Events; search; recommendation list (name, distance, wait min, accuracy %) |
| Filters sheet | Filters | Queue length (Under 10 / 15 / 20 / 30 mins), business type (All, Restaurant, Cafes, Food truck, Events, More), Q Skip Pass (Pass available, Discount available, Any), accuracy (90%+ high, 70–89%, Any), occupancy (Quiet, Moderate, Busy, Full, Any), distance slider 1–10 mi, toggles Open now / Rewards available / Verified business only, Apply |
| Map pin guide | (sheet in Home) | Short queue <10 min, Moderate 10–20, Busy queue 20–30, Very busy 30+, Q Skip Pass available, Rewards, Food truck, Verified. Smart filters: Save time, Save money, High accuracy, Your choice. Sorting: Shortest wait, Closest, Highest accuracy, Best rewards, Cheapest pass, Trending now. "AI recommendation" card |
| Venue | Detail (2), Menu, Go to Direction | Hero image, name, rating 4.8 (526), distance; live card WAIT TIME 10 min / QUEUE SIZE 18 People / occupancy bar 65%; buttons Reserve, Q Skip Pass, Contact, Menu; About; Location map + Direction; Reviews; Opening hours table; primary button Join Queue |
| Menu | Menu | Category tabs (All, Burgers, Sides, Drinks), search, 2-column item grid with image, name, price |
| Queue | You're in queue | Ring with "Estimated entrance 10–15 mins", YOUR POSITION #7, AHEAD OF YOU 6, note "We'll notify you when it's almost your turn", Message Business, Leave Queue |
| Reservation | Reservation, Reservation (confirmed) | Date chips, time slot grid, party size stepper, notes, Confirm Reservation → "Your booking is confirmed!" Booking ID #GRWM1234 |
| Pass | Buy Pass, Buy Pass (purchased) | Q Skip Pass £2.99 per pass, tags One-time use / Valid today / Non-refundable, venue, benefits (Skip the wait — saves 10–15 min; 10% off total bill, dine-in only), "Valid for this venue only. One-time use." → "Pass purchased! Show this code on arrival" big code |
| Passes | Passes- Active (2), Passes- Used, Passes- Expired | Tabs Active / Used / Expired; active card with code + Refresh Code; rate-your-experience sheet (stars + text) |
| Points | Points | "Q Skip Points Card" balance 1250 + progress; how to earn (join a queue, visit a venue, buy a pass); rewards list |
| Inbox | Inbox, Inbox_participants | Conversation list, chat with a venue |
| Profile | Profile, Edit Profile, My Activity, Password & Security, Change Password, Email, Payment Methods, Manage Subscription, Push Notifications, FAQ, Contact Us, Terms of Service, Privacy Policy | My Activity: venues visited, passes used, queues joined, your reviews. Password & Security: change password, email, Delete Account. Payment Methods: saved Visa, Add Payment Method. Manage Subscription: Monthly £5.99/mo, Yearly £49.99/yr, Change / Cancel. Push Notifications: categories Queue, Pass, Points, New, Refund |

## Business app (tablet 1194×834, left icon sidebar)

Sidebar order: Overview · Analytics · Queue Control · Live View · Sensors · Scan · Earnings · Menu · Inbox · Teams · Reviews · Profile

| Module | Frames | What is on screen |
| --- | --- | --- |
| Auth / onboarding | Splash Screen, 0–16 numbered steps, OTP, Verify Code, Verify Code- Error, Forgot password, Create New Password | Per comment #32 signup moves to the website; keep login only (see blocker B-020) |
| Overview | Overview ×4 states | (1) "Application under review" (2) normal (3) red "Queue update needed" (4) "Complete your business profile". Normal: orange banner "Queue info is becoming outdated — last updated 15 min ago", KPI cards Queue 18 people (+Update) / Wait time 18 min / Passes sold 24 today / Occupancy 65% / Revenue £320.50 / Reservations 8 today; table "Active Passes Right Now" (ID, Customer, Code, Issued, Status) |
| Analytics | Queue Analytics, Datepicker | Today's summary: Total visitors 468, Peak queue 38, Total passes sold 38, Avg wait 16 min; line chart People in Queue Over Time (Jan–Dec); date picker |
| Queue Control | Queue Control, Set Table modal | Accept Reservation toggle; Queue Size stepper (18 people); Estimated Wait Time stepper (10 min); Tables occupied 10/24 + Set total; Queue status Open / Closed; Update Queue; right panel Current Queue (People 18, Occupancy 65%, Wait 10 min, Status Open) + Recent Activity (pass used, queue updated, pass sold, reservation confirmed) |
| Live View | Live View | "Live" badge, Settings; camera image with drawn Queue Zone polygon and Entrance line; cards Queue Accuracy Score 87%, People in Queue 24 (Live count), Estimated Wait 24 (Updating live), Queue Trend Increasing (+6 in last 10 min), Peak time today 12:00–14:00 |
| Sensors | Sensors | EMPTY frame — no design yet |
| Scan | (sidebar icon only) | Passcode verification — no frame found |
| Earnings | Earnings | Passes sold (all time) 284, Total earnings £849.16, Revenue over time bar chart, Payout history table (Period, Passes, Gross, Commission, You received, Status Pending/Paid) |
| Menu | Menu, Menu- Modal | Menu item list + add/edit modal |
| Inbox | Inbox | Customer conversations |
| Teams | Teams, Add Member modal | Table Name, Email, Role (Manager, Staff, Queue Updater), edit/delete; Add New Member (name, email, role) |
| Reviews | Reviews | Customer reviews list |
| Profile | Profile ×12 | Business profile and settings sub-pages |

## Website (desktop 1440)

| Page / frame | What is on it |
| --- | --- |
| Home | Hero "Skip the wait", how it works in 3 steps, app screenshots, "What people are saying", venues on Q Skip, Q Skip Pass promo, footer with app store badges |
| How it Works | "Everything you need to know": for customers (open app, choose venue, buy a skip pass, show your code, rate your experience) and for businesses (sign up and get approved, configure your queue, go live on the map, verify passes at the door, get paid) |
| Pricing | Business: Basic £10/mo, Pro £30/mo. Customers: £5.99/mo. Contract options 12 or 24 months. FAQ |
| For Business | "Turn your queue into revenue": why venues choose Q Skip, works for any venue type, "Live in under 10 minutes" steps |
| Signup flow (frames 12, 19, 20, 21, 22, 23, Build It, Modal) | 12 Let's get started with your business → 19 Set up your business profile → 20 Choose your subscription plan (Basic £10: manual queue updates, sell passes, customer messaging, standard support · Pro £30: everything in Basic, 1 sensor included, auto queue updates, smart pricing suggestions, priority map visibility, faster payouts, priority support · Q Skip Business Kit: Android tablet, tablet stand, charger, queue sensor; "equipment remains the property of Q Skip") → 21 Review and confirm → 22 Welcome back (login) → 23 / Build It: Welcome to Q Skip |

## Admin dashboard (screenshots only)

Sidebar: Overview, Businesses (expandable), Users, Inbox, Tickets, Staff, Earnings, Payments, Refunds,
Sensors, Knowledge Base, Activity Log, Profile Settings.
Overview: Total revenue £12223, Bookings 4567, Pending 1222, Passes Sold Today 12334; charts Passes sold
and Earning Overview by month; table Top businesses (Business, Plan, Status, Accuracy, Joined, Earning, view).
Other sections exist only as screenshots image 2–15 (businesses list, detail modals, users, tickets,
staff, payments). Export them to `figma-screens/admin_image_XX.png`.
