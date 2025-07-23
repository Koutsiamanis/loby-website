# Loby Cloud Hosting Website
[loby.com](https://spiffy-flan-17e179.netlify.app/index.html)
A responsive marketing website for Loby cloud hosting platform, built with vanilla HTML, CSS, and modern web technologies.

## Tech Stack & Implementation

### HTML5 Structure
The site uses semantic HTML5 with three main pages:
- `index.html` - Homepage with hero section and service overview
- `features.html` - Detailed platform capabilities 
- `docs.html` - Documentation and getting started guides

Each page follows a consistent structure with navbar, main content sections, and footer.

### CSS Architecture

**Two-file CSS approach:**
- `style.css` - Component-specific styles and layouts
- `utilities.css` - Reusable utility classes and helpers

**CSS Grid & Flexbox:**
```css
.grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
}

.flex {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

The layout system uses CSS Grid for main sections and Flexbox for component alignment. Responsive breakpoints handle tablet (768px) and mobile (500px) layouts.

**CSS Custom Properties:**
```css
:root {
    --primary-color: #37475A;
    --secondary-color: #1c3fa8;
    --dark-color: #131A22;
}
```

Color theming is handled through CSS variables, making it easy to maintain consistency across components.

**Animation System:**
Custom keyframe animations for page elements:
- `slideInFromLeft` - Hero text animation
- `slideInFromRight` - Form animation  
- `slideInFromBottom` - Stats section
- Hover transforms on cards and buttons

### Typography & Icons

**Google Fonts Integration:**
```css
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@1,300&display=swap');
```
Uses Lato font family for clean, modern typography.

**Font Awesome Icons:**
Loaded via CDN for consistent iconography across statistics, features, and social links.

### Responsive Design Strategy

**Mobile-First Approach:**
Base styles target mobile, with `min-width` media queries for larger screens:

```css
@media(max-width: 768px) {
    .grid,
    .showcase .grid,
    .stats .grid {
        grid-template-columns: 1fr;
    }
}
```

**Breakpoint System:**
- Mobile: < 500px (stacked navbar, simplified layout)
- Tablet: 501px - 768px (single column grids)
- Desktop: > 768px (full multi-column layouts)

### Component Implementation

**Navbar:**
Fixed height navbar with flexbox navigation. Mobile version stacks vertically with background overlay.

**Hero Section (Showcase):**
Uses CSS Grid with 55%/auto split. Includes CSS transform skew effect for visual interest:
```css
.showcase::before {
    transform: skewY(-3deg);
}
```

**Card Components:**
Reusable card system with shadow effects and hover animations:
```css
.card {
    box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
    border-radius: 10px;
}

.languages .card:hover {
    transform: translateY(-15px);
}
```

**Form Handling:**
Contact form includes Netlify integration with honeypot spam protection:
```html
<form name="contact" method="POST" netlify-honeypot="bot-field" data-netlify="true">
```

### Performance Considerations

- Minimal external dependencies (only Google Fonts and Font Awesome)
- CSS animations use `transform` instead of layout properties for better performance
- Images are set to `width: 100%` for responsive scaling
- Utility classes reduce CSS duplication

### Browser Compatibility

The CSS uses modern features but maintains broad compatibility:
- CSS Grid with fallbacks
- Flexbox for alignment
- CSS custom properties
- Transform animations

No JavaScript dependencies - pure CSS/HTML implementation.

## File Structure

```
├── css/
│   ├── style.css          # Main component styles, animations, responsive design
│   └── utilities.css      # Layout helpers, color classes, spacing utilities
├── index.html            # Homepage - hero, stats, language support
├── features.html         # Platform features with icon grid
├── docs.html            # Documentation with sidebar navigation
└── images/              # Asset folder (icons, illustrations)
```

## Development Setup

1. Clone and navigate to the project
2. Open `index.html` in a browser or run a local server
3. For live development, use VS Code with Live Server extension

The site is static HTML/CSS, so no build process or dependencies are required.

## Customization

**Colors:** Update CSS custom properties in `:root`  
**Layout:** Modify grid templates in respective component sections  
**Typography:** Change Google Fonts import and font-family declarations  
**Animations:** Adjust keyframe values or transform properties

The utility class system makes it easy to adjust spacing, colors, and typography without writing new CSS.
