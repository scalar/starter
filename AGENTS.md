# AGENTS.md

## Repository purpose

The Scalar Docs Starter Kit — a configuration-only documentation project deployed via Scalar Docs GitHub Sync. There is no build system, no package.json, and no source code. All behavior is driven by `scalar.config.json` plus MDX files under `docs/content/` (the starter is MDX-by-default; `.md` still works) and OpenAPI documents under `docs/api-reference/`.

## Commands

All tooling runs through the Scalar CLI (`npx @scalar/cli`). There is no install step.

- `npx @scalar/cli project preview` — local dev server at `http://localhost:7971` with live reload
- `npx @scalar/cli project check-config` — validate `scalar.config.json` (this is what CI runs)
- `npx @scalar/cli project publish` — publish current local files to Scalar
- `npx @scalar/cli project upgrade` — migrate a Docs 1.0 config to 2.0

CI (`.github/workflows/validate-scalar-configuration.yml`) runs `check-config` on any push/PR that touches `scalar.config.json` or `docs/**`. Run `check-config` locally before committing changes to those paths.

## Architecture

Everything is orchestrated by `scalar.config.json`:

- `navigation.routes` is the single source of truth for sitemap and sidebar. Each key is a URL path; each value has a `type` of `page`, `openapi`, `group`, or `link`.
- `type: "page"` routes reference MDX via `filepath` (paths relative to repo root, e.g. `docs/content/quickstart.mdx`).
- `type: "openapi"` routes reference OpenAPI documents via `filepath`, or pull from the Scalar Registry (`namespace` + `slug`), or a remote `url`.
- `type: "group"` nests children and supports `mode`: `folder` (default), `flat`, or `nested`. `mode: "flat"` hoists children into the parent level without a collapsible wrapper — used in this repo for the Components, Layouts, and Examples sections.
- `siteConfig` controls branding, theme, custom domain/subdomain, `head` injection (scripts/styles/meta), and redirects.
- Page-level `layout` overrides (`toc`, `sidebar`, `header`, `tabs`, `pageTitle`, `pageActions`, `search`) live on the route entry, not in the MDX. See the Layouts gallery for live examples.

Adding a new page: create a `.mdx` file under `docs/content/`, then add a route entry in `scalar.config.json` pointing at it. `docs/content/components/` and `docs/content/layouts/` are galleries — don't add unrelated pages there; put new top-level content next to `quickstart.mdx`. Adding a new API reference: drop the OpenAPI document under `docs/api-reference/` and add a `type: "openapi"` route. The file path in `filepath` is relative to the repo root, not to `docs/`.

MDX components from `scalar-mdx-components` (`Callout`, `Button`, `Tabs`, `PageLink`, etc.) currently need explicit imports at the top of each page — the CLI's MDX pipeline does not auto-inject them. The Components gallery pages demonstrate the pattern.

The config schema is fetched from `https://registry.scalar.com/@scalar/schemas/config` (see `$schema`). `.vscode/settings.json` whitelists this host so VS Code autocompletes and validates the config inline — keep that whitelist when editing VS Code settings.

## Scalar config reference

`.agents/skills/scalar-docs-config-skill.mdc` is a comprehensive, up-to-date reference for every field in `scalar.config.json` (route types, header/sidebar/tabs, theming, domains, `head` injection, redirects, migration from 1.0). Consult it before editing the config rather than guessing field names — it is the authoritative local reference and more specific than the public docs.
