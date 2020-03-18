TOPICS: <span>

# HTML 通用行内容器：`<span>`

**HTML `<span>` 元素**是*短语内容*的**通用行内容器**，并没有任何特殊语义。可以使用它来编组元素以达到某种样式意图（通过使用 `class` 或者 `id` 属性），或者这些元素有着共同的属性，
比如 `lang`。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*, *短语内容*。 |
| **允许的内容** | *短语内容* |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。 |
| **允许的父元素** | 任意可以包含 *短语内容* 或 *流式内容* 的元素。 |
| **DOM 接口** | **`HTMLSpanElement`** (在 HTML5, 之前是 **`HTMLElement`**) |

## 属性

该元素仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 使用须知

应该在没有其他合适的语义元素时才使用它。`<span>` 与 *[`<div>`](/zh-hans/webfrontend/<div>)* 元素很相似，
但 [`<div>`](/zh-hans/webfrontend/<div>) 是一个块级元素，而 `<span>` 则是行内元素。一般[`<div>`](/zh-hans/webfrontend/<div>)用于大布局框架，`<span>`用于小一部分或需小润饰的地方。

## 示例

### 简单的 `<span>`

```html
<p><span>一些文字</span></p>
```

### 带样式的 `<span>`

```html
<li><span>
  <a href="portfolio.html" target="_blank">See my portfolio</a>
</span></li>
```

```css
li span {
  background: gold;
}
```
