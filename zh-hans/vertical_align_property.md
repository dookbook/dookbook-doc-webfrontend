TOPICS: vertical-align property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Bayes; 827130441@qq.com; github:coconilu
         Dong WEI; FredWe@mozilla.net; mdn:FredWe
         Teoli; teoli@mozilla.net; mdn:teoli
         Ivan Yan; yanxyz@github.com; github:yanxyz
         Colin Cheng; zbinlin@outlook.com; github:zbinlin

# CSS 属性: `vertical-align`

CSS 属性 **`vertical-align`** 用来指定**行内元素**（`inline`）或**表格单元格**（`table-cell`）元素的**垂直对齐方式**。

`vertical-align` 属性可被用于两种环境：

- 使行内元素盒模型与其行内元素容器垂直对齐。例如，用于垂直对齐一行文本的内的图片[`<img>`](/zh-hans/webfrontend/<img>)
- 垂直对齐表格单元内容

!!! warn "注意"
    `vertical-align` 只对**行内元素**、**表格单元格元素生效**、不能用它垂直对齐块级元素。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`baseline`** | 使元素的基线与父元素的基线对齐。HTML规范没有详细说明部分可替换元素的基线，如 [`<textarea>`](/zh-hans/webfrontend/<textarea>)，这意味着这些元素使用此值的表现因浏览器而异。|
| **`sub`** | 使元素的基线与父元素的下标基线对齐。|
| **`super`** | 使元素的基线与父元素的上标基线对齐。|
| **`text-top`** | 使元素的顶部与父元素的字体顶部对齐。|
| **`text-bottom`** | 使元素的底部与父元素的字体底部对齐。|
| **`middle`** | 使元素的中部与父元素的基线加上父元素`x-height`（译注：`x`高度）的一半对齐。|
| length | 使元素的基线对齐到父元素的基线之上的给定长度。可以是负数。|
| **`%`** | 使元素的基线对齐到父元素的基线之上的给定百分比，该百分比是 `line-height` 属性的百分比。可以是负数。|
| **`top`** | 使元素及其后代元素的顶部与整行的顶部对齐。|
| **`bottom`** | 使元素及其后代元素的底部与整行的底部对齐。没有基线的元素，使用外边距的下边缘替代。|

## 示例

```css
img.top { vertical-align: text-top; }
img.bottom { vertical-align: text-bottom; }
img.middle { vertical-align: middle; }
```

```html
<div>An <img src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a default alignment.</div>
<div>An <img class="top" src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a text-top alignment.</div>
<div>An <img class="bottom" src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a text-bottom alignment.</div>
<div>An <img class="middle" src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a middle alignment.</div>
```
