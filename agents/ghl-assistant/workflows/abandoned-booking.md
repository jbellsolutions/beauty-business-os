# Abandoned Booking Recovery Workflow

## Overview
Captures potential clients who visited the booking page but didn't complete their appointment. These are high-intent leads — they were interested enough to look at your availability. A gentle nudge often converts them.

## Trigger
- **Event:** Contact visited booking page but did not complete a booking (tracked via GHL pixel, UTM tag, or webhook)
- **Alternative trigger:** Contact tagged `abandoned-booking` manually or via integration
- **Conditions:** Contact has a valid phone number or email AND has NOT booked in the last 24 hours

## Workflow Steps

### Step 1: Helpful SMS (1 hour after abandonment)
**Wait:** 1 hour

**Send SMS:**
```
Hey {{contact.first_name}}! Noticed you were checking out our booking page. Have questions about any of our services? Happy to help! Just reply here
```

### Step 2: Services + Social Proof Email (24 hours, conditional)
**Wait:** 24 hours (from trigger)
**Condition:** Contact has NOT replied AND has NOT booked

**Send Email:**
- **Subject:** Not sure which service is right for you?
- **Body includes:**
  - Top 3 most popular services with brief descriptions and pricing
  - 2-3 client testimonials with results
  - "Most popular for first-time clients: [service name]"
  - Direct booking link: `{{links.booking}}`
  - "Reply to this email with any questions — happy to help you choose!"

### Step 3: Urgency SMS (3 days after abandonment, conditional)
**Wait:** 3 days (from trigger)
**Condition:** Contact has NOT replied AND has NOT booked

**Send SMS:**
```
Hey {{contact.first_name}}! Just wanted to let you know we have a few openings this week. Would you like me to hold a spot for you? Book here: {{links.booking}}
```

### Step 4: Tagging + Tracking
**Actions (on trigger):**
- Add tag: `abandoned-booking`
- Add internal note: "Visited booking page on {{event.date}}, did not complete"

**If contact books at any step:**
- Add tag: `abandoned-booking-recovered`
- Remove tag: `abandoned-booking`
- Track: revenue recovered from abandoned bookings

**After full sequence with no booking:**
- Add tag: `abandoned-booking-unrecovered`
- Move to nurture sequence (see nurture-sequence.md)

## GHL Implementation Notes

### Tracking Setup
**Option A: GHL Booking Page Pixel**
1. Add the GHL tracking pixel to your booking page
2. Create a trigger: "Page visited" = booking URL
3. Add condition: "Appointment NOT created" within 30 minutes of page visit

**Option B: UTM + Tag Trigger**
1. Use tagged booking links in your marketing (e.g., `?utm_source=instagram`)
2. Trigger on link click + no booking within 1 hour

**Option C: Form Abandonment**
1. If using a multi-step booking form, trigger when step 1 is completed but final step is not

### Custom Fields Required
- `abandoned_booking_date` — date of last abandonment
- `abandoned_booking_count` — number of times they've abandoned

### Tags Used
- `abandoned-booking` — currently in recovery sequence
- `abandoned-booking-recovered` — booked after receiving recovery messages
- `abandoned-booking-unrecovered` — did not book after full sequence

### Key Metrics to Track
- Abandoned booking rate
- Recovery rate (% that book after sequence)
- Revenue recovered monthly
- Most common drop-off point (if multi-step form)
- Which message (SMS 1, Email, SMS 2) drives the most recoveries

## Customization
- For luxury/high-ticket services, replace SMS 1 with a personal voice note or phone call
- Add a first-time client offer in Step 3 instead of urgency messaging
- If you know which service they were viewing, personalize all messages to that service
- A/B test: urgency ("limited spots") vs. incentive ("10% off first visit") in Step 3
- For returning clients who abandoned, use warmer "welcome back" language
