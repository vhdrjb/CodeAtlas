# Usage

This guide explains how to use Code Atlas to analyze a software project. Code Atlas works through a combination of configuration parameters that control the depth, focus, audience, and purpose of the analysis.

---

## Basic Usage

The simplest way to use Code Atlas is to point your AI agent at the skill file and a target project:

```
Read the Code Atlas skill file at /path/to/CodeAtlas/skill.md.
Then analyze the project at /path/to/my-project.
```

This uses all defaults: `standard` analysis level, `overview` mode, `developer` audience, `understand` purpose.

---

## Specifying Configuration

You can override any default by including the configuration in your prompt:

```
Read /path/to/CodeAtlas/skill.md.
Analyze the project at /path/to/my-project with:
- Analysis level: deep
- Mode: architecture
- Audience: developer
- Purpose: understand
```

---

## Common Scenarios

### Quick Project Triage

```
Read /path/to/CodeAtlas/skill.md.
Analyze /path/to/my-project with analysis level: quick, mode: overview.
```

Use this when you encounter an unfamiliar repository and want a rapid understanding before deciding whether to invest more time.

### Pre-Modification Context

```
Read /path/to/CodeAtlas/skill.md.
Analyze /path/to/my-project with mode: ai-context, analysis level: standard, audience: ai-agent.
```

Use this before asking an AI agent to make code changes. The agent will understand the project's conventions, structure, and patterns before writing any code.

### Resume Writing

```
Read /path/to/CodeAtlas/skill.md.
Analyze /path/to/my-project with mode: resume, audience: recruiter, purpose: pitch, analysis level: standard.
```

Use this to generate resume-ready descriptions of a project you have worked on.

### Code Review

```
Read /path/to/CodeAtlas/skill.md.
Analyze /path/to/my-project with mode: review, purpose: review, analysis level: standard, audience: developer.
```

Use this for a structured quality assessment of a project.

### Client Status Report

```
Read /path/to/CodeAtlas/skill.md.
Analyze /path/to/my-project with mode: overview, audience: client, purpose: document, analysis level: standard.
```

Use this to generate a client-friendly project summary.

### Full Documentation for Onboarding

```
Read /path/to/CodeAtlas/skill.md.
Analyze /path/to/my-project with mode: full-documentation, analysis level: deep, purpose: document, audience: developer.
```

Use this when onboarding a new team member or creating comprehensive project documentation.

---

## Understanding the Output

Every Code Atlas output includes an analysis metadata section at the end:

- **Analysis Level**: How deep the analysis went (quick, standard, deep).
- **Files Inspected**: How many files were read during analysis.
- **Confidence**: How confident the analysis is (high, medium, low).
- **Timestamp**: When the analysis was performed.

Information marked with `[Inferred]` was not directly stated in the codebase but was reasonably deduced from available evidence.

---

## Saving Output

To save the generated output to a file, instruct the agent:

```
Save the output to /path/to/CodeAtlas/outputs/{filename}.md
```

The `outputs/` directory is the designated location for generated documents.

---

## Chaining Analyses

You can run multiple analyses of the same project with different configurations:

```
Read /path/to/CodeAtlas/skill.md.

First, analyze /path/to/my-project with mode: architecture, analysis level: standard.
Then, analyze /path/to/my-project with mode: product, audience: product-manager.
```

The agent will build a fresh knowledge model for each analysis. For large projects, consider running a single `full-documentation` analysis instead, which covers all perspectives in one pass.

---

## Tips for Best Results

1. **Use the right analysis level**: `quick` for triage, `standard` for most tasks, `deep` for comprehensive documentation.
2. **Match audience to reader**: Select the audience that matches who will actually read the output.
3. **Be specific with purpose**: If you want recommendations, use `improve` purpose, not `understand`.
4. **Verify inferences**: Pay attention to `[Inferred]` tags and verify them if accuracy matters.
5. **Save outputs**: Generated analyses are valuable — save them for future reference.
6. **Iterate**: If the first output is too shallow, re-run with a deeper analysis level or more focused mode.