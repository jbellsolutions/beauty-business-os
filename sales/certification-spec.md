# Certification Spec — "Beauty Business OS Level 1"

**Future repo:** `jbellsolutions/beauty-business-os-certification`
**Hosted at:** `jbellsolutions.github.io/beauty-business-os-certification/`
**Modeled on:** `claude-code-ecosystem-certification/` (same structure, beauty-adapted)

---

## What This Is

A login-gated GitHub Pages certification portal with 5 video modules + checklists. Takes a beauty professional from "what is this?" to "I'm using it daily" — then delivers the download.

This is the middle of the funnel. They came from the lead magnet, they're interested, now they complete a short course and get the product.

---

## Page Structure

### Pre-Login View

#### Topbar
```
[brand mark] Certification Portal — Beauty Business OS
                                              [Benefits] [Curriculum] [Log Out]
```

#### Hero / Auth Section (Split Layout)

**Left side — marketing copy:**
- **Eyebrow:** "Level One Certification"
- **H1:** "Beauty Business OS Level One Certification"
- **Headline:** (dynamically set from app.js data)
- **Subheadline:** (dynamically set)
- **Stat ribbon:** module count, total runtime, certification badge

**Marketing cards (2-column):**

Card 1:
- **Label:** "What This Is"
- **H2:** "A practical certification for running your beauty business with AI."
- **Body:** "A hands-on certification built around the actual product, not generic AI talking points, so you can watch the modules and immediately apply them to your business."

Card 2:
- **Label:** "Why You Should Do This"
- **H2:** "It takes you from curious to confident in under 30 minutes."
- **Body:** "This matters because the workflows in this certification can save you 10+ hours a week on content, marketing, and follow-ups once you start using what you learned."

**Audience panel:**
- **Who It Is For:** Solo estheticians, Lash techs, Med spa owners, Hair stylists, Brow artists, Nail techs, Body contouring specialists, Any beauty professional
- **Why Teams Buy It:** Onboard new hires in 30 minutes, Standardize marketing across locations, Replace agency dependency, Get every team member using the same system

**Right side — login card:**
- Hero art image
- "Enter the certification portal"
- "Use your email and password to access the full course library."
- Email + Password fields
- [Log In] button
- "Use any valid email and password to enter." (same open-access as existing cert)

### Post-Login View (Portal)

#### Portal Hero
- **Eyebrow:** "Certification Dashboard"
- **H2:** "Welcome to the course."
- **Body:** "Watch the modules in order, then use the checklist under each lesson to make sure you've got it."
- **Progress card:** "Getting Started → Confident User" / "Built for beauty professionals at every level."

#### Video Curriculum

5 modules, each with:
- Module number + title
- Video player (HTML5 `<video>` with poster + captions)
- Checklist of what they should now understand
- "Mark Complete" interaction (client-side localStorage)

---

## Curriculum — 5 Modules

### Module 1: "What Beauty Business OS Is" (3 min)
**What to record:** Positioning video. Not a demo — this is the "why."

Script outline:
- You're amazing at your craft. But the business side — content, marketing, follow-ups, booking, reporting — is eating you alive.
- What if your business had a brain? An AI partner that handles all of it, in your voice, for your services.
- Not another app. Not another dashboard. Just a conversation.
- That's Beauty Business OS. Built by someone who spent years in the beauty industry helping businesses like yours.
- In the next 4 modules, you're going to see exactly how it works and set it up yourself.

**Checklist:**
- [ ] Understand what Beauty Business OS does (AI business partner, not another tool)
- [ ] Understand what it replaces (marketing agency, social media manager, coaching programs)
- [ ] Understand who built it and why (beauty industry insider, not a tech company)
- [ ] Understand the setup takes 5 minutes and requires zero technical knowledge

### Module 2: "Setting Up Your Business" (5 min)
**What to record:** Screen recording of install + setup wizard.

Script outline:
- Download Claude Code (show claude.ai/download)
- Open the Beauty Business OS folder
- Type "set me up"
- Walk through each question: name, niche, services, pricing, location, voice, integrations
- Show the confirmation
- "Your entire business system is now configured for you. That took 5 minutes."

**Checklist:**
- [ ] Know how to download and install Claude Code
- [ ] Know how to open the Beauty Business OS project
- [ ] Know what "set me up" does and what questions it asks
- [ ] Understand what niche presets and voice presets are (the AI's industry knowledge + your brand personality)
- [ ] Know what optional integrations are available (GoHighLevel, Metricool, Replicate)

### Module 3: "Your First Day" (5 min)
**What to record:** Screen recording of typical daily commands.

Script outline:
- Morning: "What's on my schedule today?" → morning briefing
- Between clients: "What should I post today?" → content suggestion
- After a service: "Make me a before/after post for the lash set I just did" → content + image
- End of day: "How did I do today?" → daily summary with revenue, clients, follow-ups
- "This is your new daily routine. 5 minutes of conversation replaces 2 hours of admin."

**Checklist:**
- [ ] Know how to get your morning briefing
- [ ] Know how to get content suggestions on demand
- [ ] Know how to create posts, promos, and graphics through conversation
- [ ] Know how to check revenue and daily performance
- [ ] Understand the daily workflow: morning briefing → throughout the day → end of day summary

### Module 4: "Content & Marketing On Autopilot" (5 min)
**What to record:** Screen recording of content creation and auto-posting.

Script outline:
- "Create this week's content" → watch it generate 5-7 posts in your voice
- Show the Titan Genome system: "It doesn't write generic AI content — it writes like a world-class copywriter, in YOUR voice"
- "Make me a promo graphic for my filler special" → image generation
- "Post this to Instagram at 6pm" → auto-scheduling via Metricool
- "Plan my content for next week" → batch content creation
- "This is what a marketing agency charges you $1,500/month for. You just did it in 3 minutes."

**Checklist:**
- [ ] Know how to batch-create a week of content in one conversation
- [ ] Understand how the brand voice system makes content sound like YOU, not like AI
- [ ] Know how to generate promo graphics and images
- [ ] Know how to schedule and auto-post content
- [ ] Understand that content creation works for any niche — lash, skin, hair, nails, body, everything

### Module 5: "Your Dashboard & Next Steps" (3 min)
**What to record:** Screen recording of dashboard + closing.

Script outline:
- Open dashboard/index.html in the browser
- Walk through: appointments, revenue, content, leads, tasks
- "Your AI updates this throughout the day. Refresh to see the latest."
- "You just completed the Beauty Business OS Level 1 Certification."
- "You now know more about running your business with AI than 99% of beauty professionals."
- CTA: "Download your Beauty Business OS below and get started today."
- Mention Boss Edition: "When you're ready for fully automated social media — content created, produced, and posted for you across all platforms — ask about the Boss Edition."

**Checklist:**
- [ ] Know how to open and use the visual dashboard
- [ ] Understand what each dashboard section shows (appointments, revenue, content, leads, tasks)
- [ ] Know the daily workflow for checking your dashboard
- [ ] Know where to get help (docs folder, FAQ, "help me with [whatever]")
- [ ] Know about the Boss Edition upgrade path for automated social media

---

## Post-Completion CTA

After Module 5, show a completion section:

- **H2:** "You're Level 1 Certified."
- **Body:** "You just learned more about running your beauty business with AI than 99% of professionals in the industry. Now download your Beauty Business OS and get started."
- **CTA:** [Download Beauty Business OS] → link to repo download/clone
- **Secondary CTA:** [Watch The Setup Walkthrough Video] → links to the video from `training/VIDEO_OUTLINE.md`
- **Tertiary CTA:** "Ready for the Boss Edition? [Learn about the Boss Blowout]" → link to Beauty Boss OS info

---

## App.js Data Structure

Model on the existing `claude-code-ecosystem-certification/app.js`. Key data:

```javascript
const COURSE = {
  title: "Beauty Business OS Level One Certification",
  heroHeadline: "A practical certification for running your beauty business with AI.",
  heroSubheadline: "Watch the modules, complete the checklists, and download your Beauty Business OS — all free.",
  audience: [
    "Solo estheticians",
    "Lash technicians",
    "Med spa owners",
    "Hair stylists",
    "Brow & lash artists",
    "Nail technicians",
    "Body contouring specialists",
    "Massage therapists"
  ],
  outcomes: [
    "Set up your AI business partner in 5 minutes",
    "Create a week of content in one conversation",
    "Automate follow-ups, reminders, and review requests",
    "Replace your marketing agency with a conversation",
    "Track revenue, appointments, and leads from one dashboard"
  ],
  modules: [ /* 5 modules with video paths, checklists */ ]
};
```

---

## Design System

Same adaptation as the lead magnet (see `sales/lead-magnet-spec.md` design section). Beauty-adapted color palette on the same structural design.

---

## Files to Create (When Building the Repo)

```
beauty-business-os-certification/
├── index.html
├── styles.css
├── app.js
├── .gitignore
├── README.md
├── edited_videos/
│   ├── module-1-what-is-beauty-os.mp4
│   ├── module-2-setting-up.mp4
│   ├── module-3-your-first-day.mp4
│   ├── module-4-content-marketing.mp4
│   └── module-5-dashboard-next-steps.mp4
├── site/
│   └── assets/
│       └── brand/
│           ├── hero-art.png
│           └── social-card.png
├── transcripts/
│   ├── module-1.vtt
│   └── module-1.txt
│   └── ... (one per module)
└── scripts/
    ├── prepare_content.py
    ├── render_brand_assets.py
    └── render_video.py
```

---

## Prerequisites Before Building

1. **Record 5 source videos** — Can be done in one 45-60 minute session, then cut into modules
2. **Design hero art + social card** — Beauty-branded versions
3. **Write final checklist copy** — Outlined above, needs review pass
4. **Decide on download delivery** — Direct GitHub clone link vs. zip download vs. GHL delivery page
