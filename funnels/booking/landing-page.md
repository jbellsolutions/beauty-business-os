# Booking Landing Page Copy Template

> This template generates the main booking page for your beauty business. All placeholders pull from your CLIENT_CONFIG.md and active niche preset.

---

## Page Structure

### Section 1: Hero

**Headline:**
```
{{service_name}} in {{city}} — Book Your Appointment
```

**Subheadline:**
```
{{tagline_or_value_prop}}
```

**Hero Image:** Before/after transformation photo or high-quality service-in-action shot

**Primary CTA Button:**
```
Book Now →
```

---

### Section 2: Social Proof Bar

```
⭐⭐⭐⭐⭐ {{avg_rating}} stars · {{review_count}} reviews on Google
```

**Testimonials (2-3):**

> "{{testimonial_1_text}}"
> — {{testimonial_1_name}}

> "{{testimonial_2_text}}"
> — {{testimonial_2_name}}

> "{{testimonial_3_text}}"
> — {{testimonial_3_name}}

*Pull from highest-rated Google/Yelp reviews. Use first name + last initial only.*

---

### Section 3: Services + Pricing

**Section Headline:** Our Services

| Service | Duration | Price |
|---------|----------|-------|
| {{service_1_name}} | {{duration}} | ${{price}} |
| {{service_2_name}} | {{duration}} | ${{price}} |
| {{service_3_name}} | {{duration}} | ${{price}} |
| {{service_4_name}} | {{duration}} | ${{price}} |

*Prices pulled from niche preset. Include brief 1-line description under each service name.*

**New Client Special:**
```
First-time visit? Enjoy {{new_client_offer}} — Book today!
```

**CTA Button:**
```
View Availability →
```

---

### Section 4: About

**Section Headline:** Meet {{provider_name}}

**Photo:** Professional but warm headshot or candid working photo

**Bio Copy (150-200 words):**
```
Hi, I'm {{provider_name}}! I've been passionate about {{niche_area}} for {{years_experience}} years, and I love helping my clients {{desired_outcome}}.

I specialize in {{specialties}}, and my approach is all about {{approach_philosophy}}.

When you visit {{business_name}}, you can expect {{experience_description}}. I believe everyone deserves to feel {{feeling}}, and that's exactly what I'm here to help you with.

{{certification_or_credential_mention}}

I can't wait to meet you!
```

---

### Section 5: FAQ

**Section Headline:** Common Questions

**Q: How do I prepare for my {{service_type}} appointment?**
A: {{preparation_instructions}}

**Q: How long does a {{service_type}} appointment take?**
A: {{duration_answer}}

**Q: What is your cancellation policy?**
A: We require {{cancellation_window}} notice for cancellations or reschedules. Late cancellations may be subject to a {{cancellation_fee}} fee.

**Q: Is there parking available?**
A: {{parking_info}}

**Q: Do you offer {{common_related_service}}?**
A: {{related_service_answer}}

*FAQ questions should be customized per niche. Pull from niche preset's common_questions if available.*

---

### Section 6: Final CTA

**Headline:**
```
Ready to Book?
```

**Body:**
```
Your {{desired_outcome}} is just one appointment away. Pick a time that works for you — I can't wait to see you!
```

**CTA Button:**
```
Book Your Appointment →
```

**Below CTA:**
```
Questions? Call or text us at {{phone_number}}
```

---

## Design Notes

- **Mobile-first**: 80%+ of traffic will be mobile. Stack all sections vertically, full-width CTAs
- **Load speed**: Compress images to < 200KB, lazy-load below fold
- **Colors**: Use brand colors from CLIENT_CONFIG.md
- **Typography**: Clean, modern sans-serif. Large headline text (32-48px mobile)
- **CTA buttons**: High contrast, rounded corners, large tap target (min 48px height)
- **Sticky CTA**: Mobile should have a sticky "Book Now" bar at bottom of screen
- **GHL**: Embed calendar widget inline or as popup triggered by CTA button click

## SEO

- **Page title**: `{{service_name}} in {{city}} | {{business_name}}`
- **Meta description**: `Book your {{service_name}} appointment at {{business_name}} in {{city}}. {{social_proof_snippet}}. Online booking available.`
- **H1**: The hero headline (only one H1 per page)
- **Schema markup**: LocalBusiness + Service schema for rich search results
