# CLI Runtime Detection

Use this first for any task that renders or exports slides.

## Docker-first decision rule

Prefer Docker when both of these are true:

- `docker` is available on `PATH`
- `docker version` succeeds

If the CLI exists but the daemon is unavailable, do not keep insisting on Docker. Fall back to local `marp` or `npx`.

## Manual checks

```bash
command -v docker >/dev/null 2>&1 && docker version >/dev/null 2>&1
command -v marp >/dev/null 2>&1
command -v node >/dev/null 2>&1 && command -v npx >/dev/null 2>&1
```

## Preferred path order

1. Docker
2. `marp`
3. `npx @marp-team/marp-cli@latest`
4. explanation-only guidance

## Explanation-only mode

When no runtime is available:

- still create or revise the markdown deck
- leave exact commands for HTML, PDF, PPTX, image, and notes export
- mention prerequisites such as Node or Docker and browser-backed export requirements
