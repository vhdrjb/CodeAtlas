# Example: Quick + Overview + Developer

This example demonstrates the fastest way to get a technical summary of an unfamiliar project. The combination of Quick analysis level, Overview mode, and Developer audience produces a concise, scannable document that a developer can read in under a minute.

---

## Prompt

```
Read the Code Atlas skill file at ./code-atlas/skill.md.

Analyze the project at /path/to/my-project with:
- Analysis level: quick
- Mode: overview
- Audience: developer
- Purpose: understand

Save the output to ./code-atlas/outputs/my-project-quick-overview.md
```

---

## Expected Output

Below is a representative output for this configuration. The actual output will vary based on the target project.

---

```markdown
# MyProject

MIT | https://github.com/example/myproject

A task management API built with TypeScript and Express that provides RESTful endpoints for managing projects, tasks, and user assignments.

## Technology Stack

| Category | Technologies |
|----------|-------------|
| Languages | TypeScript |
| Frameworks | Express.js |
| Databases | PostgreSQL |
| Tooling | ESLint, Prettier, Jest |

## Architecture

Layered monolith following a controller-service-repository pattern. Controllers handle HTTP concerns, services contain business logic, and repositories manage database access.

**Pattern**: Monolith (layered)

## Modules

| Module | Path | Purpose | Status |
|--------|------|---------|--------|
| Auth | src/auth/ | JWT authentication and authorization | Implemented |
| Users | src/users/ | User management and profiles | Implemented |
| Projects | src/projects/ | CRUD operations for projects | Implemented |
| Tasks | src/tasks/ | Task lifecycle management | Partial |
| Notifications | src/notifications/ | Email and push notifications | Planned |

## Key Observations

- Uses class-based dependency injection via tsyringe for service instantiation.
- Authentication middleware is applied globally via Express middleware chain.
- PostgreSQL schema is managed through Knex.js migrations in `db/migrations/`.

## Analysis Confidence

- **Analysis Level**: quick
- **Files Inspected**: 8
- **Confidence**: medium
- **Timestamp**: 2026-07-28T12:00:00Z

This is a Quick-level analysis. For deeper understanding, use `standard` or `deep` analysis levels.
```

---

## When to Use This Combination

- Rapid triage of an unfamiliar repository before deciding whether to invest more time.
- Evaluating multiple repositories in a batch.
- Getting oriented before a small, targeted code change.
- Free-tier AI models with limited context windows.

## Token Estimate

- Input: ~8,000 tokens
- Output: ~800 tokens
- Total: ~8,800 tokens