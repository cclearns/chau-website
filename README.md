# Chau Cao — Personal Academic Website

Static, framework-free HTML/CSS site. Reads as a single continuous document —
bio, publications, and research flow one into the next, closed with a short
signoff — rather than a navigated multi-section app.

Designed with [Hallmark](https://github.com/) (macrostructure: Long Document,
theme: Atelier).

## Files

- `index.html` — all page content
- `tokens.css` — design tokens (colour, type, spacing, motion) — imported first
- `style.css` — all styling, references tokens by name; light/dark mode via
  `prefers-color-scheme`
- `.hallmark/` — design-system memory (not required for the site to run;
  safe to delete or keep out of version control)

## Local preview

Just open `index.html` directly in a browser, or serve the folder:

```
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Deploying to GitHub Pages

1. Create a new GitHub repository (e.g. `chau-website` or `<username>.github.io`).
2. Push these files to the repo's default branch:
   ```
   git init
   git add index.html tokens.css style.css README.md
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<username>/<repo>.git
   git push -u origin main
   ```
3. On GitHub, go to **Settings → Pages**.
4. Under **Source**, select **Deploy from a branch**, pick `main` and `/ (root)`, then save.
5. The site will be live at `https://<username>.github.io/<repo>/` (or
   `https://<username>.github.io/` if the repo is named `<username>.github.io`)
   within a minute or two.

## Updating content

- **Bio**: edit the opening paragraphs inside `<article class="prose">` in `index.html`.
- **Publications**: add new `<li>` entries inside the `.bib-list` under the
  "Journal articles" or "Translation works" heading in the `#publications` section.
- **Research**: edit the paragraphs inside the `#research` section.
- **Colours / fonts / spacing**: change values in `tokens.css` only — `style.css`
  references everything by token name, so a palette or font swap is a one-file edit.
