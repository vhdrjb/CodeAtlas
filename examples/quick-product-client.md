# Example: Quick + Product + Client

This example demonstrates generating a client-friendly product summary with minimal token investment. The combination of Quick analysis level, Product mode, and Client audience produces a concise, value-focused document suitable for a client status update or project brief.

---

## Prompt

```
Read the Code Atlas skill file at ./code-atlas/skill.md.

Analyze the project at /path/to/my-project with:
- Analysis level: quick
- Mode: product
- Audience: client
- Purpose: understand

Save the output to ./code-atlas/outputs/my-project-client-summary.md
```

---

## Expected Output

```markdown
# TaskFlow — Product Summary

TaskFlow is a team task management platform that helps your team organize work, assign responsibilities, and track progress across multiple projects in one place.

## Problem and Solution

**The Problem**: Teams need a centralized place to manage tasks, track who is working on what, and ensure nothing falls through the cracks. Scattered tools and email threads lead to missed deadlines and confusion.

**The Solution**: TaskFlow provides a single, organized workspace where team members can create projects, break them into tasks, assign them to team members, and track progress through completion.

## Target Users

**Team Leads and Managers**: Need visibility into team workload and project progress.

**Team Members**: Need a clear view of their assigned tasks and priorities.

## Key Features

1. **Project Management**: Create and organize work into projects with customizable settings.
2. **Task Tracking**: Create, assign, and track tasks through completion with clear status indicators.
3. **Team Collaboration**: Assign tasks to team members and manage roles (admin, manager, member).
4. **Secure Access**: Role-based access control ensures each team member sees only what they need.
5. **Third-Party Integrations**: Webhook support connects TaskFlow to your existing tools and workflows.
```

---

## When to Use This Combination

- Generating a client-facing project brief.
- Sending a quick status update to a non-technical stakeholder.
- Creating marketing or demo materials for a client.
- Any scenario where the reader needs to understand the product value without technical details.

## Token Estimate

- Input: ~8,000-12,000 tokens
- Output: ~600-1,000 tokens
- Total: ~9,000-13,000 tokens
