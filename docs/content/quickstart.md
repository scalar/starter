# Quickstart

This is the Scalar Docs Starter Kit — a ready-to-use template for building beautiful documentation. Fork it, clone it, and make it your own. Everything here is meant to be modified, extended, or replaced to fit your project.

## 1. Preview Your Docs

Run a local development server to see your changes in real-time:

```bash
npx @scalar/cli project preview
```

This starts a live preview at `http://localhost:7971` where every edit you make is instantly visible.

Read more about [Development](development.md).

## 2. Include OpenAPI Documents

Drop your OpenAPI files into `docs/api-reference/`, and add them to `@scalar.config.json` to have them automatically become interactive API references.

The starter kit includes an example OpenAPI document to show you how it works.

Read more about [API References](api-references.md)

## 3. Customize Everything

Make it yours with themes, custom CSS, and MDX. Configure your documentation structure, navigation, and styling through `scalar.config.json`.

## 4. Publish Your Docs

First, authenticate with your Scalar account:

```bash
npx @scalar/cli auth login
```

Then publish your documentation:

```bash
npx @scalar/cli project publish
```

Your site will be available at `<your-slug>.apidocumentation.com`.

## Stuck?

Check whether your `scalar.config.json` is valid:

```bash
npx @scalar/cli project check-config
```

We're here to help:

- [Email support@scalar.com](mailto:support@scalar.com)
- [Chat with us on Discord](https://discord.gg/scalar)
- [Schedule a call](https://scalar.cal.com/scalar/chat-with-scalar)
