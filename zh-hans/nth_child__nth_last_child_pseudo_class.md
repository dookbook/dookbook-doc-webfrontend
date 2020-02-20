TOPICS: :nth-child()
        :nth-last-child()
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 伪类: `:nth-child()`、`:nth-last-child()`

**`:nth-child(n)`** CSS 伪类匹配父元素中的第 *n* 个子元素，元素类型没有限制

**`:nth-last-child(n)`** CSS 伪类素匹配属于其元素的第 *n* 个子元素的每个元素，不论元素的类型，从最后一个子元素开始计数。

## 参数

*n* 可以是一个数字，一个关键字，或者一个公式。

## 示例

```html
<p>The first paragraph.</p>
<p>The second paragraph.</p>
<p>The third paragraph.</p>
<p>The fourth paragraph.</p>
```

```css
p:nth-child(1) {
  background:#ff0000;
}

p:nth-last-child(1) {
  background:#ff0000;
}
```
