TOPICS: <button>

# `<button>`

**HTML`<button>`元素** 表示可单击的按钮，可以用在表单或文档其它需要使用简单标准按钮的地方。 默认情况下，HTML按钮的显示样式接近于`user agent`所在的宿主系统平台（用户操作系统）的按钮，但你可以使用CSS来改变按钮的样貌。

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*交互式内容*，列出的，可标记的和可提交的与表单相关的元素，*可触知的内容*。 |
| **允许的内容** | *短语内容*，但不得包含*交互内容*。 |
| **标签遗漏** | 无，开始标签和结束标签都是必需的。 |
| **允许的父元素** | 任何接受*短语内容*的元素。 |
| **允许的ARIA角色** | `checkbox`, `link`, `menuitem`, `menuitemcheckbox`, `menuitemradio`, `radio`, `switch`, `tab` |
| **DOM 接口** | **`HTMLButtonElement`** |

## 属性

该元素的属性包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `autofocus` | 使用此布尔属性，可以指定在页面加载时按钮应具有输入焦点，除非用户将其覆盖，例如通过键入其他控件来覆盖它。 文档中只有一个与表单相关的元素可以指定此属性 |
| `autocomplete` | 在`<button>`上使用此属性是非标准且特定于Firefox的。 默认情况下，与其他浏览器不同，[Firefox保持动态禁用状态](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)页面加载中的`<button>`标签。 将此属性的值设置为`off`（即`autocomplete="off"`）会禁用此功能。请参阅[bug 654072](https://bugzilla.mozilla.org/show_bug.cgi?id=654072)。 |
| `disabled` | 此布尔值属性指示用户无法与按钮进行交互。 如果未指定此属性，则按钮从包含元素（例如，[`<fieldset>`](/zh-hans/webfrontend/<fieldset>)）继承其设置。 如果没有包含设置了**disabled**属性的包含元素，则将启用按钮。<br>与其他浏览器不同，Firefox默认情况下将在整个页面加载期间保持动态[`<disable>`](/zh-hans/webfrontend/<disable>)状态的禁用状态 。 使用`autocomplete`属性来控制此功能。|
| `form` | 与按钮关联的表单元素（其表单所有者）。 该属性的值必须是同一文档中[`<form>`](/zh-hans/webfrontend/<form>)元素的id属性。 如果未指定该属性，则`<button>`元素将与祖先的[`<form>`](/zh-hans/webfrontend/<form>)元素（如果存在）相关联。 这个属性使您可以将`<button>`元素与文档中任何地方的[`<form>`](/zh-hans/webfrontend/<form>)元素相关联，而不仅仅是作为[`<form>`](/zh-hans/webfrontend/<form>)元素的后代。|
| `formaction` | 处理按钮提交的信息的程序的URI。 如果指定，它将覆盖按钮表单所有者的`action`属性。|
| `formenctype` | 如果按钮是一个提交按钮，则此属性指定用于将表单提交到服务器的内容类型。 可能的值为：<br>`application/x-www-form-urlencoded`：如果未指定属性，则为默认值。<br>`multipart/form-data`：如果您使用的是`type`属性设置为`file`的`input`元素。<br>`text/plain` <br>如果指定了此属性，它将覆盖按钮表单所有者的enctype属性。|
| `formmethod` | 如果按钮是一个提交按钮，则此属性指定浏览器用来提交表单的HTTP方法。 可能的值为：<br>`post`：来自表单的数据包含在表单主体中，并发送到服务器。<br>`get`：来自表单的数据附加到表单属性URI， 加上“？” 作为分隔符，结果URI被发送到服务器。 当表单没有副作用且仅包含ASCII字符时，请使用此方法。<br>如果指定，则此属性将覆盖按钮表单所有者的`method`属性。|
| `formnovalidate` | 如果按钮是一个提交按钮，则此布尔属性指定在提交表单时不对其进行验证。 如果指定了此属性，它将覆盖按钮的表单所有者的`novalidate`属性。|
| `formtarget` | 如果按钮是“提交”按钮，则此属性是名称或关键字，指示在提交表单后在何处显示收到的响应。 这是浏览上下文（例如，选项卡，窗口或嵌入式框架）的名称或关键字。 如果指定了此属性，它将覆盖按钮的表单所有者的target属性。 以下关键字具有特殊含义：<br>`_self`：将响应加载到与当前响应相同的浏览上下文中。 如果未指定属性，则此值为默认值。<br>`_blank`：将响应加载到新的未命名浏览上下文中。<br>`_parent`：将响应加载到当前浏览器的父浏览上下文中。 如果没有父级，则此选项的行为与_self相同。<br>`_top`：将响应加载到顶级浏览上下文（即，当前上下文的祖先的浏览上下文， 并且没有父母）。 如果没有父母，该选项的行为与_self相同。|
| `name` | 按钮的名称，与表单数据一起提交。|
| `type` | 按钮的类型。 可能的值为：<br>`submit`：按钮将表单数据提交到服务器。 如果未指定该属性，或者该属性被动态更改为空或无效值，则为默认设置。<br>`reset`：该按钮将所有控件重置为其初始值。 该按钮没有默认行为。 它可以具有与元素的事件相关联的客户端脚本，这些脚本在事件发生时触发。|
| `value` | 按钮的初始值。 它定义与与表单数据一起提交的按钮关联的值。 提交表单时，此值以参数形式传递给服务器。|

## 笔记

`<button>`元素比[`<input>`](/zh-hans/webfrontend/<input>)元素更容易样式化。 您可以添加内部HTML内容（例如[`<em>`](/zh-hans/webfrontend/<em>)，[`<strong>`](/zh-hans/webfrontend/<strong>)甚至[`<img>`](/zh-hans/webfrontend/<img>)），并使用`::after`和`::before`
伪元素来实现复杂的呈现，而[`<input>`](/zh-hans/webfrontend/<input>)仅接受文本值属性 。

如果您的按钮不是要向服务器提交表单数据，请确保将其`type`属性设置为`button`。 否则，他们将尝试提交表单数据并加载（不存在）响应，这可能会破坏文档的当前状态。

!!! error "Don't try this at home"
    Internet Explorer 7有一个错误，即在提交具有`<button type =“ submit” name =“ myButton” value =“ foo”>点击我</ button>`
    的表单时，发送的POST数据将导致`myButton=Click` me而不是 `myButton=foo`。 在Internet Explorer 6中，问题更加严重，其中通过按钮提交表单
    会提交所有表单按钮，其问题与Internet Explorer 7中的问题相同。这些问题已在Internet Explorer 8中得到解决。

!!! warn "Don't try this at home"
    与其他浏览器不同，Firefox默认情况下会[保持动态禁用状态](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
    页面加载中的`<button>`标签。 将autocomplete属性的值设置为关禁用此功能。请参阅[bug 654072](https://bugzilla.mozilla.org/show_bug.cgi?id=654072)。

Firefox 35之前的Android Firefox版本在所有按钮上均设置了默认的`background-image`渐变
（请参阅[bug 763671](https://bugzilla.mozilla.org/show_bug.cgi?id=763671))。可以使用`background-image:none`禁用它。

## 示例

```html
<button name="button">Click me</button>
```

## 可达性问题

### 图标按钮

仅使用图标表示功能的按钮没有可访问的名称。可访问名称为诸如屏幕阅读器之类的辅助技术提供了程序化的钩子，以在他们解析文档并生成可访问性树时进行访问。然后辅助技术使用可访问性树导航和操纵页面内容。

要给图标按钮起一个易于访问的名称，请为`<button>`元素提供一串文字，以简洁地描述按钮的功能。

```html
<button name="favorite" type="button">
  <svg aria-hidden="true" viewBox="0 0 10 10"><path d="M7 9L5 8 3 9V6L1 4h3l1-3 1 3h3L7 6z"/></svg>
  Add to favorites
</button>
```

如果要在视觉上隐藏按钮的文本，可以使用的一种便捷方法是使用[属性的组合](https://gomakethings.com/hidden-content-for-better-a11y/#hiding-the-link)以从屏幕上将其删除，但可以通过辅助技术对其进行解析。

但是值得注意的是，使按钮文本在视觉上清晰可见可以帮助那些可能不熟悉图标含义或不了解按钮用途的人们。这对于技术水平不高的人，或对于图标按钮使用的图像可能具有不同文化解释的人们而言，尤其重要。

- [什么是易用名称？ | Paciello集团](https://developer.paciellogroup.com/blog/2017/04/what-is-an-accessible-name/)
- [MDN了解WCAG，准则4.1的说明](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Robust#Guideline_4.1_%E2%80%94_Compatible_Maximize_compatibility_with_current_and_future_user_agents_including_assistive_technologies)
- [了解成功标准4.1.2 | W3C了解WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/ensure-compat-rsv.html)

### 大小和接近度

尺寸

诸如按钮之类的交互式元素应提供足够大的区域，以便于激活它们。这可以为各种人提供帮助，包括运动控制问题的人和使用非精确形式的输入（例如手写笔或手指）的人。建议最小互动尺寸为44 x 44[CSS像素](https://www.w3.org/TR/WCAG21/#dfn-css-pixels)。

- [了解成功标准2.5.5：目标规模| W3C了解WCAG 2.1](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html)
- [目标尺寸和2.5.5 | 阿德里安·罗塞利（Adrian Roselli）](http://adrianroselli.com/2019/06/target-size-and-2-5-5.html)
- [快速测试：大型接触目标-A11Y项目](https://a11yproject.com/posts/large-touch-targets/)

接近

大量交互式内容（包括按钮）应放置在彼此靠近的视觉位置，并应插入空格以将它们分开。此间距对于遇到运动控制问题的人很有用，他们可能会意外激活错误的交互式内容。

可以使用CSS属性（例如`margin`）创建间距。

- [手部震动和巨大按钮问题-Axess Lab](https://axesslab.com/hand-tremors/)

### 火狐浏览器

Firefox将在焦点按钮上添加一个小虚线边框。该边框是通过CSS在浏览器样式表中声明的，但是您可以根据需要使用`button::``-moz-focus-inner``{}`来添加边框以覆盖自己的样式。

如果被覆盖，重要的是要确保将焦点移到按钮上时状态变化足够高，以使处于弱视状态的人们能够感知到它。

通过将按钮文本的亮度和背景颜色值与放置按钮的背景进行比较来确定颜色对比度。 为了满足当前的[Web内容可访问性指南（WCAG）](https://www.w3.org/WAI/intro/wcag)，
文本内容的比例为4.5：1，较大文本的比例为3：1 例如标题。 大文本定义为18.66像素和“粗体”或更大，或24像素或更大。

- [WebAIM：颜色对比度检查器](https://webaim.org/resources/contrastchecker/)
- [MDN了解WCAG，准则1.4解释](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#Guideline_1.4_Make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [了解成功标准1.4.3 | W3C了解WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)

### 点击并专注

单击`<button>`是否（默认情况下）使其成为焦点，这取决于浏览器和操作系统。 `type="button"`和`type ="submit"`的[`<input>`](/zh-hans/webfrontend/<input>)结果相同。

**单击`<button>`是否可以使其具有焦点？**

| 桌面浏览器 | Windows 8.1 | OS X 10.X |
| :-- | :-- | :-- |
| Firefox | 是-Firefox 30.0 | 否（甚至带有tabindex）Firefox 63 |
| Chrome | 是-Chrome 35 | 是的-Chrome 65 |
| Safari | N/A | 否（即使带有tabindex）Safari 12 |
| Internet Explorer | 是-Internet Explorer 11不适用 |
| Presto | 是的-Opera 12 | 是的-Opera 12 |

**轻触`<button>`可以使其具有焦点吗？**

| 移动浏览器 | iOS 7.1.2 | Android 4.4.4 |
| :-- | :-- | :-- |
| Safari Mobile | 否（即使使用tabindex）| 不适用 |
| Chrome 35 | 否（即使使用tabindex）| 是 |
