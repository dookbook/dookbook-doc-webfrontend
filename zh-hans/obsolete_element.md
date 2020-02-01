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
| **`<acronym>`** | HTML 缩写元素。定义**首字母缩写**或**简略语**。HTML 5 请使用 **[`<abbr>`](/zh-hans/webfrontend/<abbr>)** 代替。|
| **`<applet>`** | HTML Applet 元素。标记文档中内嵌 **[[Java]] applet**。 HTML 5 请使用 **[`<object>`](/zh-hans/webfrontend<object>)** 代替。|
| `<basefont>` | **HTML标签`<basefont></basefont>`** 用来设置文档的默认字体大小。使用`<font>`可以相对于默认字体大小进行变化。 |
| `<bgsound>` | **`<bgsound></bgsound>`** 是IE浏览器中设置网页背景音乐的元素。 |
| `<big>` | **HTML大元素 (`<big>`)** 会使字体加大一号（例如从小号(small)到中号(medium)，从大号(large)到加大(x-large)），最大不超过浏览器的最大字体。|
| `<blink>` | **HTML闪烁元素(`<blink>`)** 不是标准元素，它会使包含其中的文本闪烁。 |
| `<center>` | **HTML中央元素 (`<center>`)** 是个块级元素，可以包含段落，以及其它块级和内联元素。这个元素的整个内容在它的上级元素中水平居中(通常是 [`<body>`](/zh-hans/webfrontend/<body>))。 |
| `<command>` | **`command`元素**用来表示一个用户可以调用的命令. |
| `<content>` | **HTML `<content>` 元素**— Web 组件 的技术套件的废弃部分 — 用于 Shadow DOM 内部作为 insertion point，并且不可用于任何正常的 HTML，现在已被 [`<slot>`](/zh-hans/webfrontend/<slot>) 元素代替，它在 DOM 中创建一个位置，Shadow DOM 会插入这里。 |
| `<dir>` | 已废弃的**HTML目录元素（`<dir>`）** 被作为一个文件和/或文件夹的目录的容器，可能还有 用户代理 应用的样式与图标. |
| `<element>` | **`<element>`元素** 被定义在最新的 HTML DOM 元素中。`</element>`. |
| `<font>` | **HTML字形元素（`<font>`）** 定义了该内容的字体大小、顏色与表现。. |
| `<frame>` | **`<frame>`是HTML元素**，它定义了一个特定区域，另一个HTML文档可以在里面展示。帧应该在`<frameset>`中使用. |
| `<frameset>` | **`<frameset>`** 是一个用于包含`<frame>`的HTML元素。 |
| **`<image>`** | HTML 图片元素。曾经是一个试验性的元素，用来显示图片。它从未被实现过，请使用标准的 **[`<img>`](/zh-hans/webfrontend/<img>)** 元素。 |
| `<isindex>` | **`<isindex>`元素** 的作用是使浏览器显示一个对话框，提示用户输入单行文本。在W3C的规范中建议，`<isindex>`元素最好被放置在 [`<head>`](/zh-hans/webfrontend/<head>) 标签块内，但是对于浏览器来说，`<isindex>`标签在页面任何位置都没有关系。 |
| `<keygen>` | **HTML`<keygen>`元素** 是为了方便生成密钥材料和提交作为 HTML form 的一部分的公钥.这种机制被用于设计基于 Web 的证书管理系统。按照预想，`<keygen>` 元素将用于 HTML 表单与其他的所需信息一起构造一个证书请求，该处理的结果将是一个带有签名的证书。 |
| `<listing>` | **HTML列表元素 (`<listing>`)** 渲染了开始和结束标签之间的文本，而不会解释 HTML，并使用等宽字体。HTML2 标准建议，当一行不超过 132 个字符时，不应该将其拆开。 |
| `<marquee>` | **HTML选框元素（`<marquee>`）** 用来插入一段滚动的文字。你可以使用它的属性控制当文本到达容器边缘发生的事情。 |
| `<menuitem>` | 用户可以通过**HTML`<menuitem>`元素** 生成一个弹出式菜单。这包括上下文菜单，以及按钮可能附带的菜单。 |
| `<multicol>` | **HTML`<multicol>` 元素** 是一个实验元素，旨在允许多列布局。它从来没有任何显着的牵引力，并没有在任何主流浏览器中实现。`</multicol>` |
| `<nextid>` | **`<nextid>`** 是一个过时的HTML元素，用于使NeXT Web设计工具为其锚点生成自动的NAME标签。 |
| `<nobr>` | **HTML`<nobr>`元素** 阻止文本自动拆分成新行，所以它展示为长的一行，可能还需要滚动。这个标签不是标准的 HTML，并且不应该使用。反之应该使用 CSS 属性 |
| `<noembed>` | **`<noembed>`** 元素是个废除的和不标准的方式，用于向不支持 [`<embed>`](/zh-hans/webfrontend/<embed>) ，或者不支持作者希望的 嵌入式内容 的浏览器提供替代（或者“后备”）内容。这个元素在 HTML 4.01 起废除，以支持后备 |
| `<noframes>` | **`<noframes>`** 是个 HTML 元素，用于支持不支持 `<frame>` 元素的浏览器，或者这样配置的浏览器。 |
| `<plaintext>` | **HTML纯文本元素 (`<plaintext>`)** 将起始标签后面的任何东西渲染为纯文本，不会解释为 HTML。它没有闭合标签，因为任何后面的东西都会看做纯文本。 |
| `<shadow>` | **HTML `<shadow>` 元素** — Web 组件技术套件的废弃部分 — 目的是用作 Shadow DOM insertion point。如果你在 shadow host 下面创建了多个 shadow root，你就可能已经使用了它。在正常的 HTML 没有任何用处。 |
| `<spacer>` | **`<spacer>`** 是过时的 HTML 元素，它可以向页面插入间隔。它由 Netscape 设计，用于实现单像素布局图像的相同效果，Web 设计师用它来向页面添加空白，而不需要实际使用图片。 但是，`<spacer>` 不再受任何主流浏览器支持，并且相同效果可以简单由 CSS 实现。 |
| `<strike>` | **HTML `<strike>` 元素**（或者 HTML 删除线元素）在文本上放置删除线。 |
| `<tt>` | **HTML电报文本元素 (`<tt>`)** 产生一个内联元素，使用浏览器内置的 monotype 字体展示。这个元素用于给文本排版，使其等宽展示，就像电报那样。使用 [`<code>`](/zh-hans/webfrontend/<code>) 元素来展示等宽文本可能更加普遍。 |
| `<xmp>` | **`<xmp>`** 标签之间的内容不会被当作文档内容解析，而会被用等宽字体直接呈现。HTML2 规范建议，本标签中的内容应该具有足够容纳每行80个字母的宽度。 |
