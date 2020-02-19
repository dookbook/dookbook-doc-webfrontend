TOPICS: <fieldset>
        <legend>
        <fieldset> form attribute
        <fieldset> disabled attribute
        <fieldset> name attribute

# HTML `<fieldset>` / `<legend>` 元素

HTML **`<fieldset>`** 元素用于将多个控件以及Web表单中的标签（*[`<label>`](/zh-hans/webfrontend/<label>)*）分组。

HTML **`<legend>`** 元素表示其父级 *`<fieldset>`* 的内容的**标题**。

## 技术摘要

| - | `<fieldset>` | `<legend>` |
| :-- | :-- | :-- |
| **内容分类** | *流式内容*，*区块根*，*列表型、与表单相关的元素*，*可触摸内容*。| 没有。|
| **允许的内容** | 可选的 *`<legend>`* 元素，后跟 *流式内容*。| *短语内容*。|
| **标签省略** | 不允许，开始标签和结束标签都是必需的。| 不允许，开始标签和结束标签都是必需的。|
| **允许的父元素** | 任何接受 *流式内容* 的元素。 | *`<fieldset>`* 的**第一个子元素**。|
| **允许的 ARIA 角色** | `group`, `presentation` | 无 |
| **DOM 接口** | **`HTMLFieldSetElement`** | **`HTMLLegendElement`** |

## `<fieldset>` 属性

**`<fieldset>`** 元素包括[HTML 全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| **`form`** | 此属性接受 `<fieldset>` 元素所属的 **[`<form>`](/zh-hans/webfrontend/<form>)** 元素 **`id`** 属性值，即使它不在表单中。 |
| **`disabled`** | *布尔*属性。如果设置了，则所有属于 `<fieldset>` 后代的表单控件都将被禁用，这意味着它们不可编辑，但仍然可以一起与 *[`<form>`](/zh-hans/webfrontend/<form>)* 一起提交。他们不会收到任何浏览器事件，例如鼠标单击或与焦点相关的事件。默认情况下，浏览器将此类控件显示为灰色。请注意，不会禁用 `<legend>` 元素内的表单元素。|
| `name` | 与组关联的名称。 |

## 字段集用法

**`<fieldset>`** 元素为HTML表单的一部分提供分组，而嵌套的 **`<legend>`** 元素为 *`<fieldset>`* 提供*标题*。
它具有很少的属性，其中最引人注目的是 **`form`**，当它等于同一页面上的某一个 *[`<form>`](/zh-hans/webfrontend/<form>)* 的 *`id`*，
则该 `<fieldset>` 属于该 [`<form>`](/zh-hans/webfrontend/<form>) 的一部分，
即使它没有嵌套在其中；而是 **`disabled`** 属性，允许您一次性禁用 `<fieldset>` 及其所有内容。

这个例子展示了一个非常简单的 **`<fieldset>`** 例子，里面有一个 **`<legend>`** 和两个输入控件。

```html
<form action="#" method="post">
  <fieldset>
    <!-- 字段集的标题由嵌套在其中的第一个`<legend>`元素给出 -->
    <legend>Simple fieldset</legend>
    <label>Spirit of radio 1
      <input type="radio">
    </label>
    <label>Spirit of radio 2
      <input type="radio">
    </label>
  </fieldset>
</form>
```

### 禁用字段集

这个例子显示了一个**禁用**的 **`<fieldset>`**，里面有两个输入控件。请注意，由于处于禁用的`<fieldset>`中，这两个控件同时禁用。

```html
<form action="#" method="post">
  <fieldset disabled>  <!-- `disabled` 禁用字段集 -->
    <legend>Simple fieldset</legend>
    <label>Spirit of radio 1
      <input type="radio">
    </label>
    <label>Spirit of radio 2
      <input type="radio">
    </label>
  </fieldset>
</form>
```

## CSS 样式

**`<fieldset>`** 有一些特殊的样式注意事项。

默认情况下，它的 **`display`** 值是 **`block`** 并建立一个块格式化上下文。
如果`<fieldset>`用内联级别 `display` 样式设置，它将表现为 **`inline-block`**，否则它将表现为 *`block`*。
默认情况下，内容周围有 *`2px`* 的凹槽边框，以及少量的默认 *`padding`*。默认情况下，该元素具有 **`min-inline-size：min-content`**。

如果存在 **`<legend>`**，则将其放置在块开始边界上。`<legend>` 收缩边界，并建立格式化上下文。**`display`** 值设置为 **`blockified`**
（例如 `display:inline` 的行为与 `block` 相同）。

`<fieldset>` 的内容将放在一个继承了 `<fieldset>` 某些属性的匿名框中。
如果将 `<fieldset>` 设置为 **`display:grid`** 或 **`display:inline-grid`** 样式，则匿名框将是网格格式化上下文（*网格布局*）。
如果将 `<fieldset>` 设置为 **`display:flex`** 或**`display:inline-flex`** 样式，则匿名框将是弹性格式化上下文（*弹性盒布局*），否则将建立块格式化上下文。

您可以随意使用想要适合页面设计的任何方式来设置 `<fieldset>` 和 `<legend>` 的样式。
