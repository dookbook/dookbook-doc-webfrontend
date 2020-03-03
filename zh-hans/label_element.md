TOPICS: <label>
        <label> for attribute
        <label> form attribute

# HTML `<label>` 元素

HTML **`<label>`** 元素表示用户界面中某个项目(*[`<input>`](/zh-hans/webfrontend/<input>)* 元素)的标题/标注（标记）。

`<label>` 元素不会向用户呈现任何特殊效果。不过，它为鼠标用户改进了可用性。如果您在`<label>` 元素内点击文本，就会触发此控件。就是说，当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件上。

## 技术摘要

| | |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*交互内容*，*表单相关元素*，*可触知内容*。|
| **允许的内容** | *短语内容*，但不包括 `<label>` 元素。除带标签的控件外，不允许带其他 `<label>` 的元素。|
| **标签省略** | 不允许，开始标签和结束标签都是必需的。|
| **允许的父元素** | 任何接受 *短语内容* 的元素。|
| **允许的 ARIA 角色** | 无 |
| **DOM 接口** | **`HTMLLabelElement`** |

## 属性

**`<label>`** 元素支持[HTML 全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`for`** | 与关联元素（可标签化的元素，比如 *[`<input>`](/zh-hans/webfrontend<input>)*）的 **`id`** 属性相同。如果目标绑定元素不可标签化，则 `for` 属性无效。<br> **注意:** 一个 `<label>` 元素可以同时具有`for`属性和包含的控制元素， 只要 `for` 属性指向所包含的控制元素。|
| **`form`** | 所关联的 **[`<form>`](/zh-hans/webfrontend/<form>)** 元素。如果指定，则属性的值是同一文档中 [`<form>`](/zh-hans/webfrontend/<form>) 元素的 **`id`**。 这使您可以将此元素放置在文档中的任何位置，而不仅仅是 [`<form>`](/zh-hans/webfrontend/<form>) 元素的后代。|

## 使用须知

- **`<label>`** 文本不仅在视觉上与其对应输入的文本相关联；它也以编程方式与之关联。这意味着，例如当用户专注于表单输入时，屏幕阅读器将读出标签，从而使辅助技术用户更容易理解应输入哪些数据。
- 您可以单击关联的 **`<label>`** 来聚焦/激活输入以及输入本身。 这种增加的点击区域为尝试激活输入的任何人（包括使用触摸屏设备的用户）提供了优势。

其他用法说明：

- **`<label>`** 正在标记的表单控件称为 `<label>` 元素的标签控件。一个 *[`<input>`](/zh-hans/webfrontend/<input>)*
可以与多个 `<label>` 关联。
- `<label>` 本身并不直接与表单关联。它们仅通过与之关联的控件与表单间接关联。
- 当单击或点击 `<label>` 并将其与表单控件关联时，也会为关联的控件引发单击事件。

### 关联 `<label>` 和 `<input>`

要将 `<label>` 与一个 *[`<input>`](/zh-hans/webfrontend/<input>)* 元素相关联，
您需要给该 [`<input>`](/zh-hans/webfrontend/<input>) 一个 **`id`** 属性。
然后，`<label>` 元素需要一个 **`for`** 属性，其值与 [`<input>`](/zh-hans/webfrontend/<input>) 的 `id` 相同。

如果还有其他元素也与 `id` 值匹配，则仅匹配**第一个**，其余忽略。

```html
<!-- 示例： 关联标签的表单输入 -->
<form action="" method="post">
  <label for="username">用户名:</label>
  <input id="username" type="text" name="username">
  <input type="submit" value="保存">
</form>
```

### 嵌入到 `<label>` 中的 `<input>`

另外，您可以将 *[`<input>`](/zh-hans/webfrontend/<input>)* 直接**嵌套**在 `<label>` 中。
在这种情况下，因为关联是隐式的，所以不需要 *`for`* 和 *`id`* 属性：

```html
<!-- 示例： 嵌入到 `<label>` 中的输入框 -->
<label>用户名: <input type="text" name="username"></label>
```

如果没有将 `<label>`嵌入 *[`<input>`](/zh-hans/webfrontend/<input>)* 中，如下所示：

```html
<form>
  <input type="text" name="yes-no">是
  <input type="text" name="yes-no">否
</form>
```

这时当我把鼠标移动到 "是" 或 "否" 时，鼠标变为了 "工" 形，是不可以点击的。如果在 *[`<input>`](/zh-hans/webfrontend/<input>)* 前加 `<label>`
则鼠标移动到 "是" 或 "否" 时，不改变样式，可以点击。

```html
<form>
  <label><input type="text" name="yes-no">是</label>
  <label><input type="text" name="yes-no">否</label>
</form>
```

## 无障碍问题

### 互动内容

请勿在 **`<label>`** 内放置诸如*锚点* (*[`<a>`](/zh-hans/webfrontend/<a>)*)
或*按钮* (*[`<button>`](/zh-hans/webfrontend/<button>)*)之类的交互式元素。
这样做使人们很难激活与 `<label>` 相关联的 [`<input>`](/zh-hans/webfrontend/<input>)。

错误

```html
<label for="tac">
  <input id="tac" type="checkbox" name="terms-and-conditions">
  我同意 <a href="terms-and-conditions.html">《服务条款》</a>
</label>
```

正确

```html
<label for="tac">
  <input id="tac" type="checkbox" name="terms-and-conditions">
  我同意《服务条款》
</label>
<p>
  <a href="terms-and-conditions.html">阅读《服务条款》</a>
</p>
```

### 标题

将*标题元素*放置在 **`<label>`** 中会干扰多种辅助技术，因为标题通常用作导航辅助。如果 `<label>` 的文本需要在视觉上进行调整，请使用应用于 `<label>` 元素的 *[[CSS]]*。

如果表单或表单的一部分需要标题，请使用放置在 *[`<fieldset>`](/zh-hans/webfrontend/<fieldset>)* 中的
*[`<legend>`](/zh-hans/webfrontend/<legend>)* 元素。

错误

```html
<label for="your-name">
  <h3>你的名字</h3>
  <input id="your-name" name="your-name" type="text">
</label>
```

正确

```html
<label class="large-label" for="your-name">
  你的名字
  <input id="your-name" name="your-name" type="text">
</label>
```

### 关联按钮

具有 **`type="button"`** 声明和有效的 `value` 属性的 *[`<input>`](/zh-hans/webfrontend/<input>)* 元素不需要与之关联的 `<label>`。
这样做实际上可能会干扰辅助技术解析按钮输入的方式。同样的情况适用于 **[`<button>`](/zh-hans/webfrontend/<button>)** 元素。

## 标记 `<label>` vs. 占位符 `placeholder`

开门见山，关键点是：如果可以，请勿使用 **`placeholder`** 属性。
如果需要标记 *[`<input>`](/zh-hans/webfrontend/<input>)* 元素，请使用 **`<label>`** 元素。

有三种看似相似的方式将辅助文本与 [`<input>`](/zh-hans/webfrontend/<input>) 相关联。但是它们实际上是完全不同的，只有其中一个始终是一个不错的选择。在这里，我们将研究它们的每一个，并学习在将数据输入表单时为用户提供指导的最佳实践。

### `<label>` 元素

**`<label>`** 元素是提供始终适用的表单字段解释信息的唯一方法（除了您所关心的布局问题之外）。使用 `<label>` 来解释应在 [`<input>`](/zh-hans/webfrontend/<input>)
或 [`<textarea>`](/zh-hans/webfrontend/<textarea>) 中输入什么绝不是坏主意。

### 占位符属性: `placeholder`

占位符属性 **`placeholder`** 使您可以指定一个空白的文本，该文本将显示在 [`<input>`](/zh-hans/webfrontend/<input>) 元素的内容区域中。它旨在用于显示示例输入，而不是进行解释或提示，但往往会被严重误用。

具有自动页面翻译功能的浏览器在翻译时可能会跳过该属性的内容。这意味着它的内容可能不会被翻译，从而导致重要信息没有被翻译。

如果您觉得需要使用占位符，则可以同时使用占位符 `placeholder` 和 `<label>`：

### 与 `<input>` 元素相邻的未经修饰的文本

您也可以在 [`<input>`](/zh-hans/webfrontend/<input>) 元素旁边添加纯文本，如下所示：

```html
<p>Enter your name: <input id="name" type="text" size="30"></p>
```

请不要这样做。这不会在文本提示和 [`<input>`](/zh-hans/webfrontend/<input>) 元素之间建立关系。

### 为什么要使用 `<label>`

除了上面提供的信息外，还有其他许多原因使 **`<label>`** 是解释 [`<input>`](/zh-hans/webfrontend/<input>) 的最佳方法：

*[`<input>`](/zh-hans/webfrontend/<input>)* 和 `<label>` 元素的语义对于匹配诸如屏幕阅读器之类的辅助技术很有用。
通过使用 `<label>` 的 **`for`** 属性将其绑定到 [`<input>`](/zh-hans/webfrontend/<input>)，使屏幕阅读器可以更准确地向用户描述输入。

通过将 `<label>` 和 [`<input>`](/zh-hans/webfrontend/<input>) 配对，点击标签文本即可触发
[`<input>`](/zh-hans/webfrontend/<input>) 聚焦。
如果您使用明文标记输入，则不会发生这样的效果。 将激活区域的提示部分用于输入对于有电机控制条件的人很有帮助。

作为Web开发人员，重要的是，我们切勿以为人们会知道我们所知道的一切。实际上，您网站的某些访问者的思维过程和情况会有所不同，从而导致他们对您的表格的理解与您的理解大相径庭，而显示统一的标签则可以最大限度避免这样的误解。
