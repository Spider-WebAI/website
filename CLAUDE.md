# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the **MWConsultants website** — a professional business consultancy website built with vanilla HTML, CSS, and JavaScript. The site showcases consulting services in AI & Automation, Financial Services & GST, IT Infrastructure Support, and Real Estate Consultancy.

**Technology Stack:**
- HTML5 (semantic markup)
- CSS3 (inline styles, responsive design with media queries)
- Vanilla JavaScript (no frameworks)
- Font Awesome 6.4.0 for icons
- Static site (no build process required)

## Directory Structure

```
website/
├── index.html              # Home page (hero section + services overview)
├── about.html              # About Us page (mission, vision, team, stats)
├── services.html           # Services detail page
├── contact.html            # Contact Us page (form + contact info)
├── ainautomation.html      # AI & Automation service detail page
├── Testindex.html          # Test file (likely for testing, not part of main site)
└── README.md               # Basic project description
```

## Key Architecture Decisions

### Styling Approach
- **Inline CSS**: All CSS is embedded within `<style>` tags in each HTML file
- **CSS Variables**: Uses CSS custom properties for consistent theming:
  - `--primary: #1e3a5f` (deep navy blue)
  - `--secondary: #4a6fa5` (medium blue)
  - `--accent: #e67e22` (warm orange)
  - `--light: #f5f7fa` (light background)
  - `--dark: #2c3e50` (dark text)
  - `--gray: #7f8c8d` (secondary text)
  - `--gradient: linear-gradient(...)` for hero sections

### Layout System
- **Container-based**: Max-width 1200px with 90% viewport width
- **CSS Grid & Flexbox**: Modern layout techniques throughout
- **Responsive breakpoints**:
  - `@media (max-width: 992px)` — tablets
  - `@media (max-width: 768px)` — mobile menu activation, layout adjustments
  - `@media (max-width: 576px)` — small phones, font size reductions

### Shared Components Across Pages
- **Header**: Fixed navigation with mobile hamburger menu (consistent across all pages)
- **Footer**: Contact info, quick links, newsletter signup, social links
- **Buttons**: `.btn` class with hover effects and animation
- **Section styling**: `.section-padding`, `.section-title`, `.container` utilities
- **Cards**: Service cards, team member cards, mission/vision cards with hover animations

### JavaScript Features
- **Mobile menu toggle**: Hamburger menu functionality for screens < 768px
- **Smooth scrolling**: Anchor link smooth scroll behavior
- **Form handling**: Contact form submission with alert and reset

## Common Development Tasks

### Adding a New Page
1. Create a new `.html` file
2. Copy the header/footer structure from an existing page (maintains consistency)
3. Update nav links to include your new page in all existing pages
4. Link the new page from appropriate navigation points

### Modifying Colors or Theme
- Update CSS variables in the `:root` section of any page's `<style>` tag
- Remember to update all HTML files for consistency since styles are inline
- Test responsive behavior at all breakpoints

### Adding New Service Cards or Content
- Service cards use `.service-card` class with `.services-grid` container
- Mission/vision cards use `.mission-card` class
- Team member cards use `.team-member` class
- Icon areas use `.service-icon` or `.mission-icon` classes with Font Awesome icons

### Mobile Responsiveness Testing
- Test at 992px (tablet), 768px (mobile menu), 576px (small phone)
- Mobile menu uses `nav.active` class toggle and `transform: translateY()`
- Ensure all grid layouts collapse to single column on smaller screens

## Important Notes

- **Styles Duplication**: Since CSS is inline in each HTML file, making global style changes requires updating multiple files. Consider consolidating styles to an external CSS file for easier maintenance in the future.
- **Navigation Consistency**: All nav links must be kept in sync across all HTML files. Check link paths carefully (use relative paths or full filenames).
- **Font Awesome CDN**: External dependency loaded via CDN. Ensure icons are properly referenced with correct FontAwesome classes (e.g., `fas fa-robot`).
- **Placeholder Content**: Some pages use placeholder gradient divs for images (e.g., "MWConsultants Team" sections). Replace these with actual image elements or proper image paths.
- **Form Submission**: Current form submission shows an alert. No backend integration exists yet; if adding email functionality, backend setup will be needed.

## URL Path Issues to Watch
- Contact page link in index.html line 602 references `contactUs.html` (inconsistent with `contact.html`)
- Review all internal links across pages to ensure consistent file naming
