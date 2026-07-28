# Example: Deep + AI Context + AI Agent

This example demonstrates the most thorough context generation for an AI coding agent. The combination of Deep analysis level, AI Context mode, and AI Agent audience produces a dense, maximally informative document that gives an AI agent everything it needs to make precise code modifications.

---

## Prompt

```
Read the Code Atlas skill file at ./code-atlas/skill.md.

Analyze the project at /path/to/my-project with:
- Analysis level: deep
- Mode: ai-context
- Audience: ai-agent
- Purpose: understand

Save the output to ./code-atlas/outputs/my-project-ai-context.md
```

---

## Expected Output

Below is a representative output for this configuration. AI Context output is intentionally the most token-dense format.

---

```markdown
PROJECT: TaskFlow
PURPOSE: Task management platform with real-time collaboration, role-based access control, and webhook integrations.
STACK: TypeScript + NestJS + PostgreSQL + Redis
PATTERN: Modular monolith with event-driven inter-module communication.

## Directory Map

taskflow/
├── src/
│   ├── auth/              # JWT authentication, session management, API key handling
│   │   ├── auth.module.ts       # Module definition, providers, exports
│   │   ├── auth.service.ts      # Token generation, validation, password hashing
│   │   ├── auth.controller.ts   # POST /auth/login, /auth/register, /auth/refresh
│   │   ├── auth.guard.ts        # CanActivate guard for protected routes
│   │   ├── strategies/          # Passport.js JWT and API key strategies
│   │   └── dto/                 # LoginDto, RegisterDto, AuthResponseDto
│   ├── users/             # User profiles, roles, preferences
│   │   ├── users.module.ts
│   │   ├── users.service.ts     # CRUD, role assignment, profile updates
│   │   ├── users.controller.ts  # GET/PUT /users, /users/:id
│   │   └── dto/
│   ├── tasks/             # Task CRUD, assignment, status transitions
│   │   ├── tasks.module.ts
│   │   ├── tasks.service.ts     # Business logic, state machine for task status
│   │   ├── tasks.controller.ts  # REST endpoints
│   │   └── dto/
│   ├── projects/          # Project management, member management
│   │   ├── projects.module.ts
│   │   ├── projects.service.ts
│   │   └── projects.controller.ts
│   ├── webhooks/          # Outgoing webhook delivery
│   │   └── webhooks.module.ts
│   ├── events/            # Internal event bus (NestJS EventEmitter2)
│   │   └── events.module.ts
│   ├── common/            # Shared decorators, filters, guards, pipes
│   │   ├── decorators/
│   │   ├── filters/       # Global exception filter (HttpExceptionFilter)
│   │   ├── guards/        # RolesGuard (requires @Roles decorator)
│   │   └── pipes/
│   ├── prisma/            # Prisma client singleton module
│   │   └── prisma.module.ts
│   ├── config/            # ConfigModule setup (@nestjs/config)
│   │   └── configuration.ts
│   └── app.module.ts      # Root module, imports all modules
├── prisma/
│   ├── schema.prisma      # Full database schema
│   ├── migrations/        # SQL migration files
│   └── seed.ts            # Database seeder
├── test/                  # E2E tests (*.spec.ts)
├── .env.example
├── nest-cli.json
├── tsconfig.json
├── package.json
└── README.md

## Module Index

## auth (src/auth/)
Purpose: JWT-based authentication and role-based access control.
Key exports: AuthService, AuthGuard, JwtStrategy, ApiKeyStrategy, LoginDto, RegisterDto, AuthResponseDto
Depends on: users, prisma, config

## users (src/users/)
Purpose: User CRUD operations, role management, and profile handling.
Key exports: UsersService, UsersController, UpdateUserDto, UserResponseDto
Depends on: prisma, auth

## tasks (src/tasks/)
Purpose: Task lifecycle management with a state machine for status transitions.
Key exports: TasksService, TasksController, CreateTaskDto, UpdateTaskDto, TaskState
Depends on: prisma, users, projects, events

## projects (src/projects/)
Purpose: Project CRUD, member management, and project-level settings.
Key exports: ProjectsService, ProjectsController, CreateProjectDto, ProjectMemberDto
Depends on: prisma, users, events

## common (src/common/)
Purpose: Shared decorators, guards, filters, and pipes used across all modules.
Key exports: RolesGuard, Roles decorator, HttpExceptionFilter, ParseIntPipe
Depends on: auth, config

## Conventions

NAMING: PascalCase for classes and decorators, camelCase for functions and variables, UPPER_SNAKE_CASE for constants.
FILES: One class per file. Co-located DTOs in dto/ subdirectory. Controllers end in .controller.ts, services in .service.ts.
TESTS: E2E tests in test/ directory, named *.spec.ts. Unit tests co-located with source as *.spec.ts.
STYLES: No CSS framework — this is an API-only project.
STATE: Task state managed via a finite state machine in TasksService. Valid transitions: TODO->IN_PROGRESS->DONE, TODO->CANCELLED.
DATABASE: Prisma ORM with PostgreSQL. Schema defined in prisma/schema.prisma. Migrations via `npx prisma migrate dev`.
VALIDATION: All DTOs use class-validator decorators. ValidationPipe is globally enabled in main.ts.
ERRORS: All errors go through HttpExceptionFilter which normalizes responses to { statusCode, message, error }.

## Entry Points

ENTRY: src/main.ts — Bootstraps NestJS application, sets global prefix /api, enables CORS and validation pipes.
ROUTE: Requests arrive at src/main.ts, pass through global middleware (CORS, Logger, ValidationPipe), then to module-specific controllers.
FLOW: HTTP Request -> main.ts -> AuthGuard (if protected) -> Controller -> Service -> Prisma Client -> PostgreSQL

## Key Types

// src/tasks/tasks.service.ts
enum TaskState {
  TODO = 'TODO',
  IN_PROGRESS = 'IN_PROGRESS',
  DONE = 'DONE',
  CANCELLED = 'CANCELLED',
}

// src/common/decorators/roles.decorator.ts
decorator Roles(...roles: string[]): SetMetadata

// src/auth/dto/auth-response.dto.ts
class AuthResponseDto {
  access_token: string;
  refresh_token: string;
  user: UserResponseDto;
}

## Testing Guide

FRAMEWORK: Jest (unit), Supertest (e2e via @nestjs/testing)
RUN: npm test (unit), npm run test:e2e (e2e)
LOCATION: Unit tests co-located with source as *.spec.ts, e2e tests in test/ directory.
NAMING: {filename}.spec.ts. Test files mirror the structure of src/.

## Modification Guidelines

DO:
- Use class-validator decorators for all new DTOs.
- Apply @Roles() decorator on controller methods that require specific roles.
- Emit events via EventEmitter2 for cross-module communication (e.g., task created -> notify webhook module).
- Follow the existing Prisma service pattern: inject PrismaService, use prisma.{model}.{operation}().
- Create migration files for any schema changes: npx prisma migrate dev --name {descriptive-name}.

DON'T:
- Do not import between modules directly. Use events for cross-module communication.
- Do not add new global middleware without updating src/main.ts.
- Do not use raw SQL — always use Prisma's query builder.
- Do not skip validation pipes on new endpoints.
- Do not store secrets in .env files — use the ConfigModule pattern.
```

---

## When to Use This Combination

- Preparing context before an AI agent makes code changes.
- Generating a project context file for use across multiple AI sessions.
- Complex projects where the AI agent needs maximum context to avoid mistakes.
- Large-context models (128K+ tokens) where comprehensive context is affordable.

## Token Estimate

- Input: ~80,000-150,000 tokens
- Output: ~5,000-8,000 tokens
- Total: ~85,000-158,000 tokens