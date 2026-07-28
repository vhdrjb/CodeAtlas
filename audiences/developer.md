# Audience: Developer

**Perspective**: Technical peer who will read, maintain, or extend the codebase.

---

## Profile

Developers are technically proficient readers who need accurate, specific, and actionable information. They are comfortable with technical terminology, code references, and architectural diagrams. They value precision over simplification and detail over brevity — but they still appreciate well-organized, scannable content.

Developers reading Code Atlas output typically fall into one of these scenarios:

- **New team member** onboarding onto an existing project.
- **Contractor or consultant** evaluating a codebase before beginning work.
- **Open-source contributor** understanding a project before submitting a PR.
- **Tech lead** reviewing a team's project for standards compliance.

---

## Tone and Style

- **Technical but not academic**. Use correct terminology but avoid unnecessarily formal language.
- **Specific over general**. Prefer "The auth module uses JWT tokens with RS256 signing" over "The project has authentication."
- **Action-oriented**. Tell the developer what they need to know to do their job.
- **Honest about uncertainty**. If something is inferred, say so. Developers respect transparency.
- **Include file paths**. Developers navigate by file paths — always reference them.

---

## Terminology

Use standard engineering terminology. Assume familiarity with:

- Common software patterns (MVC, repository, observer, etc.)
- Version control concepts (branches, merges, rebasing)
- Build and dependency management concepts
- Testing terminology (unit, integration, e2e, mocking)
- Web concepts (REST, GraphQL, middleware, caching)

Do not explain these concepts unless the project uses them in a non-standard way.

---

## Detail Level

- **Architecture**: Full detail — module relationships, design patterns, data flow.
- **Implementation**: Moderate detail — key abstractions and interfaces, not every function.
- **Infrastructure**: Moderate detail — enough to deploy and debug.
- **Business context**: Brief — what the project does and why, but no market analysis.
- **Testing**: Moderate detail — testing strategy, framework, and conventions.

---

## What to Emphasize

- File paths and module locations.
- Technology versions and configuration.
- Code conventions and patterns to follow.
- Common pitfalls and things that break.
- How to build, test, and run the project.
- Inter-module dependencies and interfaces.

---

## What to De-emphasize

- Business justification and market positioning.
- User experience descriptions.
- Project history and team background.
- Competitive analysis.
- Investment or financial information.

---

## Recommended Analysis Levels

- **Standard**: Best for most developer use cases — enough detail without excessive token use.
- **Deep**: Best for onboarding or when the developer will make significant changes.
- **Quick**: Suitable for a quick orientation before a small task.