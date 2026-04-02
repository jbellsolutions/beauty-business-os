# Value Email #1 (Day 3)

> Sent 3 days after opt-in. Pure educational value that positions you as the expert. Soft CTA only.

---

## Email

**Subject:** {{niche_specific_tip_headline}}

**Preview text:** A quick tip that makes a big difference

---

**Example subjects by niche:**
- Lash: "The one thing that makes lash extensions last weeks longer"
- Facial: "Why your moisturizer might not be doing what you think"
- Hair: "The 60-second trick for salon-worthy blowouts at home"
- Waxing: "How to never get an ingrown hair again"
- Microblading: "The biggest myth about microblading (debunked)"
- Nails: "Why your gel polish keeps peeling (and the easy fix)"

---

**Body:**

```
Hi {{first_name}},

I wanted to share something that comes up with my clients all the time — and once you know this, it's a total game-changer.

{{EDUCATIONAL CONTENT BLOCK}}

[Insert 200-300 words of genuinely useful, niche-specific advice. This should be something actionable that the reader can use right away. Write it in a conversational, knowledgeable tone — like you're chatting with a friend who asked for your expert opinion.]

{{/EDUCATIONAL CONTENT BLOCK}}

The takeaway? {{one_sentence_summary}}.

If you found this helpful, just wait — I've got more good stuff coming your way in a few days.

And if you want personalized help with this, that's literally what I do every day! I'd love to help you get {{desired_result}}.

👉 [Learn more about our {{service_name}}]({{service_page_link}})

Talk soon,
{{provider_name}}
{{business_name}}

P.S. Got a question? Hit reply — I love hearing from you.
```

---

## Example Content Block: Lash Extensions

```
Here's something I tell every single client: your lash aftercare in the first 24 hours determines how long your set will last.

I know it's tempting to touch them (they look so good!), but here's the deal:

1. Keep them completely dry for 24 hours. That means no steamy showers, no face washing directly on the lashes, and no crying at that movie you've been meaning to watch (okay, maybe save it for day 2).

2. Skip the oil-based products around your eyes. Oil breaks down lash adhesive faster than anything. Check your makeup remover, your moisturizer, even your sunscreen. If it has oil in the first 5 ingredients, keep it away from your lash line.

3. Sleep on your back if you can. I know, I know — easier said than done. But if you're a face-smoosher, try a silk pillowcase at minimum. Your lashes (and your skin) will thank you.

These three things alone can add an extra week to your lash retention. And that means more time looking fabulous between fills.
```

---

## GHL Configuration

- **Trigger:** 3 days after welcome email sent
- **Condition:** Contact has NOT booked an appointment (if they already booked, skip nurture)
- **Send via:** Email
- **Workflow name:** Lead Nurture - Value 1
- **Actions after send:**
  - Apply tag: "nurture-email-2-sent"
  - Wait 4 days, then trigger Value Email #2
