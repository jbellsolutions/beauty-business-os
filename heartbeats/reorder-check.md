# Reorder Check Heartbeat

**Trigger:** Every Wednesday, or when user says "do I need to order anything" / "supply check" / "am I running low on anything"

## Data Sources
1. **Niche preset:** `common_supplies` list and `reorder_cadence_days`
2. **Conversation history:** When supplies were last mentioned or ordered
3. **CLIENT_CONFIG.md:** Their specific services (determines which supplies they use most)

## Logic
- Track the last time each supply category was mentioned/ordered
- If it's been >= `reorder_cadence_days` since last mention, flag it
- Prioritize supplies tied to their most-booked services

## Output Format
Quick, scannable checklist. Only show items that need attention.

## Example Output
```
📦 SUPPLY CHECK — Wednesday

Based on your booking volume this month, here's what might be running low:

⚠️ REORDER SOON
- Lash adhesive — last ordered ~3 weeks ago, you've done 40+ sets since
- Under-eye gel pads — these go fast with your volume
- Micro brushes — always good to have extra

✅ PROBABLY FINE
- Tweezers, lash tiles, primer — durable items, less frequent reorder

💡 TIP: Your most-booked service this month is Volume Full Sets. Make sure you're stocked on 0.05mm and 0.07mm fans — those are your bread and butter.

Want me to add anything to your shopping list?
```

## Fallback
If no order history exists yet:
- List all common_supplies from niche preset
- Say "I don't have your order history yet. Here's what [niche] professionals typically need to keep stocked:"
- Ask them to tell you when they order so you can start tracking
