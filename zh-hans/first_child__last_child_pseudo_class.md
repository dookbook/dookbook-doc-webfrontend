TOPICS: :first-child
        :last-child
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 伪类: `:first-child`、`:last-child`

**`:first-child`** CSS 伪类表示在一组兄弟元素中的第一个元素。按照最初定义时，所选元素必须有一个父元素。从选择器 Level 4 开始，这不再是必需的。

**`:last-child`** CSS 伪类代表父元素的最后一个子元素。按照最初的定义，所选元素必须具有一个父元素。从选择器 Level 4 开始，这不再是必需的。

## 基本示例

```html
<div>
  <p>This text is selected!</p>
  <p>This text isn't selected.</p>
</div>

<div>
  <h2>This text isn't selected: it's not a `p`.</h2>
  <p>This text isn't selected.</p>
</div>
```

```css
p:first-child {
  color: lime;
  background-color: black;
  padding: 5px;
}

p:last-child {
  color: #ff0;
  background-color: red;
  padding: 5px;
}
```

## 样式清单

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3
    <ul>
      <li>Item 3.1</li>
      <li>Item 3.2</li>
      <li>Item 3.3</li>
    </ul>
  </li>
</ul>
```

```css
ul li {
  color: blue;
}

ul li:first-child {
  border: 1px solid blue;
  color: blue;
}

ul li:last-child {
  border: 1px solid red;
  color: red;
}
```
