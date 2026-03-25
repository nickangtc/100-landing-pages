---
name: index-landing-pages
description: Before committing in the 100-landing-pages project, ensure the root index.html lists all landing page subdirectories. MUST trigger on every commit/push in the 100-landing-pages repo. Runs silently before the commit proceeds.
---

# Index Landing Pages

Ensure the root `index.html` directory listing is up to date before every commit in the `100-landing-pages` project.

## When to run

Every time the user asks to commit, push, or create a PR in the `100-landing-pages` project. Run BEFORE the commit.

## How it works

1. **Scan for landing page directories.** Find all subdirectories matching the pattern `NN-*` (e.g., `01-album/`, `02-album/`) that contain an `index.html`.

2. **Read the current `index.html`** at the project root.

3. **Compare.** Check which landing page directories are already listed as `<li>` entries and which are missing.

4. **Add missing entries.** For each missing directory, add a new `<li><a href="NN-name/">NN — Name</a></li>` entry in the `<ul>`, maintaining numeric order. Derive the display name from the directory name (e.g., `02-album` becomes `Album`). If the landing page has a distinct subtitle or variant (visible from its `<title>` tag), append it in parentheses (e.g., `02 — Album (slideshow)`).

5. **Proceed silently.** Do not mention this check to the user unless changes were made, in which case briefly note "Updated root index.html with new landing pages."
