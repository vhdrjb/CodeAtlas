# Configuration Guide

Code Atlas is configured through four independent dimensions: analysis level, mode, audience, and purpose. These dimensions compose to produce the final output. This guide explains each dimension and how they interact.

---

## The Four Dimensions

```
Output = AnalysisLevel + Mode + Audience + Purpose + Template
```

Each dimension is defined in its own directory and can be selected independently:

| Dimension | Directory | Default | Options |
|-----------|-----------|---------|--------|
| Analysis Level | `configs/analysis-levels/` | `standard` | `quick`, `standard`, `deep` |
| Mode | `modes/` | `overview` | 9 modes available |
| Audience | `audiences/` | `developer` | 7 audiences available |
| Purpose | `purposes/` | `understand` | 5 purposes available |

---

## Analysis Levels

Analysis levels control **how deeply** the agent inspects the repository.

### Quick

- **Files inspected**: 5-10
- **Input tokens**: 5,000-15,000
- **Output tokens**: 500-1,500
- **Best for**: Free-tier models, rapid triage, batch evaluation

Quick analysis reads only the most important files: package manifest, README, key configuration, and the main entry point. It produces a concise summary suitable for deciding whether to invest more analysis time.

### Standard (Recommended)

- **Files inspected**: 20-40
- **Input tokens**: 15,000-50,000
- **Output tokens**: 1,500-5,000
- **Best for**: Most use cases, documentation, pre-modification context

Standard analysis provides a balanced understanding. It inspects core modules, routing, key business logic, and configuration. It produces a comprehensive output suitable for most purposes.

### Deep

- **Files inspected**: All relevant
- **Input tokens**: 50,000-200,000+
- **Output tokens**: 5,000-20,000+
- **Best for**: Comprehensive documentation, due diligence, onboarding

Deep analysis reads the entire repository. It captures inter-module dependencies, data flows, code quality patterns, and testing practices. It requires a large-context model and produces the most thorough output.

---

## Modes

Modes control **what the analysis focuses on**.

| Mode | Focus | Best Template |
|------|-------|--------------|
| `overview` | General project summary | `project-overview.md` |
| `product` | Business and product perspective | `product-overview.md` |
| `architecture` | Technical architecture | `architecture-summary.md` |
| `progress` | Implementation status | `roadmap.md` |
| `infrastructure` | Deployment and operations | `architecture-summary.md` |
| `resume` | Professional descriptions | `resume-description.md` |
| `ai-context` | AI agent context | `llm-context.md` |
| `review` | Quality evaluation | `project-review.md` |
| `full-documentation` | Comprehensive documentation | `project-overview.md` |

Each mode file defines its own analysis scope, expected outputs, and token optimization strategy. See the individual files in `modes/` for details.

---

## Audiences

Audiences control **who the output is written for**. The same analysis will produce very different text for a developer versus an executive.

| Audience | Tone | Detail Level |
|----------|-------|-------------|
| `developer` | Technical, specific, action-oriented | High (technical) |
| `product-manager` | Business-oriented, feature-centric | Moderate |
| `executive` | Concise, strategic, outcome-focused | Minimal |
| `recruiter` | Professional, keyword-rich | High (keywords) |
| `client` | Professional, confidence-inspiring | Moderate |
| `investor` | Strategic, evidence-based | Moderate |
| `ai-agent` | Dense, structured, path-anchored | Maximum (technical) |

Each audience file defines its own terminology preferences, emphasis rules, and recommended analysis levels. See the individual files in `audiences/` for details.

---

## Purposes

Purposes control **why the analysis is being performed**. The purpose changes the behavioral characteristics of the output.

| Purpose | Behavior |
|---------|----------|
| `understand` | Maximize clarity and accuracy |
| `document` | Produce polished, publication-ready output |
| `review` | Adopt a critical, evaluative stance |
| `improve` | Generate actionable improvement plans |
| `pitch` | Present the project compellingly |

Each purpose file defines behavioral modifications and recommended mode pairings. See the individual files in `purposes/` for details.

---

## Precedence Rules

When configuration dimensions conflict, the following precedence applies:

1. **Explicit user instruction** — always wins
2. **Mode defaults** — a mode may override global defaults
3. **Purpose defaults** — a purpose may further tune behavior
4. **Audience defaults** — an audience adjusts tone and detail
5. **Global defaults** — baseline from `configs/defaults.md`

---

## Mode-to-Template Mapping

When no template is explicitly specified, Code Atlas uses this mapping:

| Mode | Default Template |
|------|-----------------|
| overview | `project-overview.md` |
| product | `product-overview.md` |
| architecture | `architecture-summary.md` |
| progress | `roadmap.md` |
| infrastructure | `architecture-summary.md` |
| resume | `resume-description.md` |
| ai-context | `llm-context.md` |
| review | `project-review.md` |
| full-documentation | `project-overview.md` |

---

## Custom Configuration

You can override any configuration by specifying it directly in your prompt to the AI agent. The agent will use your explicit instruction over the file-based defaults.

For persistent customization, you can create your own configuration files that extend the defaults. See the [Developer Guide](developer-guide.md) for instructions on extending Code Atlas.
