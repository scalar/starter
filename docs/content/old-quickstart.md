# Quickstart

Get your documentation site up in a flash.

## Scalar CLI

You can run the Scalar CLI by either installing it, or executing it via `npx`.
<scalar-steps>
<scalar-step title="Install the CLI" open="false">
```sh
npm -g install @scalar/cli
```
</scalar-step>
<scalar-step title="Or, run without install">
If you prefer not to install the cli, just prefix all commands with `npx @scalar/cli` instead of `scalar`.
</scalar-step>
</scalar-steps>

## Create Project

No `scalar config` file? No problem!

<scalar-steps>
<scalar-step title="Add a config file">
Create a `scalar.config.json` file with the following content:
```json
// scalar.config.json
{
  "$schema": "https://cdn.scalar.com/schema/scalar-config-next.json",
  "scalar": "2.0.0",
  "info": {
    "title": "My Docs",
    "description": "My documentation site"
  },
  "navigation": {
    "routes": {
      "/": {
        "type": "group",
        "title": "Getting Started",
        "children": {}
      }
    }
  }
}
```
</scalar-step>
<scalar-step title="Start the local preview server">
```sh
npx @scalar/cli project preview
```
</scalar-step>
</scalar-steps>

Your (currently empty) documentation site should now be up and running!

## Publish

<scalar-steps>

<scalar-step title="Authorization">
Before we can publish we need to authorize!

```sh
npx @scalar/cli auth login
```

After logging in we can create a project. You'll need to pass a `name` and `slug`.

```sh
npx @scalar/cli project create \
  --name "My Documentation" \
  --slug my-docs
```
</scalar-step>

<scalar-step title="Publish your site">
```sh
npx @scalar/cli project publish
```

</scalar-step>
</scalar-steps>

That's it! You can now visit your published site at `<my-docs>.apidocumentation.com`

:::scalar-callout{type="info"}

**Our phone lines are open, 24/7.**

:scalar-icon{src="discord-logo"} Chat with us on [Discord](https://discord.gg/scalar)

:scalar-icon{src="phone"} Set up a [call](https://cal.com/scalar/30min)

:scalar-icon{src="star"} Star us on [GitHub](https://github.com/scalar/scalar)
:::
