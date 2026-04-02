# Email Newsletter Template

> Monthly email newsletter template for staying top-of-mind with your client list. Tell Claude what you want to feature and it will generate the full newsletter in your brand voice.

---

## Newsletter Structure

### Subject Line

**Primary:** {{subject_line}}
**A/B Test:** {{subject_line_variant}}

**Subject line formulas:**
- "[Month] at {{business_name}}: [teaser]"
- "What's new + a little treat for you"
- "Your [month] beauty forecast is here"
- "[First_name], this month is going to be good"
- "The one thing you need this [season]"

**Preview text:** {{preview_text}} (40-90 characters, complements the subject)

---

### Header

- Business logo
- Brand colors
- Month / edition number (optional)

---

### Personal Greeting

```
Hi {{first_name}},

{{personal_opening}}
```

**Opening options:**
- Seasonal: "Can you believe it's already [month]? Here's what I've been up to..."
- Conversational: "I've been so excited to share this with you..."
- Gratitude: "Before we dive in — thank you for being part of this community."
- Direct: "I've got some good stuff for you this month. Let's get into it."

---

### Main Content Block

Choose ONE primary content type per newsletter:

**Option A: Tip / Educational**
```
[SECTION TITLE: e.g., "Your [Season] [Niche] Tip"]

{{educational_content — 150-250 words}}

Keep it actionable, specific, and tied to your expertise.
```

**Option B: Story / Personal Update**
```
[SECTION TITLE: e.g., "A Little Behind the Scenes"]

{{personal_story — 150-250 words}}

Share something real: a client win (with permission), a business milestone, a lesson learned, or something that inspired you.
```

**Option C: Seasonal Update**
```
[SECTION TITLE: e.g., "What's New This [Season]"]

{{seasonal_content — 150-250 words}}

New services, updated hours, product launches, or seasonal recommendations.
```

---

### Featured Service Spotlight

```
━━━━━━━━━━━━━━━━━━━━━━━━━

SERVICE SPOTLIGHT: {{service_name}}

{{service_description — 2-3 sentences}}

Duration: {{duration}} | Price: ${{price}}

Perfect for: {{ideal_client_description}}

[Book This Service →]({{booking_link}})

━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

### CTA Button

**Primary CTA:**
```
[{{cta_text}}]({{cta_link}})
```

**CTA options:**
- "Book Your [Month] Appointment"
- "Grab This Month's Special"
- "Schedule a Consultation"
- "Shop Recommended Products"
- "Claim Your Offer"

---

### Social Links Footer

```
━━━━━━━━━━━━━━━━━━━━━━━━━

Stay connected:
Instagram: @{{instagram_handle}}
TikTok: @{{tiktok_handle}}
Facebook: {{facebook_url}}

{{business_name}}
{{business_address}}
{{phone_number}}

[Unsubscribe]({{unsubscribe_link}}) | [Update Preferences]({{preferences_link}})
```

---

## Cadence

- **Recommended:** 1x per month (consistent, not overwhelming)
- **Send day:** Tuesday or Thursday (highest open rates for beauty/wellness)
- **Send time:** 10 AM local time
- **Segment:** Active clients (visited in last 6 months) vs. inactive (6+ months) — tailor content accordingly

## Monthly Content Calendar

| Month | Theme | Content Focus | Promo Tie-In |
|-------|-------|---------------|--------------|
| January | Fresh start | New year skincare/beauty reset tips | New Year special |
| February | Love/self-care | Self-care routine or Valentine's gift guide | Valentine's promo |
| March | Spring refresh | Transitional beauty tips | Spring special |
| April | Prep season | Prom/event prep tips | Event booking push |
| May | Appreciation | Mother's Day gift cards / pampering | Mother's Day promo |
| June | Summer ready | Summer beauty prep and protection | Summer special |
| July | Mid-year | Mid-year review, new services announcement | Mid-year offer |
| August | Back to routine | Getting back on schedule | Back-to-school promo |
| September | Fall transition | Fall beauty trends and tips | Fall special |
| October | Spooky/fun | Halloween looks or cozy fall vibes | Halloween promo |
| November | Gratitude + deals | Client appreciation + holiday prep | Black Friday / holiday |
| December | Holiday + reflection | Holiday gifting + year in review | Gift card push |

## GHL Configuration

- **Send via:** Email (GHL bulk email or integrated ESP)
- **List:** All contacts with tag "newsletter-subscribed"
- **Exclude:** Contacts with tag "unsubscribed" or "bounced"
- **Track:** Opens, clicks, unsubscribes
- **Template:** Save as reusable GHL email template

## Usage

Tell Claude:
```
"Write my newsletter for this month. Feature my new [service] and include a [season] tip."
```

Claude will generate the complete newsletter using your brand voice, niche details, and current promotions.
