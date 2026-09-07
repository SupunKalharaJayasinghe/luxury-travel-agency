# Project

- This is a premium luxury tourism and travel agency website.
- Aim for a bespoke, high-end commercial website rather than a generic template.

# Stack

- npm with `package-lock.json`; use `npm ci` for reproducible installs.
- Next.js 16.3.4 App Router, React / React DOM 19.2.8, and TypeScript 6.0.3 with strict mode and bundler module resolution.
- Tailwind CSS 4.3.3 through `@tailwindcss/postcss` in `postcss.config.mjs`.
- ESLint 9.39.5 with Next.js Core Web Vitals and TypeScript flat configs in `eslint.config.mjs`.
- These are the currently installed versions; consult `package.json` and the lockfile before changing dependencies. Check peer compatibility before upgrades.
- `next.config.ts` currently uses framework defaults; add configuration only for a concrete need.

# Architecture

- Follow Next.js App Router conventions and extend the current `src/` structure cleanly.
- Routes and page composition live in `src/app/`; the scaffold contains `page.tsx`, `layout.tsx`, and `globals.css`.
- Prefer Server Components. Add `"use client"` only where client-side behavior requires it, keeping the client boundary narrow.
- Separate reusable UI from page-specific composition when appropriate; introduce `src/components/` when shared components are needed.
- Use the existing `@/*` alias, which resolves to `src/*`.

# TypeScript

- Maintain strict typing. Avoid `any` unless there is a justified reason.
- Prefer explicit domain types for meaningful data structures.
- Do not suppress TypeScript errors or relax compiler settings simply to make checks pass.
- The layout uses generated `LayoutProps<"/">`. Run `npm run typecheck`, which generates Next.js route types before `tsc --noEmit`; do not manually edit generated types.

# Styling and UI

- Use the existing Tailwind v4 setup: `src/app/globals.css` imports `tailwindcss` and is imported by the root layout. Follow v4's CSS-first configuration when extending the theme.
- Responsive design and accessibility are required, including semantic markup, keyboard access, visible focus, and sufficient contrast.
- Prefer reusable design primitives and consistent spacing and typography. Avoid generic template-looking UI.
- Introduce a component library only when it provides a clear benefit and the user approves it.

# Dependencies

- Reuse existing capabilities before adding dependencies; do not add packages unnecessarily.
- Ask before introducing a major framework, UI library, state-management library, animation library, CMS, database, or other architectural dependency.
- Keep `package.json` and `package-lock.json` in sync for approved dependency changes.

# Quality

- After meaningful implementation changes, run the relevant `npm run lint`, `npm run typecheck`, and `npm run build` checks. A build does not replace the explicit type check.
- For UI work, also verify the result in the browser when practical, including responsive and keyboard behavior.
- Fix issues caused by changes rather than hiding or suppressing them. Report actual check results and any checks that could not run.

# Scope

- Make focused changes, avoid unrelated refactors, and preserve existing conventions unless there is a clear reason to improve them.

# Git

- Do not commit or push unless explicitly asked.
- Do not force-push.
- Do not merge branches or pull requests unless explicitly asked.
- Review the diff and Git status before finishing; leave unrelated user changes untouched.
