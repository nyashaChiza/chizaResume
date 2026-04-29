# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static HTML personal resume/portfolio website for Nyasha Chizampeni. No build system, no package manager, no dependencies to install — open `index.html` directly in a browser to view.

## Running the Site

Open `index.html` in a browser. For a local dev server with live reload you can use any static file server, e.g.:

```bash
npx serve .
# or
python -m http.server 8080
```

## Architecture

Single-page layout with two columns driven entirely by CSS:

- **Left sidebar** (`left-content`, fixed 300px): name/logo, anchor nav links, social icons, contact info
- **Right main content** (`main-content`, `flex: 1`, scrollable): stacked `<div class="section1">` blocks — one per resume section (`#Home`, `#About`, `#Work`, `#Portfolio`, `#Education`, `#Skills`)

Navigation links are plain `<a href="#SectionId">` anchors. The `js/scripts.js` file contains jQuery-based smooth-scrolling and scrollspy logic inherited from the Start Bootstrap Resume template, but **jQuery is not currently loaded** in `index.html` — the script is effectively inert.

External CDN dependencies (no local copies):
- Font Awesome 4.7.0 — icons throughout
- Google Fonts — Quicksand (body) and Roboto (name/role/headings)

## CSS Conventions

`css/styles.css` uses utility classes for spacing (`.p-30`, `.m-10`, etc.) and flex layout (`.d-flex`, `.d-flex-align-center`, `.flex-1`). Section content goes inside `.text` divs. Section titles use `.sec-title > .pg-sub-title + .pg-title`.
