# Analysis Level: Quick

**Optimized for**: Free-tier models, rapid triage, first-pass understanding.

---

## Objective

Provide a concise, high-level summary of the project with minimal token expenditure. This level is designed for scenarios where context window is limited or a fast overview is sufficient.

---

## Scanning Strategy

### Files to Inspect (Maximum 5-10 files)

Prioritize files in this order. Stop once the token budget is reached.

1. **Package manifest** — `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `pom.xml`, `build.gradle`, or equivalent.
2. **README or equivalent** — Any top-level documentation file (`README.md`, `README.rst`, `README.txt`).
3. **Configuration files** — Up to 2 config files (e.g., `tsconfig.json`, `.env.example`, `docker-compose.yml`).
4. **Entry point** — The main application entry file (e.g., `src/index.ts`, `app/main.py`, `cmd/server/main.go`).
5. **Directory structure** — A single `ls` or tree view of the top-level directories (depth 1).

### Files to Skip

- All test files.
- All documentation files beyond the README.
- All source files beyond the entry point.
- Dependency lock files (`package-lock.json`, `yarn.lock`, `go.sum`).
- CI/CD configuration files.
- All `node_modules/`, `vendor/`, `build/`, `dist/` directories.

---

## Knowledge Model Scope

At the Quick level, populate only these fields from the knowledge model:

- `project_name`
- `purpose`
- `technology_stack` (language and framework only)
- `architecture_pattern` (if inferable from structure)
- `major_modules` (names and paths only, no detailed descriptions)
- `analysis_metadata`

All other fields should be left empty or marked as "not analyzed at this level."

---

## Token Budget

| Dimension         | Limit          |
|-------------------|----------------|
| Files to read     | 5 - 10         |
| Input tokens      | 5,000 - 15,000 |
| Output tokens     | 500 - 1,500    |
| Directories depth | 1              |

---

## Output Guidelines

- Use bullet points instead of paragraphs.
- Limit each module description to one line.
- Do not include code snippets.
- Do not include dependency listings.
- Do not include implementation status details.
- Clearly state: "This is a Quick-level analysis. For deeper understanding, use `standard` or `deep` analysis levels."

---

## When to Use Quick

- Free-tier AI models with limited context windows.
- Initial project triage before deciding whether to invest more analysis.
- Quick "what is this project?" questions.
- Pipeline or automation contexts where speed matters more than depth.
- Evaluating multiple repositories in a batch.