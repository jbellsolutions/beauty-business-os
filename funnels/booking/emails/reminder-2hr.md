# 2-Hour Reminder Email

> Sent 2 hours before the appointment. Brief, friendly, and practical.

---

## Email

**Subject:** Almost time! ✨

**Preview text:** Your {{service_name}} appointment is in 2 hours

---

**Body:**

```
Hi {{first_name}},

This is your friendly heads-up — your appointment is in about 2 hours!

📍 {{business_address}}
🕐 {{appointment_time}}

Google Maps: {{maps_link}}

If anything comes up, call or text us at {{phone_number}}.

See you soon!
{{provider_name}}
```

---

## SMS Version (Recommended for 2hr)

```
Hi {{first_name}}! Your {{service_name}} appointment is in 2 hours at {{appointment_time}}. Address: {{business_address}}. See you soon! — {{provider_name}} 💕
```

*The 2-hour reminder is most effective as an SMS. Email can be used as a supplement or fallback if the client hasn't opted into SMS.*

---

## GHL Configuration

- **Trigger:** Time-based — 2 hours before appointment
- **Send via:** SMS preferred, email as fallback
- **Workflow name:** 2hr Appointment Reminder
- **Condition:** Only send if appointment status is not "cancelled" or "rescheduled"
