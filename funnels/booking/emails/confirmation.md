# Booking Confirmation Email

> Sent immediately after a client books an appointment. Sets expectations and reduces no-shows.

---

## Email

**Subject:** You're booked! Here's what to know before your {{service_name}}

**Preview text:** Your appointment details + how to prepare

---

**Body:**

```
Hi {{first_name}},

Great news — your appointment is confirmed! Here are your details:

━━━━━━━━━━━━━━━━━━━━━━━━━
📋 Service: {{service_name}}
📅 Date: {{appointment_date}}
🕐 Time: {{appointment_time}}
📍 Location: {{business_address}}
👤 With: {{provider_name}}
━━━━━━━━━━━━━━━━━━━━━━━━━

HOW TO PREPARE

{{preparation_instructions}}

WHAT TO BRING

{{what_to_bring}}

PARKING & ARRIVAL

{{parking_directions}}
Please arrive 5-10 minutes early, especially if this is your first visit.

OUR POLICY

We kindly ask for {{cancellation_window}} notice if you need to cancel or reschedule. Late cancellations or no-shows may be subject to a {{cancellation_fee}} fee.

Need to reschedule? Click here: {{reschedule_link}}

━━━━━━━━━━━━━━━━━━━━━━━━━

We're looking forward to seeing you, {{first_name}}! If you have any questions at all, just reply to this email or text us at {{phone_number}}.

See you soon,
{{provider_name}}
{{business_name}}
```

---

## Niche-Specific Preparation Instructions

Load from the active niche preset. Defaults by niche:

**Lash Extensions:**
- Come with completely clean lashes — no mascara, eyeliner, or eye cream
- Avoid caffeine before your appointment (it can make your eyes flutter!)
- Your appointment will take 1.5-2 hours, so feel free to relax or nap
- Bring: Nothing special needed, just yourself!

**Facials / Skincare:**
- Arrive with a clean face if possible (we'll cleanse either way)
- Discontinue retinoids and exfoliants 48 hours before
- Let us know about any new products or skin changes
- Bring: A list of your current skincare products if it's your first visit

**Hair Color / Styling:**
- Don't wash your hair the day of your appointment
- Wear a button-up or zip-up top to avoid pulling over fresh color
- Bring reference photos of your desired look
- Bring: Inspiration photos saved on your phone

**Waxing:**
- Hair should be at least 1/4 inch long (about 2-3 weeks of growth)
- Gently exfoliate the area 24 hours before
- Avoid sun exposure and tanning 24 hours before
- Bring: Nothing special needed

**Microblading / PMU:**
- Avoid blood thinners, alcohol, and excessive caffeine 24 hours before
- No retinoids on the brow area for 2 weeks before
- Avoid sun exposure and tanning 1 week before
- Bring: Reference photos of your desired brow shape

**Nails:**
- Remove any existing polish or dip before arriving (or add removal to your service)
- Push back cuticles gently if you can
- Bring: Inspiration photos of your desired design

---

## GHL Configuration

- **Trigger:** Appointment booked (calendar event created)
- **Send via:** Email
- **From:** {{business_name}} <{{business_email}}>
- **Reply-to:** {{business_email}}
- **Workflow name:** Booking Confirmation
