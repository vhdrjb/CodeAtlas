# Mode: AI Context

**Purpose**: Generate optimized context for AI coding agents that will modify the project.

---

## Objective

The AI Context mode produces a compact, high-signal document designed specifically to be fed to an AI coding agent as background context before it makes code changes. It answers the question: "What does an AI agent need to know about this project to make good changes?" This is the most token-optimized mode — every word must earn its place.

Unlike human-facing modes, this mode assumes the consumer is an LLM that can parse structured formats efficiently. It prioritizes information that prevents common AI mistakes: importing from wrong modules, using inconsistent patterns, breaking existing conventions, or misunderstanding the project's architecture. The output should be as dense and structured as possible.

---

## Analysis Scope

- **Project Identity and Purpose**: Brief — just enough for the AI to understand what it is modifying.
- **Directory Structure**: A complete but concise map of where things are.
- **Module Map**: What each major module does and what it exports.
- **Key Conventions**: Naming patterns, file organization rules, coding style observations.
- **Technology Stack**: Exact versions matter here — the AI needs to know which APIs are available.
- **Entry Points**: Where the application starts and how requests flow.
- **Type System**: Important type definitions, interfaces, and schemas the AI should know about.
- **Testing Conventions**: Where tests live, how they are named, what framework they use.
- **Common Patterns**: Recurring patterns (error handling, data access, state management) that the AI should replicate.
- **Pitfalls**: Things an AI commonly gets wrong in this type of project, based on the codebase's specific structure.

---

## Expected Inputs

- A full or near-full repository clone. This mode benefits significantly from `standard` or `deep` analysis levels.
- Type definition files, interface files, and schema definitions are high-priority inspection targets.
- Configuration files that define conventions (eslint, prettier, tsconfig, etc.).

---

## Expected Outputs

1. **Project Summary** — 2-3 sentences maximum.
2. **Tech Stack** — Structured list with versions where available.
3. **Directory Map** — Tree-like structure with purpose annotations.
4. **Module Index** — For each module: path, purpose, key exports, and dependencies.
5. **Conventions** — Naming, organization, and style rules observed in the codebase.
6. **Entry Points** — Application startup and request flow.
7. **Key Types** — Important interfaces, types, or schemas the AI will encounter.
8. **Testing Guide** — How to run tests, naming conventions, framework used.
9. **Modification Guidelines** — Specific do's and don'ts for this codebase.

---

## Token Optimization Strategy

- This is the most token-sensitive mode. Every section should use the most compact representation possible.
- Prefer structured formats (tables, lists, key-value pairs) over prose.
- Omit all business context, product descriptions, and stakeholder information.
- Omit implementation status and progress information unless it directly affects what the AI should or should not modify.
- Use absolute file paths for all references so the AI can navigate directly.
- Include file paths in the directory map so the AI does not need to discover them.
- Limit descriptions to what the AI needs to know to avoid mistakes, not to understand the project holistically.
- Target output size: 1,500-3,000 tokens for standard level, 3,000-8,000 for deep.

---

## Recommended Template

`templates/llm-context.md`

---

## Recommended Combinations

| Audience | Purpose | Why It Works |
|----------|---------|--------------|
| AI Agent | Understand | Primary use case — AI agent gets the context it needs. |
| AI Agent | Document | AI generates its own context file for future sessions. |
| AI Agent | Improve | AI understands current state before suggesting improvements. |
| Developer | Understand | Developer uses the AI-context output as a quick reference. |