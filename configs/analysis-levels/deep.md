# Analysis Level: Deep

**Optimized for**: Comprehensive documentation, large-context models, thorough audits.

---

## Objective

Provide the most thorough understanding of the project possible. This level inspects the entire repository, reads implementation details, and produces comprehensive documentation. It is designed for large-context models and situations where completeness matters more than token efficiency.

---

## Scanning Strategy

### Files to Inspect (All relevant files)

Inspect the entire repository systematically. There is no hard file limit — continue until the full picture is captured or the context window is exhausted.

**Phase 1 — Project Identity**

1. Package manifest and all dependency files.
2. All top-level documentation (README, CONTRIBUTING, CHANGELOG, CODE_OF_CONDUCT, etc.).
3. License file.
4. All configuration files at the project root.
5. CI/CD pipeline definitions.

**Phase 2 — Full Structure Mapping**

6. Complete directory tree (up to depth 4).
7. Every source directory's index or barrel file.
8. All routing definitions.
9. All database schemas, migrations, and seed files.
10. Infrastructure definitions (Dockerfiles, docker-compose, Kubernetes manifests, Terraform, etc.).

**Phase 3 — Implementation Review**

11. Every source file in core modules (read in full).
12. Every source file in secondary modules (read key exports and types).
13. All type definitions, interfaces, and schemas.
14. All API endpoint implementations.
15. All middleware, guards, interceptors, and decorators.
16. All utility and helper files.
17. All test files (structure, coverage patterns, key test cases).
18. All environment configuration and secrets management files.

**Phase 4 — Cross-cutting Concerns**

19. Error handling patterns across the codebase.
20. Logging configuration and patterns.
21. Security-related files and configurations.
22. Performance-related configurations (caching, CDN, etc.).
23. Any monorepo or workspace configurations.
24. Scripts defined in package manifests.

### Files to Skip

- Dependency lock files (unless analyzing dependency versions specifically).
- Generated build artifacts (`dist/`, `build/`, `.next/`, `__pycache__/`).
- Binary assets (images, fonts, compiled binaries) — note their existence but do not read them.
- `node_modules/`, `vendor/`, and other bundled dependencies.
- Very large auto-generated files (e.g., generated GraphQL types, OpenAPI specs) — read only headers/summaries.

---

## Knowledge Model Scope

At the Deep level, **all fields** in the knowledge model should be fully populated:

- Every field under Identity, Purpose, Product, Architecture, and Implementation Status.
- Full `technology_stack` with version numbers where available.
- Complete `major_modules` list with detailed descriptions and inter-module dependencies.
- Thorough `known_constraints`, `technical_debt`, and `risks` sections.
- All `assumptions` explicitly listed with rationale.
- Full `inferred` section with evidence citations.

Additionally, the Deep level should capture:

- **Inter-module dependencies**: Which modules depend on which.
- **Data flow**: How data moves through the system.
- **Error handling patterns**: Consistency and coverage.
- **Testing patterns**: Test strategy, coverage, and quality signals.
- **Code quality signals**: Linting rules, type strictness, naming conventions.

---

## Token Budget

| Dimension         | Estimate          |
|-------------------|-------------------|
| Files to read     | All relevant      |
| Input tokens      | 50,000 - 200,000+ |
| Output tokens     | 5,000 - 20,000+   |
| Directories depth | 3 - 4             |

> **Note**: Deep analysis may exceed the context window of smaller models. Ensure your model supports the expected token count before selecting this level.

---

## Output Guidelines

- Use full paragraphs with detailed explanations.
- Each module description should be a full paragraph (4-6 sentences) covering purpose, implementation approach, dependencies, and current state.
- Include comprehensive technology stack details with versions.
- Include a complete module dependency diagram (textual).
- Provide detailed implementation status with evidence.
- Include a thorough risks and technical debt assessment.
- Cite specific files and line numbers as evidence for claims.
- Separate observed facts from inferences with clear markers.
- Include a detailed confidence assessment per section.
- Provide actionable recommendations when in `review` or `improve` purpose.

---

## When to Use Deep

- Large-context models (200k+ tokens) where completeness is valuable.
- Preparing comprehensive project documentation for onboarding.
- Conducting thorough code reviews or audits.
- Generating LLM context files for complex projects.
- Due diligence evaluations (acquisition, investment, partnership).
- Creating reference documentation that will be used over a long period.
- Situations where missing a detail could have significant consequences.