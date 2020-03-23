TOPICS: caption-side property

# CSS 属性: `caption-side`

CSS 中 **`caption-side`** 属性会将表格的标题 [*`<caption>`*](/zh-hans/webfrontend/<caption>) 放到规定的位置。但是具体显示的位置与
表格的 *`writing-mode`* 属性值有关。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`top`** | 默认值。把表格标题定位在表格之上 |
| **`bottom`** | 把表格标题定位在表格之下 |

## 示例

```css
.top caption {
  caption-side: top;
}

.bottom caption {
  caption-side: bottom;
}

table {
  border: 1px solid red;
}

td {
  border: 1px solid blue;
}
```

```html
<table class="top">
  <caption>Caption ABOVE the table</caption>
  <tr>
    <td>Some data</td>
    <td>Some more data</td>
  </tr>
</table>

<br>

<table class="bottom">
  <caption>Caption BELOW the table</caption>
  <tr>
    <td>Some data</td>
    <td>Some more data</td>
  </tr>
</table>
```
