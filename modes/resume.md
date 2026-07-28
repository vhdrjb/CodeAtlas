# Mode: Resume

**Purpose**: Generate project descriptions suitable for resumes, portfolios, and professional profiles.

---

## Objective

The Resume mode transforms project analysis into polished, achievement-oriented descriptions designed for resumes, LinkedIn profiles, portfolios, and job applications. It answers the question: "How do I describe this project to a potential employer or client?" This mode deliberately reframes technical work in terms of impact, scale, and responsibility.

Unlike other modes that serve the project's stakeholders, this mode serves the **developer's** professional interests. It extracts the most impressive aspects of the project — complex problems solved, technologies mastered, scale achieved — and presents them in the concise, action-oriented format that recruiters and hiring managers expect.

---

## Analysis Scope

- **Project Identity**: Name and one-line description that sounds impressive yet accurate.
- **Technical Achievements**: Notable engineering challenges, clever solutions, and architectural decisions.
- **Technology Demonstrated**: Languages, frameworks, and tools used — emphasizing breadth and modern stack.
- **Scale Indicators**: Any evidence of scale — user counts, data volumes, performance metrics, or complex integrations.
- **Responsibility Scope**: What the developer likely owned — full stack, backend, frontend, infrastructure, or specific modules.
- **Business Impact**: How the project affects end users or the business — measured outcomes where available.
- **Collaboration Signals**: Evidence of teamwork — contribution guidelines, code review setup, team conventions.
- **Complexity Indicators**: Difficult problems solved — real-time features, distributed systems, security requirements, compliance.

---

## Expected Inputs

- The repository to analyze.
- Optionally, the developer's specific role or contributions (if they were part of a larger team).
- The target resume format (bullet points vs. paragraph) can be specified by the audience selection.

---

## Expected Outputs

1. **One-Liner** — A single sentence describing the project for a resume bullet point or LinkedIn headline.
2. **Short Description** — 2-3 sentence paragraph suitable for a project section.
3. **Bullet Points** — 3-5 achievement-oriented bullet points using action verbs.
4. **Technical Keywords** — Comma-separated list of technologies for ATS optimization.
5. **Scale and Impact** — Quantifiable metrics or evidence of project significance.
6. **Long Description** — A fuller narrative suitable for a portfolio page or cover letter.

---

## Token Optimization Strategy

- Prioritize impact and outcome over process description.
- Use action verbs consistently (built, designed, implemented, optimized, led).
- Quantify wherever possible — even inferred numbers are better than none.
- Avoid internal jargon or project-specific terminology that a recruiter would not understand.
- Do not include negative information (missing tests, technical debt) unless reframed as improvement opportunities led by the developer.
- Keep the output concise: recruiters spend seconds per entry.

---

## Recommended Template

`templates/resume-description.md`

---

## Recommended Combinations

| Audience | Purpose | Why It Works |
|----------|---------|--------------|
| Recruiter | Pitch | Directly optimized for how recruiters scan resumes. |
| Client | Pitch | Client sees the developer's capability through project evidence. |
| Developer | Document | Developer builds their own portfolio content. |
| Executive | Pitch | Executive summary of a developer's project for a bio. |
