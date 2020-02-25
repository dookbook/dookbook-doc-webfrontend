TOPICS: writing-mode property
AUTHORS: virgil6; 1198994896@qq.com; github:virgil6

# CSS 属性: `writing-mode`

**`writing-mode`** 属性定义了**文本水平或垂直排布**以及在**块级元素中文本的行进方向**。为整个文档设置书时，应在根元素上设置它（对于 HTML 文档应该在
[`<html>`](/zh-hans/webfrontend/<html>) 元素上设置）

此属性指定块流动方向，即块级容器堆叠的方向，以及行内内容在块级容器中的流动方向。因此，它也确定块级内容的顺序。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`horizontal-tb`** | 水平方向自上而下的书写方式。即 `left-right-top-bottom` |
| **`vertical-rl`** | 垂直方向自右而左的书写方式。即 `top-bottom-right-left` |
| **`vertical-lr`** | 垂直方向内内容从上到下，水平方向从左到右 |

## 示例

```css
table, td, th {
  border: 1px solid black;
}

table {
  border-collapse: collapse;
  width: 100%;
}
.example.Text1 span, .example.Text1 {
  writing-mode: horizontal-tb;
  -webkit-writing-mode: horizontal-tb;
  -ms-writing-mode: horizontal-tb;
}

.example.Text2 span, .example.Text2 {
  writing-mode: vertical-lr;
  -webkit-writing-mode: vertical-lr;
  -ms-writing-mode: vertical-lr;
}

.example.Text3 span, .example.Text3 {
  writing-mode: vertical-rl;
  -webkit-writing-mode: vertical-rl;
  -ms-writing-mode: vertical-rl;
}
```

```html
<table>
  <tr>
    <th>value</th>
    <th>Vertical script</th>
    <th>Horizontal script</th>
    <th>Mixed script</th>
  </tr>
  <tr>
    <td>horizontal-tb</td>
    <td class="example Text1"><span>我家没有电脑。</span></td>
    <td class="example Text1"><span>Example text</span></td>
    <td class="example Text1"><span>1994年に至っ    </span></td>
  </tr>
  <tr>
    <td>vertical-lr</td>
    <td class="example Text2"><span>我家没有电脑。</span></td>
    <td class="example Text2"><span>Example text</span></td>
    <td class="example Text2"><span>1994年に至っては</span></td>
  </tr>
  <tr>
    <td>vertical-rl</td>
    <td class="example Text3"><span>我家没有电脑。</span></td>
    <td class="example Text3"><span>Example text</span></td>
    <td class="example Text3"><span>1994年に至っては</span></td>
  </tr>
</table>
```
