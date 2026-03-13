# AGENTS.md

## Cursor Cloud specific instructions

This is a **Scalar Docs Starter Kit** — a documentation-only repository with no build system, no `package.json`, and no traditional dependencies. All tooling is provided via `npx @scalar/cli`.

### Requirements

- **Node.js v24+** is required. The `@scalar/cli` latest version (1.7.x+) requires Node 24; older Node versions fall back to an older CLI that fails to render docs properly.

### Key commands

| Task | Command |
|---|---|
| Validate config | `npx @scalar/cli@latest project check-config` |
| Preview docs (dev server) | `npx @scalar/cli@latest project preview` |
| Preview on specific port | `npx @scalar/cli@latest project preview --port 3000` |

### Gotchas

- The first run of `npx @scalar/cli@latest project preview` downloads a "docs isolate" (~30-60s). Subsequent runs are faster since this is cached.
- The preview server may auto-select a different port if the requested one is in use. Check the server output for the actual URL.
- There is no lint or test suite in this repo. The only validation is `npx @scalar/cli@latest project check-config` which validates `scalar.config.json`.
- The CI workflow (`.github/workflows/validate-scalar-configuration.yml`) runs `npx @scalar/cli@latest project check-config` on pushes/PRs that touch `scalar.config.json` or `docs/**`.
