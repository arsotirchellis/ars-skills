# Marp Core Basics

Marp is built on top of Marpit.

## What Marp adds

Compared with plain Marpit, Marp Core adds practical presentation defaults:

- built-in themes: `default`, `gaia`, `uncover`
- `size` global directive for slide size presets such as `4:3`
- more permissive authoring defaults for Marp Markdown, such as GFM-style tables and strikethrough
- inline SVG slide and loose YAML parsing enabled by default in Marp Core

## Preferred Marp deck header

Prefer starting Marp-authored decks with:

```markdown
---
marp: true
theme: default
paginate: true
---
```

Use `marp: true` as the recognizable deck marker for Marp-aware tooling and previews.

## Built-in themes

Start with built-ins before inventing a custom theme:

- `default`: neutral baseline
- `gaia`: strong content slides
- `uncover`: larger display-oriented layouts

Example:

```markdown
---
marp: true
theme: gaia
size: 4:3
---
```

## When to switch to plain Marpit

Use pure `@marp-team/marpit` only when you intentionally want framework-level behavior without Marp Core themes or defaults. For ordinary slide creation, Marp Core plus Marp CLI is the practical path.
