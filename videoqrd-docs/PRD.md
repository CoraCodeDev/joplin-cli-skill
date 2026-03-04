VideoQrd PRD

# VideoQrd - Product Requirements Document

## Project Overview

**Project Name:** VideoQrd  
**Type:** Web Application  
**Summary:** A platform where users register, paste a YouTube/Vimeo URL (or upload directly), and receive a stylized QR code linking to their video. QR codes can be embedded into images or printed for physical use.  
**Target Users:** Crafters, scrapbookers, families, plus businesses (weddings, events, retail)

---

## Problem Statement

- QR codes are utilitarian and ugly
- Video content is digital-only and hard to share physically
- People want to combine digital memories with physical keepsakes
- Existing QR code generators lack customization and don't handle video-to-QR workflows

---

## Solution (MVP)

A web app where:
1. User registers (email or Google OAuth)
2. User creates a "VideoQrd" by:
   - Pasting a YouTube/Vimeo URL, OR
   - Uploading a video (goes to their YouTube via our platform)
3. System creates a **private** landing page at videoqrd.com/{slug} that embeds the video
4. User downloads a QR code pointing to their landing page
5. Only people with the QR code/link can view the video — not searchable, not indexed

---

## Authentication

| Method | Description |
|--------|-------------|
| **Email/Password** | Traditional registration |
| **Google OAuth** | Sign in with Google + optional YouTube upload |

---

## Video Input Options

### Option 1: Paste URL
- User pastes existing YouTube/Vimeo URL

### Option 2: Upload to YouTube
- User uploads video within VideoQrd
- System uploads to their YouTube channel via YouTube Data API

---

## Core Features

### 1. User Authentication
- Email/password + Google OAuth

### 2. Dashboard / VideoQrd Management
- Create, edit, list, delete VideoQrds

### 3. Video Input
- Paste YouTube/Vimeo URL
- Upload to YouTube (with OAuth)

### 4. Landing Page (videoqrd.com/{slug})
- Embedded video player
- Video title
- "Video unavailable" fallback

### 5. QR Code Generation
- Link to landing page
- Basic customization
- Download as PNG

---

## Monetization

### Tiered Subscription

| Tier | Price | Features |
|------|-------|----------|
| **Free** | $0 | 3 VideoQrds, basic QR styles, VideoQrd branding |
| **Pro** | $9.99/mo | Unlimited VideoQrds, custom colors, no branding |
| **Business** | $49/mo | Analytics, password protection, custom slug |

### White-Label / Enterprise

This is where it gets interesting. Businesses pay for branded VideoQrd on their own domain.

| Package | Price | Features |
|---------|-------|----------|
| **Starter** | $99/mo | Custom domain, no branding, 5 users |
| **Professional** | $299/mo | Custom domain, API, 20 users, priority support |
| **Enterprise** | Custom | Unlimited everything, dedicated support, SLA |

**Who pays for white-label?**
- Wedding photographers — QR codes in photo albums
- Event planners — QR on programs linking to highlight reels  
- Family historians — QR codes on printed photo books
- Real estate — QR on "sold" signs linking to tours
- Restaurants — QR codes on tables linking to menu videos
- Retail — Product videos on packaging

**White-label features:**
- Custom domain (`qr.yourbusiness.com`)
- Your logo on landing pages
- Your branding/colors
- Bulk creation tools
- API access
- No "Made with VideoQrd" footer

---

## Revenue Projections (Hypothetical)

| Scenario | Year 1 |
|----------|--------|
| 1,000 free users → 5% convert to Pro | $6,000/yr |
| 10 businesses on Starter | $12,000/yr |
| 3 enterprises | $30,000/yr |
| **Total** | **~$48,000/yr** |

Not huge, but it's a SaaS. Add more tiers and pricing as you learn.

---

## Future Features

- Video file uploads (direct to R2/S3)
- Full QR customization (styles, logos)
- Analytics (scan counts, locations)
- Password protection
- Link expiry
- Bulk creation
- Print templates

---

## Phases

### Phase 1 (MVP)
- User auth (email + Google OAuth)
- YouTube/Vimeo URL paste
- Simple landing page
- Basic QR generation

### Phase 2
- YouTube upload via API
- Custom QR colors
- Analytics

### Phase 3
- Subscriptions + payments
- White-label

---

**Document Status:** Draft  
**Owner:** Dave

