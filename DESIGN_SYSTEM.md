# Scyphora Design System

> Reference guide for the Scyphora website design patterns and components

## Brand Identity

**Tagline**: "Invisible Power. Visible Simplicity."
**Essence**: "Not just simple — inevitable."

### Philosophy
- Embrace complexity and translate it into clarity
- Act as the AI proxy between deep system power and human-friendly interaction
- Power made invisible, experience made inevitable

---

## Color Palette

### Primary Colors
```css
--color-space: #0a0b0e           /* Deep space black - base background */
--color-space-light: #151619     /* Lighter space - secondary background */
--color-aurora: #ffffff          /* Pure white - primary text */
--color-aurora-dark: #f1f3f5     /* Off-white - secondary highlights */
--color-pulse: #5ba8d0           /* Blue - primary accent */
--color-chronos: #d5a021         /* Gold - secondary accent */
```

### Extended Colors
```css
--color-gravity: #d1d5db         /* Light gray - secondary text */
--color-gravity-light: #e5e7eb   /* Lighter gray - tertiary text */
--color-pulse-light: #7bbde0     /* Light blue - hover states */
--color-chronos-light: #e5b741   /* Light gold - hover states */
```

### Usage Guide
- **Space**: All backgrounds in dark mode
- **Aurora**: Primary text and headings
- **Gravity**: Secondary text and labels
- **Pulse**: Interactive elements, hover states, primary CTAs
- **Chronos**: Accent highlights, secondary CTAs

---

## Typography

### Font Families
```css
--font-sans: 'Sora', 'Poppins', sans-serif;        /* Body text */
--font-display: 'Space Grotesk', 'Sora', sans-serif; /* Headings */
```

### Font Weights
```css
--font-weight-light: 300
--font-weight-regular: 400
--font-weight-medium: 500
--font-weight-semibold: 600
--font-weight-bold: 700
```

### Scale
- **h1**: `clamp(2.5rem, 5vw, 4.5rem)` - Hero headlines
- **h2**: `clamp(2rem, 4vw, 3.5rem)` - Section headings
- **Body**: `16px` base with `1.7` line-height

---

## Component Patterns

### 1. Backlight Glow Effect ⭐

**The signature pattern**: Transparent backgrounds with glowing borders and shadows

```css
/* Primary Button */
bg-pulse/10
border-2 border-pulse
text-aurora
shadow-lg shadow-pulse/40
hover:shadow-xl hover:shadow-pulse/60
hover:border-pulse-light
backdrop-blur-sm

/* Secondary Button */
bg-space-light/50
border border-aurora/20
hover:border-chronos/50
shadow-lg shadow-chronos/30
backdrop-blur-sm

/* Ghost Button */
bg-transparent
border-2 border-aurora/20
hover:border-pulse
hover:bg-pulse/5
shadow-pulse/30
```

**When to use**:
- All buttons (primary, secondary, ghost)
- Interactive cards
- Social media icons
- Form inputs on focus
- CTA elements

**DO NOT use**: Solid gradient backgrounds (`bg-gradient-to-r from-pulse to-chronos`)

---

### 2. Glass Morphism

```css
/* Light Glass */
.glass {
  background: rgba(15, 16, 20, 0.5);
  backdrop-filter: blur(20px) saturate(180%);
  border: 1px solid rgba(241, 243, 245, 0.08);
}

/* Strong Glass */
.glass-strong {
  background: rgba(20, 21, 25, 0.7);
  backdrop-filter: blur(30px) saturate(200%);
  border: 1px solid rgba(241, 243, 245, 0.12);
}
```

**When to use**:
- Modal overlays
- Dropdown menus
- Card backgrounds
- Form containers
- Navigation bars (with backdrop-blur-md)

---

### 3. Gradient Text

```css
/* Animated Gradient */
.gradient-text {
  background: linear-gradient(135deg, var(--color-pulse-light), var(--color-chronos-light));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  background-size: 200% 200%;
  animation: gradient-shift 4s ease infinite;
}

/* Static Gradient */
.gradient-text-static {
  background: linear-gradient(135deg, var(--color-pulse), var(--color-chronos));
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}
```

**When to use**:
- Hero headline keywords
- Stats/metrics numbers
- Special emphasis words
- Section highlights

---

## Animations

### Available Keyframes

```css
@keyframes fadeInUp          /* Entrance animation */
@keyframes fadeInScale       /* Scale-in animation */
@keyframes float             /* Floating effect */
@keyframes pulse-glow        /* Pulsing glow */
@keyframes rotate-slow       /* Slow rotation */
@keyframes gradient-shift    /* Gradient animation */
@keyframes slide-up          /* Slide-up entrance */
```

### Usage Classes

```css
.animate-fade-in-up         /* duration: 0.8s */
.animate-fade-in-scale      /* duration: 0.6s */
.animate-float              /* duration: 6s, infinite */
.animate-pulse-glow         /* duration: 3s, infinite */
.animate-rotate-slow        /* duration: 30s, infinite */
.animate-slide-up           /* duration: 0.6s */
```

### Stagger Delays

Use inline `style="animation-delay: 0.2s"` to create stagger effects:

```html
<div class="animate-fade-in-up">First</div>
<div class="animate-fade-in-up" style="animation-delay: 0.1s;">Second</div>
<div class="animate-fade-in-up" style="animation-delay: 0.2s;">Third</div>
```

---

## Spacing System

```css
--spacing-xs: 0.5rem    /* 8px */
--spacing-sm: 1rem      /* 16px */
--spacing-md: 1.5rem    /* 24px */
--spacing-lg: 2rem      /* 32px */
--spacing-xl: 3rem      /* 48px */
--spacing-2xl: 4rem     /* 64px */
```

### Container Padding
- Mobile: `px-6` or `px-8`
- Desktop: `lg:px-8` or `lg:px-16`
- Max width: `max-w-7xl mx-auto`

---

## Responsive Breakpoints

Following Tailwind defaults:
- **sm**: 640px
- **md**: 768px
- **lg**: 1024px (primary breakpoint)
- **xl**: 1280px
- **2xl**: 1536px

### Common Patterns

```html
<!-- Mobile first -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3">

<!-- Hide on mobile -->
<div class="hidden lg:flex">

<!-- Mobile menu -->
<div class="lg:hidden">
```

---

## Component Library

### Button Component

**Location**: `src/components/ui/Button.astro`

**Variants**:
- `primary`: Pulse blue backlight glow
- `secondary`: Chronos gold backlight glow
- `ghost`: Transparent with border

**Sizes**:
- `sm`: `px-5 py-2.5 text-sm`
- `md`: `px-7 py-3.5 text-base`
- `lg`: `px-9 py-4 text-lg`

**Usage**:
```astro
<Button href="#contact" variant="primary" size="lg">
  Contact Us
</Button>
```

---

### Card Component

**Location**: `src/components/ui/Card.astro`

**Features**:
- Glass morphism background
- Hover lift effect
- Optional glow prop

**Usage**:
```astro
<Card glow="pulse">
  <h3>Card Title</h3>
  <p>Card content</p>
</Card>
```

---

## Navigation Patterns

### Desktop Navigation
- Fixed top navbar with `backdrop-blur-md`
- Horizontal menu with 12-unit gap
- Scroll effect: changes background opacity at 20px
- Contact button uses primary button style

### Mobile Navigation
- Hamburger menu (transforms to X on open)
- Full-screen slide-in from right
- Dark mode: `rgba(10, 11, 14, 0.98)`
- Light mode: `rgba(255, 255, 255, 0.98)`
- Closes on: link click, outside click, button click
- z-index: `z-40` (navbar is `z-50`)

---

## Theme Support

### Dark Mode (Default)
- Background: Radial gradient from space-light to space
- Text: Aurora (white) and gravity (light gray)
- Ambient effects: Pulse and chronos glows

### Light Mode
- Background: Sunrise gradient (`#fef3e2` → `#fca86d`)
- Text: Dark grays and blacks
- Maintained contrast for accessibility
- Uses `@media (prefers-color-scheme: light)`

### Color Overrides for Light Mode
```css
@media (prefers-color-scheme: light) {
  body { background: linear-gradient(...); }
  h1, h2, h3 { color: #1a1a1a; }
  .text-aurora { color: #1a1a1a; }
  #mobile-menu { background: rgba(255, 255, 255, 0.98) !important; }
}
```

---

## Accessibility

### Standards
- WCAG 2.2 AA compliance
- Proper contrast ratios (min 4.5:1 for text)
- Focus indicators on all interactive elements
- Semantic HTML structure
- ARIA labels on icon-only buttons

### Focus States
```css
focus:outline-none
focus:border-pulse
focus:ring-2
focus:ring-pulse/20
```

---

## Best Practices

### DO ✅
- Use backlight glow effect for all buttons
- Apply `backdrop-blur-sm` to interactive elements
- Use gradient text sparingly for emphasis
- Implement smooth transitions (200-300ms)
- Maintain consistent spacing using Tailwind utilities
- Test in both light and dark modes
- Use semantic HTML

### DON'T ❌
- Use solid gradient backgrounds on buttons
- Overuse animations (subtle is better)
- Forget mobile responsiveness
- Skip accessibility attributes
- Use too many accent colors
- Hardcode spacing values

---

## File Structure

```
src/
├── components/
│   ├── ui/
│   │   ├── Button.astro
│   │   └── Card.astro
│   ├── sections/
│   │   ├── HeroSection.astro
│   │   ├── PhilosophySection.astro
│   │   ├── SolutionsSection.astro
│   │   ├── HowItWorksSection.astro
│   │   ├── AboutSection.astro
│   │   └── ContactSection.astro
│   ├── Navbar.astro
│   └── Footer.astro
├── layouts/
│   └── Layout.astro
├── pages/
│   └── index.astro
└── styles/
    └── global.css
```

---

## Quick Reference

### Common Class Combinations

**Primary Button**:
```
bg-pulse/10 border-2 border-pulse text-aurora
shadow-lg shadow-pulse/40 hover:shadow-xl hover:shadow-pulse/60
hover:border-pulse-light backdrop-blur-sm transition-all duration-200
```

**Card with Glow**:
```
glass-strong rounded-3xl p-8 hover-lift
hover:shadow-lg hover:shadow-pulse/30 transition-all duration-300
```

**Section Container**:
```
container mx-auto px-8 lg:px-16 py-20 relative z-10
```

**Gradient Heading**:
```
text-4xl lg:text-6xl font-display font-bold gradient-text
```

---

## Version
Last updated: 2025-10-06
Design System v1.0
