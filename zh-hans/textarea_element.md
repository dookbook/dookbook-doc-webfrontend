TOPICS: <textarea>
        <textarea> rows attribute
        <textarea> cols attribute
        <textarea> name attribute
        <textarea> maxlength attribute
        <textarea> minlength attribute
        <textarea> required attribute
        <textarea> wrap attribute
        <textarea> autocomplete attribute
        <textarea> autofocus attribute
        <textarea> disabled attribute
        <textarea> readonly attribute
        <textarea> placeholder attribute
        <textarea> spellcheck attribute
        <textarea> form attribute

# HTML `<textarea>` 元素

**HTML `<textarea>` 元素**代表**多行纯文本编辑控件**，当您希望允许用户输入大量自由格式文本（例如，对评论或反馈表单的评论）时，该控件很有用。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*交互式内容*，*列表型、可标记的、可重置的和可提交的与表单相关的元素*。 |
| **允许的内容** | *文本* |
| **标签省略** | 不允许，开始标签和结束标签都是必需的. |
| **允许的父元素** | 任何接受 *短语内容* 的元素. |
| **允许的 ARIA 角色** | 无 |
| **DOM 接口** | **`HTMLTextAreaElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`rows`** | 控件的**可见文本行数**。|
| **`cols`** | 文本控件的**可见宽度**，以平均字符宽度为单位。如果指定，则必须为*正整数*。如果未指定，则默认值为 *`20`*。|
| **`name`** | 控件的**名称**。|
| **`maxlength`** | 用户可以输入的**最大字符数**（*UTF-16* 编码单元）。如果未指定此值，则用户可以输入*不限数量*的字符。|
| **`minlength`** | 用户应输入的**最小字符数**（*UTF-16* 编码单元）。|
| **`wrap`** | 指示控件如何环绕文本。可能的值为：<br><br>**`hard`:** 浏览器会自动插入换行符（CR + LF），以使每行的宽度不超过控件的宽度； <br>**`soft`:** 默认值。浏览器确保值中的所有换行符均由CR + LF对组成，但不会插入任何其他字符 <br>**`off`:** 类似于 `soft`，但将外观更改为空白之前，不要环绕超过 `cols` 的线段，并且 `<textarea>` 可以水平滚动。|
| **`placeholder`** | 描述文本区域预期值的**简短提示**。呈现提示时，占位符文本内的 *回车符或换行符视为换行符*。|
| `spellcheck` | 指定`<textarea>`是否受基础浏览器/OS的拼写检查。 值可以是：<br> **`true`:** 表示该元素需要检查其拼写和语法。<br> **`default`:** 表示该元素将按照 默认行为，可能基于父元素自己的`spellcheck`值。<br> **`false`:** 指示不应对元素进行拼写检查。|

`<textarea>`元素还支持用于 *[`<input>`](/zh-hans/webfrontend/<input>)* 的几种常见属性:
**`form`**、**`autocomplete`**、**`autofocus`**、**`disabled`**、`placeholder`、**`readonly`** 和 **`required`**。

## 基本用法

以下示例显示了一个非常简单的文本区域，其中包含一定数量的行和列以及一些默认内容。

```html
<label for="t">输入文本：</label>
<textarea id="t" name="textarea"
   rows="10" cols="50">Write something here</textarea>
```

**`id`** 属性允许将 `<textarea>` 与 *[`<label>`](/zh-hans/webfrontend/<label>)* 元素相关联以实现可访问性，而 **`name`** 属性则用于设置
关联数据的名称，在提交表单后将其提交给服务器。

使用 **`rows`** 和 **`cols`** 属性可以指定 `<textarea>` 的确切大小。设置这些值是保持一致性的一个好主意，因为浏览器的默认设置可能有所不同。

如果您想要 `<textarea>` 的默认内容，请在开始和结束标签之间输入。`<textarea>` 不支持 `value` 属性。

## 用法：最小和最大长度

**`maxlength`** 指定 `<textarea>` 允许包含的最大字符数。您还可以使用 **`minlength`** 属性设置一个被视为有效的最小长度，
并使用 **`required`** 属性来指定 `<textarea>` 如果为空则不会提交（并且无效）。
这为`<textarea>`提供了简单的验证，它比其他表单元素更为基本
（例如，您不能提供特定的正则表达式来像 [`<input>`](/zh-hans/webfrontend/<input>) 元素一样，使用 *`pattern`* 属性来验证值）。

此示例的最小和最大字符数分别为`10`和`20`。试试看。

```html
<textarea name="textarea"
   rows="5" cols="30"
   minlength="10" maxlength="20">Write something here</textarea>
```

**请注意**，*`minlength`* 不会阻止用户删除字符，从而使输入的数字超过最小值，但确实会使输入 `<textarea>` 的值无效。**还要注意**，即使您设置了 `minlength`
值（例如3），除非您也设置了 *`required`* 属性，否则空的 `<textarea>` 仍然被认为是有效的。

## 用法： 占位符 `placeholder`

本示例设置了一个**占位符**。请注意，当您开始在框中输入内容时，它是如何消失的。

```html
<textarea name="textarea"
   rows="5" cols="30"
   placeholder="Comment text."></textarea>
```

!!! warn "提示"
    如若 `placeholder` 属性里的提示文字需要两行或者多行显示，请用换行符（`&#10;`）来换行

```html
<textarea name="textarea"
   placeholder="hello you&#10;Second line&#10;Third line"></textarea>
```

!!! warn "注意"
    占位符 **`placeholder`** 仅用于显示应输入表单的数据示例；
    但不能替代绑定输入的 *[`<label>`](/zh-hans/webfrontend/<label>)* 元素。

## 用法：禁用和只读

这个例子显示了两个 `<textarea>` - 其中一个是 **`disabled`**，另一个是 **`readonly`**。两者兼而有之，您会看到行为上的差异 — 禁用元素禁用任何方式（并且其值未提交）；
而只读元素可选且其内容可复制（且可以提交），您只是无法编辑内容。

```html
<textarea name="textarea"
   rows="5" cols="30"
   disabled>I am a disabled textarea</textarea>

<textarea name="textarea"
   rows="5" cols="30"
   readonly>I am a readonly textarea</textarea>
```

## CSS 样式

`<textarea>` 是一个替换的元素 - 它具有固有的尺寸，如光栅图像。默认情况下，其 **`display`** 值为 **`block`**。
与其他表单元素相比，它的样式相对容易，其盒模型 (box model)，字体，配色方案等可以使用常规 [[CSS]] 轻松操作。

[样式化 HTML 表单](/zh-hans/webbfrontend/<form>)提供了一些样式化 `<textarea>` 的有用技巧。

### 基线不一致

HTML 规范没有定义 `<textarea>` 的*基线*在哪里，因此不同的浏览器将其设置在不同的位置。请勿在该元素上使用 *`vertical-align: baseline`*，其行为是无法预测的。

### 可调整大小

在大多数浏览器中，`<textarea>` 的大小是可调整的 - 您会注意到右上角的拖动手柄，可用于更改页面上元素的大小。这由 CSS 属性 **`resize`** 控制 - 默认情况下，调整大小是启用的，
但是您可以显式禁用它：

```css
/* 示例： 禁用 <textarea> 可调整大小 */
textarea {
  resize: none;
}
```

### 设置有效值和无效值的样式

`<textarea>` 元素的有效值和无效值（例如，在`minlength`，`maxlength`或`required`所设置的边界之内和之外的值）
可以使用 **`:valid`** 和 **`:invalid`** 伪类突出显示。
例如，根据文本区域的有效或无效来为其设置不同的边框：

```css
textarea:invalid { /*无效时显示的样式*/
  border: 2px dashed red;
}

textarea:valid { /*有效时显示的样式*/
   border: 2px solid lime;
}
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<textarea>` | 支持 | 支持 | 支持 |

## 其他与表单相关的元素

- [`<form>`, `<input>`](/zh-hans/webfrontend/<form>)
- [`<label>`](/zh-hans/webfrontend/<label>)
- [`<fieldset>`, `<legend>`](/zh-hans/webfrontend/<fieldset>)
- [`<button>`](/zh-hans/webfrontend/<button>)
- [`<select>`, `<datalist>`, `<option>`, `<optgroup>`](/zh-hans/webfrontend/<select>)
- [`<output>`](/zh-hans/webfrontend/<output>)
- [`<progress>`](/zh-hans/webfrontend/<progress>)
- [`<meter>`](/zh-hans/webfrontend/<meter>)
