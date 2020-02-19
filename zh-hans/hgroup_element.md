TOPICS: <hgroup>

# `<hgroup>`

**HTML`<hgroup>`元素** 代表文档部分的多级标题。 它对一组[`<h1>`](/zh-hans/webfrontend/<h1>)~[`<h6>`](/zh-hans/webfrontend/<h6>)元素进行分组。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | *流式内容*，*标题内容*，*可触知的内容*。|
| **允许的内容** | 一个或多个[`<h1>`](/zh-hans/webfrontend/<h1>)、[`<h2>`](/zh-hans/webfrontend/<h2>)、[`<h3>`](/zh-hans/webfrontend/<h3>)、[`<h4>`](/zh-hans/webfrontend/<h4>)、[`<h5>`](/zh-hans/webfrontend/<h5>)和或[`<h6>`](/zh-hans/webfrontend/<h6>)。|
| **标签遗漏** | 没有，开始标签和结束标签都是必需的。|
| **允许的父元素** | 接受*流式内容*的任何元素。|
| **允许的ARIA角色** | `tab`, `presentation` |
| **DOM 接口** | **`HTMLElement`** |

## 属性

该元素仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 使用说明

!!! warn "Don't try this at home"
    `<hgroup>`元素已从HTML5（W3C）规范中删除，但仍处于HTML的WHATWG版本中。 不过，大多数浏览器都可部分实现该功能，因此不太可能消失。
    鉴于`<hgroup>`元素的主要目的是影响标题由**HTML规范大纲算法定义的显示方式，但是HTML大纲算法未在任何浏览器中实现**，因此实际上，`<hgroup>`语义只是理论上的。
    HTML5（W3C）规范提供了有关如何在不使用`<hgroup>`的情况下标记副标题，字幕，替代标题和标语的建议。

`<hgroup>`元素允许将文档节的主要标题与任何辅助标题（例如子标题或替代标题）组合在一起，以形成多层标题。

换句话说，`<hgroup>`元素可防止其任何辅助（如：[`<h1>`](/zh-hans/webfrontend/<h1>)-[`<h6>`](/zh-hans/webfrontend/<h6>)）子级在大纲中创建自己的单独部分，
就像[`<h1>`](/zh-hans/webfrontend/<h1>)-[`<h6 >`](/zh-hans/webfrontend/<h6>)元素通常不是（`<hgroup>`）的子元素。

因此，在由HTML规范中定义的HTML轮廓算法产生的抽象轮廓中，整个`<hgroup>`构成一个逻辑标题，
而整个[`<h1>`](/zh-hans/webfrontend/<h1>) ~ [`<h6>`](/zh-hans/webfrontend/<h6>)作为 `<hgroup>`一个多级单元进入大纲，以在抽象大纲中包含该单个逻辑标题。

为了产生这样的轮廓的任何（非抽象的）渲染视图，必须在渲染工具的设计中做出一些选择，以关于如何表达`<hgroup>`标题以传达其多层次性质的方式。
在呈现的轮廓中可能会以多种方式显示`<hgroup>`。 例如：

- `<hgroup>`可能会在呈现的轮廓中以冒号和空格（“：”）或其他此类标点符号显示在主要标题之后和第一个次要标题之前（以及相同或相似的标点符号位于任何其他次要标题之前）。
- `<hgroup>`可能会显示在渲染的轮廓中，其中主标题后跟辅助标题周围的括号。

考虑以下HTML文档：

```html
<!DOCTYPE html>
<title>HTML Standard</title>
<body>
  <hgroup id="document-title">
    <h1>HTML</h1>
    <h2>Living Standard — Last Updated 12 August 2016</h2>
  </hgroup>
  <p>Some intro to the document.</p>
  <h2>Table of contents</h2>
  <ol id=toc>...</ol>
  <h2>First section</h2>
  <p>Some intro to the first section.</p>
</body>
```

该文档的渲染轮廓可能如下所示：

![outline-colon](/media/webfrontend__outline-colon.png)

也就是说，渲染的轮廓可能显示主要标题HTML，后跟冒号和空格，然后显示次要标题Living Living-Last Updated 2016年8月12日。

或者，该文档的渲染轮廓看起来可能如下所示：

![outline-paren](/media/webfrontend__outline-paren.png)

呈现的轮廓，包含一个`<hgroup>`元素，并在副标题周围添加了括号

也就是说，渲染的轮廓可能会显示主要标题HTML，然后是括号中显示的次要标题：（生活标准-2016年8月12日最后更新）。

## 示例

```html
<hgroup id="document-title">
  <h1>HTML</h1>
  <h2>Living Standard — Last Updated 12 August 2016</h2>
</hgroup>
```
