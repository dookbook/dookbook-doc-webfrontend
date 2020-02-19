TOPICS: <source>

# `<source>`

HTML HTML `<source>`元素为[`<picture>`](/zh-hans/webfrontend/<picture>)，
[`<audio>`](/zh-hans/webfrontend/<audio>)或[`<video>`](/zh-hans/webfrontend/<video>)元素指定了多种媒体资源。
它是一个空元素，表示它没有内容且没有结束标记。 它通常用于提供不同浏览器支持的多种格式的相同媒体内容。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | 没有。 |
| **允许的内容** | 无，这是一个空元素。 |
| **标签遗漏** | 它必须具有开始标签，但不能具有结束标签。 |
| **允许的父元素** | 媒体元素-[`<audio>`](/zh-hans/webfrontend/<audio>)或[`<video>`](/zh-hans/webfrontend/<video>),并且必须放置在任何*流式内容*或[`<track>`](/zh-hans/webfrontend/<track>)元素之前.<br>[`<picture>`](/zh-hans/webfrontend/<picture>)元素,必须将其放在[`<img>`](/zh-hans/webfrontend/<img>)元素之前。 |
| **允许的 ARIA 角色** | 没有 |
| **DOM 接口** | **`HTMLSourceElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `sizes` | 是源尺寸的列表，描述了源表示的图像的最终渲染宽度.每个源大小均包含一个以逗号分隔的媒体条件长度对列表。 浏览器将使用此信息来确定页面布局之前在`srcset`中定义使用的图像。<br>`sizes`属性仅在`<source>`元素是直接子元素时才有效。[`<picture>`](/zh-hans/webfrontend/<picture>)元素的元素。|
| `src` | 媒体资源地址[`<audio>`](/zh-hans/webfrontend/<audio>)和[`<video>`](/zh-hans/webfrontend/<video>)是必需的。 当将`<source>`元素放置在[`<picture>`](/zh-hans/webfrontend/<picture>)元素内时，此属性的值将被忽略。 |
| `srcset` | 由逗号分隔的一个或多个字符串的列表，指示由浏览器使用的源表示的一组可能的图像。 每个字符串由以下组成：<br> 1、图片的一个URL，<br> 2、宽度描述符，它是一个正整数，紧跟着`w`。 如果缺少默认值，则为无穷大。<br> 3、像素密度描述符，它是一个正浮点数，后跟`x`。 如果缺少默认值，则默认值为`1x`。<br> <br>列表中的每个字符串都必须至少具有宽度描述符或像素密度描述符才有效。 在列表中必须只有一个字符串，其中包含相同的宽度描述符和像素密度描述符元组。<br>浏览器选择在给定时间点显示的最合适图像。<br> `srcset`属性具有作用 仅当`<source>`元素是[`<picture>`](/zh-hans/webfrontend/<picture>)元素的直接子元素时。|
| `type` | 资源的MIME类型，可以选择使用`codecs`参数。 有关如何指定编解码器的信息，请参见RFC 4281。 |
| `media` | 资源预期媒体的媒体查询； 如果未指定`type`属性，则从服务器检索媒体的类型，并检查用户代理是否可以处理它；否则，仅在[`<picture>`](/zh-hans/webfrontend/<picture>)元素中使用。 如果无法呈现，则检查下一个`<source>`。 如果指定了type属性，则将其与用户代理可以提供的类型进行比较，如果不识别，则甚至不会查询服务器。 而是立即检查下一个`<source>`元素。|

## 使用说明

`<source>`元素是一个 **空元素**，这意味着它不仅没有内容，而且没有结束标记。 也就是说，您永远不会在HTML中使用“`</source>`”。

## 示例

### 影片范例

本示例演示如何为浏览器支持Ogg格式的用户提供Ogg格式的视频，以及为浏览器支持Ogg格式的用户提供QuickTime格式的视频。 如果浏览器不支持`audio`或`video`元素，则会显示一条通知。
如果浏览器支持该元素但不支持任何指定格式，则将引发`error`事件，并且默认媒体控件（如果启用）将指示错误。 另请参见各种浏览器中音频和视频元素支持的媒体格式列表。

```html
<video controls>
  <source src="foo.webm" type="video/webm">
  <source src="foo.ogg" type="video/ogg">
  <source src="foo.mov" type="video/quicktime">
  I'm sorry; your browser doesn't support HTML5 video.
</video>
```

有关更多示例，请参阅在Firefox中使用音频和视频。

### 图片示例

```html
<picture>
   <source srcset="mdn-logo-wide.png" media="(min-width: 800px)">
   <source srcset="mdn-logo-medium.png" media="(min-width: 600px)">
   <img src="mdn-logo-narrow.png" alt="MDN">
</picture>
```

使用[`<picture>`](/zh-hans/webfrontend/<picture>)元素时，必须始终包括带有后备图像的[`<img>`](/zh-hans/webfrontend/<img>)，并带有`alt`属性以确保可访问性。
