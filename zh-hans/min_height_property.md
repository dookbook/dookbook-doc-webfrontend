TOPICS: min-height property
AUTHORS: Cici Hu; Huooo@mozilla.net; mdn:Huooo

# CSS 属性: `min-height`

CSS属性 **`min-height`** 通常用来设置**一个元素的最小高度**。这个属性 `min-height` 不允许一个元素的高度
[**`height`**](/zh-hans/webfrontend/height_property) 小于这个元素指定的最小高度 `min-height`。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| length | 定义元素的最小高度。默认值是 `0`。|
| `%` | 定义基于包含它的块级对象的百分比最小高度。|

## 示例

```css
p {
  min-height:100px;
  background-color:yellow;
}
```

```html
<p>这段的最小高度设置为100 px。</p>
```
