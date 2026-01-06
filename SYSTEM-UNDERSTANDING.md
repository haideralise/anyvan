# System Understanding & Architecture Overview

**Date:** January 6, 2026
**Document Type:** System Understanding Based on Client Requirements
**Status:** For Client Confirmation

---

## Table of Contents

1. [System Overview](#system-overview)
2. [Three Main Components](#three-main-components)
3. [Complete User Journeys](#complete-user-journeys)
4. [System Architecture](#system-architecture)
5. [Data Flow](#data-flow)
6. [User Roles & Permissions](#user-roles--permissions)
7. [Key Features Breakdown](#key-features-breakdown)
8. [Technical Components](#technical-components)

---

## System Overview

### What We're Building

A complete **logistics and removals management platform** consisting of three interconnected systems:

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│  CUSTOMER WEBSITE  →  ADMIN DASHBOARD  →  DRIVER APP   │
│                                                         │
│  (Books jobs)         (Manages jobs)      (Executes)   │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Core Business Flow

```
Customer Books → Job Created → Admin Assigns → Driver Executes → Job Complete
```

### Key Differentiator

Following the **AnyVan model**: Simple, instant booking with transparent pricing and real-time tracking.

---

## Three Main Components

### 1. Customer Website (Public-Facing)

**Purpose**: Allow customers to book removal/delivery services online instantly

**Key Pages**:
- Homepage (hero section, services, trust signals)
- Service category pages
- Booking form (multi-step)
- Quote/price display
- Payment page
- Confirmation page
- Customer account (optional - TBC)
- My bookings (if accounts enabled)

**Technology**: Responsive web application (works on desktop, tablet, mobile)

---

### 2. Admin Dashboard (Office Staff)

**Purpose**: Central command center for managing all bookings, drivers, and business operations

**Access**: Web-based (accessible via browser on desktop/laptop/tablet)

**Main Sections**:

#### A. Dashboard Home
- Today's overview
- Active jobs count
- New bookings count
- Drivers on duty
- Revenue today
- Quick actions

#### B. New Jobs (Ready to Assign)
- Queue of unassigned bookings
- Job details visible
- Assign to driver action
- Filter/search capabilities

#### C. Assigned Jobs
- All jobs with drivers
- Status tracking
- Reassignment capability
- Job details view

#### D. Diary Management
- Calendar view (day/week/month)
- All drivers' schedules
- Job allocation visualization
- Drag-drop (TBC)
- Driver availability

#### E. Live Tracking
- Map view
- All active drivers' locations
- Real-time updates
- Driver status indicators

#### F. Drivers Management
- Driver list
- Add/edit/remove drivers
- Driver details (contact, vehicle, docs)
- Performance metrics
- Availability calendar

#### G. Customers Management
- Customer list
- Booking history per customer
- Contact details
- Notes

#### H. Finance Section
- Revenue dashboard
- Payments received
- Outstanding payments
- Driver earnings
- Payouts
- Invoices
- Financial reports

#### I. Analytics & Reports
- Booking statistics
- Revenue trends
- Driver performance
- Service breakdown
- Custom reports
- Export data

#### J. Settings
- Business settings
- Pricing configuration
- Staff user management
- System preferences
- Integrations

---

### 3. Driver Mobile App

**Purpose**: Enable drivers to manage jobs, navigate, and complete deliveries efficiently

**Platform**: iOS and/or Android (TBC)

**Main Screens**:

#### A. Login
- Username/password
- Secure authentication
- Remember me option

#### B. Today's Jobs (Dashboard)
- List of assigned jobs
- Time-ordered
- Job card preview (time, location, customer)
- Status indicators

#### C. Job Details
- **Pickup Information**:
  - Address
  - Contact name
  - Phone number (tap to call)
  - Special instructions
  - Access notes
- **Delivery Information**:
  - Address
  - Contact name
  - Phone number
  - Special instructions
- **Items List**:
  - What needs moving
  - Quantity
  - Special handling notes
- **Navigation**:
  - Button to open Google Maps
  - Distance and estimated time

#### D. Job Execution Workflow
- Status update buttons:
  - [ ] Start job
  - [ ] En route to pickup
  - [ ] Arrived at pickup
  - [ ] Loading
  - [ ] In transit
  - [ ] Arrived at delivery
  - [ ] Unloading
  - [ ] Complete job

#### E. Photos Section
- Camera access
- Take multiple photos
- Label photos (pickup/delivery/damage)
- Upload to system
- View uploaded photos

#### F. Signature Capture
- Digital signature pad
- Customer name input
- Capture at pickup
- Capture at delivery
- Save with timestamp

#### G. Notes & Comments
- Text input field
- Voice-to-text (optional)
- Add observations
- Report issues
- Save notes

#### H. Completed Jobs
- History of finished jobs
- View details
- View photos/signatures
- Earnings per job

#### I. Earnings
- Today/week/month earnings
- Payment history
- Pending payments

#### J. Profile
- Driver info
- Vehicle details
- Change password
- Settings

---

## Complete User Journeys

### Journey 1: Customer Booking Process

```
CUSTOMER SIDE:
┌─────────────────────────────────────────────┐
│ 1. Visit website                            │
│    └─ Homepage with "Get a quote" button    │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 2. Select service type                      │
│    └─ House removal / Man & van / Other     │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 3. Quote Form - Step 1: WHAT                │
│    └─ Select items / room count             │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 4. Quote Form - Step 2: WHERE               │
│    └─ Pickup address + Delivery address     │
│    └─ Access details (stairs, parking)      │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 5. Quote Form - Step 3: WHEN                │
│    └─ Select date and time                  │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 6. Quote Form - Step 4: EXTRAS              │
│    └─ Packing, insurance, etc. (optional)   │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 7. Instant Quote Display                    │
│    └─ Price shown: £XXX                     │
│    └─ Breakdown: distance, items, extras    │
│    └─ "Book Now" button                     │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 8. Customer Details                         │
│    └─ Name, email, phone                    │
│    └─ Create account OR guest checkout      │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 9. Payment                                  │
│    └─ Enter card details                    │
│    └─ Process payment                       │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 10. Confirmation                            │
│     └─ Booking reference number             │
│     └─ Email confirmation sent              │
│     └─ SMS confirmation sent                │
└─────────────────────────────────────────────┘
```

```
ADMIN SIDE (After Customer Books):
┌─────────────────────────────────────────────┐
│ 11. Job appears in "New Jobs" queue         │
│     └─ Admin sees notification              │
│     └─ Job details visible                  │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 12. Admin reviews job                       │
│     └─ Check details                        │
│     └─ Select available driver              │
│     └─ Assign job to driver                 │
└─────────────────────────────────────────────┘
```

```
DRIVER SIDE (After Assignment):
┌─────────────────────────────────────────────┐
│ 13. Driver receives notification            │
│     └─ Push notification: "New job"         │
│     └─ Opens mobile app                     │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 14. Driver views job details                │
│     └─ Pickup/delivery addresses            │
│     └─ Customer contact                     │
│     └─ Items list                           │
└─────────────────────────────────────────────┘
```

```
CUSTOMER SIDE (After Assignment):
┌─────────────────────────────────────────────┐
│ 15. Customer receives notification          │
│     └─ Email: "Driver assigned"             │
│     └─ Driver name and contact              │
│     └─ Vehicle details                      │
└─────────────────────────────────────────────┘
```

---

### Journey 2: Job Execution (Move Day)

```
DRIVER APP WORKFLOW:
┌─────────────────────────────────────────────┐
│ 1. Driver logs in to app (morning)          │
│    └─ Sees today's jobs                     │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 2. Opens job details                        │
│    └─ Reviews pickup address                │
│    └─ Taps "Navigate" → Opens Google Maps   │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 3. Updates status: "En route to pickup"     │
│    └─ GPS tracking starts                   │
│    └─ Admin sees driver location on map     │
│    └─ Customer gets notification (optional) │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 4. Arrives at pickup location               │
│    └─ Updates status: "Arrived at pickup"   │
│    └─ Customer notified (SMS)               │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 5. Meets customer                           │
│    └─ Reviews items to move                 │
│    └─ Takes photos of items (before)        │
│    └─ Opens signature screen                │
│    └─ Customer signs on phone               │
│    └─ Signature saved with timestamp        │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 6. Loading items                            │
│    └─ Updates status: "Loading"             │
│    └─ Loads items into vehicle              │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 7. Departs for delivery                     │
│    └─ Updates status: "In transit"          │
│    └─ GPS tracking continues                │
│    └─ Navigate to delivery address          │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 8. Arrives at delivery location             │
│    └─ Updates status: "Arrived at delivery" │
│    └─ Customer notified                     │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 9. Unloading                                │
│    └─ Updates status: "Unloading"           │
│    └─ Unloads items carefully               │
│    └─ Places items as requested             │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 10. Completion process                      │
│     └─ Takes photos (items delivered)       │
│     └─ Adds any notes/comments              │
│     └─ Customer signs delivery confirmation │
│     └─ Updates status: "Job complete"       │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 11. Job finished                            │
│     └─ Job moves to "Completed"             │
│     └─ Driver sees earnings updated         │
│     └─ Admin sees job marked complete       │
│     └─ Customer receives confirmation       │
└─────────────────────────────────────────────┘
```

---

### Journey 3: Admin Staff Managing Jobs

```
MORNING ROUTINE:
┌─────────────────────────────────────────────┐
│ 1. Admin logs in to dashboard               │
│    └─ Sees today's overview                 │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 2. Checks "New Jobs" section                │
│    └─ 5 new bookings from overnight         │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 3. Opens first job                          │
│    └─ Reviews details:                      │
│        • Pickup: SW1 2AA                    │
│        • Delivery: SE1 9SG                  │
│        • Date: Tomorrow                     │
│        • Items: 2-bed flat                  │
│        • Price: £280                        │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 4. Checks driver availability               │
│    └─ Opens diary/calendar                  │
│    └─ Sees which drivers are free tomorrow  │
│    └─ Checks driver locations               │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 5. Assigns job to driver                    │
│    └─ Selects "Driver: John Smith"          │
│    └─ Sets time: 9:00 AM                    │
│    └─ Clicks "Assign"                       │
│    └─ Confirmation: "Job assigned to John"  │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 6. Repeats for other new jobs               │
│    └─ Assigns all 5 jobs to drivers         │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 7. Monitors active jobs (during day)        │
│    └─ Live tracking map shows driver locs   │
│    └─ Sees job status updates in real-time  │
│    └─ Customer calls with question → helps  │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│ 8. End of day review                        │
│    └─ Checks completed jobs                 │
│    └─ Reviews any issues/notes              │
│    └─ Prepares tomorrow's schedule          │
└─────────────────────────────────────────────┘
```

---

## System Architecture

### High-Level Architecture

```
┌────────────────────────────────────────────────────────────┐
│                     USERS                                  │
├────────────────────────────────────────────────────────────┤
│                                                            │
│  Customers        Admin Staff          Drivers            │
│  (Web Browser)    (Web Browser)        (Mobile App)       │
│                                                            │
└───────┬────────────────┬─────────────────────┬────────────┘
        │                │                     │
        │ HTTPS          │ HTTPS               │ HTTPS/WSS
        │                │                     │
┌───────▼────────────────▼─────────────────────▼────────────┐
│                   LOAD BALANCER / CDN                      │
│                   (SSL Termination)                        │
└───────┬────────────────┬─────────────────────┬────────────┘
        │                │                     │
┌───────▼────────┐ ┌─────▼──────────┐ ┌───────▼────────────┐
│   CUSTOMER     │ │     ADMIN      │ │    DRIVER API      │
│   WEB APP      │ │   DASHBOARD    │ │   (Mobile API)     │
│   (Frontend)   │ │   (Frontend)   │ │                    │
└───────┬────────┘ └─────┬──────────┘ └───────┬────────────┘
        │                │                     │
        └────────────────┴─────────────────────┘
                         │
        ┌────────────────▼─────────────────────┐
        │        API GATEWAY / BACKEND         │
        │         (Node.js / NestJS)           │
        │                                      │
        │  ┌──────────────────────────────┐   │
        │  │  Authentication Service      │   │
        │  │  Booking Service             │   │
        │  │  Driver Service              │   │
        │  │  Payment Service             │   │
        │  │  Notification Service        │   │
        │  │  GPS Tracking Service        │   │
        │  │  File Upload Service         │   │
        │  └──────────────────────────────┘   │
        └────────────────┬─────────────────────┘
                         │
        ┌────────────────┴─────────────────────┐
        │                                      │
┌───────▼─────────┐  ┌────────▼──────────┐  ┌▼────────────┐
│   PostgreSQL    │  │      Redis        │  │  AWS S3     │
│   (Database)    │  │    (Cache)        │  │  (Images)   │
│                 │  │   (Sessions)      │  │             │
│  • Bookings     │  │   (Real-time)     │  │ • Photos    │
│  • Drivers      │  │                   │  │ • Signatures│
│  • Customers    │  │                   │  │ • Documents │
│  • Payments     │  │                   │  │             │
└─────────────────┘  └───────────────────┘  └─────────────┘
                         │
        ┌────────────────┴─────────────────────┐
        │                                      │
┌───────▼─────────┐  ┌────────▼──────────┐  ┌▼────────────┐
│   Google Maps   │  │     Stripe        │  │  Twilio     │
│   (Navigation)  │  │   (Payments)      │  │   (SMS)     │
└─────────────────┘  └───────────────────┘  └─────────────┘
```

---

## Data Flow

### 1. Booking Creation Flow

```
Customer Website → API Server → Database → Admin Dashboard

Step-by-step:
1. Customer fills form on website
2. Frontend validates input
3. Frontend sends POST request to API
4. API validates data
5. API calculates price
6. API processes payment (Stripe)
7. API creates booking record in database
8. API sends confirmation email (via email service)
9. API sends SMS notification (via Twilio)
10. Admin dashboard receives real-time update (via WebSocket)
11. Admin sees new booking appear in queue
```

### 2. Job Assignment Flow

```
Admin Dashboard → API Server → Database → Driver App

Step-by-step:
1. Admin selects driver from dropdown
2. Admin clicks "Assign"
3. Frontend sends PUT request to API
4. API updates booking record (driver_id, status)
5. API sends push notification to driver app
6. Driver app receives notification
7. Driver sees new job in "Today's Jobs"
8. API sends email/SMS to customer ("Driver assigned")
```

### 3. GPS Tracking Flow

```
Driver App → API Server → Redis Cache → Admin Dashboard

Step-by-step:
1. Driver app tracks GPS location (every 30 seconds)
2. App sends location update to API
3. API stores location in Redis (fast, temporary)
4. Admin dashboard polls/subscribes for location updates
5. Dashboard displays driver position on map in real-time
```

### 4. Photo Upload Flow

```
Driver App → API Server → AWS S3 → Database

Step-by-step:
1. Driver takes photo in app
2. App compresses image
3. App sends image to API (multipart/form-data)
4. API validates image
5. API uploads to S3 bucket
6. S3 returns URL
7. API saves URL in database (linked to booking)
8. Driver sees upload confirmation
9. Admin can view photos in booking details
```

### 5. Signature Capture Flow

```
Driver App → API Server → AWS S3 → Database

Step-by-step:
1. Customer signs on driver's phone screen
2. App captures signature (canvas drawing)
3. App converts to image (PNG)
4. App uploads to API
5. API saves to S3
6. API records signature details in database:
   - Booking ID
   - Type (pickup/delivery)
   - Timestamp
   - Customer name
   - Image URL
7. Signature stored as proof of completion
```

---

## User Roles & Permissions

### Detailed Permission Matrix

| Feature | Customer | Driver | Customer Service | Manager | Finance | Super Admin |
|---------|----------|--------|------------------|---------|---------|-------------|
| **BOOKING** |
| Create booking | ✅ | ❌ | ✅ (on behalf) | ✅ | ❌ | ✅ |
| View own bookings | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ |
| View all bookings | ❌ | ❌ | ✅ | ✅ | ✅ (read-only) | ✅ |
| Edit booking | ✅ (before assigned) | ❌ | ✅ | ✅ | ❌ | ✅ |
| Cancel booking | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ |
| **DRIVER MANAGEMENT** |
| Assign driver to job | ❌ | ❌ | ✅ | ✅ | ❌ | ✅ |
| View driver locations | ❌ | ❌ | ✅ | ✅ | ❌ | ✅ |
| Add/edit driver | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ |
| Delete driver | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |
| View driver performance | ❌ | ✅ (own) | ✅ | ✅ | ❌ | ✅ |
| **JOB EXECUTION** |
| View assigned jobs | ❌ | ✅ (own only) | ✅ (all) | ✅ (all) | ❌ | ✅ |
| Update job status | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ |
| Upload photos | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ |
| Capture signature | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ |
| Add notes/comments | ❌ | ✅ | ✅ | ✅ | ❌ | ✅ |
| **FINANCE** |
| View revenue | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ |
| Process payments | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ |
| View driver earnings | ❌ | ✅ (own) | ❌ | ✅ | ✅ | ✅ |
| Process payouts | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |
| Generate invoices | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ |
| Financial reports | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ |
| **ANALYTICS** |
| View basic stats | ❌ | ❌ | ✅ | ✅ | ❌ | ✅ |
| View detailed analytics | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ |
| Export reports | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ |
| **SETTINGS** |
| View settings | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |
| Edit pricing | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |
| Manage staff users | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |
| System configuration | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |
| **COMMUNICATION** |
| Contact driver | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ |
| Contact customer | ❌ | ✅ | ✅ | ✅ | ❌ | ✅ |
| View messages | ✅ (own) | ✅ (own) | ✅ (all) | ✅ (all) | ❌ | ✅ |

---

## Key Features Breakdown

### Customer Website Features

#### 1. Homepage
```
Components:
- Hero section
  └─ Headline: "Move anything, anywhere"
  └─ Subheading: "Instant quotes in 2 minutes"
  └─ CTA button: "Get a quote"

- Service categories (cards)
  └─ House removals
  └─ Man and van
  └─ Office moves
  └─ Furniture delivery

- How it works (3 steps)
  └─ 1. Get instant quote
  └─ 2. Book online
  └─ 3. We deliver

- Trust signals
  └─ Reviews/ratings
  └─ Number of completed moves
  └─ Insurance coverage
  └─ Professional drivers

- Footer
  └─ About us
  └─ Services
  └─ Contact
  └─ Terms & Privacy
```

#### 2. Booking Form (Multi-Step)
```
Step 1: What are you moving?
└─ Radio buttons: Studio / 1-bed / 2-bed / 3-bed / 4+ bed / Custom
└─ If Custom: Item selector (furniture catalog)
└─ Quantity inputs
└─ Special items (piano, antiques, etc.)
└─ "Next" button

Step 2: Where are you moving?
└─ Pickup address input (Google autocomplete)
└─ Floor level dropdown
└─ Parking availability checkbox
└─ Access notes textarea
└─ Delivery address input
└─ Floor level dropdown
└─ Parking availability checkbox
└─ Access notes textarea
└─ Distance calculation (auto)
└─ "Next" button

Step 3: When do you need this?
└─ Date picker (calendar)
└─ Time slot selection (Morning/Afternoon/Evening/Flexible)
└─ "Next" button

Step 4: Extras (optional)
└─ Packing service checkbox (+£XX)
└─ Packing materials checkbox (+£XX)
└─ Assembly/disassembly checkbox (+£XX)
└─ Extra insurance checkbox (+£XX)
└─ Storage checkbox (+£XX)
└─ "Get Quote" button

Quote Display:
└─ Large price display: £XXX
└─ Price breakdown (collapsible)
└─ What's included (list)
└─ "Book Now" button
└─ "Edit details" link
```

#### 3. Booking Confirmation
```
Components:
- Customer details form
  └─ Name
  └─ Email
  └─ Phone
  └─ (Create account checkbox - optional)

- Payment form
  └─ Card number
  └─ Expiry
  └─ CVV
  └─ Billing address
  └─ Save card checkbox

- Booking summary (sidebar)
  └─ Service type
  └─ Pickup & delivery
  └─ Date & time
  └─ Items
  └─ Price
  └─ Edit links

- Terms acceptance
  └─ Checkbox: "I agree to T&Cs"

- "Confirm & Pay" button
```

---

### Admin Dashboard Features

#### 1. Dashboard Home (Overview)
```
Widgets:
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ Today's Jobs    │ │ Active Drivers  │ │ Revenue Today   │
│      12         │ │       8         │ │    £2,450       │
└─────────────────┘ └─────────────────┘ └─────────────────┘

┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ New Bookings    │ │ Completed Jobs  │ │ Pending Jobs    │
│       5         │ │       7         │ │       10        │
└─────────────────┘ └─────────────────┘ └─────────────────┘

Recent Activity Feed:
- 10:45 AM - New booking received (#1234)
- 10:30 AM - Job completed by John Smith (#1230)
- 10:15 AM - Payment received from Sarah M.
- 10:00 AM - Driver Tom en route to pickup

Quick Actions:
[+ New Booking] [Assign Jobs] [View Drivers]
```

#### 2. New Jobs Queue
```
Table Layout:
┌────────┬──────────┬─────────┬──────────┬────────┬─────────┐
│ Ref    │ Customer │ Date    │ Route    │ Price  │ Actions │
├────────┼──────────┼─────────┼──────────┼────────┼─────────┤
│ #1234  │ Sarah M. │ 15 Jan  │ SW1→SE1  │ £280   │ [Assign]│
│ #1235  │ John D.  │ 16 Jan  │ W2→E14   │ £350   │ [Assign]│
│ #1236  │ Emily R. │ 16 Jan  │ N1→NW3   │ £420   │ [Assign]│
└────────┴──────────┴─────────┴──────────┴────────┴─────────┘

Filters:
[All Services ▼] [All Dates ▼] [Search...]

Click "Assign" → Opens modal:
┌─────────────────────────────────────┐
│ Assign Job #1234                    │
├─────────────────────────────────────┤
│ Customer: Sarah M.                  │
│ Date: 15 Jan, Morning               │
│ Route: SW1 2AA → SE1 9SG (8 miles) │
│ Items: 2-bed flat                   │
│                                     │
│ Select Driver:                      │
│ [John Smith        ▼]               │
│                                     │
│ Available drivers for this date:    │
│ ✓ John Smith (2 jobs)               │
│ ✓ Mike Johnson (1 job)              │
│ ✓ Tom Williams (0 jobs)             │
│                                     │
│ [Cancel] [Assign to John Smith]     │
└─────────────────────────────────────┘
```

#### 3. Diary Management (Calendar)
```
Calendar View:

┌──────────────────────────────────────────────────────────┐
│ [< Previous] [  Week of 15-21 Jan 2026  ] [Next >]       │
│                                                           │
│ [Day] [Week] [Month]                 [+ Add Booking]     │
├──────────────────────────────────────────────────────────┤
│         Mon 15  Tue 16  Wed 17  Thu 18  Fri 19  Sat 20  │
├──────────────────────────────────────────────────────────┤
│ John    ■■■     ■■■■    ■■      ■■■■    ■■■■    ■■■■    │
│ Smith   9-12    9-1pm   9-11    8-12    9-1pm   8-12    │
│         #1234   #1240   #1248   #1255   #1260   #1268   │
│                                                           │
│ Mike    ■■■■            ■■■     ■■■■                      │
│ Johnson 8-12            9-12    10-2                     │
│         #1235           #1250   #1258                    │
│                                                           │
│ Tom     ■■■     ■■■■    ■■■                               │
│ Williams 10-1   8-11    1-4                              │
│         #1238   #1242   #1252                            │
└──────────────────────────────────────────────────────────┘

Legend: ■ = Job assigned   [Empty] = Available

Click on job block → Shows job details popup
Drag job to different slot → Reassigns (TBC)
```

#### 4. Live Tracking Map
```
Map Interface:

┌──────────────────────────────────────────────────────────┐
│ [Filters: All Drivers ▼] [Refresh: 30s ▼] [Fullscreen]  │
├──────────────────────────────────────────────────────────┤
│                                                           │
│              🗺️  Google Map                              │
│                                                           │
│         📍 Driver: John (en route)                       │
│           Job #1234: SW1 → SE1                           │
│                                                           │
│         📍 Driver: Mike (at pickup)                      │
│           Job #1235: W2 → E14                            │
│                                                           │
│         📍 Driver: Tom (in transit)                      │
│           Job #1238: N1 → NW3                            │
│                                                           │
└──────────────────────────────────────────────────────────┘

Sidebar:
┌────────────────────────┐
│ Active Drivers (3)     │
├────────────────────────┤
│ 🟢 John Smith          │
│    Job #1234           │
│    Status: En route    │
│    Last update: 2m ago │
├────────────────────────┤
│ 🟢 Mike Johnson        │
│    Job #1235           │
│    Status: At pickup   │
│    Last update: 1m ago │
├────────────────────────┤
│ 🟢 Tom Williams        │
│    Job #1238           │
│    Status: In transit  │
│    Last update: 3m ago │
└────────────────────────┘
```

#### 5. Finance Dashboard
```
Overview:

┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ Today's Revenue │ │ This Week       │ │ This Month      │
│    £2,450       │ │    £18,500      │ │    £65,200      │
└─────────────────┘ └─────────────────┘ └─────────────────┘

┌─────────────────────────────────────────────────────────┐
│ Revenue Chart (Last 30 Days)                            │
│                                                         │
│ £3k │     ███                                           │
│     │    ████ ███                                       │
│ £2k │   █████████  ███                                  │
│     │ ██████████████████                                │
│ £1k │██████████████████████                             │
│     └────────────────────────────────────────           │
│      1  5  10  15  20  25  30                          │
└─────────────────────────────────────────────────────────┘

Recent Transactions:
┌────────┬──────────┬─────────┬──────────┬─────────────┐
│ Date   │ Ref      │ Customer│ Amount   │ Status      │
├────────┼──────────┼─────────┼──────────┼─────────────┤
│ 6 Jan  │ #1234    │ Sarah M.│ £280.00  │ ✓ Paid      │
│ 6 Jan  │ #1230    │ John D. │ £350.00  │ ✓ Paid      │
│ 5 Jan  │ #1225    │ Emily R.│ £420.00  │ ✓ Paid      │
│ 5 Jan  │ #1220    │ Tom S.  │ £190.00  │ ⏳ Pending  │
└────────┴──────────┴─────────┴──────────┴─────────────┘

Driver Payouts:
┌────────────┬───────────┬──────────┬────────────────┐
│ Driver     │ Jobs      │ Earnings │ Next Payout    │
├────────────┼───────────┼──────────┼────────────────┤
│ John Smith │ 7         │ £1,260   │ Fri 10 Jan     │
│ Mike J.    │ 5         │ £980     │ Fri 10 Jan     │
│ Tom W.     │ 4         │ £720     │ Fri 10 Jan     │
└────────────┴───────────┴──────────┴────────────────┘
```

---

### Driver Mobile App Features

#### App Screens Breakdown

**1. Login Screen**
```
┌─────────────────────────┐
│                         │
│     🚚 [Company Logo]   │
│                         │
│  Driver Login           │
│                         │
│  Username:              │
│  [__________________]   │
│                         │
│  Password:              │
│  [__________________]   │
│                         │
│  [ ] Remember me        │
│                         │
│  [    LOGIN    ]        │
│                         │
│  Forgot password?       │
│                         │
└─────────────────────────┘
```

**2. Today's Jobs (Dashboard)**
```
┌─────────────────────────┐
│ ☰  Today's Jobs    [👤] │
├─────────────────────────┤
│ Monday, 15 Jan 2026     │
│                         │
│ 3 jobs scheduled        │
├─────────────────────────┤
│ 🟢 ACTIVE               │
│ Job #1234               │
│ 9:00 AM - 12:00 PM      │
│ SW1 2AA → SE1 9SG       │
│ Sarah Mitchell          │
│ 2-bed flat              │
│ [View Details]          │
├─────────────────────────┤
│ ⏳ UPCOMING             │
│ Job #1240               │
│ 2:00 PM - 5:00 PM       │
│ W2 1AA → E14 5AB        │
│ John Davis              │
│ Office equipment        │
│ [View Details]          │
├─────────────────────────┤
│ ⏳ UPCOMING             │
│ Job #1245               │
│ 6:00 PM - 8:00 PM       │
│ N1 9AG → NW3 5QY        │
│ Emily Roberts           │
│ Furniture delivery      │
│ [View Details]          │
└─────────────────────────┘

Bottom Nav:
[🏠 Jobs] [✓ Completed] [💰 Earnings] [👤 Profile]
```

**3. Job Details Screen**
```
┌─────────────────────────┐
│ ← Job #1234        [⋮]  │
├─────────────────────────┤
│ Status: En route        │
│ [●●●●○○○○] 50%         │
├─────────────────────────┤
│                         │
│ 📍 PICKUP               │
│ 123 Victoria Street     │
│ London SW1 2AA          │
│ 3rd Floor, No lift      │
│ Parking: Street (free)  │
│                         │
│ [📞 Call] [🗺️ Navigate]│
├─────────────────────────┤
│ 📍 DELIVERY             │
│ 45 London Bridge St     │
│ London SE1 9SG          │
│ Ground floor            │
│ Parking: Permit needed  │
│                         │
│ [📞 Call] [🗺️ Navigate]│
├─────────────────────────┤
│ 👤 CUSTOMER             │
│ Sarah Mitchell          │
│ 📞 07700 900123         │
│ 📧 sarah@email.com      │
│                         │
│ [📞 Call] [💬 Message]  │
├─────────────────────────┤
│ 📦 ITEMS                │
│ • 1x 3-seater sofa      │
│ • 1x Coffee table       │
│ • 2x Armchairs          │
│ • 1x Dining table       │
│ • 4x Dining chairs      │
│ • 1x Double bed         │
│ • 1x Wardrobe (large)   │
│ [View full list]        │
├─────────────────────────┤
│ 📝 NOTES                │
│ "Piano requires extra   │
│ care. Stairwell narrow."│
├─────────────────────────┤
│                         │
│ [  Update Status  ]     │
│ [  Add Photos    ]      │
│ [  Get Signature ]      │
│ [  Add Notes     ]      │
│                         │
└─────────────────────────┘
```

**4. Status Update Screen**
```
┌─────────────────────────┐
│ ← Update Job Status     │
├─────────────────────────┤
│ Job #1234               │
│ Current: En route       │
├─────────────────────────┤
│                         │
│ Select new status:      │
│                         │
│ ⭕ Start job            │
│ ✓ En route to pickup    │
│ ⭕ Arrived at pickup     │
│ ⭕ Loading               │
│ ⭕ In transit            │
│ ⭕ Arrived at delivery   │
│ ⭕ Unloading             │
│ ⭕ Job complete          │
│                         │
│ [   Update Status   ]   │
│                         │
└─────────────────────────┘
```

**5. Photo Upload Screen**
```
┌─────────────────────────┐
│ ← Upload Photos         │
├─────────────────────────┤
│ Job #1234               │
├─────────────────────────┤
│                         │
│ Pickup Photos (3)       │
│ ┌───┐ ┌───┐ ┌───┐      │
│ │📷 │ │📷 │ │📷 │      │
│ └───┘ └───┘ └───┘      │
│ 10:05 10:06 10:08       │
│                         │
│ [+ Take Photo]          │
│ [+ From Gallery]        │
├─────────────────────────┤
│ Delivery Photos (2)     │
│ ┌───┐ ┌───┐            │
│ │📷 │ │📷 │            │
│ └───┘ └───┘            │
│ 11:45 11:47             │
│                         │
│ [+ Take Photo]          │
│ [+ From Gallery]        │
├─────────────────────────┤
│                         │
│ [   Upload All   ]      │
│                         │
└─────────────────────────┘
```

**6. Signature Capture Screen**
```
┌─────────────────────────┐
│ ← Customer Signature    │
├─────────────────────────┤
│ Job #1234               │
│ Type: ⭕Pickup ⭕Delivery│
├─────────────────────────┤
│ Customer name:          │
│ [Sarah Mitchell______]  │
│                         │
│ Sign below:             │
│ ┌─────────────────────┐ │
│ │                     │ │
│ │   [Signature area]  │ │
│ │                     │ │
│ │                     │ │
│ └─────────────────────┘ │
│                         │
│ [Clear] [Save Signature]│
│                         │
│ By signing, customer    │
│ confirms items          │
│ received/delivered.     │
│                         │
└─────────────────────────┘
```

**7. Add Notes Screen**
```
┌─────────────────────────┐
│ ← Add Notes             │
├─────────────────────────┤
│ Job #1234               │
├─────────────────────────┤
│                         │
│ Notes/Comments:         │
│ ┌─────────────────────┐ │
│ │                     │ │
│ │                     │ │
│ │                     │ │
│ │                     │ │
│ │                     │ │
│ └─────────────────────┘ │
│ [🎤 Voice to text]      │
│                         │
│ Quick options:          │
│ [Heavy traffic]         │
│ [Difficult access]      │
│ [Extra items]           │
│ [Customer not ready]    │
│                         │
│ [   Save Notes   ]      │
│                         │
└─────────────────────────┘
```

**8. Completed Jobs**
```
┌─────────────────────────┐
│ ☰  Completed Jobs  [👤] │
├─────────────────────────┤
│ This Week: 7 jobs       │
│ Earnings: £1,260        │
├─────────────────────────┤
│ ✓ Job #1234  Mon 15 Jan │
│ SW1 → SE1               │
│ Earned: £180            │
│ [View Details]          │
├─────────────────────────┤
│ ✓ Job #1230  Mon 15 Jan │
│ W2 → E14                │
│ Earned: £210            │
│ [View Details]          │
├─────────────────────────┤
│ ✓ Job #1228  Sun 14 Jan │
│ N1 → NW3                │
│ Earned: £250            │
│ [View Details]          │
├─────────────────────────┤
│                         │
│ [Load More]             │
│                         │
└─────────────────────────┘
```

**9. Earnings Screen**
```
┌─────────────────────────┐
│ ☰  Earnings        [👤] │
├─────────────────────────┤
│ This Week               │
│ £1,260.00               │
│ 7 jobs completed        │
├─────────────────────────┤
│ [Today] [Week] [Month]  │
├─────────────────────────┤
│ Mon 15 Jan: £390 (2)    │
│ Sun 14 Jan: £250 (1)    │
│ Sat 13 Jan: £410 (2)    │
│ Fri 12 Jan: £210 (1)    │
│ Thu 11 Jan: £0 (0)      │
├─────────────────────────┤
│ 💰 NEXT PAYOUT          │
│ Friday, 19 January      │
│ £1,260.00               │
│ Bank: ****4567          │
├─────────────────────────┤
│ Payment History         │
│ 12 Jan: £980 ✓ Paid     │
│ 5 Jan: £1,150 ✓ Paid    │
│ [View All]              │
└─────────────────────────┘
```

**10. Profile Screen**
```
┌─────────────────────────┐
│ ☰  Profile         [👤] │
├─────────────────────────┤
│     [Profile Photo]     │
│                         │
│ John Smith              │
│ Driver since 2023       │
│ ⭐ 4.8 (247 jobs)       │
├─────────────────────────┤
│ 📧 john@email.com       │
│ 📞 07700 900456         │
├─────────────────────────┤
│ 🚚 Vehicle              │
│ Mercedes Sprinter       │
│ Reg: AB12 CDE           │
│ Capacity: 12m³          │
├─────────────────────────┤
│ [Edit Profile]          │
│ [Change Password]       │
│ [Notification Settings] │
│ [Help & Support]        │
│ [Terms & Privacy]       │
│ [Logout]                │
│                         │
└─────────────────────────┘
```

---

## Technical Components

### Required Technologies

**Frontend (Web)**:
- React.js / Next.js (website + admin)
- Tailwind CSS (styling)
- Google Maps JavaScript API
- Stripe.js (payments)
- Socket.io-client (real-time updates)

**Mobile App**:
- React Native (iOS + Android)
- OR Flutter (cross-platform)
- OR Native (Swift for iOS, Kotlin for Android)
- GPS/Location services
- Camera integration
- Signature capture library

**Backend**:
- Node.js (Express or NestJS)
- OR Python (Django/FastAPI)
- RESTful API
- WebSocket server (real-time)
- JWT authentication

**Database**:
- PostgreSQL (primary database)
- Redis (caching, sessions, real-time)

**Cloud Services**:
- AWS S3 (image storage)
- OR Cloudflare R2
- OR Google Cloud Storage

**Third-Party APIs**:
- Google Maps API (geocoding, distance, navigation)
- Stripe (payment processing)
- Twilio (SMS notifications)
- SendGrid / AWS SES (email notifications)
- Firebase Cloud Messaging (push notifications)

**Infrastructure**:
- Cloud hosting (AWS, Google Cloud, or Azure)
- OR Platform-as-a-Service (Railway, Render, Heroku)
- CDN (Cloudflare)
- SSL certificate
- Database backups
- Monitoring (Sentry, Datadog)

---

## Next Steps

### ✅ Client Actions Required

1. **Review this document** - Ensure system understanding is correct
2. **Answer questions** in CLIENT-REQUIREMENTS.md
3. **Prioritize features** - Must-have vs nice-to-have
4. **Confirm business details**:
   - Number of current drivers
   - Expected growth
   - Budget range
   - Target launch date
5. **Approve technical approach** once clarified

### ⏳ Development Team Actions (After Approval)

1. Create detailed technical specification
2. Design database schema
3. Create UI/UX mockups
4. Estimate timeline and costs
5. Propose development phases (MVP → Full platform)
6. Begin development

---

**Document Status**: Draft - Awaiting Client Confirmation
**Last Updated**: January 6, 2026
