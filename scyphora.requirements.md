# scyphora.requirements.md

## Project: Scyphora Website

### Purpose

To create the **official Scyphora website**, representing the brand’s invisible intelligence, minimal design, and effortless user experiences.  
The website should feel inevitable — every element calm, sharp, and necessary.

---

## 1. General Directives

| Key                  | Description                                                     |
| -------------------- | --------------------------------------------------------------- |
| **Framework**        | Astro + TailwindCSS v4 + ts                                     |
| **Style**            | Minimalist dark mode with aurora highlights                     |
| **Design System**    | Space-inspired gravity flow, sharp typography, subtle gradients |
| **AI Integration**   | Content personalization based on context or user type           |
| **Accessibility**    | WCAG 2.2 AA minimum                                             |
| **Animation Style**  | Framer Motion — smooth gravity or orbit transitions             |
| **Performance Goal** | Core Web Vitals > 90%                                           |

---

## 2. Brand Tokens

### Color Palette

```css
/* Tailwind Config Css*/
@theme {
  --color-space: #0b0c10;
  --color-gravity: #43464b;
  --color-aurora: #f1f3f5;
  --color-pulse: #5ba8d0;
  --color-chronos: #d5a021;
}
```

## 3.- Typography

```css
/* Tailwind Config Css*/

{
  "fontFamily": {
    "sans": ["Sora", "Poppins", "sans-serif"],
    "display": ["Space Grotesk", "Sora", "sans-serif"]
  },
  "fontWeights": {
    "light": 300,
    "regular": 400,
    "medium": 500,
    "semibold": 600
  }
}

```

## 4. Grid

use @src/styles/grid.css for grid styles with a wrapper of content-grid and if the section is full width use full-grid and a breakout for intermediate width

4. Page Architecture

- Homepage (/)

- Hero Section

* **Headline**: “Invisible Power. Visible Simplicity.”

* **Subline**: “Not just simple — inevitable.”

* **Button**: “Discover Scyphora”

* **Visual**: Abstract gravity field or smooth vortex background animation.

* **Tone**: Calm authority, quiet confidence.

- Philosophy Section

* **Title**: “We translate complexity into clarity.”

* **Paragraph**: Short explanation of how Scyphora simplifies experiences across legacy and modern systems using AI context.

* **Accent**: Highlight Honesty, Transformation, Inevitability.

- Solutions Section

* **Grid of Scyphora pillars**:

  1.- Core – Backend intelligence made invisible.

  2.- Flow – Frontend experience, natural and fluid.

  3.- Nexus – Bridge between systems and AI.

  4.- Pulse – Real-time adaptive context.

  5.- Horizon – Predictive foresight and analytics.

Each card has:

Subtle pulse hover animation.

Minimal icon or flowing line art.

**How It Works**

- Visual diagram:
  Complex Systems → AI Proxy (Scyphora) → Effortless Experience

- Include animation showing simplification or gravity convergence.

**About Section**

- **Quote:**

> “We’re not afraid of legacy — we make it inevitable.”

- Short company story with mention of honesty and transformative approach.

**Contact Section**

- **Message**: “Tell us what feels too complex — we’ll make it effortless.”

**Contact** form or CTA to schedule consultation.

**Button**: “Let’s Simplify Together”

5. Component Guidelines
   Component Description Behavior
   Button Rounded-xl, gradient hover (pulse → chronos) Soft transition, no bounce
   Card Floating, shadow-lg, bg-space/40 with blur Hover lift 1–2px
   Navbar Transparent → solid on scroll Active link glow (pulse blue)
   Footer Minimal links + Scyphora logo Include slogan subtly
   Logo Wordmark “Scyphora” with optional ring motion SVG adaptable

6. AI Context Integration (Optional for Smart Version)
   Context Behavior
   User Type Detection Adjust homepage emphasis: technical, business, or creative.
   System Scan Input Option to upload API or JSON to see simplification demo.
   AI Narrative Mode Generate adaptive case studies or product demos live.

7. Visual Metaphors
   Concept Representation
   Gravity Smooth inward animation, curved motion, subtle lens distortion.
   Flow Linear gradients that move slowly or respond to hover.
   Chronos (Time) Smooth sequential transitions — no abrupt cuts.
   Inevitability Consistency, balance, predictable rhythm in UX.

8. Logo Specifications
   Element Description
   Wordmark “Scyphora” – Sora or Poppins, tight kerning, lowercase preferred.
   Slogan “Invisible Power. Visible Simplicity.” below or right-aligned.
   Logomark (optional) Circular flow / gravitational ring.
   Spacing Clear 1.5× height padding.
   Color Use Aurora White on Space Black primary.

9. Technical Recommendations
   Area Requirement
   Hosting Vercel or Netlify for CI/CD integration.
   CMS Sanity or Contentlayer (if editable sections needed).
   AI API Optional integration with OpenAI / Gemini for contextual interaction demos.
   Analytics Simple privacy-first analytics (Plausible / Umami).

10. SEO & Metadata
    Tag Value
    Title Scyphora – Invisible Power. Visible Simplicity.
    Description Scyphora transforms complexity into effortless AI-driven experiences.
    OG Image Minimal dark gradient with “Scyphora” and slogan.
    Keywords AI context integration, UX simplification, legacy modernization, frontend experience, backend intelligence

11. Copy Guidelines
    Section Style Example
    Headlines Declarative, calm, confident “Complexity ends here.”
    Body Honest and explanatory “We build invisible bridges between old systems and new experiences.”
    CTAs Minimal verbs “Discover”, “Simplify”, “Connect”

12. Summary

Scyphora’s website must feel like an AI-native gravity field — calm, intelligent, inevitable.
Every section should breathe simplicity while hiding immense potential beneath.

Design Principle: If it can be removed and still work — remove it.
Experience Goal: The user should feel guided, not impressed.

13. Deliverables

✅ index.tsx (Home page)

✅ components/ (cards, nav, footer, buttons)

✅ styles/globals.css with Tailwind tokens

✅ public/logo.svg and favicon

✅ SEO metadata and OG image

✅ Optional AI contextual layer integration

13. Final Note

Scyphora is not a product — it’s a transformation layer.
The website must reflect this truth in every pixel, motion, and sentence.

> Invisible Power. Visible Simplicity.
> Not just simple — inevitable.

````yaml
## Layout Structure

```bash
/app
  ├── layout.tsx
  ├── page.tsx
  ├── globals.css
/components
  ├── HeroSection.tsx
  ├── PhilosophySection.tsx
  ├── SolutionsSection.tsx
  ├── AboutSection.tsx
  ├── HowItWorks.tsx
  ├── ContactSection.tsx
  ├── Navbar.tsx
  ├── Footer.tsx
/lib
  ├── aiContext.ts (optional AI integration)
/public
  ├── logo.svg
  ├── favicon.svg

````
