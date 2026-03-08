# Slide Structure

## Split slides

Use horizontal rules such as `---` to split slides.

```markdown
# Slide 1

Intro

---

# Slide 2

Details
```

CommonMark may require a blank line before the ruler. When needed, use:

- `---`
- `___`
- `***`
- `- - -`

## Auto-split from headings

When converting prose into slides, use `headingDivider` instead of manual rulers.

```markdown
---
headingDivider: 2
---

# Deck title

## Slide title

Content
```

## Practical deck outline

A reliable default structure is:

1. Title slide
2. Agenda or framing slide
3. 3-7 content slides
4. Summary / close

Keep each slide focused on one point. Move overflow text into more slides instead of shrinking everything to fit.

## Starter example

```markdown
---
marp: true
theme: default
paginate: true
---

# Product Update

Q2 roadmap and delivery status

---

## Goals

- Reduce latency
- Improve reliability
- Ship migration plan

---

## Milestones

1) Platform work
2) Beta rollout
3) Full launch
```
