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
        <input> list attribute
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
        <input> pattern attribute

# HTML 表单 `<form>` / `<input>`

**HTML 表单元素** (**`<form>`**) 标记了文档中一个包含**交互控制元件**，用来**向Web服务器提交表单信息**的区域。

**`<input>`** 元素用于为基于Web的表单创建交互式控件，以便接受来自用户的数据；根据设备和用户代理的不同，可以使用多种类型的输入数据和控件。

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
| **`list`** | *[`<datalist>`](/zh-hans/webfrontend/<datalist>)* 元素的 **`id`**，该元素提供输入建议值的列表。|
| **`form`** | **所属 `<form>` 的 `id`**。如果不存在，则输入是包含*最近*的表单的成员，或者根本不是表单的成员。|
| `pattern` | 规定用于验证 `<input>` 元素的值的正则表达式。适用于 `type` 类型为: *`text`*, *`search`*, *`url`*, *`tel`*, *`email`* 和 *`password`*。|
| `autocomplete` | **`on`**: (默认) 启用**自动补全**；**`off`**: 禁用自动补全。仅用于 `type` 为 *`text`*, *`password`*, *`email`*, *`search`*, *`url`*, *`tel`*, *`date`*, *`datetime`*, *`datetime-local`*, *`range`* 以及 *`color`* 的 `<input>`。|

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

## 输入元素的样式

您可以特别使用各种与颜色相关的属性来设置 `<input>` 元素的样式。

可以用 **`:valid`** 和 **`:invalid`** CSS 伪类 来给表单内的元素指定样式。CSS **`caret-color`** 属性是特定于文本输入相关元素的一种不寻常的属性，它使您可以设置用于绘制文本输入插入符号的颜色：

```html
<input class="custom" size="32">
```

```css
input.custom {
  caret-color: red;
  font: 16px "Helvetica", "Arial", "sans-serif";
}
```

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
