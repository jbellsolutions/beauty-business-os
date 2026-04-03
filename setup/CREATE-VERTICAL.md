# How to Create a New Vertical

This guide walks you through cloning the Business OS template for a new industry. The beauty vertical is the reference implementation — you're adapting it for your target market.

**Time required:** 2-4 hours of focused work.

---

## What You're Building

A self-contained Claude Code repo that:
1. Knows everything about [your industry]
2. Asks the right setup questions for [your industry]
3. Configures GHL with the right pipeline for [your industry]
4. Generates content in the right voice for [your industry]
5. Opens a dashboard with the right metrics for [your industry]

---

## Step 1: Clone the Repo

```bash
git clone https://github.com/jbellsolutions/beauty-business-os.git [industry]-business-os
cd [industry]-business-os
rm -rf .git
git init
```

---

## Step 2: Update Vertical Config

Edit `setup/vertical-config.json`:

```json
{
  "current_vertical": "your-industry",
  "product_name": "Your Industry OS",
  "product_tagline": "Your AI-powered [industry] operating system."
}
```

Add your vertical to the `verticals` object with:
- `display_name` — Product name
- `tagline` — One-line pitch
- `industry` — Category
- `identity_context` — What the AI knows about this industry (2-3 sentences)
- `niches` — Sub-types (e.g., for recruiting: staffing-agency, executive-search, temp-agency)
- `voice_presets` — Which voice options make sense
- `pipeline_stages` — CRM stages for this business type
- `dashboard_theme` — Color palette
- `seasonality` — Seasonal business events

---

## Step 3: Create Niche Presets

For each niche in your vertical, create a JSON file in `config/niche-presets/`:

**Schema:**
```json
{
  "niche": "your-niche-slug",
  "display_name": "Your Niche Name",
  "common_services": ["Service 1", "Service 2", "Service 3"],
  "avg_price_range": {"min": 100, "max": 500},
  "content_themes": ["Theme 1 for social content", "Theme 2", "Theme 3"],
  "trending_hashtags": ["#hashtag1", "#hashtag2", "#hashtag3"],
  "seasonal_promos": {
    "q1": "Promotion idea for Q1",
    "q2": "Promotion idea for Q2",
    "q3": "Promotion idea for Q3",
    "q4": "Promotion idea for Q4"
  },
  "common_supplies": ["Supply 1", "Supply 2"],
  "reorder_cadence_days": 30,
  "ideal_posting_times": {"weekday": "12:00 PM", "weekend": "10:00 AM"},
  "competitor_keywords": ["competitor type 1", "competitor type 2"],
  "client_psychology": "What motivates clients in this niche. What they fear. What they value. How trust is built."
}
```

**Delete the beauty niche presets** and replace with yours:
```bash
rm config/niche-presets/esthetician.json
rm config/niche-presets/lash-tech.json
# ... etc
```

**Example for recruiting:**
- `staffing-agency.json` — temp staffing, light industrial, clerical
- `executive-search.json` — retained search, C-suite placements
- `technical-recruiting.json` — software engineers, data science, DevOps

---

## Step 4: Update Voice Presets (If Needed)

The 5 voice presets (`fun-girly`, `clean-professional`, `edgy-bold`, `warm-nurturing`, `luxury-elevated`) are fairly universal. You may want to:

- **Rename** presets to fit the industry (e.g., "fun-girly" → "casual-friendly" for recruiting)
- **Update `preferred_terms`** with industry-specific vocabulary
- **Update `avoided_terms`** with terms that don't apply
- **Update `cta_style`** with industry-appropriate calls to action

Or just keep the ones that fit and remove the rest.

---

## Step 5: Rewrite CLAUDE.md Identity Section

The top of `CLAUDE.md` defines the AI's identity. Replace the beauty-specific content:

### Replace "Who You Are"
- Change industry expertise from beauty to your industry
- Update example language (instead of "your 2 o'clock filler appointment" → "your 2 o'clock candidate interview")

### Replace "What You Understand"
- **Seasonality** — Your industry's seasonal patterns
- **Client psychology** — Why clients buy in your industry
- **Services and pricing** — Your industry's service model
- **Trends** — What's trending in your industry
- **Business models** — How businesses in your industry are structured

### Update Setup Wizard Questions
- Keep the universal questions (business name, location, team size, revenue goal, biggest challenge)
- Replace industry-specific questions:
  - "What are your top 3-5 services?" → relevant to your industry
  - "Where are you finding clients?" → relevant lead sources
  - "What booking system?" → relevant tools for your industry
  - "How do you want to sound?" → voice options that make sense

---

## Step 6: Update Playbooks

### Organic Marketing Playbook (`playbooks/organic-marketing/`)
- `PLAYBOOK.md` — Rewrite the marketing strategy for your industry
- `hooks-and-headlines.md` — New hooks relevant to your industry's content
- `hashtag-sets.md` — Industry-specific hashtag research
- `algorithm-guide.md` — Platform tips still apply (keep most of this)
- `content-calendar.md` — Weekly calendar with your industry's content pillars

### Posting Playbook (`playbooks/posting/`)
- Keep as-is — Metricool and ManyChat setup are universal

### Client Ops Playbook (`playbooks/client-ops/`)
- `booking-flow.md` — Update for your industry's booking process
- `client-retention.md` — Update retention strategies for your industry
- `review-collection.md` — Keep as-is (review collection is universal)

---

## Step 7: Update GHL Workflows

Edit `agents/ghl-assistant/workflows/` — update the messaging templates:

- `lead-response.md` — Change the SMS/email templates to match your industry
- `no-show-followup.md` — Update messaging
- `review-request.md` — Keep mostly the same
- `abandoned-booking.md` — Update for your booking process
- `nurture-sequence.md` — Rewrite educational content for your industry

Also update `setup/ghl-setup.md` if your pipeline stages are different.

---

## Step 8: Update Funnels & Templates

### Funnels (`funnels/`)
- Update booking funnel for your industry's conversion flow
- Update lead capture with relevant lead magnets
- Update referral program for your industry

### Templates (`templates/`)
- `social-post.md` — Update examples for your industry
- `email-newsletter.md` — Update for your audience
- `video-script.md` — Update hooks and topics
- Keep the template structure the same — just swap content

---

## Step 9: Update Dashboard

Edit `dashboard/index.html`:

1. **Branding** — Update product name, tagline, colors
2. **Onboarding wizard** — Update niche chips and voice cards for your vertical
3. **Metrics** — Update stat cards if your industry tracks different KPIs
4. **Content types** — Update post types in the content studio for your platforms

The dashboard is a single HTML file with no dependencies — all changes are in one place.

---

## Step 10: Update Supporting Files

- `README.md` — Update product name, description, install steps
- `PRODUCT.md` — Update pricing, revenue math if different
- `docs/GETTING-STARTED.md` — Update walkthrough for your industry
- `docs/FAQ.md` — Update FAQs
- `training/VIDEO_OUTLINE.md` — Update video script for your industry demo

---

## Step 11: Test

1. Open the repo in Claude Code
2. Say "set me up"
3. Walk through the full setup as if you're a customer
4. Verify:
   - [ ] Questions make sense for the industry
   - [ ] Niche presets load correctly
   - [ ] Voice presets sound right
   - [ ] GHL setup creates the right pipeline (if connected)
   - [ ] Dashboard opens and shows correct branding
   - [ ] Content generation produces industry-relevant content
   - [ ] Returning user greeting works

---

## Step 12: Deploy

```bash
git add -A
git commit -m "Initial [industry] vertical"
git remote add origin https://github.com/your-org/[industry]-business-os.git
git push -u origin main
```

---

## Checklist

- [ ] `setup/vertical-config.json` — Updated with new vertical
- [ ] `config/niche-presets/` — New niche JSONs for your industry
- [ ] `config/voice-presets/` — Updated or filtered for your industry
- [ ] `CLAUDE.md` — Identity, expertise, setup questions rewritten
- [ ] `playbooks/organic-marketing/` — Rewritten for your industry
- [ ] `agents/ghl-assistant/workflows/` — Messaging updated
- [ ] `funnels/` — Updated for your conversion flow
- [ ] `templates/` — Examples updated for your industry
- [ ] `dashboard/index.html` — Rebranded
- [ ] `README.md` — Updated product name and description
- [ ] `PRODUCT.md` — Updated if pricing differs
- [ ] Full "set me up" test passed
