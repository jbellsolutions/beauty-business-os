# Referral Offer Page

> This is the page a new client sees when they click a friend's referral link. Personalized, warm, and focused on one action: booking.

---

## Page Content

### Section 1: Personalized Hero

**Headline:**
```
Share the Love, Get Rewarded
```

**Subheadline (if referrer name is available):**
```
Your friend {{referrer_first_name}} thought you'd love us — and we already love you for being here!
```

**Subheadline (generic fallback):**
```
Someone special sent you our way — welcome!
```

---

### Section 2: How It Works

**Headline:** Here's How It Works

**Steps:**

```
1. 🔗 Share your unique referral link with a friend
2. 📅 Your friend books and completes their first appointment
3. 🎁 You BOTH get rewarded!
```

**Reward Display:**

```
┌─────────────────────────────────┐
│                                 │
│   YOUR FRIEND GETS:             │
│   {{new_client_reward}}         │
│                                 │
│   YOU GET:                      │
│   {{referrer_reward}}           │
│                                 │
└─────────────────────────────────┘
```

---

### Section 3: For the New Client (Referral Landing)

*When someone arrives via a referral link, show this:*

**Headline:**
```
Welcome! Here's Your Special Offer
```

**Body:**
```
{{referrer_first_name}} sent you here because they think you'd love what we do — and we want to make your first visit extra special.
```

**Offer Card:**
```
✨ {{new_client_reward}} on your first visit ✨

Just book using the link below and your discount will be applied automatically.
```

**CTA Button:**
```
Book My First Appointment →
```

**Below CTA:**
```
No code needed — your referral is already tracked!
```

---

### Section 4: Social Proof

**Star Rating:**
```
⭐⭐⭐⭐⭐ {{avg_rating}} stars from {{review_count}} reviews
```

**Testimonials (2-3):**

> "{{testimonial_1}}"
> — {{name_1}}

> "{{testimonial_2}}"
> — {{name_2}}

---

### Section 5: About

**Brief intro:**
```
{{business_name}} is run by {{provider_name}}, a {{niche_title}} in {{city}} who specializes in {{specialties}}. With {{years_experience}} years of experience and hundreds of happy clients, you're in great hands.
```

---

### Section 6: Referral Dashboard (for Existing Clients)

*Shown when a logged-in/identified client visits their referral page:*

**Headline:** Your Referrals

**Unique Link:**
```
Your personal referral link:
[{{referral_link}}]                    [Copy Link]
```

**Share Buttons:**
- Send via text message (pre-filled message)
- Send via email (pre-filled email)
- Share on Instagram DM
- Copy link to clipboard

**Pre-filled Text Message:**
```
Hey! I've been going to {{business_name}} for {{service_type}} and I love it. They're offering {{new_client_reward}} for first-time clients — here's my link: {{referral_link}}
```

**Referral Tracker:**

| Friend | Status | Your Reward |
|--------|--------|-------------|
| {{friend_name_1}} | Booked - {{date}} | {{reward_status}} |
| {{friend_name_2}} | Visited - {{date}} | Ready to redeem! |
| {{friend_name_3}} | Link shared | Waiting for booking |

**Stats:**
```
Total friends referred: {{total_referred}}
Rewards earned: {{total_rewards_earned}}
Rewards available: {{rewards_available}}
```

---

## Design Notes

- Clean, warm, inviting design
- Referrer's name makes it feel personal, not like a cold landing page
- Single CTA for new clients: Book Now
- Existing client view is more of a dashboard with sharing tools
- Mobile-optimized — most referral links are shared via text/DM and opened on phones
- No navigation bar — keep focus on the booking action
- Use brand colors and imagery consistent with the rest of the funnel

## Technical Notes

- Referral link format: `{{base_url}}/ref/{{client_id}}` or `{{base_url}}?ref={{client_id}}`
- URL parameter is captured and stored on the new client's contact record in GHL
- When new client books, GHL workflow links the two contacts and tracks the referral
- Reward fulfillment can be manual (apply discount at checkout) or automated (GHL coupon code)
