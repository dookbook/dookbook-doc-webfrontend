TOPICS: border-collapse property
        border-spacing property
        caption-side property
        table-layout property
        empty-cells property

# CSS Table Property

Use CSS table attributes to make HTML tables more beautiful

## CSS Property `border-collapse`

**`border-collapse`** The CSS property is used to determine whether **the border of the table** is
**divided** or **combined**. In split mode, adjacent cells have independent borders. In merge mode,
adjacent cells share a border.

Delimited mode is the traditional mode for HTML tables. Adjacent cells have different borders. The
distance between borders is determined by the CSS property *`border-spacing`*.

| Property Value | Description |
| :--- | :--- |
| **`separate`** | Keyword, used to draw tables with separated borders, is the default |
| **`collapse`** | Keyword for drawing tables with merged borders |

## CSS Property: `border-spacing`

**`border-spacing`** attribute specification **distance between borders of adjacent cells** (only
applicable for border separation mode). Equivalent to the *`cellspacing`* attribute in HTML, but the
second is optional The value of can be used to set a vertical spacing different from the horizontal spacing.

The `border-spacing` value also applies to the outer border of the table, that is, the space between
the border of the table and the cells in the first, first, last, and last columns is determined by
the table ( Sum of horizontal or vertical `border-spacing` and corresponding (`top`, `right`, `bottom`,
or `left`) padding.

This property only applies when *`border-collapse`* is *`separate`*.

| Property Value | Description |
| :--- | :--- |
| **length** | A length value describing the horizontal and vertical distance between the cells. It is only used under single value syntax |
| **`horizontal`** | A length value describing the horizontal distance between cells in two adjacent columns. It is used only in double-valued syntax |
| **`vertical`** | A length value describing the vertical distance between two adjacent rows of cells. It is used only in double-valued syntax |

## CSS Property: `caption-side`

The **`caption-side`** attribute in CSS will **put the table's title [*`<caption>`*](/en/webfrontend/<caption>)
to the required position**.

| Property Value | Description |
| :--- | :--- |
| **`top`** | Defaults. Position the table title above the table |
| **`bottom`** | Position the table title below the table |

## CSS Property: `table-layout`

**`table-layout`** The CSS property defines **an algorithm for layout table cells**, **rows**, and **columns**.

| Property Value | Description |
| :--- | :--- |
| **`automatic`** | Default. Column width is set by cell content |
| **`fixed`** | Column width is set by table width and column width |

## CSS Property: `empty-cells`

The **`empty-cells`** property in CSS defines how the client should render the table [*`<table>`*](/en/webfrontend/<table>)
for cells with no visible content Border and background.

Only takes effect when the *`border-collapse`* property value is *`separate`*.

| Property Value | Description |
| :--- | :--- |
| **`show`** | Border and background **normal rendering**. Same as ordinary element |
| **`hide`** | Border and background **hidden** |

## Example

```css
table {
  width: 100%;
  height: 300px;
  border-collapse: separate; /* Split table cells */
  border-spacing: 10px; /* Define cell to cell as 10px */
  caption-side: bottom; /* Define the table title as the bottom of the table  */
  empty-cells: show; /* Define the border or background color of cells with no content in the table */
  table-layout: fixed; /* Defines the width and height of the table by splitting the table rows and columns */
}

table, td, th {
  border: 1px solid black;
}
```

```html
<table>
  <caption>Caption the table</caption>
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
  </tr>
  <tr>
    <td>Peter</td>
    <td></td>
  </tr>
  <tr>
    <td>Lois</td>
    <td>Griffin</td>
  </tr>
</table>
```
