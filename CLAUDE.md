# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

# CLAUDE.md — calebhoulding.com

Static personal site · GitHub Pages · `master` is live · Template: *Aerial by HTML5 UP* (CC-BY 3.0)

## Core Principles

This is a deliberately tiny static "business card" site. Keep it that way. No build tools, no bundlers, no JS frameworks, no analytics or trackers — every addition has to justify itself. Output only the change; no preamble, no trailing summaries, no restating the request.

Visual design is the user's call — don't restyle, recolour, or "modernise" the layout unless asked. When asked, make the minimal change that achieves the request; don't refactor surrounding HTML/CSS while you're in there.

Never ship bandaid fixes — if the cause of a styling or layout bug is structural, fix the structure, don't pile `!important` on top. If the proper fix is out of scope, stop and tell the user rather than papering over.

## Architecture

Single-page site. The whole thing is:

- **`index.html`** — the page. Pure HTML, no JS. Header contains everything visible: name (`<h1>`), job title (`<p>`), three social icon links (LinkedIn, GitHub, `mailto:` to `business@calebhoulding.com`), and a footer line ("Based in Newcastle Upon Tyne").
- **`assets/css/main.css`** — the active stylesheet. Hand-edited. Edit this directly.
- **`assets/css/fontawesome-all.min.css`** — hand-trimmed Font Awesome stub: two `@font-face` declarations (brands, solid) plus glyph rules for the three icons in use. Edit when adding/removing icons.
- **`assets/css/images/overlay-pattern.png`** — the subtle texture overlay layered above the page background.
- **`assets/webfonts/`** — vendored woff2 fonts: IBM Plex Serif (Light + Bold, latin + latin-ext subsets) and Font Awesome 5 brands + solid. All `@font-face` rules in CSS point here.
- **`CNAME`** — `calebhoulding.com`. Don't remove or rename.
- **`README.txt`** — original Aerial template README with author attribution. Keep it.
- **`LICENSE.txt`** — template licence.

The Aerial template's SCSS sources were removed — `main.css` is the only stylesheet. Don't propose adding a Sass build step.

## Editing

- **Content changes** (name, job title, social links, footer location) → `index.html`.
- **Styling changes** → `assets/css/main.css` only.
- **Adding a new social icon** → add the `<li><a class="icon brands fa-<name>">` in `index.html`, *and* add the corresponding `.fa-<name>:before { content: "\fXXX"; }` rule to `assets/css/fontawesome-all.min.css` (look up the codepoint at fontawesome.com or in a full FA CSS distribution). Only the three glyphs currently shown ship in the trimmed CSS.

## Deploy

Commit to `master` and push. GitHub Pages serves the result at `calebhoulding.com`. There is no staging environment and no CI. Verify locally first by opening `index.html` in a browser (or `python3 -m http.server` from the repo root if you need relative-path-correct testing).

## Don'ts

- Don't add tracking, analytics, or third-party scripts without asking.
- Don't add JS frameworks, bundlers, or a build step. Static HTML/CSS is the design.
- Don't add bytes to `assets/webfonts/` unless adding a new typeface family (it's a tight 6-file set).
- Don't reintroduce a Sass build — `main.css` is hand-edited.
- Don't strip the Aerial template attribution from `README.txt` unless replacing the template wholesale.
- Don't run `git push` without being asked.
