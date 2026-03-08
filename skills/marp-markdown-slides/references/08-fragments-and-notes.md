# Fragments And Notes

## Fragmented lists

Marpit uses marker style to infer fragments.

Bullet fragments:

```markdown
* One
* Two
* Three
```

Ordered fragments:

```markdown
1) One
2) Two
3) Three
```

Do not use `-` or `1.` when the slide should reveal items one by one.

## Presenter notes

Non-directive HTML comments are collected as presenter notes.

Example:

```markdown
# Slide title

<!-- Keep this explanation for presenter view or exported notes. -->
```

Notes are useful for:

- `--notes` text export
- `--pdf-notes`
- PPTX note support in normal, non-editable PPTX export

## Working rule

Keep presenter notes separate from visible slide content. Do not misuse directive comments as notes because directive comments are parsed as directives, not note text.
