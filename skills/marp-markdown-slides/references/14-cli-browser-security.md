# Browser And Security

## Browser-backed exports

These outputs depend on a compatible browser:

- PDF
- PPTX
- PNG / JPEG

Supported browser choices documented by Marp CLI:

- `auto`
- `chrome`
- `edge`
- `firefox`

## Browser selection

```bash
marp --browser firefox slide.md -o slide.png
marp --browser firefox,chrome slide.md -o slide.pdf
```

## Browser path

```bash
marp --browser-path /path/to/browser slide.md -o slide.pdf
```

## Protocol and timeout

- `--browser-protocol cdp`
- `--browser-protocol webdriver-bidi`
- `--browser-timeout 30`
- `--browser-timeout 0` disables the timeout

## Local file security

Browser-backed conversions cannot access local files by default.

Enable only for trusted inputs:

```bash
marp --pdf --allow-local-files slide-deck.md
```

Use this only when the deck depends on local images or assets and cannot be switched to remote URLs.

## Firefox caveat

Firefox support exists, but PDF output may differ from Chrome output. Prefer Chrome or Edge when layout fidelity matters.
