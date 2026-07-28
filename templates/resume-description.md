# Resume Description Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | Resume Description |
| Intended Use | Professional profiles, resumes, portfolios |
| Typical Length | 50 - 400 words |
| Compatible Modes | resume |
| Compatible Audiences | recruiter, client, developer |

---

## Required Sections

### 1. One-Liner

```markdown
{action_verb} {project_description} using {key_technologies}.
```

A single sentence suitable for a resume bullet point. Use strong action verbs: Built, Designed, Developed, Architected, Led, Implemented, Engineered. Focus on scope and impact.

Source from: `knowledge_model.purpose`, `knowledge_model.technology_stack.language`, `knowledge_model.technology_stack.framework`.

---

### 2. Short Description

```markdown
{2-3 sentences describing the project, its purpose, and the technologies used}
```

A paragraph suitable for a project section on a resume or LinkedIn. Frame in terms of problems solved and technologies demonstrated.

---

### 3. Bullet Points

```markdown
- {action_verb} {what was done} using {technology}, resulting in {outcome/impact}
- {action_verb} {what was done} that {demonstrates skill/achieves result}
- {action_verb} {what was done} for {audience/benefit}
```

3-5 achievement-oriented bullet points. Each should demonstrate a distinct skill or achievement:

1. **Core capability**: What was built (full-stack, backend, frontend, etc.).
2. **Technical complexity**: Hard problems solved.
3. **Scale or impact**: Evidence of significance.
4. **Engineering quality**: Testing, documentation, CI/CD.
5. **Collaboration or methodology**: Team practices if evident.

---

### 4. Technical Keywords

```markdown
{tech1}, {tech2}, {tech3}, ...
```

Comma-separated list of all technologies used, optimized for ATS systems. Include:
- All programming languages
- All frameworks and libraries
- Databases and data stores
- Infrastructure tools (Docker, AWS, etc.)
- Testing frameworks
- CI/CD tools

---

### 5. Scale and Impact

```markdown
**Scale**: {evidence of project size — modules, features, or user count}
**Impact**: {what the project enables or achieves}
```

Quantify wherever possible. If exact numbers are not available, use directional indicators: "supports multiple database backends," "handles concurrent user sessions," "processes thousands of records."

---

### 6. Long Description (Optional)

```markdown
{Full narrative paragraph suitable for a portfolio page}
```

A fuller 4-6 sentence narrative. Suitable for portfolio pages or cover letter project descriptions. Include the problem, approach, technologies, and outcome.

---

## Optional Sections

### A. Role Clarification

```markdown
**Role**: {inferred role based on scope of contributions}
```

Include when the developer's specific role needs clarification (e.g., "led backend development," "contributed to frontend components").

---

## Rendering Rules

1. **Never include negative information** — no technical debt, missing tests, or incomplete features.
2. **Use past tense** for completed work, present tense for ongoing projects.
3. **Prioritize impact over process** — "reduced load times by 40%" beats "implemented caching."
4. **Be honest but favorable** — do not fabricate metrics, but do frame achievements in their best light.
5. **Match the audience** — `recruiter` gets keywords and bullets; `client` gets outcomes and reliability signals.
6. **Adjust length to context** — a resume bullet is 1 line; a portfolio description is a full paragraph.
