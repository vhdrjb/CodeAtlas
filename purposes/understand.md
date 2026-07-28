# Purpose: Understand

**Goal**: Build comprehension of the project without producing formal documentation.

---

## Description

The Understand purpose is the most common and default purpose. It directs the AI agent to analyze the project and produce output that maximizes the reader's understanding. The output is informational — it exists to be read and absorbed, not to be published, submitted, or used as a formal deliverable.

When the purpose is Understand, the AI agent should prioritize clarity, accuracy, and completeness. The output should feel like a knowledgeable colleague explaining the project to you — thorough but approachable, detailed but not overwhelming.

---

## Behavioral Characteristics

- **Accuracy over polish**. Facts should be correct even if the writing is not perfectly styled.
- **Comprehensive but focused**. Cover all important aspects of the selected mode without going off-topic.
- **Evidence-based**. Every claim should be traceable to something observed in the codebase.
- **Inference transparency**. Clearly separate observed facts from reasonable inferences.

---

## Output Modifications

- Include a confidence note at the end indicating which observations were direct and which were inferred.
- Do not include action items, recommendations, or next steps (unless the mode specifically calls for them).
- Do not format the output as a formal document with title pages or metadata headers.
- The output should read naturally as an explanation, not as a report.

---

## Recommended Modes

All modes work well with the Understand purpose. The most common pairings:

| Mode | Value |
|------|-------|
| Overview | General project understanding |
| Architecture | Technical structure comprehension |
| Product | Business and product context |
| AI Context | Agent-ready project context |
| Progress | Current state and trajectory |