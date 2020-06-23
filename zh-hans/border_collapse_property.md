TOPICS: border-collapse property

# CSS 属性: `border-collapse`

CSS **`border-collapse`** 属性是用来决定**表格的边框**是**分开**的还是**合并的**。在分隔模式下，相邻的单元格都拥有独立的边框。在合并模式下，相邻单元格共享边框。

分隔模式是HTML表格的传统模式。相邻单元格都拥有不同的边框。边框之间的距离是通过CSS属性
[*`border-spacing`*](/zh-hans/webfrontend/border-spacing_property) 来确定的。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`separate`** | 关键字，用于使用**分隔的边框**来绘制表格，是默认值。 |
| **`collapse`** | 关键字，用于使用**合并的边框**来绘制表格。 |

## 示例

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
