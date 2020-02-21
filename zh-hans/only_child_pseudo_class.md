TOPICS: :only-child

# CSS 伪类: `:only-child`

CSS伪类 **`:only-child`** 匹配**没有任何兄弟元素的元素**，例如：一个元素里面只包含一个元素的

## 基本例子

```html
<div>
  <div>I am an only child.</div>
</div>

<div>
  <div>I am the 1st sibling.</div>
  <div>I am the 2nd sibling.</div>
  <div>I am the 3rd sibling, <div>but this is an only child.</div></div>
</div>
```

```css
div:only-child {
  color: red;
}

div {
  display: inline-block;
  margin: 6px;
  outline: 1px solid;
}
```
