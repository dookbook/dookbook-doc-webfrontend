TOPICS: <script>

# `<script>`

**HTML`<script>`元素** 用于嵌入或引用可执行代码；通常用于嵌入或引用JavaScript代码。 `<script>`元素也可以与其他语言一起使用，例如WebGL的GLSL着色器编程语言。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *元数据内容*，*流式内容*，*短语内容*。|
| **允许的内容** | 动态脚本，例如`text/javascript`。 |
| **标签遗漏** | 无，开始标签和结束标签都是必需的。 |
| **允许的父元素** | 接受*元数据内容*的任何元素，或接受*短语内容*的任何元素。 |
| **允许的 ARIA 角色** | 角色无 |
| **DOM 接口** | **`HTMLScriptElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `async` | 这是一个布尔型属性，指示浏览器应尽可能地异步加载脚本。<br> **错误：** 如果不存在`src`属性（即内联脚本），则不得使用此属性。 如果在这种情况下将其包括在内，它将不起作用。<br>浏览器通常会假定最坏的情况，并在HTML解析期间同步加载脚本（即`async="false"`）。<br>动态插入的脚本（使用 默认情况下，`document.createElement()`异步加载，因此要打开同步加载（即脚本以插入顺序加载），请设置`async="false"`。<br>有关浏览器支持的说明，请参见浏览器兼容性。另请参见asm.js的异步脚本 |
| `crossorigin` | 对于不通过标准CORS检查的脚本，普通脚本元素将最少的信息传递给`window.onerror`。 要允许对使用单独域的静态媒体进行站点的错误记录，请使用此属性。 有关其有效参数的更多描述性说明，请参见CORS设置属性。|
| `defer` | 此布尔属性设置为向浏览器指示脚本应在文档解析后但在触发`DOMContentLoaded`之前执行。具有`defer`属性的脚本将阻止`DOMContentLoaded`事件的发生。 触发，直到脚本加载并完成评估。<br> **错误：** 如果不存在`src`属性（例如，对于内联脚本），则不得使用此属性，在这种情况下，它将无效。 要对动态插入的脚本实现类似的效果，请改用`async="false”`。 具有`defer`属性的脚本将按照它们在文档中出现的顺序执行。
| `integrity` | 此属性包含内联元数据，用户代理可使用这些内联元数据来验证获取的资源是否已交付而没有意外的操作。 请参阅子资源完整性。
| `nomodule` | 设置此布尔属性是为了指示该脚本不应在支持ES2015模块的浏览器中执行-实际上，该属性可用于向不支持模块化JavaScript代码的旧版浏览器提供后备脚本。
| `nonce` | 加密随机数（一次使用的数字），用于将script-src Content-Security-Policy中的内联脚本列入白名单。 服务器每次发送策略时都必须生成一个唯一的随机数值。 提供一个无法猜测的随机数非常重要，因为绕开资源策略是微不足道的。 |
| `referrerpolicy` | 指示在获取脚本或脚本获取的资源时发送哪个引荐来源网址：<br>`no-referrer`：不会发送`Referer`标头。<br>`no-referrer-when-downgrade`（默认设置）：`Referer`标头不会发送到没有TLS（HTTPS）的来源。<br>`origin`：发送的引荐来源将限于引荐页的来源：其方案，主机和端口。<br >`origin-when-cross-origin`：发送到其他来源的引荐来源网址仅限于方案，主机和端口。 <br>`same-origin`：将发送相同来源的引荐来源网址，但跨域请求将不包含引荐来源信息。<br>`strict-origin`：仅当协议安全级别保持不变（例如HTTPS→HTTPS）但不将其发送到安全性较低的目的地（例如HTTPS→HTTP）时，将文档的原始位置作为引荐来源发送。<br> `strict-origin- when-cross-origin`：在执行相同来源请求时发送完整的URL，但仅在协议安全级别保持不变（例如HTTPS→HTTPS）时发送来源，不向安全性较低的目标发送任何头（例如HTTPS→HTTP）。<br>`unsafe-url`：引荐来源网址将包含来源和路径（但不包括片段，密码或用户名）。此值是不安全的，因为它将泄漏源和从受TLS保护的资源到不安全源的路径。<br> **注意：** 空字符串值（`""`）既是默认值，又是后备值不支持`referrerpolicy`。如果未在`<script>`元素上明确指定`referrerpolicy`，则它将采用更高级别的引荐来源网址策略，即在整个文档或域上设置一个。如果没有更高级别的策略，则将空字符串视为等同于`no-referrer-when-downgrade`。 |
| `src` | 此属性指定外部脚本的URI。 <br> **错误：** 如果`script`元素指定了`src`属性，则不应在其TOPICS中嵌入脚本。 它可能导致意外行为。 意外的行为是因为只有`src`属性中引用的文件中的JavaScript才会添加到HTML页面。|
| `type` | 此属性指示所表示的脚本的类型。 此属性的值将属于以下类别之一:<br>1、**省略或JavaScript MIME类型**：这表示脚本是JavaScript。 HTML5规范敦促作者忽略该属性，而不是提供冗余的MIME类型。在早期的浏览器中,这标识了嵌入式或导入的脚本语言（通过src属性）。 规范中列出了JavaScript MIME类型。<br>2、**module**：使代码被视为JavaScript模块。 脚本内容的处理不受`charset`和`Defer`属性的影响。 有关使用“模块”的信息，请参见我们的JavaScript模块指南。<br>3、**任何其他值**：嵌入的内容被视为一个数据块，浏览器将不对其进行处理。 开发人员必须使用不是JavaScript MIME类型的有效MIME类型来表示数据块。 `src`属性将被忽略。|

!!! warn "Don't try this at home"
    注意：在Firefox中，您可以通过在type属性中包含非标准的`version`参数来指定`<script>`元素中包含的JavaScript版本-
    例如`type ="text/javascript; version = 1.8"`。 。 Firefox 59中已将其删除（请参见Bug 1428745）。

## 笔记

在浏览器继续解析页面之前，将立即获取并执行不具有“ async”，“ defer”]或“ type =“ module”`属性的脚本以及内联脚本。

该脚本应该以`text/javascript` MIME类型提供，但是浏览器比较宽松，只有在脚本以图像类型（`image/*`）提供服务时，浏览器才会被阻止；
视频类型（`video/*`）；音频（`audio/*`）类型； 或`text/csv`。 如果脚本被阻止，则向该元素发送一个“错误”，否则，将发送一个“加载”事件。

## 示例

### 基本用法

这些示例说明了如何在HTML4和HTML5中使用`<script>`元素导入脚本。

```html
<!-- HTML4 -->
<script type="text/javascript" src="javascript.js"></script>

<!-- HTML5 -->
<script src="javascript.js"></script>
```

### 模块后备

支持`type`属性的`module`值的浏览器将忽略任何具有`nomodule`属性的脚本。 这使您可以使用模块脚本，同时还为不支持的浏览器提供带有`nomodule`标记的后备脚本。

```html
<script type="module" src="main.js"></script>
<script nomodule src="fallback.js"></script>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<script>` | 支持 | 支持 | 支持 |
