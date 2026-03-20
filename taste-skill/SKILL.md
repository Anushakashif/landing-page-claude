# UI & Animation Design Skill

**Version:** 1.0.0  
**Purpose:** Create premium, modern UI designs with polished animations and visual quality

---

## Configuration

Adjust these settings before starting (scale 1-10):

```
DESIGN_VARIANCE: 7     // Layout creativity: 1-3 (standard) → 8-10 (experimental)
MOTION_INTENSITY: 6    // Animation level: 1-3 (subtle) → 8-10 (dynamic)
VISUAL_DENSITY: 4      // Spacing density: 1-3 (spacious) → 8-10 (compact)
```

---

## Core Design Principles

### 1. Layout & Composition

- **Break the grid**: Use asymmetric layouts, overlapping elements, and unexpected whitespace
- **Visual hierarchy**: Establish clear focal points with size, color, and positioning
- **Rule of thirds**: Position key elements along imaginary 3x3 grid lines
- **Negative space**: Use generous margins/padding (minimum 24px, often 48px-96px)
- **Container max-width**: 1200px-1440px for content, full-bleed for hero sections

### 2. Typography

- **Font stacks**: Use premium fonts (Inter, Geist, SF Pro, General Sans, Satoshi)
- **Scale ratio**: 1.250 (Major Third) or 1.333 (Perfect Fourth)
- **Line-height**: 1.2-1.4 for headings, 1.5-1.7 for body text
- **Letter-spacing**: -0.02em to -0.04em for large headings (>48px)
- **Font weights**: 400 (regular), 500 (medium), 600 (semibold), 700 (bold)
- **Max line length**: 65-75 characters for readability

### 3. Color System

- **Primary palette**: 1 base color + 3-5 shades (50-900 scale)
- **Neutral tones**: Warm grays (#F5F5F4, #E7E5E4, #A8A29E, #57534E, #292524)
- **Accent usage**: 60-30-10 rule (60% neutral, 30% secondary, 10% accent)
- **Gradients**: Subtle 2-3 color gradients at 10-20% opacity for depth
- **Dark mode**: Pure black (#000) avoided; use #0A0A0A or #111111

### 4. Spacing & Sizing

- **Base unit**: 4px or 8px grid system
- **Spacing scale**: 4, 8, 12, 16, 24, 32, 48, 64, 96, 128, 192px
- **Component padding**: Minimum 16px, preferred 24px-32px
- **Section padding**: 96px-128px vertical on desktop, 64px on mobile
- **Border radius**: 8px (small), 12px (medium), 16px-24px (large), 9999px (pills)

### 5. Shadows & Depth

```css
/* Elevation levels */
shadow-xs: 0 1px 2px rgba(0, 0, 0, 0.04)
shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.06), 0 1px 2px rgba(0, 0, 0, 0.04)
shadow-md: 0 4px 8px rgba(0, 0, 0, 0.06), 0 2px 4px rgba(0, 0, 0, 0.04)
shadow-lg: 0 10px 24px rgba(0, 0, 0, 0.08), 0 4px 8px rgba(0, 0, 0, 0.04)
shadow-xl: 0 20px 40px rgba(0, 0, 0, 0.1), 0 8px 16px rgba(0, 0, 0, 0.06)
shadow-2xl: 0 40px 80px rgba(0, 0, 0, 0.12), 0 16px 32px rgba(0, 0, 0, 0.08)

/* Colored shadows for depth */
shadow-colored: 0 8px 32px rgba(59, 130, 246, 0.15)
```

### 6. Borders & Dividers

- **Border width**: 1px standard, use rgba for subtlety: `rgba(0,0,0,0.08)` or `rgba(255,255,255,0.1)`
- **Inner borders**: For inset depth: `inset 0 1px 0 rgba(255,255,255,0.1)`
- **Gradient borders**: Use `background-clip` with gradient for premium feel
- **Divider opacity**: 10-20% of base color

---

## Animation & Motion Guidelines

### 1. Timing Functions

```css
/* Easing curves */
ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1)      /* Premium feel */
ease-out-expo-strong: cubic-bezier(0.19, 1, 0.22, 1)
ease-in-out-quart: cubic-bezier(0.76, 0, 0.24, 1)
ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1)    /* Bouncy */
ease-smooth: cubic-bezier(0.4, 0, 0.2, 1)         /* Standard */
ease-elastic: cubic-bezier(0.68, -0.55, 0.265, 1.55)

/* Duration scale */
duration-instant: 100ms
duration-fast: 200ms
duration-normal: 300ms
duration-slow: 500ms
duration-slower: 700ms
duration-slowest: 1000ms
```

### 2. Animation Patterns

#### Entrance Animations
```css
/* Fade up (most common) */
@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(24px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Scale in */
@keyframes scaleIn {
  from {
    opacity: 0;
    transform: scale(0.95);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

/* Stagger children */
.child-1 { animation-delay: 0ms; }
.child-2 { animation-delay: 100ms; }
.child-3 { animation-delay: 200ms; }
.child-4 { animation-delay: 300ms; }
```

#### Hover Effects
```css
/* Lift + shadow */
.card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}
.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
}

/* Scale + glow */
.button {
  transition: all 0.2s ease;
}
.button:hover {
  transform: scale(1.02);
  box-shadow: 0 0 24px rgba(59, 130, 246, 0.4);
}

/* Magnetic effect (advanced) */
/* Follow cursor slightly within element bounds */
```

#### Loading States
```css
/* Skeleton loader */
@keyframes shimmer {
  0% { background-position: -1000px 0; }
  100% { background-position: 1000px 0; }
}
.skeleton {
  background: linear-gradient(
    90deg,
    #f0f0f0 0%,
    #f8f8f8 50%,
    #f0f0f0 100%
  );
  background-size: 1000px 100%;
  animation: shimmer 2s infinite;
}

/* Spinner */
@keyframes spin {
  to { transform: rotate(360deg); }
}
```

#### Scroll-Triggered
```css
/* Reveal on scroll */
.reveal {
  opacity: 0;
  transform: translateY(48px);
  transition: opacity 0.8s ease, transform 0.8s ease;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Parallax (subtle) */
.parallax {
  transform: translateY(calc(scrollY * 0.3));
}
```

### 3. Micro-interactions

- **Button press**: Scale down to 0.96-0.98 on active
- **Input focus**: Border color + ring shadow (3px offset)
- **Toggle switch**: Spring animation with 0.4s duration
- **Dropdown**: Fade + scale from 0.95 to 1, 200ms
- **Tooltip**: Fade + slide 8px, 150ms
- **Modal**: Backdrop fade (200ms) + content scale (300ms)

### 4. Page Transitions

```css
/* Cross-fade */
.page-enter {
  opacity: 0;
}
.page-enter-active {
  opacity: 1;
  transition: opacity 400ms ease;
}
.page-exit {
  opacity: 1;
}
.page-exit-active {
  opacity: 0;
  transition: opacity 300ms ease;
}

/* Slide + fade */
.slide-up-enter {
  opacity: 0;
  transform: translateY(48px);
}
.slide-up-enter-active {
  opacity: 1;
  transform: translateY(0);
  transition: opacity 500ms ease, transform 500ms ease;
}
```

---

## Component Patterns

### Buttons

```css
/* Primary button */
.btn-primary {
  padding: 12px 24px;
  font-weight: 500;
  border-radius: 12px;
  background: linear-gradient(135deg, #3B82F6 0%, #2563EB 100%);
  color: white;
  border: none;
  box-shadow: 0 4px 12px rgba(59, 130, 246, 0.3);
  transition: all 0.2s ease;
}
.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(59, 130, 246, 0.4);
}
.btn-primary:active {
  transform: scale(0.97);
}

/* Ghost button */
.btn-ghost {
  padding: 12px 24px;
  font-weight: 500;
  border-radius: 12px;
  background: rgba(255, 255, 255, 0.5);
  backdrop-filter: blur(8px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.2s ease;
}
.btn-ghost:hover {
  background: rgba(255, 255, 255, 0.7);
}
```

### Cards

```css
/* Glassmorphism card */
.card-glass {
  background: rgba(255, 255, 255, 0.7);
  backdrop-filter: blur(24px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 24px;
  padding: 32px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.06);
}

/* Elevated card */
.card-elevated {
  background: white;
  border-radius: 16px;
  padding: 24px;
  border: 1px solid rgba(0, 0, 0, 0.06);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.04);
  transition: all 0.3s ease;
}
.card-elevated:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 32px rgba(0, 0, 0, 0.08);
}
```

### Inputs

```css
/* Modern input */
.input-modern {
  padding: 14px 18px;
  font-size: 15px;
  border-radius: 12px;
  border: 1px solid rgba(0, 0, 0, 0.1);
  background: rgba(255, 255, 255, 0.8);
  transition: all 0.2s ease;
}
.input-modern:focus {
  outline: none;
  border-color: #3B82F6;
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.15);
  background: white;
}

/* Floating label */
.input-floating {
  position: relative;
}
.input-floating label {
  position: absolute;
  left: 16px;
  top: 50%;
  transform: translateY(-50%);
  transition: all 0.2s ease;
  pointer-events: none;
}
.input-floating input:focus + label,
.input-floating input:not(:placeholder-shown) + label {
  top: 0;
  font-size: 12px;
  padding: 0 8px;
  background: white;
  color: #3B82F6;
}
```

### Navigation

```css
/* Sticky nav with blur */
.nav-sticky {
  position: sticky;
  top: 0;
  z-index: 100;
  background: rgba(255, 255, 255, 0.8);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid rgba(0, 0, 0, 0.06);
}

/* Active link indicator */
.nav-link {
  position: relative;
  padding: 8px 0;
}
.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: #3B82F6;
  transition: width 0.3s ease;
}
.nav-link.active::after,
.nav-link:hover::after {
  width: 100%;
}
```

---

## Responsive Breakpoints

```css
/* Mobile-first approach */
--breakpoint-sm: 640px;   /* Small tablets */
--breakpoint-md: 768px;   /* Tablets */
--breakpoint-lg: 1024px;  /* Laptops */
--breakpoint-xl: 1280px;  /* Desktops */
--breakpoint-2xl: 1536px; /* Large screens */

/* Container queries for components */
@container (min-width: 400px) {
  /* Component-specific responsive */
}
```

---

## Accessibility Requirements

- **Color contrast**: Minimum 4.5:1 (WCAG AA), prefer 7:1 (AAA)
- **Focus visible**: Always show focus ring (2px minimum)
- **Reduced motion**: Respect `prefers-reduced-motion`
- **Keyboard nav**: All interactive elements reachable via Tab
- **Screen readers**: Use semantic HTML + ARIA where needed
- **Touch targets**: Minimum 44x44px for mobile

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## Code Quality Rules

1. **No placeholder comments**: Never write `// ... rest of code` or `<!-- content here -->`
2. **Complete implementations**: Write full, working code
3. **Semantic HTML**: Use proper elements (`<article>`, `<section>`, `<nav>`, etc.)
4. **BEM or utility classes**: Consistent naming convention
5. **CSS custom properties**: Use variables for colors, spacing, fonts
6. **Mobile-first**: Write base styles for mobile, enhance for larger screens
7. **Performance**: Optimize animations (use `transform` and `opacity` for 60fps)

---

## Visual Checklist

Before finalizing any UI:

- [ ] Hierarchy is clear at a glance
- [ ] Sufficient whitespace (add 20% more than feels natural)
- [ ] Colors have proper contrast
- [ ] Animations feel smooth (ease-out, not linear)
- [ ] Hover states exist for all interactive elements
- [ ] Focus states are visible
- [ ] Mobile layout is considered
- [ ] Typography scale is consistent
- [ ] Border radius is consistent
- [ ] Shadows create appropriate depth
- [ ] Loading states are designed
- [ ] Error states are designed
- [ ] Empty states are designed

---

## Inspiration References

Study these for premium design patterns:

- **Linear** (linear.app) - Clean, performant, subtle animations
- **Vercel** (vercel.com) - Modern gradients, clean typography
- **Raycast** (raycast.com) - Polished interactions, dark mode excellence
- **Notion** (notion.so) - Editorial layouts, warm minimalism
- **Stripe** (stripe.com) - Gradients, illustrations, motion
- **Apple** (apple.com) - Large imagery, smooth scroll animations
- **Gumroad** (gumroad.com) - Playful, colorful, personality-driven

---

## Usage Instructions

1. Copy this `SKILL.md` file to your project root
2. Reference it in your AI editor: `@SKILL.md` or include in context
3. Adjust configuration values at the top to match project needs
4. Build UI components following these guidelines
5. Always implement complete, production-ready code

---

**Remember:** Great design is invisible. It feels natural, not forced. Every pixel should have intention. Every animation should serve a purpose. Make it feel expensive.
