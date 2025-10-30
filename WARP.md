# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

A cinematic one-page portfolio website for video editor Vivek. Built with vanilla HTML/CSS/JavaScript (no build system), featuring a modern black and neon blue (#00d4ff) design with smooth animations and interactive elements.

## Development Commands

### Running the Project

Since this is a static HTML site with no build process, use a local development server:

```bash
# Python 3 (recommended)
python -m http.server 8000

# Node.js
npx http-server

# PHP
php -S localhost:8000
```

Then navigate to `http://localhost:8000`

### Testing

No test framework is configured. Test manually by opening index.html in browsers.

## Architecture

### File Structure
- **index.html** - Single-page application structure with all sections (hero, about, services, portfolio, testimonials, contact)
- **styles.css** - All styling including CSS variables, animations, responsive breakpoints
- **script.js** - Vanilla JavaScript for interactions, no dependencies
- **assets/** - Media files (hero video, portfolio images)

### Key Technical Patterns

**CSS Architecture:**
- CSS variables in `:root` define the design system (colors, transitions)
- Uses CSS Grid and Flexbox for layouts
- Responsive breakpoints: 480px (mobile), 768px (tablet), 968px, 1200px+ (desktop)
- Animation keyframes for fade-in effects and micro-interactions

**JavaScript Architecture:**
- Event-driven with DOM manipulation
- Intersection Observer API for scroll-triggered animations
- Smooth scrolling via `scrollIntoView` for navigation
- Portfolio filtering system using `data-category` attributes
- Parallax effects on hero video background
- Active navigation link highlighting based on scroll position

**Animation System:**
- `.fade-in`, `.fade-in-delay`, `.fade-in-delay-2` classes with keyframe animations
- Intersection Observer adds `.animate-in` class to trigger scroll animations
- Staggered animations using `setTimeout` and CSS `animation-delay`
- Cursor glow effect creates dynamic DOM elements on mousemove

**Design System:**
```css
--neon-blue: #00d4ff (primary accent)
--dark-bg: #000000 (main background)
--dark-bg-alt: #0a0a0a (alternate sections)
--text-primary: #ffffff
--text-secondary: #b0b0b0
```

### Section Components

1. **Hero** - Full-screen video background with overlay gradient, title, tagline, CTA buttons
2. **Navigation** - Fixed navbar with smooth scroll links, appears after 1s delay
3. **About** - Two-column grid (text + tools showcase)
4. **Services** - 5 service cards in auto-fit grid (min 280px)
5. **Portfolio** - Filterable 9-item grid with overlay effects, categories: all/commercial/music/documentary/social
6. **Testimonials** - 3 client reviews in auto-fit grid
7. **Contact** - Two-column grid (form + social links), form shows alert on submit
8. **Footer** - Copyright notice

## Important Implementation Details

### Assets Management
- Hero video must be at `assets/hero-video.mp4` (recommended: 1920x1080, <10MB)
- Portfolio images at `assets/portfolio/project-{1-9}.jpg`
- Missing assets will cause broken images but won't break functionality

### Form Integration
The contact form (contactForm) currently uses `alert()` and `console.log()`. To integrate:
- Option 1: FormSubmit.co - update form action attribute
- Option 2: Netlify Forms - add `data-netlify="true"` attribute
- Option 3: Custom backend - modify submit handler in script.js lines 84-108

### Browser Compatibility
- Requires modern browser with ES6+ support (const/let, arrow functions)
- Uses Intersection Observer API (check for polyfill if supporting IE11)
- Video autoplay requires muted attribute (line 15 in index.html)

### Performance Considerations
- Lazy loading implemented for portfolio images via Intersection Observer
- Cursor glow effect creates/removes DOM elements frequently - may impact performance on lower-end devices
- No CSS/JS minification - consider for production deployment

## Customization Guide

### Changing Colors
Edit CSS variables in styles.css lines 8-16. The neon-blue color is used throughout for accents, glows, borders, and hover states.

### Adding/Removing Portfolio Items
1. Add/remove `.portfolio-item` divs in index.html (lines 122-202)
2. Set `data-category` attribute to: commercial, music, documentary, or social
3. Ensure corresponding images exist in assets/portfolio/

### Modifying Animations
- Animation timing: CSS variables (line 15) and keyframe durations (lines 154-178)
- Stagger delays: JavaScript lines 72, 143-149, 154, 188-193
- Intersection Observer threshold: script.js line 17

### Typography
Fonts loaded from Google Fonts (lines 8-10 in index.html):
- Playfair Display (700) - used for headings/titles
- Montserrat (300, 400, 600, 700) - body text

## Deployment

### Static Hosting Options
- **GitHub Pages**: Push to repo, enable Pages in settings
- **Netlify**: Drag-and-drop or connect GitHub repo
- **Vercel**: `npm i -g vercel && vercel`

### Pre-deployment Checklist
1. Replace placeholder social media links (Instagram, YouTube, LinkedIn)
2. Update personal information in About section
3. Add actual portfolio images and hero video
4. Test form submission integration
5. Validate all internal links work correctly

## Common Tasks

### Add a new service card
Copy a `.service-card` div (lines 81-85) and update icon, title, description

### Change navigation items
Edit `.nav-menu` list items (lines 36-42) and ensure corresponding section IDs exist

### Adjust responsive breakpoints
Modify media queries in styles.css (lines 667-738)

### Disable cursor glow effect
Comment out or remove lines 157-177 in script.js (can impact performance)
