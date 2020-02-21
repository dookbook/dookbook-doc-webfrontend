TOPICS: :first-of-type
        :last-of-type

# CSS 伪类: `:first-of-type`、`:last-of-type`

**`:first-of-type`** CSS 伪类表示**一组兄弟元素中其类型的第一个元素**。

**`:last-of-type`** CSS 伪类 表示了在（它父元素的）子元素列表中，**最后一个给定类型的元素**。当代码类似父标签名称`:last-of-type`的作用区域包含父元素的所有子元素中的最后一个选定元素，也包括子元素的最后一个子元素并以此类推。

## 示例: 装饰第一个段落和最后一个段落

```html
<h2>Heading</h2>
<p>Paragraph 1</p>
<p>Paragraph 2</p>
<p>Paragraph 3</p>
<p>Paragraph 4</p>
```

```css
p:first-of-type {
  color: red;
  font-style: italic;
}

p:last-of-type {
  color: blue;
  font-style: italic;
}
```

## 示例: 嵌套元素

```html
<article>
  <div>This `div` is first!</div>
  <div>This <span>nested `span` is first</span>!</div>
  <div>This <em>nested `em` is first</em>, but this <em>nested `em` is last</em>!</div>
  <div>This <span>nested `span` gets styled</span>!</div>
  <b>This `b` qualifies!</b>
  <div>This is the final `div`.</div>
</article>
```

```css
article :first-of-type {
  background-color: pink;
}

article :last-of-type {
  background-color: red;
}
```
