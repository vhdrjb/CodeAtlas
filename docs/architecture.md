# Architecture Overview

Code Atlas uses a compositional architecture where the final output is determined by combining independent, plug-and-play dimensions. This design maximizes extensibility while keeping the system simple and maintainable.

---

## Design Principles

### Composition Over Configuration

Code Atlas does not use a complex configuration file or a rigid command structure. Instead, it composes behavior from independent dimension files. Each dimension (analysis level, mode, audience, purpose) is a self-contained Markdown file that the AI agent reads and follows. This means:

- Adding a new mode requires only creating a new file in `modes/`. No existing code or configuration needs to change.
- The same mode works with any audience, purpose, and analysis level.
- Dimensions can be combined freely — any valid combination produces a coherent output.

### Configuration-Driven, Not Command-Driven

Code Atlas does not implement commands like `"analyze this project."` Instead, it provides a structured framework that the AI agent follows. The agent reads the skill definition, selects the appropriate configuration files, and produces output according to their instructions. This design:

- Works with any AI agent that can read Markdown.
- Avoids vendor-specific APIs or tooling.
- Keeps the system transparent and auditable — every instruction is in plain Markdown.

### Knowledge Model as Source of Truth

Rather than generating output directly from file inspection, Code Atlas first builds an internal Project Knowledge Model. This model captures all discovered information in a structured format. The model then feeds the output template. This separation ensures:

- Multiple outputs can be generated from a single analysis.
- The same knowledge model powers all templates, modes, and audiences.
- The model clearly separates observed facts from inferred information.

---

## Component Architecture

```
┌──────────────────────────────────────────────────┐
│                   Code Atlas                     │
│                                                  │
│  ┌─────────┐  ┌──────┐  ┌──────────┐  ┌───────┐ │
│  │ Analysis│  │ Mode │  │ Audience │  │Purpose│ │
│  │  Level  │  │      │  │          │  │       │ │
│  └────┬────┘  └──┬───┘  └────┬─────┘  └──┬────┘ │
│       │          │           │           │       │
│       ▼          ▼           ▼           ▼       │
│  ┌────────────────────────────────────────────┐  │
│  │           Knowledge Model Builder           │  │
│  │  (Scans repo, populates structured model)   │  │
│  └──────────────────┬─────────────────────────┘  │
│                     │                            │
│                     ▼                            │
│  ┌────────────────────────────────────────────┐  │
│  │           Project Knowledge Model           │  │
│  │  (Structured data: facts + inferences)      │  │
│  └──────────────────┬─────────────────────────┘  │
│                     │                            │
│                     ▼                            │
│  ┌────────────────────────────────────────────┐  │
│  │              Template Renderer              │  │
│  │  (Selects template, applies dimensions)     │  │
│  └──────────────────┬─────────────────────────┘  │
│                     │                            │
│                     ▼                            │
│              Output Document                    │
└──────────────────────────────────────────────────┘
```

---

## Directory Structure

```
code-atlas/
├── skill.md                  # Entry point — AI agents start here
├── configs/
│   ├── defaults.md            # Global defaults and precedence rules
│   └── analysis-levels/       # Scanning depth control
│       ├── quick.md
│       ├── standard.md
│       └── deep.md
├── modes/                     # What to focus on (9 modes)
├── audiences/                 # Who the output is for (7 audiences)
├── purposes/                  # Why the analysis is done (5 purposes)
├── templates/                 # Output format definitions (11 templates)
├── docs/                      # Human-facing documentation
├── examples/                  # Realistic usage examples
└── outputs/                   # Generated documents go here
```

### Key Design Decisions

- **Markdown throughout**: Every file is plain Markdown. This maximizes compatibility with AI agents and makes the system human-readable.
- **No runtime code**: Code Atlas is entirely instruction-based. There is no code to install, build, or execute. The AI agent is the runtime.
- **Flat dimension directories**: Each dimension (mode, audience, purpose) is a flat directory of files. There is no nesting, no hierarchy, no inheritance — just files that the agent reads and applies.
- **Templates use placeholders**: Templates describe the structure and content rules using `{placeholder}` notation. The AI agent interprets these as instructions to fill in data from the knowledge model.

---

## Data Flow

1. **Agent reads `skill.md`** — Understands the overall framework, knowledge model schema, and available options.
2. **Agent identifies configuration** — From user prompt or defaults, determines analysis level, mode, audience, and purpose.
3. **Agent reads dimension files** — Loads the appropriate analysis level, mode, audience, and purpose files.
4. **Agent scans the target repository** — Following the analysis level's scanning strategy.
5. **Agent builds the knowledge model** — Populating the structured schema from discovered information.
6. **Agent reads the template** — Loads the template mapped to the selected mode.
7. **Agent renders the output** — Filling the template with knowledge model data, adjusting for audience and purpose.

---

## Extensibility

Adding new capabilities requires only creating new files:

| To Add | Create File In | Modify Existing Files |
|--------|---------------|---------------------|
| New analysis level | `configs/analysis-levels/` | None |
| New mode | `modes/` | `configs/defaults.md` (to add template mapping) |
| New audience | `audiences/` | None |
| New purpose | `purposes/` | None |
| New template | `templates/` | `configs/defaults.md` (if auto-mapping needed) |

This extensibility model means contributions are low-risk — new additions cannot break existing functionality.