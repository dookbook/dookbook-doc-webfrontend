TOPICS: <meta>

# HTML元数据元素：`<meta>`

HTML的`<meta>`元素表示**元数据**，而其他HTML的与元相关的元素不能表示这些元数据，例如[`<base>`](/zh-hans/webfrontend/<base>)、[`<link>`](/zh-hans/webfrontend/<link>)、[`<script>`](/zh-hans/webfrontend/<script>)、[`<style>`](/zh-hans/webfrontend/<style>)或[`<title>`](/zh-hans/webfrontend/<title>)。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *元数据内容*。 如果存在`itemprop`属性：*流式内容*，*短语内容*。|
| **允许的内容** | 无，这是一个空元素。 |
| **标签遗漏** | 由于它是一个void元素，因此必须存在开始标签，而不能存在结束标签。 |
| **允许的父元素** | [`<meta charset>`](/zh-hans/webfrontend/<meta>_charset_attribute)，[`<meta http-equiv>`](/zh-hans/webfrontend/<meta>_http-equiv_attribute)：一个[`<head>`](/zh-hans/webfrontend/<head>)元素。 如果[`http-equiv`](/zh-hans/webfrontend/<meta>_http-equiv_attribute)不是编码声明，则它也可以位于[`<noscript>`](/zh-hans/webfrontend/<noscript>)元素内部，本身也位于[`<head>`](/zh-hans/webfrontend/<head>)元素内部。|
| **允许的 ARIA 角色** | 没有 |
| **DOM 接口** | **`HTMLMetaElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

!!! warn "注意"
    属性[`name`](/zh-hans/webfrontend/<meta>_name_attribute)对`<meta>`元素具有特定的含义，并且`itemprop`属性不能用在已经存在
    [`name`](/zh-hans/webfrontend/<meta>_name_attribute), [`http-equiv`](/zh-hans/webfrontend/<meta>_http-equiv_attribute)或[`charset`](/zh-hans/webfrontend/<meta>_charset_attribute)属性的同一个`<meta>`元素上。

| 属性 | 描述 |
| :-- | :-- |
| **[`charset`](/zh-hans/webfrontend/<meta>_charset_attribute)** | 此属性声明页面的 **[字符编码](/zh-hans/glossary/Character_Set)**。|
| **[`http-equiv`](/zh-hans/webfrontend/<meta>_http-equiv_attribute)** | 定义一个**编译指示**。该属性被命名为"*`http-equiv`(alent)*"，因为所有允许的值都是特定**HTTP头部**的名称。 |
| **[`name`](/zh-hans/webfrontend/<meta>_name_attribute)** | 该属性定义了一段文档级**元数据的名称**。如果还设置了属性`itemprop`，[`http-equiv`](/zh-hans/webfrontend/<meta>_http-equiv_attribute)或[`charset`](/zh-hans/webfrontend/<meta>_charset_attribute)之一，则不应设置此属性。 |
| **`content`** | 此属性包含[`http-equiv`](/zh-hans/webfrontend/<meta>_http-equiv_attribute)或[`name`](/zh-hans/webfrontend/<meta>_name_attribute)属性的值，具体取决于所使用的属性。|

## 注意事项

根据属性集，元数据的类型可以是以下之一：

- 如果设置了[`name`](/zh-hans/webfrontend/<meta>_name_attribute)，则它是文档级元数据，适用于整个页面。
- 如果设置了[`http-equiv`](/zh-hans/webfrontend/<meta>_http-equiv_attribute)，则它是一个编译指示，即Web服务器通常提供的有关如何提供网页的信息。
- 如果设置了[`charset`](/zh-hans/webfrontend/<meta>_charset_attribute)，则它是一个字符集声明-网页使用的字符编码。
- 如果设置了`itemprop`，则它是用户定义的元数据-对用户代理而言是透明的，因为元数据的语义是特定于用户的。

## 示例

```html
<html>
<head>
<meta charset="utf-8">
<title>Dookbook</title>
<!--定义web页面描述：-->
<meta name="description" content="开发者的日常菜谱">
<!--定义文档关键词，用于搜索引擎：-->
<meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">
<!--定义页面作者：-->
<meta name="author" content="dookbook">
</head>
<body>
<p>所有 meta 标签显示在 head 部分</p>
</body>

```
