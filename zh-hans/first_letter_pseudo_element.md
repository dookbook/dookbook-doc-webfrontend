TOPICS: ::first-letter

# CSS 伪元素: `::first-letter`

**`:first-letter`** CSS 伪元素用来指定元素**第一个字母**的样式。

!!! warn "注意"
    `::first-letter` 选择器仅适用于在*块级元素*中.

## 示例

```html
<h1>Welcome to My Homepage</h1>
<p>My name is Donald.</p>
<p>I live in Duckburg.</p>
<p>My best friend is Mickey.</p>
```

```css
p::first-letter {
  font-size:200%;
  color:#8A2BE2;
}
```
