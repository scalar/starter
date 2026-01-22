# Project Settings

Your Scalar project is highly customizable by updating your `scalar.config.json` file.

:::scalar-callout{type="info"}
Check the fully detailed [JSON Schema](https://cdn.scalar.com/schema/scalar-config-next.json) for all possible options.
:::

## Properties

### $schema
`string` _optional_

The JSON schema URL for validation and autocompletion.

:::scalar-detail{title="Example"} 
```
"$schema": "https://cdn.scalar.com/schema/scalar-config-next.json"
```
:::

### scalar
`string` _required_

The Scalar config version.

:::scalar-detail{title="Example"} 
```
"scalar": "2.0.0"
```
:::

### info
`object` _required_

Metadata about your documentation site.

:::scalar-detail{title="Example"} 
```
"info": {
  "title": "My Docs",
  "description": "My documentation site"
}
```
:::

### navigation
`object` _required_

The navigation structure for your documentation site, containing routes that define pages and groups.

::::scalar-detail{title="Example"}
This yields a navigation with a group containing pages and nested groups.

```
"navigation": {
  "routes": {
    "/": {
      "type": "group",
      "title": "Getting Started",
      "children": {
        "/": {
          "type": "page",
          "filepath": "docs/content/quickstart.md",
          "title": "Quickstart",
          "icon": "phosphor/regular/compass"
        },
        "/customizing": {
          "type": "group",
          "title": "Customizing Your Setup",
          "mode": "nested",
          "icon": "phosphor/regular/gear",
          "children": {
            "project-settings": {
              "type": "page",
              "filepath": "docs/content/project-settings.md",
              "title": "Project Settings"
            }
          }
        },
        "/api-reference": {
          "type": "openapi",
          "filepath": "docs/api-reference/openapi.yaml",
          "title": "API Reference",
          "icon": "phosphor/regular/notebook",
          "mode": "nested"
        }
      }
    }
  }
}
```

:::scalar-callout{type=warning}
Routes are recursively defined: a group can contain nested groups with further children.
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
