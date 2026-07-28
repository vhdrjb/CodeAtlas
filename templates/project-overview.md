# Project Overview Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | Project Overview |
| Intended Use | General-purpose project summary |
| Typical Length | 500 - 2,000 words |
| Compatible Modes | overview, full-documentation |
| Compatible Audiences | All |

---

## Required Sections

### 1. Project Identity

```markdown
# {project_name}

{license} | {repository_url}

{purpose}
```

One-paragraph description of what the project is and why it exists. Source from `knowledge_model.purpose`.

---

### 2. Technology Stack

```markdown
## Technology Stack

| Category | Technologies |
|----------|-------------|
| Languages | {technology_stack.language} |
| Frameworks | {technology_stack.framework} |
| Databases | {technology_stack.database} |
| Infrastructure | {technology_stack.infrastructure} |
| Tooling | {technology_stack.tooling} |
```

Source from `knowledge_model.technology_stack`. Omit categories with no entries.

---

### 3. Architecture

```markdown
## Architecture

{architecture_summary}

**Pattern**: {architecture_pattern}
```

2-3 sentences describing the system design. Source from `knowledge_model.architecture_summary` and `knowledge_model.architecture_pattern`.

---

### 4. Module Overview

```markdown
## Modules

| Module | Path | Purpose | Status |
|--------|------|---------|--------|
| {name} | {path} | {purpose} | {status} |
```

Source from `knowledge_model.major_modules`. Limit descriptions to one line per module.

---

### 5. Implementation Status

```markdown
## Implementation Status

**Overall**: {implementation_status.overall_completion}

**Completed**: {implementation_status.completed_features}
**In Progress**: {implementation_status.in_progress_features}
**Planned**: {implementation_status.planned_features}
```

Source from `knowledge_model.implementation_status`. If data is unavailable, state "Status not assessed at this analysis level."

---

### 6. Key Observations

```markdown
## Key Observations

- {observation_1}
- {observation_2}
- {observation_3}
```

3-5 notable findings. These are not issues — they are interesting or important characteristics discovered during analysis.

---

## Optional Sections

### A. Business Context

```markdown
## Business Context

- **Domain**: {business_domain}
- **Target Users**: {target_users}
- **Stakeholders**: {stakeholders}
```

Include when audience is not `ai-agent` and analysis level is `standard` or `deep`.

---

### B. Constraints and Risks

```markdown
## Constraints and Risks

**Known Constraints**:
- {constraint}

**Risks**:
- {risk}
```

Include when analysis level is `standard` or `deep`, or when purpose is `review` or `improve`.

---

### C. Confidence Note

```markdown
## Analysis Confidence

- **Analysis Level**: {analysis_metadata.analysis_level}
- **Files Inspected**: {analysis_metadata.files_inspected}
- **Confidence**: {analysis_metadata.confidence}
- **Timestamp**: {analysis_metadata.timestamp}
```

Always include when inferences were made. Mark each knowledge model field that was inferred with `[Inferred]`.

---

## Rendering Rules

1. Use the audience definition to adjust terminology and detail level.
2. Use the purpose definition to adjust tone and structure.
3. Omit optional sections when token budget is constrained.
4. Never fabricate data — if a knowledge model field is empty, state that it was not available.
5. Preserve the section order unless the audience or purpose definition specifies otherwise.
