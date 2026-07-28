# Project Review Template

> Render this template using data from the Project Knowledge Model.

---

## Template Metadata

| Field | Value |
|-------|-------|
| Template Name | Project Review |
| Intended Use | Quality evaluation and actionable recommendations |
| Typical Length | 600 - 3,000 words |
| Compatible Modes | review |
| Compatible Audiences | developer, product-manager, executive |

---

## Required Sections

### 1. Overall Assessment

```markdown
# {project_name} — Project Review

## Overall Assessment

**Grade**: {A/B/C/D/F or equivalent maturity level}

{one-paragraph justification for the grade}
```

Provide a balanced overall assessment. Consider code quality, architecture, testing, documentation, and process maturity. The grade should reflect the project's current state relative to industry best practices for its type and size.

---

### 2. Strengths

```markdown
## Strengths

1. **{strength}**: {specific evidence}
2. **{strength}**: {specific evidence}
3. **{strength}**: {specific evidence}
```

3-5 things the project does well. Every strength must be supported by specific evidence (file names, patterns observed, or configurations found). Do not give generic praise.

---

### 3. Critical Issues

```markdown
## Critical Issues

### {issue_title}
- **Severity**: Critical
- **Evidence**: {file or pattern where the issue was found}
- **Impact**: {what could go wrong}
- **Recommendation**: {specific action to take}
```

Issues that require immediate attention: security vulnerabilities, data loss risks, critical bugs, or fundamental design flaws. Limit to genuine critical issues — do not inflate severity.

---

### 4. Major Issues

```markdown
## Major Issues

| # | Issue | Evidence | Impact | Recommendation |
|---|-------|----------|--------|---------------|
| 1 | {issue} | {file} | {impact} | {action} |
```

Significant problems that affect maintainability, performance, or reliability but are not immediately dangerous. Use table format for density.

---

### 5. Minor Issues

```markdown
## Minor Issues

- {issue}: {brief description and fix}
- {issue}: {brief description and fix}
```

Smaller problems: style inconsistencies, missing documentation, minor code smells. Group related issues rather than listing each individually.

---

### 6. Testing Assessment

```markdown
## Testing Assessment

**Framework**: {observed testing framework}
**Coverage**: {observed or inferred coverage level}
**Quality**: {assessment of test quality}
**Gaps**: {untested areas}
```

Specific evaluation of the testing practices observed in the codebase.

---

### 7. Prioritized Recommendations

```markdown
## Recommendations

| Priority | Action | Effort | Impact |
|----------|--------|--------|--------|
| 1 | {recommendation} | {low/medium/high} | {high/medium/low} |
```

Numbered, actionable improvement steps ordered by impact. Each recommendation should be specific enough that a developer could start working on it immediately.

---

## Optional Sections

### A. Quick Wins

```markdown
## Quick Wins

- {low-effort, high-impact improvement}
```

Include when the review identifies easy fixes that would noticeably improve the project.

---

## Rendering Rules

1. **Evidence is non-negotiable** — every finding must reference specific files, patterns, or configurations.
2. **Be specific** — "missing input validation in `src/api/users.ts`" not "insufficient validation."
3. **Be balanced** — acknowledge strengths alongside weaknesses.
4. **Calibrate to audience** — use a table for `executive`, detailed findings for `developer`.
5. **Do not exaggerate** — "major" issues are genuinely significant problems, not preferences.
6. Recommendations should reference the specific files that need to change.