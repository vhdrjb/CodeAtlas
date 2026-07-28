# Mode: Progress

**Purpose**: Assess the current implementation status and project trajectory.

---

## Objective

The Progress mode evaluates how far a project has come and where it appears to be heading. It answers the question: "What is the current state of this project, and what comes next?" This mode is valuable for onboarding, project handoffs, stakeholder updates, and investment due diligence.

Rather than simply listing what exists, this mode synthesizes evidence from the codebase — commit patterns, TODO comments, placeholder implementations, test coverage, and documentation completeness — into a coherent assessment of project health and momentum. It distinguishes between what is genuinely complete and what merely appears functional.

---

## Analysis Scope

- **Completion Assessment**: Which features and modules are fully implemented, partially implemented, or scaffolded but empty — determined by inspecting actual implementation versus declared intent.
- **Test Coverage**: The presence and quality of tests — directory structure, test file naming conventions, coverage tooling, and observed test density.
- **Documentation Maturity**: How complete and current the documentation is — README depth, API docs, inline comments, and contributing guides.
- **Roadmap Signals**: Evidence of planned work — TODO/FIXME/HACK comments, open issue references, roadmap files, milestone markers in version control.
- **Technical Debt Indicators**: Signs of rushed or deprecated code — disabled tests, commented-out code, deprecated API usage, workaround comments.
- **Development Velocity**: Inferred from commit history if available — frequency, size, and distribution of recent commits.
- **Stability Signals**: Presence of CI/CD, versioning strategy, release tags, and dependency update patterns.
- **Blockers and Risks**: Anything that could impede progress — external dependencies, missing documentation, test failures, configuration issues.

---

## Expected Inputs

- A repository with meaningful history (commits, branches, tags). Shallow clones or snapshot-only views limit this mode's effectiveness.
- Test directories are particularly important — their structure and content reveal testing culture.
- Look for project management artifacts: CHANGELOG, ROADMAP, .github/ project boards, milestone references.

---

## Expected Outputs

1. **Current Phase** — Assessment of where the project is in its lifecycle (MVP, beta, production, maintenance).
2. **Completion by Module** — Table showing each major module and its completion status.
3. **Feature Status** — Detailed list of features: complete, in-progress, planned, and missing.
4. **Test Maturity** — Assessment of testing practices and coverage quality.
5. **Documentation Score** — Evaluation of documentation completeness across categories.
6. **Identified Roadmap** — What appears to be planned next, based on code evidence.
7. **Technical Debt** — List of observed technical debt items with severity estimates.
8. **Risks and Blockers** — Potential obstacles to continued progress.
9. **Momentum Assessment** — Is the project active, slowing, or stalled?

---

## Token Optimization Strategy

- Use a status table for modules and features rather than verbose descriptions.
- Cite specific evidence for status claims (file names, comment contents) to keep assertions verifiable without long explanations.
- Group technical debt items by severity (high, medium, low) rather than describing each in depth.
- Limit roadmap items to those with direct code evidence — do not speculate extensively.
- If analysis level is `quick`, output only sections 1, 2, and 8.

---

## Recommended Template

`templates/roadmap.md`

---

## Recommended Combinations

| Audience | Purpose | Why It Works |
|----------|---------|--------------|
| Developer | Understand | New team member quickly learns what is built and what is not. |
| Product Manager | Review | PM assesses whether the product is on track. |
| Executive | Document | Leadership gets a progress snapshot without technical details. |
| Recruiter | Pitch | Candidate sees project maturity and growth potential. |
| Investor | Pitch | Investor evaluates execution velocity and runway. |