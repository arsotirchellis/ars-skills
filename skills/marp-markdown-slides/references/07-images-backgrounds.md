# Background Images

## Basic background syntax

Use `bg` in the alt text:

```markdown
![bg](https://example.com/background.jpg)
```

## Background sizing

Supported keywords:

- `cover`
- `contain`
- `fit`
- `auto`
- percentages such as `150%`
- length-based `w` and `h`

Example:

```markdown
![bg contain](background.jpg)
```

## Multiple and split backgrounds

Advanced background behavior requires inline SVG mode. See [`10-inline-svg.md`](10-inline-svg.md).

Supported advanced patterns:

- multiple backgrounds in one slide
- `vertical` stacking
- split layouts with `left` or `right`
- split sizes like `left:33%`

Examples:

```markdown
![bg right](image-a.jpg)
![bg](image-b.jpg)
```

```markdown
![bg left:33%](image.jpg)
```

## Rule of thumb

- For ordinary decks, prefer one `![bg]()` image per slide.
- Reach for split or multiple backgrounds only when the layout genuinely benefits from them.
