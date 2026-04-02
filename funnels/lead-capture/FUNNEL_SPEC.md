# Lead Capture Funnel Specification

## Purpose

Capture email and phone number from cold traffic (social media, search, ads) by offering a valuable free resource. Nurture these leads with a 4-email sequence that builds trust and converts them into booked clients.

## Funnel Flow

```
Opt-in Page → Thank You / Download → Nurture Email Sequence (4 emails over 10 days)
```

## Lead Magnet Options by Niche

Choose the lead magnet that best fits your niche, or ask Claude to generate one for you.

| Niche | Lead Magnet Ideas |
|-------|-------------------|
| Lash Extensions | "The Ultimate Lash Aftercare Cheat Sheet", "5 Things to Know Before Your First Lash Appointment" |
| Facials / Skincare | "5 Skincare Mistakes That Are Aging You Faster", "Your Perfect Morning Skincare Routine (Quiz)" |
| Hair Stylist | "How to Make Your Color Last 2x Longer", "The Seasonal Hair Care Guide" |
| Waxing | "First-Time Wax? Here's Everything You Need to Know", "The Smooth Skin Prep Guide" |
| Microblading / PMU | "Microblading vs. Other Brow Options: Which Is Right for You?", "What to Expect: Your Complete Microblading Guide" |
| Nails | "How to Make Your Manicure Last 2 Weeks+", "Nail Shape Guide: Finding Your Perfect Fit" |
| Med Spa | "Anti-Aging 101: The Treatments That Actually Work", "Your Guide to Injectable Options" |
| Makeup Artist | "5-Minute Everyday Makeup Routine", "How to Find Your Perfect Foundation Match" |

## Pages

### Opt-in Page (`opt-in.md`)
- Clear headline about the lead magnet
- Benefit bullets (what they'll learn)
- Simple form: first name + email (phone optional)
- Trust signals and social proof

### Thank You Page
- Immediate download or access to lead magnet
- "Check your email" reminder
- Soft pitch: first-time client offer
- Social media follow links

## Nurture Email Sequence

| Email | Timing | File | Purpose |
|-------|--------|------|---------|
| Welcome | Immediately | `nurture/welcome.md` | Deliver lead magnet + introduce yourself |
| Value #1 | Day 3 | `nurture/value-1.md` | Educational content, build authority |
| Value #2 | Day 7 | `nurture/value-2.md` | FAQ content + social proof |
| Offer | Day 10 | `nurture/offer.md` | First-time client offer with booking link |

## GHL Integration

| Action | GHL Feature | Trigger |
|--------|------------|---------|
| Contact created | Contacts API | Form submission |
| Tag applied | Contact tags | "lead-magnet-{{slug}}" |
| Enters workflow | Workflows | Nurture sequence activated |
| Pipeline stage | Opportunities | "New Lead" stage |
| Lead source tracked | Custom fields | UTM parameters stored |

### Tags Applied
- `lead-magnet-downloaded`
- `lead-magnet-{{specific-magnet-slug}}`
- `source-{{utm_source}}`
- `nurture-active` (removed when sequence completes)
- `nurture-completed` (added when sequence finishes)

## Tracking

### Key Metrics
- **Opt-in rate**: Submissions / page views (target: 25-40%)
- **Email open rate**: Opens / delivered (target: 40-60% for welcome, 25-35% for nurture)
- **Click rate**: Clicks / opens (target: 5-10%)
- **Lead-to-booking rate**: Bookings / leads (target: 10-20% within 30 days)
- **Cost per lead**: Ad spend / leads (if running paid traffic)

### Attribution
- Track which lead magnet each contact downloaded
- Track the source (UTM) of each lead
- Measure booking conversion rate by lead magnet and by source
- Use this data to optimize: double down on best-performing magnets and channels

## Content Generation

Ask Claude to generate your lead magnet content:

```
"Create a lead magnet for my [niche] business called [title]. Make it a [format: PDF guide / checklist / cheat sheet]. It should be [X] pages and cover [topics]."
```

Claude will generate the content in your brand voice using the active voice preset.

## Notes

- Keep the opt-in form short: name + email minimum, phone optional (but valuable for SMS)
- A/B test headlines on the opt-in page — even small changes can double conversion rates
- The lead magnet should be genuinely valuable, not just a sales pitch
- Nurture emails should be 80% value, 20% promotion
- Set up a re-engagement sequence for leads who don't book within 30 days
