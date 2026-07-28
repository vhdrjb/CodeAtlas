# Mode: Product

**Purpose**: Analyze the project from a business and product perspective.

---

## Objective

The Product mode shifts the analytical lens away from implementation details and toward the business context of the software. It answers the question: "What problem does this project solve, for whom, and how does it deliver value?" This mode is essential when the consumer of the output needs to understand the product's market positioning, user experience, and feature set without wading through technical architecture.

This mode treats the codebase as evidence of product intent. It reads between the lines of source code, configuration, and documentation to reconstruct the product vision, user personas, and competitive context. Where explicit product documentation exists, it is used directly. Where it does not exist, the mode infers product characteristics from the implemented features, UI structure, and user-facing text.

---

## Analysis Scope

- **Problem Statement**: What problem the project solves, derived from README, documentation, and feature analysis.
- **Target Users**: Who uses this product — primary personas and secondary audiences, inferred from language, features, and UX patterns.
- **Value Proposition**: What makes this project valuable or differentiated from alternatives.
- **Key Features**: A catalog of major features with descriptions focused on user benefit rather than implementation.
- **User Flows**: Primary user journeys through the application, inferred from routing, page structure, and controller logic.
- **Business Domain**: The industry or domain the project operates in (e.g., e-commerce, fintech, healthcare, developer tools).
- **Stakeholders**: Who has a vested interest in the project — users, administrators, developers, third-party integrators.
- **Competitive Positioning**: How the project differentiates itself, inferred from stated goals and unique features.
- **Current Maturity**: Whether the product appears to be in MVP, beta, production, or maintenance phase.

---

## Expected Inputs

- A repository with sufficient structure to infer product characteristics (UI files, routing, README, documentation).
- Product-focused files are particularly valuable: README, CHANGELOG, marketing pages, onboarding flows.
- If the repository is purely a library or CLI tool without a UI, the mode adapts to focus on the developer experience as the "product."

---

## Expected Outputs

1. **Product Summary** — 2-3 sentences describing what the product is and who it is for.
2. **Problem and Solution** — A paragraph on the problem addressed and how the project solves it.
3. **Target Users** — Description of primary and secondary user personas.
4. **Key Features** — Numbered list of major features with user-focused descriptions.
5. **User Flows** — 3-5 primary user journeys described step by step.
6. **Business Domain** — The industry/domain with any relevant context.
7. **Maturity Assessment** — Current development phase with supporting evidence.
8. **Opportunities and Gaps** — Missing features, underserved user needs, or growth areas.

---

## Token Optimization Strategy

- Emphasize business and user-centric language over technical jargon.
- Focus on outcomes (what the user can do) rather than mechanisms (how it works internally).
- Skip implementation details unless they directly inform product understanding (e.g., a specific integration reveals a target market).
- Limit user flows to the 3-5 most important ones — do not attempt to document every possible path.
- Use structured lists for features to maximize information density.
- If the repository lacks explicit product documentation, clearly state which product claims are inferred.

---

## Recommended Template

`templates/product-overview.md`

---

## Recommended Combinations

| Audience | Purpose | Why It Works |
|----------|---------|--------------|
| Product Manager | Understand | PM gets a product-level view of an unfamiliar codebase. |
| Client | Pitch | Client sees the product value, not the plumbing. |
| Executive | Understand | Leadership grasps the product vision without technical noise. |
| Investor | Pitch | Investor-focused summary of the product and its market. |
| Developer | Document | Developer produces product docs from code evidence. |
