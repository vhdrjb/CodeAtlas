# Purpose: Improve

**Goal**: Identify specific, actionable improvements and generate an implementation plan.

---

## Description

The Improve purpose goes beyond identifying problems — it generates a concrete plan for fixing them. The output should read like a backlog or improvement roadmap, with each item specific enough that a developer could pick it up and start working. The AI agent should consider the project's current state, constraints, and priorities when formulating recommendations.

When the purpose is Improve, the AI agent should prioritize actionability, feasibility, and impact. Recommendations should be ordered so that earlier items create the foundation for later ones. Quick wins should be surfaced separately from structural improvements.

---

## Behavioral Characteristics

- **Prescriptive, not descriptive**. The focus is on what to do, not just what is wrong.
- **Sequenced**. Recommendations should have a logical order — some improvements enable others.
- **Effort-aware**. Distinguish between quick wins, medium-effort improvements, and major undertakings.
- **Impact-weighted**. Prioritize by impact, not by number of issues found.
- **Respectful of existing decisions**. Do not recommend rewriting everything. Work within the existing architecture unless it is fundamentally flawed.

---

## Output Modifications

- Include a "Quick Wins" section for low-effort, high-impact improvements.
- For each recommendation: describe the change, explain the benefit, estimate the effort, and list affected files.
- Group recommendations by category (testing, documentation, performance, security, etc.).
- Include a suggested implementation order with rationale.
- If the project has obvious constraints (small team, limited budget), factor those into recommendations.
- End with a summary of the top 3-5 highest-impact improvements.

---

## Recommended Modes

| Mode | Value |
|------|-------|
| Review | Identify issues and generate improvement plan |
| Architecture | Architectural improvement recommendations |
| Infrastructure | DevOps and operational improvements |
| Progress | Process and methodology improvements |
| Full Documentation | Comprehensive improvement roadmap |