TOPICS: CSS Dimension
        width property
        min-width property
        max-width property
        height property
        min-height property
        max-height property

# CSS 尺寸

**CSS 尺寸** 属性允许你控制元素的**高度**和**宽度**。

| 属性 | 描述 |
| :--- | :--- |
| **`width`** | 指定**元素的宽度**。默认情况下，它设置**内容区域的宽度**，但是如果 **`box-sizing`** 设置为 **`border-box`**，它则是**边框区域的宽度**。|
| **`min-width`** | 指定**元素的最小宽度**。它可以阻止 **`width`** 属性的应用值小于 `min-width` 的值。|
| **`max-width`** | 指定**元素的最大宽度**。如果 **`width`** 属性的值比 `max-width` 属性的值还大, 则 **`width`** 属性会失效. |
| **`height`** | 指定**元素的高度**。默认情况下，这个属性决定的是**内容区的高度**，但是，如果将 **`box-sizing`** 设置为 **`border-box`**, 这个属性决定的将是**边框区域的高度**。|
| **`min-height`** | 指定**元素的最小高度**。这个属性 `min-height` 不允许一个元素的高度 **`height`** 小于这个元素指定的最小高度 `min-height`。|
| **`max-height`** | 指定**元素的最大高度**。如果 **`height`** 属性的值比 `max-height` 属性的值还大, 则 **`height`** 属性会失效.

## `width` 属性值

**`min-width`** 和 **`max-width`** 也拥有同样的属性值

| 属性值 | 说明 |
| :--- | :--- |
| length | 使用 [**`px`**](/zh-hans/webfrontend/px)、[**`rem`**](/zh-hans/webfrontend/rem)、[**`em`**](/zh-hans/webfrontend/em) 等单位定义宽度 |
| **`%`** | 定义基于包含块（父元素）宽度的百分比宽度 |
| **`auto`** | 默认值。浏览器可计算出实际的宽度 |
| **`inherit`** | 规定应该从父元素继承 `width` 属性的值 |

## `height` 属性值

**`min-height`** 和 **`max-height`** 也拥有同样的属性值

| 属性值 | 说明 |
| :--- | :--- |
| length | 使用 [**`px`**](/zh-hans/webfrontend/px)、[**`rem`**](/zh-hans/webfrontend/rem)、[**`em`**](/zh-hans/webfrontend/em) 等单位定义高度。|
| **`%`** | 基于包含它的块级对象的百分比高度。|
| **`auto`** | 默认。浏览器会计算出实际的高度。|
| **`inherit`** | 规定应该从父元素继承 `height` 属性的值 |

## 示例

```html
<p id="a">这是一个段落</p>
<p id="b">这是一个段落</p>
<p id="c">这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落这是一个段落</p>
</div>
```

```css
/* 定义该元素宽高各100px */
#a { width: 100px; height: 100px; background: #0f0; }

/* 定义该元素最小宽高各50px */
#b { min-width: 50px; min-height: 50px; background: #00f; }

/* 定义该元素最大宽高各200px */
#c { max-width: 200px; max-height: 200px; background: #f00; }
```
