# Inline Images

Marpit extends image syntax by placing keywords in the alt text.

## Resizing

Use:

- `width`
- `height`
- shorthand `w`
- shorthand `h`

Examples:

```markdown
![width:200px](image.jpg)
![w:32 h:32](icon.png)
```

Rules:

- inline images accept `auto` and CSS length units
- inline images do not support percentage sizing
- avoid viewport units such as `vw`, `vh`, `vmin`, and `vmax`

## Filters

Useful filter keywords:

- `blur`
- `brightness`
- `contrast`
- `drop-shadow`
- `grayscale`
- `hue-rotate`
- `invert`
- `opacity`
- `saturate`
- `sepia`

Example:

```markdown
![brightness:.8 sepia:50%](https://example.com/image.jpg)
```

## Alt text behavior

The remaining alt text still matters:

- inline images keep it as alt text
- background images use it as figure caption
