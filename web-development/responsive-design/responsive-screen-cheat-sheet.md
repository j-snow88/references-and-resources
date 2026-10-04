# Responsive Screen Cheat Sheet

> Mobile-first responsive design reference.

---

## Screen Size Reference

| Category | Width | Typical Device |
|---|---:|---|
| Extra Small | `320px–480px` | Small smartphones |
| Small | `481px–767px` | Large phones |
| Medium | `768px–991px` | Tablets / iPads |
| Large | `992px–1199px` | Laptops / small desktops |
| Extra Large | `1200px–1399px` | Large desktops |
| 2XL | `1400px+` | Ultra-wide monitors |

---

# CSS Media Queries

## Mobile First

Base styles should target mobile devices first.

```css
/* Base / Mobile */
.element {
    width: 100%;
}
```

Then progressively enhance the layout as the available screen width increases.

---

## Small / Large Phones

```css
@media (min-width: 481px) and (max-width: 767px) {
    /* Large-phone styles */
}
```

---

## Tablet

```css
@media (min-width: 768px) and (max-width: 991px) {
    /* Tablet styles */
}
```

---

## Laptop

```css
@media (min-width: 992px) and (max-width: 1199px) {
    /* Laptop styles */
}
```

---

## Desktop

```css
@media (min-width: 1200px) and (max-width: 1399px) {
    /* Desktop styles */
}
```

---

## 2XL / Ultra-Wide

```css
@media (min-width: 1400px) {
    /* Ultra-wide styles */
}
```

---

# Bootstrap 5 Breakpoints

| Prefix | Minimum Width |
|---|---:|
| Default | `<576px` |
| `sm` | `≥576px` |
| `md` | `≥768px` |
| `lg` | `≥992px` |
| `xl` | `≥1200px` |
| `xxl` | `≥1400px` |

Example:

```css
/* Bootstrap breakpoint equivalents */

@media (min-width: 576px) {
    /* sm */
}

@media (min-width: 768px) {
    /* md */
}

@media (min-width: 992px) {
    /* lg */
}

@media (min-width: 1200px) {
    /* xl */
}

@media (min-width: 1400px) {
    /* xxl */
}
```

---

# Tailwind CSS Breakpoints

| Prefix | Minimum Width |
|---|---:|
| `sm` | `640px` |
| `md` | `768px` |
| `lg` | `1024px` |
| `xl` | `1280px` |
| `2xl` | `1536px` |

Example:

```html
<div class="
    w-full
    md:w-1/2
    lg:w-1/3
    xl:w-1/4
">
    Responsive Content
</div>
```

This means:

```text
Default      → Full width
≥ 768px      → 50% width
≥ 1024px     → 33.33% width
≥ 1280px     → 25% width
```

---

# Responsive Design Best Practices

## 1. Use Flexbox and Grid

Prefer flexible layout systems rather than fixed positioning.

```css
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
}
```

Or:

```css
.container {
    display: grid;
    grid-template-columns: repeat(
        auto-fit,
        minmax(250px, 1fr)
    );
    gap: 1rem;
}
```

---

## 2. Use Relative Units

Prefer:

```text
%
rem
em
vw
vh
fr
```

instead of relying entirely on fixed pixel dimensions.

Example:

```css
.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
}
```

---

## 3. Make Images Responsive

```css
img {
    max-width: 100%;
    height: auto;
}
```

---

## 4. Design Mobile First

Start with the smallest layout:

```css
.card {
    width: 100%;
}
```

Then progressively enhance it:

```css
@media (min-width: 768px) {
    .card {
        width: 50%;
    }
}

@media (min-width: 1200px) {
    .card {
        width: 33.333%;
    }
}
```

---

## 5. Test on Real Devices

Browser developer tools are useful, but responsive layouts should also be tested on actual:

- Phones
- Tablets
- Laptops
- Desktop monitors

Check:

- Touch targets
- Font readability
- Navigation
- Scrolling
- Orientation changes
- Form usability

---

## 6. Avoid Fixed Widths

Avoid:

```css
.container {
    width: 1200px;
}
```

Prefer:

```css
.container {
    width: 100%;
    max-width: 1200px;
    margin-inline: auto;
}
```

---

# Quick Reference

```text
GENERAL SCREEN GUIDE

320–480px       Small Mobile
481–767px       Large Mobile
768–991px       Tablet
992–1199px      Laptop
1200–1399px     Desktop
1400px+         Large / Ultra-Wide


BOOTSTRAP 5

sm      576px
md      768px
lg      992px
xl      1200px
xxl     1400px


TAILWIND CSS

sm      640px
md      768px
lg      1024px
xl      1280px
2xl     1536px
```

---

## Core Principle

> Build for the smallest screen first, then progressively enhance the experience as additional screen space becomes available.