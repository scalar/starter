# Development
Live preview your changes while your work on your docs site!

Run `@scalar/cli project preview` and a local preview of your site will be opened.

## Ports
By default the CLI uses `7970`. You can also pass a desired port via the `--port <number>` flag.

:::scalar-callout{type="info"}
If the port is in use, the cli will select another port automatically.
:::

## Passing the Config
The CLI will automatically look for your `scalar.config.json5` file in the current directory.

You can use a different name, or a config from a different directory, by passing it directly to the
preview command.

```sh
npx @scalar/cli project preview my-scalar-config.json5
npx @scalar/cli project preview ../other-dir/scalar.config.json5
```

## Automatic Opening
To prevent the CLI from automatically opening a new tab in your browser at the current port, you can pass the `--no-open`
flag.

:::scalar-callout{type="warning"}
The preview works best if only open in a single tab at a time.
:::

## Debugging

You can turn on the debugging logs with `--log-level debug`
