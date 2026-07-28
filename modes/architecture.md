# Mode: Architecture

**Purpose**: Analyze and document the technical architecture of a project.

---

## Objective

The Architecture mode provides a deep technical analysis of how a software project is structured and why it is structured that way. It answers the question: "How is this system designed, and what are the key engineering decisions?" This mode is intended for audiences who need to understand the technical foundation — either to maintain, extend, or evaluate the project.

Architecture analysis goes beyond listing technologies. It identifies patterns, maps dependencies between modules, traces data flows, and evaluates the consistency of the design. The output should enable an experienced engineer to form a mental model of the system and anticipate where changes would propagate.

---

## Analysis Scope

- **Architecture Pattern**: Whether the system follows monolithic, microservices, event-driven, layered, hexagonal, or other architectural patterns — identified from directory structure, configuration, and module boundaries.
- **Module Decomposition**: How the codebase is divided into modules, the responsibility of each, and the interfaces between them.
- **Dependency Graph**: Which modules depend on which others, both at the code level (imports) and at the infrastructure level (shared databases, services).
- **Data Flow**: How data enters the system, is transformed, stored, and returned — traced from entry points through business logic to persistence.
- **Technology Decisions**: Not just what technologies are used, but why they appear to have been chosen (inferred from usage patterns).
- **API Design**: How the system exposes functionality — REST, GraphQL, gRPC, CLI, SDK — and the design conventions followed.
- **State Management**: How application state is handled — client-side, server-side, database-backed, cache layers.
- **Scalability Approach**: How the architecture supports (or limits) horizontal/vertical scaling, load balancing, and fault tolerance.
- **Cross-Cutting Concerns**: How authentication, logging, error handling, and configuration are implemented across modules.

---

## Expected Inputs

- A repository with meaningful source code structure. This mode benefits most from `standard` or `deep` analysis levels.
- Key files include: entry points, routing configuration, dependency injection setup, middleware chains, database schemas, and inter-module interfaces.
- Infrastructure definitions (Docker, Kubernetes, cloud config) provide valuable context for deployment architecture.

---

## Expected Outputs

1. **Architecture Overview** — 2-3 sentence high-level description of the system design.
2. **Pattern Identification** — Named architectural pattern with justification and any hybrid characteristics.
3. **Module Map** — Table or list of modules with responsibilities, dependencies, and interfaces.
4. **Dependency Relationships** — Text-based dependency diagram or structured list of inter-module dependencies.
5. **Data Flow** — Step-by-step description of how data moves through the system.
6. **Technology Rationale** — Key technology choices and the apparent reasoning behind them.
7. **API Surface** — Description of how the system exposes functionality, with key endpoints or interfaces.
8. **Scalability and Resilience** — Assessment of how the architecture handles growth and failure.
9. **Technical Risks** — Architectural concerns, coupling issues, or scalability bottlenecks.

---

## Token Optimization Strategy

- Use text-based diagrams (ASCII art or structured lists) to represent relationships — these are far more token-efficient than prose descriptions of the same information.
- Focus on structural relationships and design decisions, not implementation details.
- When describing a module, state its purpose and interfaces rather than listing its files.
- Avoid documenting every class or function — focus on module-level boundaries.
- If the analysis level is `quick`, limit output to sections 1, 2, 3, and 9 only.
- Use consistent notation throughout: arrows for dependencies, brackets for optional components.

---

## Recommended Template

`templates/architecture-summary.md`

---

## Recommended Combinations

| Audience | Purpose | Why It Works |
|----------|---------|--------------|
| Developer | Understand | Engineer needs to understand the system before modifying it. |
| Developer | Improve | Identifies architectural weaknesses and improvement opportunities. |
| AI Agent | Understand | Gives the AI agent a structural map for precise code changes. |
| Product Manager | Review | PM evaluates whether the architecture supports the product roadmap. |
| Executive | Document | Non-technical summary of the engineering foundation. |