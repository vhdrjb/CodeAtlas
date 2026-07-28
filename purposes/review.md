# Purpose: Review

**Goal**: Evaluate the project's quality and provide actionable assessment.

---

## Description

The Review purpose directs the AI agent to adopt a critical, evaluative stance. Instead of simply describing what exists, the agent should assess quality, identify issues, and provide recommendations. The output should be useful for decision-making — helping a team or individual determine what to improve and in what order.

When the purpose is Review, the AI agent should prioritize objectivity, specificity, and actionability. Every finding should be supported by evidence from the codebase, and every recommendation should be concrete enough to act on.

---

## Behavioral Characteristics

- **Critical but fair**. Identify both strengths and weaknesses — do not focus solely on problems.
- **Evidence-backed**. Every assessment should reference specific files, patterns, or observations.
- **Prioritized**. Findings should be ordered by severity or impact, not by discovery order.
- **Constructive**. Problems should be paired with actionable recommendations.
- **Calibrated to audience**. A review for an executive should focus on strategic risks; a review for a developer should focus on code-level improvements.

---

## Output Modifications

- Include an overall assessment or grade at the top.
- Organize findings by severity: Critical, Major, Minor.
- For each finding, include: the issue, evidence (file path or pattern), impact, and recommendation.
- Include a prioritized recommendations section at the end.
- Distinguish between observed issues and suspected issues.
- If the audience is non-technical, translate technical findings into business impact.

---

## Recommended Modes

| Mode | Value |
|------|-------|
| Review | Comprehensive quality assessment |
| Architecture | Architecture-specific evaluation |
| Progress | Progress and execution quality review |
| Infrastructure | DevOps and operational readiness review |
| Full Documentation | Complete project audit |