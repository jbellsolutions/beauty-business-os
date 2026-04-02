# Troubleshooting Guide

Common issues and how to fix them.

---

## Claude Doesn't Know My Business Info

**Symptom:** Claude gives generic responses, doesn't mention your business name, uses wrong services or pricing.

**Fix:**
1. Open `CLIENT_CONFIG.md` in your project root
2. Make sure all fields are filled out (business name, services, niche, voice, etc.)
3. Start a new Claude Code conversation (the config is loaded at the start of each session)

**Still not working?**
- Check that CLIENT_CONFIG.md is in the project root (not inside a subfolder)
- Make sure CLAUDE.md references CLIENT_CONFIG.md correctly
- Say "read my CLIENT_CONFIG.md and tell me what you see" to verify Claude can access it

---

## Content Doesn't Match My Voice

**Symptom:** Generated content sounds too formal, too casual, too generic, or not like your brand.

**Fix:**
1. Check the `voice` field in CLIENT_CONFIG.md — make sure it points to a valid voice preset
2. Look at your voice preset file in `presets/voices/` — does it describe your tone accurately?
3. Try regenerating with more specific guidance: "Rewrite this but more warm and conversational"

**Fine-tuning your voice:**
- Say "My brand voice is [describe it]. Update my voice preset."
- Provide examples: "Here's a caption I wrote that sounds like me: [example]. Write more like this."
- Iterate: "More casual" / "Less salesy" / "Shorter sentences" / "Add more personality"

---

## GHL Commands Don't Work

**Symptom:** Claude says it can't connect to GHL, API calls fail, or nothing happens.

**Fix:**
1. Check that `ghl_api_key` is set in CLIENT_CONFIG.md
2. Verify the API key is correct (no extra spaces, complete key)
3. Confirm your GHL account is active and the API key has the right permissions
4. Check that the GHL MCP server is connected (if using MCP integration)

**Testing:**
- Say "test my GHL connection" to see if Claude can reach your account
- Try a simple read operation first: "show me my GHL contacts"
- Check GHL's API status page if all else fails

---

## Dashboard Won't Open

**Symptom:** Saying "show me my dashboard" doesn't open anything, or the page is blank.

**Fix:**
1. Open `dashboard/index.html` directly in your browser (File > Open or drag the file into a browser window)
2. Make sure the file exists — run `ls dashboard/` to check
3. If the file is missing, say "generate my dashboard" to create it

**Common causes:**
- The dashboard file hasn't been generated yet (run setup or ask Claude to create it)
- Your browser is blocking local file access (try a different browser)
- The file path has spaces — try copying the full path and pasting it into your browser

---

## Image Generation Fails

**Symptom:** Claude can't generate images, or you get API errors when requesting images.

**Fix:**
1. Check that `REPLICATE_API_TOKEN` is set in CLIENT_CONFIG.md
2. Verify your Replicate account is active and has credits
3. Get your token at: https://replicate.com/account/api-tokens

**Note:** Image generation is optional. You can use Beauty Business OS fully without it. Stock photos or your own photos work great for social content.

---

## Heartbeats Not Triggering

**Symptom:** Scheduled automations (morning briefings, content reminders) don't run automatically.

**Fix:**
Heartbeats require a cron job or scheduled task to trigger them. They don't run on their own.

**Manual trigger:**
- Just say "good morning" or "run my morning briefing" to trigger manually

**Automated setup (optional):**
You'd need to set up a cron job on your machine to run Claude Code commands at scheduled times. This is an advanced feature and isn't required for normal use.

---

## Wrong Niche Info Showing Up

**Symptom:** Claude references services, terminology, or content from a different niche than yours.

**Fix:**
1. Open CLIENT_CONFIG.md
2. Check the `niche` field — it should match a filename in `presets/niches/` (without the extension)
3. Example: if your niche file is `presets/niches/lash-extensions.md`, your niche field should be `lash-extensions`

**Verify:**
- Say "what niche am I configured for?" to see what Claude thinks
- Say "list available niches" to see what's in your presets folder
- If your niche doesn't have a preset, say "create a niche preset for [your niche]"

---

## Content Is Repetitive

**Symptom:** Claude generates similar posts, uses the same hooks or phrases repeatedly.

**Fix:**
- Be more specific in your requests: "Write a post about lash aftercare, specifically about sleeping positions"
- Ask for variety: "Give me 5 different hooks for this topic"
- Reference the content type: "Write this as a storytime post, not educational"
- Provide constraints: "Don't use any questions as hooks this time"
- Share what you've already posted: "I just posted about [X], give me something different"

---

## Emails/Sequences Aren't Sending

**Symptom:** You've set up email templates but clients aren't receiving them.

**Fix:**
Beauty Business OS generates email *templates and copy*. The actual sending is handled by your email platform (GHL, Mailchimp, etc.).

1. Copy the generated email content into your email platform
2. Set up the workflow/automation triggers in your platform
3. Make sure your sending domain is verified and not in spam

**For GHL users:**
- Create a workflow in GHL for each email in your sequence
- Set the trigger (booking, time delay, etc.)
- Paste the Claude-generated content into the GHL email builder
- Activate the workflow

---

## How to Reset Everything

If you want to start fresh:

1. Open CLIENT_CONFIG.md
2. Clear all the field values (keep the field names/template structure)
3. Start a new Claude Code conversation
4. Say "set me up" to run through the setup flow again

**Keep your templates:** Your files in `templates/`, `funnels/`, and `presets/` won't be affected by resetting CLIENT_CONFIG.md.

---

## How to Update

If you installed from GitHub:

```
cd ~/Desktop/beauty-business-os
git pull origin main
```

This pulls the latest templates, presets, and features without overwriting your personal CLIENT_CONFIG.md (as long as you haven't modified tracked files).

If you downloaded as a ZIP: download the latest version and copy new files into your existing folder. Don't overwrite your CLIENT_CONFIG.md.

---

## Still Stuck?

Try these steps:

1. **Describe the problem to Claude.** Say "I'm having an issue with [X]. Can you help me diagnose it?" Claude can often identify and fix problems.

2. **Check your CLIENT_CONFIG.md.** 90% of issues come from missing or incorrect configuration.

3. **Start a new conversation.** Sometimes a fresh session resolves odd behavior.

4. **Check the docs.** Review `docs/FAQ.md` for answers to common questions.

5. **Check for updates.** A newer version may have fixed your issue.
