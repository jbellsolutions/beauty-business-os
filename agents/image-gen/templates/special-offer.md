# Special Offer / Sale Graphic Template

## Overview
Generates eye-catching promotional graphics for sales, seasonal offers, flash deals, and limited-time specials. These are higher-energy than standard promo posts — designed to create urgency and drive immediate bookings.

## Dimensions
- **Instagram Feed:** 1080x1080 (1:1)
- **Instagram Story:** 1080x1920 (9:16)
- Generate both sizes for each offer so the user can post everywhere

## Layout Spec
- Discount/offer text area: prominent center or upper half (largest visual element)
- Urgency element: dates, "limited time", countdown reference
- Service name: clear but secondary to the offer
- Booking CTA: bottom third ("Book Now", "Claim Your Spot")
- Brand colors as foundation with seasonal accent colors layered on

## Replicate Prompt Templates

### Standard Sale / Discount
```
Special offer promotional graphic for beauty salon, {{brand.colors}} color scheme, bold modern sale announcement design, luxury spa aesthetic, dynamic composition with emphasis area for discount text, subtle sparkle or shine elements, professional clean layout, large empty text area for offer details, no text, no faces, 1080x1080
```

### Flash Sale / Urgency
```
Flash sale promotional graphic, bold urgent design, {{brand.colors}} with red and gold accents, high energy beauty salon promotion, dramatic lighting, premium feel with urgency, countdown timer aesthetic, large centered text area, dynamic background, no text, no faces, 1080x1080
```

## Seasonal Variation Templates

### Valentine's Day (February)
```
Valentine's Day beauty salon special offer graphic, romantic pink red and gold color scheme with {{brand.accent_color}}, hearts and rose elements, elegant feminine luxury design, love-themed beauty promotion, soft romantic lighting, large text overlay area, no text, no faces, 1080x1080
```
**Offer ideas:** "Galentine's packages", couples facials, self-love specials, gift card promos

### Spring / Mother's Day (March-May)
```
Spring beauty salon promotional graphic, fresh pastel colors with {{brand.colors}}, floral botanical elements, bright airy aesthetic, mother's day gift worthy design, clean modern layout, garden party elegance, text overlay area, no text, no faces, 1080x1080
```
**Offer ideas:** Mother-daughter packages, "spring refresh" specials, gift cards

### Summer (June-August)
```
Summer beauty salon special offer graphic, bright tropical vibrant colors with {{brand.colors}}, sun-kissed warm aesthetic, beach-ready beauty promotion, bold energetic summer design, fresh modern layout, large text area, no text, no faces, 1080x1080
```
**Offer ideas:** "Summer-ready" packages, vacation prep specials, glow-up bundles

### Back to School / Fall (September-October)
```
Autumn beauty salon promotional graphic, warm rich colors with {{brand.colors}}, cozy fall aesthetic, amber burgundy and gold tones, elegant seasonal beauty design, sophisticated warm lighting, text overlay area, no text, no faces, 1080x1080
```
**Offer ideas:** Back-to-school refresh, fall transformation packages, Halloween-themed

### Holiday Season (November-December)
```
Holiday beauty salon special offer graphic, gold sparkle and {{brand.colors}} color scheme, festive luxury aesthetic, Christmas holiday glamour, premium gift-worthy design, elegant winter beauty promotion, bokeh lights, large text area, no text, no faces, 1080x1080
```
**Offer ideas:** Gift card specials, holiday glam packages, 12 days of deals, New Year prep

### New Year / Fresh Start (January)
```
New Year beauty salon promotional graphic, fresh clean modern design, white and {{brand.colors}} color scheme, new beginnings aesthetic, crisp minimal luxury, fresh start energy, sophisticated clean lines, resolution-themed beauty promotion, text area, no text, no faces, 1080x1080
```
**Offer ideas:** "New year, new you" packages, January specials to fill slow month, membership launches

## Pairing with Seasonal Promos Preset
This template works with the `seasonal_promos` configuration in your niche setup:

1. Check your niche config for pre-built seasonal offers
2. Use the seasonal prompt template that matches the current month
3. Generate the graphic
4. Apply the offer details from `seasonal_promos` as text overlay
5. Schedule across all platforms

**Example flow:**
```
User: "Create a holiday special post"
Agent checks: niche.seasonal_promos.holiday → "Holiday Glam Package: Lashes + Brows + Facial — $199 (save $60)"
Agent generates: Holiday-themed graphic
Agent suggests: Text overlay with the package details + booking link
```

## Post-Generation Workflow
1. AI generates the offer background graphic (both 1080x1080 and 1080x1920)
2. User downloads both sizes
3. User adds text in Canva:
   - Offer headline ("20% OFF" or "Holiday Special")
   - Service/package name
   - Price (original crossed out + new price)
   - Dates ("This week only" or "Dec 1-15")
   - Booking CTA + link
4. Post to feed (1080x1080) and stories (1080x1920)

## Urgency Tactics
- Expiration dates (always include one)
- "Only X spots left" (if true)
- "First 10 clients only"
- Countdown sticker on Stories
- "Last chance" follow-up story 24 hours before expiration

## Caption Template
```
[SEASONAL HOOK] is here and we're celebrating!

[OFFER DETAILS]
[Original price] → [Sale price] (save [amount])

This offer is available [timeframe] only.
[Number] spots available — don't wait!

Book now: [link in bio]

#[city]beauty #[service]special #[seasonal]deals #beautysale
```

## Best Practices
- Run max 2 special offers per month (more than that devalues your brand)
- Always include an expiration date — open-ended offers don't convert
- Make the savings crystal clear (show original price crossed out)
- Follow up with a "last chance" story on the final day
- Track which seasonal offers perform best for next year's planning
- Don't discount your most premium services — offer bundles or add-ons instead
