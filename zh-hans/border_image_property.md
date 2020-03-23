TOPICS: border-image property
        border-image-source property
        border-image-slice property
        border-image-width property
        border-image-outset property
        border-image-repeat property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `border-image`

**`border-image`** CSS属性在给定元素**周围绘制图像**。它替换了元素的**常规边框**。

此属性是 **`border-image-source`**，**`border-image-slice`**，**`border-image-width`**，**`border-image-outset`**
和 **`border-image-repeat`**的简写。与所有速记属性一样，所有省略的子值都将设置为其初始值。

## CSS 属性: `border-image-source`

CSS 属性 **`border-image-source`**  用于声明元素的边框图片（border-image）的资源

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 没有图像被使用 |
| **image** | 边框使用图像的路径 |

## CSS 属性: `border-image-slice`

通过 **`border-image-source`** 引用边框图片后，**`border-image-slice`** 属性会将图片**分割为9个区域**：四个角，四个边（edges）以及中心区域。四条切片线，从它们各自的侧面设置给定距离，控制区域的大小。

![border-image-slice](/media/webfrontend__border-image-slice.png)

上图说明了每个区域的位置。

- 区域 1-4 为角区域（corner region）。 每一个都用一次来形成最终边界图像的角点。
- 区域 5-8 边区域（edge region）。在最终的边框图像中重复，缩放或修改它们以匹配元素的尺寸。
- 区域 9 为中心区域（ middle region）。它在默认情况下会被丢弃，但如果设置了关键字`fill`，则会将其用作背景图像。

中间的区域将不会被边框使用，但当设置有 `fill` 关键词时将会被作为 `background-image`。这个关键词可以被设置在属性的任何一个位置(前面、后面或者两个值之间)

**`border-image-repeat`**, **`border-image-width`**, **`border-image-outset`** 属性则定义这些图片将如何使用。

| 属性值 | 说明 |
| :--- | :--- |
| **number** | 数字表示图像的像素（位图图像）或向量的坐标（如果图像是矢量图像）|
| **`%`** | 百分比图像的大小是相对的：水平偏移图像的宽度，垂直偏移图像的高度 |
| **`fill`** | 保留图像的中间部分 |

## CSS 属性: `border-image-width`

**`border-image-width`** 定义图像**边框宽度**。假如`border-image-width`大于已指定的`border-width`，那么它将向内部(`padding`/`content`)扩展.

| 属性值 | 说明 |
| :--- | :--- |
| **number** | 表示相应的 `border-width` 的倍数 |
| **`%`** | 边界图像区域的大小：横向偏移的宽度的面积，垂直偏移的高度的面积 |
| **`auto`** | 如果指定了，宽度是相应的image slice的内在宽度或高度 |

## CSS 属性: `border-image-outset`

**`border-image-outset`** 属性定义边框图像**可超出边框盒的大小**。

| 属性值 | 说明 |
| :--- | :--- |
| **length** | 边框图像的大小从一个维度开始，即一个带单位的数字 |
| **number** | 边框图像的大小开始时是元素相应边框宽度的倍数。例如，如果元素的边框宽度为：`1em 2px 0 1.5rem`，而 `border-image-outset：2`，则最终的`border-image-outset` 将计算为 `2em 4px 0 3rem` |

## CSS 属性: `border-image-repeat`

**`border-image-repeat`** 定义**图片如何填充边框**。或为单个值，设置所有的边框；或为两个值，分别设置水平与垂直的边框。

| 属性值 | 说明 |
| :--- | :--- |
| **`stretch`** | **拉伸图片**以填充边框 |
| **`repeat`** | **平铺图片**以填充边框 |
| **`round`** | 平铺图像。当不能整数次平铺时，根据情况放大或缩小图像 |
| **`space`** | 平铺图像。当不能整数次平铺时，会用空白间隙填充在图像周围（不会放大或缩小图像）|

## 简写示例

```css
#bitmap {
  border: 30px solid transparent;
  padding: 20px;
  border-image: url("https://mdn.mozillademos.org/files/4127/border.png") 30;
}
```

```html
<div id="bitmap">The image is stretched to fill the area.</div>
```

## `border-image-slice`、`border-image-repeat`

```css
div {
  background-color: lightgrey;
  border: 30px solid transparent;
  border-image: url('border.png');
  border-image-slice: 30;
  border-image-repeat: repeat;
}
```

```html
<div>
 DIV 使用图像边框。
</div>
<p>使用的图片:</p>
<img src="border.png">
```

## `border-image-source`、`border-image-width`

```css
div {
  border-image-source: url(border.png);
  border-image-width: 30 30;
}
```
