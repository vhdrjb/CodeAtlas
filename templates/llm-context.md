# LLM Context Template

> Render this template using data from the Project Knowledge Model.
> This is the most token-dense template. Every token must earn its place.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | LLM Context |
| Intended Use | AI agent context for code modifications |
| Typical Length | 1,500 - 8,000 tokens |
| Compatible Modes | ai-context |
| Compatible Audiences | ai-agent |

---

## Required Sections

### 1. Project Summary

```
PROJECT: {project_name}
PURPOSE: {purpose} (max 50 words)
STACK: {language} + {framework} + {database}
PATTERN: {architecture_pattern}
```

Maximum 3 lines. No prose. Source from `knowledge_model.purpose`, `knowledge_model.technology_stack`, `knowledge_model.architecture_pattern`.

---

### 2. Directory Map

```
{project_root}/
├── {dir1}/          # {one-line purpose}
│   ├── {file}      # {one-line purpose}
│   └── {file}      # {one-line purpose}
├── {dir2}/          # {one-line purpose}
└── {file}          # {one-line purpose}
```

Tree representation of the project structure with purpose annotations on every entry. Source from directory analysis. Include paths that an AI agent would need to navigate. Omit test directories unless they contain shared test utilities.

---

### 3. Module Index

```
## {module_name} ({path})
Purpose: {one-line purpose}
Key exports: {export1}, {export2}, {export3}
Depends on: {module1}, {module2}
```

For each major module. Include the specific functions, classes, or types that are exported and likely to be imported by other modules. This is the most critical section for preventing import errors.

---

### 4. Conventions

```
NAMING: {observed naming pattern — e.g., camelCase for functions, PascalCase for components}
FILES: {file organization rules — e.g., one component per file, co-located tests}
TESTS: {test location and naming — e.g., __tests__/ directory, .test.ts suffix}
STYLES: {CSS/styling approach — e.g., Tailwind utility classes, CSS Modules}
STATE: {state management approach — e.g., React Context, Redux, Zustand}
```

Observed coding conventions. Be specific and prescriptive. Use exact patterns observed in the code. This section directly prevents the AI agent from introducing inconsistencies.

---

### 5. Entry Points

```
ENTRY: {file path} — {what it does}
ROUTE: {how requests reach the application}
FLOW: {request} -> {middleware/handler} -> {service} -> {data store}
```

How the application starts and how requests flow through the system. Include the main entry file and the primary request processing chain.

---

### 6. Key Types

```
// {file_path}
type {TypeName} = {
  {field}: {type}  // {purpose}
}
```

Important type definitions, interfaces, or schemas that the AI agent will encounter frequently. Only include types that are imported across multiple modules or appear in function signatures the agent is likely to modify.

---

### 7. Testing Guide

```
FRAMEWORK: {testing framework}
RUN: {exact command to run tests}
LOCATION: {where tests live}
NAMING: {test file naming convention}
```

Minimal testing information — just what the AI agent needs to run tests and write new ones that match the existing pattern.

---

### 8. Modification Guidelines

```
DO:
- {specific rule based on observed patterns}
- {rule}

DON'T:
- {anti-pattern to avoid}
- {common mistake specific to this codebase}
```

Specific do's and don'ts for this codebase. This is the most valuable section for preventing mistakes. Base every rule on specific observations from the codebase.

---

## Rendering Rules

1. **Maximum density** — use structured formats, not prose. Every word should carry information.
2. **Absolute file paths** — always use paths relative to the project root.
3. **No business context** — omit all product, market, and user information.
4. **No implementation status** — omit what is complete/incomplete unless it affects what the AI should modify.
5. **No redundancy** — if something is stated once, do not restate it.
6. **Prescriptive language** — use imperative mood ("use", "import from", "follow").
7. **Token target**: 1,500-3,000 tokens for `standard`, 3,000-8,000 for `deep`.