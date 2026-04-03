# GHL Auto-Configuration Spec

This file tells the AI how to automatically configure GoHighLevel during the "set me up" flow. The AI reads this after collecting the user's business info in the Setup Wizard.

---

## Prerequisites

Before running GHL setup:
1. Confirm GHL API key is present in `.mcp/settings.json` → `mcpServers.ghl.env.GHL_API_KEY`
2. If not present, ask the user: "Do you have a GoHighLevel account? If so, I can set up your entire CRM automatically."
3. If they say yes, guide them: "Go to GHL → Settings → Business Profile → API Keys. Copy the key and paste it here."
4. If they say no or want to skip, mark GHL as `not_connected` in CLIENT_CONFIG.md and move on

---

## Step 1: Create Pipeline

Read the current vertical from `setup/vertical-config.json` to get the pipeline stages.

**For Beauty vertical, create this pipeline:**

```
Pipeline Name: "{business_name} Client Pipeline"
Stages:
  1. New Lead
  2. Contacted
  3. Consultation Booked
  4. Showed Up
  5. Service Completed
  6. Follow-Up Sent
  7. Retained Client
  8. Lost
```

**GHL MCP calls:**
- Use `ghl.pipelines.create` or equivalent to build the pipeline
- If a pipeline already exists, ask: "You already have a pipeline set up. Want me to add these stages to it, or create a new one?"

**Confirm to user:** "Your client pipeline is set up with 8 stages — from New Lead all the way to Retained Client. Every new inquiry will flow through this automatically."

---

## Step 2: Deploy Core Workflows

Set up 5 automation workflows. For each, read the detailed spec from `agents/ghl-assistant/workflows/`.

### Workflow 1: Lead Response
- **Trigger:** New contact enters pipeline at "New Lead" stage
- **Action 1:** Immediately send SMS: "Hey {first_name}! Thanks for reaching out to {business_name}. We'd love to get you booked — what service are you interested in?"
- **Action 2:** Wait 5 minutes → Send email with service menu + booking link
- **Move to:** "Contacted" stage

### Workflow 2: No-Show Follow-Up
- **Trigger:** Appointment marked as no-show
- **Action 1:** Wait 1 hour → Send SMS: "Hey {first_name}, we missed you today! No worries — want to reschedule? Just reply with a day that works."
- **Action 2:** Wait 24 hours → Send email with easy rebooking link + "we saved your spot" messaging
- **Tag:** Add "no-show" tag

### Workflow 3: Review Request
- **Trigger:** Contact moves to "Service Completed" stage
- **Action 1:** Wait 24 hours → Send SMS: "Hey {first_name}! So glad you came in. If you loved your experience, a quick Google review would mean the world. [review_link]"
- **Action 2:** Wait 48 hours → If no review → Send follow-up email with review link

### Workflow 4: Abandoned Booking
- **Trigger:** Contact starts booking flow but doesn't complete
- **Action 1:** Wait 1 hour → Send SMS: "Hey {first_name}! Looks like you started booking but didn't finish — no pressure! Your spot is still open if you want to grab it. [booking_link]"
- **Action 2:** Wait 24 hours → Send email with "still thinking about it?" + social proof

### Workflow 5: Nurture Sequence
- **Trigger:** Contact in "Follow-Up Sent" stage with no rebook after 7 days
- **Action 1:** Day 7 → Email with educational content (skin tips, style guide, treatment info based on niche)
- **Action 2:** Day 14 → SMS with limited-time offer ("20% off your next visit this month")
- **Action 3:** Day 21 → Email with before/after client results + testimonial
- **Action 4:** Day 30 → Final SMS: "It's been a month — we miss you! Book this week and get a free add-on."
- **If no response after 30 days:** Move to "Lost" stage, add to 90-day win-back campaign

**GHL MCP calls:**
- Use `ghl.workflows.create` or equivalent for each workflow
- Set triggers, wait steps, SMS/email actions, and stage transitions
- If GHL MCP doesn't support workflow creation directly, create them as documented specs and tell the user: "I've prepared your 5 automations. Let me walk you through activating them in GHL — it takes about 10 minutes."

**Confirm to user:** "Your automations are live. When a new lead comes in, they'll get an instant text. If someone no-shows, they'll get a friendly follow-up. After every service, clients get a review request. And if anyone drifts, a nurture sequence brings them back. All on autopilot."

---

## Step 3: Create Tags

Based on the user's services and lead sources, create these tag categories:

### Service Tags
One tag per service from CLIENT_CONFIG.md. Examples:
- `facial-client`, `lash-client`, `brow-client`, `body-contouring-client`

### Status Tags (Standard)
- `new` — First-time client
- `returning` — Has visited 2+ times
- `vip` — 5+ visits or high spender
- `lapsed` — No visit in 60+ days
- `no-show` — Has missed an appointment
- `referral` — Referred by another client

### Source Tags
Based on their lead sources from setup:
- `source-instagram`, `source-tiktok`, `source-google`, `source-referral`, `source-walkin`, etc.

**GHL MCP calls:**
- Use `ghl.contacts.addTag` structure — tags are created on first use in GHL
- Document the tag taxonomy in CLIENT_CONFIG.md for reference

**Confirm to user:** "I've set up your tagging system. Every client gets automatically tagged by what service they get, how they found you, and their status. This means when you want to send a promo to all your lash clients, or re-engage people who haven't been back in 2 months — one command."

---

## Step 4: Configure Calendar

Set up a booking calendar based on their business:

- **Calendar name:** "{business_name} Bookings"
- **Timezone:** Based on their location
- **Business hours:** Default to Mon-Sat 9:00 AM - 6:00 PM (ask if different)
- **Services:** One service type per service in CLIENT_CONFIG.md, with:
  - Name
  - Duration (ask or use niche preset defaults)
  - Price
  - Buffer time (default 15 min between appointments)
- **Booking page:** Enable if available

**GHL MCP calls:**
- Use calendar creation endpoints
- Add service types with durations

**Confirm to user:** "Your booking calendar is live. Clients can book [top 3 services] online. I've added 15-minute buffers between appointments so you're never rushed."

---

## Step 5: Final GHL Confirmation

Summarize everything that was configured:

"Here's your CRM setup:
- **Pipeline:** {business_name} Client Pipeline — 8 stages from lead to retained
- **Automations:** 5 workflows running on autopilot (lead response, no-show recovery, review requests, abandoned bookings, client nurture)
- **Tags:** {X} service tags + 6 status tags + {Y} source tags
- **Calendar:** Online booking live with {Z} services

Everything is connected and running. When someone DMs you on Instagram asking about pricing, just add them as a lead and the system takes over."

---

## Error Handling

- **GHL API key invalid:** "That API key didn't work. Double-check it in GHL → Settings → Business Profile → API Keys. Copy the whole thing and paste it here."
- **GHL rate limit:** "GHL is processing — give it a sec." Space out calls by 500ms.
- **MCP not available:** Fall back to documenting everything as specs. "I can't connect to GHL directly right now, but I've prepared everything. Want me to walk you through setting it up manually? It's about 10 minutes."
- **Partial setup:** If any step fails, continue with the rest and note what needs manual completion.

---

## Vertical-Specific Overrides

Different verticals may have different pipeline stages and workflow triggers. Always read from `setup/vertical-config.json` for the current vertical's pipeline stages. The workflow templates above are the default — adapt the messaging to match the vertical's terminology and client journey.
