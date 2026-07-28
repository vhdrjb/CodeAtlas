# Product Overview Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | Product Overview |
| Intended Use | Business and product perspective analysis |
| Typical Length | 400 - 1,500 words |
| Compatible Modes | product, full-documentation |
| Compatible Audiences | product-manager, executive, client, investor |

---

## Required Sections

### 1. Product Summary

```markdown
# {project_name} — Product Overview

{product_summary}
```

2-3 sentence product overview. Source from `knowledge_model.product_summary`. Frame in terms of user value and market need.

---

### 2. Problem and Solution

```markdown
## Problem and Solution

**The Problem**:
{description of the problem this project addresses}

**The Solution**:
{description of how this project solves it}
```

Derived from `knowledge_model.purpose` and `knowledge_model.value_proposition`. If the README explicitly states the problem/solution, use that language. Otherwise, infer from features and target users.

---

### 3. Target Users

```markdown
## Target Users

{user_persona_1}: {description of who they are and what they need}
{user_persona_2}: {description}
```

Source from `knowledge_model.target_users`. If no explicit personas exist, infer from the feature set and any user-facing text in the codebase.

---

### 4. Key Features

```markdown
## Key Features

1. **{feature_name}**: {user-focused description of the feature and its benefit}
2. **{feature_name}**: {description}
```

Source from `knowledge_model.key_features`. Each feature should be described in terms of what the user can accomplish, not how it is implemented. Limit to the 5-10 most significant features.

---

### 5. User Flows

```markdown
## User Flows

### {flow_name}
1. {step}
2. {step}
3. {step}
```

Source from `knowledge_model.user_flows`. Describe 3-5 primary user journeys. Each step should be a concrete action the user takes. Inferred flows should be marked `[Inferred]`.

---

## Optional Sections

### A. Value Proposition

```markdown
## Value Proposition

{value_proposition}
```

Include when audience is `investor` or `client`. Source from `knowledge_model.value_proposition`.

---

### B. Business Domain

```markdown
## Business Domain

**Domain**: {business_domain}
**Stakeholders**: {stakeholders}
```

Include when the business context adds useful context for the audience.

---

### C. Maturity Assessment

```markdown
## Product Maturity

**Phase**: {inferred.development_phase}
**Evidence**: {supporting observations}
```

Include when audience is `investor` or `product-manager`. Clearly state if this is inferred.

---

### D. Opportunities and Gaps

```markdown
## Opportunities and Gaps

- {opportunity_1}
- {opportunity_2}
```

Include when purpose is `improve` or `pitch`. Identify features, user segments, or market opportunities that the project does not currently address.

---

## Rendering Rules

1. Use business and user-centric language, not technical jargon (unless audience is `developer`).
2. Focus on outcomes and user benefits, not implementation mechanisms.
3. If the repository is a library or CLI tool (not a user-facing product), adapt the template to describe the "product" as the developer experience.
4. Mark inferred information with `[Inferred]` tags.
5. Do not include code snippets or file paths unless they demonstrate a user-facing capability.
