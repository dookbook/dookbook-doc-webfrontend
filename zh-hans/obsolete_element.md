TOPICS: <acronym>
        <applet>
        <basefont>
        <bgsound>
        <big>
        <blink>
        <center>
        <command>
        <content>
        <dir>
        <element>
        <font>
        <frame>
        <frameset>
        <image>
        <isindex>
        <keygen>
        <listing>
        <marquee>
        <menuitem>
        <multicol>
        <nextid>
        <nobr>
        <noembed>
        <noframes>
        <plaintext>
        <shadow>
        <spacer>
        <strike>
        <tt>
        <xmp>

# 过时和弃用的 HTML 元素

!!! error ""
    警告：下面这些旧的 HTML 元素已被弃用，且不应再被使用。千万不要在新的项目中使用它们，并且要尽快替换旧项目中的残余。在此列出，仅供参考。

| 元素 | 描述 |
| :--- | :--- |
| **`<acronym>`** | **HTML 缩写元素**。定义**首字母缩写**或**简略语**。HTML 5 请使用 **[`<abbr>`](/zh-hans/webfrontend/<abbr>)** 代替。|
| **`<applet>`** | HTML Applet 元素。标记文档中内嵌 **[[Java]] applet**。 HTML 5 请使用 **[`<object>`](/zh-hans/webfrontend<object>)** 代替。|
| `<basefont>` | **HTML标签`<basefont></basefont>`** 用来设置文档的默认字体大小。使用`<font>`可以相对于默认字体大小进行变化。 |
| `<bgsound>` | **`<bgsound></bgsound>`** 是IE浏览器中设置网页背景音乐的元素。 |
| `<big>` | **HTML 大元素 (`<big>`)** 会使字体加大一号（例如从小号(`small`)到中号(`medium`)，从大号(`large`)到加大(`x-large`)），最大不超过浏览器的最大字体。对于那些不支持`<big>`标签的浏览器来说，它经常被解释成粗体。在HTML5中不支持。|
| `<blink>` | **HTML 闪烁元素(`<blink>`)** 不是标准元素，它会使包含其中的文本闪烁。 |
| `<center>` | **HTML 居中元素 (`<center>`)** 是个块级元素，可以包含段落，以及其它块级和内联元素。这个元素的整个内容在它的上级元素中水平居中(通常是 [`<body>`](/zh-hans/webfrontend/<body>))。 |
| `<command>` | **`command`元素**用来表示一个用户可以调用的命令（比如单选按钮、复选框或按钮）。 |
| `<content>` | **HTML `<content>` 元素**— Web 组件技术套件的废弃部分 — 用于 Shadow DOM 内部作为insertion point，并且不可用于任何正常的HTML，现在已被 [`<slot>`](/zh-hans/webfrontend/<slot>) 元素代替，它在 DOM 中创建一个位置，Shadow DOM 会插入这里。 |
| **`<dir>`** | **HTML 目录元素**。被作为一个文件和/或文件夹的**目录的容器**，可能还有用户代理设置的样式与图标。请使用 **[`<ul>`](/zh-hans/webfrontend/<ul>)** 代替。 |
| `<element>` | **`<element>`元素** 被定义在最新的 HTML DOM 元素中。 |
| `<font>` | **HTML 字形元素（`<font>`）** 定义该内容的字体大小、顏色与表现。 |
| **`<frameset>`** | 定义一个**框架集**。它用来组织一个或者多个 **`<frame>`** 元素。HTML5 请使用 **[`<iframe>`](/zh-hans/webfrontend/<iframe>)** 代替。 |
| **`<frame>`** | 定义 **`<frameset>`** 中的子窗口（框架）。HTML5 请使用 **[`<iframe>`](/zh-hans/webfrontend/<iframe>)** 代替。 |
| **`<noframes>`** | 用于支持不支持 **`<frame>`** 元素的浏览器，或者这样配置的浏览器。在 HTML5 中完全过时。 |
| **`<image>`** | **HTML 图片元素**。曾经是一个试验性的元素，用来显示图片。它从未被实现过，请使用标准的 **[`<img>`](/zh-hans/webfrontend/<img>)** 元素。 |
| **`<isindex>`** | 使浏览器显示一个**对话框**，提示用户输入**单行文本**。HTML5 请使用 **[`<input>`](/zh-hans/webfrontend/<input>)** 代替。 |
| **`<keygen>`** | **HTML 密钥生成元素**。为了方便**生成密钥**和作为 *HTML 表单*中**公钥的提交**。这种机制被用于设计基于Web的证书管理系统。按照预想，它将用于 HTML 表单与其他的所需信息一起构造一个证书请求，该处理的结果将是一个带有签名的证书。 |
| **`<listing>`** | 渲染开始和结束标签之间的文本，而不会解释 HTML，并使用等宽字体*`monotype`* 呈现。HTML2 标准建议，当一行不超过132个字符时，不应该将其拆开。请使用 **[`<pre>`](/zh-hans/webfrontend/<pre>)** 或 **[`<samp>`](/zh-hans/webfrontend/<samp>)** 元素替代。 |
| `<marquee>` | **HTML 选框元素（`<marquee>`）** 用来插入一段滚动的文字。你可以使用它的属性控制当文本到达容器边缘发生的事情。 |
| **`<menuitem>`** | **HTML 菜单选项元素**。定义一个**弹出式菜单选项**。更多可参见 **[`<menu>`](/zh-hans/webfrontend/<menu>)**。 |
| `<multicol>` | **HTML`<multicol>` 元素** 是一个实验元素，旨在允许多列布局。它从来没有任何显着的牵引力，并没有在任何主流浏览器中实现。|
| `<nextid>` | **`<nextid>`** 是一个过时的HTML元素，用于使NeXT Web设计工具为其锚点生成自动的NAME标签。 |
| `<nobr>` | **HTML`<nobr>`元素** 阻止文本自动拆分成新行，所以它展示为长的一行，可能还需要滚动。这个标签不是标准的 HTML，并且不应该使用。反之应该使用 CSS 属性。 |
| `<noembed>` | **`<noembed>`** 元素是个废除的和不标准的方式，用于向不支持 [`<embed>`](/zh-hans/webfrontend/<embed>) ，或者不支持作者希望的 嵌入式内容 的浏览器提供替代（或者“后备”）内容。这个元素在 HTML 4.01 起废除,在HTML5中请使用 [`<object>`](/zh-hans/webfrontend/<object>) 来替代。 |
| **`<plaintext>`** | HTML 纯文本元素。将从标签开始以后的所有文本渲染为**纯文本**，不会解释为 HTML。它没有闭合标签，因为任何后面的东西都会看做纯文本。请使用 **[`<pre>`](/zh-hans/webfrontend/<pre>)** 替代。|
| `<shadow>` | **HTML `<shadow>` 元素** — Web 组件技术套件的废弃部分 — 目的是用作 Shadow DOM insertion point。如果你在 shadow host 下面创建了多个 shadow root，你就可能已经使用了它。在正常的 HTML 没有任何用处。 |
| **`<spacer>`** | **HTML 空格元素**。可以向页面插入空格。推荐使用 HTML **`&nbsp;`** 或 [[CSS]] 属性。 |
| **`<strike>`** | **HTML 删除线元素**。如果是标记删除文本，推荐使用 **[`<del>`](/zh-hans/webfrontend/<del>)** 代替；如果是在文本上放置删除线的样式，推荐使用 CSS 属性 **`text-decoration: line-through`** 代替；如果是标记不再准确或不再相关的文本，推荐使用 **[`<s>`](/zh-hans/webfrontend/<s>)** 代替。 |
| **`<tt>`** | **HTML 电报文本或打字机文本元素**。创建一个使用浏览器内置的 *`monotype`* 等宽字体展示的内联元素。这个元素用于给文本**排版**，就像电报那样。请使用 [[CSS]]代替。 |
| **`<xmp>`** | **HTML 示例元素**。 开始和结束标签之间的内容**不会被当作 HTML 文档内容解析**，而会被用等宽字体 *`monotype`* 直接呈现。*HTML 2* 规范建议，本标签中的内容应该具有足够容纳每行 *80* 个字母的宽度。请使用 **[`<pre>`](/zh-hans/webfrontend/<pre>)** 或 **[`<samp>`](/zh-hans/webfrontend/<samp>)** 代替。 |
