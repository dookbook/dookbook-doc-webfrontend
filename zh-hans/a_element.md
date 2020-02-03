TOPICS: <a>
        HTMLAnchorElement
        <a> href attribute
        <a> target attribute
        <a> rel attribute
        <a> download attribute
        <a> type attribute
        <a> hreflang attribute
        <a> ping attribute

# HTML 锚元素：`<a>`

**HTML `<a>` 元素**（或称**锚元素**）它与`href`属性一起，可以创建通向其他网页、文件、同一页面内的不同位置、电子邮件地址或任何其他URL的**超链接**。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*、*短语内容*、*交互内容*、*可触摸内容*。|
| **允许的内容** | 可见的，包含*流式内容*（不包括*交互内容*）或*短语内容*。|
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | *流式内容*或*短语内容*的元素，`<a>`元素除外。|
| **允许的 ARIA 角色** | `button`, `checkbox`, `menuitem`, `menuitemcheckbox`, `menuitemradio`, `option`, `radio`, `switch`, `tab`, `treeitem` |
| **DOM 接口** | **`HTMLAnchorElement`** |

## 属性

该元素的属性包含[HTML全局属性](/zh-hans/webfrontend/HTML_Global_attributes)。

| 属性 | 描述 |
| :-- | :-- |
| **`href`** | 包含**超链接**指向的URL或URL片段(fragment)。URL不限于基于HTTP的文档 (*`http:`*)，也可以使用浏览器支持的任何协议。例如，*[`file:`](https://en.wikipedia.org/wiki/File_URI_scheme)*、*`ftp:`*、*`tel:`* 和 *`mailto:`*。|
| **`target`** | 该属性指定在**何处显示**链接的资源。取值为标签页(tab)、窗口(window)、或[`<iframe>`](/en/webfrontend/<iframe>)等浏览上下文的名称或关键词。以下关键字具有特殊的意义：*`_self`* (*默认*)，*`_blank`*，*`_parent`*，*`_top`*。 |
| **`rel`** | 该属性指定了目标对象到链接对象的**关系**。该值是*空格分隔*的列表类型值。 |
| **`download`** | 此属性指示浏览器**下载**URL而不是导航到它，因此将提示用户将其保存为本地文件。如果属性有一个值，那么此值将在下载保存过程中作为预填充的文件名（如果用户需要，仍然可以更改文件名）。此属性对允许的值没有限制，但是 *`/`* 和 *`\`*会被转换为 *下划线* (*`_`*)。大多数文件系统限制了文件名中的标点符号，因此浏览器将相应地调整建议的文件名。 |
| `type` | 该属性指定目标URL链接的**媒体类型** (**[[MIME]]类型**)。其仅提供建议，并没有内置的功能。|
| `hreflang` | 该属性用于指定**链接文档的人类语言**。其仅提供建议，并没有内置的功能。允许的值取决于*[BCP47](http://www.ietf.org/rfc/bcp/bcp47.txt)* |
| `ping` | 包含一个以*空格分隔*的URL列表，当**跟随**超链接时，将由浏览器(在后台)发送带有正文PING的`POST`请求。通常用于**跟踪** |
| `referrerpolicy` | 表明在获取URL时发送哪个提交者（referrer）:<br><br>`"no-referrer"` 表示 `Referer:` 头将不会被发送。<br>`"no-referrer-when-downgrade"` 表示当从使用HTTPS的页面导航到不使用 TLS(HTTPS)的来源 时不会发送 `Referer:` 头。如果没有指定策略，这将是用户代理的默认行为。<br>`"origin"` 表示 referrer将会是页面的来源，大致为这样的组合：主机和端口（不包含具体的路径和参数的信息）。<br>`"origin-when-cross-origin"` 表示导航到其它源将会限制为这种组合：主机 + 端口，而导航到相同的源将会只包含 referrer的路径。<br>`'strict-origin-when-cross-origin'`<br>`"unsafe-url"` 表示 referrer将会包含源和路径（domain + path）（但是不包含密码或用户名的片段）。这种情况是不安全的，因为它可能会将安全的URL数据泄露给不安全的源。 |

### `target`属性

!!! warn "Note"
    使用`target`时，考虑添加**`rel="noopener"`**以防止针对*`window.opener`* API的恶意行为。

| 属性值 | 描述 |
| :-- | :-- |
| **`_self`** | (*默认*) 在**当前页面**加载，即跳转到当前浏览上下文中。|
| **`_blank`** | 在**新窗口或标签页**加载，即跳转到一个新的未命名的浏览器上下文。|
| **`_parent`** | 在**当前的父级浏览器上下文**加载。如果没有父级浏览上下文，此选项的行为方式与`_self`相同。|
| **`_top`** | 在**顶级浏览器上下文**加载。(即最高级浏览器上下文)。如果没有顶级浏览上下文，此选项的行为方式与`_self`相同。|

### `download`属性

!!! warn "注意"
    此 *`download`*属性仅适用于**同源**URL，但是*`file:`*除外。

尽管HTTP(s) URL需要位于同源中，但是可以使用 **`blob:`** URL和 **`data:`** URL，以方便用户下载使用JavaScript生成的内容（例如使用在线绘图Web应用程序创建的照片）。

如果HTTP头部中的 **`Content-Disposition`**赋予了一个不同于此属性的文件名，HTTP头属性优先于此属性。如果`Content-Disposition`被设置为 **`inline`**，
那么Firefox浏览器优先考虑HTTP头部`Content-Disposition`，而Chrome浏览器优先考虑`download`属性。

## 链接到外部地址

```html
<a href="http://dookbook.info/">外部链接</a>
```

## 链接到本页的某个部分

```html
<!-- 链接到本页的某个部分 id="attr-href" -->
<a href="#attr-href">链接的显示文本</a>
```

## Email链接

点击该按钮或链接，可将用户的电子邮件程序打开，开始发送新邮件。这里有一个简单的例子：

```html
<a href="mailto:dookbook@zhiliaokeji.com">发送邮件给Dookbook</a>
```

有关`mailto:`URL方案的更多细节，比如如何包含主题，正文，或其他预定内容，参考[RFC 6068](https://tools.ietf.org/html/rfc6068)。

## 电话链接

提供电话链接有助于用户查看连接到手机的网络文档和笔记本电脑。

```html
<a href="tel:+8612312345678">+86 123 1234 5678</a>
```

关于`tel:`更详细的语法请参考[RFC 3966](https://tools.ietf.org/html/rfc3966)。

## 在新的浏览环境打开链接

!!! warn "安全和隐私问题"
    使用**`target="_blank"`**链接到另一个页面将在与页面相同的进程上运行新页面。
    如果新页面执行昂贵的JavaScript，那么页面的性能可能会受到影响。要避免这种情况，请使用`rel=noopener`。

```html
<!-- 在新的标签页或浏览器窗口打开链接 -->
<a href="https://dookbook.info/" target="_blank" rel="noreferrer noopener">External Link</a>
```

## 图片链接

```html
<!-- 创建一个可点击的图片 -->
<a href="https://dookbook.info">
  <img src="https://dookbook.info/static/img/logo-tail.svg" alt="Dookbook logo" />
</a>
```

## 下载链接

```html
<a href="<下载地址>" download="<默认文件名>" title="<文本提示>">下载链接文本</a>
```

## 保存`<canvas>`为PNG格式

如果你想允许用户下载一个HTML画布 ([`<canvas>`](/zh-hans/webfrontend/<canvas>)元素)，你可以创建一个下载属性和画布数据作为文件URL链接图像：

```javascript
var link = document.createElement('a');
link.innerHTML = 'download image';

link.addEventListener('click', function(ev) {
    link.href = canvas.toDataURL();
    link.download = "my_painting.png";
}, false);

document.body.appendChild(link);
```

## 无障碍建议

锚点标签常常通过将`href`属性设置为`"#"` 或 `"javascript:void(0)"` 来创造一个能阻止页面刷新的伪按钮的方式被滥用。 这些属性值会在拖动或
复制链接时导致意外行为，在新窗口或新标签打开链接，加入书签以及JavaScript仍在下载时会出现错误或被禁用。这也会向辅助技术（如屏幕阅读器）传达不正确的语义。在这些情况下，推荐使用
[`<button>`](/zh-hans/webfrontend/<button>) 来代替。通常情况下，您应该只将锚点用于正常的URL导航。
