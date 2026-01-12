# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal portfolio website for John Dall'Olio (GitHub username: CelalKincross), showcasing IT System Administration, Cybersecurity, and Software Development work. The site is deployed via GitHub Pages at CelalKincross.github.io.

## Tech Stack

- **Frontend**: Pure HTML5, CSS3, JavaScript (no frameworks)
- **Styling**: Custom CSS with CSS variables for theming (Inter font family)
- **Deployment**: GitHub Pages (deployed directly from repository)
- **Form Handling**: Formspree integration for contact form

## Development Commands

### Local Development
```bash
# Run local server (from website/ directory)
python3 -m http.server

# Then open http://localhost:8000 in browser
```

### Deployment
```bash
# Commit and push to deploy (GitHub Pages serves from main branch)
git add .
git commit -m "Your message"
git push origin main
```

No build process is required - this is a static site that deploys directly.

## Site Structure

```
website/
├── index.html          # Main landing page with hero, certifications, projects
├── cv.html             # Full CV/resume page
├── blog.html           # Blog index page
├── blog/               # Individual blog posts
│   ├── automating-linux-admin.html
│   ├── handling-zero-day.html
│   └── securing-supply-chain.html
├── assets/
│   ├── css/styles.css  # Single stylesheet with CSS variables
│   ├── js/app.js       # Mobile nav toggle functionality
│   ├── icons/          # Certification badges, social icons, favicons
│   ├── images/         # Project screenshots, profile images
│   └── docs/           # Downloadable documents (e.g., presentations)
└── personal/           # Not part of the website (CV PDFs, presentations)
```

## Architecture Notes

### CSS Design System
The site uses a minimal design system with CSS custom properties defined in `styles.css`:
- Color scheme: Neutral greys with GitHub-inspired accent colors (`#24292e`)
- Typography: Inter font family throughout
- Responsive design using media queries (no CSS framework)

### Navigation
- Consistent navigation bar across all pages (index, cv, blog)
- Mobile-responsive burger menu toggled via `app.js`
- All navigation links use relative paths

### Content Sections
- **Hero/About**: Bio with profile image
- **Certifications**: Linked certification badges (CISSP, CompTIA Security+, Google Cybersecurity, ISC2 CC)
- **Projects**: Cards linking to GitHub repositories
- **Blog**: Technical articles on System Administration and Security
- **Contact**: Formspree-powered contact form

## Key Considerations When Editing

1. **Navigation Consistency**: When adding new pages, ensure the navigation bar matches the pattern in existing pages (index.html, cv.html, blog.html)

2. **Asset Paths**: Use relative paths (e.g., `./assets/css/styles.css`) consistently across all HTML files

3. **External Links**: All certification badges and project links point to external URLs (Credly, GitHub repos)

4. **Styling Approach**: Use existing CSS variables from `styles.css` rather than inline styles where possible. When inline styles are necessary (e.g., section-specific layouts), use CSS custom properties for colors

5. **Mobile Responsiveness**: Test changes on mobile viewports - the burger menu and responsive layouts are critical

6. **Blog Posts**: New blog posts should be added to `blog/` directory and linked from `blog.html` following the existing article structure

7. **Git Remote**: The repository is connected to `https://github.com/CelalKincross/CelalKincross.github.io` - changes pushed to main deploy automatically

## Contact Form Integration

The contact form submits to Formspree endpoint: `https://formspree.io/f/xlekbppl`
Do not modify the form action URL without verifying a new Formspree configuration.
