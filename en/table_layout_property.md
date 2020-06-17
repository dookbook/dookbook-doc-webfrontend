TOPICS: table-layout property

# CSS 属性: `table-layout`

CSS **`table-layout`** 属性定义了**用于布局表格单元格**，**行**和**列的算法**。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`automatic`** | 默认。列宽度由**单元格内容设定**。|
| **`fixed`** | 列宽由**表格宽度**和**列宽度设定**。|
| **`inherit`** | 规定应该从父元素继承 **`table-layout`** 属性的值。|

## 示例

```css
table.ex1 {table-layout:auto;}
table.ex2 {table-layout:fixed;}
```

```html
<table class="ex1" border="1" width="100%">
  <tr>
    <td width="5%">1000000000000000000000000000</td>
    <td width="95%">10000000</td>
  </tr>
</table>
<br>

<table class="ex2" border="1" width="100%">
  <tr>
    <td width="5%">1000000000000000000000000000</td>
    <td width="95%">10000000</td>
  </tr>
</table>
```
