TOPICS: <iframe>

# `<iframe>`

**HTML Inline Frame元素（`<iframe>`）** 表示嵌套的浏览上下文，将另一个HTML页面嵌入到当前页面中。

每个嵌入式浏览上下文都有其自己的会话历史记录和文档。 嵌入其他浏览上下文的浏览上下文称为父浏览上下文。 最顶层的浏览上下文（无父上下文）通常是浏览器窗口，由Window对象表示。

!!! error ""
    由于每个浏览上下文都是完整的文档环境，因此页面中的每个`<iframe>`都需要增加内存和其他计算资源。 从理论上讲您可以根据需要使用任意数量的`<iframe>`，但是请检查性能问题.

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*嵌入内容*，*交互内容*，*可触知内容*。 |
| **允许的内容** | 后备内容，即通常不渲染但不支持`<iframe>`元素的浏览器将渲染的内容。(RSS阅读器和电子邮件客户端通常显示备用内容。) |
| **标签遗漏** | 无，开始标签和结束标签都是必需的. |
| **允许的父元素** | 任何接受*嵌入内容*的元素.|
| **允许的 ARIA 角色** | `application`, `document`, `img` |
| **DOM 接口** | **`HTMLIFrameElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `allow` | 指定`<iframe>`的功能策略. |
| `allowfullscreen` | 如果`<iframe>`可以通过调用`requestFullscreen()`方法激活全屏模式，则设置为true。<br> **注意：** 此属性被认为是旧属性，并重新定义为allow="fullscreen". |
| `allowpaymentrequest` | 如果应允许跨域的`<iframe>`调用付款请求API，则设置为true。<br>**注意：** 此属性被认为是旧属性，并重新定义为`allow =“ payment”`.
| `csp` | 为嵌入式资源强制实施的内容安全策略。 有关详细信息，请参见`HTMLIFrameElement.csp`. |
| `height` | 框架的高度(以CSS像素为单位).默认值为150. |
| `importance` | 资源在`<iframe>`的src属性中的下载优先级。 允许的值：<br>`auto（默认）`<br>无首选项。 浏览器使用自己的试探法来确定资源的优先级。<br>`high` <br>应该先下载资源，然后再下载其他优先级较低的页面资源。<br>`low` <br>应下载资源 在其他更高优先级的页面资源之后。|
| `name` | 嵌入式浏览上下文的可定位名称。 可以在[`<a>`](/zh-hans/webfrontend/<a>)，[`<form>`](/zh-hans/webfrontend/<form>)或[`<base>`](/zh-hans/webfrontend/<base>)元素的target属性中使用。[`<input>`](/zh-hans/webfrontend/<input>)或[`<button>`](/zh-hans/webfrontend/<button>)元素的`formtarget`属性；或`window.open()`方法中的windowName参数. |
| `referrerpolicy` | 指示在获取框架资源时发送哪个引荐来源网址：<br>`no-referrer`：不会发送引荐来源标头。<br>`no-referrer-when-downgrade`（默认）：`Referer`标头将会不能发送到没有TLS（HTTPS）的源。<br>`origin`：发送的引荐来源网址将限于引荐页的来源：其方案，主机和端口。<br>`origin-when-cross- origin`：发送到其他来源的引荐来源网址仅限于方案，主机和端口。<br>`same-origin`：将发送相同来源的引荐来源网址，但跨域请求将不包含引荐来源信息。<br>`strict-origin`：仅当协议安全级别保持不变（HTTPS→HTTPS）但不将其发送到安全性较弱的目标（HTTPS→HTTP）时，将文档的原点作为引荐来源发送。<br>`strict-origin-when- cross-origin`：在执行相同来源请求时发送完整的URL，仅在协议安全级别保持不变时发送来源（HTTPS→HTTPS），不向安全性较低的目标发送任何头（HTTPS→HTTP）。<br>`unsafe-url`：引荐来源网址将包含来源和路径（但不包括片段，密码或用户名）。此值是不安全的，因为它会将来源和路径从受TLS保护的资源泄漏到不安全的来源。 |
| `sandbox` | 对框架中的内容施加额外的限制。该属性的值可以为空以应用所有限制，或以空格分隔的标记以解除特定限制：<br>`allow-forms`：允许资源提交表单。如果不使用此关键字，则阻止表单提交。<br>`allow-modals`：允许资源[打开模式窗口](https://html.spec.whatwg.org/multipage/origin.html#sandboxed-modals-flag)。<br>`allow-orientation-lock`：让资源锁定屏幕方向。<br>`allow-pointer-lock`：让资源使用Pointer Lock API。<br>`allow- popups`：允许弹出窗口（例如`window.open（）`，`target ="_ blank"`或`showModalDialog（）`）。如果不使用此关键字，则弹出窗口将无提示打开。<br>`allow-popups-to-escape-sandbox`：允许沙盒文档打开新窗口，而这些窗口不会继承沙盒。例如，这可以安全地将广告沙箱化，而不必对广告链接到的页面施加相同的限制。<br>`allow-presentation`：让资源开始演示会话。<br>`allow-same-origin`：如果不使用此令牌，则资源被视为来自特殊来源，该来源始终无法执行同源策略。<br>`allow-scripts`：让资源运行脚本（但不创建弹出窗口）。 >`allow-storage-access-by-user-activation`：允许资源使用Storage Access API请求访问父级的存储功能。<br>`allow-top-navigation`：允许资源在顶层导航浏览上下文（一个名为_top的浏览上下文）。<br>`allow-top-navigation-by-user-activation`：允许资源浏览顶级浏览上下文，但前提是由用户手势启动。 <br>无需用户激活即可进行下载：<br> **关于沙箱的注意事项：** <br>当嵌入式文档具有与嵌入页面具有相同的来源，强烈建议不要同时使用allow-scripts和allow-same-origin，因为这会使嵌入的文档删除sandbox属性-使其比根本不使用sandbox属性更安全。 <br>如果攻击者可以在沙盒iframe外部显示内容，例如查看者在新标签页中打开框架，则沙盒是无用的。还应从单独的来源提供此类内容，以限制潜在的损害。<br> Internet Explorer 9和更早版本不支持sandbox属性. |
| `src` | 要嵌入页面的URL。 使用值`about：blank`嵌入一个符合同源策略的空白页面。 还要注意，以编程方式删除`<iframe>`的`src`属性（例如，通过`Element.removeAttribute()`通过）会导致在基于Chromium的Firefox（版本65）中将`about：blank`加载到Firefox的框架中 和Safari / iOS. |
| `srcdoc` | 内嵌HTML，以覆盖`src`属性。 如果浏览器不支持`srcdoc`属性，它将退回到`src`属性中的URL。 |
| `width` | 框架的宽度（以CSS像素为单位）。 默认值为300。<br> **非标准属性** |
| `mozbrowser` | 有关将其公开给Firefox中的WebExtensions的信息，请参见bug 1318532。|

使`<iframe>`的行为类似于顶级浏览器窗口。 有关详细信息，请参见浏览器API。 **仅适用于WebExtensions **。

## 脚本编写

内联框架，如`<frame>`元素，包含在`window.frames`伪数组中。

使用DOM `HTMLIFrameElement`对象，脚本可以通过contentWindow属性访问框架资源的window对象。 `contentDocument`属性是指`<iframe>`内部的`document`，与`contentWindow.document`相同。

从框架内部，脚本可以使用`window.parent`获取对其父窗口的引用。

脚本对框架内容的访问应遵循同源策略。 如果脚本是从其他来源加载的，则脚本无法访问其他窗口对象中的大多数属性，包括框架内的脚本可以访问框架的父级。 跨域通信可以使用`Window.postMessage()`实现。

## 定位和缩放

作为替换元素，可以使用`object-position和object-fit`属性调整`<iframe>`元素框中嵌入文档的位置，对齐方式和缩放比例。

## 示例

### 一个简单的`<iframe>`

动作中的`<iframe>`。创建框架后，当用户单击按钮时，其标题将显示在警报中。

```html
<iframe src="https://mdn-samples.mozilla.org/snippets/html/iframe-simple-contents.html"
        title="iframe Example 1"
        width="400"
        height="300">
</iframe>
```

### 在另一个标签中的`<iframe>`中打开链接

在此示例中，Google地图显示在框架中；

```html
<iframe id="Example2"
    title="iframe Example 2"
    width="400" height="300"
    style="border:none;"
    src="https://maps.google.com/maps?f=q&source=s_q&q=buenos+aires&sll=37.0625,-95.677068&sspn=38.638819,80.859375&t=h&hnear=Buenos+Aires,+Argentina&z=11&ll=-34.603723,-58.381593&output=embed">
</iframe>
```

## 可达性问题

借助屏幕阅读器等辅助技术进行导航的人们可以使用`iframe`上的`title`属性来标记其内容。 标题的值应简明扼要地描述嵌入内容：

```html
<iframe title="Wikipedia page for Avocados" src="https://en.wikipedia.org/wiki/Avocado"></iframe>
```

没有这个标题，他们必须进入`iframe`来确定其嵌入内容是什么。 这种上下文转换可能会造成混乱和耗时，特别是对于具有多个`<iframe>`的页面和/或如果嵌入包含诸如视频或音频之类的交互式内容时。
