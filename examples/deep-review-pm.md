# Example: Deep + Review + Product Manager

This example demonstrates a comprehensive quality review from a product management perspective. The combination of Deep analysis level, Review mode, and Product Manager audience provides a thorough assessment that connects code quality observations to product implications.

---

## Prompt

```
Read the Code Atlas skill file at ./code-atlas/skill.md.

Analyze the project at /path/to/my-project with:
- Analysis level: deep
- Mode: review
- Audience: product-manager
- Purpose: review

Save the output to ./code-atlas/outputs/my-project-review.md
```

---

## Expected Output

```markdown
# TaskFlow — Project Review

## Overall Assessment

**Grade**: B+

TaskFlow demonstrates solid engineering fundamentals with a clean modular architecture, consistent coding standards, and good test coverage for core features. The product is functionally capable with task management, user management, and authentication fully implemented. However, the notification system is incomplete, there is no frontend, and several product-critical features (search, reporting, real-time updates) are missing. The team appears to be a small, skilled group in active development.

## Strengths

1. **Clean Architecture**: The NestJS modular architecture is well-organized with clear separation between controllers, services, and data access. This supports independent feature development and testing.
2. **Authentication Security**: JWT implementation includes refresh token rotation, which is a security best practice that many projects skip. Evidence: `src/auth/auth.service.ts` lines 45-72.
3. **Type Safety**: Prisma schema provides strong typing across the entire data layer. All DTOs use class-validator for request validation, reducing runtime errors.
4. **Testing Culture**: Unit and e2e test infrastructure is established and actively used for core modules (auth, users, tasks).

## Critical Issues

None identified. The system handles authentication, authorization, and data persistence correctly based on the code review.

## Major Issues

| # | Issue | Evidence | Impact | Recommendation |
|---|-------|----------|--------|---------------|
| 1 | No frontend implementation | No HTML, CSS, or frontend framework files found | Product is API-only with no user interface, limiting usability for non-technical users | Plan a frontend development phase or position as a headless API |
| 2 | Notification module is a stub | `src/notifications/` contains only module definition with no service implementation | Users receive no notifications for task assignments, deadlines, or status changes | Prioritize notification implementation — it is critical for team collaboration |
| 3 | No search functionality | No search-related code in any module | Users cannot search for tasks or projects, which becomes painful as the system grows | Add full-text search on tasks (title, description) using PostgreSQL tsvector or an external service |
| 4 | No API rate limiting | Not configured in middleware or auth guard | The API is vulnerable to abuse and potential denial-of-service attacks | Add rate limiting middleware, especially on authentication endpoints |

## Minor Issues

- Missing API documentation (no Swagger/OpenAPI configuration found).
- No pagination on list endpoints — could cause performance issues at scale.
- No request logging middleware for production monitoring.
- The webhook module has no retry mechanism for failed deliveries.

## Testing Assessment

**Framework**: Jest (unit) + Supertest (e2e)
**Coverage**: Core modules (auth, users, tasks) have test files. Notification and webhook modules have none.
**Quality**: Tests cover happy paths and common error cases. No edge case tests observed.
**Gaps**: No tests for event-driven communication between modules. No load or performance tests.

## Recommendations

| Priority | Action | Effort | Impact |
|----------|--------|--------|--------|
| 1 | Implement notification service (email at minimum) | High | High — enables core collaboration use case |
| 2 | Add Swagger/OpenAPI documentation | Low | Medium — enables API adoption and testing |
| 3 | Implement pagination on all list endpoints | Medium | High — required for production use at scale |
| 4 | Add API rate limiting | Low | Medium — prevents abuse |
| 5 | Build or integrate a frontend | Very High | Very High — makes the product usable |
| 6 | Add search functionality | Medium | High — essential for larger deployments |

## Quick Wins

- Add `@nestjs/swagger` with decorators to auto-generate API documentation (1-2 hours).
- Add `@nestjs/throttler` for rate limiting (30 minutes).
- Add pagination to task and project list endpoints (2-3 hours).
```

---

## When to Use This Combination

- Product managers evaluating technical quality against product expectations.
- Preparing a quality report for stakeholders or investors.
- Identifying improvement priorities before the next development sprint.
- Due diligence when considering adopting or investing in a project.

## Token Estimate

- Input: ~80,000-120,000 tokens
- Output: ~4,000-6,000 tokens
- Total: ~84,000-126,000 tokens