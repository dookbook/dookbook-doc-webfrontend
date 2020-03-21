TOPICS: <button>
        <button> type attribute
        <button> name attribute
        <button> value attribute
        <button> autofocus attribute
        <button> form attribute
        <button> formaction attribute
        <button> formmethod attribute
        <button> formenctype attribute
        <button> formnovalidate attribute
        <button> formtarget attribute

# HTML 按钮元素 `<button>`

**HTML `<button>` 元素** 表示**可单击的按钮**，可以用在表单或文档其它需要使用简单标准按钮的地方。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*交互内容*，*列表型，可标记和可提交的与表单相关的元素*，*可触知内容*。 |
| **允许的内容** | *短语内容*，但不得包含*交互内容*。 |
| **标签省略** | 不允许，开始标签和结束标签都是必需的。 |
| **允许的父元素** | 任何接受 *短语内容* 的元素。 |
| **允许的ARIA角色** | `checkbox`, `link`, `menuitem`, `menuitemcheckbox`, `menuitemradio`, `radio`, `switch`, `tab` |
| **DOM 接口** | **`HTMLButtonElement`** |

## 属性

该元素的属性包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`type`** | **按钮的类型**。可能的值为：<br>**`submit`**：（*默认*值）按钮将表单数据提交到服务器。<br>**`reset`**： 该按钮将所有控件重置为其初始值。<br>**`button`**： 该按钮没有默认行为。它可以触发事件，由客户端脚本执行事件处理。|
| **`disabled`** | *布尔*值，指示用户**无法**与按钮进行交互。如果该属性为指定，则它将继承包含它的元素的 **`disabled`** 值。|
| **`name`** | **按钮的名称**，与表单数据一起提交。|
| **`value`** | 按钮关联的**初始值**。提交表单时，此值以参数形式传递给服务器。|
| **`autofocus`** | *布尔*值，指定在页面加载时应具有*焦点*，除非用户将其覆盖。文档中只有一个与表单相关的元素可以指定此属性。|
| `form` | 指定关联的 *[`<form>`](/zh-hans/webfrontend/<form>)* 元素。该属性的值必须是同一文档中 *`<form>`* 元素的 **`id`** 属性。这个属性使您可以将该元素与文档中任何地方的 `<form>` 元素相关联，而不必嵌入其中。|
| `formaction` | 覆盖所关联的 *[`<form>`](/zh-hans/webfrontend/<form>)* 的 **`action`** 属性。|
| `formmethod` | 覆盖所关联的 *[`<form>`](/zh-hans/webfrontend/<form>)* 的 **`method`** 属性。|
| `formenctype` | 覆盖所关联的 *[`<form>`](/zh-hans/webfrontend/<form>)* 的 **`enctype`** 属性。|
| `formnovalidate` | 覆盖所关联的 *[`<form>`](/zh-hans/webfrontend/<form>)* 的 **`novalidate`** 属性。|
| `formtarget` | 覆盖所关联的 *[`<form>`](/zh-hans/webfrontend/<form>)* 的 **`target`** 属性。|

## 注意事项

`<button>` 元素比 *[`<input>`](/zh-hans/webfrontend/<input>)* 元素更容易样式化。您可以添加内部 HTML 内容
（例如 *[`<em>`](/zh-hans/webfrontend/<em>)*，*[`<strong>`](/zh-hans/webfrontend/<strong>)* 甚至
*[`<img>`](/zh-hans/webfrontend/<img>)*），并使用 *`::after`* 和 *`::before`*
伪元素来实现复杂的呈现，而 `<input>` 仅接受文本值属性 。

如果按钮不是要向服务器提交表单数据，请确保将其 `type` 属性设置为 **`button`**。否则，他们将尝试提交表单数据并加载（不存在）响应，这可能会破坏文档的当前状态。

## 简单示例

```html
<button type="button" value="2">Click me</button>
<script>
  document.querySelector('button').onclick = function(e) {
    alert(this.value)
  }
</script>
```

## 无障碍性问题

### 图标按钮

按钮的可访问名称为诸如屏幕阅读器之类的辅助技术提供了程序化的钩子，以在他们解析文档并生成可访问性树时进行访问。然后辅助技术使用可访问性树导航和操纵页面内容。

要给图标按钮起一个易于访问的名称，请为 `<button>` 元素提供一串文字，以简洁地描述按钮的功能。

```html
<button name="favorite" type="button">
  <svg aria-hidden="true" viewBox="0 0 10 10"><path d="M7 9L5 8 3 9V6L1 4h3l1-3 1 3h3L7 6z"/></svg>
  Add to favorites
</button>
```

使按钮文本在视觉上清晰可见可以帮助那些可能不熟悉图标含义或不了解按钮用途的人们。
这对于技术水平不高的人，或对于图标按钮使用的图像可能具有不同文化解释的人们而言，尤其重要。

### 尺寸大小和视觉位置

#### 尺寸大小

诸如按钮之类的交互式元素应提供足够大的区域，以便于激活它们。这可以为各种人提供帮助，包括运动控制问题的人和使用非精确形式的输入（例如手写笔或手指）的人。建议最小互动尺寸为 **44 x 44** [CSS像素](https://www.w3.org/TR/WCAG21/#dfn-css-pixels)。

#### 视觉位置

大量交互式内容（包括按钮）应放置在彼此靠近的视觉位置，并应插入空格以将它们分开。此间距对于遇到运动控制问题的人很有用，他们可能会意外激活错误的交互式内容。

可以使用 CSS 属性（例如 `margin` ）创建间距。比如[手部震动和巨大按钮问题](https://axesslab.com/hand-tremors/)

### 点击并专注

单击`<button>`是否（默认情况下）使其成为焦点，这取决于浏览器和操作系统。
`type="button"` 和 `type ="submit"` 的 [`<input>`](/zh-hans/webfrontend/<input>) 结果相同。

#### 单击 `<button>` 是否可以使其具有焦点

| 桌面浏览器 | Windows 8.1 | OS X 10+ |
| :-- | :-- | :-- |
| Firefox 63+ | 是 | 否（即使带有 `tabindex`）|
| Chrome 65+ | 是 | 是 |
| Safari 12+ | N/A | 否（即使带有 `tabindex`）|

#### 触控 `<button>` 是否可以使其具有焦点

| 移动浏览器 | iOS 7.1+ | Android 4.4+ |
| :-- | :-- | :-- |
| Safari Mobile | 否（即使使用 `tabindex`）| 不适用 |
| Chrome 35 | 否（即使使用 `tabindex`）| 是 |

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<button>` | 支持 | 支持 | 支持 |
