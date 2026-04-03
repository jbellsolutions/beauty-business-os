# Agents — Beauty Business OS

## Agent Roster

| Agent | Role | Definition File | Trigger |
|-------|------|----------------|---------|
| **COO** | Daily operations, revenue, scheduling, supply management | `agents/coo/SOUL.md` | "What's on my schedule?" / "How much did I make?" / "Do I need to order anything?" |
| **Content Creator** | Social posts, emails, blog posts, video scripts in brand voice | `agents/content/CONTENT_AGENT.md` | "Create content" / "What should I post?" / "Write me a caption" |
| **GHL Assistant** | GoHighLevel CRM management (leads, bookings, campaigns) | `agents/ghl-assistant/GHL_AGENT.md` | "Follow up with leads" / "Book Sarah for Thursday" / "Send reminders" |
| **Image Generator** | AI image generation for promos, graphics, templates | `agents/image-gen/IMAGE_AGENT.md` | "Make me a promo graphic" / "Create a before/after template" |

## Orchestration

There is no explicit router. Claude (via CLAUDE.md) acts as the orchestrator, reading the user's intent and invoking the appropriate agent's instruction set. For ambiguous requests, Claude uses the COO agent as the default.

## Agent Pipeline — Content Creator

The Content Creator uses a 3-stage pipeline:

```
Stage 1: Creator — Generates raw content using Titan Genome copywriting framework
    ↓
Stage 2: Critic — Reviews for brand voice compliance, hook strength, CTA clarity
    ↓
Stage 3: Approver — Final quality gate, ensures niche-specific accuracy
```

The Titan Genome framework draws from legendary copywriters (Hormozi, Kennedy, Schwartz, Ogilvy, etc.) to generate high-converting content adapted to the beauty professional's voice preset.

## Agent Data Dependencies

```
All agents read:
  ├── CLIENT_CONFIG.md (business profile, services, pricing)
  ├── config/niche-presets/{niche}.json (industry knowledge)
  └── config/voice-presets/{voice}.json (brand personality)

COO also reads:
  └── heartbeats/*.md (scheduled check-in templates)

Content Creator also reads:
  └── agents/content/titan-genome/ (copywriting framework)

GHL Assistant also reads:
  ├── agents/ghl-assistant/workflows/ (automation templates)
  └── .mcp/settings.json (MCP server config)

Image Generator also reads:
  └── agents/image-gen/templates/ (graphic templates)
```

## Handoff Protocols

- **COO → Content Creator:** When COO identifies a content gap (e.g., "your books are light next week"), it suggests content creation, which triggers the Content Creator.
- **COO → GHL Assistant:** When COO identifies leads to follow up or appointments to manage, it delegates to the GHL Assistant.
- **Content Creator → Image Generator:** When content requires a graphic (promo post, before/after, story), the Content Creator hands off to Image Generator.
- **Any Agent → User:** All agents present their output to the user for review before taking external actions (posting, sending emails, booking).

## Adding New Agents

1. Create a new directory under `agents/`
2. Write an `AGENT.md` (or `SOUL.md`) defining the agent's identity, capabilities, and constraints
3. Add any rules, templates, or workflows as subdirectories
4. Update this file (AGENTS.md) with the new agent's entry
5. Add trigger phrases to CLAUDE.md so the orchestrator knows when to invoke it
