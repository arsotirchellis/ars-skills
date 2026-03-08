# Workflow

Use this sub-skill first.

## Decide the task shape

- New deck: read [`01-marp-core-basics.md`](01-marp-core-basics.md) and [`02-slide-structure.md`](02-slide-structure.md).
- Deck mechanics: read the directive, image, fragment, or theme references that match the requested effect.
- Rendering or exporting: read [`11-cli-runtime-detection.md`](11-cli-runtime-detection.md) and the relevant CLI references.

## Runtime decision

Check runtime manually:

```bash
command -v docker >/dev/null 2>&1 && docker version >/dev/null 2>&1
command -v marp >/dev/null 2>&1
command -v node >/dev/null 2>&1 && command -v npx >/dev/null 2>&1
```

Interpret the result:

- working Docker CLI: use Docker as the default rendering path
- no working Docker but `marp` found: use the local `marp` binary
- no Docker or `marp` but `node` and `npx` found: use `npx @marp-team/marp-cli@latest`
- none available: do not block; finish the deck and provide exact commands plus prerequisites

## Build order

1. Start with front matter.
2. Lay out the slide sequence with headings and `---`.
3. Add directives for pagination, theme, header/footer, classes, and backgrounds.
4. Add images, fragments, and speaker notes.
5. Add theme CSS only when the built-in themes or directives are not enough.
6. Render early and fix issues while the deck is still small.

## Deliverables

Aim to leave behind:

- a working markdown deck
- optional theme CSS
- an exact render command
- output expectations such as HTML, PDF, PPTX, PNG, or TXT notes
