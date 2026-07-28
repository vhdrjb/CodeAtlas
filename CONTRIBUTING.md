# Contributing to Code Atlas

Thank you for your interest in contributing to Code Atlas! This guide explains how to contribute effectively.

---

## Types of Contributions

Code Atlas welcomes the following types of contributions:

- **New modes** — Focus areas for project analysis (e.g., security, performance, compliance).
- **New audiences** — Reader types that change how output is written (e.g., designer, student, legal).
- **New purposes** — Behavioral goals that change the agent's approach (e.g., audit, migrate, teach).
- **New templates** — Output format definitions for new use cases.
- **New analysis levels** — Scanning depth profiles for different scenarios.
- **Bug fixes** — Corrections to existing files (typos, inaccuracies, unclear instructions).
- **Documentation improvements** — Better explanations, clearer examples, additional guides.

---

## Before You Start

1. **Read the existing files** — Familiarize yourself with at least 2-3 files in the dimension you want to contribute to. Understand the conventions, structure, and level of detail.
2. **Read the Developer Guide** — The [Developer Guide](docs/developer-guide.md) explains the structure and conventions for each type of file.
3. **Check for existing proposals** — Search open issues and pull requests to see if someone has already proposed or started the same contribution.
4. **Consider the compositional design** — Your contribution should be a new file that composes with existing files, not a modification to existing behavior.

---

## Making a Contribution

### Step 1: Fork and Clone

```bash
git clone https://github.com/your-username/CodeAtlas.git
cd CodeAtlas
```

### Step 2: Create a Branch

```bash
git checkout -b add/{type}/{name}
# Examples:
# add/mode/security
# add/audience/designer
# add/template/api-documentation
```

### Step 3: Create Your File

Follow the structure template for your contribution type. See the [Developer Guide](docs/developer-guide.md) for detailed structure specifications.

### Step 4: Test Your Contribution

Instruct an AI agent to use your new file:

```
Read the Code Atlas skill file at ./skill.md.
Analyze /path/to/test-project with mode: {your-new-mode}.
```

Verify the output:
- Follows the structure you defined
- Uses the tone and terminology you specified
- Respects the token optimization strategy
- Is useful and coherent

### Step 5: Commit

```bash
git add {your-new-file}
git commit -m "feat({type}): add {name} {brief description}"
```

Commit message format:
- `feat(modes): add security mode for vulnerability assessment`
- `feat(audiences): add designer audience for UX-focused output`
- `fix(templates): correct rendering rules in project-review.md`
- `docs: improve configuration guide with token estimates`

### Step 6: Submit a Pull Request

Push to your fork and open a pull request against the `main` branch. Include:

- **What** you are adding and why
- **How** you tested it
- **Which example** demonstrates its use (if applicable)

---

## Contribution Guidelines

### Quality Standards

- **No placeholders** — every section must have real, meaningful content.
- **No duplication** — do not repeat content that exists in other files. Reference them instead.
- **Consistent terminology** — use the same terms as existing files in the same dimension.
- **Production quality** — the file should be immediately usable by anyone who clones the repository.

### Design Principles

- **Composition over modification** — your contribution should be a new file, not a change to existing files (except `configs/defaults.md` for template mappings).
- **Self-contained** — each file should be understandable without reading other files.
- **Audience-aware** — consider who will read your file (humans configuring Code Atlas, and AI agents following its instructions).

### What Needs Review

You do need to update `configs/defaults.md` if:
- You are adding a new **mode** that needs a default template mapping.

You do **not** need to update any existing file if:
- You are adding a new audience, purpose, template, or analysis level.

---

## Reporting Issues

If you find a problem with Code Atlas:

1. Check if the issue has already been reported in [GitHub Issues](https://github.com/vhdrjb/CodeAtlas/issues).
2. If not, open a new issue with:
   - **Description** — what is wrong and what you expected
   - **Reproduction** — the configuration you used and the target project type
   - **Agent** — which AI agent you used (Claude Code, Cursor, etc.)
   - **Model** — which model (if relevant to the issue)

---

## Code of Conduct

- Be respectful and constructive in all interactions.
- Focus on the contribution, not the contributor.
- Provide actionable feedback during reviews.
- Assume good intent.

---

## License

By contributing to Code Atlas, you agree that your contribution will be licensed under the [MIT License](LICENSE).
