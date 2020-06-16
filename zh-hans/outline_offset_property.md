TOPICS: outline-offset property

# CSS 属性: `outline-offset`

CSS **`outline-offset`** 属性用于设置 [**`outline`**](/zh-hans/webfrontend/outline_property) 与**一个元素边缘或边框之间的间隙**。

[**`outline`**](/zh-hans/webfrontend/outline_property) 是元素的轮廓，悬浮在元素边框之上。元素和其轮廓之间是透明的。也就是说，它们之间的颜色会继承父元素的背景色。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **length** | 元素和轮廓间的宽度。负值将轮廓绘制在元素之内。|

## 示例

```css
p {
  outline: dashed thin;
  /* Move the outline 10px away from the border */
  outline-offset: 10px;
  border:1px solid black;
}
```

```html
<p>outline: offset 10px. Border is solid and outline is dashed</p>
```
