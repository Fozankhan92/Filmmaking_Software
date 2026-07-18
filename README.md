# Filmmaking Software

## One complete workspace for every stage of filmmaking

Filmmaking Software is an all-in-one production platform built to support filmmakers from the initial idea through final delivery. It brings the planning, creative development, production management, documentation, and delivery workflow into one organized system.

Built for filmmakers by filmmakers, the goal is simple: make the entire filmmaking process clearer, more connected, and easier to manage.

## What it covers

- Initial ideas, concepts, and project development
- Scriptwriting and screenplay development
- Storyboards and shot planning
- Mood boards and visual references
- Budgeting and financial planning
- Scheduling and production calendars
- Call sheets and crew coordination
- Audit logs and production records
- Camera sheets and camera reports
- Audio sheets and sound records
- Editing sheets and post-production tracking
- Final deliverables and delivery documentation

The platform is designed to keep every stage connected so that creative decisions, production details, and final delivery requirements remain accessible throughout the life of a project.

## Editing and audio tools

The initial version does not include built-in video editing or audio editing tools. Instead, it is designed to work alongside the professional tools filmmakers already use, including:

- DaVinci Resolve
- Adobe Premiere Pro
- Adobe After Effects
- Final Cut Pro
- Avid Media Composer
- Logic Pro
- Pro Tools
- GarageBand
- Adobe Audition

The software focuses on the workflow surrounding editing and audio post-production: preparation, organization, documentation, tracking, approvals, and final deliverables. Media can continue to be edited in the external applications best suited to each project.

## MCP server layer

The platform will include an MCP server layer, creating a structured foundation for connecting filmmaking workflows, project data, and future tools. AI tools are not included yet, but future versions may introduce AI-assisted capabilities where they genuinely help filmmakers.

Future versions are also planned to support a growing ecosystem of connectors and plugins, allowing the platform to work with the services and tools production teams already rely on.

## Architecture

The project architecture is documented in [Filmmaking OS — Final Architecture V1](Filmmaking_OS_Final_Architecture_V1.md). This document is included as part of the project and describes the planned system structure, technology stack, modules, services, data model, and implementation direction.

## Our vision

Filmmaking is a collaborative journey with many moving parts. This project aims to bring those parts together in a practical, filmmaker-first environment—from the first spark of an idea to the final exported deliverable.

Let’s revolutionize the filmmaking workflow.

## Support the project

If you believe in a better filmmaking workflow, you can support the project through donations. Donation options will be added as the project develops.

## Status

This project is in active development.

## Final architecture (V1)

The following architecture is part of this README and describes the planned Filmmaking Operating System. The original architecture document remains unchanged in the repository at [`Filmmaking_OS_Final_Architecture_V1.md`](Filmmaking_OS_Final_Architecture_V1.md).

### Vision

A modern, modular, web-based Filmmaking Operating System managing the complete filmmaking lifecycle from idea to delivery.

### Technology stack

- Frontend: React 19, Next.js App Router, TypeScript, Tailwind CSS, shadcn/ui, Radix UI, Motion, TanStack Query, React Hook Form, and Zod
- Backend: Node.js, Express.js, TypeScript, REST API, MCP Server, service layer, and repository pattern
- Database and ORM: PostgreSQL and Prisma
- Authentication: Better Auth with organizations, teams, users, roles and permissions, sessions, and invitations
- Storage: Local Storage, MinIO, AWS S3, or Cloudflare R2 through a storage adapter
- Search: PostgreSQL full-text search, with Meilisearch planned for the future
- Background jobs: Inngest
- Documentation: Storybook and OpenAPI / Swagger
- Testing: Vitest and Playwright
- Version control: Git and GitHub
- Deployment: Docker, PM2, and Nginx on a customer server
- Realtime collaboration: Liveblocks or Socket.IO in a future version

### System architecture

```text
GitHub Repository
        │
        ▼
Frontend (React + Next.js)
        │
 REST API / MCP
        │
        ▼
Backend (Node.js + Express)
        │
 ├── Core
 ├── Modules
 ├── Services
 ├── MCP Server
 └── Prisma
        │
        ▼
PostgreSQL
        │
        ▼
Storage (Local / MinIO / S3 / R2)
```

### Core entities

Organizations, teams, users, projects, scenes, characters, locations, assets, files, tasks, calendar, notes, comments, activity, notifications, reports, tags, and custom fields.

### Navigation

Dashboard, Projects, Development, Pre-Production, Production, Post-Production, Delivery, Files, Calendar, Reports, Automation, MCP, and Settings.

### Milestones

1. Development: idea development, story development, character management, world building, and screenwriting.
2. Pre-Production: script breakdown, budget, scheduling, crew, casting, locations, equipment, shot planning, and call sheets.
3. Production: dashboard, daily reports, camera reports, sound reports, continuity, shot tracking, attendance, and incident reports.
4. Post-Production: asset management, reviews, VFX tracking, subtitle management, QC, and deliverables.
5. Delivery: distribution, festivals, marketing, rights management, and archive.

### Shared features

Files, tasks, notes, comments, mentions, calendar, notifications, activity feed, search, reports, dashboards, templates, version history, tags, custom fields, import/export, and audit logs.

### MCP layer

MCP resources will include projects, scenes, characters, assets, files, tasks, budgets, schedules, and reports. Planned tools include Create Scene, Update Scene, Create Character, Create Budget Item, Generate Call Sheet, Search Assets, and Generate Reports. Planned prompts include Screenplay Review, Story Analysis, Budget Analysis, Schedule Review, and Production Summary.

### Project flow

```text
Project → Development → Pre-Production → Production → Post-Production → Delivery
```

Example workflow:

```text
Scene 12 → Breakdown → Budget → Schedule → Shot List → Production Reports
         → VFX Tracking → Review → Delivery
```
