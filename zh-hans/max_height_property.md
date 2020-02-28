TOPICS: max-height property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         Dong WEI; FredWe@mozilla.net; mdn:FredWe
         Teoli; teoli@mozilla.net; mdn:teoli
         紫云飞; ziyunfei@mozilla.net; mdn:ziyunfei

# CSS 属性: `max-height`

**`max-height`** 属性用来设置给定**元素的最大高度**. 如果 [**`height`**](/zh-hans/webfrontend/height)
属性的值比 `max-height` 属性的值还大, 则 [**`height`**](/zh-hans/webfrontend/height) 属性会失效.

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| length | 定义元素的最大高度值。|
| **`%`** | 定义基于包含它的块级对象的百分比最大高度。|

## 示例

```css
p{
  height: 150px;
  max-height:50px;
  background-color:yellow;
}
```

```html
<p>这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。</p>
```
