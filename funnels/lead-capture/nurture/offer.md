# Offer Email (Day 10)

> Sent 10 days after opt-in (3 days after Value #2). The conversion email. Presents the first-time client offer clearly with gentle urgency.

---

## Email

**Subject:** This is for you, {{first_name}}

**Preview text:** A special offer I put together just for you

---

**Body:**

```
Hi {{first_name}},

Over the past week, I've shared some of my best tips and insider knowledge about {{niche_area}} — and I hope you've found it helpful!

But here's the thing: reading tips is great, having a professional take care of you is even better.

So I want to make it really easy for you to experience it firsthand.

━━━━━━━━━━━━━━━━━━━━━━━━━

YOUR EXCLUSIVE FIRST-TIME OFFER

✨ {{offer_description}} ✨

{{offer_details}}

This offer is just for my email community, and it expires in 7 days ({{offer_expiry_date}}).

👉 [Book Now and Claim Your Offer]({{booking_link_with_offer}})

━━━━━━━━━━━━━━━━━━━━━━━━━

WHY MY CLIENTS LOVE COMING TO {{business_name}}:

✅ {{selling_point_1}} (e.g., "Personalized service tailored to your unique needs")
✅ {{selling_point_2}} (e.g., "A clean, relaxing space where you can truly unwind")
✅ {{selling_point_3}} (e.g., "{{review_count}}+ five-star reviews from happy clients")
✅ {{selling_point_4}} (e.g., "Flexible scheduling including evenings and weekends")

I would genuinely love to meet you and help you {{desired_outcome}}. This offer is my way of saying — let's make it happen!

Book your spot before {{offer_expiry_date}}:

👉 [Book Now]({{booking_link_with_offer}})

With love,
{{provider_name}}
{{business_name}}

P.S. Not sure which service is right for you? Just reply to this email or text me at {{phone_number}} — I'm happy to help you figure out the perfect starting point. No pressure, just honest advice!
```

---

## Offer Options by Price Point

**Budget-Friendly:**
- 15% off your first service
- $10 off any service over $50
- Free add-on (e.g., brow tint with lash extensions)

**Mid-Range:**
- 20% off your first service
- $25 off any service over $100
- Free upgrade (e.g., classic to hybrid lash set)

**Premium:**
- Complimentary consultation + $50 off first service
- Free add-on service valued at $30+
- "First visit experience" package at a bundled rate

*Choose based on your average service price and margins. The offer should feel generous but sustainable.*

---

## Urgency Elements

- "This offer expires in 7 days" — clear, honest deadline
- "I only have {{X}} openings this week" — scarcity (only if true)
- "Once this email series ends, this offer goes away" — exclusive to nurture sequence

*Never use fake urgency. Gentle, honest urgency works better for building trust with beauty clients.*

---

## GHL Configuration

- **Trigger:** 3 days after Value Email #2 sent
- **Condition:** Contact has NOT booked an appointment
- **Send via:** Email
- **Workflow name:** Lead Nurture - Offer
- **Actions after send:**
  - Apply tag: "nurture-email-4-sent"
  - Apply tag: "nurture-completed"
  - Remove tag: "nurture-active"
  - If no booking within 7 days:
    - Apply tag: "nurture-no-convert"
    - Enter re-engagement workflow (monthly value emails)
  - If booking made:
    - Apply tag: "nurture-converted"
    - Move pipeline stage to "Booked"
    - Remove from nurture workflow
