# Default Configuration

This file defines the default settings used when no explicit configuration is provided.

---

## Defaults

| Parameter       | Default Value  | Notes                                     |
|-----------------|----------------|-------------------------------------------|
| Analysis Level  | `standard`     | Balanced depth for most use cases          |
| Mode            | `overview`     | General-purpose project understanding      |
| Audience        | `developer`    | Technical audience with engineering focus  |
| Purpose         | `understand`   | Build comprehension of the project          |
| Output Format   | `markdown`     | All templates produce Markdown             |
| Output Location | `outputs/`     | Generated files are saved here              |

---

## Precedence Rules

When configuration conflicts occur, the following precedence applies (highest to lowest):

1. **Explicit user instruction** — Direct user input overrides everything.
2. **Mode-specific defaults** — A mode file may override global defaults for its context.
3. **Purpose-specific defaults** — A purpose file may further tune behavior.
4. **Audience-specific defaults** — An audience file adjusts tone and detail level.
5. **Global defaults** — This file provides the baseline.

---

## Fallback Behavior

If a required parameter is missing and no default exists:

- **Analysis Level**: Fall back to `standard`.
- **Mode**: Fall back to `overview`.
- **Audience**: Fall back to `developer`.
- **Purpose**: Fall back to `understand`.
- **Template**: If the selected mode does not map to a template, use `templates/project-overview.md`.

---

## Mode-to-Template Mapping

| Mode               | Default Template              |
|--------------------|-------------------------------|
| overview           | `project-overview.md`         |
| product            | `product-overview.md`         |
| architecture       | `architecture-summary.md`     |
| progress           | `roadmap.md`                  |
| infrastructure     | `architecture-summary.md`     |
| resume             | `resume-description.md`       |
| ai-context         | `llm-context.md`              |
| review             | `project-review.md`           |
| full-documentation | `project-overview.md`         |

This mapping can be overridden by explicit user instruction.
