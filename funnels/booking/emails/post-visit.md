# Post-Visit Follow-Up Email

> Sent 2 hours after the appointment is marked as completed. Thanks the client, delivers aftercare, asks for a review, and opens the door for rebooking and referrals.

---

## Email

**Subject:** How are you feeling after your {{service_name}}?

**Preview text:** Aftercare tips + a little thank you from {{business_name}}

---

**Body:**

```
Hi {{first_name}},

Thank you so much for coming in today! It was so great to see you, and I hope you're loving your results.

AFTERCARE REMINDERS

To keep your results looking their best, here are a few tips:

{{aftercare_instructions}}

REBOOK YOUR NEXT APPOINTMENT

To maintain your results, I recommend coming back in {{recommended_interval}}. The sooner you book, the more likely you'll get your preferred time!

👉 [Book Your Next Appointment]({{booking_link}})

SHARE YOUR EXPERIENCE

If you had a great experience, it would mean the world to me if you left a quick review. It only takes a minute and it helps other people like you find us!

⭐ [Leave a Google Review]({{google_review_link}})

SHARE THE LOVE

Know someone who'd love this? Share your personal referral link and you'll both get {{referral_reward}}:

🔗 {{referral_link}}

━━━━━━━━━━━━━━━━━━━━━━━━━

Thanks again, {{first_name}}. You looked amazing, and I can't wait to see you again!

With love,
{{provider_name}}
{{business_name}}

P.S. Have any questions about aftercare? Just reply to this email — I'm always happy to help!
```

---

## Niche-Specific Aftercare Instructions

**Lash Extensions:**
- Avoid getting your lashes wet for the first 24 hours
- Don't use oil-based products near your eyes
- Avoid rubbing or pulling at your lashes
- Sleep on your back or side to avoid crushing them
- Use the lash brush we gave you to gently groom them each morning
- Come back in 2-3 weeks for a fill to keep them full

**Facials / Skincare:**
- Your skin may be slightly pink or sensitive — this is normal
- Avoid heavy makeup for 24 hours
- Use SPF 30+ sunscreen daily (even indoors!)
- Keep your routine gentle for the next 2-3 days
- Drink plenty of water to support your skin's healing
- Book your next facial in 4-6 weeks

**Hair Color / Styling:**
- Wait 48-72 hours before washing your hair
- Use sulfate-free, color-safe shampoo and conditioner
- Wash with cool/lukewarm water to preserve color
- Minimize heat styling — use heat protectant when you do
- Come back in 6-8 weeks for a touch-up or refresh

**Waxing:**
- Avoid hot showers, saunas, and tight clothing for 24 hours
- No exfoliating the area for 48 hours
- Apply soothing aloe or the post-wax product we recommended
- Begin gentle exfoliation after 3-4 days to prevent ingrowns
- Come back in 4-6 weeks for your next appointment

**Microblading / PMU:**
- Keep the area dry for 10 days — no swimming, sweating, or steam
- Apply the aftercare ointment as directed (thin layer, 2-3x daily)
- Don't pick or scratch as it heals — let the scabs fall off naturally
- Color will appear darker at first, then lighten 30-50% as it heals
- Book your touch-up in 6-8 weeks (this is required for best results)

**Nails:**
- Avoid submerging nails in water for extended periods for 24 hours
- Wear gloves when cleaning with chemicals
- Apply cuticle oil daily to keep nails and cuticles healthy
- Avoid using nails as tools (opening cans, picking at things)
- Come back in 2-3 weeks for a fill or new set

---

## GHL Configuration

- **Trigger:** Appointment status changed to "Completed" + 2 hour delay
- **Send via:** Email
- **Workflow name:** Post-Visit Follow-Up
- **Additional actions:**
  - Move pipeline stage to "Rebook Pending"
  - Add tag: "visited-{{service_slug}}"
  - If no rebook within 7 days, trigger rebook reminder sequence
