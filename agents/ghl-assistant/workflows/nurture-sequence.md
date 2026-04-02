# Long-Term Nurture Sequence Workflow

## Overview
Keeps your business top-of-mind for leads who aren't ready to book yet. Most beauty clients don't book on first contact — this sequence builds trust over weeks through education, social proof, and gentle offers until they're ready.

## Trigger
- **Event:** Contact tagged `nurture` (manually or automatically)
- **Auto-trigger:** Contact has no booking after 14 days of being in the system
- **Conditions:** Contact is NOT currently in another active workflow (lead response, no-show, etc.)

## Workflow Steps

### Week 1: Educational Email
**Wait:** 7 days from trigger

**Send Email:**
- **Subject:** [Tip] How to [relevant tip based on service interest]
- **Body includes:**
  - Genuinely useful tip related to their interest area
  - Examples by niche:
    - **Lashes:** "How to make your lash extensions last 2x longer"
    - **Hair:** "3 products your colorist wishes you'd use at home"
    - **Skin:** "The nighttime routine dermatologists actually recommend"
    - **Nails:** "How to keep your manicure chip-free for 2+ weeks"
  - Subtle mention of your expertise: "This is what we tell all our clients..."
  - No hard sell — just value

### Week 2: Social Proof Email
**Wait:** 14 days from trigger

**Send Email:**
- **Subject:** See what {{business.name}} clients are saying
- **Body includes:**
  - 2-3 client testimonials (text or screenshot)
  - Before/after photos (with client permission)
  - Star rating badge
  - "Ready to see results like these?" + booking link
  - Casual, not pushy

### Week 3: FAQ Email
**Wait:** 21 days from trigger

**Send Email:**
- **Subject:** Your top questions about [service], answered
- **Body includes:**
  - 4-5 most common questions for their service interest
  - Examples:
    - "Does it hurt?"
    - "How long does it last?"
    - "What's the price range?"
    - "How do I prepare for my appointment?"
    - "What if I don't like it?"
  - Honest, reassuring answers
  - "Still have questions? Just reply — I'm happy to help"

### Week 4: Soft Offer Email
**Wait:** 28 days from trigger

**Send Email:**
- **Subject:** A little something for you, {{contact.first_name}}
- **Body includes:**
  - First-time client special offer
  - Clear value statement (what they get, what it normally costs, what they pay)
  - Expiration date (2 weeks from send)
  - Direct booking link with offer code
  - "No pressure — just wanted to make it easy for you to try us out"

### Week 6: Check-In SMS
**Wait:** 42 days from trigger

**Send SMS:**
```
Still thinking about {{contact.service_interest}}? Happy to answer any questions! Just reply here or book when you're ready: {{links.booking}}
```

### Week 8: Seasonal / Timely Offer
**Wait:** 56 days from trigger

**Send Email:**
- **Subject:** [Seasonal hook — e.g., "Summer-ready skin starts now"]
- **Body includes:**
  - Timely angle tied to season, holiday, or event
  - Relevant service recommendation
  - Limited-time seasonal offer
  - Booking link

### After 90 Days: Cold List Transition
**Wait:** 90 days from trigger
**Condition:** Contact has NOT booked AND has NOT engaged (no opens, no clicks, no replies) in the last 30 days

**Actions:**
- Remove tag: `nurture`
- Add tag: `cold-lead`
- Move to monthly newsletter/broadcast list only
- Reduce frequency to 1 email per month (monthly promo or update)

**If contact engages at any point during nurture:**
- Track which message they engaged with
- If they reply: notify owner for personal follow-up
- If they book: remove from nurture, add tag `nurture-converted`

## GHL Implementation Notes

### Custom Fields Required
- `service_interest` — used to personalize content throughout the sequence
- `nurture_start_date` — when they entered the sequence
- `nurture_stage` — which week they're on (for reporting)

### Tags Used
- `nurture` — currently in nurture sequence
- `nurture-converted` — booked during nurture sequence
- `cold-lead` — completed nurture without booking or engaging
- `nurture-engaged` — opened/clicked but hasn't booked yet

### Content Library
Create email templates for each niche you serve:
- **Lash niche:** lash care tips, lash FAQ, lash before/afters
- **Hair niche:** hair care tips, color FAQ, transformation photos
- **Skin niche:** skincare routine tips, facial FAQ, glow-up photos
- **Nail niche:** nail care tips, manicure FAQ, nail art showcase

Store these as GHL email templates and use conditional logic to send the right content based on `service_interest`.

### Engagement Tracking
- Track email opens and clicks at each step
- If a contact opens 3+ emails but doesn't book, trigger an owner alert for personal outreach
- If a contact never opens any email, check if email is valid / move to SMS-only nurture

### Key Metrics to Track
- Nurture-to-booking conversion rate
- Average time in nurture before booking
- Which email in the sequence drives the most bookings
- Engagement rate by week
- Cold list size growth (indicates top-of-funnel issue if growing too fast)

## Customization
- Shorten sequence to 4 weeks for lower-priced services (nails, brows)
- Extend to 12 weeks for high-ticket services (full transformations, packages)
- Add SMS versions of each email for contacts who prefer text
- Integrate with social media: "Follow us on IG for daily inspo" in early emails
- For referral leads, add a "your friend [referrer] recommended us" angle
- Pair with the `seasonal_promos` preset from your niche configuration for Week 8 content
