# Lead Magnet Spec — "Beauty Business OS In 15 Minutes"

**Future repo:** `jbellsolutions/beauty-business-os-lead-magnet`
**Hosted at:** `jbellsolutions.github.io/beauty-business-os-lead-magnet/`
**Modeled on:** `claude-in-15-minutes-lead-magnet/` (same structure, beauty-adapted)

---

## What This Is

A static GitHub Pages landing page with a 15-minute highlight video showing Beauty Business OS in action. Companion PDF download. CTA to the full Level 1 certification.

This is the top of the funnel — the first thing a beauty professional sees after clicking through from a cold email, podcast CTA, or social media link.

---

## Page Structure

### 1. Topbar Navigation
```
[brand mark] Free Course — Beauty Business OS In 15 Minutes
                                          [Watch] [Checklist] [Download PDF]
```

### 2. Hero Section
- **Eyebrow:** "Free Course For Beauty Professionals"
- **H1:** "Beauty Business OS In 15 Minutes"
- **Headline:** "See how to set up an AI business partner that handles your content, marketing, follow-ups, and reporting — in one fast walkthrough."
- **Subheadline:** "No tech skills required. No apps to learn. You just talk to it and it runs your business."
- **Lead:** "This course condenses a full walkthrough into a tighter highlight edit so you can quickly see how Beauty Business OS works in practice."
- **CTAs:** [Watch The Video] [Download The PDF]
- **Stat chips:** "~15 minute walkthrough" | "Includes companion PDF" | "Built for beauty professionals"
- **Hero art:** Branded artwork (Beauty OS dashboard screenshot or styled graphic)

### 3. Video Section
- **Kicker:** "Free Course Video"
- **H2:** "Watch your AI business partner set up and run a real beauty business."
- **Body:** "The full video is below — setup wizard, first commands, content creation, and the dashboard in action."
- **Video player:** HTML5 `<video>` with poster frame and captions
- **Downloads:** [Download Companion PDF] [Download Transcript]

### 4. Three-Card Grid (What You'll See)
```
┌─────────────────────┐  ┌─────────────────────┐  ┌─────────────────────┐
│ Set Up Your Business │  │ Create Content In    │  │ Automate Everything │
│                      │  │ Your Voice           │  │                     │
│ Watch the AI ask     │  │ See it generate      │  │ Follow-ups, posting,│
│ 10-15 questions and  │  │ social posts, promos,│  │ scheduling, revenue │
│ configure everything │  │ emails — all in your │  │ tracking — running  │
│ for your specific    │  │ brand personality    │  │ on autopilot while  │
│ business in 5 min.   │  │ and for your         │  │ you focus on        │
│                      │  │ specific services.   │  │ clients.            │
└─────────────────────┘  └─────────────────────┘  └─────────────────────┘
```

### 5. Checklist Section
- **Kicker:** "What You'll Learn"
- **H2:** "What this walkthrough covers."

Checklist items:
1. How to install and open Beauty Business OS in under 2 minutes
2. How the setup wizard configures everything for your specific business, services, and brand voice
3. How to ask your AI partner for a morning briefing, schedule check, or revenue summary
4. How content gets created in your voice — not generic AI content, YOUR personality
5. How the image generator creates promo graphics, before/after templates, and story content
6. How auto-posting schedules and publishes your content without you touching it
7. How the dashboard gives you a visual overview of your entire business at a glance
8. How follow-ups, appointment reminders, and review requests happen automatically
9. Why this replaces marketing agencies, coaching programs, and DIY social media management
10. How to get started right now — for free

### 6. PDF Download Section
- **Kicker:** "Companion Download"
- **H2:** "Get the PDF that goes with the video."
- **Body:** "Download the short companion guide for the main ideas, the setup checklist, and the first 10 commands to try."
- **CTA:** [Download PDF]

### 7. Footer CTA
- **Kicker:** "Next Step"
- **H2:** "Get your full Level 1 certification here for free."
- **Body:** "If you want the full walkthrough, all the video modules, and the deeper certification path, go here next."
- **CTA:** [Take The Full Level One Certification Here For Free] → links to certification portal

---

## Video Content (What to Record)

The video is a 15-minute highlight edit. Source material comes from a longer screen recording (same approach as the Claude In 15 Minutes lead magnet).

**Recording script:**

1. **Intro (0:00-0:30):** "Hey — I'm going to show you how to set up an AI business partner for your beauty business in about 15 minutes. No tech skills. No coding. You just talk to it."

2. **Install & Open (0:30-2:00):** Download Claude Code → open the project → "this is where you talk to your business"

3. **Setup Wizard (2:00-6:00):** Type "set me up" → walk through questions (use lash tech as demo niche, fun & girly voice preset) → show the confirmation

4. **First Commands (6:00-10:00):** "What's on my schedule today?" → "Create this week's content" → "Make me a promo for my lash special" → "How much did I make this week?"

5. **Dashboard (10:00-12:00):** Open dashboard in browser → walk through sections → "your AI updates this throughout the day"

6. **Daily Workflow (12:00-14:00):** Morning briefing → between-client posting → end-of-day summary → Sunday batch content

7. **Outro (14:00-15:00):** "That's it. 5-minute setup, then you just talk to it. Click below for the full Level 1 certification — it's free — and you'll have everything you need to run your beauty business with AI."

---

## Companion PDF Contents

One-page (front and back) or 2-3 page companion guide:

**Page 1: What Is Beauty Business OS**
- One-paragraph overview
- Who it's for (bullet list)
- What it replaces (visual comparison)

**Page 2: The Setup Checklist**
- Install Claude Code (link)
- Open the project folder
- Say "set me up"
- Answer 10-15 questions
- You're live

**Page 3: Your First 10 Commands**
1. "What's on my schedule today?"
2. "Create this week's content"
3. "Make me a promo for [your top service]"
4. "How much did I make this week?"
5. "What should I post today?"
6. "Follow up with yesterday's leads"
7. "Post this to Instagram at 6pm"
8. "Remind tomorrow's clients about their appointments"
9. "Plan my content for next week"
10. "Do I need to order anything?"

---

## Design System

Adapt the existing `claude-in-15-minutes-lead-magnet` design system with beauty-specific colors:

| Token | Claude Lead Magnet | Beauty OS Version |
|-------|-------------------|-------------------|
| `--bg` | `#0e2430` (dark teal) | `#1a0a1e` (dark plum) |
| `--bg-deep` | `#081721` | `#0f0612` |
| `--surface` | `rgba(248, 239, 225, 0.84)` | `rgba(255, 245, 248, 0.84)` (warm pink-white) |
| `--surface-strong` | `#fff8ef` | `#fff5f8` |
| `--ink` | `#153540` | `#2a1530` |
| `--muted` | `#54676c` | `#6c5470` |
| `--accent` | `#ea7f3a` (orange) | `#c9a0dc` (soft purple) or `#f7c6d0` (pink) |

Keep the same typography (Avenir Next / serif for headlines), same layout grid, same component structure. Just swap the palette.

---

## Files to Create (When Building the Repo)

```
beauty-business-os-lead-magnet/
├── index.html                    # Landing page
├── styles.css                    # Stylesheet (adapted palette)
├── .gitignore
├── README.md
├── edited_video/
│   └── beauty-os-in-15-minutes.mp4
├── deliverables/
│   └── beauty-os-companion-guide.pdf
├── transcripts/
│   ├── beauty-os-in-15-minutes.vtt
│   └── beauty-os-in-15-minutes.txt
├── site/
│   └── assets/
│       ├── hero-art.png
│       ├── social-card.png
│       ├── poster.jpg
│       ├── intro-slate.png
│       └── outro-slate.png
└── scripts/
    ├── prepare_content.py
    ├── render_brand_assets.py
    ├── render_video.py
    └── render_pdf.py
```

---

## Prerequisites Before Building

1. **Record the source video** — Screen recording of Justin walking through Beauty Business OS setup and first commands (30-45 min raw, will be cut to 15 min)
2. **Design hero art** — Branded artwork for the landing page hero
3. **Design social card** — OG image for link sharing
4. **Write companion PDF content** — Outlined above, needs final copy
