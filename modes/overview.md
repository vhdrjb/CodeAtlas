# Mode: Overview

**Purpose**: Provide a comprehensive yet concise summary of the entire project.

---

## Objective

The Overview mode is the default and most versatile analysis mode. It produces a general-purpose project summary that covers the essential aspects of a software project from both business and engineering perspectives. This mode is designed to answer the question: "What is this project, and how is it built?" The output should give any reader — technical or non-technical — a solid foundational understanding of the project within a single document.

The overview should be self-contained. A reader should not need to reference the source repository to grasp what the project does, how it is structured, and what technologies power it. This mode prioritizes breadth of coverage over depth in any single area.

---

## Analysis Scope

- **Project Identity**: Name, description, repository URL, license, and version information extracted from package manifests and documentation files.
- **Business Context**: Purpose, business domain, target users, and value proposition — drawn from README, documentation, and inferred from code structure.
- **Technology Stack**: Primary languages, frameworks, databases, and infrastructure tooling — identified from configuration files and dependency manifests.
- **Module Structure**: Top-level modules and directories with a brief description of each — derived from directory structure and key source files.
- **Implementation Status**: Overall completion level and which major features appear to be implemented, in progress, or planned.
- **Key Observations**: Notable design decisions, patterns, or characteristics that stand out during analysis.

---

## Expected Inputs

- A valid repository with at least a package manifest and a README or equivalent documentation file.
- The selected analysis level determines how many files are inspected (quick: 5-10, standard: 20-40, deep: all relevant).
- No additional user input is required beyond the repository path or URL.

---

## Expected Outputs

The output document should contain these sections:

1. **Project Identity** — Name, URL, license, and one-line description.
2. **Purpose** — A paragraph explaining what the project does and why it exists.
3. **Technology Stack** — A table or structured list of languages, frameworks, databases, and tooling.
4. **Architecture Pattern** — Identified pattern (monolith, microservices, etc.) with a brief justification.
5. **Module Overview** — A list of major modules with name, path, purpose, and status.
6. **Implementation Status** — Summary of what is built, what is in progress, and what appears planned.
7. **Key Observations** — 3-5 notable findings or characteristics.
8. **Confidence Note** — Which areas were directly observed vs. inferred.

---

## Token Optimization Strategy

- Prioritize breadth over depth. Every major aspect should be covered, but none in exhaustive detail.
- Use bullet points and structured lists instead of long paragraphs.
- Limit each module description to 1-2 lines.
- Omit individual dependency listings unless they reveal something notable about the project.
- Do not include code snippets, file contents, or line-level details.
- Use tables for the technology stack to compress information.
- If the analysis level is `quick`, further reduce the output to just sections 1, 3, 5, and 7.

---

## Recommended Template

`templates/project-overview.md`

---

## Recommended Combinations

| Audience | Purpose | Why It Works |
|----------|---------|--------------|
| Developer | Understand | Developer gets a quick technical grounding in the project. |
| Developer | Document | Produces a solid reference document for the team. |
| AI Agent | Understand | Gives the AI agent a broad map of the project before deeper work. |
| Executive | Understand | Non-technical readers get a high-level picture without jargon. |
| Product Manager | Understand | PM sees both the product and technical sides in one view. |
