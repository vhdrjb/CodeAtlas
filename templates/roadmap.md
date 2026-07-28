# Roadmap Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | Roadmap |
| Intended Use | Project status assessment and forward-looking analysis |
| Typical Length | 400 - 1,500 words |
| Compatible Modes | progress, full-documentation |
| Compatible Audiences | developer, product-manager, executive, investor |

---

## Required Sections

### 1. Current Phase

```markdown
# {project_name} — Project Roadmap

## Current Phase

{development_phase assessment with supporting evidence}
```

Source from `knowledge_model.inferred.development_phase` and `knowledge_model.implementation_status`. Clearly state whether the project is in prototyping, MVP, beta, production, or maintenance phase, and cite the evidence supporting this assessment.

---

### 2. Completion by Module

```markdown
## Module Completion

| Module | Status | Evidence |
|--------|--------|----------|
| {name} | {completed/partial/planned} | {what was observed} |
```

Source from `knowledge_model.major_modules` and `knowledge_model.implementation_status`. Each module's status should be supported by specific observations from the codebase.

---

### 3. Feature Status

```markdown
## Feature Status

### Completed
- {feature}: {brief evidence of completion}

### In Progress
- {feature}: {what exists and what is missing}

### Planned
- {feature}: {evidence this is intended}
```

Source from `knowledge_model.implementation_status`. Group features by status. Each entry should include a one-line evidence reference.

---

### 4. Technical Debt

```markdown
## Technical Debt

| Item | Severity | Location | Description |
|------|----------|----------|-------------|
| {item} | {high/medium/low} | {file or module} | {what the issue is} |
```

Source from `knowledge_model.technical_debt` and analysis observations. Only include at `standard` or `deep` analysis levels.

---

### 5. Risks

```markdown
## Risks

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| {risk} | {high/medium/low} | {high/medium/low} | {suggested approach} |
```

Source from `knowledge_model.risks`. Assess both likelihood and impact. Include a suggested mitigation for each risk.

---

## Optional Sections

### A. Momentum Assessment

```markdown
## Development Momentum

{assessment of whether the project is actively developed, slowing, or stalled}
```

Include when commit history is available. Assess frequency, size, and distribution of recent commits.

---
### B. Identified Roadmap

```markdown
## Inferred Roadmap

Based on code analysis, the following appear to be planned:

1. {item}: {evidence}
2. {item}: {evidence}
```

Include when TODO/FIXME comments, empty directories, or scaffolded files suggest planned work.

---

## Rendering Rules

1. **Evidence is mandatory** — every status claim must reference specific observations.
2. **Distinguish observed from inferred** — use `[Inferred]` tags consistently.
3. For the `executive` audience, simplify the technical debt and risk tables into a high-level summary.
4. For the `investor` audience, emphasize momentum and execution velocity.
5. For the `developer` audience, include file paths as evidence references.
6. Do not fabricate roadmap items — only include items with direct code evidence (TODO comments, empty modules, issue references).
