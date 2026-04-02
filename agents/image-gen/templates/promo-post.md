# Promo Post Image Template

## Overview
Generates professional promotional graphics for beauty services. The AI creates the visual background/design, and the user adds text overlays in Canva or their preferred editor (AI is unreliable at text rendering).

## Dimensions
- **Instagram Feed:** 1080x1080 (1:1)
- **Instagram Story / Reel Cover:** 1080x1920 (9:16)
- **Facebook Post:** 1200x630
- Generate feed size by default; story size on request

## Layout Spec
- Service name area: top third or center
- Price/discount area: bold, lower third
- CTA area: bottom (e.g., "Book Now", "Link in Bio")
- Brand colors as primary palette
- Clean negative space for text overlay
- No human faces (avoids uncanny valley issues with AI generation)

## Replicate Prompt Templates

### Minimal / Clean Style
```
Professional beauty salon promotional graphic, {{brand.colors}} color scheme, modern clean minimalist design, elegant feminine aesthetic, soft lighting, high-end spa atmosphere, abstract beauty elements, subtle floral accents, large empty space for text overlay, no text, no faces, no hands, 1080x1080
```

### Bold / Vibrant Style
```
Bold vibrant beauty salon promotional graphic, {{brand.colors}} color palette, modern energetic design, dynamic composition, beauty product elements, glossy textures, bright professional lighting, eye-catching gradient background, prominent empty text area, no text, no faces, no hands, 1080x1080
```

### Luxury / Gold Style
```
Luxury gold-accented beauty salon promotional graphic, black and gold color scheme with {{brand.accent_color}} touches, premium elegant design, marble texture elements, gold foil aesthetic, sophisticated spa branding feel, refined minimalist layout, large text overlay area, no text, no faces, no hands, 1080x1080
```

## Post-Generation Workflow
1. AI generates the background/design image via Replicate
2. User downloads the image
3. User opens in Canva (or Photoshop, etc.)
4. User adds:
   - Service name (e.g., "Lash Lift & Tint")
   - Price or discount (e.g., "$89" or "20% Off")
   - CTA (e.g., "Book Now - Link in Bio")
   - Logo (if not baked into the design)
5. Export and post

## Canva Pairing Tips
- Use Canva's "Background Remover" if AI image has unwanted elements
- Add brand fonts consistently across all promos
- Save as a Canva template for quick reuse
- Use Canva's "Brand Kit" to keep colors consistent

## Usage Examples

**User says:** "Make me a promo post for 20% off lash extensions"
**Agent generates:** Clean luxury background graphic in their brand colors
**Agent responds with:**
- The generated image
- Suggested text overlay: "Lash Extensions / 20% Off This Week / Book Now"
- Suggested hashtags for the caption
- Reminder to add text in Canva

**User says:** "I need a bold post announcing our new keratin treatment"
**Agent generates:** Vibrant, energetic background in brand colors
**Agent responds with:**
- The generated image
- Suggested text: "NOW OFFERING / Keratin Smoothing Treatment / Starting at $199"

## Niche Variations
- **Lash studio:** Soft pinks, close-up texture elements, wispy accents
- **Hair salon:** Rich warm tones, flowing abstract shapes, shine elements
- **Nail salon:** Glossy finishes, polish bottle silhouettes, bold color pops
- **Med spa:** Clinical clean whites, blue accents, professional medical aesthetic
- **Esthetician:** Natural earthy tones, botanical elements, dewy textures
