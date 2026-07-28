# Mode: Review

**Purpose**: Evaluate the project's quality, identify issues, and provide actionable recommendations.

---

## Objective

The Review mode performs a structured assessment of a project's code quality, architecture, and practices. It answers the question: "How good is this project, and what should be improved?" This mode is designed for code review sessions, technical due diligence, and quality audits.

Unlike a simple bug hunt, the Review mode provides a balanced assessment that acknowledges strengths alongside weaknesses. It categorizes findings by severity and provides actionable, prioritized recommendations. The output should enable a team to create a concrete improvement plan.

---

## Analysis Scope

- **Code Quality**: Naming conventions, code organization, function complexity, duplication, and readability.
- **Architecture Quality**: Module coupling, separation of concerns, pattern consistency, and scalability design.
- **Testing Quality**: Test coverage, test quality, testing patterns, and gap identification.
- **Documentation Quality**: Completeness, accuracy, and usefulness of documentation.
- **Security Practices**: Authentication, authorization, input validation, secrets handling, and dependency security.
- **Performance Signals**: N+1 query risks, missing indexes, memory leaks, caching opportunities.
- **Maintainability**: Code complexity, onboarding difficulty, and technical debt accumulation.
- **Best Practices Adherence**: Compliance with language and framework conventions and idioms.
- **Dependency Health**: Outdated dependencies, known vulnerabilities, and dependency management practices.

---

## Expected Inputs

- A repository with meaningful source code. This mode requires at least `standard` analysis level to be useful.
- Configuration files for linters, formatters, and type checkers — their presence and strictness reveal quality standards.
- Test files are critical — their presence, structure, and content reveal testing culture.
- CI/CD configuration reveals whether quality gates are automated.

---

## Expected Outputs

1. **Overall Assessment** — A letter grade or maturity level with a one-paragraph justification.
2. **Strengths** — 3-5 things the project does well.
3. **Critical Issues** — High-severity findings that should be addressed immediately (security vulnerabilities, data loss risks, critical bugs).
4. **Major Issues** — Significant problems that affect maintainability, performance, or reliability.
5. **Minor Issues** — Smaller problems, style inconsistencies, and improvement opportunities.
6. **Testing Assessment** — Specific evaluation of test quality and coverage.
7. **Documentation Assessment** — Specific evaluation of documentation completeness.
8. **Prioritized Recommendations** — Numbered, actionable improvement steps ordered by impact.
9. **Quick Wins** — Low-effort, high-impact improvements.

---

## Token Optimization Strategy

- Use severity categories to group findings rather than listing every individual issue.
- For each issue category, give 1-2 representative examples rather than an exhaustive catalog.
- Recommendations should be actionable one-liners, not lengthy explanations.
- Use a table format for the recommendations with columns: Priority, Finding, Recommendation, Effort.
- Skip positive findings if token budget is tight — focus on what needs to change.
- If analysis level is `quick`, output only sections 1, 3, and 8.

---

## Recommended Template

`templates/project-review.md`

---

## Recommended Combinations

| Audience | Purpose | Why It Works |
|----------|---------|--------------|
| Developer | Review | Engineer identifies improvement priorities for their work. |
| Product Manager | Review | PM evaluates technical quality against product expectations. |
| Executive | Review | Leadership gets a high-level quality assessment. |
| Developer | Improve | Review naturally leads to an improvement plan. |
| AI Agent | Improve | AI agent understands current quality before suggesting fixes. |