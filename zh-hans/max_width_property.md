TOPICS: max-width property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ

# CSS 属性: `max-width`

**`max-width`** 属性用来给**元素设置最大宽度值**. 如果 [**`width`**](/zh-hans/webfrontend/width)
属性的值比 `max-width` 属性的值还大, 则 [**`width`**](/zh-hans/webfrontend/width) 属性会失效.

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| length | 定义元素的最大宽度值。|
| **`%`** | 定义基于包含它的块级对象的百分比最大宽度。|

## 示例

在下面的例子里, `id` 为 `"child"` 的 [`<div>`](/zh-hans/webfrontend/<div>) 元素设置了 `width` 值, 使它的宽度与父元素
`"parent"` 相等(`100%`),但是 `max-width` 值限制了它最大宽度只能到`150px`.

```html
<div id="parent">
  <div id="child">
    The Mozilla community produces a lot of great software.
  </div>
</div>
```

```css
#parent { width: 300px; }

#child  {
  background: gold;
  width: 100%;
  max-width: 150px;
}
```
