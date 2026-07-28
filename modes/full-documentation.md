# Mode: Full Documentation

**Purpose**: Generate comprehensive, multi-section project documentation covering all aspects.

---

## Objective

The Full Documentation mode produces the most complete output possible. It combines the perspectives of Overview, Product, Architecture, Progress, and Infrastructure into a single, well-organized document. It answers the question: "Tell me everything important about this project." This mode is designed for onboarding new team members, creating project documentation sites, and producing reference materials.

This mode requires the highest token budget and is best paired with the `deep` analysis level. The output is long by design — it sacrifices conciseness for completeness. It is the mode to choose when the output will serve as a long-lived reference document rather than a quick summary.

---

## Analysis Scope

This mode inherits the full analysis scope of all other modes:

- **Overview**: Project identity, purpose, technology stack, module structure.
- **Product**: Problem statement, target users, value proposition, key features, user flows.
- **Architecture**: Pattern identification, module decomposition, dependency graph, data flow, API design.
- **Progress**: Completion assessment, test maturity, documentation score, technical debt, roadmap.
- **Infrastructure**: Build system, CI/CD, containerization, environment management, observability, security.

Additionally, this mode includes:
- **Getting Started**: Setup instructions, prerequisites, and first-run guidance.
- **Contributing Guide**: How to contribute, development workflow, and coding standards.
- **Glossary**: Project-specific terms and abbreviations.

---

## Expected Inputs

- A complete repository clone.
- The `deep` analysis level is strongly recommended for meaningful full documentation.
- README, CONTRIBUTING, and any existing documentation files are essential inputs.
- Package scripts, Makefile targets, or task runner configurations for the getting-started section.

---

## Expected Outputs

1. **Project Overview** — Identity, purpose, and high-level summary.
2. **Product Context** — Business domain, users, value proposition, and features.
3. **Architecture** — System design, modules, data flow, and technology decisions.
4. **Technology Stack** — Complete stack with versions and rationale.
5. **Module Reference** — Detailed description of each module with interfaces and dependencies.
6. **Development Guide** — Setup, building, testing, and development workflow.
7. **Infrastructure** — Deployment, CI/CD, monitoring, and operations.
8. **Project Status** — Implementation progress, test coverage, and documentation maturity.
9. **Roadmap and Risks** — Planned work, technical debt, and risk assessment.
10. **Glossary** — Project-specific terminology.

---

## Token Optimization Strategy

- Full Documentation is the one mode where completeness is prioritized over token efficiency.
- However, still avoid unnecessary verbosity — use structured formats where possible.
- Each section should be thorough but not redundant — do not repeat information across sections.
- Use cross-references ("see Architecture section") rather than restating information.
- If the analysis level is `standard`, the output will be less detailed but should still cover all sections.
- If the analysis level is `quick`, warn that full documentation is not achievable and suggest switching to overview mode.

---

## Recommended Template

`templates/project-overview.md` (extended with additional sections beyond the template's base structure)

---

## Recommended Combinations

| Audience | Purpose | Why It Works |
|----------|---------|--------------|
| Developer | Document | Produces comprehensive onboarding documentation. |
| Executive | Document | Complete reference for leadership and stakeholders. |
| Product Manager | Document | Full product and technical context in one document. |
| Client | Document | Client receives a thorough project briefing. |
| Recruiter | Pitch | Demonstrates depth of experience in portfolio. |