# Templates And Transitions

## Templates

Choose the template with:

```bash
marp --template bespoke slide-deck.md
marp --template bare slide-deck.md
```

### `bespoke`

Default interactive template.

Features:

- keyboard and swipe navigation
- fullscreen
- on-screen controller
- presenter view
- progress bar option
- fragmented lists
- slide transitions

Useful flags:

- `--bespoke.osc`
- `--bespoke.progress`
- `--bespoke.transition`

### `bare`

Minimal template with no extra presentation behavior.

Use this when you want the simplest possible output or a zero-JS Marpit path:

```bash
marp --template bare --engine @marp-team/marpit slide-deck.md
```

## Transition directive

`bespoke` supports the `transition` local directive.

```markdown
---
transition: fade
---
```

It applies to the next slide boundary, not the current slide in isolation.

Single-slide opt-out:

```markdown
<!-- _transition: none -->
```

## Built-in transition usage

Useful built-in names include:

- `none`
- `fade`
- `cover`
- `cube`
- `flip`
- `reveal`
- `slide`
- `swap`
- `wipe`
- `zoom`

Duration can be appended:

```yaml
transition: fade 1s
```

## Custom transitions

Custom `bespoke` transitions are CSS-only and use keyframes such as:

- `marp-transition-name`
- `marp-outgoing-transition-name`
- `marp-incoming-transition-name`

## Morphing

`bespoke` can use View Transition API morphing via `view-transition-name`.

If the deck uses raw HTML with `data-*` based morph markers, enable raw HTML:

```bash
marp deck.md --html
```

## Accessibility

Viewers with reduced-motion preferences will get simpler transition behavior. Do not rely on elaborate transitions to communicate essential content.
