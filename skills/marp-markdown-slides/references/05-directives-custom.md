# Custom Directives

Use this sub-skill only when the deck is rendered through a custom Marpit or Marp engine.

Stock Marp CLI decks do not automatically have arbitrary custom directives available.

## How custom directives work

Marpit exposes:

- `customDirectives.global`
- `customDirectives.local`

A handler returns ordinary directive key-value pairs.

## Typical uses

- aliasing a directive name
- mapping a higher-level preset such as `colorPreset: dark`
- providing project-specific presentation conventions

## Example

```javascript
marpit.customDirectives.local.colorPreset = (value) => {
  switch (value) {
    case 'dark':
      return { backgroundColor: '#303033', color: '#f8f8ff' }
    default:
      return {}
  }
}
```

Markdown:

```markdown
<!-- _colorPreset: dark -->
```

## Working rule

Only tell another agent to use a custom directive when:

- the engine has been explicitly customized, and
- the directive definition exists in the project
