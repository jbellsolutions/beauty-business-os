# Speed-to-Lead Response Workflow

## Overview
Automatically responds to new leads within seconds to maximize conversion. Speed-to-lead is the single biggest factor in whether a new inquiry becomes a booked client.

## Trigger
- **Event:** New contact created (any source — form submission, Facebook ad, Instagram DM, website chat, manual entry)
- **Conditions:** Contact has a valid phone number or email

## Workflow Steps

### Step 1: Initial SMS (30 seconds after trigger)
**Wait:** 30 seconds

**Send SMS:**
```
Hey {{contact.first_name}}! Thanks for reaching out to {{business.name}}. We'd love to help you with {{contact.service_interest}}. Would you like to book a consultation? Reply YES and I'll send you our available times!
```

### Step 2: Welcome Email (immediately after SMS)
**Send Email:**
- **Subject:** Welcome to {{business.name}} — Here's What We Offer
- **Body includes:**
  - Warm personal welcome from the owner
  - Overview of services (pulled from business profile)
  - Direct booking link: `{{links.booking}}`
  - Social proof snippet (star rating + review count)
  - Social media links
  - Contact info / reply instructions

### Step 3: Follow-Up SMS (5 minutes, conditional)
**Wait:** 5 minutes
**Condition:** Contact has NOT replied to Step 1

**Send SMS:**
```
No pressure at all! Whenever you're ready, here's our booking link to pick a time that works for you: {{links.booking}}
```

### Step 4: Tag + Pipeline
**Actions (immediate):**
- Add tag: `new-lead`
- Add tag: `source-{{contact.source}}` (tracks where they came from)
- Add to pipeline: **Sales Pipeline**
- Set pipeline stage: **New Lead**
- Set lead source field

### Step 5: Owner Notification
**Send notification to business owner:**
- **Channel:** Push notification + in-app
- **Message:** "New lead! {{contact.first_name}} {{contact.last_name}} just inquired about {{contact.service_interest}}. They've been sent a welcome message and booking link."

## GHL Implementation Notes

### Custom Fields Required
- `service_interest` — auto-populated from form/ad or set to "our services" as default
- `lead_source` — Facebook, Instagram, Website, Referral, Walk-in, Other

### Tags Used
- `new-lead` — identifies all new leads for reporting
- `source-{platform}` — tracks acquisition channel

### Pipeline Setup
- **Pipeline:** Sales Pipeline
- **Stages:** New Lead > Contacted > Consultation Booked > Showed Up > Converted > Lost

### Key Metrics to Track
- Time from lead creation to first response
- Reply rate on initial SMS
- Booking rate from lead response sequence
- Conversion rate by lead source

## Customization
- Adjust wait times based on business hours (don't text at 2am)
- Swap SMS copy for different service niches (lashes, nails, hair, skin)
- Add a third follow-up at 24 hours for high-value services (e.g., full sets, facials)
- For Instagram DM leads, use a more casual tone
