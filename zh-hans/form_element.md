TOPICS: <form>
        <input>
        <form> action attribute
        <form> method attribute
        <form> enctype attribute
        <form> novalidate attribute
        <form> target attribute
        <form> autocomplete attribute
        <form> accept-charset attribute
        <form> name attribute
        <input> type attribute
        <input> name attribute
        <input> value attribute
        <input> required attribute
        <input> maxlength attribute
        <input> minlength attribute
        <input> autofocus attribute
        <input> disabled attribute
        <input> readonly attribute
        <input> form attribute
        <input> formaction attribute
        <input> formmethod attribute
        <input> formenctype attribute
        <input> formnovalidate attribute
        <input> formtarget attribute
        <input> checked attribute
        <input> autocomplete attribute
        <input> accept attribute
        <input> src attribute
        <input> alt attribute
        <input> height attribute
        <input> width attribute
        <input> placeholder attribute
        <input> size attribute
        <label>
        <label> for attribute
        <label> form attribute

# HTML 表单 `<form>`/`<input>`/`<label>`

**HTML 表单元素** (**`<form>`**) 标记了文档中一个包含**交互控制元件**，用来**向Web服务器提交表单信息**的区域。

**`<input>`** 元素用于为基于Web的表单创建交互式控件，以便接受来自用户的数据；根据设备和用户代理的不同，可以使用多种类型的输入数据和控件。

**`<label>`** 元素表示用户界面中某个项目(*`<input>`* 元素)的标题。

可以用 *`:valid`* 和 *`:invalid`* CSS 伪类 来给表单内的元素指定样式。

## 技术摘要

| - | `<form>` | `<input>` |
| :-- | :-- | :-- |
| **内容分类** | *流式内容*，*可触知内容*。| *流式内容*，*列表型*，*可提交*，*可重置*，*表单相关元素*，*短语内容*。如果 *`type`* 属性不是 *`hidden`* 的，则为*可标记*元素，*可触知内容*。|
| **允许的内容** | *流式内容*, 但是不包括 `<form>` 元素。 | 无，这是一个 **[空元素](/zh-hans/webfrontend/Empty_Element)**。 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。| 必须具有开始标签，不得具有结束标签。|
| **允许的父元素** | 任何接受 *流式内容* 的元素。| 任何接受 *短语内容* 的元素。|
| **允许的 ARIA 角色** | `group`, `presentation` | **`type=button`**: `link`, `menuitem`,`menuitemcheckbox`,`menuitemradio`,`radio`,`switch`,`tab`<br>**`checkbox`**: `button`,`menuitemcheckbox`,`option`,`switch`<br>**`image`**: `link`,`menuitem`,`menuitemcheckbox`,`menuitemradio`,`radio`,`switch`<br>**`radio`**: `menuitemradio`<br>**`color`**,**`file`**: None<br>**`text`**,**`password`**,**`hidden`**,**`submit`**,**`reset`**,**`email`**,**`url`**,**`tel`**,**`search`**: 无<br>**`number`**,**`range`**: 无<br>**`time`**,**`date`**,**`datetime`**,**`datetime-local`**,**`month`**,**`week`**: 无 |
| **DOM 接口** | **`HTMLFormElement`** | **`HTMLInputElement`** |

## `<form>` 属性

这个元素包括一些[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`action`** | 指定处理这个表单信息的程序所在的URL。这个值可以被 *[`<button>`](/zh-hans/webfrontend/<button>)* 或者 *`<input>`* 元素中的 **`formaction`** 属性重载（覆盖）。 |
| **`method`** | 指定提交表单的 **[[HTTP]] 请求方式**。可能的值有:**`post`**，**`get`**: (默认值，不推荐)，<br><br>这个值可以被 *[`<button>`](/zh-hans/webfrontend/<button>)* 或者 *`<input>`* 元素中的 **`formmethod`** 属性重载（覆盖）。 |
| `enctype` | 当 *`method`* 属性值为 *`post`* 时, 它是将提交数据的 [[MIME]] 类型。可能的取值有:<br><br>**`application/x-www-form-urlencoded`**: 未指定属性时的默认值。<br>**`multipart/form-data`**: 这个值用于一个 *`type`* 属性设置为 *`file`* 的 `<input>` 元素。<br>**`text/plain`** (HTML5) 纯文本。<br><br>这个值可以被 *[`<button>`](/zh-hans/webfrontend/<button>)* 或者 *`<input>`* 元素中的 **`formenctype`** 属性重载（覆盖）。|
| `novalidate` | *布尔*类型的属性，指示当提交时表单是否没有被验证。如果这个属性没有指定，则这个表单是验证通过的。这个默认设置可以被 *[`<button>`](/zh-hans/webfrontend/<button>)* 或者*`<input>`* 元素中的 **`formnovalidate`** 属性重载（覆盖）。|
| `target` | 表单提交之后的跳转。参见 **[`<a>` 的 `target` 属性](/en/webfrontend/<a>)**。<br><br>HTML5: 这个值可以被 *[`<button>`](/zh-hans/webfrontend/<button>)* 或者 *`<input>`* 元素中的 **`formtarget`** 属性重载（覆盖）。|
| `autocomplete` | 用于指示 *`<input>`* 元素是否能够拥有一个默认值，这个默认值是由浏览器自动补全的。这个设置可以被属于这个 `<form>` 的子元素的 **`autocomplete`** 属性重载（覆盖）。可能的值有:<br><br>**`off`**: 浏览器不会自动补全。<br>**`on`**: 浏览器能够根据用户之前的输入自动补全。|
| `accept-charset` | 一个*空格*分隔或*逗号*分隔的列表，这个列表包括了服务器支持的字符编码。浏览器以这些编码被列举的顺序使用它们。默认值是一个保留字符串 **`"UNKNOWN"`**。这个字符串指的是，和当前文档相同的编码。在之前版本的HTML中，不同的字符编码可以用空格或逗号分隔。**在HTML5中，只有*空格*可以允许作为分隔符**。 |
| `name` | 表单名称。在HTML4中，这个用法不被推荐(作为替代，应该使用`id`). HTML5中，一个文档中的多个表单当中，name必须唯一而不仅仅是一个空字符串。|

## `<input>` 属性

由于输入类型和属性的组合数量众多，因此 `<input>` 元素是所有 HTML 中功能最强大和最复杂的元素之一。
由于每个 `<input>` 元素（无论类型如何）均基于 *`HTMLInputElement`* 接口，
因此从技术上讲，它们都共享完全相同的一组属性。但是实际上，许多属性仅在特定的输入类型上起作用，并且某些输入类型仅支持这些属性中的很少。另外，某些输入类型以特殊方式处理某些属性。

### `<input>` 共有属性

除了[HTML 全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)，还包括以下共有属性：

| 属性 | 描述 |
| :-- | :-- |
| **`type`** | **输入类型**。|
| **`name`** | 提交输入的**变量名**。如果未指定或为空，则输入字段的值不会与表单一起提交。|
| **`value`** | 输入的**当前值**。|
| **`required`** | *布尔*值，指示输入字段的值是**必需的**。如果指定该属性，则元素可应用 **`:required`** 伪类；否则可应用 **`:optional`** 伪类。不可用于 `type` 为 *`submit`*，*`color`*，*`hidden`*，*`range`*，*`image`*，*`reset`*，*`button`* 的输入框。|
| **`autofocus`** | *布尔*值，指示在呈现表单时使该输入控件自动聚焦。在触发 *`DOMContentLoaded`* 事件之前，具有此属性的元素可以获得焦点。不可用于 `type="hidden"` 的输入框。|
| **`disabled`** | *布尔*值，指示**禁用输入**。该输入不会收到 `click` 事件，并且禁用的输入不会与表单一起提交。|
| **`readonly`** | *布尔*值，表示**无法编辑**输入。仅文本控件可以设置为只读，因为对于其他控件（例如复选框和按钮），在只读(`readonly`)和禁用(`disabled`)之间没有区别，因此`readonly`属性不适用。|
| **`form`** | **所属 `<form>` 的 `id`**。如果不存在，则输入是包含*最近*的表单的成员，或者根本不是表单的成员。|
| `autocomplete` | **`on`**: (默认) 启用**自动补全**；**`off`**: 禁用自动补全。仅用于 `type` 为 *`text`*, *`password`*, *`email`*, *`search`*, *`url`*, *`tel`*, *`date`*, *`datetime`*, *`datetime-local`*, *`range`* 以及 *`color`* 的 `<input>`。|
| `list` | [`<datalist>`](/zh-hans/webfrontend/<datalist>)元素的ID，该元素提供输入建议值的列表 |
| `tabindex` | 一个数字值，向用户代理提供有关用户按Tab键时控件获得焦点的顺序的指导 |

!!! warn "**`autofocus`** 属性用法注意事项"
    文档中最多**只能有一个**元素具有 `autofocus` 属性。警告：自动聚焦表单控件会使使用屏幕阅读技术的视障人士感到困惑。分配自动对焦后，屏幕阅读器会将用户“自动传送”到表单控件，而不会事先警告他们。

!!! warn "`readonly` 和 `required` 属性不可同时使用"
    注意：指定了 `readonly` 属性的 `<input>` 不允许使用 `required` 属性。

!!! info "`disabled` vs `readonly`"
    `disabled` 和 `readonly` 之间的区别在于，`readonly` 控件仍然可以起作用，而 `disabled` 的控件通常在启用前通常不充当控件。

## `<input>` 的类型 `type`

`<input>`的工作方式根据其 **`type`** 属性的值而有很大不同。默认类型为 *`text`*。

可用的类型如下：

| `type` | 描述 |
| :-- | :-- |
| **`text`** | **单行文本字段**。换行符会自动从输入值中*删除*。可以使用 **`placeholder`** 属性来标记占位符，显示在空白的输入框中。可以使用 **`size`** 属性来标记可接受的最大文本字符数量。|
| **`submit`** | **提交表单的按钮**。|
| **`password`** | *单行文本*字段，其值被遮盖或隐藏。使用可选的 **`maxlength`** 和 **`minlength`** 属性指定可以输入的值的*最大长度*和*最小长度*。|
| **`hidden`** | **不显示**，但其值会提交给服务器的输入控件。|
| **`checkbox`** | **复选框**。使用可选的 **`checked`** 属性可指定*预先选定*的项。|
| **`radio`** | **单选框**。使用可选的 **`checked`** 属性可指定*预先选定*的项。|
| **`button`** | 没有默认行为的**按钮**。|
| **`reset`** | 将表单内容**重置**为默认值的按钮。|
| **`email`** | 编辑**电子邮件地址**的字段。|
| **`url`** | 输入**URL**的字段。|
| **`tel`** | 输入**电话号码**的控件。|
| **`number`** | 输入**数字**的控件。|
| **`range`** | 用于输入**数字范围**的控件。|
| **`search`** | 用于输入**搜索字符串**的*单行文本*字段。换行符会自动从输入值中删除。|
| **`color`** | 用于指定**颜色**的控件。颜色选择器的UI除了接受简单的颜色作为文本外，没有其他必需的功能。|
| **`file`** | 允许用户选择**文件**的控件。使用 **`accept`** 属性定义控件可以选择的文件类型。|
| **`image`** | **图形**提交按钮。您必须使用 **`src`** 属性定义图像的来源，并使用 **`alt`** 属性定义替代文本。您可以使用 **`width`** 和 **`height`** 属性来定义图像的大小（以像素为单位）。可参考 *[`<img>`](/zh-hans/webfrontend/<img>)*。 |
| **`time`** | 用于输入**没有时区的时间值**的控件。|
| **`date`** | 输入**日期**（年，月，日，无时间）的控件。|
| **`datetime`** | 用于输入**日期和时间**的控件。|
| **`datetime-local`** | 用于输入**日期和时间**（**无时区**）的控件。|
| **`month`** | 用于输入**月份和年份**（**无时区**）的控件。|
| **`week`** | 用于输入**日期（由周年号和无时区的周号组成）**的控件。|

```html
<!-- 示例： 密码输入, maxlength 代表密码最长为32个字符，minlength 代表最短为8个字符 -->
<input type="password">
<input type="password" maxlength="32" minlength="8">

<!-- 示例： 隐藏输入，值为10 -->
<input type="hidden" value="10">

<!-- 示例： 复选框，提交的变量名为point，选项值分别为A1, A2 -->
<input type="checkbox" name="point" value="A1" checked>
<input type="checkbox" name="point" value="A2">

<!-- 示例： 单选框，提交的变量名为sex，选项值分别为M, F -->
<input type="radio" name="sex" value="M" checked>
<input type="radio" name="sex" value="F">

<!-- 示例： 一个按钮 -->
<input type="button">

<!-- 示例： 一个重置按钮 -->
<input type="reset">

<!-- 示例： 邮箱地址输入框 -->
<input type="email">

<!-- 示例： URL输入框 -->
<input type="url">

<!-- 示例： 电话号码输入框 -->
<input type="tel">

<!-- 示例： 数字输入框 -->
<input type="number">

<!-- 示例： 带范围的数字输入框 -->
<input type="range">

<!-- 示例： 搜索字符串输入框 -->
<input type="search">

<!-- 示例： 颜色选择器输入框 -->
<input type="color">

<!-- 示例： 文件输入框 -->
<input type="file">

<!-- 示例： 图片按钮 -->
<input type="img" src="..." alt="替换文字">

<!-- 示例： 时间输入框 -->
<input type="time">
<input type="date">
<input type="datetime">
<input type="datetime-local">
<input type="month">
<input type="week">
```

## 示例：简单表单 (POST请求)

```html
<!-- 示例： 一个简单的表单，发送 POST 请求 -->
<form action="" method="post">
  <input type="text" name="username">
  <input type="submit" value="保存">
</form>
```

提交表单数据时，`name`的值作为变量名与控件的值一起提交。同时该 `name` 的值成为所属 `<form>` 元素属性 *`HTMLFormElement.elements`* 的属性。如下：

```javascript
let form = document.querySelector("form");
let userName1 = form.elements.username;
let userName2 = form.elements["username"];
```

## `<label>` 使用须知

- `<label>` 文本不仅在视觉上与其对应输入的文本相关联；它也以编程方式与之关联。这意味着，例如当用户专注于表单输入时，屏幕阅读器将读出标签，从而使辅助技术用户更容易理解应输入哪些数据。
- 您可以单击关联的 `<label>` 来聚焦/激活输入以及输入本身。 这种增加的点击区域为尝试激活输入的任何人（包括使用触摸屏设备的用户）提供了优势。

其他用法说明：

- `<label>` 正在标记的表单控件称为 `<label>` 元素的标签控件。一个 `<input>` 可以与多个 `<label>` 关联。
- `<label>` 本身并不直接与表单关联。它们仅通过与之关联的控件与表单间接关联。
- 当单击或点击 `<label>` 并将其与表单控件关联时，也会为关联的控件引发单击事件。

### `<label>` 技术摘要

| | |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*交互内容*，*表单相关元素*，*可触知内容*。|
| **允许的内容** | *短语内容*，但不包括 `<label>` 元素。除带标签的控件外，不允许带其他 `<label>` 的元素。|
| **标签省略** | 不允许，开始标签和结束标签都是必需的。|
| **允许的父元素** | 任何接受 *短语内容* 的元素。|
| **允许的 ARIA 角色** | 无 |
| **DOM 接口** | **`HTMLLabelElement`** |

### `<label>` 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`for`** | 与关联元素（可标签化的元素，比如 *`<input>`*）的 **`id`** 属性相同。如果目标绑定元素不可标签化，则 `for` 属性无效。<br> **注意:** 一个`<label>`元素可以同时具有`for`属性和包含的控制元素， 只要 `for` 属性指向所包含的控制元素。|
| **`form`** | 所关联的 **[`<form>`](/zh-hans/webfrontend/<form>)** 元素。如果指定，则属性的值是同一文档中[`<form>`](/zh-hans/webfrontend/<form>)元素的 **`id`**。 这使您可以将此元素放置在文档中的任何位置，而不仅仅是 `<form>` 元素的后代。|

### 关联标签的表单输入

要将 `<label>` 与一个 [`<input>`](/zh-hans/webfrontend/<input>) 元素相关联，
您需要给该[`<input>`](/zh-hans/webfrontend/<input>)一个 **`id`** 属性。
然后，`<label>` 元素需要一个 **`for`** 属性，其值与 `<input>` 的 `id` 相同。

如果还有其他元素也与 `id` 值匹配，则仅匹配**第一个**，其余忽略。

```html
<!-- 示例： 关联标签的表单输入 -->
<form action="" method="post">
  <label for="username">用户名:</label>
  <input id="username" type="text" name="username">
  <input type="submit" value="保存">
</form>
```

### 嵌入到 `<label>` 中的输入框

另外，您可以将 [`<input>`](/zh-hans/webfrontend/<input>) 直接**嵌套**在 `<label>` 中。
在这种情况下，因为关联是隐式的，所以不需要 `for` 和 `id` 属性：

```html
<!-- 示例： 嵌入到 `<label>` 中的输入框 -->
<label>用户名: <input type="text" name="username"></label>
```

## `<label>` 无障碍建议

### `<label>` 中的互动内容

请勿在 `<label>` 内放置诸如*锚点* (*[`<a>`](/zh-hans/webfrontend/<a>)*)
或*按钮* (*[`<button>`](/zh-hans/webfrontend/<button>)*)之类的交互式元素。
这样做使人们很难激活与 `<label>` 相关联的表单 `<input>`。

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

### `<label>` 中的标题

将标题元素放置在 `<label>` 中会干扰多种辅助技术，因为标题通常用作导航辅助。如果 `<label>` 的文本需要在视觉上进行调整，请使用应用于 `<label>` 元素的CSS。

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

### `<label>` 关联按钮

具有 **`type="button"`** 声明和有效的 `value` 属性的 *[`<input>`](/zh-hans/webfrontend/<input>)* 元素不需要与之关联的 `<label>`。
这样做实际上可能会干扰辅助技术解析按钮输入的方式。同样的情况适用于 **[`<button>`](/zh-hans/webfrontend/<button>)** 元素。

***

属性

**`list`**

位于同一文档中的`<datalist>`元素的`id`，该元素提供了一系列预定义值以向用户建议此输入。建议选项中不包含列表中与`type`不兼容的任何值。

`hidden`, `password`, `checkbox`, `radio`, `file`或任何按钮类型均不支持`list`属性。

**`tabindex`**

一个可选的数值，它定义通过使用`<kbd>Tab</kbd>`键是否可以使输入聚焦以及该元素是否参与顺序焦点导航。 该值还确定使用`<kbd>Tab</kbd>`键访问元素的顺序。

`tabindex`的值根据符号具有特殊含义：

- `tabindex`的负值表示该元素应可由用户聚焦，但不能使用顺序键盘导航。 建议始终使用值-1，因为使用其他值可能会很复杂。
- `tabindex`为0意味着该元素应该是可聚焦的，并且应该可以通过顺序的键盘导航到达，但是该Tab的顺序由用户代理决定，后者应该应用用户的平台约定。 当您希望元素可聚焦并参与键盘导航而不是尝试自己管理选项卡顺序时，通常这是最佳使用值。
- `tabindex`”的正值表示元素的制表顺序。 每次用户按下`<kbd>Tab</kbd>`键时，其标签索引依次高的元素都会被聚焦。大多数平台通常提供反向标签功能，通常结合使用
`<kbd>Shift </kbd>`+`<kbd>Tab</kbd>`会反转制表顺序。如果`tabindex`被省略或不是有效的整数，则用户代理将遵循平台约定来确定要执行的操作。

## 标记 `<label>` vs. 占位符 `placeholder`

开门见山，关键点是：如果可以，请勿使用 **`placeholder`** 属性。如果需要标记 `<input>` 元素，请使用 **`<label>`** 元素。

有三种看似相似的方式将辅助文本与 `<input>` 相关联。但是它们实际上是完全不同的，只有其中一个始终是一个不错的选择。在这里，我们将研究它们的每一个，并学习在将数据输入表单时为用户提供指导的最佳实践。

### `<label>` 元素

**`<label>`** 元素是提供始终适用的表单字段解释信息的唯一方法（除了您所关心的布局问题之外）。使用 `<label>` 来解释应在 `<input>` 或  [`<textarea>`](/zh-hans/webfrontend/<textarea>)中输入什么绝不是坏主意。

### 占位符属性: `placeholder`

占位符属性 **`placeholder`** 使您可以指定一个空白的文本，该文本将显示在 `<input>` 元素的内容区域中。它旨在用于显示示例输入，而不是进行解释或提示，但往往会被严重误用。

具有自动页面翻译功能的浏览器在翻译时可能会跳过该属性的内容。这意味着它的内容可能不会被翻译，从而导致重要信息没有被翻译。

如果您觉得需要使用占位符，则可以同时使用占位符 `placeholder` 和 `<label>`：

### 与 `<input>` 元素相邻的未经修饰的文本

您也可以在 `<input>` 元素旁边添加纯文本，如下所示：

```html
<p>Enter your name: <input id="name" type="text" size="30"></p>
```

请不要这样做。这不会在文本提示和 `<input>` 元素之间建立关系。

### 为什么要使用 `<label>`

除了上面提供的信息外，还有其他许多原因使 **`<label>`** 是解释 `<input>` 的最佳方法：

`<input>` 和 `<label>` 元素的语义配对对于诸如屏幕阅读器之类的辅助技术很有用。通过使用`<label>` 的 *`for`* 属性将其绑定到 `<input>`，使屏幕阅读器可以更准确地向用户描述输入。

通过将 `<label>` 和 `<input>` 配对，点击标签文本即可触发 `<input>` 聚焦。如果您使用明文标记输入，则不会发生这样的效果。 将激活区域的提示部分用于输入对于有电机控制条件的人很有帮助。

作为Web开发人员，重要的是，我们切勿以为人们会知道我们所知道的一切。实际上，您网站的某些访问者的思维过程和/或情况会有所不同，从而导致他们对您的表格的理解与您的理解大相径庭，而显示统一的标签则可以最大限度避免这样的误解。

## `HTMLInputElement` 方法

`HTMLInputElement`接口提供了以下方法，该接口表示DOM中的`<input>`元素。
父接口指定的那些方法（`HTMLElement`，`HTML`，`Element`，`Node` 和 `EventTarget`）也可用。

| 方法 | 描述 |
| :-- | :-- |
| `checkValidity()` | 立即对元素进行有效性检查，如果值无效，则触发文档在元素上触发`invalid`事件。|
| `reportValidity()` | 如果元素的值通过有效性检查，则返回`true`。 否则，返回`false`。|
| `select()` | 如果元素的内容是可选的，则选择元素`<input>`的全部内容。对于没有可选文本内容的元素（例如可视颜色选择器或日历日期输入），此方法不执行任何操作。|
| `setCustomValidity()` | 设置自定义消息，以在输入元素的值无效时显示。|
| `setRangeText()` | 将输入元素中指定字符范围的内容设置为给定的字符串。selectMode参数可用于控制如何影响现有内容。|
| `setSelectionRange()` | 在文本输入元素中选择指定的字符范围。 对于未显示为文本输入字段的输入不执行任何操作。|
| `stepDown()` | 默认情况下，将数字输入的值减一，或者按指定的单位数减一。|
| `stepUp()` | 将数字输入的值增加一或以指定的单位数递增。|

## 样式输入元素

您可以特别使用各种与颜色相关的属性来设置`<input>`元素的样式。 CSS`caret-color`属性是特定于文本输入相关元素的一种不寻常的属性，它使您可以设置用于绘制文本输入插入符号的颜色：

```html
<label for="textInput">Note the red caret:</label>
<input id="textInput" class="custom" size="32">
```

```css
input.custom {
  caret-color: red;
  font: 16px "Helvetica", "Arial", "sans-serif";
}
```

有关在HTML元素中添加颜色的更多信息，请参阅使用CSS将颜色应用于HTML元素。

## 示例

```html
<!-- 使用 fieldset, legend, and label 的表单 -->
<form action="" method="post">
  <fieldset>
    <legend>Title</legend>
    <input type="radio" name="radio" id="radio"> <label for="radio">Click me</label>
  </fieldset>
</form>
```
