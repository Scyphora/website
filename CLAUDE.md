# Base Instructions for Claude

Always use context7 when I need code generation, setup or configuration steps, or
library/API documentation. This means you should automatically use the Context7 MCP
tools to resolve library id and get library docs without me having to explicitly ask.

## Recent Session Notes (2025-10-06)

### Design System Established
- **Buttons**: Use backlight glow effect (transparent bg with glowing border/shadow), NOT gradient fills
  - Primary: `bg-pulse/10 border-2 border-pulse shadow-lg shadow-pulse/40 backdrop-blur-sm`
  - Hover effect: Intensify shadow (`shadow-pulse/60`) and brighten border
- **Mobile Navigation**: Fully functional with proper z-index (z-40) and light/dark mode support
- **Footer**: 3-column clean layout with backlight glow on social icons

### Component Patterns
- All interactive elements use backlight glow pattern (transparent bg + border + shadow glow)
- Glass morphism with `backdrop-blur-sm` on buttons and UI elements
- Proper light/dark mode support throughout

**See `SESSION_LOG.md` for complete session details and all changes made.**

# Bash commands

- pnpm run dev: Run the project
- pnpm run build: Build the typechecker
- pnpm run preview: Preview the project
- pnpm run astro: Run Astro commands

# Code style

- Use ES modules (import/export) syntax, not CommonJS (require)
- Destructure imports when possible (eg. import { foo } from 'bar') and use type import syntax when importing types (eg. import type { Foo } from 'bar')
- Use single quotes for strings, except to avoid escaping
- Use semicolons
- Use trailing commas in multiline objects/arrays
- Use 2 spaces for indentation
- Use parentheses around arrow function parameters, even if there is only one parameter
- Use template literals instead of string concatenation
- Use object shorthand syntax when the property name is the same as the variable name
- Use optional chaining and nullish coalescing operators when appropriate

# Workflow

- Be sure to typecheck when you’re done making a series of code changes
- Prefer running single tests, and not the whole test suite, for performance

# Used Technologies

- [Astro](https://astro.build/): Static site generator
- [TypeScript](https://www.typescriptlang.org/): Type checker and language
- [pnpm](https://pnpm.io/): Package manager
- [Tailwind CSS](https://tailwindcss.com/): CSS framework version 4
- [Biome.js] (https://biomejs.dev/): Code formatter and linter
