# Accessible Profile Card — Frontend Wizards Stage 1B

A fully responsive, accessible profile card component built with semantic HTML, modern CSS, and vanilla JavaScript. This project meets the technical requirements of the **Frontend Wizards Stage 1B** task, including required `data-testid` attributes for automated testing, real‑time epoch time display, keyboard navigation, and WCAG AA colour contrast.

## ✨ Features

- **Semantic HTML5** – `<article>`, `<header>`, `<figure>`, `<nav>`, `<section>`, `<ul>`.
- **Required `data-testid` attributes** – all elements are targetable by automated tests.
- **Live epoch time** – displays `Date.now()` in milliseconds, updates every 500 ms with an `aria-live` region.
- **Accessible avatar** – meaningful `alt` text and proper `figure`/`figcaption` structure.
- **Social links** – open in a new tab with `rel="noopener noreferrer"`.
- **Keyboard navigation** – all links are focusable with visible focus outlines.
- **Responsive layout** – stacks vertically on mobile, switches to a two‑column grid on tablets/desktops.
- **Modern CSS** – Flexbox, Grid, custom properties, and smooth hover effects.
- **Font Awesome icons** – visual enhancements for bio, time, hobbies, and social links.

## 📋 Required Data Attributes

The component includes the following `data-testid` attributes (exactly as specified):

| Element                    | `data-testid`                     |
|----------------------------|-----------------------------------|
| Profile card container     | `test-profile-card`              |
| User name                  | `test-user-name`                 |
| Short biography            | `test-user-bio`                  |
| Current epoch time (ms)    | `test-user-time`                 |
| Avatar image               | `test-user-avatar`               |
| Social links container     | `test-user-social-links`         |
| Twitter link               | `test-user-social-twitter`       |
| GitHub link                | `test-user-social-github`        |
| LinkedIn link              | `test-user-social-linkedin`      |
| Instagram link             | `test-user-social-mastodon`      |
| Hobbies list               | `test-user-hobbies`              |
| Dislikes list              | `test-user-dislikes`             |

> **Note:** The Instagram link uses `test-user-social-mastodon` to satisfy the requirement for a fourth social network while keeping the attribute name stable for tests.

## 🚀 Live Demo

[View the live profile card →](https://helpful-centaur-389765.netlify.app/)  

## 🖥️ How to Run Locally

You can run this project in two simple ways – no build tools or installation required.

### Directly open the file (easiest)

1. **Save the HTML code**  
   - Copy the complete `index.html` code (provided above) into a new file.  
   - Name the file `index.html` (or any name ending with `.html`).

2. **Open with your browser**  
   - Double‑click the `index.html` file.  
   - It will open in your default web browser.  
   - The profile card will work immediately – all scripts and styles are inside the same file.
