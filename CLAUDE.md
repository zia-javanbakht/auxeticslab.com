# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static academic website for the Auxetics Lab at Griffith University. The site is hosted on DigitalOcean and serves as the lab's online presence, showcasing research, team members, publications, and contact information.

## Architecture

The website follows a simple static HTML structure with shared styling:

- **HTML Pages**: Each page (`index.html`, `research.html`, `people.html`, etc.) follows a consistent template structure with:
  - Common header with lab branding and university affiliation
  - Navigation menu across all pages
  - Grid-based content layout using CSS Grid
  - Shared footer with copyright information

- **CSS Architecture**: 
  - Single stylesheet at `/assets/styles.css` with CSS custom properties (variables) for consistent theming
  - Grid system using 12-column layout (`gc-start-*` and `gc-end-*` classes)
  - Typography system with Inter and Source Serif Pro fonts
  - Responsive design with mobile-first approach

- **Assets Organization**:
  - Fonts stored in `/assets/fonts/` (Inter font family with all variants)
  - Images in `/assets/images/` with subdirectories for specific sections (index/, research/, resource/)
  - Team member photos follow consistent naming (initials.jpg/png)

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
All styling is centralized in `/assets/styles.css`. The system uses:
- CSS custom properties for colors, typography, and layout values
- Grid system with predefined column classes
- Consistent spacing and typography scales
- Component-based class naming (e.g., `link-navigation`, `text-size-*`)

## Content Structure

Each HTML page follows this consistent structure:
1. Header section with lab branding and university affiliation
2. Navigation menu (8 main sections)
3. Main content using grid layout system
4. Footer with copyright and privacy links

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