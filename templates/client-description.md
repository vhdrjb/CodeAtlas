# Client Description Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | Client Description |
| Intended Use | Client-facing project summaries and status reports |
| Typical Length | 300 - 800 words |
| Compatible Modes | overview, product, progress, full-documentation |
| Compatible Audiences | client, executive |

---

## Required Sections

### 1. Project Overview

```markdown
# {project_name} — Project Summary

{purpose}
```

A clear, jargon-free description of the project and its value. Source from `knowledge_model.purpose`. Frame in terms of business outcomes and user benefits rather than technical implementation.

---

### 2. What Has Been Delivered

```markdown
## Delivered Features

- **{feature_name}**: {user-friendly description of the feature and its value}
- **{feature_name}**: {description}
```

Source from `knowledge_model.implementation_status.completed_features`. Present each feature from the user's perspective — what they can now do that they could not before.

---

### 3. Current Work

```markdown
## In Progress

- **{feature_name}**: {status and expected completion context}
```

Source from `knowledge_model.implementation_status.in_progress_features`. Give the client a clear picture of what is being worked on without exposing internal technical challenges.

---

### 4. Technology Summary

```markdown
## Technology

| Area | Choice | Benefit |
|------|--------|--------|
| {category} | {technology} | {business benefit} |
```

Source from `knowledge_model.technology_stack`. Each technology choice should be paired with a business benefit: reliability, speed, security, cost-efficiency. Do not list more than 5-6 technologies.

---
## Optional Sections

### A. Security and Reliability

```markdown
## Security and Reliability

{description of security measures and reliability indicators}
```

Include when the client has expressed concern about security or when the project handles sensitive data. Describe authentication, data protection, and uptime measures in business terms.

---

### B. Next Steps

```markdown
## Planned Enhancements

- {planned feature or improvement}
```

Source from `knowledge_model.implementation_status.planned_features`. Present planned work as enhancements and opportunities, not as things that are missing.

---

## Rendering Rules

1. Every technical statement must be accompanied by a business benefit explanation.
2. Never expose internal issues, technical debt, or team challenges to the client.
3. Use the client's language, not the engineering team's language.
4. Present progress positively — focus on what exists, not on what is missing.
5. If analysis reveals quality concerns, reframe them as "identified improvement opportunities" and include them in Next Steps.
6. Keep the tone professional and confidence-inspiring throughout.