TOPICS: :first

# CSS 伪类: `:first`

**`:first`** **`@page`** CSS 伪类选择器描述的是：打印文档的时候，**第一页的样式**。

!!! warn "提示"
    你不能改变所有的CSS属性. 你只能改变 `margins`、 `orphans`、 `widows`、文档什么时候换页。别的所有CSS样式都会被忽略。

## 示例

```html
<p>First Page.</p>
<p>Second Page.</p>
<button>Print!</button>
```

```css
@page :first {
  margin-left: 50%;
  margin-top: 50%;
}

p {
  page-break-after: always;
}
```

```javascript
document.querySelector("button").onclick = function(){ window.print() }
```
