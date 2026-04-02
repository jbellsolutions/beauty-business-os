# Thank You / Confirmation Page

> Shown immediately after a client books an appointment. Reinforces the decision, sets expectations, and opens the door for referrals.

---

## Page Content

### Section 1: Confirmation Message

**Headline:**
```
You're all set, {{first_name}}! 🎉
```

**Subheadline:**
```
Your appointment has been booked. Here are your details:
```

**Appointment Details Card:**
```
📋 Service: {{service_name}}
📅 Date: {{appointment_date}}
🕐 Time: {{appointment_time}}
📍 Location: {{business_address}}
👤 With: {{provider_name}}
```

---

### Section 2: What to Expect / How to Prepare

**Headline:** How to Prepare

**Body:**
```
To get the best results from your {{service_name}}, here's what we recommend:

{{preparation_instructions}}
```

*Preparation instructions are pulled from the active niche preset. Examples:*
- **Lash extensions**: Come with clean lashes, no mascara or eye makeup. Appointment takes 1.5-2 hours — feel free to nap!
- **Facials**: Arrive with a clean face if possible. Avoid retinols 48 hours before your appointment.
- **Hair color**: Don't wash your hair the day of. Wear a button-up top to avoid pulling over color.
- **Waxing**: Hair should be at least 1/4 inch long. Gently exfoliate the day before.
- **Microblading**: Avoid blood thinners, alcohol, and caffeine 24 hours before.

---

### Section 3: Add to Calendar

**Button:**
```
📅 Add to Calendar
```

*Generate .ics file or deep links for:*
- Google Calendar
- Apple Calendar
- Outlook

*Calendar event should include:*
- Event title: `{{service_name}} at {{business_name}}`
- Time: `{{appointment_date}} {{appointment_time}}`
- Location: `{{business_address}}`
- Description: Preparation instructions + contact number

---

### Section 4: Share With a Friend

**Headline:** Know Someone Who'd Love This?

**Body:**
```
Share the love! Send a friend our way and you'll both get {{referral_reward}}.
```

**Share Buttons:**
- Text message (pre-filled: "I just booked at {{business_name}} and love it! Here's their link: {{booking_url}}")
- Email share
- Copy link
- Instagram DM

*If referral funnel is active, use the client's unique referral link here.*

---

### Section 5: Follow Us

**Headline:** Stay Connected

```
Follow us for tips, transformations, and behind-the-scenes content:
```

- Instagram: @{{instagram_handle}}
- TikTok: @{{tiktok_handle}}
- Facebook: {{facebook_url}}

---

### Section 6: Aftercare Preview

**Headline:** After Your Visit

**Body:**
```
We'll send you personalized aftercare instructions after your appointment so your results last as long as possible. You'll also get a link to rebook at your preferred interval.

We can't wait to see you, {{first_name}}!
```

---

## Technical Notes

- This page is shown after GHL form/calendar submission
- Appointment details are dynamically populated from the booking submission
- Add-to-calendar links are generated dynamically with appointment details
- Referral link should be generated for the client if referral funnel is active
- Page should also trigger the confirmation email workflow in GHL
- Track this page view as the conversion event for ad pixel tracking
