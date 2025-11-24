# Leviathan AI Framework Structure
## Baseline Framework Documentation for Web Builds

**Repository:** leviath-ai.github.io
**Framework Type:** Pure Static HTML/CSS/JavaScript
**Deployment:** GitHub Pages
**Build System:** None (Zero-build architecture)

---

## Table of Contents

1. [Overview](#overview)
2. [Technology Stack](#technology-stack)
3. [Directory Structure](#directory-structure)
4. [Design System](#design-system)
5. [Component Architecture](#component-architecture)
6. [JavaScript Patterns](#javascript-patterns)
7. [Page Templates](#page-templates)
8. [Asset Management](#asset-management)
9. [Development Workflow](#development-workflow)
10. [Deployment Process](#deployment-process)
11. [Replication Guide](#replication-guide)
12. [Relationship to Φ-Mamba Research](#relationship-to-φ-mamba-research)

---

## Overview

The Leviathan AI framework is a **zero-build, framework-free** static website architecture optimized for:
- **Performance:** No build step, instant deployment
- **Simplicity:** Pure HTML/CSS/JavaScript with no dependencies
- **Interactivity:** Advanced Canvas API visualizations
- **Maintainability:** Self-contained pages with shared design patterns
- **Scalability:** Easy to replicate and extend

### Key Statistics
- **Total Size:** ~210KB
- **Pages:** 7 HTML files
- **External Dependencies:** 0
- **Build Time:** 0 seconds
- **Framework Weight:** 0KB

---

## Technology Stack

### Core Technologies
```yaml
HTML: HTML5 (semantic markup)
CSS: CSS3 (Grid, Flexbox, Custom Properties, Animations)
JavaScript: ES6+ (Classes, Arrow Functions, Promises)
Graphics: Canvas API (2D Context)
Deployment: GitHub Pages
Version Control: Git
```

### What We DON'T Use
- ❌ No React/Vue/Angular
- ❌ No webpack/Vite/Rollup
- ❌ No npm/yarn dependencies
- ❌ No CSS preprocessors (Sass/Less)
- ❌ No TypeScript
- ❌ No external JavaScript libraries
- ❌ No CSS frameworks (Bootstrap/Tailwind)

### Why This Approach?
1. **Zero latency** - No build step means instant updates
2. **No dependency hell** - Nothing to update or break
3. **Maximum control** - Complete understanding of every line
4. **Future-proof** - Web standards evolve slowly and predictably
5. **Performance** - No framework overhead, pure native speed

---

## Directory Structure

```
leviath-ai.github.io/
│
├── .git/                          # Git repository
├── .gitignore                     # Ignore patterns
│
├── README.md                      # Project overview
├── QFNN_Architecture.md          # Technical documentation
├── LEVIATHAN_FRAMEWORK_STRUCTURE.md  # This file
│
├── images/                        # Asset directory
│   ├── phase-distance-attention.png
│   ├── qfnn-architecture.png
│   ├── quantum-computing-alignment.png
│   └── reality-engine-concept.png
│
├── index.html                     # Homepage (37KB)
├── leviathan-contact.html         # Contact component (3KB)
├── leviathan-research.html        # Research page (16KB)
├── leviathan-technology.html      # Technology page (33KB)
├── physicsVisualizer.html         # Interactive visualizer (56KB)
├── quantum-computing-implementation.html  # Quantum details (25KB)
└── reality-engine-pathway.html    # Reality engine docs (21KB)
```

### File Organization Principles

1. **Root-level pages** - All HTML files in root for simple URLs
2. **Asset subdirectories** - Images, fonts, etc. in `/images/`, `/assets/`
3. **No deep nesting** - Flat structure for easy navigation
4. **Self-contained files** - Each HTML includes its own CSS/JS

---

## Design System

### Color Palette

```css
/* CSS Custom Properties (defined in :root) */

/* Backgrounds */
--bg-primary: #0a192f;        /* Deep navy - main background */
--bg-secondary: #112240;      /* Navy blue - cards and sections */
--bg-tertiary: #1d2d50;       /* Lighter navy - hover states */

/* Accents */
--accent-primary: #64ffda;    /* Cyan/turquoise - primary CTAs */
--accent-gold: #ffd700;       /* Gold - highlights and icons */
--accent-purple: #c792ea;     /* Purple - secondary accents */

/* Text */
--text-primary: #e6f1ff;      /* Near white - headings */
--text-secondary: #8892b0;    /* Muted blue-gray - body text */
--text-accent: #ccd6f6;       /* Light blue - emphasized text */

/* Animation */
--transition: all 0.25s cubic-bezier(0.645, 0.045, 0.355, 1);
```

### Typography

```css
/* Font Stack */
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
             'Helvetica Neue', Arial, sans-serif;

/* Hierarchy */
h1: 3.5rem (56px)   /* Hero headings */
h2: 2.5rem (40px)   /* Section headings */
h3: 2rem (32px)     /* Subsection headings */
p:  1.1rem (17.6px) /* Body text */

/* Responsive scaling */
@media (max-width: 768px) {
  h1: 2.5rem;
  h2: 2rem;
  h3: 1.5rem;
}
```

### Layout System

```css
/* Container */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Section Spacing */
.section {
  padding: 100px 0;
}

/* Hero Sections */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Grid System */
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}

/* Flexbox Utilities */
.flex-center {
  display: flex;
  align-items: center;
  justify-content: center;
}
```

### Component Library

#### Buttons
```css
.button {
  padding: 15px 30px;
  background: transparent;
  border: 2px solid var(--accent-primary);
  color: var(--accent-primary);
  font-size: 1rem;
  cursor: pointer;
  transition: var(--transition);
  border-radius: 5px;
}

.button:hover {
  background: rgba(100, 255, 218, 0.1);
  transform: translateY(-2px);
}

.button-primary {
  background: var(--accent-primary);
  color: var(--bg-primary);
}
```

#### Cards
```css
.card {
  background: var(--bg-secondary);
  padding: 30px;
  border-radius: 10px;
  transition: var(--transition);
  border: 1px solid rgba(100, 255, 218, 0.1);
}

.card:hover {
  transform: translateY(-5px);
  border-color: var(--accent-primary);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}
```

#### Navigation
```css
nav {
  position: fixed;
  top: 0;
  width: 100%;
  padding: 20px 0;
  backdrop-filter: blur(10px);
  background: rgba(10, 25, 47, 0.85);
  z-index: 1000;
  transition: var(--transition);
}

nav.scrolled {
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  background: rgba(10, 25, 47, 0.95);
}
```

---

## Component Architecture

### Page Structure Template

Every page follows this structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title | Leviathan AI</title>

    <style>
        /* CSS Custom Properties */
        :root { /* color variables */ }

        /* Reset & Base Styles */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { /* base styles */ }

        /* Layout Components */
        .container { /* container styles */ }
        .section { /* section styles */ }

        /* Page-Specific Styles */
        /* ... */
    </style>
</head>
<body>
    <!-- Navigation Header -->
    <nav>
        <div class="container">
            <!-- Logo & Links -->
        </div>
    </nav>

    <!-- Main Content -->
    <main>
        <section class="hero">
            <!-- Hero content -->
        </section>

        <section class="section">
            <!-- Section content -->
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="container">
            <!-- Footer content -->
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // Page-specific JavaScript
    </script>
</body>
</html>
```

### Navigation Component

**Consistent across all pages:**

```html
<nav id="navbar">
    <div class="container">
        <div class="nav-content">
            <a href="index.html" class="logo">Leviathan AI</a>
            <div class="nav-links">
                <a href="index.html#about">About</a>
                <a href="leviathan-technology.html">Technology</a>
                <a href="leviathan-research.html">Research</a>
                <a href="physicsVisualizer.html">Visualizer</a>
                <a href="index.html#contact">Contact</a>
            </div>
        </div>
    </div>
</nav>
```

### Footer Component

```html
<footer>
    <div class="container">
        <div class="footer-content">
            <div class="footer-section">
                <h3>Leviathan AI</h3>
                <p>Advanced AI Research & Development</p>
            </div>
            <div class="footer-section">
                <h4>Quick Links</h4>
                <a href="index.html">Home</a>
                <a href="leviathan-technology.html">Technology</a>
                <a href="leviathan-research.html">Research</a>
            </div>
            <div class="footer-section">
                <h4>Contact</h4>
                <p>contact@leviathan-ai.net</p>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2024 Leviathan AI. All rights reserved.</p>
        </div>
    </div>
</footer>
```

---

## JavaScript Patterns

### Canvas Animation System

**Core pattern used in index.html:**

```javascript
// 1. Define Particle Class
class RealityParticle {
    constructor(x, y) {
        this.x = x;
        this.y = y;
        this.amplitude = Math.random() * 2;
        this.phase = Math.random() * Math.PI * 2;
        this.speed = Math.random() * 0.02;
    }

    update() {
        // Physics-based movement
        this.phase += this.speed;
        this.x += Math.cos(this.phase) * this.amplitude;
        this.y += Math.sin(this.phase) * this.amplitude;

        // Boundary wrapping
        if (this.x < 0) this.x = canvas.width;
        if (this.x > canvas.width) this.x = 0;
        if (this.y < 0) this.y = canvas.height;
        if (this.y > canvas.height) this.y = 0;
    }

    draw(ctx) {
        ctx.beginPath();
        ctx.arc(this.x, this.y, 2, 0, Math.PI * 2);
        ctx.fillStyle = 'rgba(100, 255, 218, 0.8)';
        ctx.fill();
    }
}

// 2. Initialize Canvas & Particles
const canvas = document.getElementById('canvas');
const ctx = canvas.getContext('2d');
const particles = [];

function resizeCanvas() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
}

function initParticles() {
    for (let i = 0; i < 70; i++) {
        particles.push(new RealityParticle(
            Math.random() * canvas.width,
            Math.random() * canvas.height
        ));
    }
}

// 3. Animation Loop
function animate() {
    ctx.fillStyle = 'rgba(10, 25, 47, 0.1)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    particles.forEach(particle => {
        particle.update();
        particle.draw(ctx);
    });

    requestAnimationFrame(animate);
}

// 4. Initialize
resizeCanvas();
initParticles();
animate();
window.addEventListener('resize', resizeCanvas);
```

### Scroll Effects

```javascript
// Navbar scroll effect
const navbar = document.getElementById('navbar');

window.addEventListener('scroll', () => {
    if (window.scrollY > 50) {
        navbar.classList.add('scrolled');
    } else {
        navbar.classList.remove('scrolled');
    }
});

// Fade-in on scroll
const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -100px 0px'
};

const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.classList.add('fade-in');
        }
    });
}, observerOptions);

document.querySelectorAll('.section').forEach(section => {
    observer.observe(section);
});
```

### Responsive Canvas Pattern

```javascript
// Used in physicsVisualizer.html
function resizeCanvases() {
    const container = document.querySelector('.canvas-container');
    const containerWidth = container.offsetWidth;

    // Resize all canvases
    phaseCanvas.width = containerWidth;
    phaseCanvas.height = containerWidth * 0.75;
    energyCanvas.width = containerWidth;
    energyCanvas.height = containerWidth * 0.4;

    // Redraw after resize
    updateVisualization();
}

window.addEventListener('resize', resizeCanvases);
```

---

## Page Templates

### 1. Landing Page Template (index.html)

**Purpose:** Homepage with hero section, about, services, contact

**Key Features:**
- Full-viewport hero with canvas animation
- Sticky navigation header
- Grid-based service cards
- Contact form section
- Fade-in scroll animations

**Structure:**
```
Hero Section (100vh)
  ├── Canvas Background Animation
  └── Centered Content (Title, Subtitle, CTA)

About Section
  ├── Two-column layout (image + text)
  └── Founder background

What We Build Section
  └── Grid of 3 cards

Services Section
  └── Grid of 4 service cards

Contact Section
  └── Contact form + info

Footer
```

### 2. Technology Page Template (leviathan-technology.html)

**Purpose:** Deep-dive into QFNN technology

**Key Features:**
- Technical content sections
- Code examples and diagrams
- Performance comparison tables
- Architecture visualizations

### 3. Interactive Visualizer Template (physicsVisualizer.html)

**Purpose:** Real-time physics/quantum visualization

**Key Features:**
- Multi-canvas layout
- Control panel with play/pause/reset
- Real-time data table
- Performance metrics
- Complex animation loop

**Structure:**
```
Header
  └── Title + Controls (buttons)

Canvas Container (2-column grid)
  ├── Phase Space Canvas
  └── Energy Visualization Canvas

Analysis Section
  ├── Metrics Display
  └── Token State Table

Footer
```

### 4. Documentation Page Template (research/quantum-computing)

**Purpose:** Technical documentation and research papers

**Key Features:**
- Article-style layout
- Code blocks and equations
- Section navigation
- References and citations

---

## Asset Management

### Image Organization

```
/images/
├── phase-distance-attention.png
├── qfnn-architecture.png
├── quantum-computing-alignment.png
└── reality-engine-concept.png
```

**Best Practices:**
1. Use descriptive kebab-case filenames
2. Keep images in `/images/` directory
3. Optimize images before adding (WebP preferred)
4. Use relative paths: `images/filename.png`
5. Provide alt text for accessibility

### Icon System

**Using Unicode & CSS:**
```css
.icon::before {
    content: '→';
    margin-right: 10px;
    color: var(--accent-primary);
}
```

**Recommended:** Add Font Awesome or custom SVG sprite for richer icons

---

## Development Workflow

### Setting Up a New Project

```bash
# 1. Create new repository
mkdir project-name
cd project-name
git init

# 2. Copy baseline structure
cp ../leviath-ai.github.io/index.html ./index.html
mkdir images

# 3. Update colors and branding
# Edit CSS custom properties in <style> tag

# 4. Add content
# Modify HTML sections

# 5. Test locally
# Open in browser or use Live Server

# 6. Deploy to GitHub Pages
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <repo-url>
git push -u origin main

# Enable GitHub Pages in repo settings
```

### Adding a New Page

```bash
# 1. Copy template
cp index.html new-page.html

# 2. Update <title> tag
# 3. Update navigation links
# 4. Replace content sections
# 5. Update page-specific JavaScript
# 6. Test and commit
```

### Creating New Components

**Pattern for reusable cards:**
```css
/* Define in :root styles */
.custom-card {
    background: var(--bg-secondary);
    padding: 30px;
    border-radius: 10px;
    border: 1px solid rgba(100, 255, 218, 0.1);
    transition: var(--transition);
}

.custom-card:hover {
    border-color: var(--accent-primary);
    transform: translateY(-5px);
}
```

```html
<!-- Use in HTML -->
<div class="custom-card">
    <h3>Card Title</h3>
    <p>Card content</p>
</div>
```

---

## Deployment Process

### GitHub Pages Setup

1. **Create GitHub Repository**
   ```bash
   git remote add origin https://github.com/username/repo-name.git
   ```

2. **Enable GitHub Pages**
   - Go to repository Settings
   - Navigate to Pages section
   - Source: Deploy from branch `main` or `gh-pages`
   - Folder: `/ (root)`
   - Save

3. **Custom Domain (Optional)**
   - Add `CNAME` file with domain name
   - Configure DNS records at domain provider

4. **Deploy**
   ```bash
   git add .
   git commit -m "Deploy website"
   git push origin main
   ```

5. **Access Site**
   - Default: `https://username.github.io/repo-name`
   - Custom: `https://yourdomain.com`

### Continuous Deployment

**Every push to main automatically deploys:**
```bash
# Make changes
git add .
git commit -m "Update content"
git push origin main

# Wait 1-2 minutes for GitHub Pages to rebuild
# Changes are live!
```

---

## Replication Guide

### Quick Start: Clone & Customize

```bash
# 1. Clone the baseline framework
git clone https://github.com/qLeviathan/leviath-ai.github.io.git my-new-project
cd my-new-project

# 2. Remove git history (start fresh)
rm -rf .git
git init

# 3. Customize colors (edit index.html)
:root {
    --bg-primary: #YOUR_COLOR;
    --accent-primary: #YOUR_ACCENT;
}

# 4. Update content
# Replace text in sections
# Update navigation links
# Change logo/branding

# 5. Add your images
cp /path/to/images/* ./images/

# 6. Create new repository
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main

# 7. Enable GitHub Pages
# Done! Your site is live.
```

### Customization Checklist

- [ ] Update `:root` CSS color variables
- [ ] Replace logo text in `<nav>`
- [ ] Update `<title>` tags on all pages
- [ ] Modify hero section content
- [ ] Replace about section text
- [ ] Update service/feature cards
- [ ] Change contact information
- [ ] Update footer content
- [ ] Replace placeholder images
- [ ] Test all navigation links
- [ ] Test responsive design on mobile
- [ ] Verify canvas animations work
- [ ] Update meta tags (description, keywords)
- [ ] Add favicon
- [ ] Test across browsers

### Adding Advanced Features

**1. Add Form Handling:**
```javascript
// Use Formspree, Netlify Forms, or custom backend
document.getElementById('contact-form').addEventListener('submit', async (e) => {
    e.preventDefault();
    const formData = new FormData(e.target);

    // Send to API
    await fetch('YOUR_FORM_ENDPOINT', {
        method: 'POST',
        body: formData
    });
});
```

**2. Add Analytics:**
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
<script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'GA_ID');
</script>
```

**3. Add SEO Meta Tags:**
```html
<meta name="description" content="Your site description">
<meta name="keywords" content="keyword1, keyword2, keyword3">
<meta property="og:title" content="Page Title">
<meta property="og:description" content="Description">
<meta property="og:image" content="image-url">
<meta property="og:url" content="page-url">
<meta name="twitter:card" content="summary_large_image">
```

---

## Advanced Patterns

### Fibonacci Ratio Motion (Signature Pattern)

```javascript
// Used throughout for natural motion
const PHI = 1.618033988749; // Golden ratio

class FibonacciParticle {
    constructor(x, y) {
        this.x = x;
        this.y = y;
        this.baseSpeed = 1;
        this.fibonacciMultiplier = PHI;
    }

    update() {
        // Motion follows golden ratio
        this.x += Math.cos(this.angle) * this.baseSpeed * this.fibonacciMultiplier;
        this.y += Math.sin(this.angle) * this.baseSpeed * this.fibonacciMultiplier;
    }
}
```

### Quantum Tunneling Effect

```javascript
// Random quantum jumps (used in particle systems)
function updateParticle(particle) {
    // Normal physics
    particle.x += particle.vx;
    particle.y += particle.vy;

    // 1% chance of quantum tunneling
    if (Math.random() < 0.01) {
        particle.x = Math.random() * canvas.width;
        particle.y = Math.random() * canvas.height;
    }
}
```

### Triangular Topology Rendering

```javascript
// Phase space visualization (physicsVisualizer.html)
function drawTriangularTopology() {
    const centerX = canvas.width / 2;
    const centerY = canvas.height / 2;
    const radius = Math.min(canvas.width, canvas.height) * 0.35;

    // Draw three points forming triangle
    const points = [];
    for (let i = 0; i < 3; i++) {
        const angle = (i * 2 * Math.PI / 3) - Math.PI / 2;
        points.push({
            x: centerX + Math.cos(angle) * radius,
            y: centerY + Math.sin(angle) * radius
        });
    }

    // Connect points
    ctx.beginPath();
    ctx.moveTo(points[0].x, points[0].y);
    for (let i = 1; i < points.length; i++) {
        ctx.lineTo(points[i].x, points[i].y);
    }
    ctx.closePath();
    ctx.strokeStyle = 'rgba(100, 255, 218, 0.3)';
    ctx.stroke();
}
```

---

## Configuration Files

### .gitignore Template

```gitignore
# Python
__pycache__/
*.py[cod]
*.so
*.egg
*.egg-info/

# Node
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Environment
.env
.env.local
.env.*.local

# Editor
.vscode/
.idea/
*.swp
*.swo
*~

# OS
.DS_Store
Thumbs.db

# Build outputs (if you add a build system later)
dist/
build/
```

### README.md Template

```markdown
# Project Name

Brief description of your project.

## Features

- Feature 1
- Feature 2
- Feature 3

## Technologies

- HTML5
- CSS3
- JavaScript (ES6+)
- Canvas API

## Setup

1. Clone the repository
2. Open `index.html` in your browser
3. That's it! No build step required.

## Deployment

Deployed on GitHub Pages: [your-url]

## Contact

Email: your-email@example.com
```

---

## Performance Optimization

### Best Practices

1. **Inline Critical CSS**
   - All above-the-fold CSS in `<head>`
   - Reduces render-blocking requests

2. **Optimize Canvas Rendering**
   ```javascript
   // Use requestAnimationFrame
   function animate() {
       // Clear only necessary areas
       ctx.clearRect(dirty.x, dirty.y, dirty.width, dirty.height);

       // Batch draw calls
       ctx.beginPath();
       particles.forEach(p => {
           ctx.moveTo(p.x, p.y);
           ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
       });
       ctx.fill();

       requestAnimationFrame(animate);
   }
   ```

3. **Debounce Resize Events**
   ```javascript
   let resizeTimeout;
   window.addEventListener('resize', () => {
       clearTimeout(resizeTimeout);
       resizeTimeout = setTimeout(() => {
           resizeCanvases();
       }, 250);
   });
   ```

4. **Lazy Load Images**
   ```html
   <img src="placeholder.jpg" data-src="actual-image.jpg" loading="lazy">
   ```

5. **Minimize Reflows**
   - Batch DOM reads and writes
   - Use CSS transforms instead of top/left
   - Cache DOM queries

---

## Browser Compatibility

### Tested & Supported

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

### Polyfills (if needed)

```javascript
// IntersectionObserver polyfill for older browsers
if (!('IntersectionObserver' in window)) {
    // Fallback to immediate visibility
    document.querySelectorAll('.section').forEach(section => {
        section.classList.add('fade-in');
    });
}
```

---

## Maintenance & Updates

### Regular Tasks

1. **Content Updates**
   - Edit HTML directly
   - Commit and push
   - Live in 1-2 minutes

2. **Adding New Pages**
   - Copy existing page template
   - Update navigation on all pages
   - Test links

3. **Image Updates**
   - Replace files in `/images/`
   - Update `src` attributes if filename changed
   - Optimize images before uploading

4. **Style Tweaks**
   - Modify CSS variables in `:root`
   - Test responsiveness
   - Commit changes

---

## Troubleshooting

### Common Issues

**Issue:** Canvas not resizing properly
```javascript
// Solution: Ensure resize function is called
function resizeCanvas() {
    canvas.width = canvas.offsetWidth;
    canvas.height = canvas.offsetHeight;
    // Redraw content
    draw();
}
window.addEventListener('resize', resizeCanvas);
resizeCanvas(); // Initial call
```

**Issue:** Navigation links not working
```html
<!-- Ensure href attributes are correct -->
<a href="index.html">Home</a>        <!-- ✓ Correct -->
<a href="/index.html">Home</a>       <!-- ✗ Wrong for GH Pages subdirectory -->
```

**Issue:** GitHub Pages not updating
```bash
# Clear browser cache (Ctrl+Shift+R)
# Check GitHub Actions tab for build status
# Wait 2-3 minutes after push
```

---

## Future Extensions

### Recommended Additions

1. **Blog System**
   - Create `/blog/` directory
   - Add `blog-post.html` template
   - Generate index page with post list

2. **Dark/Light Mode Toggle**
   ```javascript
   const toggle = document.getElementById('theme-toggle');
   toggle.addEventListener('click', () => {
       document.body.classList.toggle('light-mode');
       localStorage.setItem('theme',
           document.body.classList.contains('light-mode') ? 'light' : 'dark'
       );
   });
   ```

3. **Search Functionality**
   - Add search input
   - Implement client-side search with Fuse.js
   - Highlight results

4. **Internationalization**
   - Create language switcher
   - Duplicate pages for each language
   - Store preference in localStorage

---

## Relationship to Φ-Mamba Research

### Understanding the Dual Framework Approach

This website documents the **front-end presentation layer** of Leviathan AI. However, the **actual research implementation** exists in a parallel repository: `phase_locked`.

#### **Website Framework: QFNN (Quantum Flux Neural Networks)**
- **Status:** Conceptual/aspirational architecture
- **Foundation:** Quantum field theory principles
- **Representation:** Tokens as quantum particles with phase/amplitude in 2D space
- **Approach:** Physics-inspired neural architecture
- **Implementation:** Demonstrated through interactive visualizers on this site

#### **Research Framework: Φ-Mamba (Phi-Mamba)**
- **Status:** Production-ready with full validation (4000+ lines)
- **Foundation:** Game theory + golden ratio mathematics
- **Representation:** Language as dynamic strategic game with φ-primitives
- **Approach:** Game-theoretic language modeling with retrocausality
- **Repository:** https://github.com/qLeviathan/phase_locked

### Philosophical Alignment

Both frameworks share the same core insight: **Intelligence emerges from fundamental mathematical structures, not arbitrary matrix operations.**

| Aspect | QFNN (Website) | Φ-Mamba (phase_locked) |
|--------|----------------|------------------------|
| **Mathematical Foundation** | Quantum mechanics | Game theory + golden ratio |
| **Core Primitive** | Phase & amplitude | φ = 1.618... (golden ratio) |
| **Computation** | Hamiltonian dynamics | Backward induction equilibrium |
| **Attention Mechanism** | Phase-distance interference | Nash equilibrium payoffs |
| **Energy** | Conservation via normalization | φ^(-t) exponential decay |
| **Learning** | Hebbian plasticity | Utility maximization |
| **Exact Math** | Quantum operators | Integer Fibonacci arithmetic |

### Key Innovations in Φ-Mamba

**1. Golden Ratio as Foundational Primitive**
```
Traditional: Start with 1, derive φ = (1 + √5)/2
Φ-Mamba: Start with φ, derive 1 = φ² - φ
```

**2. Language as Game**
```python
Game Γ = (N, S, A, u, T, β)
- N: Players (tokens as strategic agents)
- S: States (θ angle, energy φ^(-t), Fibonacci shells)
- A: Actions (token selection)
- u: Utility (phase coherence × energy)
- T: Termination (natural via energy decay)
- β: Discount (1/φ = 0.618... ensures time consistency)
```

**3. Retrocausality = Backward Induction**
Future endpoint Ω constrains all past decisions through the Bellman equation:
```
V*(s) = max{u(s,a) + β·E[V*(s')|s,a]}
```

**4. Causal Inference via Fibonacci**
Difference-in-differences using Zeckendorf decomposition as natural experiments.

**5. Integer-Only Computation**
All operations reduce to Fibonacci integer addition → exact arithmetic.

### AURELIA: Conscious Trading Agent

Φ-Mamba's practical application—a trading agent with five-layer consciousness:

1. **Perception:** Market data via Zeckendorf encoding
2. **Cognition:** φ/ψ lattice dynamics for decision-making
3. **Emotion:** 5 evolving states (confidence, fear, greed, patience, discipline)
4. **Memory:** Episodic, semantic, and procedural persistence
5. **Execution:** Kelly criterion with emotional multipliers

**Unique Feature:** Personality develops through market experience—path-dependent evolution creates a unique "trader consciousness."

### Technical Implementation

**Language Stack:**
- Python (60.2%): Core algorithms
- Rust (30.8%): Performance optimization
- Jupyter (6.0%): Analysis
- LaTeX (1.9%): Academic papers

**Validation Status:**
- ✅ All game theory tests passed
- ✅ δ = 0.000815 (DiD treatment effect)
- ✅ Natural convergence at t≈10
- ✅ β = 1/φ verified to machine precision

**Applications:**
- Language modeling with exact arithmetic
- Financial trading with game equilibrium guarantees
- Causal inference in sequential decision-making

### Potential Synthesis

QFNN and Φ-Mamba aren't competing—they're **dual perspectives**:

```
QFNN Phase-Distance Attention ↔ Φ-Mamba Nash Equilibrium
QFNN Energy Conservation      ↔ Φ-Mamba Game Constraints
QFNN Quantum Tunneling         ↔ Φ-Mamba Mixed Strategies
QFNN Hamiltonian               ↔ Φ-Mamba Value Function
```

Both achieve the same goal: **Post-AGI recursive operational intelligence through fundamental mathematics.**

### Resources

- **Φ-Mamba Implementation:** https://github.com/qLeviathan/phase_locked
- **Comprehensive Analysis:** See `COMPREHENSIVE_RESEARCH_ANALYSIS.md` in this repository
- **Academic Paper:** `arxiv_preprint.tex` in phase_locked repository
- **Quick Start:** `QUICKSTART.md` in phase_locked repository

### For Developers

When building on this framework:
1. **Website/Marketing:** Use patterns from this repository
2. **Research/Production:** Use Φ-Mamba from phase_locked
3. **Integration:** Both share design philosophy—choose based on needs

**This website showcases the vision. phase_locked delivers the implementation.**

---

## Credits & License

**Framework:** Leviathan AI
**Created by:** qLeviathan
**Repositories:**
- Website: https://github.com/qLeviathan/leviath-ai.github.io
- Research: https://github.com/qLeviathan/phase_locked
**License:** MIT

---

## Conclusion

This framework represents the **minimal viable architecture** for modern web development:

✅ **Zero dependencies**
✅ **Instant deployment**
✅ **Complete control**
✅ **Maximum performance**
✅ **Future-proof**
✅ **Easy to maintain**

**Use this as your baseline for all web builds going forward.**

For questions or contributions, contact: contact@leviathan-ai.net

---

**Last Updated:** 2024
**Framework Version:** 1.0
**Documentation Status:** Complete
