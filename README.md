# Scalar Docs Starter Kit

Welcome to the Scalar Docs starter kit! This project provides you with a complete foundation to create beautiful, interactive API documentation using Scalar's powerful documentation platform.

## Preview

Use the Scalar CLI to render a live preview of your project locally:

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

## Project Structure

```
starter/
├── docs/
│   └── api-reference/      # OpenAPI documents
├── guides/                 # Free-form text
│   └── quick-start/        # Getting started materials
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
