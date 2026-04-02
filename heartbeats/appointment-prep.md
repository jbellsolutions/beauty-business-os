# Appointment Prep Heartbeat

**Trigger:** 1 hour before each scheduled appointment, or when user says "prep me for my [time] appointment" / "who's coming in next"

## Data Sources
1. **GHL (if connected):** Client name, service booked, contact history, last visit, previous services, notes, tags
2. **CLIENT_CONFIG.md:** Service menu for upsell suggestions
3. **Niche preset:** Common upsell patterns for this service type

## Output Format
Quick prep card. No more than 6-8 lines. Everything they need at a glance.

1. **Client name + service** — What they're coming in for
2. **Client history** — Last visit, what they got, any notes
3. **Prep notes** — Anything to prepare (allergies, preferences)
4. **Upsell suggestion** — One complementary service or add-on from their menu
5. **Conversation starter** — Something personal if available (mentioned a trip, birthday coming up)

## Fallback (GHL Not Connected / New Client)
- Show service name and default prep for that service type
- Generic upsell based on niche preset common_services
- Suggest asking: "Is this your first time getting [service]?"

## Example Output
```
⏰ INCOMING — 1:00 PM

👤 Jessica R. — Lash Fill (2-week)
📅 Last visit: March 18 (Classic Full Set — $200)
📝 Notes: Prefers natural look, sensitive eyes — use sensitive adhesive
💡 Upsell: Lash serum ($25) — "Your lashes look great! A growth serum between fills keeps them even fuller"
💬 She mentioned her daughter's wedding is in May — ask how planning is going!
```
