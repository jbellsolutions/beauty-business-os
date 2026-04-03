# Dashboard Customization Flow

This file defines how the AI presents the dashboard customization options after setup, and how to walk users through DIY customization.

---

## When to Present

After the GHL setup (or skip) is complete and the dashboard has been opened locally, present the customization options.

---

## The Offer Script

Say this (adapt to their voice/vibe — if they picked "fun and girly" voice, match that energy):

---

"Your dashboard is ready to go — it works great as-is. But if you want it fully branded with your colors, your name front and center, and hosted on your own website, you've got two options:

**Option 1: I'll walk you through it right now** — We'll customize the colors, add your branding, and you'll have a personalized dashboard in about 15 minutes. Totally free.

**Option 2: We build it for you** — Our team creates a fully custom-branded dashboard and deploys it to your own URL. You just tell us your colors and we handle the rest.

👉 Book your custom dashboard setup: [BOOKING_LINK]

Or just say 'skip' and use the default — you can always customize later."

---

## BOOKING_LINK Configuration

The booking link is set here. Update this when the booking page is live:

```
BOOKING_LINK: https://calendly.com/jbellsolutions/dashboard-setup
```

If the booking link is not yet configured, say: "Want us to build it for you? Just reach out to Justin at jbellsolutions — he'll get you set up."

---

## Option 1: DIY Walkthrough

If the user chooses to customize themselves, walk them through these steps conversationally. Never dump all steps at once — go one at a time.

### Step 1: Business Name & Tagline

"First, let's put your name on it. What do you want the dashboard to say at the top? Your business name is [name from config] — want to use that, or something different?"

**What to change in `dashboard/index.html`:**
- The sidebar brand text (`.sidebar-brand` content)
- The page title (`<title>` tag)
- The wizard welcome text

### Step 2: Colors

"Now let's pick your colors. The dashboard uses a gradient — right now it's purple, pink, and gold. Want to keep that vibe, or do you have brand colors? Just tell me your colors and I'll update everything."

**What to change:**
- CSS custom properties in `:root` — `--purple`, `--pink`, `--gold`, `--green`, `--blue`
- Gradient definitions throughout
- The wizard button gradient
- Stat card accent colors

**Common beauty brand palettes:**
- Soft glam: `#c9a0dc` (lavender), `#f7c6d0` (blush), `#fdd6a0` (champagne)
- Clean clinical: `#4A90D9` (blue), `#5BC0BE` (teal), `#E8E8E8` (silver)
- Bold lux: `#D4AF37` (gold), `#1a1a1a` (black), `#f5f5f5` (white)
- Earthy wellness: `#8B9E6B` (sage), `#D4A574` (warm tan), `#E8DCC8` (cream)

### Step 3: Font (Optional)

"Happy with the font? It's using Inter right now — clean and modern. Or we can switch to something else. Most beauty brands love: Playfair Display (elegant), Poppins (friendly), or Cormorant Garamond (luxury)."

**What to change:**
- Google Fonts import URL
- `font-family` in body and heading styles

### Step 4: Quick Preview

"Take a look — refresh the page in your browser. How's that looking?"

- If they like it: "Perfect. Your dashboard is branded and ready."
- If they want tweaks: Make the specific adjustments they request.

### Step 5: Deploy (Optional)

"Want this on a live URL so you can access it from your phone? I can deploy it to Vercel for free — you'd get a link like `yourbusiness.vercel.app`. Or if you have your own domain, we can connect that too."

**If yes:**
- Deploy via `npx vercel deploy --yes --prod`
- Return the live URL
- Note: this requires Node.js and Vercel CLI. If not available, provide the manual steps or suggest the custom build option.

**If no:**
- "No problem. Just open `dashboard/index.html` anytime you want to see it. Bookmark it in your browser for quick access."

---

## Option 2: Custom Build

If the user chooses the custom option:

1. Provide the booking link: "[BOOKING_LINK]"
2. Or if no link configured: "Reach out to Justin at jbellsolutions and he'll build you a fully custom dashboard with your branding, deployed to your own URL."
3. Note what they want customized (so Justin has context when they book):
   - Brand colors
   - Logo (if they have one)
   - Any specific features or metrics they want on the dashboard
   - Whether they want it on their own domain

---

## Skip Flow

If the user says skip or wants to move on:

"Totally fine — your dashboard works great as-is. You can always come back to this later. Just say 'customize my dashboard' anytime."

---

## Returning Users

If a user later says "customize my dashboard" or "brand my dashboard" or "change dashboard colors":
- Read this file
- Start at Step 1 of the DIY walkthrough
- Skip any steps they've already completed (check if colors/name have been changed from defaults)
