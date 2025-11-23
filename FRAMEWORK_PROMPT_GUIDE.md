# Leviathan Framework Prompt Engineering Guide
## How to Recreate the Framework Files from Scratch

**Purpose:** This guide provides detailed prompts that can recreate each file in the Leviathan AI framework. Use these as templates for building new projects based on this baseline framework.

---

## Table of Contents

1. [Landing Page Prompt](#landing-page-prompt)
2. [Interactive Visualizer Prompt](#interactive-visualizer-prompt)
3. [Technology Documentation Prompt](#technology-documentation-prompt)
4. [Research Page Prompt](#research-page-prompt)
5. [Contact Component Prompt](#contact-component-prompt)
6. [General Prompt Patterns](#general-prompt-patterns)
7. [Customization Variables](#customization-variables)

---

## Landing Page Prompt

### File: `index.html`

**Prompt to Claude:**

```
Create a landing page for a tech company with the following specifications:

DESIGN SYSTEM:
- Color scheme:
  - Primary background: #0a192f (dark navy)
  - Secondary background: #112240 (navy blue)
  - Primary accent: #64ffda (cyan)
  - Gold accent: #ffd700
  - Purple accent: #c792ea
  - Text primary: #e6f1ff (near white)
  - Text secondary: #8892b0 (muted blue-gray)
- Font: "SF Mono", "Fira Code", monospace
- Transitions: cubic-bezier(0.645, 0.045, 0.355, 1)

LAYOUT STRUCTURE:
1. Fixed header with:
   - Logo on left (text: "LEVIATHAN AI")
   - Navigation on right: About, What We Build, Services, Contact
   - Backdrop blur effect
   - Box shadow on scroll

2. Hero section (100vh):
   - Canvas background with particle animation
   - Greeting text in accent color
   - Large gradient title
   - Subtitle
   - Description paragraph
   - Two CTA buttons (primary and outline)

3. About section:
   - Two-column grid layout (story + skills)
   - Personal story with highlighted text in accent colors
   - Skills organized by categories with tag badges

4. What We Build section:
   - Grid of project cards (auto-fit, min 350px)
   - Each card has: title, description, tech tags
   - Cards have gradient top border (cyan → gold → purple)
   - Hover effect: translate up 5px

5. Services section:
   - 4 service cards in auto-fit grid (min 300px)
   - Each card has: emoji icon, title, description
   - Gradient background on cards

6. Contact section:
   - Two-column grid (info + methods)
   - Contact methods in card format

7. Footer:
   - Copyright text
   - Inspirational quote in gold

JAVASCRIPT FEATURES:
1. RealityParticle class:
   - Properties: x, y, radius, phase, speed, amplitude, phaseSpeed
   - Use Fibonacci ratio (1.618033988749)
   - Update method with sine wave motion
   - Draw method with random color (cyan, gold, or purple)
   - Quantum tunneling: random Y jump at 0.1% chance
   - Wrap particles horizontally when off-screen

2. Canvas setup:
   - Create 70 particles
   - Animation loop with requestAnimationFrame
   - Clear canvas with transparent fill (alpha 0.1)
   - Draw connections between particles within Fibonacci threshold (150 * 1.618)

3. Scroll effects:
   - Fade-in animations on sections using IntersectionObserver
   - Header shadow and background change after 50px scroll
   - Smooth scroll for anchor links

RESPONSIVE:
- Breakpoint at 768px
- Stack grids to single column
- Reduce font sizes
- Stack navigation vertically

CONTENT:
[Provide actual content for: company name, tagline, about story, services, projects, contact info]

Use only HTML, CSS in <style> tag, and JavaScript in <script> tag. No external files.
```

---

## Interactive Visualizer Prompt

### File: `physicsVisualizer.html`

**Prompt to Claude:**

```
Create an interactive physics visualization tool with the following specifications:

DESIGN SYSTEM:
- Use the same color palette as the main site (dark navy theme)
- Additional colors:
  - Energy red: #ff6b6b
  - Phase blue: #4d96ff
  - Amplitude green: #6bff8f
  - Velocity purple: #d896ff

LAYOUT STRUCTURE:
1. Fixed header (same as main site)

2. Page header section:
   - Page subtitle in accent color
   - Large title
   - Description paragraph

3. Main physics container:
   - Input area: textarea for text input + "Analyze Physics" button
   - Layer selector: 5 buttons (Input Embedding, Layer 1-3, Output Projection)
   - Two visualization panels side by side (grid layout):
     a. Quantum Field Space canvas
     b. Energy Conservation Dynamics canvas
   - Each panel has header with controls (pause/resume, toggle view)

4. Physics metrics cards (4 cards in grid):
   - System Energy (red icon)
   - Phase Coherence (blue icon)
   - Amplitude Distribution (green icon)
   - Evolution Velocity (purple icon)
   - Each shows: icon, name, large value, description

5. Physics equations display:
   - 4 equations in table format
   - Each shows: name, formula description, status

6. Tokens table:
   - Columns: Token, Amplitude (r), Phase (θ), Energy (r²), Attention Score
   - Progress bars for visual metrics
   - Color-coded by metric type

JAVASCRIPT FUNCTIONALITY:

1. Canvas Setup:
   - Two canvases: phaseSpaceCanvas and energyCanvas
   - Resize handlers for responsive behavior
   - Clear and redraw on resize

2. Phase Space Visualization:
   - Draw grid background (20x20)
   - Draw X and Y axes through center
   - Draw unit circle at center
   - Label angles: 0°, 90°, 180°, 270°
   - Draw radial lines every 45°
   - Draw triangular topology overlay (equilateral triangle)
   - Label r and θ axes

3. Energy Visualization:
   - Two modes: 'time' (line graph) and 'distribution' (bar chart)
   - Time mode: show energy conservation over 100 timesteps
   - Distribution mode: show energy per token as bars
   - Toggle between modes with button

4. Token Analysis Functions:
   - analyzeTokens(): Split input text into tokens
   - generateTokenStates(): Create quantum states for each token
     * Calculate r (amplitude) and θ (phase) from token hash
     * Generate states for all 5 layers
     * Calculate attention scores using phase-distance formula
   - generateLayerState(): Apply transformations per layer
     * Theta shift based on layer number
     * R scale variation
     * Add quantum randomness

5. Attention Calculation:
   - For each token pair:
     * Calculate phase difference
     * Calculate Euclidean distance
     * Compute interference: 0.5 + 0.5 * cos(phaseDiff)
     * Compute attention: (interference * amplitudeProduct) / (distance + 0.001)
   - Normalize attention across all tokens

6. Energy Conservation:
   - Calculate total energy for each layer
   - Normalize to ensure total = number of tokens
   - Apply normalization factor to all token states

7. Physics Metrics Updates:
   - Energy: total energy / number of tokens
   - Phase coherence: magnitude of average phase vector
   - Amplitude distribution: entropy measure
   - Evolution velocity: average distance moved between layers

8. Animation Loop:
   - Apply small random movements to tokens (quantum fluctuations)
   - Recalculate energy
   - Normalize to conserve total energy
   - Redraw visualizations
   - Update metrics
   - Use requestAnimationFrame

9. Drawing Functions:
   - drawTokenStates(): Draw particles with size based on r, color based on θ
   - Draw connections between nearby tokens (distance < 1.0)
   - Connection opacity based on phase interference
   - drawEnergyVisualization(): Line or bar chart based on mode

10. Utility Functions:
    - simpleHash(): Convert string to deterministic number
    - resizeCanvases(): Handle window resize
    - toggleAnimation(): Play/pause animation
    - resetView(): Reset to initial state

INTERACTION:
- Layer buttons switch between layers, updating all visualizations
- Animation can be paused/resumed
- Energy view can be toggled between time and distribution
- Table updates when layer changes

Use only HTML, CSS in <style> tag, and JavaScript in <script> tag. No external files.
All mathematical operations should be inline.
```

---

## Technology Documentation Prompt

### File: `leviathan-technology.html`

**Prompt to Claude:**

```
Create a technical documentation page with the following specifications:

DESIGN SYSTEM:
- Use the same color palette as the main site

LAYOUT STRUCTURE:
1. Fixed header (same as main site)

2. Page header:
   - Subtitle in accent color
   - Large page title
   - Brief description

3. Architecture Overview section:
   - Section title with underline effect
   - Introduction paragraph
   - ASCII art diagram in code-block style showing:
     * Multifold Quantum Field Theory at top
     * Three foundation components
     * Unified Field Space in center
     * Triangular topology ASCII art
     * Processing components
     * Final QFNN Model at bottom
     * Use box drawing characters and arrows

4. Comparison cards (2 columns):
   - Foundation Components card
   - Processing Components card
   - Each with bulleted list (arrow bullets)

5. Core Components section:
   - Multiple subsections with h3 titles:
     a. Quantum Token Representation
     b. Phase-Distance Attention Mechanism
     c. Imaginary-Time Quantum Evolution
     d. Hebbian Learning
   - Each has: description, implementation details
   - Sub-subsections for specific topics (h4)

6. Computational Advantages section:
   - Three tables comparing Transformer vs QFNN:
     a. Parameter Efficiency
     b. Computational Complexity
     c. Memory Usage
   - Include reduction factors
   - Bulleted explanations below each table

7. Applications section:
   - Three application cards in grid:
     a. Language Modeling
     b. Quantum Systems Simulation
     c. Financial Forecasting
   - Reality Engine subsection with description
   - Quantum Computing Implementation subsection
   - CTAs to other pages

STYLING:
- Code blocks: dark background, monospace, overflow-x auto
- Math displays: light accent background, larger font
- Tables: secondary background, accent header, hover effect
- Comparison cards: secondary background, shadow, arrow bullets
- Section titles: underline with gradient (cyan → gold)
- Images: full width, rounded corners, border

CONTENT STRUCTURE:
- Technical but accessible language
- Balance theory with practical implications
- Use "Our proprietary..." when describing implementations
- Include quantitative comparisons where possible
- Link to related pages

Use only HTML and CSS in <style> tag. No JavaScript needed.
```

---

## Research Page Prompt

### File: `leviathan-research.html`

**Prompt to Claude:**

```
Create a research overview page with the following specifications:

DESIGN SYSTEM:
- Same color palette as main site

LAYOUT STRUCTURE:
1. Fixed header (consistent with other pages)

2. Page header:
   - Subtitle (e.g., "Advancing AI Through Physics")
   - Large title (e.g., "Research Overview")
   - Brief description

3. Research sections:
   - Multiple sections with descriptive titles
   - Each section contains:
     * Introduction paragraph
     * Key points in bulleted lists
     * Technical details in sub-sections
     * Links to papers or related resources

4. Publications section:
   - Cards for each publication/paper
   - Each card shows:
     * Title
     * Authors
     * Abstract/summary
     * Link to full paper
     * Date
   - Hover effect on cards

5. Research areas grid:
   - Cards for different research focus areas
   - Icon or emoji for each area
   - Title and description
   - Related projects/papers

6. Collaboration section:
   - Information about research partnerships
   - Contact for collaboration inquiries

STYLING:
- Consistent with technology page
- Emphasis on readability for technical content
- Clear hierarchy with section titles
- Academic paper citation style for references

CONTENT:
[Provide research topics, paper titles, abstracts, focus areas]

Use only HTML and CSS in <style> tag.
```

---

## Contact Component Prompt

### File: `leviathan-contact.html`

**Prompt to Claude:**

```
Create a contact section component with the following specifications:

DESIGN SYSTEM:
- Same color palette as main site

LAYOUT STRUCTURE:
1. Section title
2. Two-column grid layout:
   - Left column: Introductory text and context
   - Right column: Contact methods card

3. Contact methods card:
   - Secondary background
   - Rounded corners
   - Contains multiple contact method blocks:
     * Email (with mailto link)
     * Consulting Inquiries (description)
     * Workshop Requests (description)
     * Licensing Opportunities (description)
   - Each method has:
     * Title in accent color
     * Content in text-secondary color

STYLING:
- Card has border with low opacity accent color
- Hover effect on email link (color change to accent)
- Responsive: stack to single column on mobile

This is designed to be included in other pages, not standalone.

Use only HTML and CSS.
```

---

## General Prompt Patterns

### Pattern 1: Creating Any New Page

```
Create a [PAGE_TYPE] page for [PROJECT_NAME] using the Leviathan framework.

FRAMEWORK REQUIREMENTS:
- Use the Leviathan design system:
  * Colors: --bg-primary: #0a192f, --bg-secondary: #112240, --accent-primary: #64ffda, etc.
  * Font: "SF Mono", "Fira Code", monospace
  * Transitions: cubic-bezier(0.645, 0.045, 0.355, 1)

- Include standard header:
  * Fixed position at top
  * Logo on left
  * Navigation on right
  * Backdrop blur effect

- Use standard footer:
  * Copyright text
  * Optional tagline/quote

LAYOUT:
[Describe specific layout requirements]

SECTIONS:
[List required sections with details]

INTERACTIONS:
[Describe any JavaScript functionality needed]

STYLING NOTES:
[Any specific styling requirements]

Use only inline HTML, CSS in <style> tag, and JavaScript in <script> tag if needed.
No external dependencies.
```

### Pattern 2: Adding Canvas Animation to Any Page

```
Add a canvas-based particle animation to [PAGE_SECTION] with these specs:

PARTICLE CLASS:
- Create a class called [ClassName]Particle
- Properties:
  * x, y (position)
  * radius (size)
  * phase (for wave motion)
  * speed (movement speed)
  * amplitude (wave amplitude)
  * fibonacci constant: 1.618033988749

PHYSICS BEHAVIOR:
- Motion type: [sine wave / random / fibonacci spiral]
- Update rule: [mathematical formula]
- Boundary behavior: [wrap / bounce / reset]
- Special effects: [quantum tunneling / connections / trails]

RENDERING:
- Number of particles: [NUMBER]
- Colors: [rgba values or palette]
- Connection threshold: [DISTANCE]
- Animation loop: requestAnimationFrame
- Clear method: [full clear / fade trail]

CANVAS SETUP:
- Position: [absolute / relative]
- Z-index: [low for background / high for foreground]
- Opacity: [0-1]
- Resize handler: [responsive behavior]

Implement using vanilla JavaScript in <script> tag.
```

### Pattern 3: Creating Comparison Tables

```
Create a comparison table for [TOPIC] with the following structure:

COLUMNS:
[List column headers]

ROWS:
[For each row, provide: label, values for each column]

STYLING:
- Use Leviathan framework table styles
- Background: --bg-secondary
- Header background: rgba(100, 255, 218, 0.1)
- Header color: --accent-primary
- Hover effect: rgba(100, 255, 218, 0.03)
- Border between rows: 1px solid --bg-primary

Add explanatory text below table describing the comparison.

Use HTML table in semantic structure.
```

### Pattern 4: Creating Interactive Controls

```
Add interactive controls for [FEATURE] with these specifications:

CONTROL TYPE: [buttons / sliders / toggles / input fields]

CONTROLS:
[For each control:
 - Label/name
 - Initial state
 - Value range (if applicable)
 - Action on interaction
]

UI STYLING:
- Button style: transparent background, accent border
- Hover effect: rgba(100, 255, 218, 0.1) background
- Active state: background color change
- Disabled state: reduced opacity

JAVASCRIPT BEHAVIOR:
- Event listeners: [click / input / change]
- State management: [variables to track]
- Update functions: [what updates when control changes]
- Animation impact: [how it affects animations]

Implement with vanilla JavaScript.
```

---

## Customization Variables

### Essential Variables to Replace

When creating a new project from these prompts, replace these variables:

**Branding:**
- `LEVIATHAN AI` → Your company/project name
- `contact@leviathan-ai.net` → Your contact email
- Logo text and styling

**Content:**
- Company tagline
- About/founder story
- Project descriptions
- Service offerings
- Research topics

**Design System (Optional Customization):**
```css
:root {
    --bg-primary: #0a192f;      /* Your dark background */
    --bg-secondary: #112240;    /* Your card background */
    --accent-primary: #64ffda;  /* Your primary accent */
    --accent-gold: #ffd700;     /* Your secondary accent */
    --accent-purple: #c792ea;   /* Your tertiary accent */
    --text-primary: #e6f1ff;    /* Your heading text */
    --text-secondary: #8892b0;  /* Your body text */
}
```

**Navigation Links:**
```html
<nav>
    <ul>
        <li><a href="#section1">Link 1</a></li>
        <li><a href="#section2">Link 2</a></li>
        <li><a href="#section3">Link 3</a></li>
        <li><a href="#section4">Link 4</a></li>
    </ul>
</nav>
```

**Section IDs:**
- Update all `id` attributes in sections
- Update corresponding `href` in navigation
- Update JavaScript selectors

---

## Prompt Best Practices

### 1. Be Specific About Structure

❌ Bad:
```
Create a nice landing page with some sections
```

✅ Good:
```
Create a landing page with these exact sections:
1. Hero (100vh, centered content, canvas background)
2. About (two-column grid, 1fr 1fr)
3. Projects (auto-fit grid, min 300px cards)
```

### 2. Provide Complete Design System

❌ Bad:
```
Use a dark theme with blue accents
```

✅ Good:
```
Use this exact design system:
:root {
    --bg-primary: #0a192f;
    --accent-primary: #64ffda;
    /* ...complete palette... */
}
Font: "SF Mono", "Fira Code", monospace
Transitions: cubic-bezier(0.645, 0.045, 0.355, 1)
```

### 3. Specify Technical Implementation

❌ Bad:
```
Add some animation to particles
```

✅ Good:
```
Create RealityParticle class with:
- Properties: x, y, phase (0 to 2π), speed (0.1-0.5)
- Update: this.y += Math.sin(this.phase * 1.618) * this.amplitude * 0.02
- Draw: ctx.arc() with random color selection from palette
- Quantum tunneling: if (Math.random() > 0.999) reset position
```

### 4. Include Responsive Behavior

❌ Bad:
```
Make it work on mobile
```

✅ Good:
```
Responsive design:
- Breakpoint: 768px
- Grid changes: 2-column → 1-column
- Font sizes: h1 from 4rem → 2.5rem
- Navigation: flex-direction from row → column
```

### 5. Request Inline Code Only

❌ Bad:
```
Create the website
```

✅ Good:
```
Create a single HTML file with:
- CSS in <style> tag in <head>
- JavaScript in <script> tag before </body>
- No external files or dependencies
```

---

## Example: Building a Complete Page

### Scenario: Create a new product showcase page

**Full Prompt:**

```
Create a product showcase page for "QuantumViz Pro" using the Leviathan framework.

FRAMEWORK REQUIREMENTS:
Use the complete Leviathan design system:

:root {
    --bg-primary: #0a192f;
    --bg-secondary: #112240;
    --bg-tertiary: #1d2d50;
    --accent-primary: #64ffda;
    --accent-gold: #ffd700;
    --accent-purple: #c792ea;
    --text-primary: #e6f1ff;
    --text-secondary: #8892b0;
    --text-accent: #ccd6f6;
    --transition: all 0.25s cubic-bezier(0.645, 0.045, 0.355, 1);
}

Font family: "SF Mono", "Fira Code", "Consolas", monospace

HEADER:
- Fixed position header
- Logo: "LEVIATHAN AI"
- Navigation: Home, Products, Documentation, Support
- Backdrop filter blur
- Box shadow on scroll

LAYOUT SECTIONS:

1. Hero Section (100vh):
   - Canvas background with 50 particles
   - Particle behavior: sine wave motion using Fibonacci ratio
   - Center-aligned content:
     * Subtitle: "Advanced Visualization"
     * Title: "QuantumViz Pro" (gradient text: cyan → gold)
     * Description: "Real-time quantum field visualization for research"
     * Two buttons: "Get Started" (primary), "View Demo" (outline)

2. Features Section:
   - Grid: 3 columns (auto-fit, min 300px)
   - 6 feature cards:
     * Real-time Rendering
     * Quantum Accuracy
     * Interactive Controls
     * Export Tools
     * Cloud Sync
     * API Access
   - Each card: icon, title, description
   - Hover effect: translateY(-5px)

3. Demo Section:
   - Full-width canvas container
   - Interactive visualization (reuse physics visualizer pattern)
   - Control panel: Play/Pause, Reset, Speed slider
   - Metrics display: 4 metric cards

4. Pricing Section:
   - 3 pricing tiers in grid
   - Each tier card:
     * Name and price
     * Feature list (checkmarks)
     * CTA button
   - Highlight middle tier

5. Footer:
   - Copyright
   - Quote: "Visualizing the quantum realm"

JAVASCRIPT:
1. Particle system in hero (70 particles):
   - Properties: x, y, phase, amplitude, speed
   - Motion: y += sin(phase * 1.618) * amplitude * 0.02
   - Colors: random selection (cyan, gold, purple)
   - Connections: draw lines between particles within 240 units

2. Demo canvas:
   - Phase space visualization
   - Token particles with quantum behavior
   - Animation loop
   - Control handlers for play/pause/reset

3. Scroll effects:
   - Fade-in animations using IntersectionObserver
   - Header shadow after 50px scroll
   - Smooth scroll for anchor links

RESPONSIVE:
Breakpoint at 768px:
- Hero title: 4rem → 2.5rem
- Grid columns: multi → single
- Navigation: horizontal → vertical
- Canvas height: maintain aspect ratio

Create as single HTML file with inline CSS and JavaScript.
```

---

## Troubleshooting Common Issues

### Issue 1: Canvas Not Resizing

**Problem:** Canvas stays same size when window resizes

**Solution:** Add resize handler:
```javascript
function resizeCanvas() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
}
window.addEventListener('resize', resizeCanvas);
resizeCanvas(); // Initial call
```

### Issue 2: Animations Too Fast/Slow

**Problem:** Particle movement not smooth or too fast

**Solution:** Use small speed values and requestAnimationFrame:
```javascript
class Particle {
    constructor() {
        this.speed = Math.random() * 0.02 + 0.01; // 0.01-0.03
        this.phaseSpeed = Math.random() * 0.04 + 0.01;
    }
}
```

### Issue 3: Grid Not Responsive

**Problem:** Cards don't stack on mobile

**Solution:** Use auto-fit with minmax:
```css
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
}

@media (max-width: 768px) {
    .grid {
        grid-template-columns: 1fr;
    }
}
```

### Issue 4: Scroll Animations Not Triggering

**Problem:** Fade-in animations don't work

**Solution:** Verify IntersectionObserver setup:
```javascript
const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.classList.add('visible');
        }
    });
}, {
    threshold: 0.1,
    rootMargin: '0px 0px -100px 0px'
});

document.querySelectorAll('.fade-in').forEach(el => {
    observer.observe(el);
});
```

---

## Advanced Prompt Techniques

### Technique 1: Iterative Refinement

Start with basic structure, then refine:

**Round 1:**
```
Create a basic landing page with hero, about, and contact sections
using the Leviathan framework color scheme.
```

**Round 2:**
```
Add a canvas particle animation to the hero section with 70 particles
using Fibonacci motion patterns.
```

**Round 3:**
```
Add fade-in animations to all sections using IntersectionObserver,
triggered when 10% visible with -100px bottom margin.
```

### Technique 2: Component-Based Building

Build in modular pieces:

**Prompt 1: Header Component**
```
Create a fixed header component with logo and navigation for the Leviathan framework.
Specifications: [detailed header specs]
```

**Prompt 2: Hero Component**
```
Create a hero section with canvas animation for the Leviathan framework.
Specifications: [detailed hero specs]
```

**Prompt 3: Assembly**
```
Combine these components into a complete page:
[paste header HTML]
[paste hero HTML]
Add: about section, footer
```

### Technique 3: Reference Existing Code

```
Using the attached index.html as a reference for styling and structure,
create a new page for [PURPOSE] with these sections:
[section details]

Maintain the exact same:
- Color scheme and CSS variables
- Typography and spacing
- Header and footer structure
- Animation patterns
- Responsive breakpoints

Change only the content and section-specific layout.
```

---

## Prompt Templates by Page Type

### Landing Page Template

```
Create a [PRODUCT_NAME] landing page using the Leviathan framework.

DESIGN SYSTEM: [paste design system]
HEADER: [paste header spec]
FOOTER: [paste footer spec]

SECTIONS:
1. Hero:
   - Height: [100vh / auto]
   - Background: [canvas animation / gradient / solid]
   - Content: [title, subtitle, description, CTAs]

2. [Section Name]:
   - Layout: [grid / flexbox / two-column]
   - Content: [description]

[Additional sections...]

INTERACTIONS:
- [List JavaScript requirements]

Create as single HTML file with inline styles and scripts.
```

### Documentation Page Template

```
Create a documentation page for [TOPIC] using the Leviathan framework.

DESIGN SYSTEM: [paste design system]
HEADER: [paste header spec]

CONTENT STRUCTURE:
- Page title and subtitle
- Table of contents (optional)
- [Number] main sections with subsections
- Code blocks with syntax highlighting
- Comparison tables
- Diagrams (ASCII art or image placeholders)

SECTIONS:
[List each section with title and brief content description]

STYLING:
- Code blocks: monospace, dark background
- Tables: accent header, hover effect
- Links: accent color, underline on hover

Create as single HTML file with inline styles.
```

### Interactive Tool Template

```
Create an interactive [TOOL_NAME] using the Leviathan framework.

DESIGN SYSTEM: [paste design system]

LAYOUT:
1. Control Panel:
   - [List controls: buttons, sliders, inputs]
   - Styling: [button specs]

2. Visualization Area:
   - [Number] canvas elements
   - Layout: [grid / stacked]
   - Size: [dimensions]

3. Data Display:
   - Metrics: [list metrics]
   - Table: [columns]

JAVASCRIPT FUNCTIONALITY:
1. Initialization:
   [Setup steps]

2. Core Functions:
   - [Function name]: [purpose and implementation]

3. Animation Loop:
   [Description of update cycle]

4. Event Handlers:
   [List events and handlers]

Create as single HTML file with inline styles and scripts.
```

---

## Conclusion

These prompts provide a complete blueprint for recreating and extending the Leviathan AI framework. Key principles:

1. **Be Explicit:** Provide complete specifications
2. **Use Consistent Patterns:** Follow the established design system
3. **Request Inline Code:** Keep everything in single files
4. **Specify Interactions:** Detail all JavaScript behavior
5. **Include Responsive:** Always specify mobile breakpoints

**Next Steps:**
1. Choose the appropriate prompt template
2. Customize variables for your project
3. Add your specific content
4. Iterate and refine as needed

**For Advanced Users:**
- Combine multiple templates
- Create custom component libraries
- Build automated generation tools
- Develop style guide variations

---

**Framework Version:** 1.0
**Last Updated:** 2024
**Maintained by:** Leviathan AI
**Contact:** contact@leviathan-ai.net
