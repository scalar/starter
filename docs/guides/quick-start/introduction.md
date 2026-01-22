# Quickstart

This is the Scalar Docs Starter Kit — a ready-to-use template for building beautiful documentation. Fork it, clone it, and make it your own. Everything here is meant to be modified, extended, or replaced to fit your project.

## 1. Preview Your Docs

Run a local development server to see your changes in real-time:

```bash
npx @scalar/cli project preview
```

This starts a live preview at `http://localhost:7971` where every edit you make is instantly visible.

## 2. Include OpenAPI Documents

Drop your OpenAPI files into `docs/api-reference/`, and add them to `@scalar.config.json` to have them automatically become interactive API references.

The starter kit includes an example OpenAPI document to show you how it works.

## 3. Customize Everything

Make it yours with themes, custom CSS, and MDX. Configure your documentation structure, navigation, and styling through `scalar.config.json`.

## Stuck?

Check whether your `scalar.config.json` is valid:

```bash
npx @scalar/cli project check-config
```

And [reach out to our support team](mailto:support@scalar.com), we're here to help.
