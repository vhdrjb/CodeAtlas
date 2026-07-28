# Example: Standard + Full Documentation + Executive

This example demonstrates generating a comprehensive yet executive-friendly project document. The combination of Standard analysis level, Full Documentation mode, and Executive audience produces a complete overview that a senior leader can use for strategic decision-making without drowning in technical details.

---

## Prompt

```
Read the Code Atlas skill file at ./code-atlas/skill.md.

Analyze the project at /path/to/my-project with:
- Analysis level: standard
- Mode: full-documentation
- Audience: executive
- Purpose: document

Save the output to ./code-atlas/outputs/my-project-executive-brief.md
```

---

## Expected Output

```markdown
# TaskFlow — Executive Brief

**Date**: 2026-07-28  **Analysis Level**: Standard  **Confidence**: Medium-High

---

## Project Overview

TaskFlow is a collaborative task management platform designed to help teams organize, track, and complete their work through project-based workspaces. The system provides role-based access control, automated workflows, and third-party integrations via webhooks. It is built as a modular backend API, currently without a user interface.

## Product Context

### Business Domain

TaskFlow operates in the **team productivity and project management** space. It competes with tools like Trello, Asana, and Linear, targeting teams that need a simple, self-hostable task management solution.

### Target Users

- **Primary**: Small to mid-size development teams (5-50 members) who want a self-hosted, customizable task management tool.
- **Secondary**: Organizations with compliance requirements that prevent using cloud-based project management tools.

### Key Features

1. **Project Management**: Create and organize work into projects with member management.
2. **Task Lifecycle**: Track tasks from creation through completion with enforced status transitions.
3. **Team Roles**: Three-tier role system (admin, manager, member) controlling access and permissions.
4. **Secure Authentication**: JWT-based login with refresh tokens and optional API key authentication.
5. **Webhook Integration**: Automated notifications to external systems when events occur.

## Architecture

TaskFlow uses a **modular monolith** architecture. The system is built with NestJS, a TypeScript framework that enforces a modular structure. Each business domain (users, tasks, projects, authentication) is an independent module with its own controller, service, and data access layer. Modules communicate through an internal event system, which keeps them loosely coupled.

This architecture supports the current team size and expected growth. It can be deployed as a single service and scaled vertically. If the product requires horizontal scaling in the future, the modular structure would support extracting modules into separate microservices.

## Technology Stack

| Technology | Business Purpose |
|-----------|-----------------|
| TypeScript + NestJS | Modern, type-safe development that reduces bugs and speeds up delivery |
| PostgreSQL | Reliable, proven database for structured task and user data |
| Redis | Fast session management and potential caching for improved performance |
| Docker | Consistent deployment across environments, simplified operations |
| Prisma ORM | Type-safe database access that catches errors at development time |

## Project Status

**Phase**: Late Beta / Early Production

### Completed
- User authentication with JWT and refresh token rotation
- Role-based access control (3 roles)
- Full task CRUD with status state machine
- Project management with member assignment
- API key authentication for integrations
- Database schema and migration system
- Docker-based deployment
- Test infrastructure (unit and e2e)

### In Progress
- Notification system (module created, service not implemented)
- Webhook delivery (basic structure exists, retry mechanism missing)

### Planned
- Frontend user interface
- Task search functionality
- API documentation (Swagger/OpenAPI)
- Rate limiting
- Reporting and analytics

## Risks and Recommendations

| Risk | Impact | Recommended Action |
|------|--------|-------------------|
| No user interface limits adoption | High | Prioritize frontend development in the next phase |
| Notification gaps reduce collaboration value | High | Complete the notification service before promoting to production |
| No search capability at scale | Medium | Plan search implementation for the next release |
| Missing API documentation slows integration | Medium | Add Swagger documentation as a quick win |
```

---

## When to Use This Combination

- Preparing a board-level update or investor briefing.
- Creating an executive summary for a project handoff or acquisition evaluation.
- Giving senior leadership a complete but accessible picture of a project.
- Onboarding an executive sponsor to a technical project.

## Token Estimate

- Input: ~25,000-40,000 tokens
- Output: ~3,000-4,500 tokens
- Total: ~28,000-45,000 tokens
