TOPICS: visibility property

# CSS 显示或隐藏元素属性: `visibility`

CSS属性 **`visibility`** **显示**或**隐藏**元素而**不更改文档的布局**。该属性还可以隐藏[*`<table>`*](/zh-hans/webfrontend/<table>)中的**行**或**列**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`visible`** | 元素正常显示 |
| **`hidden`** | **隐藏元素**，但是其他元素的布局不改变，相当于此元素变成透明。要注意若将其子元素设为 `visibility: visible`，则该子元素依然可见 |
| **`collapse`** | 隐藏表格的**行**或**列**，**并且不占用任何空间**（与将 *`display: none`* 用于表格的行/列上的效果相当）。但是，如果将[*`<table>`*](/zh-hans/webfrontend/<table>)设置一个高度，**仍然会占何空间** |

## 示例

```css
h1.visible { visibility: visible }
h1.hidden { visibility: hidden }

/* 删除表格行和列的示例 */
table {
  height: 300px;
}

table, th, td {
  border: 1px solid black;
}

tr.collapse {
  visibility: collapse;
}
```

```html
<h1 class="visible">This is a visible heading</h1>
<h1 class="hidden">This is an invisible heading</h1>
<p>Notice that the invisible heading still takes up space.</p>

<!-- 删除表格行和列的示例 -->
<table>
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
  </tr>
  <tr>
    <td>Peter</td>
    <td>Griffin</td>
  </tr>
  <tr class="collapse">
    <td>Lois</td>
    <td>Griffin</td>
  </tr>
  <tr>
    <td>Peter</td>
    <td>Griffin</td>
  </tr>
  <tr>
    <td>Peter</td>
    <td>Griffin</td>
  </tr>
</table>
```
