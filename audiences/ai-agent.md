# Audience: AI Agent

**Perspective**: An LLM that will use the output as context for making code changes.

---

## Profile

AI agents are unique consumers of Code Atlas output. They do not "read" in the human sense — they process structured information as tokens. They benefit from dense, well-structured, unambiguous content. Redundancy wastes their context window. Ambiguity causes errors. Missing information causes hallucinations.

AI agents using Code Atlas are typically:

- **Coding assistants** (Claude Code, Cursor, Copilot) that need project context before generating or modifying code.
- **Automated review agents** that evaluate code quality or compliance.
- **Refactoring agents** that restructure code across multiple files.
- **Documentation agents** that generate or update project docs.

---

## Tone and Style

- **Dense and structured**. Every token should carry information. Avoid filler words, transitional phrases, and redundant explanations.
- **Unambiguous**. Use precise language. Avoid words like "similar," "various," or "several" — specify exactly.
- **Machine-readable formats**. Prefer tables, lists, and key-value pairs over prose. Use consistent formatting throughout.
- **Explicit over implicit**. State rules directly: "Always use Zod for input validation" rather than "The project tends to use Zod."
- **Path-anchored**. Reference everything by file path so the agent can navigate directly.

---

## Terminology

- Use exact identifiers: function names, class names, file paths, and configuration keys.
- Include technology names exactly as they appear in config files (case-sensitive).
- Avoid colloquial or metaphorical language — the agent takes things literally.
- If a term has a specific meaning in the project's context, define it explicitly.

---

## Detail Level

- **File paths and structure**: Maximum detail — the agent needs to know where everything is.
- **Module interfaces**: Maximum detail — what each module exports, expects, and depends on.
- **Conventions**: Maximum detail — naming patterns, file organization, coding style rules.
- **Type definitions**: High detail — important types, interfaces, and schemas.
- **Business context**: Minimal — only what the agent needs to avoid breaking product behavior.
- **Testing**: Moderate detail — how to run tests and naming conventions.

---

## What to Emphasize

- File paths and module boundaries.
- Import/export conventions and patterns.
- Naming conventions and coding rules.
- Type definitions and interfaces.
- Common patterns the agent should replicate.
- Things the agent should NOT do (pitfalls, anti-patterns).
- How to run tests and verify changes.

---

## What to De-emphasize

- Business context and market positioning.
- Project history and team background.
- User experience descriptions.
- Motivational or explanatory prose.
- Any information that does not directly help the agent write correct code.
- Redundant information (stating the same thing in multiple ways).

---

## Recommended Analysis Levels

- **Standard**: Best for most AI agent use cases — sufficient context without excessive tokens.
- **Deep**: Best for complex projects where the agent needs maximum context.
- **Quick**: Suitable for simple tasks on well-understood projects.