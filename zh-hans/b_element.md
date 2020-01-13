TOPICS: <b>
        HTMLElement

# HTML提醒注意元素：`<b>`

**HTML提醒注意元素**（**`<b>`**）用于**吸引读者的注意**到该元素的内容上（如果没有另加特别强调）。这个元素过去被认为是*粗体元素*
并且大多数浏览器仍然将文字显示为粗体。尽管如此，你不应将`<b>`元素用于显示粗体文字；替代方案是使用CSS的`font-weight`属性来创建粗体文字，或使用[`<strong>`](/zh-hans/webfrontend/<strong>)来指明需要强调的文字内容。

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*可触摸内容* |
| **允许的内容** | *短语内容* |
| **标签略写** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 可包含*短语内容*的任意元素 |
| **Permitted ARIA roles** | 任意 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

这个元素只包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 使用说明

- `<b>`应用场合如：摘要中的关键字、评论中的产品名称，或其他典型的应该加粗显示的文字（除此之外无其它特别强调）。
- 不要将`<b>`元素与[`<strong>`](/zh-hans/webfrontend/<strong>)、[`<em>`](/zh-hans/webfrontend/<em>)或
[`<mark>`](/zh-hans/webfrontend/<mark>)元素混淆。[`<strong>`](/zh-hans/webfrontend/<strong>)元素表示某些重要性的文本
[`<em>`](/zh-hans/webfrontend/<em>)强调文本，而[`<mark>`](/zh-hans/webfrontend/<mark>)元素表示某些相关性的文本。 `<b>`元素不传达这样的特殊语义信息；仅在没有其他合适的元素时使用它。
- 类似的，也不要用`<b>`元素来标记标题。如果需要表示标题，请使用[`<h1>`](/zh-hans/webfrontend/<h1>)到[`<h6>`](/zh-hans/webfrontend/<h6>)
- 标签。此外，可以通过样式表来改变这些元素的的默认样式，结果就是它们并不一定都是粗体。
- 通过在`<b>`元素上添加`class`属性来表示额外的语义信息是一个很好的方式（例如 `<b class="lead">` 来表示段落中的第一句）。这可
在样式需要变动的情况下更轻松地处理不同应用场合的`<b>`元素，无须改动HTML。
- 以前`<b>`元素就是让文本变成粗体。但从HTML4开始，不赞成标签表示带样式信息，于是`<b>`元素的含义发生了变化。
- 如果不是出于语义目的而使用`<b>`元素，那么让文本显示粗体更好的方式是使用将CSS的 `font-weight`属性设置为`"bold"`。

## 示例

```html
<p>
  This article describes several <b>text-level</b> elements.
  It explains their usage in an <b>HTML</b> document.
</p>
Keywords are displayed with the default style of the <b> element, likely in bold.
```
