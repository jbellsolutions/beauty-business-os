# Booking Funnel Specification

## Purpose

Convert interested leads into booked appointments. This is the primary revenue-generating funnel — every other funnel ultimately drives traffic here.

## Funnel Flow

```
Landing Page → Service Selection → Calendar Booking → Thank You / Confirmation
```

### Page 1: Landing Page (`landing-page.md`)
- Hero section with service imagery and headline
- Social proof (reviews, ratings, testimonials)
- Service list with pricing
- About the provider
- FAQ section
- Primary CTA: "Book Now" button

### Page 2: Service Selection
- Display services from niche preset with names, descriptions, durations, and prices
- Allow client to select service before seeing calendar
- Optional: package/bundle upsell
- GHL: Use custom fields to track selected service

### Page 3: Calendar Booking
- GHL Calendar widget embedded
- Shows real-time availability
- Client enters: name, phone, email, service (pre-filled from step 2)
- Optional: deposit collection via Stripe integration

### Page 4: Thank You / Confirmation (`thank-you.md`)
- Appointment details displayed
- Preparation instructions
- Add-to-calendar button
- Referral prompt
- Social follow links

## GHL Integration

| Action | GHL Feature | Trigger |
|--------|------------|---------|
| Contact created | Contacts API | Form submission |
| Pipeline stage update | Opportunities API | Move to "Booked" stage |
| Calendar event created | Calendar API | Booking confirmed |
| Confirmation email sent | Workflow | On booking |
| 24hr reminder | Workflow | Time-based trigger |
| 2hr reminder | Workflow | Time-based trigger |
| Post-visit follow-up | Workflow | Appointment status = completed |

### Pipeline Stages
1. New Lead
2. Booked
3. Confirmed (replied or clicked confirmation)
4. Completed
5. Rebook Pending
6. Rebooked

## Email Sequence

| Email | Timing | Template |
|-------|--------|----------|
| Booking confirmation | Immediately | `emails/confirmation.md` |
| 24-hour reminder | 24 hours before | `emails/reminder-24hr.md` |
| 2-hour reminder | 2 hours before | `emails/reminder-2hr.md` |
| Post-visit follow-up | 2 hours after | `emails/post-visit.md` |

## Tracking

### UTM Parameters
All inbound links should use consistent UTM structure:
- `utm_source`: Where traffic comes from (instagram, google, facebook, referral, email)
- `utm_medium`: Channel type (organic, paid, social, email, sms)
- `utm_campaign`: Specific campaign name (spring-promo-2025, valentines-special)
- `utm_content`: Ad or post variant (carousel-1, story-cta, bio-link)

### Key Metrics
- **Landing page views**: Total traffic
- **Booking rate**: Bookings / page views (target: 8-15%)
- **Show rate**: Attended / booked (target: 85-95%)
- **Rebook rate**: Rebooked within 30 days / completed (target: 40-60%)
- **Revenue per booking**: Average ticket value
- **Cost per booking**: Ad spend / bookings (if running paid traffic)

### Tracking Implementation
- GHL form submissions tracked by source
- UTM parameters stored on contact record as custom fields
- Conversion events fired to Facebook Pixel / Google Analytics on booking
- Dashboard widget shows booking funnel metrics

## Customization by Niche

The landing page copy, service list, FAQ, and preparation instructions all pull from the active niche preset. When generating this funnel:

1. Load `presets/niches/{niche}.md` for service names, prices, and descriptions
2. Load `presets/voices/{voice}.md` for tone and language style
3. Populate templates with niche-specific content
4. Adjust FAQ based on common questions for that service type

## Notes

- Mobile-first design is critical — 80%+ of beauty service traffic is mobile
- Page load speed matters: keep images optimized, minimal scripts
- Calendar widget should show next 2 weeks of availability by default
- Deposit collection reduces no-shows by 40-60% (recommend $25-50 or 20% of service price)
