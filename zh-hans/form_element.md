TOPICS: <form>
        <input>
        <form> action attribute
        <form> method attribute
        <input> type attribute
        <input> name attribute
        <input> value attribute

# HTML 表单 `<form>`/`<input>`

**HTML 表单元素** (**`<form>`**) 标记了文档中一个包含**交互控制元件**，用来**向Web服务器提交表单信息**的区域。

**`<input>`** 元素用于为基于Web的表单创建交互式控件，以便接受来自用户的数据；根据设备和用户代理的不同，可以使用多种类型的输入数据和控件。

可以用 *`:valid`* 和 *`:invalid`* CSS 伪类 来给表单内的元素指定样式。

## 技术摘要

| - | `<form>` | `<input>` |
| :-- | :-- | :-- |
| **内容分类** | *流式内容*，*可触知内容*。| *流式内容*，*列表型*，*可提交*，*可重置*，*与表单相关*的元素，*短语内容*。如果 *`type`* 属性不是 *`hidden`* 的，则为*可标记*元素，*可触知内容*。|
| **允许的内容** | *流式内容*, 但是不包括 `<form>` 元素。 | 无，这是一个 **[空元素](/zh-hans/webfrontend/Empty_Element)**。 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。| 必须具有开始标签，不得具有结束标签。|
| **允许的父元素** | 任何接受 *流式内容* 的元素。 | 任何接受 *短语内容* 的元素。 |
| **允许的 ARIA 角色** | `group`, `presentation` | `type=button:` `link`, `menuitem`, `menuitemcheckbox`, `menuitemradio`, `radio`, `switch`, `tab`<br>`type=checkbox:` `button`, `menuitemcheckbox`, `option`, `switch`<br>`type=image:` `link`, `menuitem`, `menuitemcheckbox`, `menuitemradio`, `radio`, `switch`<br>`type=radio:` `menuitemradio`<br>`type=color`,`date`,`datetime`,`datetime-local`,`email`,`file`: None<br>`type=hidden`,`month`,`number`,`password`,`range`,`reset`: None<br>`type=search`,`submit`,`tel`,`text`,`url`,`week`: None |
| **DOM 接口** | **`HTMLFormElement`** | **`HTMLInputElement`** |

## `<form>` 属性

这个元素包括一些[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`action`** | 指定处理这个表单信息的程序所在的URL。这个值可以被 *[`<button>`](/zh-hans/webfrontend/<button>)* 或者 *`<input>`* 元素中的 **`formaction`** 属性重载（覆盖）。 |
| **`method`** | 指定提交表单的 **[[HTTP]] 请求方式**。可能的值有:<br><br>**`post`**: HTTP POST 方法; 表单数据会包含在表单体内然后发送给服务器。<br>**`get`**: (默认值) HTTP GET 方法; 表单数据会附加在 `action` 属性的 URI 中，并以 `?` 作为分隔符, 然后将组装的 URI 再发送给服务器。这样做会使数据暴露在URI里面且仅包含ASCII字符。不推荐。<br><br>这个值可以被 *[`<button>`](/zh-hans/webfrontend/<button>)* 或者 *`<input>`* 元素中的 **`formmethod`** 属性重载（覆盖）。 |
| `accept-charset` | 一个空格分隔或逗号分隔的列表，这个列表包括了服务器支持的字符编码。浏览器以这些编码被列举的顺序使用它们。默认值是一个保留字符串“UNKNOWN”。这个字符串指的是，和包含这个form元素的文档相同的编码。在之前版本的HTML中，不同的字符编码可以用空格或逗号分隔。在HTML5中，只有空格可以允许作为分隔符。 |
| `autocapitalize` | 这是一个被 iOS Safari Mobile 使用的非标准属性。当用户在一些form的文本后代控件中，输入/编辑一些文本值时，这个属性控制了这些文本值的首字母是否大写或者使用其他的大写样式。<br>如果 `autocapitalize` 属性在某个单独的form后代控件被指定的话，那么这个单独的设定会覆盖原来form范围内的 `autocapitalize` 设定. 这个非不推荐的值从 iOS 5 及其之后可用. 默认值为 `sentences`. 可以选择的值如下:<br><br>`none`: 完全禁用自动首字母大写.<br>`sentences`: 自动对每句话首字母大写.<br>`words`: 自动对每个单词首字母大写.<br>`characters`: 自动大写所有的字母. |
| `autocomplete` | 用于指示 input 元素是否能够拥有一个默认值，这个默认值是由浏览器自动补全的。这个设定可以被属于这个form的子元素的 autocomplete 属性重载（覆盖）。 可能的值有:<br><br>`off`: 在每一个用到的输入域里，用户必须显式的输入一个值，或者document 以它自己的方式提供自动补全；浏览器不会自动补全输入。<br>`on`: 浏览器能够根据用户之前在form里输入的值自动补全。<br>**注意:**<br>如果你在一个表单里把 `autocomplete` 设置成 off 是因为 `document` 提供了它独有的自动补全，那么你也应该把这个表单里每一个 `input` 元素的 `autocomplete` 设成 off 来让 `document` 能够自动补全. 想要了解详细信息, 参见 Google Chrome notes. |
| `enctype` | 当 `method` 属性值为 `post` 时, enctype 是将form的内容提交给服务器的 MIME 类型 。可能的取值有:<br><br>`application/x-www-form-urlencoded`: 未指定属性时的默认值。<br>`multipart/form-data`: 这个值用于一个 `type` 属性设置为 "file" 的 `<input>` 元素。<br>`text/plain (HTML5)`<br>这个值可以被 [`<button>`](/zh-hans/webfrontend/<button>) 或者 `<input>` 元素中的 formenctype 属性重载（覆盖）。 |
| `name` | 这个form的名字。在HTML4中，这个用法不被推荐(作为替代，应该使用id). HTML5中，一个文档中的多个form当中，name必须唯一而不仅仅是一个空字符串。 |
| `novalidate` | 这个布尔类型的属性指示了，当提交时form是否没有被验证。 如果这个属性没有指定 (因此这个 form 是验证通过的)，这个默认设置可以被属于这个form的 [`<button>`](/zh-hans/webfrontend/<button>) 或者`<input>` 元素中的 formnovalidate 属性重载（覆盖）。 |
| `target` | 一个名字或者说关键字，用来指示在提交表单之后，在哪里显示收到的回复. 在 HTML 4 里, 这是一个用于 frame 的名字/关键字. 在 HTML5 里, 这是一个用于browsing context 浏览器上下文  的名字/关键字 (举例来说, 标签页tab, 窗口window, or 或者行内 frame). 如下的关键字含有特别的含义:<br><br>`_self`: 在当前HTML4或HTML5文档页面重新加载返回值。这个是默认值。译注：也就是说如果这个文档在一个frame中的话，self是在当前frame（document）中重新加载的，而不是整个页面（window）。<br>`_blank`: 以新的HTML4或HTML5文档窗口加载返回值。<br>`_parent`: 在父级的frame中以HTML4或HTML5文档形式加载返回值，如果没有父级的frame，行为和_self一致。<br>`_top`: 如果是HTML 4文档: 清空当前文档，加载返回内容；HTML5: 在当前文档的最高级内加载返回值，如果没有父级，和_self的行为一致。iframename: 返回值在指定frame中加载。<br>HTML5: 这个值可以被 [`<button>`](/zh-hans/webfrontend/<button>) 或者 `<input>` 元素中的 formtarget 属性重载（覆盖）。 |

## `<input>` 属性

由于输入类型和属性的组合数量众多，因此 `<input>` 元素是所有 HTML 中功能最强大和最复杂的元素之一。
由于每个 `<input>` 元素（无论类型如何）均基于 *`HTMLInputElement`* 接口，
因此从技术上讲，它们都共享完全相同的一组属性。但是实际上，许多属性仅在特定的输入类型上起作用，并且某些输入类型仅支持这些属性中的很少。另外，某些输入类型以特殊方式处理某些属性。

### `<input>` 共有属性

除了[HTML 全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)，还包括以下共有属性：

| 属性 | 描述 |
| :-- | :-- |
| **`type`** | **输入类型**。|
| **`name`** | 提交输入的**变量名**。|
| **`value`** | 输入的**当前值**。|
| `autocomplete` | 一个字符串，指示要允许输入的自动完成功能的类型（如果有）|
| `autofocus` | 一个布尔值，如果存在，则在呈现表单时使输入成为焦点 |
| `disabled` | 如果应禁用输入，则存在一个布尔属性 |
| `form` | 输入是其成员的`<form>`的ID； 如果不存在，则输入是包含最近的表单的成员，或者根本不是表单的成员 |
| `list` | [`<datalist>`](/zh-hans/webfrontend/<datalist>)元素的ID，该元素提供输入建议值的列表 |
| `readonly` | 布尔值属性，如果为true，则表示无法编辑输入 |
| `required` | 一个布尔值，如果为true，则表示输入内容必须具有值才能提交表单 |
| `tabindex` | 一个数字值，向用户代理提供有关用户按Tab键时控件获得焦点的顺序的指导 |

## `<input>` 的类型 `type`

`<input>`的工作方式根据其 **`type`** 属性的值而有很大不同。默认类型为 *`text`*。

可用的类型如下：

| `type` | 描述 |
| :-- | :-- |
| **`text`** | **单行文本字段**。换行符会自动从输入值中*删除*。|
| **`submit`** | **提交表单的按钮**。|

## 示例：简单表单 (POST请求)

```html
<!-- 一个简单的表单，发送 POST 请求 -->
<form action="" method="post">
  <input type="text" name="username">
  <input type="submit" value="保存">
</form>
```

## 示例：带标签标注的表单

```html
<form action="" method="post">
  <label for="username">用户名:</label>
  <input id="username" type="text" name="username">
  <input type="submit" value="保存">
</form>
```

- `button`: 没有默认行为的按钮。
- `checkbox`: 一个复选框，允许选择/取消选择单个值。
- `color`: 用于指定颜色的控件。 颜色选择器的UI除了接受简单的颜色作为文本（更多信息）外，没有其他必需的功能。
- `date`: 输入日期（年，月，日，无时间）的控件。
- `datetime-local`: 用于输入日期和时间（无时区）的控件。
- `email`: 用于编辑电子邮件地址的字段。
- `file`: 允许用户选择文件的控件。 使用**accept**属性定义控件可以选择的文件类型。
- `hidden`: 不显示但其值已提交给服务器的控件。
- `image`: 图形提交按钮。 您必须使用**src**属性定义图像的来源，并使用**alt**属性定义替代文本。 您可以使用**高度**和**宽度**属性来定义图像的大小（以像素为单位）。
- `month`: 用于输入月份和年份（无时区）的控件。
- `number`: 输入数字的控件。
- `password`: 单行文本字段，其值被遮盖。 使用**maxlength**和**minlength**属性指定可以输入的值的最大长度。

!!! warn "Don't try this at home"
    注意：任何涉及敏感信息的表单（例如密码）（例如登录表单）都应通过HTTPS提供；Firefox现在实现了多种机制来警告不安全的登录表单-请参阅不安全的密码。其他浏览器也正在实现类似的机制。

- `radio`: 单选按钮，允许从多个选项中选择一个值。
- `range`: 用于输入其精确值不重要的数字的控件。
- `reset`: 将表单内容重置为默认值的按钮。
- `search`: 用于输入搜索字符串的单行文本字段。换行符会自动从输入值中删除。
- `tel`: 输入电话号码的控件。
- `time`: 用于输入没有时区的时间值的控件。
- `url`: 输入URL的字段。
- `week`: 用于输入日期的控件，该日期由周年号和无时区的周号组成。

属性

**`autocomplete`**

一个字符串，描述输入应提供的自动完成功能的类型。 自动完成的一种典型实现方式是简单地调用在同一输入字段中输入的先前值，但是可以存在更复杂形式的自动完成。 例如，浏览器可以与设备的联系人列表集成，
以在电子邮件输入字段中自动完成电子邮件地址。 有关允许的值，请参见HTML自动完成属性中的值。

此属性对不返回数字或文本数据的输入类型无效，例如`checkbox`或`image`。

有关其他信息，请参见HTML自动完成属性。

**`autofocus`**

一个布尔属性，如果存在，则指示页面完成加载时（或显示包含元素的[`<dialog>`](/zh-hans/webfrontend/<dialog>)时）输入应自动具有焦点。

!!! warn "Don't try this at home"
    注意：在触发`DOMContentLoaded`事件之前，具有`autofocus`属性的元素可能会获得焦点。

文档中最多只能有一个元素具有`autofocus`属性，并且`autofocus`不能用于`hidden`类型的输入，因为隐藏的输入不能被聚焦。

!!! error ""
    警告：自动聚焦表单控件会使使用屏幕阅读技术的视障人士感到困惑。 分配自动对焦后，屏幕阅读器会将用户“传送”到表单控件，而不会事先警告他们。

**`disabled`**

一个布尔属性，如果存在，则指示用户不应与输入进行交互。 禁用的输入通常使用较暗的颜色或使用某种其他形式的字段无法使用的指示来呈现。

具体来说，禁用的输入不会收到click事件，并且禁用的输入不会与表单一起提交。

!!! warn "Don't try this at home"
    注意：尽管规范没有要求，但是Firefox默认会在页面加载过程中保持`<input>`的动态禁用状态。使用`autocomplete`(url)属性来控制此功能。

**`form`**

一个字符串，指定与输入关联的`<form>`元素（即其“表单所有者”）。该字符串的值（如果存在）必须与同一文档中的`<form>`元素的ID相匹配。如果未指定此属性，则将`<input>`元素与最近的包含形式相关联（如果有）。

`form`属性使您可以将输入放置在文档中的任何位置，但将其包含在文档中其他位置的表单中。

**`list`**

位于同一文档中的`<datalist>`元素的`id`，该元素提供了一系列预定义值以向用户建议此输入。建议选项中不包含列表中与`type`不兼容的任何值。

`hidden`, `password`, `checkbox`, `radio`, `file`或任何按钮类型均不支持`list`属性。

**`name`**

一个字符串，指定输入控件的名称。 提交表单数据时，此名称与控件的值一起提交，并与拥有的`<form>`元素的`elements`对象一起提交。

给输入元素一个“名称”时，该名称成为拥有表单元素的`HTMLFormElement.elements`属性的属性。 这意味着，如果您有一个输入，其`name`设置为`guest`，而另一个输入的名称是`hat-size`，则可以使用以下代码：

```javascript
let form = document.querySelector("form");
let guestName = form.elements.guest;
let hatSize = form.elements"hat-size"];
```

运行此代码后，`guestName`将是`guest`字段的`HTMLInputElement`，而`hatSize`将是`hat-size`字段的对象。

!!! error ""
    警告：应避免给表单元素一个与表单的内置属性相对应的名称，因为您将使用对相应输入的引用覆盖预定义的属性或方法。

名称`_charset_`具有特殊含义。 如果用作`hidden`类型的`<input>`元素的名称，则用户代理会自动将输入的`value`设置为用于提交表单的字符编码。

如果未指定`name`或`name`为空，则输入的值不会与表单一起提交。

!!! warn "Don't try this at home"
    注意：由于历史原因，不允许使用名称`isindex`。 如果您真的想知道为什么，请参阅命名表单控件：HTML规范中的`name`属性。

**`readonly`**

一个布尔属性，如果存在，则指示用户不应编辑输入的值。

`disabled`和`readonly`之间的区别在于，只读控件仍然可以起作用，而禁用的控件通常在启用前通常不充当控件。

!!! warn "Don't try this at home"
    注意：指定了`readonly`属性的输入不允许使用`required`属性。

!!! warn "Don't try this at home"
    注意：仅文本控件可以设置为只读，因为对于其他控件（例如复选框和按钮），在只读和禁用之间没有有用的区别，因此“ readonly”属性不适用。

**`required`**

`required`是一个布尔属性，如果存在，则指示用户必须先指定输入值，然后才能提交拥有表单。 除以下内容外，所有输入类型均支持`required`属性：

- `color`
- `hidden`
- `range`
- `submit`
- `image`
- `reset`
- `button`

如果输入具有`required`属性，则`:required`伪类也适用于它。相反，没有`required`属性的输入（除了不支持它的元素除外）具有`:optional`伪- 类已应用。...

!!! warn "Don't try this at home"
    注意：因为只读字段不能有值，所以`required`对也指定了`readonly`属性的输入没有任何影响。

**`tabindex`**

一个可选的数值，它定义通过使用`<kbd>Tab</kbd>`键是否可以使输入聚焦以及该元素是否参与顺序焦点导航。 该值还确定使用`<kbd>Tab</kbd>`键访问元素的顺序。

`tabindex`的值根据符号具有特殊含义：

- `tabindex`的负值表示该元素应可由用户聚焦，但不能使用顺序键盘导航。 建议始终使用值-1，因为使用其他值可能会很复杂。
- `tabindex`为0意味着该元素应该是可聚焦的，并且应该可以通过顺序的键盘导航到达，但是该Tab的顺序由用户代理决定，后者应该应用用户的平台约定。 当您希望元素可聚焦并参与键盘导航而不是尝试自己管理选项卡顺序时，通常这是最佳使用值。
- `tabindex`”的正值表示元素的制表顺序。 每次用户按下`<kbd>Tab</kbd>`键时，其标签索引依次高的元素都会被聚焦。大多数平台通常提供反向标签功能，通常结合使用
`<kbd>Shift </kbd>`+`<kbd>Tab</kbd>`会反转制表顺序。如果`tabindex`被省略或不是有效的整数，则用户代理将遵循平台约定来确定要执行的操作。

**`value`**

输入控件的值。 当在HTML中指定时，这是初始值，此后可以使用JavaScript访问相应的`HTMLInputElement`对象的`value`属性随时对其进行更改或检索。`value`属性总是可选的。

!!! warn "Don't try this at home"
    注意：与其他输入控件不同，如果当前已选中“复选框”或“单选”按钮，则复选框和单选按钮仅包含在提交的数据中。 如果是，则将“值”属性报告为输入值。

例如，如果一个名为`status`的复选框的`value`为`active`，并且选中了该复选框，则提交的表单数据将包括`status=active`。如果该复选框未激活，则它根本不会在表单数据中列出。复选框和单选按钮的默认`value`为`on`。

### 方法

`HTMLInputElement`接口提供了以下方法，该接口表示DOM中的`<input>`元素。 父接口指定的那些方法（`HTMLElement`，`HTML`，`Element`，`Node`和`EventTarget`）也可用。

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

### 样式输入元素

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

### 标签和占位符

TL;DR:为节省时间，这是关键点：如果可以避免，请勿使用`placeholder`属性。 如果需要标记`<input>`元素，请使用[`<label>`](/zh-hans/webfrontend/<label>)元素。

有三种看似相似的方式将辅助文本与`<input>`相关联。但是它们实际上是完全不同的，只有其中一个始终是一个不错的选择。在这里，我们将研究它们的每一个，并学习在将数据输入表单时为用户提供指导的最佳实践。

**[`<label>`](/zh-hans/webfrontend/<label>)元素**

[`<label>`](/zh-hans/webfrontend/<label>)元素是提供始终适用的表单字段的解释信息的唯一方法（除了您所关心的布局问题之外）。 使用[`<label>`](/zh-hans/webfrontend/<label>)来解释应在`<input>`或[`<textarea>`](/zh-hans/webfrontend/<textarea>)中输入什么绝不是坏主意。

**占位符属性**:

占位符属性使您可以指定一个空白的文本，该文本将显示在`<input>`元素的内容区域中。 它旨在用于显示示例输入，而不是进行解释或提示，但往往会被严重误用。

这是两个输入密码的输入，每个输入都有一个占位符：

正确和不正确的占位符用法示例

第一个使用占位符字符串`MyGr8P @ sswrd`，说明密码的外观。不那不是一个很好的密码。

第二个使用提示字符串`Enter your password`作为占位符。这样做的第一个也是最明显的问题是，用户输入第一个字符后，他们将不再有提示解释该字段的用途。

这就是为什么应该使用[`<label>`](/zh-hans/webfrontend/<label>)元素的原因。 绝对不需要占位符来理解您的表格。 虽然有些人能够记住一个给定的空白框，但它的唯一标识性文本消失了之后的含义，而其他人则不能。

如果在缺少占位符的情况下用户不理解您的表单（例如，在不支持占位符的浏览器中，或者在上述情况下用户开始输入然后感到困惑），则说明您没有正确使用占位符。

此外，具有自动页面翻译功能的浏览器在翻译时可能会跳过属性。 这意味着“占位符”可能不会被翻译，从而导致重要信息没有被翻译。

如果您觉得需要使用占位符，则可以同时使用占位符和标签：

**与`<input>`元素相邻的未经修饰的文本**

您也可以在`<input>`元素旁边添加纯文本，如下所示：

```html
<p>Enter your name: <input id="name" type="text" size="30"></p>
```

请不要这样做。这不会在提示和`<input>`元素之间建立关系，这是很重要的，原因是我们将在下一部分中讨论。

**为什么要使用标签**:

除了上面提供的信息外，还有其他许多原因使[`<label>`](/zh-hans/webfrontend/<label>)是解释`<input>`的最佳方法：

`<input>`和[`<label>`](/zh-hans/webfrontend/<label>)元素的语义配对对于诸如屏幕阅读器之类的辅助技术很有用。通过使用[`<label>`](/zh-hans/webfrontend/<label>)的`for`属性将它们配对，可以将标签绑定到输入，使屏幕阅读器可以更准确地向用户描述输入。
通过将[`<label>`](/zh-hans/webfrontend/<label>)和`<input>`配对， 如果您使用明文`label`您的输入，则不会发生。 将激活区域的提示部分用于输入对于有电机控制条件的人很有帮助。作为Web开发人员，重要的是，
我们切勿以为人们会知道我们所知道的一切。 实际上，使用网络以及通过扩展您的网站而来的人们的多样性保证了您网站的某些访问者的思维过程和/或情况会有所不同，从而导致他们对您的表格的理解与您的理解大相径庭，显示标签。

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
