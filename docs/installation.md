# Installation

Code Atlas is a Markdown-based skill — it does not require installation in the traditional sense. You simply make the skill files available to your AI coding agent. Below are the recommended methods for different platforms and workflows.

---

## Method 1: Clone the Repository (Recommended)

The simplest approach is to clone the Code Atlas repository and reference the `skill.md` file when instructing your AI agent.

```bash
git clone https://github.com/vhdrjb/CodeAtlas.git
cd CodeAtlas
```

Then instruct your AI agent to read `skill.md`:

```
Read the file at ./CodeAtlas/skill.md and follow its instructions to analyze my project.
```

---

## Method 2: Add as a Submodule

If you want Code Atlas available within an existing project repository:

```bash
cd /path/to/your/project
git submodule add https://github.com/vhdrjb/CodeAtlas.git .code-atlas
```

Then reference it:

```
Read .code-atlas/skill.md and analyze this project in standard mode.
```

---

## Method 3: Copy to Your Agent's Skill Directory

Some AI agents have a built-in skill or instruction directory. Copy the relevant files there:

```bash
# Example: Claude Code
cp -r /path/to/CodeAtlas ~/.claude/skills/code-atlas/

# Example: Cursor rules
cp CodeAtlas/skill.md .cursor/rules/code-atlas.md
```

Consult your agent's documentation for the specific skill or rules directory location.

---

## Method 4: Direct Prompt Inclusion

For one-time use, you can paste the content of `skill.md` directly into your prompt:

```
Here is a skill definition. Follow its instructions:

{paste content of skill.md}

Now analyze the project at /path/to/my/project using standard mode.
```

This method uses more tokens but requires no file setup.

---

## Verification

After setting up Code Atlas, verify it works by asking your AI agent:

```
Read the Code Atlas skill file at {path/to/skill.md}. What are the available analysis levels, modes, audiences, and purposes?
```

The agent should list three analysis levels (quick, standard, deep), nine modes, seven audiences, and five purposes.

---

## Updating

To update to the latest version:

```bash
cd /path/to/CodeAtlas
git pull origin main
```

If using as a submodule:

```bash
git submodule update --remote .code-atlas
```

---

## Requirements

Code Atlas itself has no dependencies. However, your AI agent needs:

- **File system access**: The agent must be able to read files from the target repository.
- **Markdown parsing**: The agent must be able to read and follow Markdown instructions.
- **Sufficient context window**: At minimum 8,000 tokens for `quick` analysis. Recommended: 32,000+ for `standard`, 128,000+ for `deep`.

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Agent ignores skill instructions | Ensure the agent reads `skill.md` before being asked to analyze. Some agents need explicit instructions to read a file first. |
| Output is too shallow | Use `standard` or `deep` analysis level instead of `quick`. |
| Output is too long | Use `quick` analysis level or select a more focused mode. |
| Agent doesn't follow template | Verify the template file exists and is readable. Check the mode-to-template mapping in `configs/defaults.md`. |
| Output is in wrong language | The skill inherits the agent's language. Set language preferences in your agent's configuration. |