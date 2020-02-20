TOPICS: title attribute

# HTML 全局属性: `title`

[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes) **`title`** 规定关于元素的额外信息。这些信息通常会在鼠标移到元素上时显示一段工具提示文本。

一些典型的用途：

- **链接**：被链接文档的标题或描述
- **媒体元素**，例如图像：描述或关联信息
- **段落**：脚注或者相关的评论
- **引用**：作者信息，以及其他

额外的语义可以附加到 [`<link>`](/zh-hans/webfrontend/<link>)、[`<abbr>`](/zh-hans/webfrontend/<abbr>)、
[`<input>`](/zh-hans/webfrontend/<input>) 和 [`<menuitem>`](/zh-hans/webfrontend/<menuitem>)
元素的 **`title`** 属性。

## 多行标题

`title`属性可以包含几行。每个`U+000A换行` (`LF`)字符代表一个换行符。一些谨慎必须采取，因为这意味着以下呈现跨两行:

```html
<p>Newlines in <code>title</code> should be taken into account,
like <abbr title="This is a
multiline title">example</abbr>.</p>
```

## 标题属性继承

如果一个元素没有`title`属性，那么它将从父节点继承该属性，而父节点又可能从父节点继承该属性，依此类推。

如果这个属性被设置为空字符串，这意味着它的父节点`title`是不相关的，不应该在这个元素的工具提示中使用。

```html
<div title="CoolTip">
  <p>Hovering here will show “CoolTip”.</p>
  <p title="">Hovering here will show nothing.</p>
</div>
```

## 参见

- 所有HTML[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).
- 反映这个属性的 `HTMLElement.title`
