# Welcome Email (Sent Immediately)

> Delivered immediately after opt-in. Provides the lead magnet, introduces yourself, and includes a first-time offer.

---

## Email

**Subject:** Here's your {{lead_magnet_title}} + a little something extra

**Preview text:** Your free {{lead_magnet_type}} is ready to download

---

**Body:**

```
Hi {{first_name}},

Welcome! I'm so glad you're here.

As promised, here's your free {{lead_magnet_title}}:

👉 [Download Your Free {{lead_magnet_type}}]({{download_link}})

Take a few minutes to read through it — I packed in everything I wish my clients knew from day one.

A LITTLE ABOUT ME

I'm {{provider_name}}, and I run {{business_name}} in {{city}}. I've been in the {{niche_area}} world for {{years_experience}} years, and honestly? I still love what I do just as much as when I started.

I'm passionate about {{passion_statement}}, and that's what I try to bring to every single client who sits in my chair / walks through my door.

A LITTLE SOMETHING EXTRA

Since you're here, I'd love to offer you something special:

✨ {{first_time_offer}} — just for new clients ✨

Use code {{offer_code}} when you book, or just mention this email:

👉 [Book Your First Appointment]({{booking_link}})

This offer is good for {{offer_duration}}, so don't let it slip away!

STAY CONNECTED

For daily tips, behind-the-scenes content, and before/after transformations, follow me on Instagram:

📱 @{{instagram_handle}}

I'll be sending you a few more helpful emails over the next week or so — good stuff, no spam. Promise.

Talk soon,
{{provider_name}}

P.S. If you have any questions about {{niche_area}}, just reply to this email. I personally read every reply!
```

---

## GHL Configuration

- **Trigger:** Contact created with tag "lead-magnet-downloaded"
- **Send via:** Email
- **Delay:** None (immediate)
- **Workflow name:** Lead Nurture - Welcome
- **Actions after send:**
  - Apply tag: "nurture-email-1-sent"
  - Wait 3 days, then trigger Value Email #1
