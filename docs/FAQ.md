# Frequently Asked Questions

---

### What is Beauty Business OS?

Beauty Business OS is an AI-powered business operating system built on Claude Code, designed specifically for beauty professionals. It acts as your personal business assistant — writing content in your brand voice, managing marketing campaigns, planning promotions, drafting emails, and helping you run your business through simple conversation. Instead of learning complicated software, you just talk to it.

---

### How much does it cost to run?

The core cost is your Claude Code subscription (check current pricing at claude.ai). Beyond that, optional integrations have their own costs:
- **GoHighLevel (GHL):** Separate subscription for CRM/booking/automation
- **Replicate:** Pay-per-image for AI image generation (typically pennies per image)
- **Metricool:** Free tier available, paid plans for more features
- **ManyChat:** Free tier available for basic DM automation

The Beauty Business OS repo itself is free.

---

### Do I need to know how to code?

No. Not even a little. Beauty Business OS is designed to be used entirely through conversation. You talk to it like you'd talk to a smart assistant, and it handles the technical parts. If you can describe what you need in plain English, you can use this tool.

---

### Can I change my niche or voice later?

Yes, anytime. You have two options:

**Option 1:** Edit CLIENT_CONFIG.md directly — change the `niche` or `voice` field to a different preset.

**Option 2:** Just say it:
- "Change my niche to esthetician"
- "Make my voice more casual and fun"
- "I want to sound more luxury and high-end"

Claude will update your configuration accordingly.

---

### What's the dashboard?

The dashboard is a visual HTML page (located at `dashboard/index.html`) that gives you a snapshot of your business at a glance. Open it in any web browser. It can show content calendars, metrics, upcoming tasks, and business health indicators. Say "show me my dashboard" or open the file directly.

---

### How does content generation work?

When you ask Claude to write content (social posts, emails, blog posts, video scripts, etc.), it:

1. Reads your CLIENT_CONFIG.md for your business details
2. Loads your active niche preset for industry-specific knowledge
3. Applies your voice preset for brand-consistent tone and language
4. Uses the relevant template from the `templates/` folder for structure
5. Generates content that sounds like you wrote it

You can ask for multiple options, request revisions, and iterate until it's perfect.

---

### Is my data private?

Yes. Everything runs locally on your computer. Your business information, client details, generated content, and configurations all stay in your project folder. Nothing is uploaded to external servers beyond the standard Claude Code API calls (which process your requests). Your data is not used to train AI models.

---

### How do I connect GoHighLevel (GHL)?

1. Log into your GHL account
2. Go to Settings > API Keys
3. Generate a new API key
4. Open CLIENT_CONFIG.md in your Beauty Business OS folder
5. Paste the API key in the `ghl_api_key` field
6. Say "test my GHL connection" to verify it works

Once connected, Claude can create contacts, manage pipelines, trigger workflows, and interact with your GHL account.

---

### What if something breaks?

See `docs/TROUBLESHOOTING.md` for common issues and fixes. The most common problems and quick fixes:

- **Content doesn't match my voice:** Check that your voice preset is set correctly in CLIENT_CONFIG.md
- **GHL commands fail:** Verify your API key is correct and your GHL account is active
- **Claude doesn't know my info:** Make sure CLIENT_CONFIG.md is filled out completely
- **Dashboard won't load:** Open `dashboard/index.html` directly in your browser

If you're stuck, describe the problem to Claude — it can often diagnose and fix issues for you.

---

### Can I use this for multiple businesses?

Yes. Create a separate folder for each business, each with its own CLIENT_CONFIG.md, niche preset, and voice preset. You can run Claude Code in whichever folder corresponds to the business you're working on.

```
~/Desktop/beauty-business-os-lashes/    (your lash business)
~/Desktop/beauty-business-os-spa/       (your spa business)
```

Each one operates independently with its own configuration.

---

### How often should I use it?

Use it as much or as little as you want. Some beauty pros use it daily for content creation and morning briefings. Others use it weekly for batch content planning. Common usage patterns:

- **Daily:** "Good morning" briefing, story ideas, quick posts
- **Weekly:** Batch create social content, plan the week ahead
- **Monthly:** Newsletter, promo planning, business review
- **As needed:** Client communications, new service launches, seasonal campaigns

---

### Can it post directly to social media?

Not by itself, but with integrations it can get close:
- **Metricool integration:** Schedule posts for publishing
- **Copy/paste:** Claude generates the content, you paste it into your platform
- **ManyChat:** Automate Instagram DM responses

Most beauty pros prefer to review content before posting, so the generate-then-post workflow keeps you in control.

---

### What if I want a feature that doesn't exist yet?

Just ask! Describe what you want and Claude will often find a way to make it work with the existing tools. If it's something that requires new files or templates, Claude can create them. The system is designed to grow with your business.

---

### How do I update Beauty Business OS?

If you cloned the repo from GitHub:
```
cd ~/Desktop/beauty-business-os
git pull
```

Your CLIENT_CONFIG.md and any personal customizations won't be overwritten. New templates, presets, and features will be pulled in.

If you downloaded it as a ZIP, download the latest version and merge any new files into your existing folder (keep your CLIENT_CONFIG.md).
