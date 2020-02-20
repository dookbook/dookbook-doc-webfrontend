TOPICS: :nth-of-type()
        :nth-last-of-type()

# CSS 伪类: `:nth-of-type()`、`:nth-last-of-type()`

**`:nth-of-type(n)`** CSS 伪类根据它们在一组同级兄弟中的位置（从**从头**算起）来匹配给定类型的元素。

**`:nth-last-of-type(n)`** CSS 伪类根据元素在同胞组中的位置（从**末尾**算起）来匹配给定类型的元素。

## 参数

*n* 可以是一个数字，一个关键字，或者一个公式。

## 示例: `:nth-of-type()`

```html
<div>
  <div>这段不参与计数。</div>
  <p>这是第一段。</p>
  <p>这是第二段。</p>
  <div>这段不参与计数。</div>
  <p>这是第三段。</p>
  <p>这是第四段。</p>
</div>
```

```css
/* 奇数段 */
p:nth-of-type(2n+1) {
  color: red;
}

/* 偶数段 */
p:nth-of-type(2n) {
  color: blue;
}

/* 第一段 */
p:nth-of-type(1) {
  font-weight: bold;
}
```

## 示例: `:nth-last-of-type`

```html
<div>
  <span>This is a span.</span>
  <span>This is another span.</span>
  <em>This is emphasized.</em>
  <span>Wow, this span gets limed!!!</span>
  <strike>This is struck through.</strike>
  <span>Here is one last span.</span>
</div>
```

```css
span:nth-last-of-type(2) {
  background-color: lime;
}
```
