# 24-Hour Reminder Email

> Sent 24 hours before the appointment. Reduces no-shows and ensures the client is prepared.

---

## Email

**Subject:** See you tomorrow, {{first_name}}!

**Preview text:** Quick reminder about your {{service_name}} appointment tomorrow

---

**Body:**

```
Hi {{first_name}},

Just a friendly reminder — your appointment is tomorrow!

━━━━━━━━━━━━━━━━━━━━━━━━━
📋 Service: {{service_name}}
📅 Date: {{appointment_date}}
🕐 Time: {{appointment_time}}
📍 Location: {{business_address}}
━━━━━━━━━━━━━━━━━━━━━━━━━

QUICK PREP REMINDERS

{{last_minute_prep}}

GETTING HERE

{{business_address}}
{{parking_directions}}

📍 Google Maps: {{maps_link}}

Please arrive 5-10 minutes early so we can get started on time.

━━━━━━━━━━━━━━━━━━━━━━━━━

Running late or need to reschedule? No worries — just text us at {{phone_number}} and we'll figure it out.

Can't wait to see you!

{{provider_name}}
{{business_name}}
```

---

## Niche-Specific Last-Minute Prep Reminders

**Lash Extensions:**
- Make sure your lashes are clean — no mascara or eye makeup tomorrow
- Skip the caffeine right before if you can (helps you stay still!)
- Charge your phone or bring earbuds — it's a great time to relax

**Facials / Skincare:**
- Come with a clean face if possible
- Skip the retinol tonight
- Drink plenty of water today

**Hair Color / Styling:**
- Don't wash your hair tonight or tomorrow morning
- Wear a button-up or zip-up top
- Have your inspiration photos ready on your phone

**Waxing:**
- Gently exfoliate tonight
- Avoid tight clothing tomorrow — wear something loose and comfy
- Take an ibuprofen 30 minutes before if you're sensitive

**Microblading / PMU:**
- No alcohol tonight
- No aspirin, ibuprofen, or fish oil today
- Have your brow inspo photos ready

**Nails:**
- Remove any old polish before you come in (or we can do it for a small fee)
- Have your design inspiration saved on your phone

---

## GHL Configuration

- **Trigger:** Time-based — 24 hours before appointment
- **Send via:** Email + SMS (optional)
- **SMS version:** "Hey {{first_name}}! Reminder: your {{service_name}} is tomorrow at {{appointment_time}}. Reply Y to confirm or text us if you need to reschedule. See you soon! — {{provider_name}}"
- **Workflow name:** 24hr Appointment Reminder
