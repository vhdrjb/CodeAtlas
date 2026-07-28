# Example: Standard + Resume + Recruiter

This example demonstrates how to generate resume-ready descriptions from a project analysis. The combination of Standard analysis level, Resume mode, and Recruiter audience produces polished, achievement-oriented content optimized for applicant tracking systems.

---

## Prompt

```
Read the Code Atlas skill file at ./code-atlas/skill.md.

Analyze the project at /path/to/my-project with:
- Analysis level: standard
- Mode: resume
- Audience: recruiter
- Purpose: pitch

Save the output to ./code-atlas/outputs/my-project-resume.md
```

---

## Expected Output

```markdown
# Resume Description — TaskFlow

## One-Liner

Built a full-stack task management platform using TypeScript, NestJS, and PostgreSQL, supporting real-time collaboration for teams of up to 500 users.

## Short Description

TaskFlow is a collaborative task management platform that enables teams to organize, track, and complete work through an intuitive project-based interface. The system supports role-based access control, webhook integrations, and real-time notifications. Built with TypeScript on a NestJS backend, PostgreSQL for persistent storage, and Redis for session management and caching.

## Bullet Points

- **Architected a modular monolith** using NestJS with dependency injection, event-driven inter-module communication, and Prisma ORM, supporting 6 independent modules and 40+ RESTful endpoints.
- **Implemented JWT authentication** with refresh token rotation, role-based access control (admin, manager, member), and API key authentication for third-party integrations.
- **Designed a task state machine** enforcing valid status transitions (TODO -> IN_PROGRESS -> DONE) with automated webhook delivery on state changes.
- **Established testing infrastructure** with Jest unit tests and Supertest e2e tests, achieving coverage across all service and controller layers.
- **Deployed with Docker** and docker-compose, including automated database migrations via Prisma and environment-based configuration management.

## Technical Keywords

TypeScript, NestJS, PostgreSQL, Prisma ORM, Redis, Docker, REST API, JWT, Passport.js, Jest, Supertest, ESLint, Prettier, Event-Driven Architecture, Dependency Injection

## Scale and Impact

**Scale**: 6 modules, 40+ API endpoints, 15 database tables, role-based access for 3 user roles.
**Impact**: Enables teams to manage projects and tasks with automated workflows and third-party integrations.

## Long Description

TaskFlow is a production-ready task management platform I designed and built from the ground up to demonstrate modern backend architecture patterns. The system uses NestJS's modular architecture with dependency injection, implementing a clean separation between controllers (HTTP layer), services (business logic), and data access (Prisma ORM). I implemented JWT-based authentication with refresh token rotation and role-based access control supporting three user levels. A key technical achievement is the event-driven communication between modules using NestJS's EventEmitter2, which allows the webhook module to react to task state changes without tight coupling. The project follows comprehensive testing practices with both unit and end-to-end tests, and is containerized with Docker for consistent deployment across environments.
```

---

## When to Use This Combination

- Writing or updating a resume with project descriptions.
- Preparing LinkedIn profile content.
- Generating portfolio descriptions for job applications.
- Creating content for a personal website or portfolio page.

## Token Estimate

- Input: ~25,000-40,000 tokens
- Output: ~1,500-2,500 tokens
- Total: ~27,000-43,000 tokens