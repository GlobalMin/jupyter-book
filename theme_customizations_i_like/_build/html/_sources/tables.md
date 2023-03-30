# Tables

## Markdown syntax

Tables can be written using the standard [Github Flavoured Markdown syntax](https://github.github.com/gfm/#tables-extension-):

| foo | bar |
| --- | --- |
| baz | bim |

:::

Cells in a column can be aligned using the `:` character:

| left | center | right |
| :--- | :----: | ----: |
| a    |   b    |     c |

:::

:::{admonition} Aligning cells in Sphinx HTML themes
:class: tip dropdown

Text is aligned by assigning `text-left`, `text-center`, or `text-right` to the cell.
It is then necessary for the theme you are using to include the appropriate css styling.

:::

## Table with captions

The `table` directive can be used to create a table with a caption:

:::{table} Table caption
:widths: auto
:align: center

| foo | bar |
| --- | --- |
| baz | bim |

:::

The following options are recognized:

:::{admonition} List table options
:class: hint

`align` : "left", "center", or "right"
: The horizontal alignment of the table.

`width` : a length or percentage
: Sets the width of the table to the specified length or percentage of the line width.
: If omitted, the renderer determines the width of the table based on its contents or the column widths.

`widths` : "auto", "grid", or a list of integers
: Explicitly set column widths. Specifies relative widths if used with the width option.
: "auto" delegates the determination of column widths to the backend renderer.
: "grid" determines column widths from the widths of the input columns (in characters).

:::
