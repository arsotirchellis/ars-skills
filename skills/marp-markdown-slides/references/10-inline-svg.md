# Inline SVG

Inline SVG mode is an advanced option. Use it when the deck needs advanced backgrounds or pixel-perfect scaling behavior.

## What it does

- wraps each slide section in an inline SVG `foreignObject`
- enables advanced backgrounds
- improves scaling control in browser-based viewers

## Caveats

- this mode is experimental
- WebKit has known rendering and scaling issues with `foreignObject`
- use the Marpit SVG polyfill only when the environment truly needs it

## When to use it

Use inline SVG when:

- the deck needs multiple or split backgrounds
- the viewer environment is known and controlled

Avoid it when:

- a normal background image is enough
- the deck must behave predictably across mixed browsers with minimal complexity
