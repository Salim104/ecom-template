# CLAUDE.md

This file is auto-loaded by Claude Code at the start of every session.
Read this before doing anything else.

---

## Project Type
South African e-commerce store built for a single client.
Template-based agency model — storefront is customised per client,
admin dashboard and backend are reused across all projects.

## Tech Stack

### Frontend
- Next.js 15 App Router (TypeScript, strict mode)
- Shadcn/ui for all UI components
- Tailwind CSS v3 (NOT v4 — do not use CSS @theme config)
- next/image for ALL images — never use <img> tags

### Auth
- Clerk for all authentication
- Never roll custom auth
- Use currentUser() in server components
- Use useUser() / useAuth() in client components
- Protect routes via middleware.ts

### Database
- Convex for all data — NO Prisma, NO raw SQL
- useQuery() for reading data in client components
- useMutation() for writing data in client components
- Fetch directly in server components via fetchQuery()
- All schema defined in convex/schema.ts

### Image Uploads
- Cloudinary for ALL image storage and delivery
- Never store images in Convex file storage
- Use next-cloudinary (CldUploadWidget, CldImage)
- Upload preset configured per project in .env

### Email
- Resend for ALL transactional emails
- React Email for templates (in /emails folder)
- Trigger emails from Convex actions — NOT Next.js API routes
- Always send: order confirmation, welcome email

### Payments (coming soon)
- PayFast or Yoco (South African clients)
- Placeholder reserved — do not implement unless specified

### Deployment
- Vercel for hosting
- Environment variables managed in Vercel dashboard

---

## Route Groups

```
app/
├── (storefront)/     ← customer facing, customised per client
├── (admin)/          ← reused across all clients
├── (auth)/           ← Clerk auth pages
└── api/              ← webhooks only (Clerk, future payment gateway)
```

---

## Component Structure

```
components/
├── ui/               ← Shadcn primitives only, never modify
├── storefront/       ← customer facing components
├── admin/            ← admin dashboard components
└── shared/           ← used in both storefront and admin
```

---

## Convex Structure

```
convex/
├── schema.ts         ← all table definitions
├── products.ts       ← product queries + mutations
├── orders.ts         ← order queries + mutations
├── customers.ts      ← customer queries + mutations
└── emails.ts         ← Resend email actions
```

---

## Coding Rules — Always Follow These

### TypeScript
- Strict mode, no `any` types
- Define interfaces for all props and data models
- Use type inference where obvious

### React / Next.js
- Server components by default
- Only use `'use client'` when needed (hooks, interactivity)
- Never use useEffect for data fetching — use Convex useQuery
- Server Actions for simple form submissions
- API routes for webhooks only

### Shadcn/ui
- Use Shadcn components first before building custom
- All forms: Shadcn Form + react-hook-form + zod validation
- Toast notifications via Shadcn Sonner

### Styling
- Tailwind for all styling
- No inline styles ever
- Dark mode first approach
- Mobile responsive always — design mobile first

### Data & Errors
- Validate all inputs with Zod
- Return { success, data, error } from all actions
- User-friendly error messages via toast

---

## Naming Conventions

- Components: PascalCase (`ProductCard.tsx`)
- Files: Match component name or kebab-case
- Functions: camelCase
- Constants: SCREAMING_SNAKE_CASE
- Convex functions: camelCase, descriptive (`getProductsByCategory`)

---

## What NOT To Do

- Never use `<img>` — always `next/image` or `CldImage`
- Never use `useEffect` for data fetching
- Never write raw fetch calls to your own API for data — use Convex
- Never create `tailwind.config` with CSS @theme (that's v4)
- Never commit without permission
- Never delete files without asking
- Never add features not in the current spec
- Never auto-commit — always ask first
