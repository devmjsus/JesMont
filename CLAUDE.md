# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev        # Start dev server at http://localhost:3000
npm run build      # Build for production
npm run generate   # Static site generation
npm run preview    # Preview production build
```

No test suite is configured for this project.

## Architecture

This is a **Nuxt 4 personal portfolio** (single-page) for Jesús Montoya, using Vue 3 + Tailwind CSS. The Nuxt `app/` directory layout is used (Nuxt 4 convention).

**Page structure** — `app/pages/index.vue` composes three full-width sections stacked vertically:
1. `HeroSection.vue` — intro with avatar, name, role, description, and CTA buttons
2. `SkillsSection.vue` — skills grid with scroll-triggered entrance animation
3. `ContactSection.vue` — social links + contact form (UI only, no backend submission)

**Scroll animations** — `SkillsSection` and `ContactSection` use `IntersectionObserver` to trigger CSS transitions on scroll. The pattern is: `isVisible` ref drives opacity/translate classes; `entranceDone` ref removes stagger delays after the entrance completes so hover transitions aren't affected.

**Styling** — Tailwind via `@nuxtjs/tailwindcss`. The design system uses `gray-950/900/800` backgrounds with `emerald-400/500` accents. `app/assets/css/main.css` only adds `scroll-behavior: smooth`. The font is Inter (declared in `tailwind.config.js`).

**Icons** — Social link icons in `ContactSection` are inline SVG strings rendered via `v-html`, not an icon library.

**No backend** — The contact form has `@submit.prevent` but no submission logic. No API routes, no server middleware, no Pinia/Vuex.
