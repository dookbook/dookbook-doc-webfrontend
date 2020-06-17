TOPICS: empty-cells property

# CSS Property: `empty-cells`

The CSS **`empty-cells`** property defines how the client should render the border and background
of cells in the table [*`<table>`*](/en/webfrontend/<table>) that have no visible content.

Only when [**`border-collapse`**](/en/webfrontend/border-collapse_property) property value is
**`separate`**, it will take effect.

## Property value

| Property value | Description |
| :--- | :--- |
| **`show`** | Border and background **normal rendering**. Same as ordinary elements. |
| **`hide`** | The border and background are **hidden**. |

## Examples

```html
<table class="table_1">
  <tr>
    <td>Moe</td>
    <td>Larry</td>
  </tr>
  <tr>
    <td>Curly</td>
    <td></td>
  </tr>
</table>
<br>
<table class="table_2">
  <tr>
    <td>Moe</td>
    <td>Larry</td>
  </tr>
  <tr>
    <td>Curly</td>
    <td></td>
  </tr>
</table>
```

```css
.table_1 {
  empty-cells: show;
}

.table_2 {
  empty-cells: hide;
}

td,
th {
  border-collapse: separate;
  border: 1px solid gray;
  padding: 0.5rem;
}
```
