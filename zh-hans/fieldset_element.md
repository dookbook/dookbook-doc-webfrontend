TOPICS: <fieldset>
        <legend>

# `<fieldset>`

**HTML的`<fieldset>`元素**用于将多个控件以及Web表单中的标签（[`<label>`](/zh-hans/webfrontend/<label>)）分组。

`<fieldset>`元素为HTML表单的一部分提供分组，而嵌套的`<legend>`元素为`<fieldset>`提供标题。
它具有很少的属性，其中最引人注目的是表单，
它可以包含同一页面上的[`<form>`](/zh-hans/webfrontend/<form>)的ID，即使您将`<fieldset>`纳入该[`<form>`](/zh-hans/webfrontend/<form>)的一部分，
即使它没有嵌套在其中，而是被禁用了，这允许您一次性禁用`<fieldset>`及其所有内容。

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `disabled` | 如果设置了此布尔属性，则所有属于`<fieldset>`后代的表单控件都将被禁用，这意味着它们不可编辑，但与表单控件上的`disabled`属性一起将与[`<form>`](/zh-hans/webfrontend/<form>)一起提交。 他们不会收到任何浏览事件，例如鼠标单击或与焦点相关的事件。<br> 默认情况下，浏览器将此类控件显示为灰色。请注意，不会禁用`<legend>`元素内的[`<form>`](/zh-hans/webfrontend/<form>)元素。|
| `form` | 此属性接受`<fieldset>`元素成为[`<form>`](/zh-hans/webfrontend/<form>)元素`id`属性的其一部分的值，即使它不在表单中。 |
| `name` | 与组关联的名称。 |

!!! warn "Don't try this at home"
    注意：字段集的标题由嵌套在其中的第一个`<legend>`元素给出.

## CSS样式

`<fieldfield>`有一些特殊的样式注意事项。

默认情况下，它的`display`值是`block`并建立一个块格式化上下文。如果`<fieldset>`用内联级别`display`样式设置，它将表现为`inline-block`，否则它将表现为块。
默认情况下，内容周围有2px的凹槽边框，以及少量的默认填充。默认情况下，该元素具有`min-inline-size：min-content`。

如果存在`<legend>`，则将其放置在块开始边界上。`<legend>`收缩包装，并建立格式化上下文。`display`值被阻塞（例如`display:inline`的行为与`block`相同）。

将有一个匿名框，其中保存了`<fieldset>`的内容，该框继承了`<fieldset>`的某些属性。 如果将`<fieldset>`设置为`display:grid`或`display:inline-grid`样式，则匿名框将是网格格式化上下文。如果将`<fieldset>`设置为`display:flex`或`display:inline-flex`样式，则匿名框将为`flex`格式化上下文，否则将建立块格式化上下文。

您可以随意使用想要适合页面设计的任何方式来设置`<fieldset>`和`<legend>`的样式。

!!! warn "Don't try this at home"
    注意：在撰写本文时，Microsoft Edge和Google Chrome中存在一些错误，这些错误会阻止在`<fieldset>`内部使用弹性框和网格布局。[此GitHub问题](https://github.com/w3c/csswg-drafts/issues/321)提供了错误跟踪链接。

## `<legend>`

**HTML`<legend>`元素** 代表其父级`<fieldset>`的内容的标题。

|  |  |
| :-- | :-- |
| **内容分类** | 没有。 |
| **允许的内容** | *短语内容*。 |
| **标签遗漏** | 无，开始标签和结束标签都是必需的。 |
| **允许的父元素** | 一个`<fieldset>`的第一个孩子是这个`<legend>`元素。 |
| **允许的 ARIA 角色** | 没有 |
| **DOM 接口** | **`HTMLLegendElement`** |

## 示例

### 简单字段集

这个例子展示了一个非常简单的`<fieldset>`例子，里面有一个`<legend>`，里面有一个控件。

```html
<form action="#">
  <fieldset>
    <legend>Simple fieldset</legend>
    <input type="radio" id="radio">
    <label for="radio">Spirit of radio</label>
  </fieldset>
</form>
```

### 禁用字段集

这个例子显示了一个禁用的`<fieldset>`，里面有两个控件。 请注意，由于处于禁用的`<fieldset>`中，如何同时禁用这两个控件。

```html
<form action="#">
  <fieldset disabled>
    <legend>Disabled fieldset</legend>
    <div>
      <label for="name">Name: </label>
      <input type="text" id="name" value="Chris">
    </div>
    <div>
      <label for="pwd">Archetype: </label>
      <input type="password" id="pwd" value="Wookie">
    </div>
  </fieldset>
</form>
```

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*章节根内容*，*列出的与表单相关的元素*，*可触摸的内容*。 |
| **允许的内容** | 可选的`<legend>`元素，后跟*流式内容*。 |
| **标签遗漏** | 无，开始标签和结束标签都是必需的。 |
| **允许的父元素** | 任何接受*流式内容*的元素。 |
| **允许的 ARIA 角色** | `group`, `presentation` |
| **DOM 接口** | **`HTMLFieldSetElement`** |
