# Service Pricing Menu Template

> A clean, professional pricing menu for your beauty business. Populate with your services from CLIENT_CONFIG.md and niche preset. Can be used on your website, in GHL pages, printed, or converted to PDF.

---

## Menu Layout

```
═══════════════════════════════════════════
          {{BUSINESS_NAME}}
     {{tagline_or_short_description}}
═══════════════════════════════════════════
```

---

### {{Category 1 Name}}

| Service | Description | Duration | Price |
|---------|-------------|----------|-------|
| {{service_name}} | {{brief_description}} | {{duration}} | ${{price}} |
| {{service_name}} | {{brief_description}} | {{duration}} | ${{price}} |
| {{service_name}} | {{brief_description}} | {{duration}} | ${{price}} |
| {{service_name}} | {{brief_description}} | {{duration}} | ${{price}} |

---

### {{Category 2 Name}}

| Service | Description | Duration | Price |
|---------|-------------|----------|-------|
| {{service_name}} | {{brief_description}} | {{duration}} | ${{price}} |
| {{service_name}} | {{brief_description}} | {{duration}} | ${{price}} |
| {{service_name}} | {{brief_description}} | {{duration}} | ${{price}} |

---

### {{Category 3 Name}} (if applicable)

| Service | Description | Duration | Price |
|---------|-------------|----------|-------|
| {{service_name}} | {{brief_description}} | {{duration}} | ${{price}} |
| {{service_name}} | {{brief_description}} | {{duration}} | ${{price}} |

---

### Add-On Services

| Add-On | Description | Price |
|--------|-------------|-------|
| {{addon_name}} | {{brief_description}} | +${{price}} |
| {{addon_name}} | {{brief_description}} | +${{price}} |
| {{addon_name}} | {{brief_description}} | +${{price}} |

---

### Packages

```
┌─────────────────────────────────────────┐
│                                         │
│   ✨ {{PACKAGE_NAME}} ✨               │
│                                         │
│   Includes:                             │
│   • {{service_1}}                       │
│   • {{service_2}}                       │
│   • {{service_3}}                       │
│                                         │
│   Duration: {{total_duration}}          │
│   Regular price: ${{regular_total}}     │
│   Package price: ${{package_price}}     │
│   You save: ${{savings}}               │
│                                         │
└─────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────┐
│                                         │
│   ✨ {{PACKAGE_NAME_2}} ✨             │
│                                         │
│   Includes:                             │
│   • {{service_1}}                       │
│   • {{service_2}}                       │
│                                         │
│   Duration: {{total_duration}}          │
│   Regular price: ${{regular_total}}     │
│   Package price: ${{package_price}}     │
│   You save: ${{savings}}               │
│                                         │
└─────────────────────────────────────────┘
```

---

### New Client Special

```
╔═════════════════════════════════════════╗
║                                         ║
║   WELCOME! New Client Special           ║
║                                         ║
║   {{new_client_offer_description}}      ║
║                                         ║
║   {{offer_details}}                     ║
║                                         ║
║   Book online: {{booking_url}}          ║
║                                         ║
╚═════════════════════════════════════════╝
```

---

### Fine Print

```
BOOKING & POLICIES

• A ${{deposit_amount}} deposit is required to secure your appointment.
• Deposits are applied toward your service total.
• Please provide at least {{cancellation_window}} notice for cancellations
  or reschedules. Late cancellations may be subject to a ${{late_fee}} fee.
• No-shows will forfeit their deposit.
• Prices are subject to change. Current prices are confirmed at booking.
• Gratuity is appreciated but never expected.

CONTACT

{{business_name}}
{{business_address}}
{{phone_number}}
{{business_email}}
{{website_url}}

BOOK ONLINE: {{booking_url}}
```

---

## Example: Lash Extensions Menu

```
═══════════════════════════════════════════
        LUXE LASH STUDIO
    Where your lash dreams come true
═══════════════════════════════════════════

CLASSIC LASHES
─────────────────────────────────────────
Full Set          Natural, elegant look              2 hrs    $150
2-Week Fill       Maintain your classic set          1 hr     $65
3-Week Fill       Fuller refresh                     1.5 hrs  $80

VOLUME LASHES
─────────────────────────────────────────
Full Set          Fluffy, dramatic volume            2.5 hrs  $200
2-Week Fill       Keep your volume full              1.5 hrs  $85
3-Week Fill       Fuller refresh                     2 hrs    $100

HYBRID LASHES
─────────────────────────────────────────
Full Set          Best of both worlds                2.5 hrs  $185
2-Week Fill       Maintain your hybrid set           1.5 hrs  $75
3-Week Fill       Fuller refresh                     2 hrs    $90

ADD-ONS
─────────────────────────────────────────
Lash Bath                                            +$10
Colored Lashes (accent)                              +$15
Bottom Lashes                                        +$30
Lash Removal                                         $25

✨ PAMPER PACKAGE ✨
Classic Full Set + Lash Bath + Brow Tint
Regular: $185 → Package: $160 (Save $25!)

═══════════════════════════════════════════
    NEW CLIENTS: 15% off your first set!
         Book at luxelashstudio.com
═══════════════════════════════════════════
```

---

## Design Notes

- Clean, easy-to-read layout with clear hierarchy
- Brand colors and fonts applied
- Categories clearly separated
- Prices right-aligned for easy scanning
- Packages and specials visually highlighted
- Works in both digital (website/GHL page) and print (PDF) formats
- Keep descriptions short — 5-10 words max per service
- List services in order from most popular / most booked at top

## Usage

Tell Claude:
```
"Create my pricing menu"
"Update my menu with new prices"
"Add a holiday package to my pricing menu"
```

Claude will generate a formatted menu using your services, prices, and brand details from CLIENT_CONFIG.md.
