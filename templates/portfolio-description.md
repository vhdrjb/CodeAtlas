# Portfolio Description Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | Portfolio Description |
| Intended Use | Developer portfolio pages, personal websites |
| Typical Length | 200 - 600 words |
| Compatible Modes | overview, product, resume |
| Compatible Audiences | recruiter, client, developer |

---

## Required Sections

### 1. Project Title and Tagline

```markdown
# {project_name}

{one-line tagline combining what it does and the key technology}
```

The tagline should be memorable and immediately communicate both the project's purpose and its technical interest. Example: "A real-time collaborative editor built with TypeScript, CRDTs, and WebSockets."

---

### 2. Project Story

```markdown
## The Story

{2-3 paragraph narrative about why this project was built, what challenges were faced, and what was learned}
```

This is the narrative heart of the portfolio entry. It should read like a short story with a beginning (the problem), middle (the approach), and end (the result). Draw from:
- `knowledge_model.purpose` — the problem and motivation
- `knowledge_model.architecture_summary` — the approach
- `knowledge_model.key_features` — the result

---

### 3. Key Achievements

```markdown
## Highlights

- **{achievement}**: {description and impact}
- **{achievement}**: {description and impact}
```

3-5 notable achievements. Mix technical accomplishments ("designed a plugin architecture that supports runtime extension") with outcomes ("reduces data processing time by 60%").

---

### 4. Technology Stack

```markdown
## Built With

{comma-separated list of technologies, optionally grouped by category}
```

Source from `knowledge_model.technology_stack`. Present as a clean list or grid — this is for visual appeal in a portfolio. Include technologies that demonstrate breadth and modern skills.

---

## Optional Sections

### A. Live Demo and Links

```markdown
## Links

- **Live Demo**: {url}
- **Source Code**: {url}
- **Documentation**: {url}
```

Include when URLs are available. These are typically added by the developer after receiving the template output.

---

### B. Screenshots

```markdown
## Screenshots

{placeholder for project screenshots}
```

Include a placeholder noting where screenshots would go. The developer adds these manually.

---

### C. Lessons Learned

```markdown
## Lessons Learned

{2-3 bullet points about what was learned from building this project}
```

Include to demonstrate growth and self-awareness. These should be genuine technical lessons, not generic platitudes.

---

## Rendering Rules

1. Write in first person ("I built," "I designed") unless the audience definition specifies otherwise.
2. Be authentic — portfolio entries that sound like marketing copy are less credible.
3. Balance technical depth with accessibility — the reader may be a non-technical hiring manager.
4. Quantify achievements wherever possible.
5. Do not include negative information, but do include honest lessons learned.
6. The output should be ready to paste into a portfolio page with minimal editing.
