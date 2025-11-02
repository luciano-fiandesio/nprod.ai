# Repository Guidelines

## Project Structure & Module Organization
- `src/pages/` holds route-level `.astro` files; landing content lives in `src/pages/index.astro`.
- `src/layouts/` provides shared shells; `BaseLayout.astro` wires global styles and fonts.
- `src/components/ui/` contains shadcn-inspired primitives (`button.astro`, `input.astro`, etc.) that should remain logic-light and reusable.
- `src/lib/` is reserved for small utilities such as `utils.ts` (`cn` helper). Add shared logic here before creating new helpers elsewhere.
- `src/styles/global.css` configures Tailwind layers, theme tokens, and background treatments. Update tokens here rather than scattering hard-coded colors.
- Public, static assets belong in `public/`; build artifacts appear in `dist/` after running the build.

## Build, Test, and Development Commands
- `npm run dev` starts the Astro dev server (default port `4321`) with live reload.
- `npm run build` produces the static site in `dist/`. Run before shipping or submitting PRs.
- `npm run preview` serves the `dist/` output for final verification.

## Coding Style & Naming Conventions
- Use two-space indentation for Astro, JSON, and CSS files; respect Prettier defaults when available.
- Favor PascalCase for component filenames (`Button.astro`) and `kebab-case` for directories.
- Keep Tailwind classes declarative and grouped by role (layout → spacing → color). Reach for CSS variables defined in `global.css` before adding new colors.
- Prefer top-level `const` declarations with descriptive names (e.g., `CONTACT_EMAIL`) and colocate component-specific scripts inside their `.astro` files when feasible.

## Testing Guidelines
- No automated test suite yet. At minimum, run `npm run build` before PRs to ensure Astro succeeds.
- When adding functionality that can be unit tested, introduce the relevant framework (e.g., Vitest) under `tests/` and document the command here.
- For modal or form changes, confirm keyboard accessibility (Tab, Escape) manually in `npm run dev`.

## Commit & Pull Request Guidelines
- History is greenfield; follow Conventional Commit style (`feat:`, `fix:`, `chore:`) for clarity.
- Scope commits narrowly and mention touched paths in the body when helpful (`src/components/ui/button.astro`).
- PRs should include: summary of changes, manual verification notes (commands run, browsers checked), and screenshots or recordings for UI updates.
- Link to any tracking tickets or discussions so future contributors understand context.
