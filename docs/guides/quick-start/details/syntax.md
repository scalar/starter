# Extended Markdown Syntax

Scalar supports Github Flavored Markdown (GFM), as well as custom extensions written in either _directive_ or _custom-html_ syntax.

For the most update-to-date documentation on our extended syntax see the `Scalar Docs` guides at `guides.scalar.com`

::scalar-button{title="View Documentation" href="https://guides.scalar.com/scalar/scalar-docs/components"}

## Directive Syntax
The directive syntax uses colons to denote a feature from plaintext, for example `:scalar-icon{src="acorn"}`

A directive receives properties through `{prop="value here" other="more values"}` structures. This is optional.

:::scalar-callout
There are 2 versions: `inline`, and `block`.
:::

### Inline
The inline syntax allows you to place the directive anywhere within the current line.
When using this syntax you only need a single `:` before the name, and _you should not have a closing `:`.
If you need to pass content it must go after the name, before the parameters, in square brackets.

:::scalar-detail{title=Example}
```
_with optional content_
:scalar-button[Optional Content]{title="View Documentation" href="https://docs.scalar.com"}

_with only parameters_
:scalar-button{title="View Documentation" href="https://docs.scalar.com"}
```
:::

### Block
The `block` syntax must:
- start with 3 or more `:`
- end with the same amount of `:`
- begin at the start of a line
- end at the start of another line

Content written between the starting-line and ending-line will be parsed and inserted
into the directive (_the detail dropdowns on this page are done with `block directive` syntax_).

::::scalar-detail{title=Example}
````
_a valid block directive_
:::scalar-detail{title=Example}
This would be inside the detail itself
:::

_an invalid block directive, does not end with ::: at the start of a line
:::scalar-detail{title=Example}
This would be inside the detail itself
this conent makes the block invalid:::
````
::::

## Custom Html Syntax
The custom html syntax look like html tags, prepended with `scalar-`. All tags must be closed with a matching tag,
even if there is no content between them.

<scalar-detail title="Example">
```
<scalar-button
  title="View Documentation"
  href="https://docs.scalar.com">
</scalar-button>


<scalar-detail title="More Info">
Here is some additional content.
</scalar-detail>
```
</scalar-detail>


## Available Features
In addition to all standard markdown features and GFM features, Scalar also supports:

<ul>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/buttons" target="_blank" rel="noopener noreferrer">Buttons</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/callouts" target="_blank" rel="noopener noreferrer">Callouts</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/card" target="_blank" rel="noopener noreferrer">Card</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/code-blocks" target="_blank" rel="noopener noreferrer">Code Blocks</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/details" target="_blank" rel="noopener noreferrer">Details</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/embeds" target="_blank" rel="noopener noreferrer">Embeds</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/images" target="_blank" rel="noopener noreferrer">Images</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/math" target="_blank" rel="noopener noreferrer">Math</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/page-link" target="_blank" rel="noopener noreferrer">Page Link</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/row" target="_blank" rel="noopener noreferrer">Row</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/steps" target="_blank" rel="noopener noreferrer">Steps</a></li>
  <li><a href="https://guides.scalar.com/scalar/scalar-docs/components/tabs" target="_blank" rel="noopener noreferrer">Tabs</a></li>
</ul>
