---
title: "GA4 Metrics That Actually Matter (And Ones You Can Ignore)"
date: 2026-06-10 10:00:00 +0530
categories: [Analytics, Digital Marketing]
tags: [google-analytics, ga4, digital-marketing, data, metrics]
---

Google Analytics 4 ships with hundreds of metrics. Most of them are noise. After running GA4 for dozens of clients at Compile & Commit, here are the ones I actually watch — and the ones I've stopped caring about.

## The Metrics I Watch Every Week

### 1. Engaged Sessions (not just Sessions)

GA4's "Engaged Session" means the user stayed for 10+ seconds, viewed 2+ pages, or completed a conversion event. It's a far better signal than raw sessions, which counted every bot and accidental click in Universal Analytics.

**What I look for:** Engaged session rate above 50% is healthy. Below 40% and I'm investigating.

### 2. Engagement Rate by Landing Page

Which pages are actually holding attention? I sort by landing page and look at:
- High traffic, low engagement = content or UX problem
- Low traffic, high engagement = underrated page worth promoting

### 3. Key Events (formerly Conversions)

GA4 calls them "Key Events" now. I track:
- Form submissions
- Button clicks (calls, WhatsApp, email)
- Scroll depth (75%+ = read the article)
- Time on page milestones

Set these up in GA4 → Admin → Events → Mark as Key Event.

### 4. User Acquisition Source/Medium

Where are your best users coming from? Not just volume — engagement quality. I compare:
- Organic search vs paid
- Direct vs referral
- Which source drives the users who actually convert

### 5. Retention Cohorts

Available under Reports → Retention. Shows how many users come back after their first visit. Most sites ignore this completely. If your 7-day retention is above 10%, you're building an actual audience.

---

## Metrics I've Mostly Stopped Watching

### Bounce Rate (the old one)
GA4 replaced it with Engagement Rate. The old bounce rate was broken anyway — someone reading your entire article and leaving was counted as a "bounce."

### Average Session Duration
Too easy to game. One person leaving their browser tab open skews your average. I look at engagement rate instead.

### Users vs New Users (as primary metrics)
Useful for context, not for decision-making. I only pull these when writing reports for clients who ask.

---

## My Weekly GA4 Dashboard Setup

I keep a simple Looker Studio dashboard with:

1. **Engaged sessions this week vs last week** (trend line)
2. **Top 10 landing pages by engaged sessions**
3. **Key events by source/medium**
4. **New vs returning users**
5. **Top countries and devices**

That's it. Five cards. Takes 10 minutes to review every Monday.

---

## The Real Point

GA4 gives you data. Your job is to turn that data into a question: *"Why is this happening, and what should I change?"*

If a metric doesn't point you toward an action, it's decoration.

What metrics are you tracking? [Let me know on LinkedIn.](https://www.linkedin.com/in/rishavgc/)
