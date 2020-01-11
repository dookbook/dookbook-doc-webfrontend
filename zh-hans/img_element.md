TOPICS: <img>
        <img> src attribute
        <img> alt attribute
        <img> width attribute
        <img> height attribute
        <img> srcset attribute
        <img> sizes attribute
        <img> longdesc attribute

# HTML 图像元素：`<img>`

**HTML `<img>` 元素** 代表文档中的一个**图像**。它是一个*可替换*的元素。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | 流式内容，段落内容，嵌入式内容，可触摸内容。如果元素有 `usemap` 属性，它也是交互内容的一部分。|
| **允许的内容** | 没有，它是一个 空元素. |
| **标签省略** | 必须有一个开始标签，不允许有结束标签. |
| **允许的父元素** | 接受嵌入式内容的任意元素. |
| **DOM 接口** | `HTMLImageElement` |

## 属性

这个元素包括 [HTML全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| **`src`** | (**必需的**) 图像URL地址。|
| **`alt`** | 这个属性定义了描述图像的**替换文本**。如果图像地址是错误的，或该图像格式不支持，或者如果图像还没有被下载，用户将看到这个显示。|
| **`width`** | 图像的**宽度** (单位是*像素*)。|
| **`height`** | 图像的**高度** (单位是*像素*)。|
| **`srcset`** | 以*逗号分隔*的一个或多个字符串列表表明**一系列用户代理可能使用**的图像。|
| **`sizes`** | 表示资源大小的以逗号隔开的一个或多个字符串。每一个资源大小包括：<br>1. 一个媒体条件。最后一项一定是被忽略的。<br>2. 一个资源尺寸的值。<br><br>资源尺寸的值被用来指定图像的预期尺寸。当`srcset`使用 `'w'` 描述符时，用户代理使用当前图像大小来选择`srcset`中合适的一个图像URL。 被选中的尺寸影响图像的显示大小（如果没有CSS样式被应用的话）。如果没有设置`srcset`属性，或者没值，那么sizes属性也将不起作用。 |
| `longdesc` | 指向图像描述信息页面的URL，是对 **`alt`** 文本的补充。 |
| `crossorigin` | 这个枚举属性表明是否必须使用 CORS 完成相关图像的抓取。启用CORS的图像 在 [`<canvas>`](/zh-hans/webfrontend/<canvas>) 元素中可以重复使用而不会被污染。允许的值有：<br><br>`anonymous`<br>执行一个跨域的请求（比如，有 `Origin:` HTTP header）。但是没有发送证书（比如，没有 cookie，没有 X.509 证书，没有 HTTP 基本的授权认证）。如果服务器没有给源站证书（没有设置 Access-Control-Allow-Origin: HTTP头），图像会被污染而且它的使用会被限制。<br><br>`use-credentials`<br>一个有证书的跨域请求（比如，有 `Origin:` HTTP header）被发送 （比如，a cookie, a certificate, and HTTP Basic authenticationis performed）。如果服务器没有给源站发送证书（通过 Access-Control-Allow-Credentials: HTTP header），图像将会被污染，且它的使用会受限制。当用户并未显式使用本属性时，默认不使用 CORS 发起请求(例如，不会向服务器发送 HTTP 头部信息)，用以防止其在[`<canvas>`](/zh-hans/webfrontend/<canvas>)中的使用。如果无效，默认当做 **anonymous** 关键字生效。更多信息，请查看 CORS 属性设置 。 |
| `ismap` | 这个布尔属性表示图像是否是服务器端map的一部分。如果是， 那么点击的精准坐标将会被发送到服务器。<br>**Note:**<br>使用说明：只有在 `<img>` 元素是一个拥有有效 `href` 属性的 [`<a>`](/zh-hans/webfrontend/<a>) 元素的后代元素的情况下，这个属性才会被允许使用。 |
| `usemap` | 与元素相关联的的 image map 的部分 URL（以 '`#`' 开始的部分）。<br>Note:<br>使用说明： 如果 `<img>` 元素是 [`<a>`](/zh-hans/webfrontend/<a>) 或 [`<button>`](/zh-hans/webfrontend/<button>) 元素的后代元素则不能使用这个属性。 |

## 基础用法

!!! warn "**`alt`** 使用说明"
    浏览器并不总是显示该元素中的图像。对于非图形浏览器（包括那些有视力障碍的人所使用的）来说就是这种情况，如果用户选择不显示图像，或者如果浏览器无法显示图像，因为它是无效的或 不支持的类型。
    在这些情况下，浏览器会用该元素的 **`alt`** 属性定义的文本来替换图像。

!!! warn "注意事项"
    省略 **`alt`** 属性表明该图像是内容的关键部分，但没有等效的文本可用。把这个属性设置为空字符串 (`alt=""`)，表明该图像不是内容的关键部分，非可视化浏览器在渲染的时候可能会忽略它。

```html
<!-- 全局链接地址 -->
<img src="https://dookbook.info/static/img/logo-tail.svg" alt="Dookbook logo">

<!-- 本地绝对路径 -->
<img src="/static/img/logo-tail.svg" alt="Dookbook logo">

<!-- 本地相对路径 -->
<img src="static/img/logo-tail.svg" alt="Dookbook logo">
```

## 支持的图像格式

HTML 标准并没有给出必须支持的图像格式的列表，因此每个用户代理支持一组不同的格式。

### Firefox

- [JPEG](http://en.wikipedia.org/wiki/JPEG)
- [GIF](http://en.wikipedia.org/wiki/Graphics_Interchange_Format)，包括动态的GIFs
- [PNG](http://en.wikipedia.org/wiki/Portable_Network_Graphics)
- [APNG](https://wiki.developer.mozilla.org/en-US/docs/Animated_PNG_graphics)
- [SVG](https://wiki.developer.mozilla.org/en-US/docs/SVG)
- [BMP](http://en.wikipedia.org/wiki/BMP_file_format)
- [BMP ICO](http://en.wikipedia.org/wiki/ICO_%28file_format%29)
- [PNG ICO](http://en.wikipedia.org/wiki/ICO_%28file_format%29)
- WebP

## 图像链接

```html
<a href="https://dookbook.info">
  <img src="https://dookbook.info/static/img/logo-tail.svg" alt="Visit the Dookbook site">
</a>
```

## 指定高度和宽度的图像

使用 **`height`** 和 **`width`** 属性来指定图像高度和宽度。

```html
<img src="https://dookbook.info/static/img/logo-tail.svg" alt="Dookbook Logo" height="128" width="256">
```

## 使用 `srcset` 属性

**`srcset`**属性值以*逗号分隔*的一个或多个字符串列表表明**一系列用户代理可能使用**的图像。每一个字符串由以下组成：

1. 一个图像的URL。
2. 可选的，空格后跟以下的其一：
    - 一个**宽度描述符**，这是一个正整数，后面紧跟 **`w`** 符号。该整数宽度除以 *`sizes`* 属性给出的资源大小来计算得到有效的像素密度，即换算成和*`x`*描述符等价的值。
    - 一个**像素密度描述符**，这是一个正浮点数，后面紧跟 **`x`** 符号。
    - 如果没有指定源描述符，那它会被指定为默认的 **`1x`**。

在相同的 `srcset` 属性中混合使用宽度描述符和像素密度描述符时，会导致该值无效。重复的描述符（比如，两个源 在相同的`srcset`两个源都是 `'2x'`）也是无效的。

浏览器会选择在特定条件下(比如用户设置或当前带宽)显示大部分适配的图片。

```html
<img src="dookbook-logo-tail.svg" alt="Dookbook Logo" srcset="dookbook-logo-tail.svg 2x">
```

## 使用 `srcset` 和 `sizes` 属性

在支持 `srcset` 的用户代理中，当使用 *`w`* 描述符时，`src` 属性会被忽略。当匹配了媒体条件 (`min-width: 600px`) 时，图像将宽 `200px`，否则宽 `50vw`（视图宽度的50%）。

```html
<img src="logo-200.png"
     alt="Logo"
     srcset="logo-200.png 200w,logo-400.png 400w"
     sizes="(min-width: 600px) 200px, 50vw">
```

## 与 CSS 的交互

关于 CSS，`<img>` 是一个 替换元素。它没有基线，这意味着当在一个行内格式的上下文中使用 `vertical-align: baseline` 时，图像的底部将会与容器的基线对齐。

根据它的类型，图像可能会有一个本征维数（intrinsic dimension），但这不是一个必要条件：SVG图像就没有，而光栅图像有。
