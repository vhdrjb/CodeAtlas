# Company Description Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | Company Description |
| Intended Use | About page, company profile, investor materials |
| Typical Length | 200 - 600 words |
| Compatible Modes | overview, product, full-documentation |
| Compatible Audiences | executive, investor, client |

---

## Required Sections

### 1. Company Mission

```markdown
# {project_name}

{purpose}
```

One paragraph describing what the organization behind the project does and why. Source from `knowledge_model.purpose` and `knowledge_model.business_domain`. Reframe the project description as a company mission statement.

---

### 2. What We Build

```markdown
## What We Build

{product_summary}
```

A 2-3 sentence product description focused on the value delivered to users. Source from `knowledge_model.product_summary`. Use customer-centric language.

---

### 3. Technology Foundation

```markdown
## Technology

{architecture_summary}

Built with: {comma-separated list of key technologies}
```

Brief, non-technical description of the technology stack emphasizing reliability, scalability, and modern practices. Source from `knowledge_model.technology_stack` and `knowledge_model.architecture_summary`. Do not list every dependency — focus on the 3-5 most impressive or relevant technologies.

---

### 4. Who We Serve

```markdown
## Who We Serve

{description of target users and the value they receive}
```

Source from `knowledge_model.target_users`. Frame in terms of the problems solved for each user group.

---

## Optional Sections

### A. Track Record

```markdown
## Track Record

{evidence of execution: completed features, milestones, user metrics}
```

Include when purpose is `pitch`. Source from `knowledge_model.implementation_status`.

---

### B. Differentiators

```markdown
## What Makes Us Different

- {differentiator_1}
- {differentiator_2}
```

Include when audience is `investor` or `client`. Identify 2-3 factors that differentiate this project from alternatives.

---

## Rendering Rules

1. Use first-person plural ("we") unless the audience definition specifies otherwise.
2. Maintain a professional, confident tone throughout.
3. Do not include implementation details, file paths, or code references.
4. Keep the description factual — do not exaggerate claims that cannot be supported by the codebase evidence.
5. If the project is a personal or open-source project (not a company), adapt the template to describe the project's mission and community.
