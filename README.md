# ars-skills

Personal AI agent skills published from this repository.

## Available Skills

### `marp-markdown-slides`

Path: [`skills/marp-markdown-slides`](./skills/marp-markdown-slides)

Create, edit, theme, and export Markdown slide decks. Use it for presentation markdown files, slide deck authoring, deck restructuring, and rendering slides with `marp`, `npx @marp-team/marp-cli`, or Docker.

## Install

Install the skill from this repository with:

```bash
npx skills add arsotirchellis/ars-skills --skill marp-markdown-slides
```

If you want to target a specific agent at install time, use:

```bash
npx skills add arsotirchellis/ars-skills --skill marp-markdown-slides --agent codex
```

If you want to reference the skill directly by path, the canonical published location in this repo is:

```text
skills/marp-markdown-slides
```

## Repository Layout

This repository uses a single canonical public layout for skills:

```text
skills/
  marp-markdown-slides/
    SKILL.md
    agents/openai.yaml
    references/
```

The skill is intentionally stored once here, instead of mirroring agent-specific copies such as `.agents/skills` or `.claude/skills`.

## Notes

- `SKILL.md` is the primary trigger and workflow file.
- `references/` contains focused sub-skills for Marp, Marpit, theme CSS, CLI, Docker, and official links.
- The skill prefers Docker-based Marp CLI when Docker is available, and otherwise explains or uses local Marp CLI workflows.
