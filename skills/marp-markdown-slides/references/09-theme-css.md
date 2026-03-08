# Theme CSS

Use this sub-skill when the deck needs layout or styling beyond built-in themes and directives.

## Mental model

- each slide is a `<section>`
- theme authors mostly style normal HTML elements
- Marpit scopes the CSS to the container automatically

## Required metadata

Regular theme CSS requires:

```css
/* @theme my-theme */
```

## Root selectors

Use either `section` or `:root`.

In Marpit theme CSS, `:root` refers to the slide root, not the document `<html>`.

## Slide size

Define slide size on the root slide selector:

```css
section {
  width: 1280px;
  height: 720px;
}
```

Rules:

- size is fixed per theme
- use absolute units only
- defaults are `1280x720`

## Pagination styling

Style page numbers through `section::after` or `:root::after`.

If you override `content`, keep `attr(data-marpit-pagination)` in the declaration.

## Header and footer styling

Marpit provides no default styles for `header` and `footer`.

Use absolute positioning when they belong in slide margins.

## Theme composition

Supported approaches:

- `@import 'base';`
- `@import-theme 'base';`

## Inline style tweaks from markdown

Use:

- `<style>` for deck-level merged CSS
- `<style scoped>` for one slide only
- `style:` global directive for deck-level tweak CSS in front matter
