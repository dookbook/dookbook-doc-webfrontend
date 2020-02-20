TOPICS: <link>
        <link> href attribute
        <link> rel attribute
        <link> type attribute
        <link> sizes attribute
        <link> media attribute
        <link> title attribute
        <link> as attribute
        <link> disabled attribute
        <link> importance attribute
        <link> integrity attribute
        <link> hreflang attribute

# HTML 外部资源链接元素：`<link>`

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
| **`rel`** | 规定当前文档与被链接文档/资源之间的**关系**。|
| *`type`* | 这个属性被用于定义链接的内容的类型。这个属性的值应该是像`text/html`，`text/css`等MIME类型。这个属性常用的用法是定义链接的样式表，最常用的值是表明了CSS的`text/css`。|
| *`sizes`* | 定义了链接属性大小，只对属性 `rel="icon"` 起作用。它可能具有以下值：<br>1. `any`，表示图标可以**按矢量格式缩放为任意大小**，例如`image/svg+xml`。<br>2. 一个空格分开的列表，每个列表的格式为`sizes="16x16"`或`sizes="16x16 32x32"`。|
| *`media`* | 规定被链接文档将显示在什么设备上。 |
| *`title`* | 此属性在`<link>`元素上具有特殊的语义。在`<link rel="stylesheet">`上使用时，它定义了**首选样式表**或**备用样式表**。错误地使用它可能会导致样式表被忽略。|
| `as` | 仅当在`<link>`元素上设置了`rel="preload"`或`rel="prefetch"`时，才使用此属性。它指定了由`<link>`加载的内容的类型，这对于内容优先级，请求匹配，正确的内容安全策略的应用以及正确的Accept request标头的设置是必需的。|
| `disabled` | 仅对于`"rel="stylesheet"`，`disabled`布尔属性指示是否应加载所描述的样式表并将其应用于文档。如果在加载HTML时在HTML中指定了`disabled`，则在页面加载期间不会加载样式表。取而代之的是，如果并且在将`disabled`属性更改为`false`或删除时，将按需加载样式表。<br>一旦加载了样式表，则对`disabled`值进行更改 属性不再与`StyleSheet.disabled`属性的值有任何关系。更改此属性的值只是简单地启用和禁用应用于文档的样式表形式。<br>这与`StyleSheet`的`disabled`属性不同。 将其更改为`true`会将样式表从文档的`document.styleSheets`列表中删除，并且切换回`false`时不会自动重新加载样式表。|
| `importance` | 指示资源的相对重要性。优先级提示使用以下值委派：<br>**`auto`**：表示没有首选项。 浏览器可以使用自己的启发式方法来确定资源的优先级。<br>**`high`**：向浏览器指示资源具有高优先级。<br>**`low`**：向浏览器指示资源属于优先级 低优先级。<br> **注意:** 如果存在`rel="preload"`或`rel="prefetch"`，则`importance`属性仅可用于`<link>`元素。|
| `integrity` | 包含内联元数据-您要告诉浏览器提取的资源（文件）的base64编码的加密哈希。 浏览器可以使用它来验证所获取的资源是否已交付，没有意外的操作。 请参阅子资源完整性。|
| `hreflang` | 此属性指示链接资源的语言。这纯粹是建议性的。允许值由BCP47确定。仅当存在`href`属性时才使用此属性。|

## `<link>` 的 `rel` 的值

| 值 | 描述 |
| :-- | :-- |
| `stylesheet` | 要导入的样式表的 URL。|
| `icon` | 导入表示该文档的图标。|
| `prefetch` | 规定应该对目标资源进行缓存。|
| `search` | 链接到针对文档的搜索工具。|
| `alternate` | 链接到该文档的替代版本（比如打印页、翻译或镜像）。|
| `author` | 链接到该文档的作者。|
| `help` | 链接到帮助文档。|
| `license` | 链接到该文档的版权信息。|
| `next` | 表示该文档是集合中的一部分，且集合中的下一个文档是被引用的文档。|
| `prev` | 表示该文档是集合中的一部分，且集合中的上一个文档是被引用的文档。|

## 包含样式表

要链接外部样式表（stylesheet），您需要在[`<head>`](/zh-hans/webfrontend/<head>)内包含一个`<link>`元素来包含样式表，请使用以下语法：

```html
<link href="style.css" rel="stylesheet">
```

这个简单的示例在`href`属性中提供了指向`stylesheet`的路径，并提供了值为`stylesheet`的`rel`属性。

## 提供替代样式表

您还可以指定其他样式表。

用户可以从浏览器菜单中选择要使用的样式表。这为用户提供了一种查看页面的多个版本的方法。

```html
<link href="default.css" rel="stylesheet" title="默认样式">
<link href="fancy.css" rel="alternate stylesheet" title="花哨">
<link href="basic.css" rel="alternate stylesheet" title="基础">
```

## 提供用于不同用法上下文的图标

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

## 通过媒体查询有条件地加载资源

您可以在`media`属性中提供媒体类型或查询；然后，只有在媒体条件满足时，才会加载此资源。例如：

```html
<link href="print.css" rel="stylesheet" media="print">
<link href="mobile.css" rel="stylesheet" media="all">
<link href="desktop.css" rel="stylesheet" media="screen and (min-width: 600px)">
<link href="highres.css" rel="stylesheet" media="screen and (min-resolution: 300dpi)">
```

## 样式表加载事件

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

!!! warn "注意"
    一旦加载了样式表及其所有导入的内容并对其进行了解析，并且在开始将样式应用于内容之前，就会触发`load`事件。
