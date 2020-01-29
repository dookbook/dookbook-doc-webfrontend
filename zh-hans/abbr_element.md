TOPICS: <abbr>

# `<abbr>`

**HTML缩写元素（`<abbr>`）** 代表简称或缩写。 可选的title属性可以提供缩写的扩展名或说明。 如果存在，标题必须包含此完整描述，而不能包含其他任何内容。

|  |  |
| :-- | :-- |
| **内容分类** | 流程内容，措辞内容，可触知内容 |
| **允许的内容** | 短语内容 |
| **标签遗漏** | 没有，开始标签和结束标签都是必需的。 |
| **允许的父元素** | 任何接受短语内容的元素 |
| **允许的 ARIA 角色** | 任何 |
| **DOM 接口** |**`HTMLElement`** |

## 属性

该元素仅支持[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。
当与`<abbr>`元素一起使用时，`title`属性具有特定的语义含义。 它必须包含完整的人类可读描述或缩写的扩展。 当鼠标单击时，此文本通常由浏览器显示为工具提示，光标悬停在元素上。

您使用的每个<abbr>元素都独立于所有其他元素。 为其中一个提供“标题”不会自动将相同的扩展文本附加到具有相同内容文本的其他文本。

## 使用说明

### 典型用例

当然不需要使用`<abbr>`标记所有的缩写。 但是在某些情况下，这样做有帮助：

- 当使用缩写并且您想在文档内容流之外提供扩展名或定义时，请使用带有适当标题的`<abbr>`。
- 要定义读者可能不熟悉的缩写，请使用`<abbr>`以及提供该定义的title属性或内联文本来呈现该术语。
- 当需要在语义上标注缩写的出现时，使用`<abbr>`元素很有用。 依次将其用于样式或脚本编写目的。
- 您可以结合使用`<abbr>`和[`<dfn>`](/zh-hans/webfrontend/<dfn>)来建立术语的定义，这些术语是缩写或首字母缩写。 请参见下面的示例定义缩写。

### 语法注意事项

在具有[语法编号](https://en.wikipedia.org/wiki/grammatical%20number)的语言中（即，项数影响句子语法的语言），请在您的中使用相同的语法编号
`title`属性位于您的`<abbr>`元素内部。 这在具有两个以上数字的语言（例如阿拉伯语）中尤其重要，但在英语中也与此相关。

## 默认样式

此元素的目的纯粹是为了方便作者，所有浏览器默认情况下都以内联方式显示它（`display：inline`），尽管其默认样式在一种浏览器之间有所不同：

- 某些浏览器（例如Internet Explorer）的样式与[`<span>`](/zh-hans/webfrontend/<span>)元素的样式不同。
- Opera，Firefox和其他一些元素的元素上添加了虚线下划线。
- 一些浏览器不仅添加了虚线下划线，而且还大写了下划线。 为了避免这种样式，在CSS中添加`font-variant：none`之类的东西可以解决这种情况。

## 示例

### 在语义上标记缩写

要标记缩写而不提供扩展名或描述，只需使用不带任何属性的`<abbr>`，如本例所示。

```html
<p>Using <abbr>HTML</abbr> is fun and easy!</p>
```

### 样式缩写

您可以使用CSS设置用于缩写的自定义样式，如以下简单示例所示。

```html
<p>Using <abbr>CSS</abbr>, you can style your abbreviations!</p>
```

```css
abbr {
  font-variant: all-small-caps;
}
```

### 提供扩展

添加`title`属性可让您提供缩写或首字母缩写的扩展名或定义。

```html
<p>Ashok's joke made me <abbr title="Laugh Out Loud">LOL</abbr> big
time.</p>
```

### 定义缩写

您可以将`<abbr>`与[`<dfn>`](/zh-hans/webfrontend/<dfn>)一起使用，以更正式地定义缩写，如下所示。

```html
<p><dfn id="html"><abbr title="HyperText Markup Language">HTML</abbr>
</dfn> is a markup language used to create the semantics and structure
of a web page.</p>

<p>A <dfn id="spec">Specification</dfn>
(<abbr title="Specification">spec</abbr>) is a document that outlines
in detail how a technology or API is intended to function and how it is
accessed.</p>
```

请参阅“如何标记缩写并使它们易于理解”一文中的更多深入示例。

## 可达性问题

第一次在页面上完全使用首字母缩写词或缩写词时，会有助于人们理解它，特别是在内容是技术或行业术语的情况下。

例子

```html
<p>JavaScript Object Notation (<abbr>JSON</abbr>) is a lightweight data-interchange format.</p>
```

这对于不熟悉内容中讨论的术语或概念的人，对语言不熟悉的人以及具有认知问题的人特别有用。
