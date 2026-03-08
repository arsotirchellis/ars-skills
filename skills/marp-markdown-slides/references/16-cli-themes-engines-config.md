# Themes Engines Config

Use this sub-skill when the task is about theme selection, custom engines, metadata, or project-level configuration.

## Metadata

Marp CLI supports these deck metadata fields:

- `title`
- `description`
- `author`
- `keywords`
- `url`
- `image` / `--og-image`

CLI options override front matter values.

## Theme override

```bash
marp --theme gaia slide-deck.md
marp --theme custom-theme.css slide-deck.md
```

Practical rule:

- use `--theme` when one deck should render with one known theme
- use `--theme-set` when multiple named themes must be registered

## Theme sets

```bash
marp --theme-set ./themes -- deck.md
marp --theme-set theme-a.css theme-b.css -- deck.md
```

## Engine swapping

Use a different engine when the project intentionally depends on it:

```bash
marp --engine @marp-team/marpit deck.md
marp --engine ./engine.mjs deck.md
```

Custom engines matter for:

- custom directives
- extra markdown-it plugins
- framework-level behavior changes

## Version check

```bash
marp --version
```

Use this to confirm whether the runtime is using:

- bundled Marp Core
- user-installed Marp Core
- a customized engine

## Config files

Supported config entry points:

- `marp.config.js`
- `marp.config.mjs`
- `marp.config.cjs`
- `marp.config.ts`
- `.marprc`
- `package.json` `marp` section

Useful CLI flags:

- `--config-file`
- `--config`
- `-c`
- `--no-config-file`
- `--no-config`

## Common config keys

- `inputDir`
- `output`
- `themeSet`
- `pdf`
- `pptx`
- `image`
- `images`
- `preview`
- `server`
- `watch`
- `browser`
- `browserPath`
- `browserProtocol`
- `browserTimeout`
- `allowLocalFiles`
- `options`

## ESM caveat

ESM config files and engines only resolve when Marp CLI is used through Node.js, not the standalone binary.
