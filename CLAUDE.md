# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website for the 2025 APSA (American Physician Scientists Association) South Regional Conference hosted by Baylor College of Medicine. The site is built using vanilla HTML, CSS, and JavaScript without any build tools or frameworks.

## Architecture

The project follows a component-based CSS and JavaScript structure:

- **index.html**: Main conference website with all sections
- **slideshow.html**: Standalone slideshow demo page
- **css/**: Modular CSS files, each prefixed with component name and version number
  - `global0.css`: Global styles and resets
  - `header0.css`: Navigation bar and header styles
  - `slideshow1.css`: Image slideshow component
  - `section-*.css`: Individual page section styles
  - `footer0.css`: Footer styles
- **js/**: JavaScript modules for interactive components
  - `slideshow0.js`: Slideshow functionality with auto-advance
  - `navbar0.js`: Mobile navigation toggle
  - `organizers0.js`: Organizers section functionality
  - `footer0.js`: Footer functionality
- **img/**: Static assets including logos, speaker photos, and slideshow images

## Development Workflow

### Testing Changes
- Open `index.html` directly in browser to test locally
- Use `slideshow.html` to test slideshow component independently
- Check responsive design at different screen sizes (mobile breakpoint: 1024px)

### File Naming Convention
- CSS and JS files use version numbers (e.g., `header0.css`, `slideshow1.css`)
- When making significant changes, increment version numbers
- Update corresponding references in HTML files

### Key Components

**Slideshow Component**:
- Auto-advances every 5 seconds
- Supports manual navigation with prev/next buttons and dots
- Handles responsive images for conference venues

**Navigation**:
- Responsive hamburger menu for mobile
- Smooth scrolling to page sections
- Social media integration in mobile menu

**Conference Sections**:
- Purpose, Schedule, Speakers, Travel Info, Organizers
- Registration status and conference details
- Speaker profiles with images and bios

## Deployment

The site is deployed via GitHub Pages at: https://code.physicianscientists.org/south-regional-conference/

## Content Updates

When updating conference information:
- Registration dates and status: `index.html` lines 130-142
- Schedule information: Schedule section in `index.html`
- Speaker information: Speakers section with corresponding images in `img/`
- Travel information: Travel section for venue details

The site structure allows for easy content updates without requiring build processes or dependency management.

## Jekyll Refactoring (jekyll branch)

This project has been refactored to use Jekyll for better content management across multiple conference events.

### Jekyll Structure
- **_data/**: Configuration and content files
  - `conference.yml`: Basic event details, dates, registration info
  - `sections.yml`: Purpose section content in markdown
  - `schedule.yml`: Event schedule with times and speakers
  - `speakers.yml`: Speaker bios and information
  - `travel.yml`: Travel and venue information
- **_layouts/**: HTML templates with Liquid templating
- **assets/**: CSS, JS, and image files (preserves existing structure)

### Content Management
- All text content lives in YAML and markdown files in `_data/`
- Event details easily updated by editing YAML values
- Speaker bios support full markdown formatting
- Slideshow images configured in `conference.yml`

### Development Commands
```bash
bundle install          # Install dependencies
bundle exec jekyll build # Build static site
bundle exec jekyll serve # Start development server at localhost:4000
```

### Creating New Events
1. Fork/copy the Jekyll version
2. Update `_data/conference.yml` with new event details
3. Replace content in `_data/sections.yml` and other data files
4. Update slideshow images in `assets/img/` and reference in `conference.yml`
5. Build and deploy

This Jekyll setup maintains the exact same visual design while separating content from presentation, making it ideal for managing multiple conference sites.