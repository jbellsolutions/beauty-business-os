# Morning Briefing Heartbeat

**Trigger:** Daily at 8 AM local time, or when user says "what's on my plate today" / "morning briefing" / "what's happening today"

## Data Sources
1. **GHL (if connected):** Today's appointments, yesterday's revenue, new leads overnight, pending tasks
2. **Content schedule:** What's queued to post today (from Metricool if connected, or from outputs/social/)
3. **CLIENT_CONFIG.md:** Business name, services, pricing for context
4. **Niche preset:** Content suggestions, seasonal promos, ideal posting times
5. **Dashboard data:** Last known revenue figures, lead counts

## Output Format
Friendly, concise summary. Use the voice preset tone. Max 1 screen of text. Sections:

1. **Greeting** — "Good morning, [Business Name]!" (warm, match voice preset)
2. **Appointments** — List with time, client name, service, price. Or "No appointments today — let's use this time for [suggestion]"
3. **Revenue snapshot** — Yesterday's total. Brief comparison to typical day
4. **Top 3 priorities** — Most important tasks for today. Revenue-generating first
5. **Content suggestion** — 1 specific post idea with hook, based on niche content_themes
6. **Alerts** — Only if something needs attention (low supplies, missed follow-up, upcoming seasonal promo)

## Fallback (GHL Not Connected)
If GHL is not connected:
- Skip appointments section (say "Connect GHL to see your appointments here")
- Skip revenue (say "Tell me about yesterday's revenue and I'll start tracking")
- Focus on content suggestion and general business coaching
- Offer to help set up GHL

## Example Output
```
Good morning, Glow Studio! ✨

📅 TODAY
- 10:00 AM — Sarah M. — Volume Full Set ($250)
- 1:00 PM — Jessica R. — Lash Fill ($85)
- 3:30 PM — Amanda K. — Lash Lift & Tint ($95)

💰 YESTERDAY: $430 (2 services) — solid Tuesday!

📋 YOUR TOP 3 TODAY
1. Sarah is a new client — make it amazing, ask for a review after
2. Post that before/after you filmed Sunday (best time: 6 PM)
3. DM back the 2 inquiries from yesterday

📱 CONTENT IDEA
"POV: getting a lash lift for the first time" — film a quick timelapse of today's 3:30 appointment (with client permission). These do great on TikTok right now.

Ready to crush it today! 💪
```
