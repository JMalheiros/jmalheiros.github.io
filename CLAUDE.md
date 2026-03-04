# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

JM Station is a Hugo static site/blog in Portuguese (pt-br) using the PaperMod theme (added as a git submodule).

## Build & Development Commands

```bash
hugo server                 # Local dev server at http://localhost:1313 with live reload
hugo server --buildDrafts   # Include draft posts in dev server
hugo                        # Build production site (output to public/)
hugo new content posts/my-post.md  # Create a new post from archetype
```

Requires Hugo >= 0.146.0.

## Architecture

- **hugo.yaml** — Site configuration (base URL, language, title, theme)
- **archetypes/default.md** — Template for new content (date, draft, title front matter)
- **content/** — Markdown posts and pages
- **layouts/** — Custom layout overrides (takes precedence over theme layouts)
- **static/** — Static files served as-is (images, etc.)
- **assets/** — Files processed by Hugo's asset pipeline (CSS/JS)
- **themes/PaperMod/** — Git submodule; do not edit directly

## Content Conventions

Posts use YAML front matter:

```yaml
---
date: '2026-01-15'
draft: true
title: 'Post Title'
---
```

Set `draft: false` when ready to publish. Drafts are excluded from production builds.

## Theme Customization

Override PaperMod templates by placing files in `layouts/` mirroring the theme's structure (e.g., `layouts/partials/header.html` overrides `themes/PaperMod/layouts/partials/header.html`). Same applies to `assets/css/extended/` for custom CSS.
