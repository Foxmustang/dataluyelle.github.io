# dataluyelle.github.io
Here is the place where people can discover my projects.


## **HTML files** — the pages themselves
index.html is the mandatory entry point. When someone visits yourusername.github.io, the server automatically looks for a file named exactly index.html at the root. It's your homepage. Every website needs one.
about.html and contact.html are additional pages. Each HTML file = one URL:

about.html → yourusername.github.io/about.html
contact.html → yourusername.github.io/contact.html

You link between them with simple anchor tags: <a href="about.html">About</a>

assets/ — everything that isn't a page
This folder holds all the supporting files your HTML pages depend on. It's purely a convention (you could name it static/ or public/), but assets/ is widely understood.
css/style.css controls the visual appearance — colors, fonts, spacing, layout, animations. Without it, your pages render in plain browser-default styling (ugly). You link it in the <head> of each HTML file:
html<link rel="stylesheet" href="assets/css/style.css" />
js/main.js adds interactivity — things like dropdown menus, form validation, animations triggered by scrolling, or fetching data from an API. Without JS, your site is static and can't react to user actions. You load it just before </body>:
html<script src="assets/js/main.js"></script>
img/logo.png (and any other images) live here. Keeping them in a dedicated folder prevents clutter. You reference them in HTML or CSS:
html<img src="assets/img/logo.png" alt="Logo" />

## README.md — for humans on GitHub, not visitors
This file is never shown to your website visitors. It's rendered by GitHub on your repository's page (github.com/yourusername/yourusername.github.io) as a description of the project — what it is, how to run it locally, how to contribute. Totally optional, but good practice.

How they all connect
Browser requests yourusername.github.io
        │
        ▼
    index.html        ← structure & content
        │
        ├── loads ──► assets/css/style.css    (how it looks)
        ├── loads ──► assets/js/main.js       (how it behaves)
        └── uses  ──► assets/img/logo.png     (media)
HTML is the skeleton, CSS is the skin, JS is the muscles. The assets/ folder just keeps those three categories tidy and separate.
