# Watch Server Preview

Use this sub-skill for iterative rendering workflows.

## Watch mode

```bash
marp -w slide-deck.md
```

Behavior:

- watches markdown and theme CSS
- re-runs conversion on changes
- refreshes opened HTML automatically

## Server mode

```bash
marp -s ./slides
```

Behavior:

- serves a directory
- converts on demand over HTTP
- writes responses instead of output files

Useful query patterns:

- `?pdf`
- `?pptx`
- `?png`
- `?jpeg`
- `?txt`

Server details:

- default port: `8080`
- override with `PORT=5000 marp -s ./slides`
- `index.md` or `PITCHME.md` can act as the root deck

## Preview window

```bash
marp -p slide-deck.md
```

Behavior:

- opens an immersive preview window
- automatically enables watch mode

Constraint:

- the official Docker image does not support `--preview`

## Parallel conversion

- default concurrency is `5`
- use `--parallel` or `-P` to tune it
- use `--no-parallel` to disable it
