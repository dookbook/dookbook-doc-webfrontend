TOPICS: <select>
        <option>
        <optgroup>
        <select> name attribute
        <select> multiple attribute
        <select> required attribute
        <select> disabled attribute
        <select> size attribute
        <select> autocomplete attribute
        <select> autofocus attribute
        <select> form attribute
        <option> value attribute
        <option> selected attribute
        <option> disabled attribute
        <option> label attribute
        <optgroup> label attribute
        <optgroup> disabled attribute

# HTML 下拉列表 `<select>`/`<option>`/`<optgroup>`

**HTML `<select>` 元素**提供一个**选项菜单的控件**。

**HTML `<option>` 元素**用于定义在 *`<select>`*, *`<optgroup>`* 或
*[`<datalist>`](/zh-hans/webfrontend/<datalist>)*元素中包含的项。
`<option>` 可以在弹出窗口和 HTML 文档中的其他项目列表中表示菜单项。

**HTML `<optgroup>` 元素**会把相关的选项 *`<option>`* 组合在一起。

## 技术摘要

| - | `<select>` | `<option>` | `<optgroup>` |
| :-- | :-- | :-- | :-- |
| **内容分类** | *流式内容*, *短语内容*, *交互内容*, *列表型、可标签化的、可重置的、可提交的表单元素相关的元素*。| 无。| 无。|
| **允许的内容** | 零或多个 *`<option>`* 或 *`<optgroup>`* 元素。| 文本。| 零或多个 *`<option>`* 元素。|
| **标签省略** | 不允许，开始和结束标签都不能省略。| 不允许。| 不允许。|
| **允许的父元素** | 任何可接受 *短语内容* 的元素。| *`<select>`*，*`<optgroup>`* 和 *`<datalist>`* 元素。| *`<select>`* 元素。|
| **允许的 ARIA 角色** | `menu` | 无 | 无 |
| **DOM 接口** | **`HTMLSelectElement`** | **`HTMLOptionElement`** | **`HTMLOptGroupElement`** |

## `<select>` 属性

包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| **`name`** | 控件**名称**。用于对提交到服务器后的表单数据进行标识，或者在客户端通过 JavaScript 引用表单数据。|
| **`multiple`** | *布尔*属性，标记 `<select>` 是否可以多选。默认是单选。|
| **`required`** | *布尔*属性，标记 `<select>` 的值不能为空。|
| **`disabled`** | 这个布尔值的属性表明一个用户是否可以操控该表单对象。如果这个属性没有被明确定义, 则从它的父元素继承, 例如 `fieldset`; 如果没有父元素设置`disabled`属性, 那么默认该表单对象启用。 |
| **`size`** | 如果控件显示为滚动列表框，则此属性表示为控件中同时可见的行数。浏览器不需要将选择元素呈现为滚动列表框。HTML 5 规定默认值为 *`1`*。|
| **`autocomplete`** | `DOMString` 提供用户代理自动完成功能的提示。|
| **`autofocus`** | *布尔*属性，能够让一个对象在页面加载的时候获得焦点。在一个页面上下文中, 只有一个表单对象可以有这个属性。|
| **`form`** | `<select>` 所关联的 *[`<form>`](/zh-hans/webfrontend/<form>)*。如果这个属性被明确定义, 那么它的值一定是在同一个文档中 `<form>` 的 **`id`**。这样能够让你把 `<select>` 标签放在任何的位置, 不仅限于作为 `<form>` 的后代元素。|

## `<option>` 属性

| 属性 | 描述 |
| :-- | :-- |
| **`value`** | 这个属性的内容代表这个选项选中的话，提交给表单的值。如果省略了这个属性，值就从选项元素的文本内容中获取。|
| **`selected`** | *布尔*属性，如果存在, 则表明该选项**初始被选中**。如果 `<option>` 元素是`<select>` 元素的后继，并且它的 `multiple` 属性没有设置，则这个 `<select>`
元素只有一个 `<option>` 元素可以拥有 `selected` 属性。|
| **`disabled`** | *布尔*属性，如果设置了，则这个选项就不是可选的。浏览器通常会将这种控件显示为灰色，并且不再接受任何浏览器事件，例如鼠标点击或者焦点相关的事件。如果这个属性没有设置，如果元素的祖先是禁用的 `<optgroup>` 元素，该元素仍然是禁用的 。|
| `label` | 这个属性是用于表示选项含义的文本。如果 `label` 属性没有定义，它的值就是元素文本内容。|

## `<optgroup>` 属性

| 属性 | 描述 |
| :-- | :-- |
| **`label`** | 选项组的名字，当在用户界面标记(`label`)选项的时候可以被浏览器使用。使用这个元素时必须加上这个属性。|
| **`disabled`** | 如果设置了这个布尔值，那么这个选项组中将没有选项是可以被选择的。通常浏览器会置灰这样的控件，它不会再接受任何浏览器事件，例如鼠标点击或者焦点相关的事件。|

## 基本用法

```html
<!-- 示例： 选择列表，第二项默认选中 -->
<select name="car">
  <option value="car1">车 1</option>
  <option value="car2" selected>车 2</option>
  <option value="car3">车 3</option>
</select>
```

## 多选项用法

!!! warn ""
    注意: `<optgroup>` 元素不能嵌套。

```html
<select name="choice" multiple>
  <optgroup label="Group 1">
    <option value="1.1">Option 1.1</option>
  </optgroup>
  <optgroup label="Group 2">
    <option value="2.1">Option 2.1</option>
    <option value="2.2" selected>Option 2.2</option>
  </optgroup>
  <optgroup label="Group 3" disabled>
    <option value="3.1">Option 3.1</option>
    <option value="3.2">Option 3.2</option>
    <option value="3.3">Option 3.3</option>
  </optgroup>
</select>
```

## 用 CSS 美化

众所周知，`<select>` 元素很难用 CSS 进行高效的设计。你可以影响任何元素的某些方面 - 例如，操纵框模型，显示的字体等，你可以使用 **appearance** 属性来删除默认的系统外观。

但是，这些属性不会在浏览器之间产生一致的结果，并且很难在列中将不同类型的表单元素相互排列。 `<select>` 元素的内部结构复杂，难以控制。 如果你想获得完全控制，你应该考虑使用一个具有良好设施的库
来构建窗体小部件（例如jQuery UI），或者尝试使用非语义元素，[[JavaScript]] 和WAI-ARIA滚动自己的下拉菜单来提供语义。
