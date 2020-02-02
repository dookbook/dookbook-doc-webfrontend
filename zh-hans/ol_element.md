TOPICS: <ol>
        <li>
        <ol> reversed attribute
        <ol> start attribute

# HTML 有序列表元素 `<ol>`

**HTML `<ol>` 元素** 表示有序列表，通常渲染为带编号的列表。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，如果`<ol>`元素包含至少一个`<li>`元素，则为*可触知内容*。 |
| **允许的内容** | 零个或多个 **`<li>`** 元素。这些`<li>`元素可以再包含嵌套的 *`<ol>`* 或 *[`<ul>`](/zh-hans/webfrontend/<ul>)* 元素。|
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 任何接受*流式内容*的元素 |
| **允许的 ARIA 角色** | `directory`, `group`, `listbox`, `menu`, `menubar`, `radiogroup`, `tablist`, `toolbar`, `tree`, `presentation` |
| **DOM 接口** | **`HTMLOListElement`** |

## 属性

这个元素包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`reversed`** | *布尔*属性，规定了列表采用**倒序**排列。 |
| **`start`** | 这是*整数*属性，规定有序列表的**起始值**。尽管列表条目的序号可能是罗马字母或字母顺序，但这个开始的顺序总是使用数字表示。比如想要元素序号从字母 `"C"` 开始，使用 `<ol start="3">`。<br>**Note:**<br>这个属性在 HTML 4 中弃用，但是在 HTML 5 中被重新引入。 |
| ~~`compact`~~ | （**废弃**。使用CSS属性 **`line-height`** 代替，默认值`80%`）此布尔属性提示列表是否需要被渲染为**更紧凑的样式**。用户代理决定如何解释这个属性，且并非所有浏览器都支持它。|
| ~~`type`~~ | （**废弃**。使用CSS属性 **`list-style-type`** 代替。）编号类型:<br>*`'a'`* 表示小写字母编号；<br>*`'A'`* 表示大写字母编号；<br>*`'i'`* 表示小写罗马数字编号；<br>*`'I'`* 表示大写罗马数字编号；<br>*`'1'`* 表示数字编号（默认值）。|

## 使用说明

- HTML 并没有对 `<ol>` 和 [`<ul>`](/zh-hans/webfrontend/<ul>) 元素的深度和反复使用次数（overlap）作出限制。
- `<ol>`和 [`<ul>`](/zh-hans/webfrontend/<ul>) 都是列表项。它们的不同点在于 `<ol>` 元素里条目的顺序是有意义的。 对于该选择哪一个去使用下面有个建议：尝试去更改列表项的顺序，如果其含义改变了，
那么应该使用 `<ol>` 元素，否则使用 *[`<ul>`](/zh-hans/webfrontend/<ul>)* 更合适。

## HTML 列表条目元素 `<li>`

|  |  |
| :-- | :-- |
| **内容类别** | 无 |
| **允许的内容** | *流式内容* |
| **标签省略** | 如果列表元素的后面紧随另一个 `<li>` 元素，或者它的父元素中没有更多内容，结束标签可以省略。|
| **DOM 接口** | **`HTMLLIElement`** |

### `<li>` 属性

| 属性 | 描述 |
| :-- | :-- |
| `value` | *整数*型属性，表明了本 `<li>` 元素在有序列表中的当前序号，随后的列表条目会从设置的值开始计数。<br>**注意**：这个属性在 HTML 4 中被废弃，在 HTML 5 中重新引入。|

## 示例

### 简单的有序列表

```html
<ol>
  <li>first item</li>
  <li>second item</li>
  <li>third item</li>
</ol>
```

### 使用自定义属性的有序列表

```html
<ol start="3">
  <li>first item</li>
  <li>second item</li>
  <li>third item</li>
</ol>
```

### 嵌套有序列表

```html
<ol>
  <li>first item</li>
  <li>second item      <!-- 注意：此处未关闭 </li> -->
    <ol>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ol>
  </li>                <!-- 此处才关闭 </li> -->
  <li>third item</li>
</ol>
```

### 嵌套 `<ol>` 和 `<ul>`

```html
<ol>
  <li>first item</li>
  <li>second item      <!-- 注意，此处未关闭 </li> -->
    <ul>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ul>
  </li>                <!-- 此处才关闭 </li> -->
  <li>third item</li>
</ol>
```
