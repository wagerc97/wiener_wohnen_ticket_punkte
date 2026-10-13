# Repository Guidelines

## Project Structure & Module Organization

This is a dependency-free static site for estimating Wiener Wohn-Ticket bonus points. `index.html` contains the application: markup, responsive CSS, translations, form configuration, and calculation logic. Keep it deployable as a single page. `README.md` explains the calculator and cites its source material. `Vergaberichtlinien_FINAL.pdf` is the reference document for rules and point values. `dist/` is a generated or publishable copy; do not make source-only changes there unless the release process requires it. GitHub Pages is deployed through `.github/workflows/static.yml`.

## Build, Test, and Development Commands

- `npm install` installs the development-only HTML linting tool.
- `npm run lint` checks `index.html` for structural HTML errors.
- Open `index.html` in a browser for local verification. Check German and English, light and dark themes, responsive layout, and point combinations.

The Pages workflow publishes the repository contents on pushes to `main`. Keep the root `index.html` as the canonical entry point.

## Coding Style & Naming Conventions

Use two-space indentation for HTML. The existing inline CSS and JavaScript deliberately use compact formatting; avoid large formatting-only rewrites. Use lowercase, hyphenated CSS classes and descriptive lowercase JavaScript identifiers. Add UI copy to both `T.de` and `T.en`, and use `data-i` for translated static text. Preserve accessible labels, `aria-label` attributes, and `rel="noopener noreferrer"` on external links opened in a new tab.

## Testing Guidelines

Run `npm run lint` before every commit. For behavior changes, test each affected input type (select, checkbox, radio) and confirm the total and breakdown update. Verify mutually exclusive point rules with both orders of selection. Any policy or scoring update must be checked against the PDF and reflected in the German and English wording.

## Commit & Pull Request Guidelines

Recent history uses short imperative subjects, such as `Update index.html` and `Create static.yml`. Follow that convention; keep each commit focused. Pull requests should state the user-visible effect, identify the applicable policy source for scoring changes, link related issues when present, and include screenshots for visual updates. Do not present the calculator as an official Wiener Wohnen service.

## Security & Content

The calculator must remain client-side: do not add analytics, form submission, or external tracking without explicit approval. Treat the PDF as source material and retain the user-facing disclaimer.

## Agent Boundaries

Agents may edit and verify files, but must not run Git commands or create commits, branches, pulls, or pushes. Git operations are performed only by the user.
