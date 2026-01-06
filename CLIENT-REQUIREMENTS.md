# Client Requirements - Meeting Notes

**Date:** January 6, 2026
**Document Type:** Client Requirements from Meeting
**Status:** Pending Clarifications

---

## Overview

The client requires a complete logistics platform with **3 main components**:

1. **Website** - Customer-facing booking system
2. **Admin Dashboard** - Office management system
3. **Driver Mobile App** - Job management and tracking

---

## 1. Website (Customer-Facing)

### Requirements
- ✅ **Instant booking system**
- ✅ **Follow AnyVan website process**
  - Multi-step quote form
  - Service selection
  - Address input (pickup + delivery)
  - Date/time selection
  - Item inventory
  - Instant price calculation
  - Online payment
  - Booking confirmation

### Key Features Needed
- Homepage with clear call-to-action
- Service categories (removals, man-van, etc.)
- Quote form (What/Where/When/Extras)
- Real-time price calculation
- Customer account creation/login
- Payment processing
- Booking confirmation (email/SMS)
- Booking history for customers

---

## 2. Admin/Office Dashboard

### Core Sections Required

#### A. New Jobs Section
- **"Ready to Assign" Queue**
  - All new bookings from customers
  - Waiting for driver assignment
  - Job details visible (pickup, delivery, items, date)
  - Assign to driver functionality

#### B. Drivers Assigned Section
- View all assigned jobs
- Filter by driver
- Filter by date
- Job status tracking
- Reassign capability

#### C. Diary Management
- Calendar view of all jobs
- See all drivers' schedules
- Visual overview of busy/available times
- Drag-and-drop job scheduling (TBC)
- Driver availability tracking

#### D. Finance Section
- Revenue tracking
- Driver earnings/payouts
- Payment status
- Invoices
- Outstanding payments
- Financial reports (daily/weekly/monthly)

#### E. Analytics & Reports
- Booking statistics
- Revenue trends
- Driver performance metrics
- Customer analytics
- Service type breakdown

#### F. Additional Features
- Customer management
- Driver management
- Vehicle/fleet management (TBC)
- Settings & configuration
- Staff user management

---

## 3. Driver Mobile App

### Core Features Required

#### A. Authentication
- ✅ **Each driver has their own account**
- Login with username/password
- Secure authentication

#### B. Job Management
- **Today's Jobs**: List of assigned jobs
- **Job Details**:
  - Pickup address
  - Delivery address
  - Customer contact details (phone/email)
  - Items to move (description/list)
  - Special instructions
  - Scheduled time

#### C. Navigation & Tracking
- ✅ **GPS Tracking System**
  - Office can see driver location in real-time
  - Link to Google Maps for navigation
  - Route to pickup/delivery

#### D. Job Updates - Status System
- En route to pickup
- Arrived at pickup
- Loading in progress
- Loaded - in transit
- Arrived at delivery
- Unloading
- Job completed

#### E. Photo Upload
- ✅ **Upload images for the job**
- Take photos at pickup (items condition)
- Take photos at delivery (proof of completion)
- Multiple photos per job
- Photo timestamps

#### F. Comments & Notes
- ✅ **Add comments for the job**
- Note any issues
- Special observations
- Damage reports
- Customer requests

#### G. Digital Signature
- ✅ **Customer signature on pickup**
- ✅ **Customer signature on drop off** (for completion purposes)
- Signature capture on mobile device
- Customer name entry
- Timestamp signature

#### H. Driver Features
- View completed jobs
- Earnings overview
- Payment history
- Profile management

---

## 4. Staff Access Levels

### Requirement
- ✅ **Different levels of access for each level of staff**

### Staff Roles

#### Level 1: Customer Service Staff
- View new jobs
- Assign jobs to drivers
- Communicate with customers
- View driver locations
- Update job status
- **CANNOT**: Access finance, change settings, manage drivers

#### Level 2: Management Staff
- All Customer Service permissions
- Access finance section
- View analytics and reports
- Manage drivers (add/remove/edit)
- Manage customers
- View all historical data
- **CANNOT**: Change system settings, manage admin users

#### Level 3: Admin/Owner (Super Admin)
- Full access to everything
- System settings
- User management (create staff accounts)
- Financial controls
- Delete/archive data
- API settings
- Integration management

#### Level 4: Finance Staff (Optional)
- Access to finance section only
- View payments, invoices, reports
- Process refunds
- Generate financial reports
- **CANNOT**: Assign jobs, manage drivers

#### Level 5: Driver (Mobile App Only)
- View assigned jobs only
- Update job status
- Upload photos/signatures
- Add comments
- View own earnings
- **CANNOT**: Access admin dashboard

---

## System Components Summary

### Technology Stack Needed
- **Frontend**: Website (responsive, mobile-friendly)
- **Admin Panel**: Web-based dashboard
- **Mobile App**: iOS and Android (or cross-platform)
- **Backend**: API server
- **Database**: Store all data
- **Real-time**: GPS tracking, notifications
- **Payment**: Payment gateway integration
- **Storage**: Image/document storage

### Key Integrations
- Google Maps (address autocomplete, navigation, distance calculation)
- Payment Gateway (Stripe recommended)
- SMS/Email notifications (Twilio, SendGrid)
- Cloud storage for images (AWS S3 or similar)
- GPS tracking service

---

## Questions & Clarifications Needed

### 🔴 CRITICAL - Need Client Input

#### 1. Booking & Driver Assignment Process
**Question**: When a customer books online, what happens next?
- **Option A**: Goes to "Ready to Assign" queue, admin manually assigns driver
- **Option B**: System auto-matches available driver based on location/schedule
- **For MVP**: Recommend Option A (manual) - simpler and faster to build

**Client Decision**: [ PENDING ]

---

#### 2. Driver App Platform
**Question**: Which mobile platforms?
- **Option A**: iOS only (iPhone/iPad)
- **Option B**: Android only
- **Option C**: Both iOS and Android (recommended)
- **Option D**: Progressive Web App (works on any phone browser)

**Client Decision**: [ PENDING ]

---

#### 3. Driver Job Acceptance
**Question**: Can drivers accept/reject jobs?
- **Option A**: Drivers can accept/reject when offered a job
- **Option B**: Admin assigns, driver must complete (no choice)
- **Option C**: Admin assigns but driver can request changes

**Client Decision**: [ PENDING ]

---

#### 4. Pricing System
**Question**: How are prices calculated?
- **Option A**: Instant automated quotes (algorithm-based like AnyVan)
  - Based on: distance, items, date, vehicle type
  - Customer sees price immediately
- **Option B**: Manual quotes (admin reviews and sends price)
  - Customer submits request, waits for quote

**If Option A - Need to know**:
- Base price structure?
- Price per mile?
- Price per item or volume?
- Peak date pricing (weekends, month-end)?
- Service types and different pricing?

**Client Decision**: [ PENDING ]

---

#### 5. Payment Process
**Question**: When does customer pay?

- **When**:
  - [ ] Pay immediately when booking
  - [ ] Pay later (e.g., 3 days before job)
  - [ ] Pay on completion (after job done)
  - [ ] Cash on delivery option

- **Payment Methods**:
  - [ ] Card (credit/debit)
  - [ ] Bank transfer
  - [ ] PayPal
  - [ ] Cash (driver collects)
  - [ ] Invoice (for business customers)

- **Driver Payouts**:
  - [ ] Paid per job (after completion)
  - [ ] Weekly payout
  - [ ] Bi-weekly
  - [ ] Monthly
  - How to track driver earnings?

**Client Decision**: [ PENDING ]

---

#### 6. Diary Management Details
**Question**: What features needed in diary/calendar?

- [ ] Calendar view showing all drivers' schedules
- [ ] Drag-and-drop jobs to different drivers/dates
- [ ] Driver availability calendar (days off, holidays)
- [ ] Color coding for job status
- [ ] Filter by driver, date, status
- [ ] Daily/weekly/monthly views
- [ ] Print schedule capability

**Client Decision**: [ PENDING ]

---

#### 7. Photo & Signature Requirements
**Question**: When and what photos are needed?

**Photos**:
- [ ] Photos at pickup (items condition before loading)
- [ ] Photos during loading
- [ ] Photos at delivery (items unloaded, condition)
- [ ] Photos of any damage
- [ ] Vehicle photos
- [ ] Property access photos (stairs, parking, etc.)

**Signatures**:
- [ ] Signature at pickup (customer confirms items collected)
- [ ] Signature at delivery (customer confirms completion)
- [ ] What if customer refuses to sign?
- [ ] Digital signature with customer name input

**Client Decision**: [ PENDING ]

---

#### 8. Finance Section Requirements
**Question**: What financial reports and features needed?

- [ ] Daily/weekly/monthly revenue reports
- [ ] Driver earnings breakdown (per driver)
- [ ] Outstanding payments from customers
- [ ] Completed payments
- [ ] Customer invoices (auto-generate PDF?)
- [ ] Driver payout tracking
- [ ] Expense tracking (fuel, maintenance, etc.)
- [ ] Profit/loss reports
- [ ] Tax reports
- [ ] Export to accounting software (Xero, QuickBooks?)

**Client Decision**: [ PENDING ]

---

#### 9. Customer Accounts
**Question**: Do customers need accounts?

- **Option A**: Required account (email/password)
  - See booking history
  - Manage profile
  - Save payment methods
  - Track jobs

- **Option B**: Guest checkout
  - Just email and phone
  - Faster booking
  - No login needed

- **Option C**: Both (guest or account)

**Client Decision**: [ PENDING ]

---

#### 10. Vehicle/Fleet Management
**Question**: Do you need to track vehicles?

- [ ] Assign vehicles to drivers
- [ ] Track vehicle types (small van, large van, truck)
- [ ] Vehicle capacity (cubic meters, weight)
- [ ] Vehicle registration numbers
- [ ] MOT expiry tracking
- [ ] Insurance expiry tracking
- [ ] Maintenance schedules
- [ ] Fuel tracking

**Client Decision**: [ PENDING ]

---

#### 11. Multiple Jobs Per Driver
**Question**: Can drivers have multiple jobs in one day?

- **Option A**: One job per day per driver
- **Option B**: Multiple jobs (drivers see list of today's jobs)
- **Option C**: Route optimization (system suggests order)

**Client Decision**: [ PENDING ]

---

#### 12. Customer Communication
**Question**: How do customers and drivers communicate?

- [ ] Phone only (show driver phone to customer)
- [ ] In-app messaging (chat feature)
- [ ] SMS notifications
- [ ] Email updates
- [ ] WhatsApp integration

**Client Decision**: [ PENDING ]

---

#### 13. Service Types
**Question**: What services do you offer?

- [ ] House removals (full home)
- [ ] Man and van (small moves)
- [ ] Office relocations
- [ ] Furniture delivery
- [ ] Single item delivery
- [ ] Storage services
- [ ] Packing services
- [ ] International removals
- [ ] Vehicle transport
- [ ] Other: _______________

**Client Decision**: [ PENDING ]

---

#### 14. Geographic Coverage
**Question**: Where do you operate?

- Coverage area: _______________
- Multiple cities/regions?
- Nationwide?
- International?
- Pricing different by region?

**Client Decision**: [ PENDING ]

---

#### 15. Notifications
**Question**: What notifications are needed?

**Customer Notifications**:
- [ ] Booking confirmation (email/SMS)
- [ ] Driver assigned (email/SMS)
- [ ] Driver en route (SMS)
- [ ] Driver arrived (SMS)
- [ ] Job completed (email/SMS)
- [ ] Payment receipt (email)
- [ ] Review request (email)

**Driver Notifications**:
- [ ] New job assigned (push notification/SMS)
- [ ] Job reminder (day before)
- [ ] Customer messages
- [ ] Payment received

**Admin Notifications**:
- [ ] New booking (email/SMS)
- [ ] Payment received
- [ ] Job completed
- [ ] Issues/problems
- [ ] Driver unavailable

**Client Decision**: [ PENDING ]

---

#### 16. Insurance & Legal
**Question**: Insurance and liability?

- [ ] Insurance included in price?
- [ ] Coverage amount (e.g., £50k)
- [ ] Customer can purchase additional insurance?
- [ ] Claims process needed in system?
- [ ] Terms & conditions acceptance
- [ ] Cancellation policy
- [ ] Refund policy

**Client Decision**: [ PENDING ]

---

#### 17. Additional Features Needed?
**Question**: Any other features required?

- [ ] Customer reviews/ratings for drivers
- [ ] Driver ratings for customers
- [ ] Promotional codes/discounts
- [ ] Referral program
- [ ] Loyalty program
- [ ] Business/corporate accounts
- [ ] API for third-party integrations
- [ ] Multi-language support
- [ ] Multi-currency support

**Client Decision**: [ PENDING ]

---

## System Understanding (Current Interpretation)

Based on the initial meeting, here's what we understand:

### Booking Flow
1. Customer visits website
2. Customer completes booking form (like AnyVan)
3. Customer pays online
4. Booking appears in admin "New Jobs" queue
5. Admin staff assigns booking to available driver
6. Driver receives notification on mobile app
7. Driver sees job details and navigates to pickup
8. Driver updates status throughout job
9. Driver collects customer signature at pickup
10. Driver transports items
11. Driver collects signature at delivery
12. Driver uploads photos and completes job
13. System marks job as complete
14. Driver receives payment (on payout schedule)
15. Customer receives completion notification

### Staff Workflow
1. Customer service staff log in to admin dashboard
2. See new bookings in "Ready to Assign" queue
3. Open job details
4. Select driver from list
5. Assign job to driver with date/time
6. Monitor job progress on diary/calendar
7. Track driver location on map
8. View job status updates from driver
9. Handle customer queries/issues
10. Management staff review analytics and financials

### Driver Workflow
1. Driver logs in to mobile app
2. Sees today's jobs (or upcoming jobs)
3. Views job details (addresses, contact, items)
4. Navigates to pickup location (GPS)
5. Updates status: "En route to pickup"
6. Arrives and updates: "Arrived at pickup"
7. Walks through items with customer
8. Takes photos of items
9. Customer signs on phone screen (pickup signature)
10. Loads items
11. Updates status: "In transit"
12. Navigates to delivery location
13. Updates status: "Arrived at delivery"
14. Unloads items
15. Takes delivery photos
16. Customer signs (delivery signature)
17. Adds any notes/comments
18. Marks job as complete
19. Moves to next job (if any)

### Access Control
- **Super Admin**: Can do everything
- **Manager**: Operations + finance, no system settings
- **Customer Service**: Assign jobs, customer support only
- **Finance**: View/manage payments only
- **Driver**: Mobile app, own jobs only

---

## Technical Assumptions (To Confirm)

### Platform
- Web-based admin dashboard (accessible on desktop/tablet)
- Responsive customer website (works on mobile browsers)
- Native or cross-platform mobile app for drivers
- Cloud-based system (accessible from anywhere)

### Data Storage
- Secure cloud database
- Image storage (photos)
- Document storage (signatures)
- Backup and recovery system

### Security
- Encrypted data transmission (HTTPS)
- Secure payment processing (PCI compliant)
- Role-based access control
- Secure authentication
- Data privacy (GDPR compliant if UK/EU)

### Performance
- Fast page load times (<2 seconds)
- Real-time GPS tracking
- Handle multiple concurrent users
- Scalable (grow with business)

### Support
- System documentation
- User training materials
- Technical support availability
- Bug fixes and updates

---

## Next Steps

### For Client
1. ✅ Review this document
2. ✅ Answer all questions marked [ PENDING ]
3. ✅ Confirm system understanding is correct
4. ✅ Add any missing requirements
5. ✅ Prioritize features (must-have vs nice-to-have)
6. ✅ Confirm budget and timeline

### For Development Team
1. ⏳ Wait for client clarifications
2. ⏳ Create detailed technical specification
3. ⏳ Estimate development timeline
4. ⏳ Provide cost breakdown
5. ⏳ Create project plan with milestones
6. ⏳ Begin design mockups (after approval)

---

## Meeting Notes & Additional Context

### Client Feedback
- Wants to follow AnyVan model (proven success)
- Emphasis on driver app being user-friendly
- Real-time tracking is important
- Different staff access levels critical
- Finance section needed for business management

### Business Context
- [ ] Number of drivers currently: ___
- [ ] Expected number of drivers in 6 months: ___
- [ ] Average jobs per day currently: ___
- [ ] Expected jobs per day in 6 months: ___
- [ ] Target launch date: ___
- [ ] MVP or full features first: ___

---

**Document Status**: Draft - Awaiting Client Input
**Last Updated**: January 6, 2026
**Next Review**: After client clarifications received
