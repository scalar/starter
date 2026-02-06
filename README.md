# Scalar Docs Starter Kit

[![Contributors](https://img.shields.io/github/contributors/scalar/starter)](https://github.com/scalar/starter/graphs/contributors)
[![GitHub License](https://img.shields.io/github/license/scalar/starter)](https://github.com/scalar/starter/blob/main/LICENSE)
[![Twitter](https://img.shields.io/twitter/follow/scalar)](https://x.com/scalar)
[![Discord](https://img.shields.io/discord/1135330207960678410?style=flat&color=5865F2)](https://discord.gg/scalar)

Welcome to the Scalar Docs Starter Kit! Deploy Markdown and OpenAPI documents from GitHub.

## Preview

Use the [Scalar CLI](https://scalar.com/tools/cli/getting-started) to render a live preview of your project locally:

```bash
npx @scalar/cli project preview
```

This will start a local development server where you can view and interact with your documentation in real-time.

## Validate Configuration

Ensure your project configuration is properly set up by running the configuration validation command:

```bash
npx @scalar/cli project check-config
```

This will verify that your `scalar.config.json` file contains valid settings and help identify any configuration issues.

### GitHub Action

This repository includes a GitHub Action workflow that automatically validates the configuration on every push and pull request. See [`.github/workflows/validate-scalar-configuration.yml`](./.github/workflows/validate-scalar-configuration.yml).

## Project Structure

```
starter/
├── docs/
│   ├── api-reference/      # OpenAPI documents
│   └── guides/             # Free-form text
├── scalar.config.json      # Configuration
```

## Configuration

All project configuration is managed through the [`scalar.config.json`](./scalar.config.json) file. This file controls:

- Documentation structure and navigation
- OpenAPI document sources
- Theme and styling options
- Build and deployment settings

## Documentation

For comprehensive guides on using Scalar Docs and setting up GitHub Sync, [read the full documentation](https://guides.scalar.com/scalar/scalar-docs/github-sync).
