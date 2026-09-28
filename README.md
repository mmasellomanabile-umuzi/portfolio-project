# Mmasello Manabile Portfolio Website

## Overview

A multi-page portfolio for an aspiring Software Developer, built with HTML5 and CSS3 only. It completes an unfinished starter codebase for the capstone: debugging errors, adding missing features and improving accessibility, design and code quality. Pages: Home, About, Projects, Contact, plus a form confirmation page.

## Issues Found

- **HTML:** missing `lang` attribute, no semantic `<header>`, `<nav>`, `<main>` or `<footer>`, no navigation links, missing image `alt` text, no data table, a form without labels, few input types and no validation attributes.
- **CSS:** few selector types, no navigation, table or form styling, no pseudo-classes, weak box-model use, poor colour contrast, a left-aligned footer, and HTML tags pasted into the stylesheet.

## Fixes Implemented

- Added semantic landmarks, and the same navigation menu and footer on every page.
- Added descriptive `alt` text to all images and a skills table on the About page.
- Rebuilt the contact form with labels, a `fieldset`, six input types plus a dropdown, and HTML5 validation.
- Added navigation, table and form styling, hover, focus and active states, a CSS-only typing animation and responsive layouts.
- Fixed contrast (including the form button hover and required markers), footer alignment, indentation, naming and redundant code, and added comments and custom properties.

## HTML Structure

Every page uses `<header>` with `<nav>`, `<main>` (holding `<section>` and `<article>` blocks) and `<footer>`. The only non-semantic `<div>` is the footer layout wrapper. Each page has one `<h1>`, headings follow in order, and the current page link carries `aria-current="page"`.

A design decision was taken to include social links on `index.html` and `submit.html` only, as this presents the site better.

## CSS Approach

`css/styles.css` is split into numbered, commented sections and stores the palette in custom properties. Selectors used: element, class, ID (`#contact-info`), descendant, child (`.card-grid > article`), attribute (`input[type="radio"]`) and pseudo-class (`:hover`, `:focus`, `:active`, `:nth-child`). Layout uses Flexbox and Grid, with media queries at 1200, 1100 and 768 px.

## Accessibility Improvements

- All text colours, including hover states and required markers, meet the 4.5:1 contrast ratio.
- Every form control has a label, and radio buttons sit in a `fieldset` with a `legend`.
- Visible `:focus` outlines, image `alt` text, an iframe `title` and `aria-label`s on icon-only links.
- The typing animation stops for visitors who prefer reduced motion.

## How to View

1. Clone the repository: `git clone https://github.com/mmasellomanabile-umuzi/portfolio-project.git`
2. Open `index.html` in Chrome or Edge and use the navigation links.
3. Or visit the published site: https://mmasellomanabile-umuzi.github.io/portfolio-project/

## Screenshots

Final site: `screenshots/After(FinalProject)`. 

![Home](<Screenshots/After(FinalProject)/index.html.png>)
![About and skills table](<Screenshots/After(FinalProject)/about.html.png>)
![Projects](<Screenshots/After(FinalProject)/projects.html.png>)
![Contact form](<Screenshots/After(FinalProject)/contact.html.png>)
![Confirmation](<Screenshots/After(FinalProject)/submit.html.png>)
![CSS validation](<Screenshots/After(FinalProject)/CSS Validation.png>)
![Home validation](<Screenshots/After(FinalProject)/indexW3c validator.png>)
![About validation](<Screenshots/After(FinalProject)/W3C_about.html.png>)
![Contact validation](<Screenshots/After(FinalProject)/W3C_contact.html.png>)
![Projects validation](<Screenshots/After(FinalProject)/W3C_projects.html.png>)
![Navigation hover state](<Screenshots/After(FinalProject)/nav-hover.png>)


## Reflection

Debugging the starter code taught me to measure problems instead of guessing. Three examples:

- **Pasted HTML in the stylesheet.** The CSS contained stray `<br>` tags. I found them by reading the file, removed them, and re-ran the W3C CSS validator until it reported no errors.
- **An invalid hover rule.** `nav :hover` used `transform: matrix(-10)`, which the validator rejects, and the selector recoloured everything inside the nav. I replaced it with `.nav-links a:hover` and a simple colour transition.
- **Contrast that only looked fine.** My first form-button hover colour still failed. Calculating the ratio showed 3.77:1, so I switched to the darker accent colour (6.66:1) and did the same for the required-field asterisk.

I also missed a closing `</footer>` in `contact.html` until feedback pointed it out. Re-running both validators after every change is now my habit.

- The issues found have been documented in a .pdf file (design/issues-identified.txt)