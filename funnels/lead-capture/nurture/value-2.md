# Value Email #2 (Day 7)

> Sent 7 days after opt-in (4 days after Value #1). FAQ-style content + social proof to build confidence and move toward booking.

---

## Email

**Subject:** What my clients always ask me about {{topic}}

**Preview text:** Real questions, honest answers from a {{niche_title}}

---

**Example subjects by niche:**
- Lash: "What my clients always ask me about lash extensions"
- Facial: "What my clients always ask me about their skin"
- Hair: "What my clients always ask me about going blonde"
- Waxing: "What my clients always ask me about their first wax"
- Microblading: "What my clients always ask me about microblading pain"
- Nails: "What my clients always ask me about gel vs. dip"

---

**Body:**

```
Hi {{first_name}},

After {{years_experience}} years in this industry, there are a few questions I get asked almost every single day. So I figured — why not just share the answers with you?

Here are the top questions my clients ask:

Q: {{FAQ_question_1}}
A: {{FAQ_answer_1}}

Q: {{FAQ_question_2}}
A: {{FAQ_answer_2}}

Q: {{FAQ_question_3}}
A: {{FAQ_answer_3}}

BUT DON'T JUST TAKE MY WORD FOR IT...

Here's what {{testimonial_client_name}} had to say after her visit:

"{{testimonial_text}}"

{{before_after_mention}}

Seeing results like this is honestly the best part of my job. And I'd love to help you get there too.

👉 [Book a Consultation / Appointment]({{booking_link}})

Have a question I didn't cover? Just reply — I personally read and respond to every email.

Talk soon,
{{provider_name}}
{{business_name}}
```

---

## Example FAQ Block: Facials

```
Q: How often should I really be getting a facial?
A: For most skin types, every 4-6 weeks is the sweet spot. That aligns with your skin's natural renewal cycle. But if you're dealing with active breakouts or specific concerns, we might start more frequently and then space them out as your skin improves.

Q: Will my skin break out after a facial?
A: It's possible to experience a mild "purge" after your first facial — especially if you haven't had one in a while. This is actually a good sign! It means we've cleared out congestion that was sitting under the surface. Any purging usually resolves within 2-3 days.

Q: What's the difference between a basic facial and a custom facial?
A: A basic facial follows a standard cleanse-exfoliate-mask routine. A custom facial is where the magic happens — I analyze your skin, choose targeted products and techniques for YOUR specific concerns, and adjust everything in real time. It's like the difference between a template and a tailor-made solution.
```

---

## Example Testimonial + Before/After Mention

```
Here's what Sarah M. had to say after her HydraFacial series:

"I was so skeptical about facials — I thought they were just a nice-to-have luxury. After 3 sessions with {{provider_name}}, my acne scars have faded significantly and my skin has this glow I've never had before. I'm actually going out without foundation now. Worth every penny!"

I wish I could show you her before and after photos here (they're incredible!). Follow me on Instagram @{{instagram_handle}} to see real client transformations.
```

---

## GHL Configuration

- **Trigger:** 4 days after Value Email #1 sent
- **Condition:** Contact has NOT booked an appointment
- **Send via:** Email
- **Workflow name:** Lead Nurture - Value 2
- **Actions after send:**
  - Apply tag: "nurture-email-3-sent"
  - Wait 3 days, then trigger Offer Email
