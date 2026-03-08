# CLI Export Commands

Use this sub-skill for one-shot conversion commands.

## Local one-shot path

```bash
npx @marp-team/marp-cli@latest slide-deck.md
```

## Local installed path

```bash
marp slide-deck.md
```

## HTML

```bash
marp slide-deck.md
marp slide-deck.md -o output.html
```

## PDF

```bash
marp --pdf slide-deck.md
marp slide-deck.md -o output.pdf
```

## PPTX

```bash
marp --pptx slide-deck.md
marp slide-deck.md -o output.pptx
```

Editable PPTX is separate and experimental:

```bash
marp --pptx --pptx-editable slide-deck.md
```

## Images

First slide only:

```bash
marp --image png slide-deck.md
marp slide-deck.md -o output.png
```

All slides:

```bash
marp --images png slide-deck.md
marp --images jpeg slide-deck.md
```

Useful flags:

- `--image-scale`
- `--jpeg-quality`

## Notes

```bash
marp --notes slide-deck.md
marp slide-deck.md -o output.txt
```

## Working rule

PDF, PPTX, and image export require a compatible browser. Do not promise those outputs unless the runtime path can satisfy that requirement.
