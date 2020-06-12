TOPICS: object-fit property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `object-fit`

CSS **`object-fit`** 属性指定**可替换元素的内容**应该如何适应到其使用的**高度**和**宽度确定的框**。

您可以通过使用 [**`object-position`**](/zh-hans/webfrontend/object-position_property) 属性来**切换被替换元素的内容对象**在元素框内的**对齐方式**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`contain`** | 被替换的内容将被缩放，以在填充元素的内容框时保持其宽高比。 整个对象在填充盒子的同时保留其长宽比，因此如果宽高比与框的宽高比不匹配，该对象将被添加“黑边”。|
| **`cover`** | 被替换的内容在保持其宽高比的同时填充元素的整个内容框。如果对象的宽高比与内容框不相匹配，该对象将被剪裁以适应内容框。|
| **`fill`** | 被替换的内容正好填充元素的内容框。整个对象将完全填充此框。|如果对象的宽高比与内容框不相匹配，那么该对象将被拉伸以适应内容框。|
| **`none`** | 被替换的内容将保持其原有的尺寸。|
| **`scale-down`** | 内容的尺寸与 *`none`* 或 *`contain`* 中的一个相同，取决于它们两个之间谁得到的对象尺寸会更小一些。|

## 示例

```html
<div>
  <h2>object-fit: fill</h2>
  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="fill"/>

  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="fill narrow"/>

  <h2>object-fit: contain</h2>
  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="contain"/>

  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="contain narrow"/>

  <h2>object-fit: cover</h2>
  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="cover"/>

  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="cover narrow"/>

  <h2>object-fit: none</h2>
  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="none"/>

  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="none narrow"/>

  <h2>object-fit: scale-down</h2>
  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="scale-down"/>

  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="scale-down narrow"/>

</div>
```

```css
h2 {
  font-family: Courier New, monospace;
  font-size: 1em;
  margin: 1em 0 0.3em;
}

div {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-items: flex-start;
  height: 940px;
}

img {
  width: 150px;
  height: 100px;
  border: 1px solid #000;
}

.narrow {
  width: 100px;
  height: 150px;
  margin-top: 10px;
}

.fill {
  object-fit: fill;
}

.contain {
  object-fit: contain;
}

.cover {
  object-fit: cover;
}

.none {
  object-fit: none;
}

.scale-down {
  object-fit: scale-down;
}
```
