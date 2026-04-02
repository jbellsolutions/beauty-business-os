# Metricool Setup Guide

> Metricool is the scheduling and analytics hub for your content pipeline. This guide walks through setup, connection, and best practices.

---

## Step 1: Create Your Metricool Account

1. Go to [metricool.com](https://metricool.com)
2. Sign up for a free account (free plan supports 1 brand with up to 50 scheduled posts/month)
3. If you need more capacity, the Starter plan supports unlimited scheduling
4. Complete your profile setup

---

## Step 2: Connect Your Social Accounts

### Instagram Business Account (Required)
1. In Metricool, go to **Settings > Social Networks > Instagram**
2. Click **Connect Instagram**
3. You will be redirected to Facebook/Meta login (Instagram business accounts are managed through Meta)
4. Log in with the Facebook account linked to your Instagram
5. Select your Instagram Business account
6. Grant all requested permissions (posting, insights, comments)

**Important:** Your Instagram must be a Business or Creator account, not a Personal account. To switch: Instagram > Settings > Account > Switch to Professional Account.

### TikTok
1. In Metricool, go to **Settings > Social Networks > TikTok**
2. Click **Connect TikTok**
3. Log in to your TikTok account
4. Authorize Metricool

**Note on TikTok auto-posting:** Metricool can auto-post to TikTok, but many creators report better reach with manual posting. Consider using Metricool for TikTok as a reminder/draft tool and posting manually from the TikTok app.

### Facebook Page
1. In Metricool, go to **Settings > Social Networks > Facebook**
2. Click **Connect Facebook**
3. Log in and select your Facebook Business Page
4. Grant all permissions

---

## Step 3: Set Up Your Content Calendar

1. Go to the **Planning** section in Metricool
2. You will see a calendar view — this is your command center
3. Click any date/time slot to create a new post
4. For each post, you can:
   - Write the caption
   - Upload media (images, videos)
   - Select which platforms to post to
   - Set the exact posting time
   - Preview how it will look on each platform
   - Add first comment (useful for Instagram hashtags if you prefer them in comments)

### Calendar Setup Tips
- Color-code your content types (education = blue, transformation = green, promo = red, etc.)
- Use Metricool's "Best Time to Post" feature — it analyzes your audience and suggests optimal times
- Schedule content 1 week in advance every Sunday during your batch session

---

## Step 4: API Integration (Optional)

If you want to integrate Metricool with other tools in your workflow:

1. Go to **Settings > Integrations** in Metricool
2. Copy your API key
3. Add the API key to your `CLIENT_CONFIG.md` file:

```yaml
metricool:
  api_key: "your-api-key-here"
  brand_id: "your-brand-id"
  connected_platforms:
    - instagram
    - tiktok
    - facebook
```

This allows automated workflows to check posting status and pull analytics.

---

## Step 5: Analytics Setup

### Weekly Analytics Review
Every week (ideally Monday morning), check these in Metricool:

1. **Dashboard** — Overview of followers, reach, engagement across all platforms
2. **Instagram Analytics:**
   - Best performing posts (by reach, engagement, saves)
   - Follower growth
   - Story performance
   - Reel performance vs. feed post performance
3. **TikTok Analytics:**
   - Video views
   - Watch time
   - Follower growth
   - Best performing videos
4. **Facebook Analytics:**
   - Page reach
   - Post engagement
   - Group activity (if applicable)

### Monthly Report
Metricool can generate PDF reports. Set up a monthly report to track:
- Follower growth across platforms
- Total reach and impressions
- Top 5 posts by engagement
- Best posting times (may shift over time)
- Content type performance comparison

---

## Best Practices

### Scheduling
- **Schedule 1 full week ahead** every Sunday
- **Auto-post for Instagram and Facebook** — set it and forget it
- **Manual post for TikTok** — better reach. Use Metricool to draft and set a reminder, then open TikTok and post manually at the scheduled time
- **Leave room for spontaneous content** — not everything should be pre-scheduled. Real-time stories and reactive content (trending sounds, current events) should be posted in the moment

### Content Management
- **Use Metricool's media library** to organize your content assets
- **Label and tag** your content by type (education, transformation, testimonial, promo)
- **Draft posts in advance** — you can save drafts without scheduling them
- **Preview before publishing** — always check the preview to make sure images are cropped correctly and captions display properly

### Analytics
- **Check analytics weekly**, not daily. Daily fluctuations are noise. Weekly trends are signal.
- **Track these KPIs monthly:**
  - Follower growth rate
  - Average reach per post
  - Engagement rate (engagements / reach)
  - Saves and shares per post
  - DMs received (manually tracked)
  - Bookings attributed to social media (manually tracked)
- **Compare content types** — after 1 month, you will clearly see which content types drive the most engagement and bookings. Double down on winners.

### Troubleshooting
- **Post failed to publish?** Check that your account is still connected (tokens expire). Reconnect if needed.
- **Instagram carousel not posting?** Metricool has specific image size requirements for carousels. Check that all images are the same aspect ratio.
- **Low reach on auto-posted content?** Try posting manually for a week and compare. Some creators report slight reach differences.
- **Analytics not updating?** Data can take 24-48 hours to fully populate. Check back later.

---

## Free vs. Paid Plans

| Feature | Free | Starter ($18/mo) | Advanced ($45/mo) |
|---|---|---|---|
| Scheduled posts/month | 50 | Unlimited | Unlimited |
| Connected brands | 1 | 5 | 15 |
| Analytics history | 3 months | 6 months | Unlimited |
| PDF reports | No | Yes | Yes |
| Competitor analysis | No | Yes | Yes |
| Best time to post | Basic | Advanced | Advanced |

For most solo beauty pros, the **free plan** is sufficient when starting out. Upgrade to Starter when you are posting daily and need unlimited scheduling and deeper analytics.
