TOPICS: column-fill property

# CSS Property: `column-fill`

The CSS **column-fill`** property controls how the **content of the element is balanced when sorted**.
This means that the content in all columns will have **the same height**, or only occupy the space
required by the content when using auto.

## Property value

| Property Value | Description |
| :--- | :--- |
| **`auto`** | The columns are filled in order. The content occupies only its **required space**, which may cause **some columns to remain blank**. |
| **`balance`** | The content is evenly distributed among the columns. In the context of fragmentation (such as paginated media), only the last fragment is balanced. Therefore, in paging media, only the last page is balanced. |
| **`balance-all`** | The content is evenly distributed among the columns. In a fragmented environment, such as paging media, all fragments are balanced. |

## Examples

```css
div {
  column-fill: balance;
  columns: 3 100px;
}
```

```html
<div>
  This is a bunch of text split into three columns
  using the CSS `columns` property. The text
  is equally distributed over the columns. The text
  is equally distributed over the columns. This is a bunch of text split into three columns
  using the CSS `columns` property. The text
  is equally distributed over the columns. The text
  is equally distributed over the columns.
</div>
```
