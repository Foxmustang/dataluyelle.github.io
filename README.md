# dataluyelle.github.io
Personal website for Marguerite de La Tullaye. Built with [Quarto](https://quarto.org/), deployed via GitHub Pages from the `docs/` folder.

## Work with Quarto 

Quarto has to be set up on the computer through : 
1. Quarto installation (in my `Program\` files) through the website : https://quarto.org/docs/get-started/
2. the VScode Quarto installation to have files with the `.yml` extension colored fancyfully

To verify Quarto is well installed, run `quarto --version` in Bash. \\

Then, to have a **local preview** of the website : 

`quarto preview`

It opens at http://localhost:xxxx with live reload. Type Ctrl + C to close the localhost.

To **deploy** : 

``quarto render``

``git add -A``

``git commit -m "update site"``

``git push``

GitHub Pages is configured to serve from the main branch, /docs folder.
If it is not, turn it on GitHub Pages. On GitHub :
* Settings → Pages (menu gauche)
* Source → Deploy from a branch
* Branch → main / docs
* Click Save


## **HTML files** — the pages themselves

Without Quarto, the repository would be organised as follows:

<table>
  <tr>
    <th>File / Folder</th>
    <th>Sub-element</th>
    <th>Description</th>
  </tr>
  <tr>
    <td colspan="2"><code>index.html</code></td>
    <td>Mandatory entry point. When someone visits <code>yourusername.github.io</code>, the server automatically looks for a file named <code>index.html</code> at the root. It is your homepage — every website needs one.</td>
  </tr>
  <tr>
    <td rowspan="3"><code>assets/</code></td>
    <td><code>css/style.css</code></td>
    <td>Controls the visual appearance — colors, fonts, spacing, layout, and animations. Linked in the <code>&lt;head&gt;</code> of each HTML file.</td>
  </tr>
  <tr>
    <td><code>js/main.js</code></td>
    <td>Adds interactivity — dropdown menus, form validation, scroll animations, or API calls. Loaded just before <code>&lt;/body&gt;</code>.</td>
  </tr>
  <tr>
    <td><code>img/</code></td>
    <td>Stores images and other media. Keeping them in a dedicated folder prevents clutter.</td>
  </tr>
</table>

The `assets/` folder holds all the supporting files your HTML pages depend on. The name is a convention — `static/` or `public/` would work equally well.

---

I chose to deploy this website through Quarto, which makes it easier to integrate mathematical equations. The reference file uses the `.qmd` suffix instead of `.html`, and the repository is structured as follows:

<table>
  <tr>
    <th>File / Folder</th>
    <th>Description</th>
  </tr>
  <tr>
    <td><code>_quarto.yml</code></td>
    <td>Defines the site structure, navigation, and external links.</td>
  </tr>
  <tr>
    <td><code>index.qmd</code>, <code>cv.qmd</code>, <code>research.qmd</code></td>
    <td>Root-level files encoding the main pages of the site.</td>
  </tr>
  <tr>
    <td><code>assets/css/custom.scss</code></td>
    <td>Controls the visual design of the site. The <code>assets/</code> folder can hold additional resources if needed.</td>
  </tr>
  <tr>
    <td><code>assets/img/</code></td>
    <td>Stores images used across the site.</td>
  </tr>
  <tr>
    <td><code>fr/</code></td>
    <td>Contains the French version of the site, mirroring the root structure.</td>
  </tr>
  <tr>
  <td><code>docs/.nojekyll</code></td>
  <td>Tells GitHub Pages not to run Jekyll on <code>docs/</code>. Required for Quarto sites, as Jekyll would otherwise ignore folders starting with <code>_</code>.</td>
</tr>
</table>