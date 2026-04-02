# Client Intake Form Template

> Comprehensive intake form for new clients. Customize based on your niche preset. Can be used as a digital form (GHL form) or printed and filled out in person.

---

## Form Fields

### Section 1: Contact Information

| Field | Type | Required |
|-------|------|----------|
| First Name | Text | Yes |
| Last Name | Text | Yes |
| Phone Number | Phone | Yes |
| Email Address | Email | Yes |
| Date of Birth | Date | Optional |
| Preferred contact method | Dropdown: Text / Email / Call | Yes |

---

### Section 2: Service Interest

| Field | Type | Required |
|-------|------|----------|
| What service are you interested in? | Dropdown (from service list) | Yes |
| Is this your first time getting this service? | Yes / No | Yes |
| If no, who was your previous provider? | Text | Optional |
| How did you hear about us? | Dropdown (see options below) | Yes |

**"How did you hear about us?" options:**
- Instagram
- TikTok
- Facebook
- Google Search
- Yelp
- Friend / Family Referral (who? ___)
- Walk-in / Saw the location
- Other: ___

---

### Section 3: Niche-Specific Questions

*Select the question set that matches your niche. Customize further based on your specific services.*

#### Lash Extensions
| Field | Type |
|-------|------|
| Do you currently have lash extensions? | Yes / No |
| If yes, what type? | Classic / Volume / Hybrid / Unsure |
| Do you wear contact lenses? | Yes / No |
| Have you ever had a reaction to lash adhesive? | Yes / No |
| Do you have any eye conditions? (dry eyes, blepharitis, etc.) | Text |
| What look are you going for? | Natural / Wispy / Dramatic / Unsure |

#### Facials / Skincare
| Field | Type |
|-------|------|
| Skin type | Dry / Oily / Combination / Sensitive / Normal / Unsure |
| Top skin concerns (select all that apply) | Acne, Aging, Hyperpigmentation, Redness, Texture, Dryness, Other |
| Current skincare routine (brief description) | Text area |
| Are you currently using retinoids or acids? | Yes / No / Unsure |
| Do you have a history of cold sores? | Yes / No |
| Have you had any skin treatments in the past 2 weeks? | Yes / No (if yes, what?) |

#### Hair Color / Styling
| Field | Type |
|-------|------|
| Hair type | Straight / Wavy / Curly / Coily |
| Current hair color | Text |
| Is your hair previously colored? | Yes / No / Unsure |
| Have you used box dye in the past 6 months? | Yes / No |
| Desired look (describe or bring photos) | Text area |
| Do you use heat styling tools regularly? | Yes / No |

#### Waxing
| Field | Type |
|-------|------|
| Area(s) to be waxed | Checkbox list |
| Is this your first time waxing this area? | Yes / No |
| Do you use retinoids on the area being waxed? | Yes / No |
| Are you currently on Accutane or have been in the past 6 months? | Yes / No |
| Do you have sensitive skin? | Yes / No |

#### Microblading / PMU
| Field | Type |
|-------|------|
| Have you had microblading or PMU before? | Yes / No |
| If yes, when? | Date / Approximate |
| Are you pregnant or nursing? | Yes / No |
| Do you have diabetes? | Yes / No |
| Are you on blood thinners? | Yes / No |
| Desired brow shape / style | Text + photo reference |
| Do you keloid or scar easily? | Yes / No |

#### Nails
| Field | Type |
|-------|------|
| Service type | Manicure / Pedicure / Both / Gel / Dip / Acrylic / Press-On |
| Do you have any nail conditions? (fungus, lifting, brittleness) | Yes / No (if yes, describe) |
| Any allergies to nail products? | Yes / No |
| Desired look (describe or bring photos) | Text area |
| Natural nail length preference | Short / Medium / Long |

---

### Section 4: Health & Safety

| Field | Type | Required |
|-------|------|----------|
| Do you have any allergies? (latex, adhesives, fragrances, etc.) | Text area | Yes |
| Are you currently pregnant or nursing? | Yes / No | Yes |
| Do you have any medical conditions we should be aware of? | Text area | Optional |
| Are you currently taking any medications? | Text area | Optional |
| Do you have any skin sensitivities? | Text area | Optional |

---

### Section 5: Goals & Expectations

| Field | Type | Required |
|-------|------|----------|
| What are your goals for this appointment? | Text area | Yes |
| Is there anything specific you'd like us to know? | Text area | Optional |
| What does a great experience look like for you? | Text area | Optional |

---

### Section 6: Consent & Policies

#### Service Consent
```
[ ] I understand the nature of the service I am receiving and any potential risks
    involved. I have had the opportunity to ask questions and have them answered
    to my satisfaction.
```

#### Cancellation Policy
```
[ ] I understand that {{business_name}} requires {{cancellation_window}} notice
    for cancellations or reschedules. Late cancellations or no-shows may result
    in a fee of ${{late_fee}} or forfeiture of my deposit.
```

#### Photo Consent
```
[ ] I consent to before/after photos being taken for my personal records.

[ ] I consent to my before/after photos being used on {{business_name}}'s
    social media and marketing materials. (My full name will not be shared
    without additional permission.)

[ ] I do NOT consent to photos being used for marketing purposes.
```

#### Communication Consent
```
[ ] I consent to receiving appointment reminders via text message.

[ ] I consent to receiving occasional promotional emails from {{business_name}}.
    (You can unsubscribe at any time.)
```

---

### Signature

```
Client Name (printed): _______________________________

Client Signature: ____________________________________

Date: _______________________________________________
```

---

## GHL Implementation

### Digital Form Setup
- Create as a GHL form or survey
- Embed on website or send link before appointment
- Map fields to GHL contact custom fields
- Trigger automation on submission:
  - Create/update contact
  - Apply tag: "intake-completed"
  - Notify provider of new intake
  - Send confirmation to client

### Custom Fields to Create in GHL
- `intake_completed` (Yes/No)
- `skin_type` or `hair_type` (niche-dependent)
- `allergies` (text)
- `medical_notes` (text)
- `photo_consent` (Yes/No/Records only)
- `referral_source` (dropdown)
- `referral_name` (text, if referred by someone)

## Notes

- Send the intake form digitally 24-48 hours before the appointment to save time at check-in
- Keep it as short as possible while still getting the info you need — long forms reduce completion rates
- Store completed forms securely (HIPAA considerations for med spas)
- Review intake before the client arrives so you're prepared
- Update intake annually for returning clients

## Usage

Tell Claude:
```
"Create my client intake form"
"Add a question about [topic] to my intake form"
"Generate a GHL form based on my intake template"
```

Claude will customize the form for your niche and format it for your preferred platform.
