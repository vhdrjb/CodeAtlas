# Developer Guide

This guide explains how to extend Code Atlas by creating new modes, audiences, purposes, templates, and analysis levels. Code Atlas is designed so that extensions never require modifying existing files.

---

## Creating a New Mode

A mode defines what the analysis focuses on. To create one:

1. Create a new file in `modes/` named after your mode: `modes/my-mode.md`.
2. Follow this structure:

```markdown
# Mode: {Mode Name}

**Purpose**: {one-line description}

---

## Objective
{2-3 sentences explaining what this mode does and when to use it}

## Analysis Scope
{bullet list of what the agent should focus on during analysis}

## Expected Inputs
{what configuration and repository characteristics are needed}

## Expected Outputs
{numbered list of sections the output should contain}

## Token Optimization Strategy
{how to keep the output efficient for this mode}

## Recommended Template
{which template from templates/ to use}

## Recommended Combinations
{table of useful audience + purpose pairings}
```

3. Optionally add the mode to the mapping table in `configs/defaults.md`.

**Design principles for modes**:
- Each mode should have a clear, distinct focus. If two modes overlap significantly, consider merging them.
- The analysis scope should be specific enough to guide the agent but flexible enough to work across different project types.
- Include a token optimization strategy — this helps the agent produce appropriately sized output.

---

## Creating a New Audience

An audience defines who the output is written for. To create one:

1. Create a new file in `audiences/` named after your audience: `audiences/my-audience.md`.
2. Follow this structure:

```markdown
# Audience: {Audience Name}

**Perspective**: {one-line description of the reader's viewpoint}

---

## Profile
{2-3 paragraphs describing who this audience is and when they would use Code Atlas}

## Tone and Style
{guidelines for how the output should sound}

## Terminology
{which terms to use, which to avoid, how to handle jargon}

## Detail Level
{how much detail each aspect of the project should receive}

## What to Emphasize
{what this audience cares about most}

## What to De-emphasize
{what this audience does not need to see}

## Recommended Analysis Levels
{which analysis levels work best for this audience}
```

**Design principles for audiences**:
- Audiences are about information filtering and presentation, not about adding new analysis. The same knowledge model feeds all audiences.
- Be specific about terminology. An audience definition that says "use technical language" is less useful than one that says "assume familiarity with REST, SQL, and Docker but explain Kubernetes concepts."

---

## Creating a New Purpose

A purpose defines why the analysis is being performed. To create one:

1. Create a new file in `purposes/` named after your purpose: `purposes/my-purpose.md`.
2. Follow this structure:

```markdown
# Purpose: {Purpose Name}

**Goal**: {one-line description of the behavioral goal}

---

## Description
{2-3 paragraphs explaining the purpose and its behavioral characteristics}

## Behavioral Characteristics
{bullet list of how the agent should behave under this purpose}

## Output Modifications
{specific changes to output format or content based on this purpose}

## Recommended Modes
{table of which modes work best with this purpose}
```

**Design principles for purposes**:
- Purposes modify the agent's behavior and output style, not the analysis scope.
- A purpose should be meaningfully different from existing purposes. If it overlaps, extend an existing one instead.

---

## Creating a New Template

A template defines the structure and content rules for the output. To create one:

1. Create a new file in `templates/` named descriptively: `templates/my-template.md`.
2. Start with template metadata:

```markdown
# {Template Name} Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | {Name} |
| Intended Use | {What this template produces} |
| Typical Length | {Word count range} |
| Compatible Modes | {Which modes can use this template} |
| Compatible Audiences | {Which audiences this template suits} |
```

3. Define sections as Required or Optional, with placeholder notation:

```markdown
## Required Sections

### 1. Section Title

```markdown
{template content with {placeholders}}
```

{instructions on what data to fill in}
```

4. Add rendering rules at the end:

```markdown
## Rendering Rules

{numbered list of rules for the AI agent when filling this template}
```

**Design principles for templates**:
- Use `{placeholder}` notation for knowledge model fields. The AI agent interprets these as instructions to insert data.
- Separate required from optional sections — this helps agents working under token constraints.
- Include rendering rules that address common mistakes.

---

## Creating a New Analysis Level

An analysis level defines how deeply the agent inspects the repository. To create one:

1. Create a new file in `configs/analysis-levels/` named descriptively: `configs/analysis-levels/my-level.md`.
2. Follow this structure:

```markdown
# Analysis Level: {Level Name}

**Optimized for**: {what this level is best suited for}

---

## Objective
{What this level aims to achieve}

## Scanning Strategy
### Files to Inspect
{priority-ordered list of files to read}

### Files to Skip
{what to exclude}

## Knowledge Model Scope
{which knowledge model fields to populate}

## Token Budget
{table with limits}

## Output Guidelines
{how to structure the output at this level}

## When to Use {Level Name}
{scenarios where this level is appropriate}
```

**Design principles for analysis levels**:
- Each level should have a clearly defined token budget that guides the agent's behavior.
- The scanning strategy should be specific enough that two agents following the same level would inspect roughly the same files.
- Knowledge model scope should be a subset of the full schema — deeper levels populate more fields.

---

## File Naming Conventions

- Mode files: `modes/{kebab-case-name}.md`
- Audience files: `audiences/{kebab-case-name}.md`
- Purpose files: `purposes/{kebab-case-name}.md`
- Template files: `templates/{kebab-case-name}.md`
- Analysis level files: `configs/analysis-levels/{kebab-case-name}.md`

Use kebab-case (lowercase with hyphens). Do not use spaces, underscores, or camelCase.

---

## Testing Your Extension

After creating a new file, test it by instructing an AI agent:

```
Read /path/to/CodeAtlas/skill.md.
Analyze /path/to/test-project with:
- Mode: {your-new-mode}
- Audience: {your-new-audience}  (if applicable)
- Purpose: {your-new-purpose}  (if applicable)
- Analysis level: {your-new-level}  (if applicable)
```

Verify the output:
1. Follows the structure you defined.
2. Uses the tone and terminology you specified.
3. Respects the token optimization strategy.
4. Produces output of the expected length.

---

## Contribution Checklist

Before submitting a new extension, ensure:

- [ ] The file follows the structure template for its type.
- [ ] No existing files were modified.
- [ ] The file is well-formatted Markdown with no syntax errors.
- [ ] The content is original and not duplicated from other files.
- [ ] The file uses consistent terminology with the rest of Code Atlas.
- [ ] You have tested the extension with at least one real project.
- [ ] You have updated `configs/defaults.md` if adding a new mode that needs a template mapping.