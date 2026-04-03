# Product Template Manifest

This repo is a **productized AI business operating system** built on Claude Code. It's designed to be cloned, configured for any business vertical, and sold as a turnkey product.

---

## How It Works

1. Customer receives this repo (download, clone, or airdrop)
2. Opens it in Claude Code (desktop app, CLI, or IDE extension)
3. Says **"set me up"**
4. AI walks them through 10-15 conversational questions
5. AI auto-configures their CRM (GoHighLevel) — pipeline, workflows, automations
6. AI opens their dashboard locally in the browser
7. AI offers custom dashboard option (self-service walkthrough or book a setup call)
8. They're live. They just talk to their business from now on.

**Zero technical knowledge required. No code. No settings. Just conversation.**

---

## Product Architecture

```
business-os/
├── CLAUDE.md                    # Brain — all AI behavior, setup wizard, rules
├── PRODUCT.md                   # This file — product template manifest
├── CLIENT_CONFIG.md             # Generated during setup — the customer's business profile
├── README.md                    # Customer-facing install guide (3 steps)
│
├── config/
│   ├── vertical.json            # Which vertical this repo is configured for
│   ├── voice-presets/           # Brand voice options (fun, professional, bold, etc.)
│   └── niche-presets/           # Industry sub-niches with defaults
│
├── agents/
│   ├── coo/                     # Chief Operating Officer — daily ops, revenue, tasks
│   ├── content/                 # Content Multiplier — Creator/Critic/Approver pipeline
│   │   └── titan-genome/        # Swipe files, style analysis, content DNA
│   ├── ghl-assistant/           # GoHighLevel CRM management
│   │   └── workflows/           # Pre-built automation workflows
│   └── image-gen/               # AI image generation (Replicate/Flux)
│       └── templates/           # Image prompt templates
│
├── setup/
│   ├── ghl-setup.md             # GHL auto-configuration spec (pipeline + workflows)
│   ├── dashboard-offer.md       # Post-setup dashboard customization flow
│   ├── vertical-config.json     # Current vertical definition + available verticals
│   └── CREATE-VERTICAL.md       # How to clone this for a new business type
│
├── playbooks/
│   ├── organic-marketing/       # Content strategy, hooks, hashtags, algorithm tips
│   ├── posting/                 # Auto-posting, Metricool, ManyChat setup
│   └── client-ops/              # Booking, retention, review collection
│
├── funnels/
│   ├── booking/                 # Booking funnel spec + email sequences
│   ├── lead-capture/            # Lead magnet funnel + nurture sequences
│   └── referral/                # Referral program spec
│
├── templates/                   # Content templates (social, email, blog, video, etc.)
├── heartbeats/                  # Scheduled check-ins (morning briefing, weekly review, etc.)
├── dashboard/                   # Local HTML dashboard (index.html — opens in browser)
├── docs/                        # Getting started, FAQ, troubleshooting
├── training/                    # Video outline for setup walkthrough recording
└── .mcp/
    └── settings.json            # MCP server configs (GHL, Calendar, Gmail)
```

---

## Vertical System

A **vertical** is a business type this product serves. Each vertical defines:

- **Niche presets** — Industry-specific services, pricing, seasonal promos, content themes
- **Voice presets** — Brand voice options appropriate for the industry
- **Pipeline stages** — CRM pipeline customized for that business type
- **Workflows** — Automated sequences relevant to that industry
- **Content playbooks** — Marketing strategies, hooks, hashtags for that niche
- **Funnel templates** — Booking, lead capture, and referral funnels
- **Dashboard** — Visual dashboard with industry-relevant metrics

### Current Verticals

| Vertical | Status | Niches Included |
|----------|--------|----------------|
| **Beauty** | Live | Esthetician, Lash Tech, Brow Artist, Med Spa, Nail Tech, Hair Stylist, Massage Therapist, Electrologist, Body Contouring |
| **Recruiting** | Planned | Staffing Agency, Executive Search, Temp Agency, RPO, Freelance Recruiter |
| **[Your Business]** | Fork it | See `setup/CREATE-VERTICAL.md` |

### Cloning for a New Vertical

```bash
# 1. Fork/clone this repo
git clone https://github.com/jbellsolutions/beauty-business-os.git my-vertical-os

# 2. Update the vertical config
# Edit setup/vertical-config.json → change vertical name, niches, pipeline

# 3. Replace niche presets
# Delete beauty niches from config/niche-presets/
# Add your industry's niches (see CREATE-VERTICAL.md for schema)

# 4. Update playbooks
# Rewrite organic-marketing playbook for your industry
# Update hooks, hashtags, content calendar

# 5. Update dashboard
# Rebrand dashboard/index.html (colors, labels, metrics)

# 6. Update CLAUDE.md identity section
# Change industry expertise, terminology, seasonality knowledge

# 7. Test: open in Claude Code, say "set me up"
```

Full guide: `setup/CREATE-VERTICAL.md`

---

## Pricing Model

| Tier | What They Get | Price |
|------|-------------|-------|
| **DIY Install** | Repo + README instructions. They set up themselves. | $500 |
| **Guided Setup** | 30-min screen share. We walk them through it. | $1,000 |
| **Full Service** | We set up everything — GHL, dashboard, content, automations. | $1,500 |
| **Monthly Maintenance** | Ongoing support, updates, content reviews, optimization. | $200/month |

### Custom Dashboard Add-On

| Option | What They Get | Price |
|--------|-------------|-------|
| **DIY Dashboard** | Walkthrough guide to customize colors, branding, metrics. Free with any tier. | $0 |
| **Custom Dashboard** | We build a fully branded dashboard deployed to their own URL. | $300 one-time |

---

## What Makes This a Product (Not a Project)

1. **Self-contained** — One repo. No external dependencies to install. No build step.
2. **Self-configuring** — Says "set me up" and the AI does everything. No manual config files.
3. **Industry-aware** — Pre-loaded with niche expertise, not generic business advice.
4. **GHL-native** — Automatically configures the customer's CRM, not just a content tool.
5. **Dashboard included** — Professional local dashboard, not just a terminal experience.
6. **Scalable** — One template serves unlimited customers across unlimited verticals.
7. **Recurring revenue** — $200/month maintenance per customer. 80 customers = $16K/month.

---

## Revenue Math

| Milestone | Customers | One-Time | Monthly Recurring | Total Monthly |
|-----------|-----------|----------|-------------------|---------------|
| Month 3 | 10 | $7,500 | $2,000 | $9,500 |
| Month 6 | 35 | $5,000 | $7,000 | $12,000 |
| Month 9 | 60 | $5,000 | $12,000 | $17,000 |
| Month 12 | 80 | $3,000 | $16,000 | $19,000 |

*Assumes blended $750 average one-time + $200/mo maintenance. New customer acquisition slows as recurring compounds.*

---

## Deployment Checklist (Per Customer)

- [ ] Customer has Claude Code installed (free)
- [ ] Customer has GoHighLevel account ($97/month — their cost)
- [ ] Send them the repo (zip, GitHub invite, or Airdrop)
- [ ] They open it, say "set me up" — AI handles the rest
- [ ] AI configures GHL (pipeline, workflows, automations)
- [ ] AI opens dashboard locally
- [ ] Customer chooses: DIY dashboard customization or book custom setup
- [ ] If custom: schedule call, build branded dashboard, deploy to their Vercel
- [ ] Monthly check-in begins (maintenance tier)

---

*Built with Claude Code. Powered by Titan Genome. Sold by you.*
