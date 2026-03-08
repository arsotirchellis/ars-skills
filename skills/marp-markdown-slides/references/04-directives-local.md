# Local Directives

Local directives affect the current slide and the following slides.

Example:

```markdown
<!-- backgroundColor: aqua -->
```

Use the `_` prefix for a spot directive that affects only the current slide:

```markdown
<!-- _backgroundColor: aqua -->
```

## High-value local directives

- `paginate`
- `header`
- `footer`
- `class`
- `backgroundColor`
- `backgroundImage`
- `backgroundPosition`
- `backgroundRepeat`
- `backgroundSize`
- `color`

## Pagination

Values behave differently:

- `true`: show and increment
- `false`: hide and increment
- `hold`: show and do not increment
- `skip`: hide and do not increment

Useful pattern:

- put `paginate: true` on slide 2 when the title slide should stay unnumbered

## Header and footer

Use for repeated chrome:

```markdown
---
header: 'Quarterly review'
footer: 'Internal only'
---
```

They support markdown formatting and inline images, but not `![bg]()` background syntax.

## Class

Attach a class to the slide `<section>`:

```markdown
<!-- _class: lead -->
```

Use this when a theme has alternate layouts such as `lead`, `split`, or `compact`.

## Background and text styling

Gradient example:

```markdown
<!-- backgroundImage: "linear-gradient(to bottom, #67b8e3, #0288d1)" -->
```

Single-slide inversion:

```markdown
<!--
_backgroundColor: black
_color: white
-->
```

Defaults called out in the docs:

- `backgroundPosition`: `center`
- `backgroundRepeat`: `no-repeat`
- `backgroundSize`: `cover`
