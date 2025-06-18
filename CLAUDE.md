# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a modern portfolio website built with **Astro**, **React**, and **Tailwind CSS**. The architecture follows a component-based approach with clean separation of concerns:

- **Framework**: Astro v5 with React integration for interactive components
- **Styling**: Tailwind CSS v4 with glassmorphism design patterns
- **Content**: Centralized data management in `src/lib/data.ts`
- **Components**: React components with `client:only="react"` directive for interactivity
- **Animations**: Framer Motion for smooth transitions and interactions
- **Theme**: Built-in dark/light mode with system preference detection

## Development Commands

```bash
# Start development server (runs on http://localhost:4321)
bun dev

# Build for production
bun run build

# Preview production build
bun run preview
```

## Architecture

### Data Layer
All portfolio content is centralized in `src/lib/data.ts` with typed exports:
- `personalInfo` - Contact details and basic info
- `workExperience` - Job history with achievements
- `education` - Academic background
- `skills` - Categorized technical skills
- `projects` - Portfolio projects with descriptions
- `awards` - Recognitions and achievements

### Component Structure
- **Layout**: `src/layouts/Layout.astro` - Base HTML structure with theme system
- **Sections**: Each portfolio section is a separate React component
- **UI Components**: Reusable components in `src/components/ui/`
- **Glass Components**: Specialized glassmorphism components with backdrop-blur effects

### Styling Patterns
- Uses Tailwind CSS v4 with custom CSS variables in `:root`
- Glassmorphism effects via `backdrop-blur-md` and semi-transparent backgrounds
- Responsive design with mobile-first approach
- Theme switching implemented via CSS classes and localStorage

### Path Aliases
TypeScript paths configured with `@/*` mapping to `./src/*`

## Key Technical Patterns

1. **Astro Components**: Use `.astro` files for static content, React components for interactivity
2. **Client Directives**: Interactive components require `client:only="react"` directive
3. **Theme System**: Automatic theme detection with manual toggle, persisted in localStorage
4. **Animation Strategy**: Framer Motion for micro-interactions, CSS transitions for theme changes
5. **Content Management**: All portfolio data lives in a single TypeScript file for easy updates

## Customization Notes

To customize the portfolio, update `src/lib/data.ts` with your information. The component structure will automatically reflect changes without requiring code modifications.