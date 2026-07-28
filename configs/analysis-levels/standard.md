# Analysis Level: Standard

**Optimized for**: General-purpose understanding. The recommended default for most use cases.

---

## Objective

Provide a balanced, comprehensive understanding of the project. This level inspects enough of the codebase to build an accurate knowledge model without consuming excessive tokens.

---

## Scanning Strategy

### Files to Inspect (Maximum 20-40 files)

Inspect files in the following priority order. Continue until a coherent picture emerges or the token budget is reached.

**Priority 1 — Project Identity (always inspect)**

1. Package manifest (`package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `pom.xml`, or equivalent).
2. README or top-level documentation.
3. License file.
4. Configuration files (up to 3: build config, runtime config, environment config).

**Priority 2 — Structure (inspect selectively)**

5. Top-level directory listing (depth 2).
6. One representative file from each top-level source directory.
7. Router or routing configuration (e.g., `routes/`, `pages/`, `app/` directory index).
8. Database schema or migration files (if present and concise).

**Priority 3 — Implementation (inspect as budget allows)**

9. Main entry point.
10. Core business logic files (up to 5 of the most frequently imported or largest files).
11. API endpoint definitions or controller files (up to 5).
12. Middleware, authentication, or shared utility files (up to 3).
13. Test directory structure (inspect only the directory names and count, not test content).

### Files to Skip

- Dependency lock files (`package-lock.json`, `yarn.lock`, `go.sum`, `Pipfile.lock`).
- Generated files (`build/`, `dist/`, `.next/`, `__pycache__/`).
- Binary assets (images, fonts, compiled binaries).
- Vendor or bundled dependencies (`node_modules/`, `vendor/`).
- Log files.
- Individual test implementation files (unless specifically reviewing quality).
- Documentation subdirectories beyond the top level (unless in `document` purpose).

---

## Knowledge Model Scope

At the Standard level, populate these fields from the knowledge model:

**Fully populated:**

- `project_name`
- `repository_url`
- `license`
- `purpose`
- `business_domain`
- `target_users` (inferred if not documented)
- `product_summary`
- `key_features`
- `architecture_summary`
- `architecture_pattern`
- `technology_stack` (all sub-fields)
- `major_modules` (name, path, purpose, status)
- `implementation_status` (overall completion, completed and in-progress features)
- `known_constraints`
- `analysis_metadata`

**Populated when evidence is available:**

- `stakeholders`
- `value_proposition`
- `user_flows`
- `technical_debt`
- `risks`
- `assumptions`

**Inferred section:**

- `inferred.team_size`
- `inferred.development_phase`
- `inferred.coding_standards`

---

## Token Budget

| Dimension         | Limit           |
|-------------------|-----------------|
| Files to read     | 20 - 40         |
| Input tokens      | 15,000 - 50,000 |
| Output tokens     | 1,500 - 5,000   |
| Directories depth | 2 - 3           |

---

## Output Guidelines

- Use a mix of paragraphs and structured lists.
- Each module description should be 2-3 sentences.
- Include a concise technology stack table.
- Include implementation status summary.
- Mark inferred information with [Inferred] tags.
- Omit detailed dependency listings unless relevant to the mode.
- Include a brief "Confidence" note indicating which areas were directly observed vs. inferred.

---

## When to Use Standard

- Default choice for most analysis tasks.
- Preparing documentation for a new team member.
- Generating context for an AI agent that will make code changes.
- Creating product or architecture summaries.
- Review sessions where full code-level detail is not required.
- Situations where you need a reliable understanding without spending excessive tokens.