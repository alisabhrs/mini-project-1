# BCA WEBSITE, CODE NOTES

## 1. HTML BASICS

- `<!DOCTYPE html>` → tells browser this is HTML5
- `<html lang="en">` → page is written in English
- `<head>` → behind-the-scenes page information
- `<body>` → visible website content
- `charset="UTF-8"` → character encoding; makes text/symbols display correctly
- `viewport` → helps website fit different screen sizes
- `width=device-width` → page width matches device width
- `initial-scale=1.0` → starts at normal 100% zoom
- `<title>` → browser tab title
- `<link>` → connects another file/resource
- `rel="stylesheet"` → says the linked file is CSS
- `href` → destination of a link
- `src` → source/location of an image
- `alt` → alternative description of an image for accessibility
- `class` → reusable label used mainly for CSS styling
- `id` → unique identifier; can also be a destination for `#` links
- `<div>` → general container/group
- `<span>` → small inline container, often used to style specific text
- `<br>` → line break
- `<p>` → paragraph
- `<strong>` → strong importance; normally bold
- `<em>` → emphasis; normally italic unless CSS changes it
- `<a>` → link
- `<img>` → image
- `<section>` → groups a major section of the page
- `<article>` → self-contained piece of content
- `<header>` → introductory/top content
- `<nav>` → navigation links
- `<footer>` → bottom section of page

---

## 2. NAVIGATION

```html
<header class="navbar">
```

- `<header>` holds the navigation area.
- `class="navbar"` connects it to `.navbar` in CSS.
- Logo is an image plus text.
- `<nav>` contains HOME, ABOUT, PROGRAMS, RESOURCES, CONTACT.

### Links

```html
href="#home"
```

→ jumps to an element on the **same page** with `id="home"`.

```html
href="about.html"
```

→ opens a **different HTML page**.

### Main CSS

- `position: fixed` → navbar stays visible while scrolling
- `top: 0` → places it at top
- `width: 100%` → full width
- `z-index: 100` → keeps navbar above other content
- `display: flex` → Flexbox layout
- `justify-content: space-between` → logo left, links right
- `align-items: center` → vertically aligns items
- `gap` → space between items
- `:hover` → styling when mouse is over an element

---

## 3. HERO

The **hero** is the large first section underneath the navigation.

```html
<section id="home" class="hero">
```

- `id="home"` → HOME links can jump here.
- `class="hero"` → connects section to `.hero` CSS.
- Contains headline, description, button, and scroll link.

```html
<em>STARTS WITH US!</em>
```

`em` = **emphasis**.

### Hero CSS

- `min-height: 100vh` → hero is at least the full height of the screen
- `background` → combines image + green gradient
- `background-size: cover` → image fills area
- `background-position: center` → centers image
- `padding` → space inside section
- `position: relative` → allows positioned children to use hero as reference
- `z-index` → controls which elements appear in front
- `clamp()` → responsive font sizing

---

## 4. SKILLS STRIP

Moving strip containing:

Problem Solving ✹ Strategy ✹ Data Analysis ✹ Communication etc.

### How it moves

This is **CSS animation, not JavaScript**.

```css
animation: marquee-scroll 25s linear infinite;
```

- `25s` → one animation cycle takes 25 seconds
- `linear` → constant speed
- `infinite` → repeats forever

```css
@keyframes marquee-scroll
```

→ defines the animation.

```css
transform: translateX(-50%);
```

→ moves the strip horizontally.

The skills are duplicated in the HTML to make the animation look like a continuous loop.

`aria-hidden="true"` hides the duplicate copy from screen readers.

---

## 5. WHO WE ARE

```html
<section id="about" class="about">
```

Contains:
- ABOUT BCA
- WHO WE ARE
- description
- statistics
- group photo area
- Learn More button

### Layout

```css
display: grid;
grid-template-columns: 1.15fr 0.85fr;
```

Uses **CSS Grid** to create two columns.

### Statistics

Four stat cards:
- 40+ Events
- 600+ Members
- 20+ Firms
- 8 Officers

`data-target` stores the number the counter should reach.

The **count-up animation uses JavaScript**.

---

## 6. VISION & MISSION

Uses two:

```html
<article>
```

elements for the Vision and Mission cards.

CSS creates the folder/paper appearance using:
- layers
- positioning
- gradients
- border radius
- shadows
- `z-index`

### Hover

```css
.folder-card:hover {
    transform: translateY(-8px);
}
```

When hovered, the folder moves upward slightly.

This is **CSS, not JavaScript**.

---

## 7. PROGRAMS

Five program cards:
- Speaker Events
- CORE
- UCP
- Networking Events
- More Opportunities

Each card has:

```html
program-front
program-back
```

### Card Flip

```css
.program-sheet:hover .program-inner {
    transform: rotateY(180deg);
}
```

The cards flip when hovered.

**Important: this flip is CSS, NOT JavaScript.**

Other important properties:

- `perspective` → creates 3D depth
- `transform-style: preserve-3d` → keeps children in 3D space
- `backface-visibility: hidden` → hides reverse side
- `rotateY(180deg)` → rotates around Y-axis
- `transition` → makes flip smooth
- `z-index` → controls overlapping cards

---

## 8. RESOURCES

Resources section has:
- heading and description
- Explore Resources button
- decorative background
- flipbook

Flipbook pages include:
1. BCA's Framework
2. What Is Consulting?
3. Case Interviews
4. Consulting Recruiting
5. Want More?

### CSS

CSS creates the **appearance and flipping animation**.

```css
.fb-page.flipped {
    transform: rotateY(-160deg);
}
```

### JavaScript

JavaScript controls the **Back and Next buttons** and determines which page should be flipped.

So:

**CSS = visual flip effect**

**JavaScript = button/page logic**

---

## 9. CONTACT

```html
<section id="contact" class="contact">
```

Contains:
- Instagram
- LinkedIn
- Email
- WhatsApp
- contact button
- Babson College map-style graphic

```html
mailto:bca@babson.edu
```

→ opens the user's email application to send an email.

Contact section uses CSS Grid for the two-column layout.

---

## 10. FOOTER

The footer contains:
- BCA logo/name
- copyright
- Back to Top link

```html
href="#home"
```

→ sends user back to the element with `id="home"`.

---

# CSS BASICS TO REMEMBER

### Selector

```css
.navbar
```

The `.` means select a **class** named `navbar`.

```css
#home
```

The `#` means select an **ID** named `home`.

### Common Properties

- `color` → text color
- `background` → background
- `font-size` → text size
- `font-weight` → thickness/boldness
- `margin` → space **outside** an element
- `padding` → space **inside** an element
- `width` / `height` → size
- `border-radius` → rounded corners
- `gap` → space between Grid/Flex items
- `display: flex` → Flexbox layout
- `display: grid` → Grid layout
- `position` → controls element positioning
- `transform` → moves, rotates, or scales something
- `transition` → smooth change between states
- `overflow: hidden` → hides content extending outside container
- `opacity` → transparency
- `box-shadow` → shadow

---

# FLEXBOX VS GRID

**Flexbox** → best for arranging things mainly in **one direction**, like a row or column.

Example: navbar.

**Grid** → best for layouts with **rows and columns**.

Example: About and Contact sections.

---

# RESPONSIVE DESIGN

```css
@media (max-width: 600px)
```

This is a **media query**.

It applies different CSS when the screen is 600px wide or smaller.

Used to make the website work better on phones.

The website also has tablet breakpoints.

---

# CSS VARIABLES

At the top of the CSS:

```css
:root {
    --green: #065735;
    --light-green: #C9D8C0;
    --white: #ffffff;
}
```

These are reusable **CSS variables**.

Example:

```css
color: var(--green);
```

Instead of repeatedly typing the color code, the variable is reused throughout the site.

---

# HTML VS CSS VS JAVASCRIPT

### HTML = Structure

Defines **what is on the page**.

Examples:
- headings
- paragraphs
- images
- links
- sections
- buttons

### CSS = Appearance + Layout + Many Animations

Controls **how the page looks and moves**.

Examples:
- colors
- fonts
- spacing
- layout
- hover effects
- program card flips
- skills-strip animation
- responsive design

### JavaScript = Behavior / Logic

Used in this homepage for:
- Resources flipbook Back/Next behavior
- animated statistics counters

---

# IMPORTANT CLASS EXPLANATION

If asked about JavaScript:

> “The assignment is primarily HTML and CSS. I was experimenting with a small amount of JavaScript for two interactive elements: the resource flipbook controls and the animated statistics. The rest of the layout, styling, animations, and hover interactions are HTML and CSS.”

---

# QUICK MEMORY GUIDE

**HTML** → structure  
**CSS** → style/layout/animation  
**JavaScript** → behavior/logic

**class** → reusable label  
**id** → unique identifier  
**href** → where a link goes  
**src** → where an image comes from  
**alt** → what an image is  
**span** → wraps small inline content  
**div** → general container  
**em** → emphasis  
**strong** → strong importance  
**br** → line break

**margin** → outside space  
**padding** → inside space  
**flex** → row/column layout  
**grid** → rows + columns  
**hover** → mouse-over state  
**transform** → move/rotate/scale  
**transition** → smooth change  
**media query** → responsive screen-size rules  
**z-index** → stacking order  
**vh** → percentage of viewport height