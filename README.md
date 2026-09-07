# Luxury Travel Agency

Minimal Next.js scaffold using TypeScript, the App Router, Tailwind CSS, and ESLint. Website implementation has not started.

## Requirements

- Node.js 20.9 or newer (setup verified with Node.js 24.13.0)
- npm

## Development

```bash
npm ci
npm run dev
```

Open [localhost:3000](http://localhost:3000). The initial page is `src/app/page.tsx`, the root layout is `src/app/layout.tsx`, and global styles are in `src/app/globals.css`. The `@/*` import alias resolves to `src/*`.

## Verification

```bash
npm run lint
npm run typecheck
npm run build
```

The type check generates Next.js route types before running TypeScript, so it also works on a fresh checkout.

## Production

```bash
npm run build
npm start
```

See the [Next.js documentation](https://nextjs.org/docs) for framework and deployment guidance.
