# VideoQrd - Agent Guide

## Project Overview

VideoQrd lets users create QR codes that link to videos (YouTube/Vimeo). Users can download QR codes to embed in photos, print for scrapbooks, or share physically.

## Tech Stack

- **Frontend:** React + TypeScript
- **Backend:** .NET API with Carter
- **Database:** PostgreSQL + EF Core
- **Auth:** JWT + Google OAuth
- **Orchestration:** .NET Aspire
- **QR:** QRCoder

## Prerequisites

- .NET 10 SDK
- Node.js 20+
- PostgreSQL (local or container)

## Getting Started

### Build
```bash
dotnet build
```

### Run Locally
```bash
dotnet run --project src/VideoQrd.AppHost
```

### Database Migrations
```bash
dotnet ef migrations add <name> --project src/VideoQrd.Api
dotnet ef database update --project src/VideoQrd.Api
```

### Tests
```bash
dotnet test
```

### Frontend Dev
```bash
cd src/VideoQrd.Web
npm install
npm run dev
```

## Environment Variables

See `.env.example` for required variables.

## Architecture

See `docs/PRD.md` for full product details.
See `docs/BUILD-PLAN.md` for build phases.
