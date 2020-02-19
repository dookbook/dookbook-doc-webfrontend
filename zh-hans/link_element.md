TOPICS: <link>

# HTML外部资源链接元素：`<link>`

**HTML外部资源链接元素（`<link>`）** 指定当前文档和**外部资源**之间的关系。此元素最常用于链接到**样式表**，但也用于建立站点图标（“**favicon**”样式图标以及用于**主屏幕**和移动设备上的**应用程序的图标**）。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *元数据内容*。 如果存在`itemprop`：*流式内容*和*短语内容*. |
| **允许的内容** | 无，这是一个空元素。 |
| **标签遗漏** | 由于它是一个void元素，因此必须存在开始标签，而不能存在结束标签。 |
| **允许的父元素** | 接受*元数据内容*的任何元素。 如果存在`itemprop`：接受*短语内容*的任何元素。 |
| **允许的 ARIA 角色** | 没有 |
| **DOM 接口** | **`HTMLLinkElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`href`** | 此属性指定**链接资源的URL**。 [[URL]]可以是*绝对地址*或*相对地址*。|
| **`rel`** | 此属性命名链接文档与当前文档的**关系**。`rel`代表“*relationship*（*关系*）”，且必须是链接类型值的、用*空格分隔*的列表。|
| *`type`* | 此属性用于定义链接到的**内容的类型**。该属性的值应为 *[[MIME]]类型*，例如`text/html`，`text/css`等。此属性的常见用法是定义所引用样式表的类型（例如`text/css`），但是鉴于[[CSS]]是网络上使用的*唯一*样式表语言，不仅可以省略`type`属性，而且还是实际上现在建议的做法。它还用于`rel="preload"`链接类型，以确保浏览器仅下载其支持的文件类型。
| *`sizes`* | 此属性定义资源中包含的**视觉媒体的图标大小**。仅当`rel`包含`icon`的值或非标准类型（例如Apple的`apple-touch-icon`）时，此属性才必须存在。它可能具有以下值：<br>- `any`，表示图标可以**按矢量格式缩放为任意大小**，例如`image/svg+xml`。<br>- 一个空格分开的列表，每个列表的格式为`<像素宽度>x<像素高度>`或`<像素宽度>X<像素高度>`。这些大小中的每一个都必须包含在资源中。|
| *`media`* | 此属性指定链接资源**适用的媒体**。 它的值必须是**媒体类型**/**媒体查询**。 当链接到外部样式表时，此属性主要有用-它允许用户代理为其运行的设备选择最适合的设备。<br>在HTML 4中，这只能是一个用空格分隔的简单媒体列表 描述文字，即媒体类型和组，在其中定义并允许作为该属性的值，例如打印，屏幕，听觉，盲文。 HTML5将此扩展到了任何类型的媒体查询，这些媒体查询是HTML 4允许值的超集。<br>不支持CSS3媒体查询的浏览器不一定会识别适当的链接； 不要忘记设置备用链接，这是HTML 4中定义的受限媒体查询集。|
| *`title`* | 此属性在`<link>`元素上具有特殊的语义。在`<link rel="stylesheet">`上使用时，它定义了**首选样式表**或**备用样式表**。错误地使用它可能会导致样式表被忽略。|
| `as` | 仅当在`<link>`元素上设置了`rel="preload"`或`rel="prefetch"`时，才使用此属性。它指定了由`<link>`加载的内容的类型，这对于内容优先级，请求匹配，正确的内容安全策略的应用以及正确的Accept request标头的设置是必需的。|
| `crossorigin` | 此枚举的属性指示在获取资源时是否必须使用CORS。启用了CORS的图像可以在[`<canvas>`](/zh-hans/webfrontend/<canvas>)元素中重复使用而不会受到污染。允许的值为：<br>`anonymous` <br>执行了跨域请求（即带有HTTP头的`Origin`），但未发送凭据（即未发送cookie，X.509证书或HTTP Basic）。身份验证）。如果服务器未将凭据提供给原始站点（未设置`Access-Control-Allow-Origin` HTTP标头），则该图像将被污染并且其使用受到限制。<br>`use-credentials` <br>一个跨域请求（即带有`Origin` HTTP标头的请求）与发送的凭证（即执行Cookie，证书和/或HTTP基本身份验证）一起执行。如果服务器未将凭据提供给原始站点（通过`Access-Control-Allow-Credentials` HTTP标头），则该资源将被污染并且其使用受到限制。<br><br>如果该属性不存在，则在没有CORS请求的情况下（即，在没有发送Origin HTTP标头的情况下）获取资源，从而防止了资源的无污染使用。如果无效，则将其视为使用了枚举关键字匿名。有关其他信息，请参见CORS设置属性。|
| `disabled` | 仅对于`"rel="stylesheet"`，`disabled`布尔属性指示是否应加载所描述的样式表并将其应用于文档。如果在加载HTML时在HTML中指定了`disabled`，则在页面加载期间不会加载样式表。 取而代之的是，如果并且在将`disabled`属性更改为`false`或删除时，将按需加载样式表。<br>一旦加载了样式表，则对`disabled`值进行更改 属性不再与`StyleSheet.disabled`属性的值有任何关系。 更改此属性的值只是简单地启用和禁用应用于文档的样式表形式。<br>这与`StyleSheet`的`disabled`属性不同。 将其更改为`true`会将样式表从文档的`document.styleSheets`列表中删除，并且切换回`false`时不会自动重新加载样式表。|
| `hreflang` | 此属性指示链接资源的语言。 这纯粹是建议性的。 允许值由BCP47确定。 仅当存在`href`属性时才使用此属性。|
| `importance` | 指示资源的相对重要性。 优先级提示使用以下值委派：<br>`auto`：表示没有首选项。 浏览器可以使用自己的启发式方法来确定资源的优先级。<br>`high`：向浏览器指示资源具有高优先级。<br>`low`：向浏览器指示资源属于优先级 低优先级。<br> **注意:** 如果存在`rel="preload"`或`rel="prefetch"`，则`importance`属性仅可用于`<link>`元素。|
| `integrity` | 包含内联元数据-您要告诉浏览器提取的资源（文件）的base64编码的加密哈希。 浏览器可以使用它来验证所获取的资源是否已交付，没有意外的操作。 请参阅子资源完整性。|
| `referrerpolicy` | 一个字符串，指示在获取资源时使用哪个引荐来源网址：<br>`no-referrer`表示将不发送`Referer`标头。<br>`no-referrer-when-downgrade`表示不提供`Referer` 导航到没有TLS（HTTPS）的来源时，将发送标头。 如果没有另外指定策略，这是用户代理的默认行为。<br>`origin`表示引荐来源网址将是页面的来源，大致是方案，主机和端口。`origin-when-cross-origin`表示导航到其他起点将仅限于方案，主机和端口，而在同一起点上导航将包括引荐来源网址的路径。<br>`unsafe-url`意味着 引荐来源网址将包含来源和路径（但不包括片段，密码或用户名）。 这种情况是不安全的，因为它可能会将来源和路径从受TLS保护的资源泄漏到不安全的来源。|

### 非标准属性

| 属性 | 描述 |
| :-- | :-- |
| `methods` | 此属性的值提供有关可能在对象上执行的功能的信息。 这些值通常在使用时由HTTP协议提供，但是（由于与`title`属性类似的原因）在链接中预先包含咨询信息可能会很有用。 例如，浏览器可能根据指定的方法选择不同的链接呈现方式。 可搜索的内容可能会得到其他图标，或者外部链接可能会显示离开当前站点的指示。 即使定义的浏览器Internet Explorer 4也无法很好地理解或支持此属性。|
| `prefetch` | 此属性标识下一个导航可能需要的资源，用户代理应检索该资源。 这允许用户代理在将来请求资源时更快地做出响应。|
| `target` | 定义具有已定义链接关系或将显示任何链接资源的呈现的框架或窗口名称。|

## `<link rel="stylesheet">`

### 包含样式表

要链接外部样式表（stylesheet），您需要在[`<head>`](/zh-hans/webfrontend/<head>)内包含一个`<link>`元素来包含样式表，请使用以下语法：

```html
<link href="style.css" rel="stylesheet">
```

这个简单的示例在`href`属性中提供了指向`stylesheet`的路径，并提供了值为`stylesheet`的`rel`属性。

### 提供替代样式表

您还可以指定其他样式表。

用户可以从浏览器菜单中选择要使用的样式表。这为用户提供了一种查看页面的多个版本的方法。

```html
<link href="default.css" rel="stylesheet" title="默认样式">
<link href="fancy.css" rel="alternate stylesheet" title="花哨">
<link href="basic.css" rel="alternate stylesheet" title="基础">
```

## `<link rel="icon">`

### 提供用于不同用法上下文的图标

您可以在同一页面上包含指向多个不同图标的链接，浏览器将使用`rel`和`sizes`值作为提示来选择最适合其特定上下文的图标。

!!! info "注意"
    大多数图标格式只能存储一个图标。因此大多数情况下，尺寸只包含一个条目。MS的ICO格式和Apple的ICNS一样。ICO更普遍，您应该使用它。

```html
<!-- 带高分辨率Retina显示屏的第三代iPad: -->
<link rel="apple-touch-icon-precomposed" sizes="144x144" href="favicon144.png">

<!-- 带高分辨率Retina显示屏的iPhone: -->
<link rel="apple-touch-icon-precomposed" sizes="114x114" href="favicon114.png">

<!-- 第一代、第二代 iPad: -->
<link rel="apple-touch-icon-precomposed" sizes="72x72" href="favicon72.png">

<!-- 非Retina屏的iPhone, iPod Touch, 和Android 2.1+设备: -->
<link rel="apple-touch-icon-precomposed" href="favicon57.png">

<!-- 基础favicon -->
<link rel="icon" href="favicon32.png">
```

## CSS样式

`<link>`元素在Web文档上没有可视化外观，因此没有样式方面的问题。

## 示例

### 通过媒体查询（media query）有条件地加载资源

您可以在`media`属性中提供媒体类型或查询；然后，只有在媒体条件满足时，才会加载此资源。例如：

```html
<link href="print.css" rel="stylesheet" media="print">
<link href="mobile.css" rel="stylesheet" media="all">
<link href="desktop.css" rel="stylesheet" media="screen and (min-width: 600px)">
<link href="highres.css" rel="stylesheet" media="screen and (min-resolution: 300dpi)">
```

### 样式表加载事件

您可以通过监视加载事件来确定何时加载样式表。类似地，您可以通过监视`error`事件来检测在处理样式表时是否发生了错误：

```html
<script>
var myStylesheet = document.querySelector('#my-stylesheet');

myStylesheet.onload = function() {
  // Do something interesting; the sheet has been loaded
}

myStylesheet.onerror = function() {
  console.log("An error occurred loading the stylesheet!");
}
</script>

<link rel="stylesheet" href="mystylesheet.css" id="my-stylesheet">
```

!!! warn "Don't try this at home"
    一旦加载了样式表及其所有导入的内容并对其进行了解析，并且在开始将样式应用于内容之前，就会触发`load`事件。

`Preload examples`

您可以在使用`rel="preload"`预加载内容中找到许多`<link rel="preload">`示例。

## 使用须知

一些有趣的新性能和安全性功能也已添加到`<link>`元素中。 举个例子：

```html
<link rel="preload" href="myFont.woff2" as="font"
      type="font/woff2" crossorigin="anonymous">
```

`preload`的`rel`值表示浏览器应预加载此资源，而`as`属性则指示要获取的特定内容类别。`crossorigin`属性指示是否应该通过CORS请求来获取资源。

其他用法说明：

- 一个`<link>`元素可以出现在[`<head>`](/zh-hans/webfrontend/<head>)或[`<body>`](/zh-hans/webfrontend/<body>)元素
中，这取决于它的链接类型是否为`body-ok`。 例如，样式表链接类型为`body-ok`，因此主体中允许使用`<link rel="stylesheet">`。但是这不是遵循的好习惯。将您的`<link>`元素与您的主体内容分开，并将它们放在[`<head>`](/zh-hans/webfrontend/<head>)中，这更有意义。
- 当使用`<link>`为站点建立图标时，并且您的站点使用内容安全策略（CSP）增强其安全性时，该策略将应用于该图标。 如果您在无法加载收藏图标时遇到问题，
请验证`Content-Security-Policy` HTTP头部的`img-src`指令是否阻止对其的访问。
- HTML和XHTML规范为`<link>`元素定义了事件处理程序，但是尚不清楚如何使用它们。
- 在XHTML 1.0下，诸如`<link>`之类的空元素需要后跟斜杠：`<link/>`。
- WebTV支持使用`rel`的`next`值来预加载文档系列中的下一页。
