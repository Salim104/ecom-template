# Current Feature

<!-- Replace this content at the start of each new feature -->
<!-- Copy the relevant spec from context/features/ into here -->

---

## Feature Name

<!-- Short name e.g. "Product Listing Page" -->

## Description

<!-- What is being built and why -->

## Design Reference

- **Pencil file:** `designs/[feature-name].pen`
- **Canvas status:** Open and active via MCP
- **Key design decisions:**
  - <!-- e.g. 3-column grid on desktop, single column mobile -->
  - <!-- e.g. Filter sidebar on left -->
  - <!-- e.g. Shadcn Card for each product -->

## Requirements

<!-- Functional requirements — what must this feature do -->

- [ ] 
- [ ] 
- [ ] 

## Technical Notes

<!-- Stack-specific implementation details -->

### Convex
- Query: `api.products.` <!-- which query to use -->
- Mutation: `api.` <!-- if writing data -->
- Schema fields needed: <!-- list any new fields -->

### Clerk
- Auth required: Yes / No
- Protected: <!-- which parts require login -->

### Cloudinary
- Images needed: Yes / No
- Upload widget: Yes / No

### Resend
- Email trigger: Yes / No
- Template: <!-- which email template -->

### Components needed
- <!-- list new components to create -->
- <!-- list existing components to reuse -->

## Acceptance Criteria

<!-- How do we know this feature is done -->

- [ ] Works on mobile (375px)
- [ ] Works on desktop (1280px)
- [ ] Loading states handled
- [ ] Empty states handled
- [ ] Error states handled
- [ ] `npm run build` passes
- [ ] Playwright test passes (if critical flow)

## Status

`Not Started` / `In Progress` / `Blocked` / `Complete`

**Branch:** `feature/`

**Blocked by:** <!-- if blocked, explain why -->

## Notes

<!-- Any extra context, decisions made, things to watch out for -->

## History

<!-- Claude updates this as work progresses -->

<!-- Example format:
- [date] Created branch feature/product-listing
- [date] Built ProductGrid component with Convex useQuery
- [date] Added filter sidebar — category and price range
- [date] Build passing, merged to main
-->
