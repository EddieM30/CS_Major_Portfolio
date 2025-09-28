# Portfolio Website

This is a small personal portfolio website (static HTML/CSS/JS) built as a learning project. It contains a hero, about, skills, projects, education, and contact sections plus a mobile sticky navigation bar.

## Project structure

- `index.html` — main HTML document (semantic sections and placeholder content)
- `styles.css` — single stylesheet for layout, components, and responsive rules
- `script.js` — placeholder for interactive behavior (currently empty)
- `profile-pic.jpg` — profile image used in the site
- `project_images/` — images used by project cards
- `SVG Icons/` — folder containing SVG icons used in the site (nav, social, etc.)

## Quick start

The site is static — you can open it directly in a browser:

```bash
# from the project folder (Windows / bash)
# open index.html in your default browser
start "" "index.html"
```

Or serve it locally (recommended if you want correct MIME types for SVGs):

```bash
# Python 3 (in the project folder)
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

## Notes about recent changes

- `styles.css` was reorganized and consolidated to group variables, reset/base styles, layout, sections, nav, forms, accessibility tweaks, and media queries for clarity.
- Fixed a stray token in `styles.css` that was preventing later CSS rules (notably the mobile nav `position: fixed`) from applying.
- Mobile sticky navigation (`.sticky-nav-mobile`) is implemented and set to `position: fixed; bottom: 0; left: 0; right: 0;` in the mobile media query.
- Placeholder content was added to the Skills, Projects, Education, and Contact sections in `index.html` as a starting point.

## Mobile nav troubleshooting

If your mobile nav does not stick to the bottom:

1. Hard-refresh the page (Ctrl+F5) or clear the browser cache — old CSS can persist.
2. Verify you are testing within the mobile media query range (the stylesheet uses the range 320–767px).
3. Open DevTools and inspect the `.sticky-nav-mobile` element. Confirm:
   - `position: fixed` is present in the Computed/Styles panel
   - `bottom: 0` is present
   - If the nav appears behind content, add `z-index: 9999` to `.sticky-nav-mobile` to bring it forward.
4. Check for transforms/filters on ancestors — those can create a containing block that makes `fixed` act like `absolute`.

## Styling / variables

Top-level CSS variables (in `styles.css`) control colors and spacing. Tweak them to change the look easily:

- `--primary` — primary brand color
- `--secondary` — secondary/accent color
- `--accent` — UI accent color (focus outlines, small accents)
- `--background1`, `--background2` — background colors
- `--text` — primary text color
- `--spacing-*` — spacing scale

The mobile nav uses `--mobile-nav-height` and `--mobile-header-height` (adjust carefully if you change header layout).

## Accessibility considerations

- Keyboard focus is preserved via `:focus-visible` outlines on focusable elements in the mobile nav.
- Tap highlight is suppressed for cleaner mobile visuals (`-webkit-tap-highlight-color: transparent`), but keyboard outlines remain.

## Next steps / TODOs

- Add small CSS rules to style the placeholder sections (projects grid, cards, contact form layout).
- Implement a small JS helper to offset anchor scrolling if you want links to land exactly above the sticky nav.
- Replace placeholder content with real project descriptions and images.
- Hook the contact form to a backend (Formspree, Netlify Forms, or custom endpoint).

## Commit message suggestion (recent changes)

"Refactor styles; fix mobile nav parsing bug; add placeholder content for skills/projects/education/contact"

## License

This project is personal; add a license (e.g. MIT) if you plan to publish it publicly.

---

If you want, I can also:
- Add the anchor-scroll JS helper and show how to install it,
- Create minimal CSS for the placeholder sections so they look polished,
- Or generate a short CHANGELOG.md capturing the file edits.

Which would you like next?