# No-Show Follow-Up Workflow

## Overview
Recovers revenue from missed appointments with empathetic, non-judgmental messaging. No-shows cost beauty businesses thousands per year — this workflow brings clients back without burning the relationship.

## Trigger
- **Event:** Appointment status changed to "No Show"
- **Conditions:** Contact has a valid phone number

## Workflow Steps

### Step 1: Gentle SMS (15 minutes after no-show)
**Wait:** 15 minutes

**Send SMS:**
```
Hey {{contact.first_name}}, we missed you today! No worries at all — life happens. Would you like to reschedule? I have availability this week: {{links.booking}}
```

### Step 2: "We Saved Your Spot" Email (24 hours, conditional)
**Wait:** 24 hours
**Condition:** Contact has NOT replied to Step 1

**Send Email:**
- **Subject:** We saved a spot for you, {{contact.first_name}}
- **Body includes:**
  - Warm, zero-guilt tone
  - "We know things come up — your appointment is easy to rebook"
  - Direct booking link with pre-selected service
  - Mention of cancellation policy (gentle, informational — not threatening)
  - "Just reply to this email if you need help finding a time"

### Step 3: Incentive SMS (3 days after no-show, conditional)
**Wait:** 3 days (from trigger)
**Condition:** Contact has NOT replied AND has NOT rebooked

**Send SMS:**
```
Still want to come in? Here's 10% off to reschedule: {{links.booking_with_discount}}
```

### Step 4: Tagging + Tracking
**Actions (immediate on trigger):**
- Add tag: `no-show`
- Update custom field: `no_show_count` (increment by 1)
- Add internal note: "No-show on {{appointment.date}} for {{appointment.service}}"

**After Step 3 completes (if no rebook):**
- Add tag: `no-show-unrecovered`
- Move pipeline stage to: **At Risk**

**If client rebooks at any step:**
- Remove tag: `no-show-unrecovered`
- Add tag: `no-show-recovered`
- Send owner notification: "{{contact.first_name}} rebooked after no-show!"

## GHL Implementation Notes

### Custom Fields Required
- `no_show_count` — number value, tracks repeat no-shows
- `last_no_show_date` — date of most recent no-show

### Tags Used
- `no-show` — permanent tag for tracking
- `no-show-recovered` — rebooked after no-show sequence
- `no-show-unrecovered` — did not rebook after full sequence

### Discount Code Setup
- Create a 10% discount code in your booking system
- Use a unique code per no-show recovery (e.g., `MISSEDYOU10`) for tracking
- Set expiration: 7 days from send

### Repeat No-Show Logic
- **2nd no-show:** Same workflow runs but owner gets an alert
- **3rd no-show:** Workflow sends owner alert instead of discount; owner decides how to handle
- **Condition:** If `no_show_count >= 3`, skip Step 3 (no discount) and notify owner for manual outreach

### Key Metrics to Track
- No-show rate (monthly)
- Recovery rate (% of no-shows that rebook)
- Revenue recovered from no-show sequence
- Repeat no-show offenders

## Customization
- Adjust discount percentage based on service value
- For high-value services ($200+), consider a phone call instead of SMS at Step 1
- Add a deposit requirement after first no-show (mention in email)
- Soften or remove discount for premium/luxury positioning
