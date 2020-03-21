TOPICS: <html>

# HTML 根元素: `<html>`

HTML`<html>`元素表示一个[[HTML]]文档的*根*（*顶级元素*），所以它也被称为**根元素**。所有其他元素必须是此元素的后代(子元素)。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | 无 |
| **允许内容** | 一个[`<head>`](/zh-hans/webfrontend/<head>)元素，后跟一个[`<body>`](/zh-hans/webfrontend/<body>/)元素。|
| **标签遗漏** | 如果`<html>`元素之前不是注释，则可以省略开始标签。 如果`<html>`元素之后没有立即加上注释，则可以省略end标记。 |
| **允许的父元素** | 作为文档的根元素，或是在复合文档中任意允许的子文档片段。|
| **允许的ARIA角色** | 无 |
| **DOM接口** | **`HTMLHtmlElement`** |

## HTML5骨架

```html
<!DOCTYPE html>
<html lang="zh-Hans">
<head>
  <meta charset="utf-8">
  <title>网页标题</title>
</head>
<body>
  网页内容
</body>
</html>
```

## `<html>`属性

| 属性 | 描述 |
| :--- | :--- |
| `xmlns` | 指派文档的 XML 命名空间。默认的值是`"http://www.w3.org/1999/xhtml"`。这在 XHTML 中是必要的，而在 HTML 中则是可选的。 |

## `<html>`可访问性

在`html`元素上提供具有有效[[IETF]]标识语言标记的`lang`属性，将有助于屏幕阅读技术确定要陈述的正确语言。标识语言标签应描述页面大部分内容使用的语言。
没有它，屏幕阅读器通常会默认使用操作系统的设置语言，这可能会导致错误陈述。

在`<html>`元素上有效的`lang`声明，还可以确保页面的[`<head>`](/zh-hans/webfrontend/<head>)中包含的重要元数据（例如页面的[`<title>`](/zh-han/webfrontend/<title>)）也可以正确声明。

- [MDN Understanding WCAG, Guideline 3.1 explanations](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Understandable#Guideline_3.1_%E2%80%94_Readable_Make_text_content_readable_and_understandable)
- [Understanding Success Criterion 3.1.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/meaning-doc-lang-id.html)

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<html>` | 支持 | 支持 | 支持 |
