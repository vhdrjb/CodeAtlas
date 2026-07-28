# Feature Catalog Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | Feature Catalog |
| Intended Use | Comprehensive listing of project features |
| Typical Length | 400 - 2,000 words |
| Compatible Modes | product, overview, full-documentation |
| Compatible Audiences | developer, product-manager, client |

---

## Required Sections

### 1. Introduction

```markdown
# {project_name} — Feature Catalog

{one-paragraph introduction to the product and its feature philosophy}
```

Source from `knowledge_model.product_summary`. Set the stage for the feature listing.

---

### 2. Feature Categories

```markdown
## Features

### {category_name}

#### {feature_name}
**Status**: {completed | in-progress | planned}
**Description**: {what the feature does, focused on user value}
```

Group features into logical categories. Source from `knowledge_model.key_features` and `knowledge_model.implementation_status`. For each feature:

- **Name**: Clear, user-facing name.
- **Status**: Completion status from the knowledge model.
- **Description**: What the user can accomplish. For the `developer` audience, also include which module implements it.

---

### 3. Feature Matrix

```markdown
## Feature Status Summary

| Category | Completed | In Progress | Planned |
|----------|-----------|-------------|--------|
| {category} | {count} | {count} | {count} |
| **Total** | {total} | {total} | {total} |
```

A summary table showing completion by category. Include only when multiple categories exist.

---

## Optional Sections

### A. Competitive Feature Comparison

```markdown
## Competitive Position

| Feature | {project_name} | Alternative A | Alternative B |
|---------|---------------|---------------|---------------|
| {feature} | {yes/partial/no} | {status} | {status} |
```

Include when audience is `investor` or `product-manager` and purpose is `pitch`. Only include if competitive alternatives can be reasonably identified from the codebase.

---

### B. Feature Roadmap

```markdown
## Planned Features

| Feature | Category | Priority Evidence |
|---------|----------|-----------------|
| {feature} | {category} | {why it appears planned} |
```

Include when purpose is `understand`, `document`, or `improve`. Source from `knowledge_model.implementation_status.planned_features` and any roadmap signals found during analysis.

---

## Rendering Rules

1. Organize features by category, not by module — the reader thinks in terms of capabilities, not code structure.
2. Clearly distinguish between completed, in-progress, and planned features.
3. For the `product-manager` audience, include user benefit for each feature.
4. For the `developer` audience, include the implementing module or file path.
5. For the `client` audience, use the Client Description template instead — this template may be too technical.
6. Do not include internal features (logging, caching) unless they are user-visible or the audience is `developer`.