TOPICS: <picture>

# `<picture>`

HTML `<picture>` 元素通过包含零或多个 [`<source>`](/zh-hans/webfrontend/<source>) 元素和一个 [`<img>`](/zh-hans/webfrontend/<img>)
元素来为不同的显示/设备场景提供图像版本。浏览器会选择最匹配的子 [`<source>`](/zh-hans/webfrontend/<source>) 元素，如果没有匹配的，
就选择 [`<img>`](/zh-hans/webfrontend/<img>) 元素的 `src` 属性中的URL。然后，所选图像呈现在[`<img>`](/zh-hans/webfrontend/<img>)元素占据的空间中。

要决定加载哪个URL，user agent 检查每个 [`<source>`](/zh-hans/webfrontend/<source>) 的 srcset、media 和 type 属性，来选择最匹配页面当前布局、显示设备特征等的兼容图像。

`<picture>` 的常见使用场景：

- 艺术指导(Art direction) —— 针对不同 media 条件裁剪或修改图像
- 遇到所有浏览器都不支持的特定格式时，提供不同的图像格式

如果提供用于高dpi(视网膜)显示的图像的高密度版本，则在[`<img>`](/zh-hans/webfrontend/<img>)元素上使用srcset。这使得浏览器可以选择数据保存模式下的低密度版本，而不必编写显式的媒体条件。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*表述内容*，*嵌入内容*。 |
| **允许的内容** | 零或多个 [`<source>`](/zh-hans/webfrontend/<source>) 元素，以及紧随其后的一个 [`<img>`](/zh-hans/webfrontend/<img>) 元素，可以混合一些脚本支持的元素。|
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 任何可以包含*嵌入内容*的元素。|
| **允许的 ARIA 角色** | 无 |
| **DOM 接口** | **`HTMLPictureElement`** |

## 属性

这个元素只包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 用法提示

你可以使用 `object-position` 属性调整元素框架内图像的位置，用 `object-fit` 属性控制图片如何调整大小来适应框架。

!!! warn "Don't try this at home"
    提示：在子 [`<img>`](/zh-hans/webfrontend/<img>) 元素上使用这些属性，不是 `<picture>` 元素。

## 示例

这些示例演示了 [`<source>`](/zh-hans/webfrontend/<source>) 元素的不同属性如何更改`<picture>`中图像的选择。

### `media` 属性

`media` 属性允许你提供一个用于给用户代理作为选择 [`<source>`](/zh-hans/webfrontend/<source>) 元素的依据的媒体条件(media condition)（类似于媒体查询）。如果这个媒体条件匹配结果为
false，那么这个 [`<source>`](/zh-hans/webfrontend/<source>) 元素会被跳过。

```html
<picture>
  <source srcset="mdn-logo-wide.png" media="(min-width: 600px)">
  <img src="mdn-logo-narrow.png" alt="MDN">
</picture>
```

### `type` 属性

`type` 属性允许你为 [`<source>`](/zh-hans/webfrontend/<source>) 元素的 `srcset` 属性指向的资源指定一个 MIME 类型。如果用户代理不支持指定的类型，
那么这个 [`<source>`](/zh-hans/webfrontend/<source>) 元素会被跳过。

```html
​<picture>
  <source srcset="mdn-logo.svg" type="image/svg+xml">
  <img src="mdn-logo.png" alt="MDN">
</picture>
```
