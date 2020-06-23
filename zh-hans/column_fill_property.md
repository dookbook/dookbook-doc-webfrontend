TOPICS: column-fill property

# CSS 属性: `column-fill`

CSS **`column-fill`** 属性控制了元素的**内容在分列时如何平衡**。这意味着所有列中的内容将具有**相同的高度**，或者在使用自动时仅占用内容所需的空间。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | 列按顺序填充。内容仅占用其**所需的空间**，这可能导致**某些列保持空白**。 |
| **`balance`** | 内容在各列之间平均分配。在片段化的上下文中（例如分页的媒体），只有最后一个片段是平衡的。因此，在分页媒体中，只有最后一页是平衡的。 |
| **`balance-all`** | 内容在各列之间平均分配。在碎片环境中，例如分页媒体，所有碎片都是平衡的。 |

## 示例

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
