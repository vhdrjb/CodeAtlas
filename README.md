<p align="center">
  <strong>Code Atlas</strong><br>
  AI-powered project intelligence for developers, AI agents, and teams
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-1.0.0-blue" alt="Version">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="License">
  <img src="https://img.shields.io/badge/platforms-Claude%20Code%20%7C%20Cursor%20%7C%20Windsurf%20%7C%20Cline%20%7C%20Codex%20%7C%20Gemini%20CLI-orange" alt="Platforms">
</p>

---

## What is Code Atlas?

Code Atlas is a **model-agnostic AI skill** that helps AI coding agents understand a software project before making changes. It builds an internal Project Knowledge Model from both business and engineering perspectives, then generates targeted documentation based on the configuration you select.

It does **not** generate code. It generates **understanding**.

Think of it as a combination of a Product Manager, Software Architect, Technical Writer, Business Analyst, and Engineering Manager — all focused on understanding your project and communicating that understanding clearly.

---

## Why Code Atlas?

AI coding agents are powerful, but they make mistakes when they don't understand the project they are modifying. Code Atlas solves this by giving the agent a structured, comprehensive understanding of the project — its purpose, architecture, conventions, and current state — before any code is written.

**Core principles**:

- **Understand before modifying** — never suggest changes without comprehending the existing structure
- **Inspect before assuming** — read actual source files, don't guess
- **Separate facts from inferences** — clearly distinguish between what is observed and what is deduced
- **Optimize for AI context efficiency** — every word earns its place
- **Support lightweight and deep analysis** — from 5 files to the entire repository

---

## Features

- **3 Analysis Levels** — Quick (5-10 files), Standard (20-40 files), Deep (all files)
- **9 Modes** — Overview, Product, Architecture, Progress, Infrastructure, Resume, AI Context, Review, Full Documentation
- **7 Audiences** — Developer, Product Manager, Executive, Recruiter, Client, Investor, AI Agent
- **5 Purposes** — Understand, Document, Review, Improve, Pitch
- **11 Output Templates** — Structured formats for every use case
- **Project Knowledge Model** — Single source of truth for all generated output
- **Composable Architecture** — Any combination of level + mode + audience + purpose works
- **Zero Dependencies** — Pure Markdown, no installation or runtime required
- **Model Agnostic** — Works with any AI agent that can read Markdown instructions

---

## How It Works

```
Output = AnalysisLevel + Mode + Audience + Purpose + Template
```

Code Atlas operates in three phases:

1. **Discover** — Scan the repository structure, identify key files, extract configuration.
2. **Model** — Build an internal Project Knowledge Model capturing business context, architecture, technology, and state.
3. **Output** — Render the knowledge model into a formatted document using the selected template.

The AI agent reads `skill.md` as the entry point, then follows the configuration files to determine how deeply to analyze and what to produce.

---

## Quick Start

```bash
git clone https://github.com/vhdrjb/CodeAtlas.git
cd CodeAtlas
```

Then point your AI agent at the skill file:

```
Read the file at ./CodeAtlas/skill.md and analyze my project at /path/to/my-project.
```

That's it. No installation, no build step, no dependencies.

---

## Configuration

Code Atlas is configured through four independent dimensions:

| Dimension | Default | Options |
|-----------|---------|--------|
| Analysis Level | `standard` | `quick`, `standard`, `deep` |
| Mode | `overview` | 9 modes available |
| Audience | `developer` | 7 audiences available |
| Purpose | `understand` | 5 purposes available |

Override defaults in your prompt:

```
Analyze /path/to/my-project with:
- Analysis level: deep
- Mode: architecture
- Audience: developer
- Purpose: understand
```

See [Configuration Guide](docs/configuration.md) for full details.

---

## Common Use Cases

| Scenario | Configuration |
|----------|--------------|
| Quick project triage | `quick` + `overview` + `developer` |
| Generate AI agent context | `standard` + `ai-context` + `ai-agent` |
| Write resume descriptions | `standard` + `resume` + `recruiter` + `pitch` |
| Client status report | `standard` + `overview` + `client` + `document` |
| Code quality review | `standard` + `review` + `developer` + `review` |
| Full onboarding documentation | `deep` + `full-documentation` + `developer` + `document` |
| Investor due diligence | `deep` + `product` + `investor` + `pitch` |
| Pre-modification context | `standard` + `ai-context` + `ai-agent` |

---

## Examples

Realistic examples are provided in the [examples/](examples/) directory:

- [Quick + Overview + Developer](examples/quick-overview-developer.md) — Rapid project triage
- [Deep + AI Context + AI Agent](examples/deep-aicontext-aiagent.md) — Comprehensive AI agent context
- [Standard + Resume + Recruiter](examples/standard-resume-recruiter.md) — Resume-ready descriptions
- [Quick + Product + Client](examples/quick-product-client.md) — Client-friendly summaries
- [Deep + Review + PM](examples/deep-review-pm.md) — Quality review for product managers
- [Standard + Full Doc + Executive](examples/standard-fulldoc-executive.md) — Executive brief

---

## Repository Structure

```
code-atlas/
├── skill.md                  # Entry point for AI agents
├── README.md                  # This file
├── LICENSE                    # MIT License
├── CONTRIBUTING.md            # Contribution guide
├── configs/
│   ├── defaults.md            # Default configuration & precedence rules
│   └── analysis-levels/       # Scanning depth definitions
│       ├── quick.md           # 5-10 files, 5-15K input tokens
│       ├── standard.md        # 20-40 files, 15-50K input tokens
│       └── deep.md            # All files, 50-200K+ input tokens
├── modes/                     # What to focus on (9 modes)
│   ├── overview.md
│   ├── product.md
│   ├── architecture.md
│   ├── progress.md
│   ├── infrastructure.md
│   ├── resume.md
│   ├── ai-context.md
│   ├── review.md
│   └── full-documentation.md
├── audiences/                 # Who the output is for (7 audiences)
│   ├── developer.md
│   ├── product-manager.md
│   ├── executive.md
│   ├── recruiter.md
│   ├── client.md
│   ├── investor.md
│   └── ai-agent.md
├── purposes/                  # Why the analysis is done (5 purposes)
│   ├── understand.md
│   ├── document.md
│   ├── review.md
│   ├── improve.md
│   └── pitch.md
├── templates/                 # Output format definitions (11 templates)
│   ├── project-overview.md
│   ├── product-overview.md
│   ├── architecture-summary.md
│   ├── resume-description.md
│   ├── company-description.md
│   ├── client-description.md
│   ├── portfolio-description.md
│   ├── feature-catalog.md
│   ├── roadmap.md
│   ├── llm-context.md
│   └── project-review.md
├── docs/                      # Human-facing documentation
│   ├── installation.md
│   ├── usage.md
│   ├── configuration.md
│   ├── architecture.md
│   ├── developer-guide.md
│   ├── best-practices.md
│   └── migration.md
├── examples/                  # Realistic usage examples
│   ├── quick-overview-developer.md
│   ├── deep-aicontext-aiagent.md
│   ├── standard-resume-recruiter.md
│   ├── quick-product-client.md
│   ├── deep-review-pm.md
│   └── standard-fulldoc-executive.md
└── outputs/                   # Generated documents (git-ignored)
```

---

## Supported AI Platforms

Code Atlas is designed to work with any AI coding agent that can read Markdown files and follow structured instructions:

- [Claude Code](https://claude.ai/code)
- [OpenAI Codex](https://openai.com/codex)
- [Gemini CLI](https://github.com/google-gemini/gemini-cli)
- [Cursor](https://cursor.sh)
- [Windsurf](https://codeium.com/windsurf)
- [Cline](https://github.com/cline/cline)
- [Roo Code](https://github.com/RooVetGit/Roo-Code)
- [MiniMaxCode](https://www.minimaxi.com)
- Any LLM capable of following Markdown instructions

The skill is intentionally **model-agnostic**. It uses no vendor-specific APIs, tooling, or file formats.

---

## Architecture

Code Atlas uses a compositional architecture where behavior is determined by combining independent dimension files:

```
┌─────────┐  ┌──────┐  ┌──────────┐  ┌───────┐  ┌──────────┐
│Analysis │  │ Mode │  │ Audience │  │Purpose│  │ Template │
│  Level  │  │      │  │          │  │       │  │          │
└────┬────┘  └──┬───┘  └────┬─────┘  └──┬────┘  └────┬─────┘
     └─────────┴───────────┴────────────┴───────────┘
                           │
                           ▼
              Project Knowledge Model
              (Structured: facts + inferences)
                           │
                           ▼
                    Output Document
```

Key design decisions:

- **Pure Markdown** — no code to install, build, or execute. The AI agent is the runtime.
- **Compositional** — add new modes, audiences, purposes, or templates by creating files. No modifications to existing files needed.
- **Knowledge Model** — a single structured model feeds all outputs, ensuring consistency.
- **Flat directories** — each dimension is a directory of self-contained files.

See [Architecture Overview](docs/architecture.md) for the full technical design.

---

## Contributing

Contributions are welcome! Code Atlas is designed for easy extension:

1. Fork the repository
2. Create a new file in the appropriate directory (`modes/`, `audiences/`, `purposes/`, `templates/`, or `configs/analysis-levels/`)
3. Follow the structure and conventions documented in [Developer Guide](docs/developer-guide.md)
4. Test with at least one real project
5. Submit a pull request

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

---

## Documentation

| Document | Description |
|----------|-------------|
| [Installation](docs/installation.md) | Setup methods for all platforms |
| [Usage](docs/usage.md) | Common scenarios and practical examples |
| [Configuration](docs/configuration.md) | Detailed guide to all four dimensions |
| [Architecture](docs/architecture.md) | System design, data flow, and extensibility |
| [Developer Guide](docs/developer-guide.md) | How to create new modes, audiences, templates |
| [Best Practices](docs/best-practices.md) | Recommendations for real-world usage |
| [Migration Guide](docs/migration.md) | Version upgrade and backwards compatibility |

---

## License

[MIT](LICENSE) — free for personal and commercial use.

---

## Roadmap

- [ ] CLI wrapper for non-interactive usage
- [ ] VS Code extension with configuration UI
- [ ] Additional analysis levels (custom, targeted)
- [ ] Community-contributed modes and templates
- [ ] Multi-language support for outputs

---

## FAQ

**Does Code Atlas run code or execute anything on my machine?**
No. Code Atlas is entirely instruction-based. The AI agent reads Markdown files and follows the instructions. Nothing is installed, executed, or modified in your project.

**Does it work with [my specific AI tool]?**
If your tool can read Markdown files and follow structured instructions, yes. Code Atlas has no runtime dependencies.

**Can I use it for proprietary projects?**
Yes. The analysis happens within your AI agent's context. No code is sent to any external service (beyond what your AI agent itself sends).

**How is this different from just asking an AI to "analyze my project"?**
Code Atlas provides structured, consistent, reusable analysis. Without it, each AI query may focus on different aspects, miss important files, or produce inconsistent output. Code Atlas ensures thorough, repeatable analysis every time.

**Can I add my own mode or audience?**
Yes. Create a new Markdown file in the appropriate directory following the conventions in the [Developer Guide](docs/developer-guide.md). No existing files need to be modified.

**What about very large repositories?**
For large repositories, use the `standard` analysis level first. It focuses on core modules and key files. If you need comprehensive coverage, use `deep` with a large-context model (128K+ tokens).
