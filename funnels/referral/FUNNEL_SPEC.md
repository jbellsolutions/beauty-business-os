# Referral Funnel Specification

## Purpose

Turn happy clients into referral sources by making it easy and rewarding to share your business with friends and family. Referrals are the highest-converting, lowest-cost lead source for beauty businesses.

## Target: 1 Referral Per 5 Clients (20% Referral Rate)

## How It Works

```
Client completes visit → Receives referral offer → Shares unique link → Friend books → Both get rewarded
```

## Offer Structure: Give X, Get X

Both the referrer and the new client receive value. This makes the referrer feel good about sharing (they're giving their friend a deal, not just promoting you).

### Reward Tiers by Price Point

| Tier | Referrer Gets | New Client Gets | Best For |
|------|---------------|-----------------|----------|
| Budget | $10 off next visit | $10 off first visit | Services under $75 |
| Mid | $25 off next visit | $25 off first visit | Services $75-$150 |
| Premium | Free add-on service | Free add-on service | Services $150+ |
| VIP | $50 off or free service | $50 off first visit | High-ticket services |

*Choose one tier and keep it simple. Clients shouldn't have to think about which offer to share.*

## Touchpoints

### 1. Post-Visit Email (Primary)
- Included in post-visit follow-up email (`booking/emails/post-visit.md`)
- Contains unique referral link
- "Share the love" messaging

### 2. SMS (Day after visit)
```
Hey {{first_name}}! Thanks again for coming in yesterday. Loved seeing you! If you know anyone who'd love {{service_type}}, share this link and you'll BOTH get {{reward}}: {{referral_link}} — {{provider_name}}
```

### 3. In-Person at Checkout
- Mention the referral program as they leave
- Hand them a physical card with their unique link/code (or QR code)
- "You were amazing today — if you have any friends who'd love this, I have a little thank-you for you both"

### 4. Monthly Referral Reminder (for active clients)
- Light-touch email or SMS reminder
- Include their current referral stats ("You've referred 2 friends so far!")
- Only send to clients who've visited in the last 90 days

## Referral Offer Page (`offer.md`)

The page the new client lands on when they click a referral link:
- Personalized: "Your friend {{referrer_name}} sent you!"
- Reward prominently displayed
- Simple booking CTA
- Trust elements (reviews, about the provider)

## GHL Integration

### Unique Referral Links
- Generated per client using GHL custom fields or a referral tracking tool
- Format: `{{booking_url}}?ref={{client_id}}` or vanity URL
- Track clicks, sign-ups, and bookings per referral link

### Tracking Flow
1. Existing client shares their unique link
2. New client clicks link and lands on referral offer page
3. New client books appointment
4. GHL captures `ref` parameter, links new contact to referrer
5. Both contacts are tagged and rewards are tracked

### Tags
- Referrer: `has-referral-link`, `referred-{{count}}`, `referral-reward-pending`, `referral-reward-redeemed`
- Referred client: `referred-by-{{referrer_id}}`, `referral-new-client`

### Pipeline
- Referrer: Pipeline stage updated when their referral books and completes
- Referred client: Enters booking pipeline with source = "referral"

### Automation
- When referred client completes visit:
  - Notify referrer: "Your friend just visited! Your {{reward}} is ready to use."
  - Apply reward to referrer's next appointment
  - Track conversion in referral dashboard

## Tracking Metrics

| Metric | Target | Calculation |
|--------|--------|-------------|
| Referral rate | 20% | Clients who refer / total active clients |
| Referral link shares | - | Tracked via link clicks |
| Referral conversion rate | 30-50% | Referred bookings / referral link clicks |
| Revenue from referrals | - | Total revenue from referred clients |
| Cost per referred client | - | Total rewards given / referred clients |
| Referral LTV | - | Lifetime value of referred clients vs. other sources |

## Physical Referral Card Template

```
━━━━━━━━━━━━━━━━━━━━━━
    {{business_name}}

  SHARE THE LOVE

  Give your friend {{new_client_reward}}
  and get {{referrer_reward}} for yourself!

  {{referral_url_or_qr_code}}

  Code: {{referral_code}}
━━━━━━━━━━━━━━━━━━━━━━
```

*Print on thick cardstock, brand colors, standard business card size. Include QR code that links to their unique referral URL.*

## Notes

- The best time to ask for referrals is immediately after a great service when the client is happiest
- Make the referral program feel like a gift, not a sales tactic
- Track which clients are your top referrers and treat them as VIPs
- Referral rewards should be redeemable on their next visit (encourages rebooking)
- Consider a tiered bonus: 3 referrals = extra reward, 5 referrals = VIP status
