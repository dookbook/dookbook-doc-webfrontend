TOPICS: border-collapse property

# CSS Property: `border-collapse`

The CSS **`border-collapse`** property is used to determine **the border of the table** is **divided**
or **merged**. In split mode, adjacent cells have independent borders. In merge mode,
adjacent cells share a border.

Separated mode is the traditional mode of HTML tables. Adjacent cells all have different borders.
The distance between the borders is determined by the CSS property [*`border-spacing`*](/en/webfrontend/border-spacing_property).

## Property value

| Property value | Description |
| :--- | :--- |
| **`separate`** | The keyword, used to draw a table with **separated borders**, is the default. |
| **`collapse`** | Keywords for drawing tables using **merged borders**. |

## Examples

```css
table {
  border-collapse: collapse;
}

table, td, th {
  border: 1px solid black;
}
```

```html
<table>
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
  </tr>
  <tr>
    <td>Peter</td>
    <td>Griffin</td>
  </tr>
  <tr>
    <td>Lois</td>
    <td>Griffin</td>
  </tr>
</table>
```
