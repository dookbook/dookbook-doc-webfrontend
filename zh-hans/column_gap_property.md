TOPICS: column-gap property

# CSS 列间距大小属性: `column-gap`

CSS **`column-gap`** 属性用来设置**元素列之间的间隔大小**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 浏览器的默认间距用于各列之间。对于多列布局，将其指定为`1em`。对于所有其他布局类型，该值为`0`。 |
| **length** | 列之间的**间隙大小**，值必须为**正数**。 |
| **percentage** | 用 **percentage**（百分比）来定义列之间的间隔大小。同样的，值也必须是**正数**。|

## 示例

```css
.content-box {
  column-count: 3; /* 将把段落设为3列 */
  column-gap: 40px; /* 列间距为40px */
}
```

```html
<p class="content-box">
  This is some multi-column text with a 40px column
  gap created with the CSS `column-gap` property.
  Don't you think that's fun and exciting? I sure do!
</p>
```
