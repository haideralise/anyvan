# AnyVan Platform - Complete Requirements Document

**Version:** 1.0
**Date:** January 6, 2026
**Document Type:** Technical & Business Requirements

---

## Table of Contents

1. [Executive Summary](#executive-summary)
2. [Business Model](#business-model)
3. [Core Features](#core-features)
4. [User Flows](#user-flows)
5. [Technical Architecture](#technical-architecture)
6. [Database Schema](#database-schema)
7. [Third-Party Integrations](#third-party-integrations)
8. [UI/UX Requirements](#uiux-requirements)
9. [Technical Stack](#technical-stack)
10. [Development Roadmap](#development-roadmap)
11. [Success Metrics](#success-metrics)

---

## Executive Summary

AnyVan is a **two-sided logistics marketplace** connecting customers who need transport/moving services with transport providers (removal companies, man-and-van operators, couriers). The platform optimizes unused transport capacity by matching jobs with providers' existing routes, offering customers up to 40% savings compared to traditional movers.

### Key Value Propositions

**For Customers:**
- Instant online quotes (<2 minutes)
- Up to 40% cheaper than traditional movers
- Price match guarantee
- Book now, pay later (payment 3 days before move)
- Free cancellation (up to 48 hours)
- £50k insurance included
- Vetted, rated providers

**For Providers:**
- Access to consistent job flow
- Route optimization (backhaul matching)
- Reduced empty miles
- Easy job management
- Automated payments
- Marketing platform

---

## Business Model

### Revenue Model
- **Commission-based**: 15-25% commission on each completed booking
- **Marketplace efficiency**: Monetizes by matching jobs with providers' existing routes
- **Value creation**: Reduces wasted miles, benefiting both customers (price) and providers (earnings)

### Market Opportunity
- **Target Market**: UK & European removals/logistics market
- **Customer Segments**:
  - Residential movers (house removals, student moves)
  - Small business (office relocations)
  - E-commerce/Retail (furniture delivery)
  - Vehicle transport
  - Storage seekers
- **Geographic Focus**: UK initially, expand to EU (Germany, France, Spain, Italy, Ireland)

### Competitive Advantages
1. Technology-driven pricing (instant quotes)
2. Route optimization reduces costs
3. Two-sided network effects
4. Price transparency
5. Flexible booking terms

---

## Core Features

### 1. Customer-Facing Features

#### 1.1 Quote & Booking System

**Multi-Step Quote Form**
- **Step 1: What** (Item Selection)
  - Pre-defined furniture catalog
  - Room-by-room selection
  - Number of bedrooms shortcut
  - Custom items (description + dimensions)
  - Special items (piano, antiques, motorcycles, vehicles)
  - Volume calculation (cubic meters)

- **Step 2: Where** (Locations)
  - Pickup address (Google Places autocomplete)
  - Delivery address
  - Multiple stops support (future)
  - Access details:
    - Floor level
    - Stairs/elevator
    - Parking restrictions
    - Access codes/instructions
  - Distance calculation (Google Distance Matrix API)

- **Step 3: When** (Date & Time)
  - Date picker (min: today + 2 days)
  - Flexible dates option (see alternative pricing)
  - Time windows:
    - Morning (8am-12pm)
    - Afternoon (12pm-5pm)
    - Evening (5pm-8pm)
    - Flexible (any time)
  - Seasonal pricing display

- **Step 4: Extras** (Additional Services)
  - Professional packing service
  - Packing materials only
  - Furniture dismantling/assembly
  - Insurance upgrade (beyond £50k)
  - Storage (temporary or long-term)
  - Express service (priority booking)

**Instant Quote Display**
- Price breakdown:
  - Base price
  - Distance charge
  - Item volume charge
  - Extras
  - Total
- Alternative date pricing (show cheaper options)
- Provider matching preview (estimated availability)
- Save quote (email/PDF)
- Compare service levels

**Booking Confirmation**
- Review all details
- Edit any step
- Payment options:
  - Pay now (5% discount)
  - Pay later (3 days before move)
- Terms & conditions acceptance
- Email confirmation
- SMS confirmation

#### 1.2 Service Categories

**House Removals**
- Full home moving service
- 1-5 bedroom homes
- Professional movers
- Packing services available
- Insurance included

**Man and Van**
- Small moves (studio, 1-bed)
- Single item delivery
- Student moves
- Budget-friendly

**Storage**
- Self-storage partnerships
- Short-term (1-30 days)
- Long-term (1-12+ months)
- Climate-controlled options
- 24/7 access

**Car Transport**
- Vehicle delivery UK-wide
- European transport
- Classic/luxury car handling
- Enclosed transport available

**Specialty Services**
- Piano transport
- Motorcycle delivery
- Antique/fine art moving
- Office relocations
- International removals

#### 1.3 Customer Dashboard

**My Bookings**
- Upcoming moves
- Past moves
- Booking status:
  - Quote saved
  - Pending provider
  - Confirmed
  - In progress
  - Completed
  - Cancelled
- Booking details view
- Modify booking (if >48hrs away)
- Cancel booking

**Provider Communication**
- In-app messaging
- Provider profile view
- Vehicle details
- Contact information
- Real-time tracking (on move day)

**Payment Management**
- Saved payment methods
- Payment history
- Invoices/receipts (PDF download)
- Refund requests

**Reviews & Ratings**
- Submit provider reviews
- View submitted reviews
- Response from providers

**Profile Settings**
- Personal information
- Email preferences
- SMS notifications
- Saved addresses
- Password/security

#### 1.4 Trust & Safety Features

**Insurance**
- £50k fire & theft cover (standard)
- Optional coverage upgrades
- Claims process
- Documentation requirements
- Claims status tracking

**Provider Verification Display**
- Insurance verified badge
- Background check badge
- Years in business
- Total moves completed
- Average rating
- Review highlights

**Support**
- Live chat (business hours)
- Phone support (8am-9pm weekdays, 8am-6pm weekends)
- Email support (24hr response)
- FAQ/Help center
- Emergency contact (move day issues)

### 2. Provider-Facing Features

#### 2.1 Provider Onboarding

**Application Process**
- Business type selection:
  - Sole trader
  - Limited company
  - Partnership
- Company details:
  - Trading name
  - Registration number
  - VAT number (if applicable)
  - Years in business
- Contact information
- Service areas (postcode coverage)

**Documentation Upload**
- Goods-in-transit insurance certificate
- Public liability insurance
- Vehicle registration documents
- Driver license(s)
- Business insurance
- Photos:
  - Vehicle exterior
  - Vehicle interior
  - Team photos
  - Logo

**Verification Process**
- Document review (24-48 hours)
- Insurance validation (automated check)
- Background check (DBS/credit)
- Equipment inspection (optional on-site)
- Approval email
- Dashboard access granted

#### 2.2 Provider Dashboard

**Job Marketplace**
- Available jobs feed:
  - Date
  - Route (pickup → delivery)
  - Distance
  - Estimated duration
  - Payment amount
  - Customer rating
  - Special requirements
- Filter by:
  - Date range
  - Service area
  - Job type
  - Minimum payment
- Sort by:
  - Date
  - Payment (high to low)
  - Distance (near to far)
  - Best match (algorithm)

**Job Management**
- Accept/reject jobs
- Counter-offer (if bidding enabled)
- View job details
- Customer communication
- Mark milestones:
  - Confirmed
  - En route to pickup
  - Loading
  - In transit
  - Unloading
  - Completed
- Upload proof of delivery (signature/photo)

**Calendar & Availability**
- Calendar view (day/week/month)
- Set available dates
- Block unavailable dates
- Set working hours
- Recurring availability patterns
- Sync with external calendar (Google/iCal)

**Fleet Management**
- Add vehicles:
  - Type (small van, large van, Luton, 7.5 tonne)
  - Registration
  - Capacity (cubic meters)
  - Max weight
  - Insurance expiry
  - MOT expiry
  - Photos
- Vehicle assignment to jobs
- Maintenance tracking

**Earnings & Payments**
- Total earnings (today/week/month/year)
- Pending payments
- Completed payments
- Payment breakdown:
  - Job payment
  - Platform commission
  - Net earnings
- Payout schedule (weekly/bi-weekly)
- Bank account management
- Tax documents (1099/invoices)

**Performance Metrics**
- Acceptance rate
- Completion rate
- Cancellation rate
- Average rating
- Total jobs completed
- Customer satisfaction score
- Response time
- On-time rate

**Reviews & Ratings**
- View customer reviews
- Respond to reviews
- Dispute unfair reviews
- Review highlights

#### 2.3 Provider Mobile Experience
- Mobile-optimized dashboard
- Push notifications for new jobs
- GPS tracking integration
- Photo upload (easy access to camera)
- Offline mode (sync when online)

### 3. Admin Panel Features

#### 3.1 Provider Management

**Provider Approval Workflow**
- Pending applications queue
- Document review interface
- Insurance verification
- Approval/rejection actions
- Rejection reason templates
- Re-application handling

**Provider Monitoring**
- Active providers list
- Provider performance dashboard
- Flag problematic providers
- Suspension/deactivation
- Commission rate management (custom rates)
- Provider support tickets

#### 3.2 Booking Management

**Booking Operations**
- All bookings list (filters by status/date)
- Manual provider assignment (if needed)
- Booking modifications
- Cancellation management
- Refund processing
- Dispute resolution

**Customer Support**
- Support ticket system
- Customer chat history
- Issue categorization
- Resolution tracking
- Escalation workflow
- Satisfaction surveys

#### 3.3 Financial Management

**Revenue Tracking**
- Gross Merchandise Value (GMV)
- Commission revenue
- Refunds/chargebacks
- Net revenue
- Revenue by service type
- Revenue by region

**Provider Payouts**
- Pending payouts list
- Payment batch creation
- Stripe Connect transfers
- Payout history
- Failed payout management

**Pricing Configuration**
- Base pricing rules
- Seasonal multipliers
- Day-of-week pricing
- Distance-based pricing
- Volume-based pricing
- Minimum/maximum prices
- Special offer management

#### 3.4 Analytics & Reporting

**Key Metrics Dashboard**
- Total bookings (today/week/month)
- Conversion rate (quote → booking)
- Average booking value
- Customer acquisition cost
- Customer lifetime value
- Provider utilization rate
- Geographic heat map

**Customer Analytics**
- New customers
- Repeat customers
- Customer retention rate
- Churn rate
- Customer segments
- Referral sources

**Provider Analytics**
- Active providers
- Provider churn rate
- Average earnings per provider
- Jobs per provider
- Provider satisfaction

**Operational Reports**
- Bookings by service type
- Bookings by region
- Peak demand times
- Cancellation reasons
- Dispute analysis
- Insurance claims

#### 3.5 Content Management

**Website Content**
- Homepage sections
- Service pages
- FAQ management
- Blog posts
- SEO settings
- Landing pages

**Email Templates**
- Transactional emails
- Marketing emails
- Notification emails
- Template variables

**Notification Settings**
- Email notification rules
- SMS notification rules
- Push notification rules

#### 3.6 System Configuration

**Platform Settings**
- Commission rates (global/per provider)
- Payment terms (days before move)
- Cancellation policy
- Refund rules
- Insurance coverage amounts
- Service areas (enable/disable regions)

**Integration Settings**
- Stripe API keys
- Google Maps API key
- Twilio credentials
- SendGrid API key
- Analytics tracking IDs

**User Roles & Permissions**
- Admin roles
- Permission sets
- Audit logs

---

## User Flows

### Flow 1: Customer Booking Journey (Detailed)

```
1. LANDING PAGE
   - Hero section: "Get an instant quote"
   - Service category buttons
   - Trust signals (181k reviews, £50k insurance)
   - Call-to-action: "Get a quote"

2. SERVICE CATEGORY SELECTION
   - User selects: House Removals
   - Brief description shown
   - "Continue" button

3. QUOTE FORM - STEP 1: WHAT ARE YOU MOVING?
   Interface:
   - Progress indicator (1 of 4)
   - Pre-defined options:
     [ ] Studio apartment
     [ ] 1 bedroom flat
     [ ] 2 bedroom house
     [ ] 3 bedroom house
     [ ] 4+ bedroom house
     [ ] Custom (item-by-item)

   If "Custom" selected:
   - Furniture catalog (images + names):
     * Living Room: Sofa (3-seater), Sofa (2-seater), Armchair,
       Coffee table, TV stand, Bookshelf, etc.
     * Bedroom: Double bed, Single bed, Wardrobe, Chest of drawers, etc.
     * Kitchen: Fridge, Washing machine, Dishwasher, etc.
     * Dining: Dining table, Chairs, Sideboard, etc.
   - Quantity selectors (+/- buttons)
   - "Add custom item" (name, length, width, height)

   Special items section:
   [ ] Piano (upright/grand dropdown)
   [ ] Motorcycle
   [ ] Antiques/Fine art

   Volume calculation displayed: "~15 cubic meters"
   Recommended vehicle: "Large van or Luton"

   Validation: At least 1 item required
   Button: "Next: Where are you moving?"

4. QUOTE FORM - STEP 2: WHERE ARE YOU MOVING?
   Interface:
   - Progress indicator (2 of 4)

   Pickup Address:
   - Google Places autocomplete input
   - Manual address entry option
   - "Collection floor" dropdown: Ground/1st/2nd/3rd/4+
   - [ ] Stairs only (no lift)
   - [ ] Parking restrictions
   - [ ] Access code required
   - Additional notes textarea

   Delivery Address:
   - Same interface as pickup

   [ ] Add another stop (+£25)

   Distance calculated: "48 miles"
   Estimated journey time: "1 hour 15 minutes"
   Map preview showing route

   Validation: Both addresses required, must be valid UK postcodes
   Button: "Next: When do you need this?"

5. QUOTE FORM - STEP 3: WHEN DO YOU NEED THIS?
   Interface:
   - Progress indicator (3 of 4)

   Date Selection:
   - Calendar picker (disabled dates: today, tomorrow)
   - Popular dates highlighted
   - [ ] I'm flexible (show me cheaper dates)

   If flexible checked:
   - Alternative date pricing shown:
     * Tue 14 Jan: £299 (20% cheaper)
     * Wed 15 Jan: £285 (24% cheaper) ⭐ BEST PRICE
     * Thu 16 Jan: £310 (17% cheaper)

   Time Window:
   - ( ) Morning (8am-12pm)
   - ( ) Afternoon (12pm-5pm)
   - ( ) Flexible (anytime - save 10%)

   Why is this date more expensive?
   - Tooltip: "Weekends and month-ends have higher demand"

   Validation: Date and time required
   Button: "Next: Any extras?"

6. QUOTE FORM - STEP 4: EXTRAS
   Interface:
   - Progress indicator (4 of 4)

   Packing Services:
   [ ] Professional packing (we pack everything) +£150
   [ ] Packing materials only (boxes, tape, wrap) +£45
   [ ] I'll pack myself (free)

   Assembly:
   [ ] Furniture dismantling & reassembly +£80

   Insurance:
   [x] Standard cover (£50k) - Included
   [ ] Premium cover (£100k) +£35

   Storage:
   [ ] I need temporary storage
       - Duration dropdown: 1 week / 2 weeks / 1 month / 2 months
       - Price calculated based on volume

   Running total displayed:
   - Items & distance: £310
   - Packing: £150
   - Assembly: £80
   - Insurance: £0 (included)
   - TOTAL: £540

   Validation: None required (all optional)
   Button: "See my instant quote"

7. INSTANT QUOTE DISPLAY
   Interface:
   - Large price display: "£540"
   - "40% cheaper than traditional movers"
   - Price breakdown (collapsible):
     * Base price: £180
     * Distance (48 miles @ £1.50/mi): £72
     * Volume charge (15m³): £58
     * Professional packing: £150
     * Furniture assembly: £80

   What's included:
   ✓ Experienced moving team (2-3 movers)
   ✓ Suitable vehicle (Luton van)
   ✓ £50,000 insurance cover
   ✓ Fuel & congestion charges
   ✓ Equipment (trolleys, straps, blankets)

   Flexible booking:
   ✓ Free cancellation up to 48 hours
   ✓ Book now, pay 3 days before
   ✓ Edit details anytime

   Alternative options:
   - "Choose a cheaper date" (shows calendar again)
   - "Remove extras to save £230"

   Save quote:
   - "Email me this quote"
   - "Download PDF"

   Provider preview:
   - "We'll match you with a local provider"
   - Sample provider card (anonymized)

   Social proof:
   - "847 moves completed in your area this month"
   - "4.8 avg rating from customers in SW London"

   CTAs:
   - Primary: "Book this move" (pink, large)
   - Secondary: "Edit details"

8. ACCOUNT CREATION / LOGIN
   If user not logged in:

   Create account:
   - Email
   - Password
   - Phone number
   - [ ] Agree to terms
   - "Create account & book"

   OR

   - "Sign in with Google"
   - "Sign in with Facebook"

   OR

   - "Already have an account? Log in"

   Phone verification:
   - SMS code sent
   - 6-digit code entry
   - "Verify"

9. BOOKING REVIEW & PAYMENT
   Interface:
   - Summary of all details (collapsible sections)
   - Edit links for each section

   Payment options:
   ( ) Pay now (save 5%: -£27) - Total: £513
       - Credit/debit card details
       - Billing address
       - [ ] Save card for future

   ( ) Book now, pay later ⭐ RECOMMENDED
       - "Reserve your move with £0 down"
       - "Payment automatically charged 3 days before"
       - Card details required (not charged now)

   Cancellation policy:
   - "Free cancellation until 14 Jan, 2:00 PM"
   - "After that, £50 fee applies"

   Checkbox:
   [x] I agree to Terms & Conditions and Privacy Policy

   Button: "Confirm booking" (large, pink)

   Trust signals:
   - "256-bit SSL encryption"
   - "Payment secured by Stripe"
   - "Money-back guarantee"

10. BOOKING CONFIRMATION
    Interface:
    - Success message: "Your move is booked!"
    - Booking reference: #AV-2026-12345
    - Confirmation email sent to: user@email.com
    - SMS confirmation sent

    Next steps:
    1. We're finding you the perfect moving team
    2. You'll be matched within 2 hours
    3. Your provider will message you to confirm details
    4. Payment on 13 Jan (3 days before move)

    What happens next:
    - "Track your booking" button → Dashboard
    - "Add to calendar" (iCal/Google)
    - "Download confirmation PDF"

    Still need help?
    - Live chat
    - Call us: 020 3872 3050

11. PROVIDER MATCHING (Backend)
    Algorithm matches based on:
    - Service area (postcode matching)
    - Vehicle availability
    - Calendar availability
    - Route optimization (existing jobs nearby)
    - Provider rating (>4.0 stars)
    - Acceptance rate (>80%)
    - Response time (<2 hours)

    Notification sent to top 3 matched providers
    First to accept wins the job
    If no acceptance within 1 hour, expand search radius

    Customer receives notification:
    - Email: "Great news! We've found your moving team"
    - SMS: "Your move is confirmed with [Provider Name]"
    - Push notification (if app installed)

12. PROVIDER ASSIGNED
    Customer dashboard updated:
    - Provider details visible:
      * Company name
      * Contact: Phone, email
      * Rating: 4.8 stars (247 reviews)
      * Photo of team
      * Vehicle details: "Mercedes Luton Van (reg: AB12 CDE)"
      * Years in business: 8 years
      * Total moves: 1,247

    Action buttons:
    - "Message [Provider Name]"
    - "Call [Provider Name]"
    - "View reviews"

    Provider's introduction message auto-sent:
    "Hi! I'm John from Swift Moves. Looking forward to helping
    with your move on 16 Jan. I'll call you 2 days before to
    confirm final details. Any questions, just message me!"

13. PRE-MOVE COMMUNICATION (Days before move)
    Day -7: Email reminder "Your move is next week"
    Day -5: SMS reminder "Don't forget to start packing"
    Day -3: Payment charged automatically
           Email: "Payment successful - £540 charged"
           SMS: "Payment received. See you on move day!"
    Day -2: Provider calls to confirm:
           - Access details
           - Parking
           - Any changes
    Day -1: Email "Your move is tomorrow!"
           - Provider details
           - What to expect
           - Emergency contact

14. MOVE DAY
    Morning (2 hours before):
    - SMS: "Your movers are preparing. ETA: 8:45 AM"

    Tracking (if GPS enabled):
    - "John is 15 minutes away"
    - Live map showing van location

    Provider updates status:
    - "Arrived at pickup" → Customer notified
    - Photo taken of items (proof)
    - Customer signs digital checklist
    - "In transit" → Customer can track
    - "Arrived at delivery" → Customer notified
    - Unloading
    - Customer signs completion

    Completion notification:
    - "Move completed!"
    - Receipt sent (PDF)

15. POST-MOVE
    2 hours after completion:
    - Email: "How was your move?"
    - Rating request (1-5 stars)
    - Review form:
      * How professional was your mover?
      * Did they arrive on time?
      * How careful were they with your items?
      * Would you use them again?
      * Leave a review (optional)

    After review submitted:
    - "Thanks for your feedback!"
    - Discount code: "MOVE20" (20% off next booking)
    - Referral offer: "Give £25, Get £25"

    Provider receives review notification
    Provider can respond

    Customer can:
    - Download invoice
    - Request receipt for expense
    - Report issues (damage claims)
    - Book another move

END OF CUSTOMER FLOW
```

### Flow 2: Provider Onboarding (Detailed)

```
1. PROVIDER LANDING PAGE
   - "Become a transport provider"
   - Benefits:
     * Earn up to £500/day
     * Fill your empty miles
     * No monthly fees
     * Weekly payouts
   - CTA: "Apply now"

2. APPLICATION START
   - "Tell us about your business"

   Business type:
   ( ) Sole trader
   ( ) Limited company
   ( ) Partnership

   Company details:
   - Trading name
   - Company number (if limited)
   - VAT number (optional)
   - Years in business
   - Number of vehicles
   - Number of drivers

   Contact:
   - Your name
   - Email
   - Phone
   - Business address

3. SERVICE DETAILS
   - What services do you offer?
     [ ] House removals
     [ ] Man and van
     [ ] Office moves
     [ ] Furniture delivery
     [ ] Vehicle transport
     [ ] International moves

   - Where do you operate?
     * Postcode areas (add multiple):
       Input: "SW1" [Add]
       Input: "SW2" [Add]
       Input: "Enter postcode area"
     * OR "Search by city"

   - How far will you travel?
     Slider: 0 - 100+ miles
     [ ] Open to nationwide jobs

4. VEHICLE INFORMATION
   Add your vehicles:

   Vehicle 1:
   - Type dropdown:
     * Small van (up to 6m³)
     * Medium van (6-10m³)
     * Large van (10-15m³)
     * Luton van (15-20m³)
     * 7.5 tonne (20+m³)
   - Registration: AB12 CDE
   - Make/Model: Mercedes Sprinter
   - Year: 2020
   - Capacity: 12m³
   - Max payload: 1000kg
   - Upload photos: [Vehicle exterior] [Vehicle interior]

   [+ Add another vehicle]

5. INSURANCE & DOCUMENTS
   Upload required documents:

   ✓ Required:
   - Goods-in-transit insurance
     * Minimum £50,000 cover
     * Upload certificate (PDF/JPG)
     * Expiry date: __/__/____

   - Public liability insurance
     * Minimum £2,000,000 cover
     * Upload certificate
     * Expiry date: __/__/____

   - Vehicle insurance (for each vehicle)
     * Business use cover
     * Upload certificates

   - Driving license
     * Photo of license (both sides)

   - Vehicle registration (V5C)
     * For each vehicle

   Optional:
   - Business insurance
   - Professional certifications
   - Reference letters

6. COMPANY PHOTOS
   Help customers trust you:

   - Your logo (optional)
   - Team photo
   - Vehicle photos (already uploaded)
   - Equipment (trolleys, blankets, etc.)

   Tips:
   - Use clear, professional photos
   - Show your team smiling
   - Highlight your branding

7. PRICING & AVAILABILITY
   Set your rates:

   - Minimum job value: £___
   - Preferred job radius: ___ miles
   - Day rate: £___ (full day)
   - Half-day rate: £___
   - Price per mile: £___

   (Platform will show you algorithm-calculated prices)

   Availability:
   - Select days you typically work:
     [ ] Monday
     [ ] Tuesday
     [x] Wednesday
     [x] Thursday
     [x] Friday
     [x] Saturday
     [ ] Sunday

   - Working hours:
     Start: 8:00 AM
     End: 6:00 PM

8. BANK DETAILS
   For receiving payments:

   - Account holder name
   - Sort code: __-__-__
   - Account number: ________
   - Bank name

   Stripe Connect setup:
   - "Connect with Stripe" button
   - Redirects to Stripe onboarding
   - Fills in business details
   - Verifies identity
   - Returns to AnyVan

9. REVIEW & SUBMIT
   Application summary:
   - Business details ✓ [Edit]
   - Service areas ✓ [Edit]
   - Vehicles ✓ [Edit]
   - Insurance ✓ [Edit]
   - Photos ✓ [Edit]
   - Bank details ✓ [Edit]

   Declaration:
   [x] I confirm all information provided is accurate
   [x] I have read and agree to Provider Terms & Conditions
   [x] I understand AnyVan's commission structure (18%)
   [x] I consent to background checks

   Submit application

10. APPLICATION SUBMITTED
    "Application received!"

    What happens next:
    1. Document verification (1-2 business days)
    2. Background check (2-3 business days)
    3. Approval decision (email notification)

    While you wait:
    - [ ] Complete your profile
    - [ ] Watch training videos
    - [ ] Read provider handbook

    "We'll email you at provider@email.com"

11. ADMIN REVIEW (Backend)
    Admin panel shows:
    - New applications queue
    - Provider: Swift Moves Ltd
    - Applied: 6 Jan 2026
    - Documents:
      * Goods in transit insurance [View PDF] ✓ Valid
      * Public liability insurance [View PDF] ✓ Valid
      * Vehicle insurance [View PDF] ✓ Valid
      * Driving license [View Images] ✓ Valid
      * V5C [View PDF] ✓ Valid

    Background check:
    - DBS check: [Request] → ✓ Clear
    - Credit check: [Request] → ✓ Clear
    - Insurance verification: ✓ Confirmed with provider

    Admin decision:
    ( ) Approve
    ( ) Reject
    Reason (if reject): ___________

    [Save decision]

12. APPROVAL EMAIL
    "Congratulations! You're approved"

    Welcome to AnyVan!

    Your account is now live and you can start receiving jobs.

    Next steps:
    1. Log in to your dashboard
    2. Set your availability calendar
    3. Watch for job notifications
    4. Accept your first job!

    Resources:
    - Provider handbook (PDF)
    - Training videos
    - Best practices guide
    - Support: providers@anyvan.com

    [Go to dashboard]

13. PROVIDER DASHBOARD (First login)
    Welcome tour:
    - "This is your job feed"
    - "This is how you accept jobs"
    - "Here's your calendar"
    - "Track your earnings here"
    - "Message customers here"

    [Skip tour] [Next]

    Dashboard loads with:
    - "No jobs yet - set your availability to start"
    - CTA: "Set availability"

END OF PROVIDER ONBOARDING FLOW
```

### Flow 3: Job Matching & Execution

```
1. JOB CREATED (From customer booking)
   System creates job record:
   - Booking ID: #AV-2026-12345
   - Service: House removal
   - Pickup: SW1A 1AA
   - Delivery: SE1 9SG
   - Date: 16 Jan 2026, Morning
   - Distance: 8 miles
   - Volume: 15m³
   - Payment: £540
   - Commission: £97 (18%)
   - Provider payout: £443

2. MATCHING ALGORITHM RUNS
   Query providers:

   Filters:
   - Service area includes SW1 OR SE1 ✓
   - Available on 16 Jan ✓
   - Vehicle capacity >= 15m³ ✓
   - Active & approved ✓
   - Rating >= 4.0 ✓

   Results: 12 providers match

   Scoring:
   - Distance from pickup: 40% weight
   - Rating: 20% weight
   - Acceptance rate: 15% weight
   - Response time: 15% weight
   - Route optimization: 10% weight

   Top 3 providers:
   1. Swift Moves (score: 95)
      - 2 miles from pickup
      - 4.8 rating
      - 92% acceptance rate
      - Has another job 3 miles away same day ⭐

   2. London Movers (score: 87)
      - 5 miles from pickup
      - 4.7 rating
      - 88% acceptance rate

   3. Express Removals (score: 82)
      - 8 miles from pickup
      - 4.9 rating
      - 78% acceptance rate

3. NOTIFY PROVIDERS
   Notification sent to top 3:

   Push notification:
   "New job: SW1 → SE1, 16 Jan, £443 payout"

   Email:
   Subject: "New job available in your area"
   Body:
   - Job summary
   - Payout
   - Distance
   - [View job details] [Accept job]

   SMS:
   "New job: 16 Jan, SW1→SE1, £443. View: anyvan.com/jobs/12345"

   In-app notification badge

4. PROVIDER VIEWS JOB
   Job details screen:

   Job #AV-2026-12345
   📅 Wednesday, 16 January 2026
   🕐 8:00 AM - 12:00 PM

   Route:
   📍 Pickup: 123 Victoria St, London SW1A 1AA
   📍 Delivery: 45 London Bridge St, London SE1 9SG
   📏 Distance: 8 miles
   ⏱️ Estimated duration: 4 hours

   Items:
   - 3 bedroom house
   - ~15m³ volume
   - Piano (upright)
   - [View full inventory]

   Special requirements:
   - 3rd floor, no lift
   - Parking permit required (provided)
   - Piano needs extra care

   Extras:
   ✓ Professional packing included
   ✓ Furniture assembly included

   Payment:
   - Customer pays: £540
   - AnyVan commission: £97 (18%)
   - Your payout: £443

   Customer:
   - Sarah M.
   - Rating: 4.9 (3 previous moves)
   - Verified: ✓

   Route optimization:
   💡 This job is on the way to your SE5 job at 2 PM

   Buttons:
   [Accept job] [Decline] [Ask question]

   "First to accept wins the job"
   "2 other providers viewing"

5. PROVIDER ACCEPTS
   Provider clicks "Accept job"

   Confirmation dialog:
   "Confirm job acceptance"
   - I can fulfill all requirements
   - I have suitable vehicle available
   - I will arrive on time
   [x] I accept the terms

   [Confirm]

   Success:
   "Job accepted!"
   "Customer notified"
   "Added to your calendar"

6. OTHER PROVIDERS NOTIFIED
   Push notification to other 2 providers:
   "Job no longer available (accepted by another provider)"

   Job disappears from their feed

7. CUSTOMER NOTIFIED
   Email to customer:
   Subject: "Great news! We've matched you with Swift Moves"

   Body:
   "Your move is confirmed!"

   Your moving team:
   🚚 Swift Moves Ltd
   ⭐ 4.8 stars (247 reviews)
   📞 07700 900123
   📧 hello@swiftmoves.co.uk

   Team:
   [Photo] John (Driver & Lead)
   [Photo] Mike (Helper)

   Vehicle:
   Mercedes Luton Van
   Registration: AB12 CDE
   [Photo of van]

   What happens next:
   1. John will message you to introduce himself
   2. He'll call 2 days before to confirm details
   3. Payment charged 3 days before (13 Jan)
   4. Track your move on move day

   [View booking] [Message John]

   SMS:
   "Move confirmed! Your provider is Swift Moves (4.8⭐).
   John will message you soon. View: anyvan.com/booking/12345"

8. AUTO-MESSAGE FROM PROVIDER
   In-app message thread created:

   John (Swift Moves) • Just now
   "Hi Sarah! I'm John from Swift Moves. Really looking
   forward to helping with your move on 16 Jan.

   I've noted you're on the 3rd floor with stairs and
   have a piano - no problem, we do this all the time!

   I'll give you a call on the 14th (Tuesday) to confirm
   final details and parking.

   If you have any questions before then, just message
   me here.

   Looking forward to meeting you!
   John"

   Customer gets notification

9. PRE-MOVE PREPARATION

   Day -7 (9 Jan):
   Email to customer: "Your move is next week"
   - Packing tips
   - What to prepare
   - Checklist

   Day -5 (11 Jan):
   SMS to customer: "Don't forget to notify utilities"

   Day -3 (13 Jan):
   PAYMENT CHARGED:
   - Stripe charges card: £540
   - Email: "Payment successful"
   - Receipt attached (PDF)
   - SMS confirmation

   Provider notified:
   - "Payment received for job #AV-2026-12345"
   - "£443 will be paid out on 17 Jan (day after completion)"

   Day -2 (14 Jan):
   Provider calls customer:
   - Confirms address & access
   - Parking arrangements
   - Any changes to inventory
   - Confirms 8 AM arrival

   Provider updates job:
   - "Pre-move call completed ✓"
   - Notes: "Parking permit collected from office"

   Day -1 (15 Jan):
   Email to customer: "Your move is tomorrow!"
   - What to expect
   - Provider details
   - Emergency contact: 020 3872 3050
   - Last-minute tips

   SMS: "See you tomorrow at 8 AM! - John"

10. MOVE DAY MORNING

    6:00 AM - Provider starts day:
    - Dashboard shows today's jobs:
      * 8:00 AM - Sarah M. (SW1 → SE1)
      * 2:00 PM - David K. (SE1 → SE5)

    7:00 AM - Provider en route:
    - Clicks "Start job"
    - Clicks "En route to pickup"

    Customer notified:
    - Push: "John is on his way!"
    - SMS: "Your movers left at 7:00 AM, ETA 7:50 AM"

    If GPS tracking enabled:
    - Customer sees live map
    - "John is 4 miles away, arriving in 12 minutes"

    7:50 AM - Arrival:
    - Provider clicks "Arrived at pickup"
    - Takes photo of building

    Customer notified:
    - "John has arrived!"
    - App: "Answer the door"

11. LOADING PHASE

    8:00 AM - Loading begins:
    - Provider walks through with customer
    - Digital inventory checklist:
      [x] 3-seater sofa
      [x] Coffee table
      [x] TV
      [x] Dining table + 4 chairs
      [x] Piano (upright) - Photo taken
      ... (full list)

    - Special notes:
      * "Piano has small scratch on left side (pre-existing)"
      * Photo evidence taken

    - Customer signs digital form:
      "Items verified and loaded"
      Signature: [Sarah signs on phone]

    - Provider clicks "Loading complete"

    9:30 AM - Departure:
    - Provider clicks "In transit"
    - Route shown on map

    Customer sees:
    - "Items loaded, on the way to delivery!"
    - ETA at delivery: 10:00 AM
    - Live tracking (if enabled)

12. DELIVERY PHASE

    10:00 AM - Arrival at delivery:
    - Provider clicks "Arrived at delivery"

    Customer notified:
    - "John has arrived at your new home!"

    10:05 AM - Unloading:
    - Items carried in
    - Placed in requested rooms
    - Furniture assembly (bed, wardrobes)
    - Piano positioned carefully

    11:45 AM - Completion:
    - Walk-through with customer
    - Verify all items delivered
    - Check for any damage

    Digital completion form:
    - [x] All items delivered
    - [x] Furniture assembled
    - [x] No damage reported
    - [x] Satisfied with service

    Rating (optional):
    ⭐⭐⭐⭐⭐ "How did we do?"

    Customer signature:
    "I confirm completion"
    [Sarah signs]

    Provider clicks "Job complete"

    Photo of empty van taken (proof)

13. POST-COMPLETION

    12:00 PM - Immediate:
    Customer email:
    "Move completed!"
    - Receipt (PDF)
    - Summary of service
    - [Leave a review]

    Provider dashboard:
    - Job moved to "Completed"
    - Status: "Payment processing"
    - Payout date: 17 Jan

    2 hours later (2:00 PM):
    Review request email to customer:
    "How was your move with Swift Moves?"
    [Rate your experience]

    Customer clicks, taken to review form:

    Rate Swift Moves:
    ⭐⭐⭐⭐⭐ 5 stars

    How would you rate:
    - Professionalism: ⭐⭐⭐⭐⭐
    - Punctuality: ⭐⭐⭐⭐⭐
    - Care with items: ⭐⭐⭐⭐⭐
    - Value for money: ⭐⭐⭐⭐⭐

    Write a review:
    "John and Mike were fantastic! Very professional,
    careful with my piano, and finished ahead of schedule.
    Highly recommend!"

    [Submit review]

    Provider notified:
    "Sarah M. left you a 5-star review!"
    [View review]

    Customer receives:
    "Thanks for your feedback!"
    - Discount code: MOVE20 (20% off next)
    - Referral link: "Refer a friend, both get £25"

14. PAYMENT PAYOUT

    17 Jan (Day after move):
    - Stripe transfer initiated: £443
    - 2-3 business days to bank account

    Provider email:
    "Payment on the way!"
    - Job: #AV-2026-12345
    - Amount: £443.00
    - Arriving: 19-20 Jan
    - [View invoice]

    Provider dashboard:
    - Earnings this week: £1,247
    - Pending: £0
    - Next payout: £804 (23 Jan)

15. DISPUTE WINDOW (if issues)

    If customer reports issue within 7 days:
    - "Report a problem" button
    - Issue types:
      * Damage to item
      * Missing item
      * Late arrival
      * Unprofessional behavior
      * Other

    - Description + photos
    - Submitted to support

    Admin reviews:
    - Customer evidence
    - Provider evidence (photos, signatures)
    - Messages between parties

    Resolution:
    - Full refund
    - Partial refund
    - Insurance claim
    - No action

    If damage claim:
    - Insurance process initiated
    - Provider notified
    - Claim form sent
    - Assessment scheduled

END OF JOB EXECUTION FLOW
```

---

## Technical Architecture

### System Architecture Overview

```
┌─────────────────────────────────────────────────────────┐
│                     CLIENT LAYER                        │
├─────────────────────────────────────────────────────────┤
│  Web App (Next.js)  │  Mobile Apps (React Native)      │
│  - Customer Portal  │  - iOS App                        │
│  - Provider Portal  │  - Android App                    │
│  - Admin Dashboard  │  - PWA                            │
└─────────────┬───────────────────────────────────────────┘
              │
              │ HTTPS / WSS
              │
┌─────────────▼───────────────────────────────────────────┐
│                   API GATEWAY                           │
│  - Rate limiting                                        │
│  - Authentication                                       │
│  - Load balancing                                       │
│  - Request routing                                      │
└─────────────┬───────────────────────────────────────────┘
              │
      ┌───────┴────────┬────────────┬──────────────┐
      │                │            │              │
┌─────▼─────┐  ┌──────▼─────┐ ┌───▼────┐  ┌──────▼──────┐
│   Auth    │  │  Booking   │ │Payment │  │   Matching  │
│  Service  │  │  Service   │ │Service │  │   Service   │
└───────────┘  └────────────┘ └────────┘  └─────────────┘

┌──────────┐  ┌─────────────┐ ┌────────┐  ┌─────────────┐
│   User   │  │Communication│ │Review  │  │  Analytics  │
│ Service  │  │  Service    │ │Service │  │   Service   │
└──────────┘  └─────────────┘ └────────┘  └─────────────┘
      │                │            │              │
      └────────────────┴────────────┴──────────────┘
                       │
              ┌────────▼──────────┐
              │  Message Queue    │
              │  (Redis/RabbitMQ) │
              └────────┬──────────┘
                       │
              ┌────────▼──────────┐
              │  Background Jobs  │
              │  - Email sender   │
              │  - SMS sender     │
              │  - Payments       │
              │  - Matching       │
              └───────────────────┘

┌─────────────────────────────────────────────────────────┐
│                    DATA LAYER                           │
├─────────────────────────────────────────────────────────┤
│  PostgreSQL  │  Redis   │  Elasticsearch │  S3 Storage │
│  (Primary DB)│  (Cache) │  (Search)      │  (Files)    │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│               THIRD-PARTY SERVICES                      │
├─────────────────────────────────────────────────────────┤
│  Stripe  │  Google Maps  │  Twilio  │  SendGrid       │
└─────────────────────────────────────────────────────────┘
```

### Technology Choices & Rationale

#### Frontend

**Next.js 14+ (React)**
- **Why**:
  - Server-side rendering for SEO (critical for organic traffic)
  - App Router for file-based routing
  - API routes reduce backend complexity
  - Image optimization built-in
  - Excellent performance
- **Use cases**:
  - Customer-facing website
  - Provider portal
  - Admin dashboard

**TypeScript**
- **Why**:
  - Type safety reduces bugs
  - Better IDE support
  - Self-documenting code
  - Easier refactoring
- **Configuration**: Strict mode enabled

**Tailwind CSS**
- **Why**:
  - Already in use by AnyVan
  - Rapid development
  - Consistent design system
  - Excellent responsive utilities
  - Small bundle size with purging
- **Plugins**:
  - @tailwindcss/forms
  - @tailwindcss/typography
  - tailwind-scrollbar

**State Management: Zustand**
- **Why**:
  - Simpler than Redux
  - Minimal boilerplate
  - Excellent TypeScript support
  - Small bundle size (3kb)
- **Alternative**: Redux Toolkit (if complex state needed)

#### Backend

**Node.js with NestJS**
- **Why NestJS**:
  - TypeScript-first
  - Modular architecture (easy to scale)
  - Built-in dependency injection
  - Excellent documentation
  - Microservices support
  - Similar to Angular (familiar patterns)
- **Alternatives considered**:
  - Express: Too bare-bones, requires more setup
  - Fastify: Great performance, but less ecosystem
  - Python/Django: Excellent for rapid development, slower than Node

**API Design: REST + GraphQL**
- **REST**: For simple CRUD operations
- **GraphQL** (optional): For complex queries (admin dashboard)
- **Why both**:
  - REST simpler for mobile apps
  - GraphQL reduces over-fetching for complex UIs

**ORM: Prisma**
- **Why**:
  - Type-safe database access
  - Excellent TypeScript integration
  - Intuitive query API
  - Built-in migrations
  - Multi-database support
- **Alternative**: TypeORM (more mature, but less modern)

**Authentication: Passport.js + JWT**
- **Passport.js**:
  - Multiple strategies (local, Google, Facebook)
  - Well-tested
  - Large ecosystem
- **JWT**:
  - Stateless authentication
  - Access tokens (15 min) + Refresh tokens (7 days)
  - Stored in httpOnly cookies (XSS protection)

#### Database

**PostgreSQL 15+**
- **Why**:
  - ACID compliance
  - Complex queries support
  - JSON/JSONB for flexible data
  - Full-text search
  - PostGIS for geospatial queries
  - Excellent performance
  - Open source
- **Configuration**:
  - Connection pooling (PgBouncer)
  - Read replicas for scaling
  - Regular backups (daily)

**Redis 7+**
- **Why**:
  - Session storage
  - Quote calculation caching
  - Queue management (BullMQ)
  - Real-time leaderboards
  - Rate limiting
  - Pub/Sub for real-time features
- **Data structures used**:
  - Strings: Session data
  - Hashes: User profiles cache
  - Sets: Online users
  - Sorted Sets: Provider rankings
  - Lists: Job queues

**Elasticsearch (Optional for MVP)**
- **Why**:
  - Fast full-text search
  - Provider search by location/rating
  - Faceted search
  - Analytics aggregations
- **When to add**: After 10k+ providers
- **Alternative**: PostgreSQL full-text search initially

#### File Storage

**AWS S3**
- **Why**:
  - Scalable
  - CDN integration (CloudFront)
  - Versioning
  - Lifecycle policies
  - Cost-effective
- **Use cases**:
  - Provider documents (insurance, licenses)
  - Vehicle photos
  - Proof of delivery photos
  - Invoices/receipts (PDFs)
- **Structure**:
  ```
  anyvan-production/
  ├── providers/
  │   ├── {provider_id}/
  │   │   ├── documents/
  │   │   ├── vehicles/
  │   │   └── profile/
  ├── bookings/
  │   ├── {booking_id}/
  │   │   ├── inventory-photos/
  │   │   └── proof-of-delivery/
  └── invoices/
      └── {year}/{month}/
  ```

#### Real-Time Communication

**Socket.io**
- **Why**:
  - WebSocket with fallbacks
  - Room support (for private chats)
  - Authentication integration
  - Automatic reconnection
  - Broadcasting
- **Use cases**:
  - Customer-provider messaging
  - Real-time tracking
  - Admin notifications
  - Provider job alerts

#### Background Jobs

**BullMQ (Redis-based)**
- **Why**:
  - TypeScript support
  - Priority queues
  - Delayed jobs
  - Job scheduling
  - Retry logic
  - Dashboard (Bull Board)
- **Job types**:
  - `send-email`: Email notifications
  - `send-sms`: SMS notifications
  - `process-payment`: Charge customers
  - `payout-provider`: Transfer to providers
  - `match-provider`: Run matching algorithm
  - `send-review-request`: 2 hours after completion
  - `insurance-expiry-check`: Daily check
  - `cleanup-quotes`: Delete old quotes

#### API Documentation

**Swagger/OpenAPI**
- **Why**:
  - Auto-generated from NestJS decorators
  - Interactive documentation
  - Client SDK generation
  - Testing interface
- **URL**: `/api/docs`

### Infrastructure

#### Hosting Options

**Option 1: AWS (Recommended for scale)**
```
- Compute: ECS (Docker containers)
- Database: RDS PostgreSQL (Multi-AZ)
- Cache: ElastiCache Redis
- Storage: S3
- CDN: CloudFront
- Load Balancer: Application Load Balancer
- Monitoring: CloudWatch
- Secrets: Secrets Manager
```

**Option 2: Vercel + Railway (Fast MVP)**
```
- Frontend: Vercel (auto-deploy from Git)
- Backend: Railway (or Render)
- Database: Railway PostgreSQL
- Redis: Railway Redis
- Storage: Vercel Blob or Cloudflare R2
```

**Option 3: Google Cloud Platform**
```
- Compute: Cloud Run
- Database: Cloud SQL
- Cache: Memorystore (Redis)
- Storage: Cloud Storage
- CDN: Cloud CDN
```

#### CI/CD Pipeline

**GitHub Actions**
```yaml
Workflow:
1. Pull Request:
   - Run linter (ESLint)
   - Run tests (Jest)
   - Type check (tsc)
   - Build check
   - Preview deployment (Vercel)

2. Merge to main:
   - Run all tests
   - Build Docker image
   - Push to registry
   - Deploy to staging
   - Run E2E tests (Playwright)
   - Manual approval
   - Deploy to production
   - Run smoke tests

3. Database migrations:
   - Run Prisma migrations
   - Backup before migration
   - Rollback script ready
```

#### Monitoring & Logging

**Application Monitoring: Datadog/New Relic**
- Request latency
- Error rates
- Database query performance
- API endpoint metrics
- Custom business metrics

**Error Tracking: Sentry**
- Real-time error alerts
- Source maps for debugging
- Release tracking
- User context

**Logging: ELK Stack (or CloudWatch)**
- Structured JSON logs
- Log levels: debug, info, warn, error
- Correlation IDs for tracing

**Uptime Monitoring: Pingdom**
- Health checks every 1 minute
- Multi-region checks
- SMS alerts for downtime

#### Security

**SSL/TLS**
- HTTPS everywhere
- TLS 1.3
- Certificate auto-renewal (Let's Encrypt or AWS ACM)

**Authentication Security**
- Password hashing: bcrypt (12 rounds)
- JWT secrets rotation
- Rate limiting: 100 req/15min per IP
- Brute force protection

**API Security**
- CORS configuration
- Request validation (class-validator)
- SQL injection prevention (Prisma)
- XSS prevention (sanitization)
- CSRF tokens

**Infrastructure Security**
- Private VPC
- Database not publicly accessible
- Security groups/firewalls
- Secrets in environment variables (never in code)
- IAM roles (least privilege)

**Compliance**
- GDPR compliance (data protection)
- PCI DSS (payment handling via Stripe)
- Data encryption at rest
- Audit logs

#### Scaling Strategy

**Horizontal Scaling**
- Load balancer distributes traffic
- Multiple API server instances
- Stateless architecture (sessions in Redis)
- Database read replicas

**Caching Strategy**
- CDN for static assets
- Redis for API responses
- Browser caching headers
- Quote calculation caching (5 min TTL)

**Database Optimization**
- Indexes on foreign keys
- Composite indexes for queries
- Query optimization
- Connection pooling
- Partitioning (if needed)

**Performance Targets**
- Page load: <2 seconds
- API response: <200ms (p95)
- Quote generation: <1 second
- Real-time messaging: <100ms

---

## Database Schema

See separate file: `database-schema.md`

---

## Third-Party Integrations

### 1. Payment Processing: Stripe Connect

**Why Stripe Connect**: Perfect for marketplace models

**Setup**:
- Platform account (AnyVan)
- Connected accounts (providers)
- Standard Connect (providers have Stripe account)

**Flows**:

**Customer Payment**:
```javascript
// 1. Create Payment Intent (when booking confirmed)
const paymentIntent = await stripe.paymentIntents.create({
  amount: 54000, // £540.00
  currency: 'gbp',
  customer: 'cus_customer123',
  payment_method: 'pm_card_visa',
  capture_method: 'manual', // Authorize now, capture later
  description: 'Move booking #AV-2026-12345',
  metadata: {
    booking_id: 'AV-2026-12345',
    provider_id: 'prov_abc123'
  }
});

// 2. Capture payment (3 days before move)
const captured = await stripe.paymentIntents.capture(
  paymentIntent.id,
  {
    amount_to_capture: 54000
  }
);

// 3. Transfer to provider (after completion)
const transfer = await stripe.transfers.create({
  amount: 44300, // £443.00 (after 18% commission)
  currency: 'gbp',
  destination: 'acct_provider123', // Provider's Stripe account
  transfer_group: 'AV-2026-12345',
  description: 'Payout for booking #AV-2026-12345'
});
```

**Refunds**:
```javascript
const refund = await stripe.refunds.create({
  payment_intent: 'pi_xxx',
  amount: 54000, // Full or partial
  reason: 'requested_by_customer',
  metadata: {
    booking_id: 'AV-2026-12345',
    reason: 'Provider cancelled'
  }
});
```

**Webhooks** (required):
- `payment_intent.succeeded`
- `payment_intent.payment_failed`
- `charge.refunded`
- `transfer.created`
- `transfer.failed`
- `account.updated` (provider account changes)

**Testing**:
- Test mode API keys
- Test cards: 4242 4242 4242 4242

**Costs**:
- 1.4% + 20p per transaction (UK cards)
- 2.9% + 20p (international cards)
- No monthly fees

### 2. Maps & Geocoding: Google Maps Platform

**APIs Used**:

**Geocoding API**:
```javascript
// Convert address to lat/lng
const response = await geocode({
  address: '123 Victoria St, London SW1A 1AA',
  key: process.env.GOOGLE_MAPS_API_KEY
});

const location = response.results[0].geometry.location;
// { lat: 51.4981, lng: -0.1337 }
```

**Distance Matrix API**:
```javascript
// Calculate distance and duration
const response = await distanceMatrix({
  origins: ['SW1A 1AA'],
  destinations: ['SE1 9SG'],
  mode: 'driving',
  units: 'imperial',
  key: process.env.GOOGLE_MAPS_API_KEY
});

const distance = response.rows[0].elements[0].distance.value; // meters
const duration = response.rows[0].elements[0].duration.value; // seconds
```

**Places API** (Autocomplete):
```javascript
// Frontend: Autocomplete input
<Autocomplete
  onLoad={onLoad}
  onPlaceChanged={onPlaceChanged}
>
  <input
    type="text"
    placeholder="Enter pickup address"
  />
</Autocomplete>

// Get place details
const place = autocomplete.getPlace();
const address = place.formatted_address;
const postcode = place.address_components.find(
  c => c.types.includes('postal_code')
).long_name;
```

**Directions API**:
```javascript
// Get route for display
const directionsService = new google.maps.DirectionsService();
const result = await directionsService.route({
  origin: 'SW1A 1AA',
  destination: 'SE1 9SG',
  travelMode: google.maps.TravelMode.DRIVING
});

// Display on map
directionsRenderer.setDirections(result);
```

**Maps JavaScript API**:
- Display interactive maps
- Show provider location (GPS tracking)
- Draw routes
- Custom markers

**Costs**:
- Geocoding: £4 per 1000 requests
- Distance Matrix: £4 per 1000 elements
- Places Autocomplete: £2.32 per 1000 sessions
- Free tier: £200 credit/month

**Optimization**:
- Cache geocoded addresses (Redis)
- Batch Distance Matrix requests
- Use Places Autocomplete session tokens

### 3. Communication: Twilio (SMS)

**Use Cases**:
- Phone verification
- Booking confirmations
- Payment reminders
- Move day notifications
- Provider alerts

**Implementation**:
```javascript
const twilio = require('twilio');
const client = twilio(
  process.env.TWILIO_ACCOUNT_SID,
  process.env.TWILIO_AUTH_TOKEN
);

// Send SMS
await client.messages.create({
  body: 'Your move is confirmed! Provider: Swift Moves. View details: https://anyvan.com/booking/12345',
  from: '+442012345678', // Twilio number
  to: '+447700900123' // Customer number
});

// Phone verification
await client.verify.v2
  .services(process.env.TWILIO_VERIFY_SERVICE_SID)
  .verifications.create({
    to: '+447700900123',
    channel: 'sms'
  });

// Check verification code
const verification_check = await client.verify.v2
  .services(process.env.TWILIO_VERIFY_SERVICE_SID)
  .verificationChecks.create({
    to: '+447700900123',
    code: '123456'
  });
```

**Costs**:
- SMS (UK): £0.04 per message
- Phone verification: £0.04 per verification
- Twilio number: £1/month

**Alternatives**:
- AWS SNS (cheaper for high volume)
- MessageBird
- Vonage

### 4. Email: SendGrid

**Email Types**:

**Transactional** (high priority):
- Booking confirmation
- Provider assignment
- Payment receipt
- Password reset
- Phone verification

**Notifications** (medium priority):
- Booking reminders
- Review requests
- Provider approval

**Marketing** (low priority):
- Newsletters
- Promotional offers
- Re-engagement campaigns

**Implementation**:
```javascript
const sgMail = require('@sendgrid/mail');
sgMail.setApiKey(process.env.SENDGRID_API_KEY);

// Dynamic template
const msg = {
  to: 'customer@example.com',
  from: 'noreply@anyvan.com',
  templateId: 'd-xxx', // SendGrid template ID
  dynamic_template_data: {
    customer_name: 'Sarah',
    booking_id: 'AV-2026-12345',
    move_date: '16 January 2026',
    provider_name: 'Swift Moves',
    amount: '£540'
  }
};

await sgMail.send(msg);
```

**Templates** (created in SendGrid):
- `booking-confirmation`
- `provider-assigned`
- `payment-receipt`
- `review-request`
- `provider-approved`

**Features Used**:
- Dynamic templates
- Unsubscribe management
- Analytics (open rates, click rates)
- A/B testing
- Scheduling

**Costs**:
- Free tier: 100 emails/day
- Essentials: £15/month (50k emails)
- Pro: £90/month (100k emails)

**Alternatives**:
- AWS SES (cheaper, less features)
- Postmark (better deliverability)
- Mailgun

### 5. Push Notifications: Firebase Cloud Messaging

**Use Cases**:
- New job alerts (providers)
- Booking updates (customers)
- Messages received
- Provider en route
- Payment due

**Implementation**:
```javascript
const admin = require('firebase-admin');
admin.initializeApp({
  credential: admin.credential.cert(serviceAccount)
});

// Send to device
await admin.messaging().send({
  token: deviceToken,
  notification: {
    title: 'New job available!',
    body: 'SW1 → SE1, 16 Jan, £443 payout'
  },
  data: {
    job_id: 'AV-2026-12345',
    type: 'new_job'
  }
});

// Send to topic (all providers in area)
await admin.messaging().sendToTopic('providers_london', {
  notification: {
    title: 'High demand alert',
    body: 'Lots of jobs available this weekend!'
  }
});
```

**Frontend** (React Native):
```javascript
import messaging from '@react-native-firebase/messaging';

// Request permission
await messaging().requestPermission();

// Get device token
const token = await messaging().getToken();
// Send token to backend

// Handle notifications
messaging().onMessage(async remoteMessage => {
  // Show notification or update UI
});
```

**Costs**: Free (no limits)

### 6. Identity Verification: Onfido (or Stripe Identity)

**Use Cases**:
- Provider background checks
- Driver license verification
- ID verification
- Right to work checks (UK)

**Stripe Identity** (simpler):
```javascript
const verificationSession = await stripe.identity.verificationSessions.create({
  type: 'document',
  metadata: {
    provider_id: 'prov_abc123'
  }
});

// Redirect provider to verification URL
res.redirect(verificationSession.url);

// Webhook
// identity.verification_session.verified
// identity.verification_session.requires_input
```

**Onfido** (more comprehensive):
```javascript
// Create applicant
const applicant = await onfido.applicant.create({
  firstName: 'John',
  lastName: 'Smith',
  email: 'john@example.com'
});

// Create check
const check = await onfido.check.create({
  applicantId: applicant.id,
  reportNames: ['document', 'identity_enhanced']
});

// Webhook receives result
```

**Costs**:
- Stripe Identity: £1.50 per verification
- Onfido: £2-5 per check (depending on level)

### 7. Reviews: Trustpilot API

**Integration**:
```javascript
// Send review invitation
await trustpilot.invitations.create({
  recipientEmail: 'customer@example.com',
  recipientName: 'Sarah M',
  referenceId: 'AV-2026-12345',
  locale: 'en-GB',
  redirectUri: 'https://anyvan.com/booking/12345'
});

// Fetch reviews
const reviews = await trustpilot.reviews.list({
  businessUnitId: 'xxx',
  perPage: 20
});

// Display on website
```

**Display Widget**:
```html
<!-- TrustBox widget -->
<div class="trustpilot-widget"
     data-locale="en-GB"
     data-template-id="xxx"
     data-businessunit-id="xxx"
     data-style-height="130px"
     data-style-width="100%"
     data-theme="light">
</div>
```

**Alternative**: Build own review system (full control)

### 8. Insurance API: Partner TBD

**Options**:
- Zego (on-demand insurance)
- Cuvva
- Custom insurance broker API

**Functionality**:
- Validate provider insurance
- On-demand coverage
- Claims management
- Certificate generation

---

## UI/UX Requirements

See current implementation details in main document above (Section 7).

Additional specifications:

### Design Tokens

```css
/* Colors */
--color-primary: #FF1493; /* AnyVan pink */
--color-secondary: #0066CC; /* Blue */
--color-success: #00CC66; /* Green */
--color-error: #FF3333; /* Red */
--color-warning: #FF9900; /* Orange */

/* Spacing */
--space-xs: 4px;
--space-sm: 8px;
--space-md: 16px;
--space-lg: 24px;
--space-xl: 32px;
--space-2xl: 48px;

/* Typography */
--font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', ...;
--font-size-sm: 14px;
--font-size-base: 16px;
--font-size-lg: 18px;
--font-size-xl: 24px;
--font-size-2xl: 32px;

/* Border radius */
--radius-sm: 4px;
--radius-md: 8px;
--radius-lg: 12px;
--radius-full: 9999px;

/* Shadows */
--shadow-sm: 0 1px 2px rgba(0,0,0,0.05);
--shadow-md: 0 4px 6px rgba(0,0,0,0.1);
--shadow-lg: 0 10px 15px rgba(0,0,0,0.1);
```

### Component Library

Build with **shadcn/ui** (Tailwind + Radix):
- Button
- Input
- Select
- Checkbox
- Radio
- Switch
- Slider
- Dialog (Modal)
- Dropdown Menu
- Toast
- Tabs
- Accordion
- Card
- Badge
- Avatar
- Progress
- Skeleton
- Alert
- Command (search)

### Accessibility Requirements

- WCAG 2.1 Level AA compliance
- Color contrast ratio: 4.5:1 minimum
- Focus indicators visible
- Keyboard navigation for all interactions
- Screen reader support (ARIA labels)
- Skip to content link
- Alt text for all images
- Form labels properly associated
- Error messages descriptive

### Responsive Breakpoints

```css
/* Mobile */
@media (max-width: 639px) { }

/* Tablet */
@media (min-width: 640px) and (max-width: 1023px) { }

/* Desktop */
@media (min-width: 1024px) { }

/* Large Desktop */
@media (min-width: 1280px) { }
```

---

## Technical Stack

**Recommended Stack** (detailed in Technical Architecture section):

**Frontend**:
- Next.js 14+ (React, TypeScript)
- Tailwind CSS + shadcn/ui
- Zustand (state)
- React Hook Form + Zod
- Socket.io-client
- @googlemaps/react-wrapper

**Backend**:
- Node.js 20 LTS
- NestJS (TypeScript)
- Prisma ORM
- PostgreSQL 15+
- Redis 7+
- BullMQ

**Infrastructure**:
- AWS (ECS, RDS, ElastiCache, S3)
- or Vercel + Railway (MVP)
- GitHub Actions (CI/CD)
- Datadog (monitoring)
- Sentry (errors)

**Third-party**:
- Stripe Connect
- Google Maps API
- Twilio
- SendGrid
- Firebase (push)

---

## Development Roadmap

### PHASE 1: MVP Foundation (Months 1-3)

**Month 1: Core Infrastructure**

Week 1-2:
- [ ] Project setup (Next.js + NestJS monorepo)
- [ ] Database design finalized
- [ ] Prisma schema + initial migration
- [ ] Authentication system (JWT)
- [ ] Basic UI component library
- [ ] Design system implementation

Week 3-4:
- [ ] Customer registration/login
- [ ] Provider registration (application form)
- [ ] Admin panel foundation
- [ ] Role-based access control
- [ ] Email service integration (SendGrid)
- [ ] File upload to S3

**Month 2: Core Features**

Week 1-2:
- [ ] Quote form (all 4 steps)
- [ ] Inventory catalog
- [ ] Address autocomplete (Google Places)
- [ ] Distance calculation
- [ ] Basic pricing algorithm
- [ ] Quote display page

Week 3-4:
- [ ] Booking creation
- [ ] Stripe Connect setup
- [ ] Payment processing (pay upfront only for MVP)
- [ ] Customer dashboard (view bookings)
- [ ] Provider dashboard (view assigned jobs)
- [ ] Admin: Manual provider assignment

**Month 3: Polish & Launch**

Week 1-2:
- [ ] Provider document upload
- [ ] Admin: Provider approval workflow
- [ ] Email notifications (booking confirmation, provider assigned)
- [ ] SMS notifications (Twilio)
- [ ] Basic messaging (customer ↔ provider)
- [ ] Booking status updates

Week 3-4:
- [ ] Testing (unit + integration)
- [ ] Bug fixes
- [ ] SEO optimization (meta tags, sitemap)
- [ ] Analytics setup (GA4)
- [ ] Documentation
- [ ] **MVP Launch** (limited market, 10-20 providers)

**MVP Success Criteria**:
- 20+ providers onboarded
- 100+ bookings completed
- <5% cancellation rate
- Payment system working flawlessly
- Positive initial feedback

---

### PHASE 2: Marketplace Automation (Months 4-6)

**Month 4: Matching Engine**

Week 1-2:
- [ ] Provider availability calendar
- [ ] Matching algorithm v1:
  - Location-based matching
  - Availability checking
  - Vehicle capacity matching
- [ ] Provider notification system (email/SMS/push)
- [ ] Job acceptance/rejection flow

Week 3-4:
- [ ] Auto-assignment (if only 1 match)
- [ ] "First to accept" system (multiple matches)
- [ ] Re-matching if no acceptance (1 hour timeout)
- [ ] Provider dashboard: Job marketplace view
- [ ] Filtering and sorting jobs

**Month 5: Enhanced Booking**

Week 1-2:
- [ ] "Book now, pay later" (Stripe payment intents)
- [ ] Scheduled payment (3 days before)
- [ ] Payment reminders (email + SMS)
- [ ] Flexible dates (show alternative pricing)
- [ ] Extras: Packing, assembly, storage

Week 3-4:
- [ ] Booking modifications (edit details)
- [ ] Free cancellation (up to 48 hours)
- [ ] Cancellation fee handling
- [ ] Refund processing
- [ ] Multiple stops support

**Month 6: Communication & Trust**

Week 1-2:
- [ ] Real-time messaging (Socket.io)
- [ ] Message notifications
- [ ] Provider profiles (public view)
- [ ] Vehicle details display
- [ ] Pre-move call scheduling

Week 3-4:
- [ ] Review system (post-booking)
- [ ] Rating display (provider profiles)
- [ ] Review responses (providers)
- [ ] Trustpilot integration
- [ ] Trust badges (insurance verified, etc.)

**Phase 2 Success Criteria**:
- 80% of jobs auto-matched
- <10 minute average matching time
- 95% payment success rate
- 4.5+ average rating
- 500+ bookings/month

---

### PHASE 3: Scale & Optimize (Months 7-9)

**Month 7: Analytics & Optimization**

Week 1-2:
- [ ] Analytics dashboard (admin)
- [ ] Key metrics tracking
- [ ] Conversion funnel analysis
- [ ] A/B testing framework
- [ ] Dynamic pricing algorithm v2:
  - Seasonal adjustments
  - Day-of-week pricing
  - Demand-based pricing

Week 3-4:
- [ ] Provider performance metrics
- [ ] Low-performer alerts
- [ ] Customer segmentation
- [ ] Cohort analysis
- [ ] Revenue reporting

**Month 8: Trust & Safety**

Week 1-2:
- [ ] Insurance inclusion (£50k standard)
- [ ] Insurance certificate validation
- [ ] Claims process
- [ ] Dispute resolution workflow
- [ ] Admin mediation tools

Week 3-4:
- [ ] Fraud detection (basic rules)
- [ ] Suspicious activity alerts
- [ ] Account verification (phone, email)
- [ ] Provider background checks (Onfido)
- [ ] Customer support ticketing

**Month 9: Mobile & Performance**

Week 1-2:
- [ ] Progressive Web App (PWA)
- [ ] Service workers (offline support)
- [ ] Push notifications (web + mobile)
- [ ] Performance optimization
- [ ] Code splitting

Week 3-4:
- [ ] React Native app (MVP)
- [ ] iOS app (TestFlight)
- [ ] Android app (Beta)
- [ ] GPS tracking (basic)
- [ ] App Store submission

**Phase 3 Success Criteria**:
- 1000+ bookings/month
- 50+ active providers
- 70% repeat customer rate
- <2 second page load
- 4.6+ average rating

---

### PHASE 4: Advanced Features (Months 10-12)

**Month 10: Real-Time Tracking**

Week 1-2:
- [ ] GPS tracking integration
- [ ] Live map display (customer view)
- [ ] Provider location updates
- [ ] ETA calculations
- [ ] Arrival notifications

Week 3-4:
- [ ] Job status milestones:
  - En route to pickup
  - Loading
  - In transit
  - Unloading
  - Completed
- [ ] Photo proof (pickup/delivery)
- [ ] Digital signature capture
- [ ] Proof of delivery

**Month 11: Route Optimization**

Week 1-2:
- [ ] Multi-job route planning
- [ ] Backhaul matching algorithm
- [ ] Route suggestions (providers)
- [ ] Fuel cost calculations
- [ ] Carbon footprint tracking

Week 3-4:
- [ ] Provider schedule optimization
- [ ] Job clustering (same area)
- [ ] Return journey matching
- [ ] Efficiency reports (providers)
- [ ] CO2 savings display (customers)

**Month 12: International & Storage**

Week 1-2:
- [ ] Multi-currency support
- [ ] International pricing
- [ ] Cross-border regulations
- [ ] Customs integration
- [ ] EU market launch prep

Week 3-4:
- [ ] Storage facility partnerships
- [ ] Storage booking flow
- [ ] Inventory management
- [ ] Storage → delivery booking
- [ ] Price match guarantee system

**Phase 4 Success Criteria**:
- 2000+ bookings/month
- 100+ providers
- International revenue: 10% of total
- 30% of jobs use route optimization
- £500k+ monthly GMV

---

### PHASE 5: Advanced Platform (Months 13+)

**AI & Machine Learning**:
- [ ] Demand forecasting
- [ ] Intelligent pricing recommendations
- [ ] Fraud detection (ML models)
- [ ] Customer support chatbot
- [ ] Image recognition (inventory verification)

**Provider Tools**:
- [ ] Fleet management (multiple vehicles)
- [ ] Driver management
- [ ] Expense tracking
- [ ] Tax reporting (HMRC integration)
- [ ] Earnings optimization suggestions

**Customer Features**:
- [ ] Loyalty program
- [ ] Referral system (give £25, get £25)
- [ ] Subscription plans (frequent movers)
- [ ] Corporate accounts (B2B)
- [ ] White-label solution

**Business Expansion**:
- [ ] Franchise model
- [ ] Partner API (integrations)
- [ ] Affiliate program
- [ ] Comparison site integrations
- [ ] Same-day delivery service

---

## Success Metrics

### Customer Metrics

**Acquisition**:
- Monthly active users (MAU)
- New customer registration rate
- Customer acquisition cost (CAC)
- Marketing channel effectiveness

**Engagement**:
- Quote-to-booking conversion rate (target: 30%+)
- Average booking value (target: £300+)
- Repeat booking rate (target: 40%+)
- Time to complete quote form (target: <2 min)

**Satisfaction**:
- Net Promoter Score (NPS) (target: 50+)
- Customer satisfaction (CSAT) (target: 4.5+/5)
- Review rating (target: 4.6+/5)
- Support ticket resolution time (target: <24hrs)

**Retention**:
- Customer retention rate (target: 60%+)
- Churn rate (target: <40%)
- Customer lifetime value (LTV) (target: £600+)
- LTV:CAC ratio (target: 3:1)

### Provider Metrics

**Supply**:
- Active providers (target: 100+ by month 12)
- Provider application rate
- Provider approval rate (target: 60%+)
- Provider churn rate (target: <20% annual)

**Engagement**:
- Jobs per provider/month (target: 15+)
- Job acceptance rate (target: 80%+)
- Response time to jobs (target: <30 min)
- Provider utilization rate (target: 70%+)

**Performance**:
- On-time rate (target: 95%+)
- Completion rate (target: 98%+)
- Cancellation rate (target: <2%)
- Average rating (target: 4.5+/5)

**Earnings**:
- Average earnings/provider/month (target: £3000+)
- Provider satisfaction (target: 4.0+/5)
- Payout timeliness (target: 100% on time)

### Platform Metrics

**Financial**:
- Gross Merchandise Value (GMV)
- Revenue (commission + fees)
- Take rate (commission %) (target: 18%)
- Monthly Recurring Revenue (MRR)
- Cash burn rate (pre-profitability)
- Path to profitability

**Operational**:
- Bookings per month
- Average booking value
- Matching success rate (target: 95%+)
- Average matching time (target: <10 min)
- Failed payment rate (target: <5%)
- Refund rate (target: <3%)

**Technical**:
- Platform uptime (target: 99.9%+)
- Average page load time (target: <2s)
- API response time p95 (target: <200ms)
- Error rate (target: <0.1%)
- Mobile app crash rate (target: <1%)

**Growth**:
- Month-over-month growth (target: 20%+)
- Market share (by region)
- Geographic expansion (cities covered)
- Service category expansion

---

## Risk Analysis

### Technical Risks

**Risk 1: Scalability Issues**
- **Likelihood**: Medium
- **Impact**: High
- **Mitigation**:
  - Load testing before launch
  - Horizontal scaling capability
  - Database optimization
  - Caching strategy
  - Performance monitoring

**Risk 2: Payment Processing Failures**
- **Likelihood**: Medium
- **Impact**: Critical
- **Mitigation**:
  - Use Stripe (99.99% uptime)
  - Implement retry logic
  - Manual fallback process
  - Real-time payment monitoring
  - Alternative payment method

**Risk 3: Security Breach**
- **Likelihood**: Low
- **Impact**: Critical
- **Mitigation**:
  - Security audits
  - Penetration testing
  - OWASP Top 10 compliance
  - Regular dependency updates
  - Bug bounty program

### Business Risks

**Risk 4: Two-Sided Marketplace Cold Start**
- **Likelihood**: High
- **Impact**: Critical
- **Mitigation**:
  - Recruit providers BEFORE customer launch
  - Target small geographic area initially
  - Manual matching if needed
  - Provider incentives (sign-up bonuses)
  - Gradual expansion

**Risk 5: Provider Quality Issues**
- **Likelihood**: Medium
- **Impact**: High
- **Mitigation**:
  - Thorough vetting process
  - Background checks
  - Insurance verification
  - Review system
  - Low-performer deactivation

**Risk 6: Customer Trust Issues**
- **Likelihood**: Medium
- **Impact**: High
- **Mitigation**:
  - Insurance included
  - Money-back guarantee
  - Provider verification badges
  - Review transparency
  - Strong customer support

**Risk 7: Regulatory Compliance**
- **Likelihood**: Medium
- **Impact**: High
- **Mitigation**:
  - Legal consultation
  - GDPR compliance
  - Insurance regulations research
  - Employment law (provider status)
  - Regular compliance audits

### Market Risks

**Risk 8: Competition**
- **Likelihood**: High
- **Impact**: Medium
- **Mitigation**:
  - Unique value proposition (40% savings)
  - Technology advantage (instant quotes)
  - Customer experience focus
  - Network effects (more providers = better service)
  - Fast iteration

**Risk 9: Economic Downturn**
- **Likelihood**: Medium
- **Impact**: High
- **Mitigation**:
  - Value positioning (cheaper alternative)
  - Diversified services (not just house moves)
  - B2B focus (less discretionary)
  - Cost control
  - Flexible business model

---

## Next Steps

### Immediate Actions

1. **Finalize Business Plan**:
   - Detailed financial projections
   - Funding requirements
   - Go-to-market strategy

2. **Legal Foundation**:
   - Company registration
   - Terms & conditions (customer, provider)
   - Privacy policy
   - Insurance requirements research

3. **Technical Setup**:
   - Choose tech stack (recommended: Next.js + NestJS)
   - Set up development environment
   - Initialize Git repository
   - Set up project management (Jira, Linear, etc.)

4. **Design Phase**:
   - Wireframes (all key screens)
   - High-fidelity mockups
   - Design system documentation
   - User testing (mockups)

5. **Team Formation**:
   - Hire key roles (see Development Team Structure)
   - Define responsibilities
   - Set up communication tools (Slack, etc.)
   - Sprint planning

6. **Provider Pre-Launch**:
   - Create provider landing page
   - Start recruiting providers
   - Target: 20 providers before launch
   - Conduct provider interviews

### Development Start

**Week 1**:
- Kickoff meeting
- Set up infrastructure (AWS, databases, etc.)
- Initialize codebase
- Sprint 1 planning

**Week 2-12**:
- Follow Phase 1 roadmap
- Bi-weekly sprints
- Regular stakeholder updates
- Continuous testing

**Month 3**:
- **MVP Launch**
- Limited geographic area
- Intensive support/monitoring
- Rapid iteration based on feedback

---

## Appendices

### A. Glossary

- **GMV**: Gross Merchandise Value (total value of transactions)
- **Take Rate**: Commission percentage
- **Backhaul**: Return journey (often empty)
- **Cubic Meter (m³)**: Volume measurement
- **Luton Van**: Large van with box body (15-20m³)
- **Man and Van**: Small removal service (1-2 people, small van)
- **Goods-in-Transit Insurance**: Coverage for items during transport

### B. Competitor Analysis

**Competitors**:
1. **AnyVan** (inspiration)
2. **Shiply** (similar model)
3. **Bark** (general services marketplace)
4. **Local removal companies** (traditional)

**Competitive Advantages**:
- Instant quotes (vs. waiting for quotes)
- Price transparency
- Technology-driven efficiency
- Insurance included
- Flexible booking terms

### C. User Personas

**Customer Persona 1: Young Professional**
- Age: 25-35
- Situation: Moving for new job
- Needs: Fast, affordable, reliable
- Tech-savvy: Yes
- Price sensitivity: High

**Customer Persona 2: Family**
- Age: 35-50
- Situation: Upgrading to larger home
- Needs: Full-service, careful handling
- Tech-savvy: Medium
- Price sensitivity: Medium

**Provider Persona 1: Sole Trader**
- Age: 30-45
- Experience: 5+ years
- Fleet: 1-2 vans
- Tech-savvy: Medium
- Needs: Consistent work, simple tools

**Provider Persona 2: Small Company**
- Size: 3-10 employees
- Fleet: 3-5 vehicles
- Tech-savvy: High
- Needs: Route optimization, efficiency

---

**Document End**

For questions or clarifications, contact: [Your contact information]

Version history:
- v1.0 (6 Jan 2026): Initial document
# anyvan
