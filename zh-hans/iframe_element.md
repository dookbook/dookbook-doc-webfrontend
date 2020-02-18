TOPICS: <iframe>
        <iframe> src attribute
        <iframe> width attribute
        <iframe> height attribute
        <iframe> name attribute
        <iframe> srcdoc attribute
        <iframe> sandbox attribute
        <iframe> seamless attribute

# HTML 内联框架元素: `<iframe>`

**HTML 内联框架 `<iframe>` 元素** 表示嵌套的浏览上下文，将另一个HTML页面嵌入到当前页面中。

每个嵌入式浏览上下文都有其自己的会话历史记录和文档。嵌入其他浏览上下文的浏览上下文称为父浏览上下文。最顶层的浏览上下文（无父上下文）通常是浏览器窗口，由Window对象表示。

!!! error ""
    由于每个浏览上下文都是完整的文档环境，因此页面中的每个`<iframe>`都需要增加内存和其他计算资源。从理论上讲您可以根据需要使用任意数量的`<iframe>`，但是请检查性能问题.

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*嵌入内容*，*交互内容*，*可触知内容*. |
| **允许的内容** | *后备内容*，即通常不渲染但不支持`<iframe>`元素的浏览器将渲染的内容。(RSS阅读器和电子邮件客户端通常显示备用内容。) |
| **标签遗漏** | 不允许，开始标签和结束标签都是必需的. |
| **允许的父元素** | 任何接受*嵌入内容*的元素.|
| **允许的 ARIA 角色** | **`application`**, **`document`**, **`img`** |
| **DOM 接口** | **`HTMLIFrameElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`src`** | 规定在 `<iframe>` 中显示的文档的 URL |
| **`width`** | 框架的宽度，默认值为300。|
| **`height`** | 框架的高度，默认值为150. |
| `name` | 规定 `<iframe>` 的名称。用于在 JavaScript 中引用元素，或者作为 [`<a>`](/zh-hans/webfrontend/<a>) 或 [`<form>`](/zh-hans/webfrontend/<form>) 元素的 `target` 属性的值，或者作为 [`<input>`](/zh-hans/webfrontend/<input>) 或 [`<button>`](/zh-hans/webfrontend/<button>) 的 `formtarget` 属性的值。 |
| `srcdoc` |规定要显示在内联框架中的页面的 HTML 内容，以覆盖`src`属性的内容。如果浏览器不支持`srcdoc`属性，它将退回到`src`属性中的URL。 |
| `sandbox` | 该属性对呈现在 `<iframe>` 框架中的内容启用一些额外的限制条件。 |
| `seamless` | 规定 `<iframe>` 看起来像是父文档中的一部分。 |

## `<iframe>` 的 `sandbox` 属性的值

如果指定了空字符串（`sandbox=""`），该属性对呈现在`<iframe>`框架中的内容启用一些额外的限制条件。

`sandbox` 属性的值既可以是一个空字符串（将会启用所有的限制），也可以是用空格分隔的一系列指定的字符串。

| 值 | 描述 |
| :-- | :-- |
| `""` | 启用所有限制条件 |
| `allow-forms` | 允许表单提交。|
| `allow-scripts` | 允许脚本执行。|
| `allow-popups` | 允许弹窗 (例如: `window.open`, `target="_blank"`, `showModalDialog`)。如果没有使用该关键字，相应的功能将自动被禁用。|
| `allow-modals` | 允许嵌入的浏览上下文打开模式窗口。|
| `allow-orientation-lock` | 允许嵌入的浏览上下文锁定屏幕方向，(比如：智能手机、平板电脑的水平朝向或垂直朝向) |
| `allow-same-origin` | 允许将内容作为普通来源对待。如果未使用该关键字，嵌入的内容将被视为一个独立的源。|
| `allow-top-navigation` | 允许嵌入的浏览上下文导航（加载）内容到顶级的浏览上下文。|

## 脚本编写

内联框架，如`<frame>`元素，包含在`window.frames`伪数组中。

使用DOM `HTMLIFrameElement`对象，脚本可以通过`contentWindow`属性访问框架资源的`window`对象。`contentDocument`属性是指`<iframe>`内部的`document`，与`contentWindow.document`相同。

从框架内部，脚本可以使用`window.parent`获取对其父窗口的引用。

脚本对框架内容的访问应遵循同源策略。如果脚本是从其他来源加载的，则脚本无法访问其他窗口对象中的大多数属性，包括框架内的脚本可以访问框架的父级。跨域通信可以使用`Window.postMessage()`实现。

## 定位和缩放

作为替换元素，可以使用`object-position`和`object-fit`属性调整`<iframe>`元素框中嵌入文档的位置，对齐方式和缩放比例。

## 一个简单的`<iframe>`

动作中的`<iframe>`。创建框架后，当用户单击按钮时，其标题将显示在警报中。

```html
<iframe src="https://mdn-samples.mozilla.org/snippets/html/iframe-simple-contents.html"
        title="iframe Example 1"
        width="400"
        height="300">
</iframe>
```

## 在另一个标签中的`<iframe>`中打开链接

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
