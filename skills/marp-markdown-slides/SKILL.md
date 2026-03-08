---
name: marp-markdown-slides
description: Create, edit, theme, and export Markdown slide decks. Use when working in presentation markdown files, when asked to create slide decks in Markdown, or when rendering slides with marp cli.
---

# Marp Markdown Slides

Use this skill for end-to-end Marp slide work:

- creating a new slide deck in Markdown
- revising an existing Marp / Marpit deck
- choosing directives, images, fragments, or theme CSS
- rendering to HTML, PDF, PPTX, images, or notes
- deciding between Docker, local `marp`, and `npx`

Treat each file in `references/` as a focused sub-skill. Read only the files needed for the current task.

## Runtime Priority

1. Check whether Docker is available by verifying both `docker` on `PATH` and a working `docker version`.
2. If Docker is available, use Docker CLI as the default execution path.
3. If Docker is unavailable but `marp` or `npx` is available, use the local CLI path.
4. If no runnable path is available, still complete the markdown and explain the exact commands, prerequisites, and expected outputs.

Do not insist on Docker when the command exists but the daemon is unavailable. In that case, fall back to local CLI if possible.

## Loading Order

Always start with:

- [`references/00-workflow.md`](references/00-workflow.md)
- [`references/11-cli-runtime-detection.md`](references/11-cli-runtime-detection.md)

Read this when you need canonical upstream docs or a primary-source check:

- [`references/18-official-links.md`](references/18-official-links.md)

Read authoring sub-skills as needed:

- [`references/01-marp-core-basics.md`](references/01-marp-core-basics.md)
- [`references/02-slide-structure.md`](references/02-slide-structure.md)
- [`references/03-directives-global.md`](references/03-directives-global.md)
- [`references/04-directives-local.md`](references/04-directives-local.md)
- [`references/05-directives-custom.md`](references/05-directives-custom.md)
- [`references/06-images-inline.md`](references/06-images-inline.md)
- [`references/07-images-backgrounds.md`](references/07-images-backgrounds.md)
- [`references/08-fragments-and-notes.md`](references/08-fragments-and-notes.md)
- [`references/09-theme-css.md`](references/09-theme-css.md)
- [`references/10-inline-svg.md`](references/10-inline-svg.md)

Read execution sub-skills as needed:

- [`references/12-cli-export-commands.md`](references/12-cli-export-commands.md)
- [`references/13-cli-live-workflows.md`](references/13-cli-live-workflows.md)
- [`references/14-cli-browser-security.md`](references/14-cli-browser-security.md)
- [`references/15-cli-templates-and-transitions.md`](references/15-cli-templates-and-transitions.md)
- [`references/16-cli-themes-engines-config.md`](references/16-cli-themes-engines-config.md)
- [`references/17-cli-docker.md`](references/17-cli-docker.md)

## Default Workflow

1. Detect the runnable path.
2. Inspect whether the repo already has an existing deck, theme CSS, or output convention.
3. Start from a Marp front-matter skeleton unless the deck already has a working structure.
4. Add slide structure first, then directives, then images, then theme CSS.
5. Render early if runtime is available. Prefer Docker when it is actually available and working.
6. If rendering is unavailable, leave a concrete command block that another agent or the user can run without additional discovery.

## Working Rules

- Prefer Marp front matter for Marp-authored decks:

```markdown
---
marp: true
theme: default
paginate: true
---
```

- Keep source Markdown readable in ordinary editors.
- Treat directives as YAML and quote ambiguous values aggressively.
- Use `_directive` spot form for single-slide exceptions.
- Prefer built-in themes before inventing custom theme CSS.
- Use Docker-first rendering when available on the machine.
- Use `--allow-local-files` only when the deck genuinely depends on local assets and the input is trusted.
- Separate deck authoring from export commands. The markdown should remain valid even when the CLI is unavailable.
- Prefer the official Marp and Marpit sources in [`references/18-official-links.md`](references/18-official-links.md) when verifying behavior.
