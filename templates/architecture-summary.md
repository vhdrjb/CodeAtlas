# Architecture Summary Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | Architecture Summary |
| Intended Use | Technical architecture analysis |
| Typical Length | 600 - 2,500 words |
| Compatible Modes | architecture, infrastructure, full-documentation |
| Compatible Audiences | developer, ai-agent, product-manager |

---

## Required Sections

### 1. Architecture Overview

```markdown
# {project_name} — Architecture

{architecture_summary}

**Pattern**: {architecture_pattern}
```

2-3 sentences describing the system design. Source from `knowledge_model.architecture_summary`.

---

### 2. Technology Stack

```markdown
## Technology Stack

| Category | Technology | Purpose |
|----------|-----------|----------|
| Language | {tech} | {why it's used} |
| Framework | {tech} | {role in the system} |
| Database | {tech} | {data stored} |
```

Source from `knowledge_model.technology_stack`. Include version numbers when available (especially for `deep` analysis). Include a brief purpose column explaining the role of each technology.

---

### 3. Module Map

```markdown
## Module Map

| Module | Path | Responsibility | Depends On |
|--------|------|---------------|------------|
| {name} | {path} | {purpose} | {list of dependencies} |
```

Source from `knowledge_model.major_modules`. Add dependency information by analyzing import statements (available at `standard` and `deep` levels). For the `ai-agent` audience, also include key exports for each module.

---

### 4. Data Flow

```markdown
## Data Flow

{entry_point} -> {processing_step} -> {data_store} -> {output}
```

Describe how data moves through the system. Use a text-based flow diagram for the `developer` audience. Use a paragraph description for the `executive` audience. This section requires `standard` or `deep` analysis level.

---

### 5. API Surface

```markdown
## API Surface

**Type**: {REST | GraphQL | gRPC | CLI | SDK}

| Endpoint/Interface | Method | Purpose |
|-------------------|--------|---------|
| {path} | {GET/POST/etc.} | {description} |
```

Document the public interface of the system. For web applications, list API routes. For libraries, list the public API. For CLIs, list commands. Omit if the project has no external interface.

---

## Optional Sections

### A. Dependency Diagram

```markdown
## Module Dependencies

```
{module_a}
  └── {module_b}
      └── {module_c}
```
```

Include at `deep` analysis level or when audience is `ai-agent`. Represent as a text-based tree or graph.

---

### B. Scalability Assessment

```markdown
## Scalability Assessment

{assessment of how the architecture supports growth}
```

Include when purpose is `review` or `improve`. Assess horizontal/vertical scaling, caching strategy, and potential bottlenecks.

---

### C. Technical Risks

```markdown
## Technical Risks

| Risk | Severity | Impact |
|------|----------|--------|
| {risk} | {high/medium/low} | {what could go wrong} |
```

Include when purpose is `review` or `improve`. Source from `knowledge_model.risks` and architectural analysis.

---

## Rendering Rules

1. Use technical language appropriate for the audience. For `ai-agent`, be maximally specific.
2. Include file paths for all module references when audience is `developer` or `ai-agent`.
3. When describing dependencies, distinguish between compile-time (imports) and runtime (API calls, shared databases) dependencies.
4. If the architecture pattern is a hybrid, explain the hybrid nature rather than forcing a single label.
5. Do not include implementation details (function signatures, code snippets) unless the audience is `ai-agent`.