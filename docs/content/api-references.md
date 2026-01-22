# API References

Scalar supports three ways to add OpenAPI documents to your documentation: using a local file, the [Scalar Registry](https://scalar.com/products/registry/getting-started) or a remote URL.

## Using a Local File

Reference an OpenAPI file stored in your GitHub repository by specifying a relative path from your configuration root:

```json
{
  "$schema": "https://cdn.scalar.com/schema/scalar-config-next.json",
  "scalar": "2.0.0",
  "navigation": {
    "routes": {
      "/api": {
        "type": "openapi",
        "title": "My API",
        "filepath": "docs/api-reference/openapi.yaml",
        "icon": "phosphor/regular/plug"
      }
    }
  }
}
```

## Using the Scalar Registry

Upload your OpenAPI document to the [Scalar Registry](https://scalar.com/products/registry/getting-started):

```bash
scalar auth login
scalar registry publish ./openapi.yaml --namespace my-organization --slug my-api
```

And reference it using a namespace, slug, and version (optional):

```json
{
  "$schema": "https://cdn.scalar.com/schema/scalar-config-next.json",
  "scalar": "2.0.0",
  "navigation": {
    "routes": {
      "/api": {
        "type": "openapi",
        "title": "My API",
        "namespace": "my-organization",
        "slug": "my-api",
        // "version": "1.0.0",
        "icon": "phosphor/regular/plug"
      }
    }
  }
}
```

## Using a URL

Fetch an OpenAPI document from a remote URL. The document is fetched on each page load, keeping your documentation in sync with your live API:

```json
{
  "$schema": "https://cdn.scalar.com/schema/scalar-config-next.json",
  "scalar": "2.0.0",
  "navigation": {
    "routes": {
      "/api": {
        "type": "openapi",
        "title": "My API",
        "url": "https://api.example.com/openapi.json",
        "icon": "phosphor/regular/plug"
      }
    }
  }
}
```

## Configuration

All OpenAPI entries support the following options:

| Option        | Type                                 | Description                                                 |
| ------------- | ------------------------------------ | ----------------------------------------------------------- |
| `type`        | `"openapi"`                          | Required: Identifies this as an OpenAPI document.           |
| `title`       | `string`                             | Title shown in navigation links.                            |
| `description` | `string`                             | Description for the API reference.                          |
| `icon`        | `string`                             | Icon to display in the sidebar.                             |
| `mode`        | `"nested"` \| `"flat"` \| `"folder"` | How to display the API in the sidebar. Default: `"folder"`. |
| `config`      | `object`                             | Scalar API Reference configuration                          |

### Display Modes

- `folder` (default): Shows a single level of links with a folder icon
- `flat` Shows a single level of links with a section title
- `nested` Shows a sub-sidebar with breadcrumbs for deep navigation

