# Skills

A collection of custom skills built on the open [Agent Skills](https://agentskills.io) standard.

These skills work with any compatible agent, including:

- [Claude Code](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) and Claude API
- [OpenAI Codex](https://developers.openai.com/codex/skills/)
- [GitHub Copilot](https://github.blog/changelog/2025-12-18-github-copilot-now-supports-agent-skills/)
- [Cursor](https://cursor.com/docs/context/skills) (nightly channel)

## Available Skills

| Skill | Description |
|-------|-------------|
| [accessibility-review](./accessibility-review) | Conducts manual accessibility reviews of UI components, pages, and applications against WCAG 2.1/2.2 Level AA standards. Provides prioritized findings (Critical/Warning) focused on practical, modern web accessibility standards. |
| [x-writing](./x-writing) | Transforms notes into engaging X (Twitter) posts. Analyzes notes to identify shareable insights and crafts authentic posts that match your voice and drive engagement. Supports macOS Notes integration. |
| [technical-writing](./technical-writing) | Writes technical blog posts about features being built. Analyzes codebase, avoids AI-sounding language, and can publish directly to WordPress. Supports sentence case titles and headings for a conversational tone. |

## What Are Skills?

Skills are modular packages that transform a general-purpose AI agent into a specialized one. They load on-demand via progressive disclosure and provide:

- **Specialized workflows** — Multi-step procedures for specific domains
- **Tool integrations** — Scripts and APIs for complex tasks
- **Domain expertise** — Knowledge, schemas, and business logic
- **Bundled resources** — References, templates, and assets

## Structure

Each skill lives in its own folder:

```
skill-name/
├── SKILL.md              # Required: Instructions and metadata
├── references/           # Optional: Documentation loaded as needed
├── scripts/              # Optional: Executable code
└── assets/               # Optional: Templates, images, etc.
```

## Installation

Copy skills to the appropriate location for your platform:

| Agent | User-level | Repo-level |
|-------|------------|------------|
| Claude Code | `~/.claude/skills/` | `.claude/skills/` |
| OpenAI Codex | `~/.codex/skills/` | `.codex/skills/` |
| GitHub Copilot | — | `.github/skills/` or `.claude/skills/` |
| Cursor | — | [See docs](https://cursor.com/docs/context/skills) |

Example:
```bash
cp -r technical-writing ~/.claude/skills/
```

## Setup

Some skills require environment variables. Copy the example file and add your credentials:

```bash
cp skill-name/.env.example skill-name/.env.local
```