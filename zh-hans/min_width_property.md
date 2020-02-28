TOPICS: min-width property
AUTHORS: BayouBao; BayouBao@github.com; github:BayouBao
         Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Teoli; teoli@mozilla.net; mdn:teoli
         sunnylost; sunnylost@gmail.com; github:sunnylost

# CSS 属性: `min-width`

**`min-width`** 属性为给定**元素设置最小宽度**。它可以阻止 [**`width`**](/zh-hans/webfrontend/width) 属性的应用值小于
`min-width` 的值。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| length | 定义元素的最小宽度值。默认值：取决于浏览器。|
| `%` | 定义基于包含它的块级对象的百分比最小宽度。|

## 示例

```css
p {
  min-width:150px;
  background-color:yellow;
  width: 10px
}
```

```html
<!-- 这个段落的最小宽度设置为 150px -->
<p>min-width</p>
```
