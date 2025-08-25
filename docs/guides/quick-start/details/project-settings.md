# Project Settings

Your Scalar project is highly customizable by updating your `scalar.config.json5` file.

:::scalar-callout{type="info"}
Check the fully detailed [JSON Schema](https://cdn.scalar.com/schema/scalar-config.json) for all possible options.
:::

## Properties

### subdomain
`string` _required_

The subdomain for your Scalar docs site.

:::scalar-detail{title="Example"} 
```
"subdomain": "starter-kit.apidocumentation.com"
```
:::

### references
`Array<object>` _optional_

A list of API references.

These will be used to auto-generate API clients on your site.

:::scalar-detail{title="Example"} 
```
"references": [
  {
    "name": "Planets",
    "path": "./docs/api-reference/open-api-spec.yaml"
  }
],
```
:::

### guides
`Array<object>` _optional_

An array of guide entries. Each entry will become its own tab, with a sidebar navigation of the entries
provided in its `sidebar` array.

::::scalar-detail{title="Example"}
This yields two guides, `First Guide` and `Second Guide`.

The `First Guide` will have two sidebar entries (a folder and a file), and `Second Guide` will have only one.
```
  "guides": [
    {
      "name": "First Guide",
      "sidebar": [
        {
          "name": "Folder Example",
          "type": "folder",
          "children": [
            { "path": "path/to/file-1.md", "type": "page", name: "Folder: File One" },
          ]
        },
        { "path": "path/to/file-2.md", "type": "page", name: "File Two" },
      ]
    },
    {
      "name": "Second Guide",
      "sidebar": [
        { "path": "path/to/file-3.md", "type": "page", name: "File Three" },
      ]
    },
  ],
```

:::scalar-callout{type=warning}
The guides are recursively defined: a sidebar entry may have it's own `sidebar` with further sidebar entries.
:::
::::

### siteConfig
`object` _optional_

An object storing meta-data for your site, including theme, logos and more.

:::scalar-detail{title="Example"} 
```
"siteConfig": {
  "theme": "purple",
  "logo": {
    "darkMode": "https://scalar.com/logo-light.svg",
    "lightMode": "https://scalar.com/logo-dark.svg"
  },
}
```
:::
