TOPICS: ::selection
AUTHORS: 紫云飞; ziyunfei@mozilla.net; mdn:ziyunfei
         晓月风尘; Serifx@mozilla.net; mdn:Serifx
         Mike Chen; ranwu@mozilla.net; mdn:ranwu
         John Cido; johncido@mozilla.net; mdn:johncido

# CSS 伪元素: `::selection`

**`::selection`** CSS伪元素应用于**文档中被用户高亮的部分**（比如使用*鼠标*或其他选择设备选中的部分）。

只有一小部分CSS属性可以用于 `::selection` 选择器：

- `color`
- `background-color`
- `cursor`
- `caret-color`
- `outline` 和它的手写
- `text-decoration` 及其相关属性
- `text-emphasis-color`
- `text-shadow`

!!! error ""
    要特别注意的是，`background-image` 会如同其他属性一样被忽略。

## 示例

```html
This text has special styles when you highlight it.
<p>Also try selecting text in this paragraph.</p>
```

```css
::-moz-selection {
  color: gold;
  background-color: red;
}

p::-moz-selection {
  color: white;
  background-color: blue;
}
/* Make selected text gold on a red background */
::selection {
  color: gold;
  background-color: red;
}

/* Make selected text in a paragraph white on a blue background */
p::selection {
  color: white;
  background-color: blue;
}
```
