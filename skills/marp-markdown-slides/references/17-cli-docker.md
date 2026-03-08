# Docker CLI

Use this sub-skill when [`scripts/detect-runtime.sh`](../scripts/detect-runtime.sh) reports `preferred: "docker"`.

## Pull image

```bash
docker pull marpteam/marp-cli
```

Tagged pull examples also exist, such as:

```bash
docker pull marpteam/marp-cli:main
```

## Standard mount pattern

Use the working directory mount and locale passthrough:

```bash
-v $PWD:/home/marp/app/
-e LANG=$LANG
```

## HTML

```bash
docker run --rm \
  -v $PWD:/home/marp/app/ \
  -e LANG=$LANG \
  marpteam/marp-cli slide-deck.md
```

## PDF

```bash
docker run --rm --init \
  -v $PWD:/home/marp/app/ \
  -e LANG=$LANG \
  marpteam/marp-cli slide-deck.md --pdf
```

## PPTX

```bash
docker run --rm --init \
  -v $PWD:/home/marp/app/ \
  -e LANG=$LANG \
  marpteam/marp-cli slide-deck.md --pptx
```

## Watch mode

```bash
docker run --rm --init \
  -v $PWD:/home/marp/app/ \
  -e LANG=$LANG \
  -p 37717:37717 \
  marpteam/marp-cli -w slide-deck.md
```

## Server mode

```bash
docker run --rm --init \
  -v $PWD:/home/marp/app \
  -e LANG=$LANG \
  -p 8080:8080 \
  -p 37717:37717 \
  marpteam/marp-cli -s .
```

Ports:

- `8080` for the HTTP server
- `37717` for watch / refresh behavior in the official examples

## Linux file permissions

On Linux hosts, mounted-directory writes can need an explicit UID/GID:

```bash
docker run --rm \
  -v $PWD:/home/marp/app/ \
  -e LANG=$LANG \
  -e MARP_USER="$(id -u):$(id -g)" \
  marpteam/marp-cli slide-deck.md
```

This workaround is mainly for Docker on Linux. Docker on macOS and Windows generally does not require `MARP_USER`.

## Constraints

From the official image and repo docs:

- `--preview` is not available in the official Docker image
- `--pptx-editable` is not available in the official Docker image

## Rule

If Docker is available and ready, use these commands by default instead of local `marp` / `npx` commands.
