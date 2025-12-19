# Quantum Media Group — Internal Media Catalog

A cross-platform (Web + Mobile) internal catalog application for **Quantum Media Group** used to organize, search, and manage media assets including audio, video, images, lyrics, prompts, and project deliverables.

This application serves as the internal “media brain” for QMG — enabling structured asset management, tiered access, and accessibility-first interaction across devices.

---

## Core Goals

- Centralized catalog for all QMG media and creative assets
- Cross-platform support (Web, iOS, Android)
- Tiered user access (Admin, Creator, Collaborator, Client, Viewer)
- Accessibility-first design (WCAG-aligned where applicable)
- Fast iteration and low-friction onboarding
- Scalable architecture that can evolve into client-facing tools

---

## Tech Stack

### Frontend
- React Native (Expo) – Mobile (iOS / Android)
- Next.js – Web
- Shared component system (monorepo)
- Accessibility-aware UI primitives

### Backend
- Convex – Typed backend, realtime data, file handling
- Clerk – Authentication, user management, roles

### Infrastructure
- Docker + Docker Compose – Local development environment
- Turborepo-style monorepo layout
- S3-compatible object storage (planned / optional)

---

## Repository Structure

```
qmg-catalog/
├─ apps/
│  ├─ web/          # Next.js web application
│  └─ expo/         # React Native (Expo) mobile app
├─ convex/          # Convex backend functions & schema
├─ docker/
│  ├─ web/          # Web Dockerfile
│  ├─ expo/         # Expo Dockerfile
│  └─ convex/       # Convex Dockerfile
├─ docker-compose.yml
├─ .gitignore
└─ README.md
```

---

## User Roles

- ADMIN – Full access, user and asset management
- CREATOR – Upload, edit, manage internal assets
- COLLABORATOR – Limited contribution access
- CLIENT – Read-only access to assigned assets
- VIEWER – Public or restricted viewing access

Roles are managed via Clerk public metadata and enforced at both UI and backend levels.

---

## Accessibility

Accessibility is a first-class requirement.

### Web
- Semantic HTML
- Keyboard navigation
- Visible focus indicators
- Screen reader-friendly labels

### Mobile
- Proper accessibility roles and labels
- Logical reading order
- Scalable text support
- Large, accessible touch targets

All shared UI components are designed to be accessible by default.

---

## Local Development (Docker)

### Prerequisites
- Docker
- Docker Compose

### Start the Environment

```
docker compose up --build
```

Services:
- Web: http://localhost:3000
- Expo Dev Server: http://localhost:19000
- Convex Backend: http://localhost:3210

---

## Environment Variables

Create a `.env` file at the project root:

```
CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=
CONVEX_DEPLOYMENT=
CONVEX_URL=
```

Commit a `.env.example` file for onboarding.

---

## Asset Model (Conceptual)

All media is treated as a unified Asset with typed metadata:
- Audio
- Video
- Images
- Lyrics
- Prompts
- Documents

Assets can be tagged, grouped into projects, versioned, and permissioned by role.

---

## Roadmap

### Phase 1
- Auth + roles
- Asset upload & catalog
- Tagging and search
- Tier-based visibility

### Phase 2
- Project collections
- Asset versioning
- Notes and internal metadata
- Client share links

### Phase 3
- AI-assisted tagging and metadata
- Transcripts / lyrics linking
- External client access
- Optional NestJS microservices

---

## Philosophy

This project prioritizes:
- Clarity over complexity
- Accessibility over shortcuts
- Speed without sacrificing structure
- Systems that scale with creative output

The goal is not just to store media — but to enable creative flow across Quantum Media Group.

---

## License

Private / Internal — Quantum Media Group, LLC  
All rights reserved.
