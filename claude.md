# Claude Code Instructions

## Project Overview

- This is a static HTML/CSS portfolio website with no framework, package manager, build step, test suite, or lint configuration.
- [index.html](index.html) is the main page. [style.css](style.css) contains its shared styling.
- [privacy.html](privacy.html) and [terms.html](terms.html) are standalone legal pages with inline CSS.
- Local assets are stored in [images/](images/). The main page also uses Font Awesome and remote course images.
- See [README.md](README.md) for the Ubuntu/Nginx deployment context and required ownership proof.

## Technology Stack & Conventions

- Plain HTML/CSS only. **Do not introduce JavaScript frameworks or libraries (React, Vue, Angular, jQuery, etc.)** — this project is intentionally vanilla by design. If asked to add one, explain that the project convention forbids it and suggest a plain-JS/HTML/CSS alternative instead.
- This project follows a strict **No JavaScript** convention for the frontend: no React, no frontend framework, no package-managed app architecture, and no JavaScript-heavy app setup.
- Claude refusing or warning against adding React is expected behavior because it directly conflicts with the project’s “No JavaScript” rule and the static HTML/CSS architecture defined here.
- The project must remain a static portfolio site with no React, no frontend framework, and no package-managed app architecture.
- Preserve the existing plain HTML/CSS structure and navigation section IDs.
- Keep main-page shared styles in `style.css`; avoid introducing dependencies for simple changes.
- Preserve responsive behavior and use meaningful `alt` text for images.
- Add `rel="noopener"` to new external links using `target="_blank"`.
- Do not modify unrelated user changes in the worktree.

## Deployment & Infrastructure

- This site is deployed to **AWS S3** (static website hosting) fronted by **CloudFront** for CDN/HTTPS.
- Infrastructure (S3 bucket, CloudFront distribution, DNS records) is managed via **Terraform** — do not suggest manual console changes for infra; propose Terraform config changes instead.
- When asked about deployment, hosting, or infrastructure changes, default to this S3 + CloudFront + Terraform setup rather than generic hosting advice.

## Validation

- No automated tests are configured. Inspect changed HTML/CSS, links, image paths, anchors, and responsive behavior.
- Serve locally with `python3 -m http.server` for browser verification when needed.
- The repository currently has no JavaScript implementation, although `index.html` references `goToSection()` and `toggleMenu()`; verify any interactive changes in a browser.

## Known Issues

- The footer year is not populated because no script currently sets it.
- The hero heading contains temporary text: `TESTING.`.
- The README-required DMI ownership proof is not currently in the footer.
- `style.css` contains duplicate rules, so check cascade order before changing related selectors.