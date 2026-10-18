# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static academic website for the Auxetics Lab at Griffith University. The site is hosted on DigitalOcean and serves as the lab's online presence, showcasing research, team members, publications, and contact information.

## Architecture

Plain static HTML with one shared stylesheet; no JavaScript and no build step.

- **HTML pages**: every page repeats the same `<head>`, `<header class="site-header">` (brand + nav) and `<footer class="site-footer">`. When adding a page or nav item, update all eight pages. The current page's nav link carries `aria-current="page"`.
- **Content layout**: `.page-head` (h1 + lead), then `.section` blocks (an `<h2>` label column + `.section-body` content column). Other components: `.figure`, `.epigraph`, `.project` (research), `.people`/`.person` cards, `.pubs` (publications, grouped by year), `.course`, `.resource`, `.note`, `.more` (arrow link).
- **CSS**: `/assets/styles.css`, themed by tokens in `:root` (colours, type sizes, layout width). Inter is self-hosted as the variable font (`assets/fonts/Inter-roman.var.woff2`, `Inter-italic.var.woff2`); no Google Fonts requests.
- **Images**: `/assets/images/` (subfolders `index/`, `research/`, `resource/`). Portraits are initials-named, square-ish, max 480 px wide; figures max 2000 px wide. Always give `<img>` an `alt`, `width`/`height`, and `loading="lazy"` below the fold. Logos in the people grid use `class="logo"` so they aren't cropped.
- External links use `target="_blank" rel="noopener"`.

## Common Development Tasks

### Deployment
The website is deployed on DigitalOcean using a LEMP stack. To update the live site:
```bash
git pull origin main
```
(Run from `/var/www/auxeticslab.com/html` on the server)

### Content Updates
- **Team Members**: Update `/people.html` and add/update photos in `/assets/images/`
- **Research Content**: Modify `/research.html` and associated images in `/assets/images/research/`
- **Publications**: Update the publications list in `/publications.html`
- **Homepage**: Main content in `/index.html` with hero image in `/assets/images/index/`

### CSS Modifications
All styling is centralized in `/assets/styles.css`; change colours, sizes and widths through the `:root` tokens.

## Content Structure

Each HTML page follows this consistent structure:
1. Header section with lab branding and university affiliation
2. Navigation menu (8 main sections)
3. Main content using grid layout system
4. Footer with affiliation, copyright and privacy link (inline in every page)

Key sections:
- **Home** (`index.html`): Lab introduction, research focus, team overview
- **Research** (`research.html`): Detailed research areas and projects
- **Publications** (`publications.html`): Year-organized publication listings
- **Teaching** (`teaching.html`): Course and educational content
- **Resources** (`resources.html`): Lab resources and tools
- **People** (`people.html`): Team member profiles with photos
- **Positions** (`positions.html`): Job openings and opportunities
- **Contact** (`contact.html`): Contact information and location

## File Conventions

- HTML files use consistent DOCTYPE and meta tags
- Image naming uses initials for team members (e.g., `MJM.jpg`)
- All external links open in new tabs with appropriate targets
- CSS classes follow semantic naming conventions
- Font files include complete Inter family with WOFF/WOFF2 formats

## Domain and Hosting

- Domain: `www.auxeticslab.com` (configured via CNAME file)
- Hosted on DigitalOcean droplet with LEMP stack
- Static site deployment via Git repository sync