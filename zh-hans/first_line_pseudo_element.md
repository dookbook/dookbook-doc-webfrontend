TOPICS: ::first-line

# CSS 伪元素: `::first-line`

**`::first-line`** CSS 伪元素用来指定选择器**第一行**的样式。

!!! warn "注意"
    `::first-line` 选择器适用于*块级元素*中。

## 示例

```html
<h1>WWF's Mission Statement</h1>
<p>To stop the degradation of the planet's natural environment and to build a future in which humans live in harmony with nature, by; conserving the world's biological diversity, ensuring that the use of renewable natural resources is sustainable, and promoting the reduction of pollution and wasteful consumption.</p>
```

```css
p::first-line {
  background-color:yellow;
}
```
