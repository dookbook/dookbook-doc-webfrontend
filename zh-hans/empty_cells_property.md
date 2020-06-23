TOPICS: empty-cells property

# CSS 属性: `empty-cells`

CSS **`empty-cells`** 属性定义了用户端应该怎么来渲染表格 [*`<table>`*](/zh-hans/webfrontend/<table>) 中没有可见内容的单元格的边框和背景。

只有当 [**`border-collapse`**](/zh-hans/webfrontend/border-collapse_property) 属性值是 **`separate`** 时，才会生效。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`show`** | 边框和背景**正常渲染**。与普通元素一样。|
| **`hide`** | 边框和背景**被隐藏**。|

## 示例

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
