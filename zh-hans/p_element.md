TOPICS: <p>

# HTML 段落元素：`<p>`

**HTML `<p>` 元素**（或者说 **HTML段落元素**）表示文本的一个**段落**。该元素通常表现为一整块与相邻文本分离的文本，或以垂直的空白隔离或以首行缩进。另外，`<p>` 是*块级*元素。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*可触知的内容*。 |
| **允许的内容** | *短语内容*。 |
| **标签省略** | 起始标签是必需的，结束标签在以下情形中可以省略。`<p>`元素后紧跟[`<address>`](/zh-hans/webfrontend/<address>), [`<article>`](/zh-hans/webfrontend/<article>), [`<aside>`](/zh-hans/webfrontend/<aside>), [`<blockquote>`](/zh-hans/webfrontend/<blockquote>), [`<div>`](/zh-hans/webfrontend/<div>), [`<dl>`](/zh-hans/webfrontend/<dl>), [`<fieldset>`](/zh-hans/webfrontend/<fieldset>), [`<footer>`](/zh-hans/webfrontend/<footer>), [`<form>`](/zh-hans/webfrontend/<form>), [`<h1>`](/zh-hans/webfrontend/<h1>), [`<h2>`](/zh-hans/webfrontend/<h2>), [`<h3>`](/zh-hans/webfrontend/<h3>), [`<h4>`](/zh-hans/webfrontend/<h4>), [`<h5>`](/zh-hans/webfrontend/<h5>), [`<h6>`](/zh-hans/webfrontend/<h6>), [`<header>`](/zh-hans/webfrontend/<header>), [`<hr>`](/zh-hans/webfrontend/<hr>), [`<menu>`](/zh-hans/webfrontend/<menu>), [`<nav>`](/zh-hans/webfrontend/<nav>), [`<ol>`](/zh-hans/webfrontend/<ol>), [`<pre>`](/zh-hans/webfrontend/<pre>), [`<section>`](/zh-hans/webfrontend/<section>), [`<table>`](/zh-hans/webfrontend/<table>), [`<ul>`](/zh-hans/webfrontend/<ul>)或另一个`<p>`元素；或者父元素中没有其他内容了，而且父元素不是[`<a>`](/zh-hans/webfrontend/<a>)元素。 |
| **允许的父元素** | 任何接受*流式内容*的元素 |
| **DOM接口** | **`HTMLParagraphElement`** |

## 属性

这个元素包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

!!! warn "注意"
    `<p>` 元素的 `align` 属性已被弃用，请不要使用。

## 示例

```html
<p>这是第一个段落。这是第一个段落。
   这是第一个段落。这是第一个段落。</p>
<p>这是第二个段落。这是第二个段落。
   这是第二个段落。这是第二个段落。</p>
```

## 访问性问题

使用CSS `margin`属性去改变段落之间的间隙，**不要**在段落之间插入空的段落元素或者[`<br>`](/zh-hans/webfrontend/<br>)元素。

```css
p {
  margin-bottom: 2em; /* increase white space after a paragraph */
}
```
