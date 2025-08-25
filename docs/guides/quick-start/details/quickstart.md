# Quickstart
Get your documentation site up in a flash.

## Local Setup
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

## Start a Project
No `scalar config` file? No problem!

<scalar-steps>
<scalar-step title="Add a config file">
Fill this in what your prefered subdomain.
```sh
cat >> scalar.config.json5 <<'EOF'
{
  "subdomain": "your-prefered-subdomain.apidocumentation.com",
  "references": [],
  "guides": []
}
EOF
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
<scalar-step title="Add some docs to your config">
Add an entry to your `guides` section of the `scalar.config.json5`.
This can be as simple as:

```json
{
  "name": "Guide Name",
  "sidebar":[
    {
      name: "Guide entry name",
      type: "page",
      path: "relative/path/from/scalar-config/to/file.md"
    },
  ]
},
```
</scalar-step>

<scalar-step title="Authorization">
Before we can publish we need to authorize!
:::scalar-callout{type=warning}
This command will redirect you to your browser to log in
:::
```sh
npx @scalar/cli auth login
```
After logging in we can create a project. You'll need to pass a `name` and `slug`.

```sh
npx @scalar/cli project create --name your-preferred-project-name \
--slug costasiella-kuroshimae
```
</scalar-step>

<scalar-step title="Publish your site">
```sh
npx @scalar/cli project publish
```

</scalar-step>
</scalar-steps>

That's it! You can now visit your published site at `<your-prefered-subdomain>.apidocumentation.com`

:::scalar-callout{type="info"}
**Our phone lines are open, 24/7.**

:scalar-icon{src="discord-logo"} Chat with us on [Discord](https://discord.gg/scalar)

:scalar-icon{src="phone"} Set up a [call](https://cal.com/scalar/30min)

:scalar-icon{src="star"} Star us on [GitHub](https://github.com/scalar/scalar)
:::
