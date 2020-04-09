TOPICS: border-collapse property
        border-spacing property
        caption-side property
        table-layout property
        empty-cells property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 表格属性

使用 CSS 表格属性可以使 HTML 表格更美观

## CSS 属性 `border-collapse`

**`border-collapse`** CSS 属性是用来决定**表格的边框**是**分开**的还是**合并的**。在分隔模式下，相邻的单元格都拥有独立的边框。在合并模式下，相邻单元格共享边框。

分隔模式是HTML表格的传统模式。相邻单元格都拥有不同的边框。边框之间的距离是通过CSS属性 *`border-spacing`* 来确定的。

| 属性值 | 说明 |
| :--- | :--- |
| **`separate`** | 关键字，用于使用分隔的边框来绘制表格，是默认值 |
| **`collapse`** | 关键字，用于使用合并的边框来绘制表格 |

## CSS 属性: `border-spacing`

**`border-spacing`** 属性指定**相邻单元格边框之间的距离**（只适用于 边框分离模式 ）。相当于 HTML 中的 *`cellspacing`* 属性，但是第二个可选的值可以用来设置不同于水平间距的垂直间距。

`border-spacing` 值也适用于表格的外层边框上，即表格的边框和第一行的、第一列的、最后一行的、最后一列的单元格之间的间距是由表格相应的（水平的或垂直的） 边框间距（`border-spacing`）和相应的（上，右，下或左）内边距之和。

该属性只适用于 *`border-collapse`* 值是 *`separate`* 的时候。

| 属性值 | 说明 |
| :--- | :--- |
| **length** | 描述单元格之间的水平和垂直距离的一个 length 值。它只在单值语法下使用 |
| **`horizontal`** | 描述相邻两列的单元格之间的水平距离的一个 length 值。它只在双值语法下使用 |
| **`vertical`** | 描述相邻两行的单元格之间的垂直距离的一个 length 值。它只在双值语法下使用 |

## CSS 属性: `caption-side`

CSS 中 **`caption-side`** 属性会**将表格的标题 [*`<caption>`*](/zh-hans/webfrontend/<caption>) 放到规定的位置**。

| 属性值 | 说明 |
| :--- | :--- |
| **`top`** | 默认值。把表格标题定位在表格之上 |
| **`bottom`** | 把表格标题定位在表格之下 |

## CSS 属性: `table-layout`

**`table-layout`** CSS属性定义了**用于布局表格单元格**，**行**和**列的算法**。

| 属性值 | 描述 |
| :--- | :--- |
| **`automatic`** | 默认。列宽度由单元格内容设定 |
| **`fixed`** | 列宽由表格宽度和列宽度设定 |

## CSS 属性: `empty-cells`

CSS中 **`empty-cells`** 属性定义了用户端应该怎么来渲染表格 [*`<table>`*](/zh-hans/webfrontend/<table>) 中没有可见内容的单元格的边框和背景。

只有当 *`border-collapse`* 属性值是 *`separate`* 时，才会生效。

| 属性值 | 说明 |
| :--- | :--- |
| **`show`** | 边框和背景**正常渲染**。与普通元素一样 |
| **`hide`** | 边框和背景**被隐藏** |

## 示例

```css
table {
  width: 100%;
  height: 300px;
  border-collapse: separate; /* 分割表格单元格 */
  border-spacing: 10px; /* 定义单元格于单元格为10px */
  caption-side: bottom; /* 定义表格标题至于表格底部  */
  empty-cells: show; /* 定义表格没有内容的单元格显示边框或背景颜色 */
  table-layout: fixed; /* 定义表格行和列平分表格的宽度和高度 */
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
