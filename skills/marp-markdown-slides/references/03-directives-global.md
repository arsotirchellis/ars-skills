# Global Directives

Global directives apply to the whole deck and are parsed as YAML.

Use either HTML comments:

```markdown
<!--
theme: default
paginate: true
-->
```

or front matter:

```markdown
---
theme: default
paginate: true
---
```

## Core global directives

- `theme`
- `style`
- `headingDivider`
- `lang`

Marp Core also adds:

- `size`

## Theme

Use a registered theme name:

```markdown
---
theme: gaia
---
```

## Style

Use `style` for deck-level CSS tweaks without embedding a visible `<style>` block in the markdown body.

```markdown
---
style: |
  section {
    background: #f5f5f5;
  }
---
```

## Heading divider

Use `headingDivider` when the source should stay close to plain markdown.

```markdown
---
headingDivider: 2
---
```

## Size

Marp Core supports `size` for built-in slide size presets such as:

```markdown
---
theme: gaia
size: 4:3
---
```

## Rules

- Marpit keeps the last repeated global value.
- Quote values that contain YAML-sensitive characters.
- Prefer front matter when the settings define the deck identity.
