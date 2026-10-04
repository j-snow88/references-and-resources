# CSS `display` Property

> Controls how an element is displayed and how it participates in page layout.

---

## Quick Reference

| Value | Behavior | Typical Use |
|---|---|---|
| `block` | Takes the full available width and starts on a new line | Sections, containers, paragraphs |
| `inline` | Uses only the space its content needs and stays in the text flow | Text-level elements |
| `inline-block` | Flows inline but allows width and height | Buttons, badges, inline components |
| `none` | Removes the element from the layout | Hiding elements |
| `flex` | Creates a one-dimensional flex layout | Rows, columns, alignment |
| `grid` | Creates a two-dimensional grid layout | Structured rows and columns |

---

# 1. `display: block`

Block elements normally:

- Start on a new line
- Take the available width
- Stack vertically
- Allow `width` and `height`

```css
.block {
    display: block;
}
```

```html
<div class="block">Div 1</div>
<div class="block">Div 2</div>
<div class="block">Div 3</div>
```

### Visual Behavior

```text
┌─────────────────────────────┐
│ Div 1                       │
└─────────────────────────────┘
┌─────────────────────────────┐
│ Div 2                       │
└─────────────────────────────┘
┌─────────────────────────────┐
│ Div 3                       │
└─────────────────────────────┘
```

Common block-level elements include:

```html
<div>
<p>
<section>
<article>
<header>
<footer>
```

---

# 2. `display: inline`

Inline elements:

- Use only the width their content needs
- Stay on the same line when space permits
- Flow naturally with surrounding text
- Do not behave like normal boxes for `width` and `height`

```css
.inline {
    display: inline;
}
```

```html
<span class="inline">Span 1</span>
<span class="inline">Span 2</span>
<span class="inline">Span 3</span>
```

### Visual Behavior

```text
[Span 1] [Span 2] [Span 3]
```

Common inline elements include:

```html
<span>
<a>
<strong>
<em>
```

---

# 3. `display: inline-block`

`inline-block` combines characteristics of `inline` and `block`.

Elements:

- Stay inline with surrounding elements
- Allow explicit `width`
- Allow explicit `height`
- Respect padding and margins as boxes

```css
.inline-block {
    display: inline-block;
    width: 100px;
    height: 50px;
}
```

```html
<span class="inline-block">Box 1</span>
<span class="inline-block">Box 2</span>
<span class="inline-block">Box 3</span>
```

### Visual Behavior

```text
┌───────┐ ┌───────┐ ┌───────┐
│ Box 1 │ │ Box 2 │ │ Box 3 │
└───────┘ └───────┘ └───────┘
```

### When to Use

Useful for elements that need to remain side-by-side while still behaving like boxes.

Examples:

```text
Buttons
Badges
Navigation links
Tags
Small UI components
```

---

# 4. `display: none`

Completely removes an element from the rendered layout.

```css
.none {
    display: none;
}
```

```html
<div class="none">
    Hidden
</div>
```

The element:

```text
Is not visible
Does not occupy space
Does not affect surrounding layout
```

## `display: none` vs `visibility: hidden`

These are not the same.

### `display: none`

```css
.element {
    display: none;
}
```

```text
Element hidden
Space removed
```

### `visibility: hidden`

```css
.element {
    visibility: hidden;
}
```

```text
Element hidden
Space preserved
```

---

# 5. `display: flex`

Creates a **flex container**.

Flexbox is primarily designed for **one-dimensional layouts**:

```text
Row
OR
Column
```

```css
.flex {
    display: flex;
}
```

```html
<div class="flex">
    <div>Item 1</div>
    <div>Item 2</div>
    <div>Item 3</div>
</div>
```

Default behavior:

```text
[Item 1] [Item 2] [Item 3]
```

---

## Common Flexbox Properties

### Direction

```css
.container {
    display: flex;
    flex-direction: row;
}
```

Possible values:

```text
row
row-reverse
column
column-reverse
```

### Main-Axis Alignment

```css
.container {
    display: flex;
    justify-content: center;
}
```

Common values:

```text
flex-start
center
flex-end
space-between
space-around
space-evenly
```

### Cross-Axis Alignment

```css
.container {
    display: flex;
    align-items: center;
}
```

Common values:

```text
stretch
flex-start
center
flex-end
baseline
```

### Allow Wrapping

```css
.container {
    display: flex;
    flex-wrap: wrap;
}
```

### Add Spacing

```css
.container {
    display: flex;
    gap: 1rem;
}
```

---

# 6. `display: grid`

Creates a **CSS Grid container**.

Grid is designed for **two-dimensional layouts**:

```text
Rows
AND
Columns
```

```css
.grid {
    display: grid;
}
```

```html
<div class="grid">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
</div>
```

---

## Basic Three-Column Grid

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1rem;
}
```

Result:

```text
┌─────┬─────┬─────┐
│  1  │  2  │  3  │
├─────┼─────┼─────┤
│  4  │  5  │  6  │
└─────┴─────┴─────┘
```

---

## Responsive Grid

A useful responsive pattern:

```css
.grid {
    display: grid;
    grid-template-columns: repeat(
        auto-fit,
        minmax(250px, 1fr)
    );
    gap: 1rem;
}
```

This automatically adjusts the number of columns based on the available width.

---

# Flexbox vs Grid

A useful rule of thumb:

| Need | Prefer |
|---|---|
| Horizontal row | Flexbox |
| Vertical column | Flexbox |
| Centering content | Flexbox |
| Navigation bar | Flexbox |
| Button group | Flexbox |
| Rows **and** columns | Grid |
| Card layout | Grid |
| Dashboard | Grid |
| Structured page layout | Grid |
| Automatically responsive columns | Grid |

This is a guideline rather than a restriction. Flexbox and Grid are frequently used together.

---

# Quick Decision Guide

```text
Do I want the element hidden?
│
├── YES → display: none
│
└── NO
    │
    ├── Should it take a full line?
    │       └── display: block
    │
    ├── Should it flow with text?
    │       └── display: inline
    │
    ├── Should it flow inline but have width/height?
    │       └── display: inline-block
    │
    ├── Am I primarily arranging items in ONE dimension?
    │       └── display: flex
    │
    └── Am I arranging items in TWO dimensions?
            └── display: grid
```

---

# Fast Reference

```css
/* Full-width block */
.element {
    display: block;
}

/* Inline with text */
.element {
    display: inline;
}

/* Inline + box dimensions */
.element {
    display: inline-block;
}

/* Remove from layout */
.element {
    display: none;
}

/* One-dimensional layout */
.container {
    display: flex;
}

/* Two-dimensional layout */
.container {
    display: grid;
}
```

---

## Key Concept

```text
block        → full-line box
inline       → text-flow element
inline-block → inline box
none         → removed
flex         → one-dimensional layout
grid         → two-dimensional layout
```