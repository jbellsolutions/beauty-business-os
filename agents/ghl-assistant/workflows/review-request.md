# Post-Service Review Request Workflow

## Overview
Automates asking happy clients for Google reviews at the perfect moment — after they've had time to enjoy their results but before the excitement fades. Reviews are the number one driver of new bookings for local beauty businesses.

## Trigger
- **Event:** Appointment status changed to "Completed" (or manual trigger via tag `request-review`)
- **Conditions:** Contact has NOT been sent a review request in the last 30 days

## Workflow Steps

### Step 1: Review Request SMS (24 hours after service)
**Wait:** 24 hours

**Send SMS:**
```
Hey {{contact.first_name}}! Hope you're still loving your {{appointment.service}}! Would you mind leaving us a quick Google review? It means the world: {{links.google_review}}
```

### Step 2: Reminder Email (3 days, conditional)
**Wait:** 3 days (from trigger)
**Condition:** Contact has NOT been tagged `left-review`

**Send Email:**
- **Subject:** How was your experience, {{contact.first_name}}?
- **Body includes:**
  - "We loved having you in!"
  - Simple 1-click link to Google review
  - Brief instruction: "It only takes 30 seconds — just click the link and leave a star rating"
  - Optional: photo of their service area / the vibe of the salon
  - "Your review helps other people like you find us"

### Step 3: Thank You (on review submission)
**Trigger:** Contact tagged `left-review` (manually or via review monitoring tool)

**Send SMS:**
```
Thank you so much for the review, {{contact.first_name}}! You're the best. We can't wait to see you next time!
```

**Actions:**
- Add tag: `left-review`
- Add tag: `vip-potential` (reviewers are your best clients)
- Remove from review request sequence
- Log review in tracking

### Step 4: Tracking + Tagging
**Actions (on trigger):**
- Add tag: `review-requested`
- Update custom field: `last_review_request_date`
- Increment: `review_requests_sent_count`

**After full sequence with no review:**
- Add tag: `review-request-no-response`
- Do NOT ask again for at least 90 days

## GHL Implementation Notes

### Custom Fields Required
- `last_review_request_date` — date, prevents over-asking
- `review_requests_sent_count` — number, lifetime tracking
- `reviews_left_count` — number, tracks how many reviews they've left

### Tags Used
- `review-requested` — sent the review ask
- `left-review` — confirmed they left a review
- `review-request-no-response` — completed sequence without reviewing

### Google Review Link Setup
1. Go to Google Business Profile
2. Click "Ask for reviews" to get your short link
3. Store as `{{links.google_review}}` in GHL custom values
4. Alternative: Use a redirect link you control so you can track clicks

### Review Monitoring
- **Option A:** Manually tag contacts as `left-review` when you see new reviews
- **Option B:** Use a tool like Grade.us, BirdEye, or Podium to auto-detect
- **Option C:** Check Google Business Profile weekly and match names to contacts

### Key Metrics to Track
- Review requests sent (monthly)
- Reviews received (monthly)
- Conversion rate (requests to reviews)
- Average star rating trend
- Revenue impact of review volume increase

## Customization
- For services with visible results (lashes, nails, hair color), wait 48 hours instead of 24 so they can show friends first
- Add a photo request: "Would you mind sharing a photo of your [service]? We'd love to feature you!"
- For repeat clients who already left a review, skip this workflow
- Rotate review platforms: Google first, then Yelp, then Facebook on subsequent visits
- Consider a small thank-you gesture for reviewers (not a bribe — just appreciation, like a sample product on next visit)
