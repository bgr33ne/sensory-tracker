# Sensory Tracker

Landing page and SEO content for Sensory Tracker - a voice-powered sensory tracking app for families, caregivers, and therapists supporting individuals with autism, ADHD, and sensory processing differences.

## Project Overview

**Goal:** Gauge demand for the product via waitlist signups
**Target audience:** Parents (primary buyers), children (users), medical professionals (OTs, therapists)
**Stage:** Pre-launch landing page

## Live URLs

- **Production:** https://www.sensorytracker.com
- **Vercel:** https://sensory-tracker.vercel.app
- **GitHub:** https://github.com/bgr33ne/sensory-tracker

## Tech Stack

- **Frontend:** Static HTML/CSS/JS (no framework)
- **Fonts:** Google Fonts (Fraunces + DM Sans)
- **Icons:** Lucide icon paths (inline SVG)
- **Hosting:** Vercel
- **Source control:** GitHub

## File Structure

```
/
├── index.html                      # Main landing page
├── what-is-sensory-tracking.html   # SEO: informational intent
├── sensory-tracking-for-autism.html # SEO: autism-specific
├── sensory-tracking-for-adhd.html  # SEO: ADHD-specific
├── sensory-diet-tracker.html       # SEO: OT/therapy intent
├── share-sensory-data-therapist.html # SEO: collaboration intent
├── sitemap.xml                     # For Google indexing
├── robots.txt                      # Crawler directives
├── llms.txt                        # AI/LLM crawler info
├── CLAUDE.md                       # This file
└── vercel.json                     # Vercel config (URL rewrites)
```

## Development Workflow

### Local Development

```bash
# Start local server
python3 -m http.server 8085

# View at http://localhost:8085
```

### Git Workflow

```bash
# Feature development
git checkout -b feature/your-feature
# ... make changes ...
git add <specific-files>
git commit -m "Description of changes"
git push origin feature/your-feature

# Create PR on GitHub for review
# Merge to main triggers staging deploy
```

### Deployment Pipeline

```
local → push to GitHub → Vercel auto-deploys
                              ↓
                         Preview URL (staging)
                              ↓
                         Merge to main → Production
```

**Environments:**
- **Local:** `http://localhost:8085`
- **Staging:** Vercel preview deployments (auto-generated URLs on PRs)
- **Production:** `https://www.sensorytracker.com`

## Vercel Configuration

The `vercel.json` file handles:
- Clean URLs (no `.html` extension needed)
- Redirects
- Headers (caching, security)

## Design System

### Colors
```css
--sage-50: #f6f7f4    /* Background light */
--sage-100: #e8ebe3   /* Borders */
--sage-200: #d4dac9   /* Secondary borders */
--sage-400: #94a47d   /* Accent light */
--sage-500: #768a5e   /* Accent */
--sage-600: #5c6e49   /* Primary buttons */
--sage-700: #49573b   /* Hover states */
--warm-50: #fdfcfb    /* Page background */
--coral-400: #e8a598  /* Soft accent (used sparingly in hero) */
--text-primary: #2d3428
--text-secondary: #5a6152
--text-muted: #7d856f
```

### Typography
- **Display:** Fraunces (headings)
- **Body:** DM Sans (text)

### Design Principles
- Warm and calming (users may be sensory-sensitive)
- Professional enough for medical staff
- Not clinical - empathetic
- Coral used sparingly (diffused background blobs only)

## SEO Strategy

### Page Types
1. **Transactional** (index.html) - "sensory tracker app"
2. **Informational** (explainer pages) - "what is sensory tracking", "sensory diet tracker"

### Key Practices
- One H1 per page matching search intent
- Meta title < 60 chars, keyword at start
- Internal linking between all pages
- Citations for statistics (link to NIH/PMC sources)
- FAQ section on main page for content depth

### Target Keywords
- sensory tracker app
- sensory processing disorder app
- sensory tracking autism
- sensory tracking ADHD
- sensory diet tracker
- share sensory data therapist

## Content Guidelines

- **Statistics must be cited** - link to NIH/PMC/reputable sources
- **Tone:** Empathetic, empowering, not clinical
- **Audience awareness:** Parents are stressed; content should feel supportive
- **No fluff:** Every section should provide value

## Form Integration

Waitlist forms submit to Google Sheets via Apps Script webhook (shared with personal-portfolio project).

**Webhook:** Google Apps Script (same as portfolio)
**Format:** `application/x-www-form-urlencoded` with `mode: 'no-cors'`
**Fields:** `email`, `name`, `source`
**Source values:**
- `sensory-tracker-hero` - Hero section email form
- `sensory-tracker-waitlist` - Bottom CTA form

## Analytics

**Vercel Analytics** enabled on all pages via `/_vercel/insights/script.js`

**Events tracked:**
- `waitlist_signup` - Form submissions (with location data)
- `cta_click` - CTA button clicks

## SEO Files

- **robots.txt** - Allows all crawlers, points to sitemap
- **llms.txt** - Product summary for AI crawlers (emerging standard)
- **Schema.org JSON-LD** - On all pages:
  - index.html: Organization, WebSite, WebPage, FAQPage
  - Article pages: Article schema

**Submitted to:**
- Google Search Console
- Bing Webmaster Tools

## Commands Reference

```bash
# Local server
python3 -m http.server 8085

# Git
git status
git add <file>
git commit -m "message"
git push origin main

# Vercel CLI (if installed)
vercel dev          # Local dev with Vercel features
vercel              # Deploy preview
vercel --prod       # Deploy production
```
