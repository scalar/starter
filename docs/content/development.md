# Development

## Local Preview

Run `@scalar/cli project preview` to start a local development server with live reload.

## Port

The default port is `7970`. Override with `--port`:

```sh
npx @scalar/cli project preview --port 3000
```

If the port is in use, the CLI selects another automatically.

## Configuration

The CLI looks for `scalar.config.json` in the current directory by default. To use a different config:

```sh
npx @scalar/cli project preview my-scalar-config.json
npx @scalar/cli project preview ../some-other-directory/scalar.config.json
```
