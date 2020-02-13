TOPICS: <div>

# HTML 无语义区块元素：`<div>`

**HTML 无语义区块元素** (**`<div>`**)是一个*流式内容*的通用容器。它在语义上不代表任何特定类型的内容。它可以被用来对其它元素进行分组，一般用于样式化相关的需求
（使用 `class` 或 `id` 属性) 或者对不同语言的内容进行分组 (使用 *`lang`* 属性)。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*可触知内容*。 |
| **允许的内容** | *流式内容*。 <br>或 (在 *[[WHATWG]]* HTML 中): 如果父元素是 **[`<dl>`](/en/webfrontend/<dl>)** 元素：一个或多个 **[`<dt>`](/en/webfrontend/<dt>)** 元素接着一个或多个 **[`<dd>`](/en/webfrontend/<dd>)** 元素，ye 也可以穿插 *[`<script>`](/en/webfrontend/<script>)* 和 *[`<template>`](/en/webfrontend/<template>)* 元素。 |
| **标签省略** | 不允许，开始和结束标签都是必需的。 |
| **允许的父元素** | 任何接受*流式内容*的元素。<br>或 (在 *[[WHATWG]]* HTML 中): **[`<dl>`](/en/webfrontend/<dl>)** 元素。 |
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLDivElement`** |

## 属性

该元素包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

!!! warn "`align` 属性已废弃"
    `align` 属性已被废弃；请不要继续使用。可以使用CSS属性或者想CSS 网格或者CSS弹性盒子的技术来在网页内对齐和定位`<div>`元素。

## 使用须知

它应该在没有任何其它语义元素(比如 *[`<article>`](/zh-hans/webfrontend/<article>)* 或 *[`<nav>`](/zh-hans/webfrontend/<nav>)*)可用时才使用。

## 示例

### 简单示例

```html
<div>
  <p>这里可以是任何内容，比如 &lt;p&gt;, &lt;table&gt;，一切由你作主。</p>
</div>
```

### 带样式的示例

这个示例创建了一个使用CSS样式来渲染的阴影区块`<div>`。请注意`class`属性的用法。

```html
<div class="shadowbox">
  <p>Here's a very interesting note displayed in a
  lovely shadowed box.</p>
</div>
```

```css
.shadowbox {
  width: 15em;
  border: 1px solid #333;
  box-shadow: 8px 8px 5px #444;
  padding: 8px 12px;
  background-image: linear-gradient(180deg, #fff, #ddd 40%, #ccc);
}
```
