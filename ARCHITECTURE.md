# Architecture — Beauty Business OS

## Overview

Beauty Business OS is a Claude Code project — a collection of markdown instructions, configuration presets, templates, and an HTML dashboard that together create an AI-powered business operating system for beauty professionals. There is no backend server. The AI (Claude) reads the instruction files and acts on them conversationally.

## Directory Layout

```
beauty-business-os/
├── CLAUDE.md                    # Master AI instructions — the brain
├── CLIENT_CONFIG.md             # Per-user business profile (populated during setup)
├── POSITIONING.md               # Founder story, sales copy, messaging
├── ETHOS.md                     # Project values and quality bar
├── README.md                    # Quick-start guide
│
├── agents/                      # Specialized AI agent definitions
│   ├── coo/                     # Chief Operating Officer agent
│   │   ├── SOUL.md              # Identity and operating principles
│   │   └── rules/RULES.md       # Decision rules and constraints
│   ├── content/                 # Content creation agent
│   │   ├── CONTENT_AGENT.md     # 3-stage pipeline: Creator→Critic→Approver
│   │   └── titan-genome/        # Copywriting framework (swipe files, style analysis)
│   ├── ghl-assistant/           # GoHighLevel CRM management agent
│   │   ├── GHL_AGENT.md         # CRM operations definition
│   │   └── workflows/           # Automation templates (lead response, no-show, etc.)
│   └── image-gen/               # Image generation agent
│       ├── IMAGE_AGENT.md       # Replicate/Flux integration
│       └── templates/           # Promo, before-after, story, special-offer templates
│
├── config/                      # Configuration presets
│   ├── niche-presets/           # 11 beauty niches (esthetician, lash, med-spa, etc.)
│   └── voice-presets/           # 5 brand voice options (fun-girly, professional, etc.)
│
├── dashboard/                   # Visual dashboard
│   └── index.html               # Single-file HTML dashboard (inline CSS/JS, localStorage)
│
├── docs/                        # User-facing documentation
│   ├── GETTING-STARTED.md
│   ├── FAQ.md
│   └── TROUBLESHOOTING.md
│
├── funnels/                     # Client-facing sales funnels
│   ├── booking/                 # Appointment booking funnel + email sequences
│   ├── lead-capture/            # Lead capture funnel + nurture sequences
│   └── referral/                # Referral program funnel
│
├── heartbeats/                  # Scheduled AI check-in templates
│   ├── morning-briefing.md
│   ├── appointment-prep.md
│   ├── end-of-day-wrap.md
│   ├── weekly-review.md
│   └── reorder-check.md
│
├── playbooks/                   # Strategy playbooks
│   ├── organic-marketing/       # Organic social media strategy
│   ├── posting/                 # Auto-posting workflows (Metricool, ManyChat)
│   └── client-ops/              # Client operations (booking, retention, reviews)
│
├── sales/                       # Product distribution funnel (selling the OS itself)
│   ├── FUNNEL.md                # Full funnel spec
│   ├── lead-magnet-spec.md      # Landing page spec
│   ├── certification-spec.md    # Certification portal spec
│   └── email-sequence.md        # Post-download nurture sequence
│
├── templates/                   # Content and business templates
│   ├── social-post.md, email-newsletter.md, blog-post.md, video-script.md
│   ├── pricing-menu.md, promo-calendar.md, client-intake.md, story-ideas.md
│   └── business/, content/      # Subcategories
│
├── training/                    # Onboarding
│   └── VIDEO_OUTLINE.md         # 15-min walkthrough video script
│
├── outputs/                     # Generated content (gitignored at runtime)
└── .mcp/                        # MCP server configuration
    └── settings.json
```

## Data Flow

```
User speaks → Claude reads CLAUDE.md → Claude reads CLIENT_CONFIG.md
    → Claude selects relevant agent (COO, Content, GHL, Image)
    → Agent reads its SOUL/AGENT.md + rules + templates
    → Agent reads niche preset + voice preset from config/
    → Agent generates response/content/action
    → Output displayed to user (and optionally saved to outputs/)
    → Dashboard updated via localStorage when user opens it
```

## Key Abstractions

### 1. Setup Wizard (CLAUDE.md Step 2)
Conversational onboarding that populates CLIENT_CONFIG.md. Asks 10-15 questions one at a time. Selects niche preset, voice preset, and configures integrations.

### 2. Niche Presets (config/niche-presets/)
JSON files containing industry-specific knowledge: services, pricing ranges, upsell paths, seasonal trends, client psychology, content themes, and compliance notes. Each preset teaches the AI about a specific beauty modality.

### 3. Voice Presets (config/voice-presets/)
JSON files defining brand personality: tone, vocabulary, emoji usage, sentence structure, avoided terms, and example phrases. Applied to all generated content.

### 4. Agent Pipeline (agents/)
Four specialized agents, each with a markdown definition file:
- **COO** — Daily operations, revenue tracking, scheduling, supply management
- **Content** — 3-stage content pipeline using Titan Genome copywriting framework
- **GHL** — GoHighLevel CRM operations via MCP server
- **Image** — AI image generation via Replicate/Flux

### 5. Heartbeats (heartbeats/)
Scheduled check-in templates that the AI uses for proactive daily/weekly operations (morning briefing, appointment prep, end-of-day summary, weekly review, reorder alerts).

### 6. Dashboard (dashboard/index.html)
Single-file HTML with inline CSS and JavaScript. Uses localStorage under `beauty-os-state` key for persistence. Dark theme design system. Sections: appointments, revenue, content, leads, tasks.

## Integration Points

| Integration | Method | Config Location |
|------------|--------|----------------|
| GoHighLevel | MCP server (269+ tools) | .mcp/settings.json |
| Metricool | API via agent instructions | CLIENT_CONFIG.md |
| Replicate | API via image-gen agent | CLIENT_CONFIG.md |
| Google Calendar | MCP server | .mcp/settings.json |
| ManyChat | Webhook via playbook | playbooks/posting/ |
