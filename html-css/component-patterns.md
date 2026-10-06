# HTML + CSS Component Patterns

> Reusable HTML and CSS examples for common website components and layout patterns.

Includes:

- Landing Page Hero
- Portfolio Header
- Social Media Card
- Blog Page Section
- Product Card
- Student ID Card
- Pricing Card
- Contact Form
- Image Gallery
- Responsive Card Layout

---

# Table of Contents

1. [Landing Page Hero](#1-landing-page-hero)
2. [Portfolio Header](#2-portfolio-header)
3. [Social Media Card](#3-social-media-card)
4. [Blog Page Section](#4-blog-page-section)
5. [Product Card](#5-product-card)
6. [Student ID Card](#6-student-id-card)
7. [Pricing Card](#7-pricing-card)
8. [Contact Form](#8-contact-form)
9. [Image Gallery](#9-image-gallery)
10. [Responsive Card Layout](#10-responsive-card-layout)
11. [Common Patterns](#11-common-patterns)
12. [Complete Example](#12-complete-example)

---

# 1. Landing Page Hero

A simple centered landing-page hero containing:

```text
Headline
Supporting text
Call-to-action button
```

## HTML

```html
<section class="hero">
    <h1>Build Your Future</h1>

    <p>
        Learn coding and create amazing websites.
    </p>

    <button type="button">
        Get Started
    </button>
</section>
```

## CSS

```css
.hero {
    min-height: 300px;
    padding: 40px;
    background: #111827;
    color: white;
    text-align: center;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.hero h1 {
    color: #1677ff;
    margin: 0 0 15px;
}

.hero p {
    margin: 0 0 20px;
}

.hero button {
    padding: 12px 22px;
    background: #1677ff;
    color: white;
    border: none;
    border-radius: 6px;
    cursor: pointer;
}
```

---

## How the Layout Works

The important part is:

```css
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
```

This creates a vertical Flexbox layout:

```text
        ┌──────────────────────┐
        │                      │
        │   Build Your Future  │
        │                      │
        │   Supporting text    │
        │                      │
        │     [ Get Started ]  │
        │                      │
        └──────────────────────┘
```

### `flex-direction: column`

Stacks the elements vertically.

### `align-items: center`

Centers them horizontally.

### `justify-content: center`

Centers them vertically within the hero.

---

# 2. Portfolio Header

A common portfolio/site header containing:

```text
Logo / Site Name
Navigation Links
```

## HTML

```html
<header class="header">
    <h2>DevPortfolio</h2>

    <nav>
        <a href="#">Home</a>
        <a href="#">Projects</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
    </nav>
</header>
```

## CSS

```css
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;

    padding: 18px 25px;
    background: #111827;
}

.header h2 {
    color: #1677ff;
    margin: 0;
}

.header nav {
    display: flex;
    gap: 20px;
}

.header a {
    color: white;
    text-decoration: none;
}
```

---

## Why `space-between` Works

```css
justify-content: space-between;
```

pushes the two main groups apart:

```text
┌──────────────────────────────────────────────┐
│ DevPortfolio        Home Projects About Contact
└──────────────────────────────────────────────┘
```

---

## Navigation Spacing

Rather than manually applying margins to every link:

```css
.header nav {
    display: flex;
    gap: 20px;
}
```

---

## Hover State

```css
.header a:hover {
    color: #1677ff;
}
```

---

# 3. Social Media Card

A reusable card component containing:

```text
Avatar / Icon
Heading
Description
Call-to-action button
```

## HTML

```html
<article class="social-card">
    <div class="social-card__icon">
        S
    </div>

    <h2>Stay Connected</h2>

    <p>
        Follow for coding tips and projects.
    </p>

    <button type="button">
        Follow
    </button>
</article>
```

## CSS

```css
.social-card {
    width: 280px;
    padding: 25px;
    background: white;
    border-radius: 15px;
    text-align: center;

    box-shadow:
        0 8px 20px
        rgba(0, 0, 0, 0.2);
}

.social-card__icon {
    width: 60px;
    height: 60px;
    margin: 0 auto 15px;

    border-radius: 50%;
    background: #1677ff;
    color: white;

    display: flex;
    align-items: center;
    justify-content: center;

    font-size: 24px;
    font-weight: bold;
}

.social-card button {
    padding: 10px 20px;
    background: #1677ff;
    color: white;
    border: none;
    border-radius: 6px;
    cursor: pointer;
}
```

---

## Circular Icon Pattern

```css
.icon {
    width: 60px;
    height: 60px;

    border-radius: 50%;

    display: flex;
    align-items: center;
    justify-content: center;
}
```

Useful for:

```text
Profile avatars
Initials
Social icons
Feature icons
Status indicators
```

---

## Card Pattern

```css
.card {
    padding: 25px;
    background: white;
    border-radius: 15px;

    box-shadow:
        0 8px 20px
        rgba(0, 0, 0, 0.2);
}
```

---

# 4. Blog Page Section

A blog/article section containing:

```text
Section heading
Section description
Article card
Article title
Article description
Article link
```

## HTML

```html
<section class="blog">
    <h1>Latest Articles</h1>

    <p>
        Explore useful tips and tutorials
        for modern web development.
    </p>

    <article class="post">
        <h2>
            Getting Started with CSS
        </h2>

        <p>
            Learn how CSS transforms simple HTML
            into beautiful web pages.
        </p>

        <a href="#">
            Read Article →
        </a>
    </article>
</section>
```

## CSS

```css
.blog {
    padding: 30px;
    background: white;
    border-radius: 12px;
    text-align: center;
}

.blog h1 {
    color: #1677ff;
    margin-bottom: 10px;
}

.blog > p {
    color: #555;
}

.post {
    margin-top: 25px;
    padding: 20px;

    border: 1px solid #ddd;
    border-radius: 8px;

    text-align: left;
}

.post h2 {
    margin-top: 0;
}

.post a {
    color: #1677ff;
    text-decoration: none;
    font-weight: bold;
}
```

---

## Child Selector

```css
.blog > p
```

selects only a paragraph that is a direct child of `.blog`.

Compare:

```css
.blog p
```

which selects every descendant paragraph.

---

# 5. Product Card

A common e-commerce component containing:

```text
Product image
Product name
Price
Call-to-action button
```

## HTML

```html
<article class="product-card">
    <div class="product-image">
        PRODUCT
    </div>

    <h2>Wireless Headphones</h2>

    <p class="price">
        $49.99
    </p>

    <button type="button">
        Add to Cart
    </button>
</article>
```

## CSS

```css
.product-card {
    width: 280px;
    padding: 20px;

    background: white;
    border-radius: 12px;

    text-align: center;

    box-shadow:
        0 8px 20px
        rgba(0, 0, 0, 0.2);
}

.product-image {
    height: 120px;

    display: flex;
    align-items: center;
    justify-content: center;

    background: #e8f1ff;
    border-radius: 8px;
}

.product-card .price {
    color: #1677ff;
    font-size: 20px;
    font-weight: bold;
}

.product-card button {
    padding: 10px 18px;

    background: #1677ff;
    color: white;

    border: none;
    border-radius: 6px;

    cursor: pointer;
}
```

---

## Using a Real Product Image

```html
<img
    class="product-image"
    src="headphones.jpg"
    alt="Black wireless headphones"
>
```

```css
.product-image {
    width: 100%;
    height: 180px;

    object-fit: contain;

    background: #e8f1ff;
    border-radius: 8px;
}
```

---

## `object-fit`

```text
contain
→ Entire image remains visible

cover
→ Container is completely filled,
  but part of the image may be cropped
```

Product photography often works well with:

```css
object-fit: contain;
```

---

# 6. Student ID Card

An identification/profile card containing:

```text
Profile image
Name
ID number
Department / program
```

## HTML

```html
<article class="id-card">
    <div class="photo">
        PHOTO
    </div>

    <h2>Alex Smith</h2>

    <p>
        Student ID: 1024
    </p>

    <p>
        Computer Science
    </p>
</article>
```

## CSS

```css
.id-card {
    width: 280px;
    padding: 20px;

    background: white;

    border: 2px solid #1677ff;
    border-radius: 12px;

    text-align: center;

    box-shadow:
        0 8px 20px
        rgba(0, 0, 0, 0.2);
}

.photo {
    width: 80px;
    height: 80px;

    margin: 0 auto 15px;

    background: #e8f1ff;

    border-radius: 50%;

    display: flex;
    align-items: center;
    justify-content: center;
}
```

---

## Circular Profile Image

```html
<img
    class="photo"
    src="student.jpg"
    alt="Alex Smith"
>
```

```css
.photo {
    width: 100px;
    height: 100px;

    margin: 0 auto 15px;

    border-radius: 50%;

    object-fit: cover;
}
```

Reusable for:

```text
Employee cards
Team member profiles
User profiles
Author cards
Speaker cards
Customer profiles
```

---

# 7. Pricing Card

Pricing cards commonly display:

```text
Product / plan image
Plan name
Price
Description
Call-to-action
```

## HTML

```html
<article class="pricing-card">
    <img
        src="https://via.placeholder.com/280x140"
        alt="Premium Plan"
    >

    <h2>Premium Plan</h2>

    <p class="price">
        $19/month
    </p>

    <p>
        Unlimited access to all features.
    </p>

    <button type="button">
        Choose Plan
    </button>
</article>
```

## CSS

```css
.pricing-card {
    width: 280px;
    padding: 20px;

    background: white;

    border: 2px solid #1677ff;
    border-radius: 12px;

    text-align: center;

    box-shadow:
        0 8px 20px
        rgba(0, 0, 0, 0.2);
}

.pricing-card img {
    width: 100%;
    height: 140px;

    object-fit: cover;

    border-radius: 8px;
}

.pricing-card .price {
    color: #1677ff;
    font-size: 22px;
    font-weight: bold;
}

.pricing-card button {
    padding: 10px 20px;

    background: #1677ff;
    color: white;

    border: none;
    border-radius: 6px;

    cursor: pointer;
}
```

---

## Pricing Card Structure

```text
┌─────────────────────────┐
│                         │
│         IMAGE           │
│                         │
├─────────────────────────┤
│      Premium Plan       │
│                         │
│       $19/month         │
│                         │
│ Unlimited access...     │
│                         │
│    [ Choose Plan ]      │
└─────────────────────────┘
```

---

## Multiple Pricing Plans

```html
<section class="pricing-grid">

    <article class="pricing-card">
        <!-- Basic Plan -->
    </article>

    <article class="pricing-card">
        <!-- Premium Plan -->
    </article>

    <article class="pricing-card">
        <!-- Enterprise Plan -->
    </article>

</section>
```

```css
.pricing-grid {
    display: grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(250px, 1fr)
        );

    gap: 20px;
}
```

---

# 8. Contact Form

A basic contact form contains:

```text
Name
Email
Message
Submit button
```

## HTML

```html
<form class="contact-form">

    <h2>Contact Us</h2>

    <input
        type="text"
        name="name"
        placeholder="Your Name"
        required
    >

    <input
        type="email"
        name="email"
        placeholder="Your Email"
        required
    >

    <textarea
        name="message"
        placeholder="Your Message"
        required
    ></textarea>

    <button type="submit">
        Send Message
    </button>

</form>
```

## CSS

```css
.contact-form {
    width: 300px;
    padding: 25px;

    background: white;

    border-radius: 12px;

    box-shadow:
        0 8px 20px
        rgba(0, 0, 0, 0.2);
}

.contact-form h2 {
    margin: 0 0 18px;

    text-align: center;
}

.contact-form input,
.contact-form textarea {
    width: 100%;

    box-sizing: border-box;

    padding: 10px;
    margin: 8px 0;

    border: 1px solid #ccc;
    border-radius: 6px;

    font-family: inherit;
}

.contact-form textarea {
    height: 100px;

    resize: none;
}

.contact-form button {
    width: 100%;

    margin-top: 10px;
    padding: 10px;

    background: #1677ff;
    color: white;

    border: none;
    border-radius: 6px;

    cursor: pointer;
}
```

---

## Why `box-sizing: border-box` Matters

Without:

```css
box-sizing: border-box;
```

padding and borders can make an element wider than its declared width.

A useful global rule is:

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

---

## Better Accessible Form Markup

```html
<form class="contact-form">

    <h2>Contact Us</h2>

    <label for="contact-name">
        Name
    </label>

    <input
        id="contact-name"
        type="text"
        name="name"
        placeholder="Your Name"
        required
    >

    <label for="contact-email">
        Email
    </label>

    <input
        id="contact-email"
        type="email"
        name="email"
        placeholder="Your Email"
        required
    >

    <label for="contact-message">
        Message
    </label>

    <textarea
        id="contact-message"
        name="message"
        placeholder="Your Message"
        required
    ></textarea>

    <button type="submit">
        Send Message
    </button>

</form>
```

---

## Focus State

```css
.contact-form input:focus,
.contact-form textarea:focus {
    outline: 2px solid #1677ff;
    outline-offset: 2px;
}
```

---

# 9. Image Gallery

CSS Grid is an excellent choice for image galleries.

## HTML

```html
<div class="gallery">

    <img
        src="image1.jpg"
        alt="City street"
    >

    <img
        src="image2.jpg"
        alt="Mountain landscape"
    >

    <img
        src="image3.jpg"
        alt="Bowl of fruit"
    >

    <img
        src="image4.jpg"
        alt="Abstract architecture"
    >

</div>
```

## CSS

```css
.gallery {
    display: grid;

    grid-template-columns:
        repeat(2, 1fr);

    gap: 10px;
}

.gallery img {
    width: 100%;
    height: 120px;

    object-fit: cover;

    border-radius: 8px;
}
```

---

## Two-Column Grid

```css
grid-template-columns:
    repeat(2, 1fr);
```

means:

```text
Create 2 columns
Each receives 1 equal fraction of available width
```

```text
┌─────────────┬─────────────┐
│   IMAGE 1   │   IMAGE 2   │
├─────────────┼─────────────┤
│   IMAGE 3   │   IMAGE 4   │
└─────────────┴─────────────┘
```

---

## Responsive Gallery

```css
.gallery {
    display: grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(180px, 1fr)
        );

    gap: 10px;
}
```

---

## Gallery Pattern

```text
display: grid
        ↓
Create grid layout

repeat()
        ↓
Generate columns

1fr
        ↓
Equal share of available width

gap
        ↓
Space between images

object-fit: cover
        ↓
Consistent image dimensions
```

---

# 10. Responsive Card Layout

A responsive card container can display multiple content blocks and automatically wrap when screen space becomes limited.

## HTML

```html
<section class="cards">

    <article class="card">
        <h2>Web Design</h2>

        <p>
            Learn modern web design.
        </p>
    </article>

    <article class="card">
        <h2>Development</h2>

        <p>
            Build powerful websites.
        </p>
    </article>

    <article class="card">
        <h2>Projects</h2>

        <p>
            Create real-world projects.
        </p>
    </article>

</section>
```

## CSS

```css
.cards {
    display: flex;

    gap: 20px;

    flex-wrap: wrap;

    justify-content: center;
}

.card {
    flex: 1 1 200px;

    padding: 20px;

    background: white;

    border-radius: 12px;

    box-shadow:
        0 6px 15px
        rgba(0, 0, 0, 0.2);
}

.card h2 {
    color: #1677ff;
}
```

---

## `flex-wrap`

```css
flex-wrap: wrap;
```

allows items to move onto additional rows when space runs out.

```text
Wide screen:

[ Card 1 ] [ Card 2 ] [ Card 3 ]


Smaller screen:

[ Card 1 ] [ Card 2 ]

[ Card 3 ]


Very small screen:

[ Card 1 ]

[ Card 2 ]

[ Card 3 ]
```

---

## Understanding `flex: 1 1 200px`

```css
flex: 1 1 200px;
```

is shorthand for:

```css
flex-grow: 1;
flex-shrink: 1;
flex-basis: 200px;
```

### `flex-grow: 1`

Allows the card to grow when space is available.

### `flex-shrink: 1`

Allows the card to shrink when necessary.

### `flex-basis: 200px`

Sets the preferred starting width.

---

## Grid Alternative

```css
.cards {
    display: grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(220px, 1fr)
        );

    gap: 20px;
}
```

Use:

```text
Flexbox
→ Primarily one-dimensional layout

Grid
→ More explicit row-and-column layout
```

---

# 11. Common Patterns

These examples reuse several important HTML and CSS patterns.

---

## Pattern 1 — Flexbox Alignment

Used in:

```text
Hero
Header
Circular icons
Navigation
```

```css
.container {
    display: flex;
    align-items: center;
    justify-content: center;
}
```

---

## Pattern 2 — Horizontal Header

```css
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
```

Think:

```text
LEFT ITEM                         RIGHT ITEM
```

---

## Pattern 3 — Vertical Hero

```css
.hero {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
```

---

## Pattern 4 — Center an Element

For a fixed-width block:

```css
.element {
    margin-left: auto;
    margin-right: auto;
}
```

Modern shorthand:

```css
.element {
    margin-inline: auto;
}
```

With Flexbox:

```css
.container {
    display: flex;
    align-items: center;
    justify-content: center;
}
```

---

## Pattern 5 — Rounded Card

```css
.card {
    background: white;
    padding: 25px;

    border-radius: 15px;

    box-shadow:
        0 8px 20px
        rgba(0, 0, 0, 0.2);
}
```

---

## Pattern 6 — Primary Button

```css
.button {
    padding: 12px 22px;

    background: #1677ff;
    color: white;

    border: none;
    border-radius: 6px;

    cursor: pointer;
}
```

```css
.button:hover {
    opacity: 0.9;
}
```

---

## Pattern 7 — Link Reset

```css
a {
    text-decoration: none;
}
```

```css
a:hover {
    text-decoration: underline;
}
```

---

## Pattern 8 — Consistent Spacing with `gap`

Instead of:

```css
.item {
    margin-right: 20px;
}
```

prefer:

```css
.container {
    display: flex;
    gap: 20px;
}
```

---

## Pattern 9 — Consistent Images

```css
.image {
    width: 100%;
    height: 180px;

    object-fit: cover;

    border-radius: 8px;
}
```

Use:

```text
cover
→ Fill container, possibly crop image

contain
→ Show entire image, possibly leave empty space
```

---

## Pattern 10 — Circular Avatar

```css
.avatar {
    width: 80px;
    height: 80px;

    border-radius: 50%;

    object-fit: cover;
}
```

---

## Pattern 11 — Responsive Flex Cards

```css
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 250px;
}
```

---

## Pattern 12 — Responsive Grid

```css
.grid {
    display: grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(250px, 1fr)
        );

    gap: 20px;
}
```

---

## Pattern 13 — Form Controls

```css
input,
textarea,
select {
    width: 100%;

    box-sizing: border-box;

    padding: 10px;

    border: 1px solid #ccc;
    border-radius: 6px;

    font: inherit;
}
```

---

## Pattern 14 — Focus State

```css
input:focus,
textarea:focus,
select:focus,
button:focus-visible,
a:focus-visible {
    outline: 2px solid #1677ff;
    outline-offset: 2px;
}
```

Visible keyboard focus styles are important for accessibility.

---

## Pattern 15 — Reusable Base Card

Many of these components share the same foundation.

```css
.card-base {
    padding: 20px;

    background: white;

    border-radius: 12px;

    box-shadow:
        0 8px 20px
        rgba(0, 0, 0, 0.2);
}
```

Then combine it with a component class:

```html
<article class="card-base product-card">
    ...
</article>
```

This reduces duplicate CSS.

---

## Pattern 16 — Global Box Sizing

A useful global CSS rule:

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

This makes width and height calculations much easier to reason about.

---

## Pattern 17 — Responsive Width

Instead of:

```css
.card {
    width: 300px;
}
```

consider:

```css
.card {
    width: min(100%, 300px);
}
```

This prevents the card from overflowing very small screens.

---

## Pattern 18 — Semantic HTML

Prefer meaningful elements:

```html
<header>
<nav>
<main>
<section>
<article>
<form>
<footer>
```

instead of making every element a generic:

```html
<div>
```

Semantic HTML improves:

```text
Accessibility
Maintainability
Document structure
SEO
Code readability
```

---

# 12. Complete Example

The concepts from these components can be combined into a simple responsive developer landing page.

## HTML

```html
<!DOCTYPE html>

<html lang="en">

<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>Developer Portfolio</title>

    <link
        rel="stylesheet"
        href="styles.css"
    >
</head>

<body>

    <header class="header">

        <h2>
            DevPortfolio
        </h2>

        <nav>
            <a href="#home">Home</a>
            <a href="#projects">Projects</a>
            <a href="#blog">Blog</a>
            <a href="#contact">Contact</a>
        </nav>

    </header>

    <main>

        <section
            id="home"
            class="hero"
        >

            <h1>
                Build Your Future
            </h1>

            <p>
                Learn coding and create
                amazing websites.
            </p>

            <button type="button">
                Get Started
            </button>

        </section>

        <section class="component-section">

            <h2>
                Featured Components
            </h2>

            <div class="cards">

                <article class="card product-card">

                    <img
                        src="headphones.jpg"
                        alt="Black wireless headphones"
                    >

                    <h2>
                        Wireless Headphones
                    </h2>

                    <p class="price">
                        $49.99
                    </p>

                    <button type="button">
                        Add to Cart
                    </button>

                </article>

                <article class="card id-card">

                    <img
                        class="photo"
                        src="student.jpg"
                        alt="Alex Smith"
                    >

                    <h2>
                        Alex Smith
                    </h2>

                    <p>
                        Student ID: 1024
                    </p>

                    <p>
                        Computer Science
                    </p>

                </article>

                <article class="card pricing-card">

                    <h2>
                        Premium Plan
                    </h2>

                    <p class="price">
                        $19/month
                    </p>

                    <p>
                        Unlimited access
                        to all features.
                    </p>

                    <button type="button">
                        Choose Plan
                    </button>

                </article>

            </div>

        </section>

        <section class="gallery-section">

            <h2>
                Gallery
            </h2>

            <div class="gallery">

                <img
                    src="image1.jpg"
                    alt="City street"
                >

                <img
                    src="image2.jpg"
                    alt="Mountain landscape"
                >

                <img
                    src="image3.jpg"
                    alt="Bowl of fruit"
                >

                <img
                    src="image4.jpg"
                    alt="Abstract architecture"
                >

            </div>

        </section>

        <section
            id="blog"
            class="blog"
        >

            <h1>
                Latest Articles
            </h1>

            <p>
                Explore useful tips and tutorials
                for modern web development.
            </p>

            <article class="post">

                <h2>
                    Getting Started with CSS
                </h2>

                <p>
                    Learn how CSS transforms
                    simple HTML into beautiful
                    web pages.
                </p>

                <a href="#">
                    Read Article →
                </a>

            </article>

        </section>

        <section id="contact">

            <form class="contact-form">

                <h2>
                    Contact Us
                </h2>

                <label for="name">
                    Name
                </label>

                <input
                    id="name"
                    type="text"
                    name="name"
                    placeholder="Your Name"
                    required
                >

                <label for="email">
                    Email
                </label>

                <input
                    id="email"
                    type="email"
                    name="email"
                    placeholder="Your Email"
                    required
                >

                <label for="message">
                    Message
                </label>

                <textarea
                    id="message"
                    name="message"
                    placeholder="Your Message"
                    required
                ></textarea>

                <button type="submit">
                    Send Message
                </button>

            </form>

        </section>

    </main>

</body>

</html>
```

## CSS

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}

body {
    margin: 0;

    font-family:
        Arial,
        sans-serif;

    background: #f3f4f6;
    color: #111827;
}

/* ==============================
   HEADER
   ============================== */

.header {
    display: flex;
    align-items: center;
    justify-content: space-between;

    padding: 18px 25px;

    background: #111827;
}

.header h2 {
    margin: 0;

    color: #1677ff;
}

.header nav {
    display: flex;

    gap: 20px;
}

.header a {
    color: white;

    text-decoration: none;
}

.header a:hover {
    color: #1677ff;
}

/* ==============================
   HERO
   ============================== */

.hero {
    min-height: 400px;

    padding: 40px;

    background: #111827;
    color: white;

    text-align: center;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.hero h1 {
    margin: 0 0 15px;

    color: #1677ff;
}

.hero p {
    margin: 0 0 20px;
}

/* ==============================
   BUTTONS
   ============================== */

button {
    padding: 10px 20px;

    background: #1677ff;
    color: white;

    border: none;
    border-radius: 6px;

    font: inherit;

    cursor: pointer;
}

button:hover {
    opacity: 0.9;
}

button:focus-visible {
    outline: 2px solid #111827;
    outline-offset: 2px;
}

/* ==============================
   COMPONENT SECTION
   ============================== */

.component-section,
.gallery-section {
    padding: 50px 20px;

    text-align: center;
}

/* ==============================
   RESPONSIVE CARDS
   ============================== */

.cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;

    gap: 20px;

    max-width: 1000px;

    margin-inline: auto;
}

.card {
    flex: 1 1 250px;

    max-width: 300px;

    padding: 20px;

    background: white;

    border-radius: 12px;

    box-shadow:
        0 6px 15px
        rgba(0, 0, 0, 0.2);
}

/* ==============================
   PRODUCT CARD
   ============================== */

.product-card img {
    width: 100%;
    height: 180px;

    object-fit: contain;

    background: #e8f1ff;

    border-radius: 8px;
}

.product-card .price {
    color: #1677ff;

    font-size: 20px;
    font-weight: bold;
}

/* ==============================
   ID CARD
   ============================== */

.id-card {
    border: 2px solid #1677ff;
}

.photo {
    width: 100px;
    height: 100px;

    margin: 0 auto 15px;

    border-radius: 50%;

    object-fit: cover;
}

/* ==============================
   PRICING CARD
   ============================== */

.pricing-card {
    border: 2px solid #1677ff;
}

.pricing-card .price {
    color: #1677ff;

    font-size: 22px;
    font-weight: bold;
}

/* ==============================
   GALLERY
   ============================== */

.gallery {
    display: grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(180px, 1fr)
        );

    gap: 10px;

    max-width: 800px;

    margin-inline: auto;
}

.gallery img {
    width: 100%;
    height: 180px;

    object-fit: cover;

    border-radius: 8px;
}

/* ==============================
   BLOG
   ============================== */

.blog {
    max-width: 700px;

    margin: 0 auto 50px;

    padding: 30px;

    background: white;

    border-radius: 12px;

    text-align: center;
}

.blog h1 {
    margin-bottom: 10px;

    color: #1677ff;
}

.blog > p {
    color: #555;
}

.post {
    margin-top: 25px;

    padding: 20px;

    border: 1px solid #ddd;
    border-radius: 8px;

    text-align: left;
}

.post h2 {
    margin-top: 0;
}

.post a {
    color: #1677ff;

    text-decoration: none;

    font-weight: bold;
}

.post a:hover {
    text-decoration: underline;
}

/* ==============================
   CONTACT FORM
   ============================== */

.contact-form {
    width: min(100%, 400px);

    margin: 0 auto 50px;

    padding: 25px;

    background: white;

    border-radius: 12px;

    box-shadow:
        0 8px 20px
        rgba(0, 0, 0, 0.2);
}

.contact-form h2 {
    margin: 0 0 18px;

    text-align: center;
}

.contact-form label {
    display: block;

    margin-top: 12px;

    font-weight: bold;
}

.contact-form input,
.contact-form textarea {
    width: 100%;

    padding: 10px;

    margin-top: 5px;

    border: 1px solid #ccc;
    border-radius: 6px;

    font: inherit;
}

.contact-form textarea {
    min-height: 120px;

    resize: vertical;
}

.contact-form input:focus,
.contact-form textarea:focus {
    outline: 2px solid #1677ff;
    outline-offset: 2px;
}

.contact-form button {
    width: 100%;

    margin-top: 15px;
}

/* ==============================
   RESPONSIVE
   ============================== */

@media (max-width: 767px) {

    .header {
        flex-direction: column;

        gap: 15px;
    }

    .header nav {
        flex-wrap: wrap;
        justify-content: center;
    }

    .hero {
        min-height: 350px;

        padding: 30px 20px;
    }

    .blog {
        margin-inline: 20px;
    }

    .contact-form {
        width: calc(100% - 40px);
    }

}
```

---

# Component Mental Model

```text
WEB PAGE
│
├── HEADER
│   ├── Branding
│   └── Navigation
│
├── HERO
│   ├── Headline
│   ├── Supporting Text
│   └── CTA Button
│
├── CARDS
│   ├── Product Card
│   ├── Profile / ID Card
│   ├── Pricing Card
│   └── Content Card
│
├── GALLERY
│   └── Responsive Image Grid
│
├── CONTENT
│   ├── Section Heading
│   ├── Description
│   └── Article Cards
│
└── FORM
    ├── Labels
    ├── Inputs
    ├── Textarea
    └── Submit Action
```

---

# Key CSS Concepts Used

```text
display: flex
        ↓
One-dimensional layout

display: grid
        ↓
Two-dimensional layout

align-items
        ↓
Cross-axis alignment

justify-content
        ↓
Main-axis alignment

flex-wrap
        ↓
Move items to additional rows

flex
        ↓
Control grow, shrink, and base size

gap
        ↓
Spacing between children

padding
        ↓
Space inside an element

margin
        ↓
Space outside an element

border-radius
        ↓
Rounded corners

box-shadow
        ↓
Visual depth

object-fit
        ↓
Control image sizing/cropping

max-width
        ↓
Prevent excessive width

box-sizing
        ↓
Predictable element dimensions

@media
        ↓
Responsive behavior
```

---

# Layout Decision Guide

```text
Need elements side-by-side?
        ↓
     Flexbox

Need rows AND columns?
        ↓
       Grid

Need cards to wrap automatically?
        ↓
Flexbox + flex-wrap

Need responsive columns?
        ↓
Grid + auto-fit + minmax()

Need a centered column?
        ↓
Flexbox + flex-direction: column

Need consistent card sizing?
        ↓
Reusable base card class

Need consistent images?
        ↓
width + height + object-fit
```

---

# Main Takeaway

These components demonstrate a common frontend development workflow:

```text
Semantic HTML
      +
Reusable CSS classes
      +
Flexbox / Grid
      +
Reusable card patterns
      +
Responsive behavior
      +
Accessible forms
      =
Reusable UI component system
```

As the component library grows, look for repeated CSS such as:

```text
Backgrounds
Border radii
Shadows
Button styles
Spacing
Colors
Typography
```

and move those into reusable base classes or design variables rather than duplicating them across every component.