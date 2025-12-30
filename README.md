# Skills

A collection of custom [Agent Skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) that extend Claude's capabilities with specialized knowledge, workflows, and tools.

## What Are Skills?

Skills are modular packages that transform a general-purpose AI agent into a specialized one. They load on-demand and provide:

- **Specialized workflows** — Multi-step procedures for specific domains
- **Tool integrations** — Scripts and APIs for complex tasks
- **Domain expertise** — Knowledge, schemas, and business logic
- **Bundled resources** — References, templates, and assets

Learn more in the [official documentation](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview).

## Available Skills

| Skill | Description |
|-------|-------------|
| [technical-writing](./technical-writing) | Write technical blog posts about features being built. Analyzes codebase, avoids AI-sounding language, and can publish directly to WordPress. |

## Structure

Each skill lives in its own folder:

```
skill-name/
├── SKILL.md              # Required: Instructions and metadata
├── references/           # Optional: Documentation loaded as needed
├── scripts/              # Optional: Executable code
└── assets/               # Optional: Templates, images, etc.
```

## Setup

Some skills require environment variables. Copy the example file and add your credentials:

```bash
cp skill-name/.env.example skill-name/.env.local
```

Never commit `.env.local` files—they're gitignored by default.
