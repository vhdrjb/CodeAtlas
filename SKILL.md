# Code Atlas — AI Skill Definition

> **Code Atlas** is a model-agnostic AI skill that helps AI coding agents understand an existing software project before making changes. It builds an internal Project Knowledge Model from both business and engineering perspectives, then generates targeted documentation based on the selected mode, audience, and purpose.

---


## What This Skill Does

Code Atlas analyzes a software repository and produces structured, audience-appropriate documentation. It does **not** generate code — it generates **understanding**.

The skill operates in three phases:

1. **Discover** — Scan the repository structure, identify key files, and extract configuration metadata.
2. **Model** — Build an internal Project Knowledge Model that captures business context, architecture, technology decisions, and current state.
3. **Output** — Render the knowledge model into a formatted document using the selected template, mode, audience, and purpose.

---

## Core Philosophy

| Principle | Description |
|-----------|-------------|
| **Understand before modifying** | Never suggest changes without first comprehending the existing structure and intent. |
| **Inspect before assuming** | Read actual source files, configs, and docs — do not guess. |
| **Separate facts from inferences** | Clearly distinguish between what is directly observed and what is reasonably inferred. |
| **Optimize for AI context efficiency** | Every output should maximize the signal-to-noise ratio for its intended consumer. |
| **Generate reusable knowledge** | The knowledge model is the single source of truth for all outputs. |
| **Avoid unnecessary token usage** | Prefer summaries over exhaustive listings; omit obvious or redundant information. |
| **Support both lightweight and deep analysis** | The analysis level controls depth; modes control focus. |

---

## How to Use This Skill

### Step 1 — Read This File

When an AI agent receives the instruction to use Code Atlas, it should start by reading this file (`skill.md`) to understand the skill's structure, conventions, and available configurations.

### Step 2 — Determine Configuration

Identify (or ask the user for) the following parameters:

- **Analysis Level**: `quick` | `standard` | `deep` — see `configs/analysis-levels/`
- **Mode**: e.g., `overview`, `architecture`, `product`, `resume` — see `modes/`
- **Audience**: e.g., `developer`, `executive`, `recruiter` — see `audiences/`
- **Purpose**: e.g., `understand`, `document`, `pitch` — see `purposes/`

Defaults:

- Analysis Level: **standard**
- Mode: **overview**
- Audience: **developer**
- Purpose: **understand**

### Step 3 — Follow the Analysis Level Instructions

Read the appropriate analysis-level file from `configs/analysis-levels/` and follow its scanning strategy.

### Step 4 — Build the Knowledge Model

Based on the analysis, construct the Project Knowledge Model. See the section below for the full schema.

### Step 5 — Read the Mode, Audience, and Purpose Files

Read the relevant files from `modes/`, `audiences/`, and `purposes/` to determine output format and behavior.

### Step 6 — Read the Template

Read the appropriate template from `templates/` and render the output using the knowledge model data.

---

## Project Knowledge Model

The knowledge model is the central data structure. Every output is derived from it.

### Schema

```yaml
knowledge_model:
  # Identity
  project_name: string
  repository_url: string          # if available
  license: string                 # if available

  # Purpose & Business Context
  purpose: string                 # one-paragraph description of what the project does
  business_domain: string         # e.g., "e-commerce", "fintech", "developer tools"
  target_users: string[]          # who uses the product
  stakeholders: string[]          # who has a vested interest
  value_proposition: string       # what makes this project valuable

  # Product
  product_summary: string         # 2-3 sentence product overview
  key_features: string[]          # list of major features
  user_flows: string[]            # primary user journeys (inferred)

  # Architecture
  architecture_summary: string    # 2-3 sentence architecture overview
  architecture_pattern: string    # e.g., "monolith", "microservices", "event-driven"
  technology_stack:
    language: string[]            # primary programming languages
    framework: string[]           # frameworks used
    database: string[]            # databases
    infrastructure: string[]      # cloud, CI/CD, hosting
    tooling: string[]             # linters, formatters, bundlers, etc.
  major_modules:                  # top-level components
    - name: string
      path: string
      purpose: string
      status: string              # "implemented" | "partial" | "planned"

  # Implementation Status
  implementation_status:
    overall_completion: string    # rough percentage or status
    completed_features: string[]  # features that appear complete
    in_progress_features: string[]
    planned_features: string[]
    test_coverage: string         # observed or inferred

  # Constraints & Risks
  known_constraints: string[]
  technical_debt: string[]
  risks: string[]
  assumptions: string[]           # explicit acknowledgment of unverified info

  # Inferred Information
  inferred:                      # clearly separated from observed facts
    team_size: string             # estimated
    development_phase: string     # e.g., "early development", "production"
    coding_standards: string[]    # observed patterns
    third_party_integrations: string[]

  # Metadata
  analysis_metadata:
    analysis_level: string        # quick | standard | deep
    mode: string
    audience: string
    purpose: string
    files_inspected: number
    timestamp: string              # ISO 8601
    confidence: string            # high | medium | low
```

### Inference Rules

When information is not directly available, the agent may **infer** it, but must:

1. Clearly label it under the `inferred` section.
2. State the evidence that supports the inference.
3. Use cautious language: "appears to", "likely", "based on the presence of...".
4. Never present an inference as a fact.

---

## Repository Layout

```
code-atlas/
├── skill.md                  # This file — entry point for AI agents
├── README.md                  # Human-facing documentation
├── LICENSE
├── CONTRIBUTING.md
├── configs/
━   ├── defaults.md            # Default configuration values
━   └── analysis-levels/
━       ├── quick.md
━       ├── standard.md
━       └── deep.md
├── modes/
━   ├── overview.md
━   ├── product.md
━   ├── architecture.md
━   ├── progress.md
━   ├── infrastructure.md
━   ├── resume.md
━   ├── ai-context.md
━   ├── review.md
━   └── full-documentation.md
├── audiences/
━   ├── developer.md
━   ├── product-manager.md
━   ├── executive.md
━   ├── recruiter.md
━   ├── client.md
━   ├── investor.md
━   └── ai-agent.md
├── purposes/
━   ├── understand.md
━   ├── document.md
━   ├── review.md
━   ├── improve.md
━   └── pitch.md
├── templates/
━   ├── project-overview.md
━   ├── product-overview.md
━   ├── architecture-summary.md
━   ├── resume-description.md
━   ├── company-description.md
━   ├── client-description.md
━   ├── portfolio-description.md
━   ├── feature-catalog.md
━   ├── roadmap.md
━   ├── llm-context.md
━   └── project-review.md
├── docs/
━   ├── installation.md
━   ├── usage.md
━   ├── configuration.md
━   ├── architecture.md
━   ├── developer-guide.md
━   ├── best-practices.md
━   └── migration.md
├── examples/
━   ├── quick-overview-developer.md
━   ├── deep-aicontext-aiagent.md
━   ├── standard-resume-recruiter.md
━   ├── quick-product-client.md
━   ├── deep-review-pm.md
━   └── standard-fulldoc-executive.md
└── outputs/
    └── .gitkeep
```

---

## Compositional Design

Code Atlas uses a compositional architecture where the final output is determined by combining four independent dimensions:

```
Output = AnalysisLevel + Mode + Audience + Purpose + Template
```

Each dimension is defined in its own directory and can be extended independently:

- Add a new **analysis level** in `configs/analysis-levels/`
- Add a new **mode** in `modes/`
- Add a new **audience** in `audiences/`
- Add a new **purpose** in `purposes/`
- Add a new **template** in `templates/`

No existing files need to be modified when extending.

---

## Token Budget Guidelines

| Analysis Level | Approx. Input Tokens | Approx. Output Tokens |
|----------------|---------------------|----------------------|
| Quick          | 5,000 - 15,000      | 500 - 1,500          |
| Standard       | 15,000 - 50,000     | 1,500 - 5,000        |
| Deep           | 50,000 - 200,000+   | 5,000 - 20,000+      |

These are rough estimates. Actual usage depends on repository size and complexity.

---

## Supported AI Platforms

Code Atlas is designed to work with any AI coding agent that can read Markdown files and follow structured instructions, including but not limited to:

- Claude Code
- OpenAI Codex
- Gemini CLI
- Cursor
- Windsurf
- Cline
- Roo Code
- MiniMaxCode
- Any LLM capable of following Markdown instructions

The skill is intentionally model-agnostic. It avoids vendor-specific features, APIs, or file formats.

---

## Version

**1.0.0**
