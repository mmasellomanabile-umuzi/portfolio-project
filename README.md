# Mmasello Manabile Portfolio Website

## Overview

A multi-page portfolio for an aspiring Software Developer, built with HTML5 and CSS3 only. It completes an unfinished starter codebase for the capstone: debugging errors, adding missing features and improving accessibility, design and code quality. Pages: Home, About, Projects, Contact, plus a form confirmation page.

## Issues Found

- **HTML:** missing `lang` attribute, no semantic `<header>`, `<nav>`, `<main>` or `<footer>`, no navigation links, missing image `alt` text, no data table, a form without labels, few input types and no validation attributes.
- **CSS:** few selector types, no navigation, table or form styling, no pseudo-classes, weak box-model use, poor colour contrast, a left-aligned footer, and HTML tags pasted into the stylesheet.

## Fixes Implemented

- Added semantic landmarks and one consistent header, navigation and footer on every page.
- Added descriptive `alt` text to all images and a skills table on the About page.
- Rebuilt the contact form with labels, a `fieldset`, six input types plus a dropdown, and HTML5 validation.
- Added navigation, table and form styling, hover, focus and active states, a CSS-only typing animation and responsive layouts.
- Fixed contrast, footer alignment, indentation, naming and redundant code, and added comments and custom properties.

## HTML Structure

Every page uses `<header>` with `<nav>`, `<main>` (holding `<section>` and `<article>` blocks) and `<footer>`. The only non-semantic `<div>` is the footer layout wrapper. Each page has one `<h1>`, headings follow in order, and the current page link carries `aria-current="page"`.

## CSS Approach

`css/styles.css` is split into numbered, commented sections and stores the palette in custom properties. Selectors used: element, class, ID (`#contact-info`), descendant, child (`.card-grid > article`), attribute (`input[type="radio"]`) and pseudo-class (`:hover`, `:focus`, `:active`, `:nth-child`). Layout uses Flexbox and Grid, with media queries at 1200, 1100 and 768 px.

## Accessibility Improvements

- Text colours meet the 4.5:1 contrast ratio.
- Every form control has a label, and radio buttons sit in a `fieldset` with a `legend`.
- Visible `:focus` outlines, image `alt` text, an iframe `title` and `aria-label`s on icon-only links.
- The typing animation stops for visitors who prefer reduced motion.

## How to View

1. Clone the repository: `git clone https://github.com/mmasellomanabile-umuzi/portfolio-project.git`
2. Open `index.html` in Chrome or Edge and use the navigation links.
3. Or visit the published site: https://mmasellomanabile-umuzi.github.io/portfolio-project/

## Screenshots

all screenshots are located in folder -Screenshots/After(FinalProject)/Before(StarterCode)


| Home | About |
|---|---|
| ![Home page](screenshots/homepage.png) | ![About page](screenshots/about.png) |

| Projects | Contact |
|---|---|
| ![Projects page](screenshots/projects.png) | ![Contact page](screenshots/contact.png) |

| Form | Table |
|---|---|
| ![Contact form](screenshots/form.png) | ![Skills table](screenshots/table.png) |

| Navigation hover | W3C validation |
|---|---|
| ![Navigation hover](screenshots/nav-hover.png) | ![W3C results](screenshots/w3c-validation.png) |

![Before and after](screenshots/before-after.png)

## Reflection

**Invalid CSS value.** A `nav :hover` rule contained `transform: matrix(-10)`, which is invalid because `matrix()` needs six values. Reading the W3C CSS validator output line by line led me straight to it. I removed it and scoped the rule to `nav a:hover`, so only the links change colour.

**Unclosed tag.** `contact.html` was missing its closing `</footer>`. Browsers correct this silently, so the page looked fine and only the HTML validator exposed it. I learned to validate with tools rather than trust how a page looks.
