VideoQrd Build Plan

# VideoQrd - Build Plan

## Approach

Build in phases. Each phase delivers something usable. No big bang releases.

---

## Phase 0: Setup (Week 1)

### Goals
- Repo created, local dev environment working
- Solution builds locally
- Database schema designed

### Tasks

- [ ] Create GitHub repo (private)
- [ ] Scaffold .NET solution with Aspire
- [ ] Set up PostgreSQL database
- [ ] Configure GitHub Actions CI (build + test)
- [ ] Verify solution builds locally
- [ ] Verify CI passes

### Definition of Done
- `dotnet run` starts the app locally
- CI shows green checkmark on GitHub

---

## Phase 1: Auth (Week 2)

### Goals
- Users can register and log in

### Tasks

- [ ] Implement user registration (email/password)
- [ ] Implement user login (JWT)
- [ ] Add Google OAuth
- [ ] Create user dashboard page

### Definition of Done
- New user can sign up
- User can log in
- Dashboard shows "Welcome, [Name]"

---

## Phase 2: VideoQrd CRUD (Week 3)

### Goals
- Users can create, view, edit, delete VideoQrds

### Tasks

- [ ] Design VideoQrd database schema
- [ ] Create API endpoints (CRUD)
- [ ] Build "Create VideoQrd" form (paste URL)
- [ ] Build dashboard list view
- [ ] Add edit/delete functionality

### Schema Idea
```
Users
- Id (GUID)
- Email
- PasswordHash
- Name
- GoogleId (nullable)
- CreatedAt

VideoQrds
- Id (GUID)
- UserId (FK)
- Name
- VideoUrl
- VideoType (YouTube/Vimeo)
- VideoId
- Slug (unique)
- CreatedAt
- UpdatedAt
```

### Definition of Done
- User can create a VideoQrd with a YouTube URL
- User sees list of their VideoQrds
- User can edit name, delete VideoQrds

---

## Phase 3: Landing Page (Week 4)

### Goals
- Public landing page at videoqrd.com/{slug} shows the video

### Tasks

- [ ] Create public landing page route
- [ ] Embed YouTube/Vimeo player
- [ ] Extract video title automatically
- [ ] Handle invalid/removed videos gracefully

### Definition of Done
- Visiting videoqrd.com/vc/abc123 shows the video
- Invalid slug shows "Not Found"

---

## Phase 4: QR Generation (Week 5)

### Goals
- User can download QR code linking to their VideoQrd

### Tasks

- [ ] Integrate QR code library
- [ ] Generate QR pointing to landing page
- [ ] Allow basic customization (color)
- [ ] Add download button (PNG)

### Definition of Done
- User clicks "Get QR" and downloads a PNG
- QR scans and goes to correct landing page

---

## Phase 5: Polish & Launch (Week 6)

### Goals
- MVP ready for real users

### Tasks

- [ ] Add proper error handling
- [ ] Add loading states
- [ ] Make it look decent (CSS/styling)
- [ ] Write README
- [ ] Deploy to production (Azure/Railway)
- [ ] Buy domain (videoqrd.com)

### Definition of Done
- You can sign up, create a VideoQrd, get QR, and it works in production

---

## Post-MVP (Future)

- YouTube upload via API
- Custom QR styles (logos, shapes)
- Analytics
- Subscriptions + payments
- White-label

---

## Tech Stack Summary

| Component | Technology |
|-----------|------------|
| Frontend | React + TypeScript + Vite |
| Backend | .NET API + Carter |
| Database | PostgreSQL + EF Core |
| Auth | JWT + Google OAuth |
| QR | QRCoder (.NET) |
| Orchestration | .NET Aspire |
| CI/CD | GitHub Actions |
| Hosting | Azure / Railway |

---

## Key Principles

1. **Ship often** — Every phase should produce something usable
2. **No scope creep** — Stay focused on MVP features
3. **Tests** — Add tests as you go, not after
4. **Automate** — CI should catch issues early
5. **Document** — README and comments as you build

---

**Last Updated:** $(date +%Y-%m-%d)

