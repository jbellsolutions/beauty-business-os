# Dashboard Agent Instructions

## Purpose

You maintain the visual dashboard at `dashboard/index.html`. This is a simple HTML file that the business owner opens in their browser to see their business at a glance.

## How It Works

There is no database. No backend. No API. You update the dashboard by reading the current HTML file, modifying the data sections, and writing the updated file. The user refreshes their browser (or it auto-refreshes every 5 minutes).

## When to Update

Update the dashboard during these heartbeats:

1. **Morning Briefing (8 AM):** Update appointments, tasks, content schedule, lead pipeline counts
2. **End of Day (6 PM):** Update revenue figures, bookings count, quick stats
3. **Weekly Review (Sunday):** Update all sections with weekly data, trends, comparisons
4. **On Demand:** When the user asks "update my dashboard" or "how am I doing"

## What to Update

### Stats Row (top 4 cards)
- `#revenue-week` — Dollar amount for current week
- `#revenue-change` — Comparison to last week (add class `up`, `down`, or `neutral`)
- `#bookings-week` — Number of bookings this week
- `#bookings-change` — Comparison text
- `#new-leads` — New leads this week
- `#leads-change` — Comparison text
- `#content-count` — Number of posts scheduled for next 7 days

### Appointments Section
Replace the contents of `#appointments` div with appointment HTML:
```html
<div class="appointment">
  <div class="appt-time">10:00 AM</div>
  <div class="appt-details">
    <div class="appt-name">Sarah Johnson</div>
    <div class="appt-service">Volume Full Set</div>
  </div>
  <div class="appt-price">$250</div>
</div>
```

### Content Schedule Section
Replace `#content-schedule` div:
```html
<div class="content-item">
  <div class="content-platform platform-tiktok">TikTok</div>
  <div class="content-desc">Before/after lash transformation</div>
  <div class="content-time">6:00 PM today</div>
</div>
```
Platform classes: `platform-tiktok`, `platform-ig`, `platform-yt`

### Tasks Section
Replace `#tasks` div:
```html
<div class="task">
  <div class="task-check"></div>
  <div class="task-text">Order more lash adhesive</div>
  <div class="task-priority priority-high">High</div>
</div>
```
Add class `done` to both `task-check` and `task-text` for completed tasks.
Priority classes: `priority-high`, `priority-med`, `priority-low`

### Lead Pipeline
Update the count values:
- `#pipe-new` — New/uncontacted leads
- `#pipe-contacted` — Leads you've reached out to
- `#pipe-booked` — Leads who've booked
- `#pipe-completed` — Completed appointments

### Quick Stats
- `#booking-rate` — Percentage of leads that book
- `#avg-service` — Average service dollar value
- `#top-service` — Name of most popular service
- `#revenue-month` — Total revenue this month

### Business Name
- `#business-name` — Set to the business name from CLIENT_CONFIG.md

## Rules

1. Always read the current HTML before writing — preserve the structure
2. Only modify data content inside the identified elements — never change CSS or layout
3. If data is unavailable, leave the empty state (don't show fake data)
4. Keep appointment list to today only
5. Content schedule shows next 7 days
6. Tasks show max 8 items (most important first)
7. Set the business name on every update from CLIENT_CONFIG.md
