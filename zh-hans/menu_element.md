TOPICS: <menu>
        <menu> label attribute

# HTML 菜单元素 `<menu>`

**HTML 菜单元素** (**`<menu>`**) 代表用户可以执行或激活的**一组命令**。这包括可能出现在屏幕顶部的*列表菜单*，以及*上下文菜单*（例如，单击按钮后可能出现在按钮下方的上下文菜单）。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*。此外，如果处于*列表菜单*状态，则为*可触知内容*。(*列表菜单*为默认状态。） |
| **允许的内容** | 如果该元素处于*列表菜单*状态：*流式内容*，或者零次或多次出现 [`<li>`](/zh-hans/webfrontend/<li>)，[`<script>`](/zh-hans/webfrontend/<script>)和[`<template>`](/zh-hans/webfrontend/<template>)。<br>如果该元素在*上下文菜单*状态：`<menu>`（仅*上下文菜单*状态），[`<hr>`](/zh-hans/webfrontend/<hr>)，[`<script>`](/zh-hans/webfrontend/<script>) 和 [`<template>`](/zh-hans/webfrontend/<template>)以任何顺序出现零次或多次。 |
| **标签遗漏**| 无，开始标签和结束标签都是必需的。 |
| **允许的父元素** | 任何接受 *流式内容* 的元素。 |
| **允许的 ARIA 角色** | 没有 |
| **DOM 接口** | **`HTMLMenuElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`label`** | 指定**菜单名称**。 在嵌套菜单中使用，以提供一个标签，通过该标签可以访问子菜单。仅当父元素为在*上下文菜单*状态下的 `<menu>` 时才必须指定该属性。|
| `type`| 指定**菜单类型**，值为二者之一。<br><br>**`context`** **上下文菜单**。即*弹出菜单*状态，该状态表示**通过另一个元素激活的一组命令**。如果没指定该属性，并且父元素也是 `<menu>` 元素，则此值为默认值。<br><br>**`toolbar`**：**工具栏**或**列表菜单**。由一系列用于**用户交互的命令组成的工具栏**。如果没指定该属性，则此值为默认值。|

!!! error ""
    菜单按钮尚未在任何已知的浏览器中实现。`<menu>`元素上的`type`属性现在已过时。

## 使用说明

`<menu>` 和 **[`<ul>`](/zh-hans/webfrontend/<ul>)** 元素均表示无序的项目列表。关键区别在于，[`<ul>`](/zh-hans/webfrontend/<ul>)主要包含要显示的项目，而`<menu>`是用于*交互项目*的对象。

!!! error ""
    [`<menuitem>`](/zh-hans/webfrontend/<menuitem>) 元素已过时。

此元素在 HTML 4 中*已弃用*，但在 HTML 5.1 和 HTML 实时标准中已重新引入。

## 上下文菜单

!!! error "请注意，此功能可能随时停止起作用。"
    **不再推荐**此功能。尽管某些浏览器可能仍支持它，但是它可能已经从相关的Web标准中**删除**，正在**被弃**或仅出于兼容性目的而保留。避免使用它，并尽可能更新现有代码。

上下文菜单由一个 `<menu>` 元素组成，该元素包含多个选项，每个可选选项使用 *[`<menuitem>`](/zh-hans/webfrontend/<menuitem>)* 元素 （**废弃**）。
可以用 *[`<hr>`](/zh-hans/webfrontend/<hr>)* 元素，将菜单内容分隔为几部分。

然后，将上下文菜单关联到带 `contextmenu` 属性的元素上。

```html
<!-- 关联 <div> 元素 -->
<div contextmenu="popup-menu">
  Right-click to see the adjusted context menu
</div>

<menu type="context" id="popup-menu">
  <menuitem>Action</menuitem>
  <menuitem>Another action</menuitem>
  <hr/>
  <menuitem>Separated action</menuitem>
</menu>
```

```css
div {
  width: 300px;
  height: 80px;
  background-color: lightgreen;
}
```

## 菜单按钮

上下文菜单也可以关联到带 *`menu`* 属性的 *[`<button>`](/zh-hans/webfrontend/<button>)* 元素。

```html
<!-- 关联按钮元素 <button> -->
<button type="menu" menu="popup-menu">Dropdown</button>

<menu type="context" id="popup-menu">
  <menuitem>Action</menuitem>
  <menuitem>Another action</menuitem>
  <hr/>
  <menuitem>Separated action</menuitem>
</menu>
```

## 工具栏菜单

!!! error ""
    工具栏菜单尚未在任何已知的浏览器中实现。

工具栏菜单由一个`<menu>`元素组成，其内容用以下两种方式之一描述：

- *[`<li>`](/zh-hans/webfrontend/<li>)* 元素组成的无序列表的形式。每个列表项目代表用户可以使用的命令或选项。
- 如果该元素没有 [`<li>`](/zh-hans/webfrontend/<li>) 子元素，则流式内容描述可用的命令和选项。

```html
<!-- A context menu for a simple editor,
   - containing two menu buttons. -->
<menu type="toolbar">
  <li>
    <button type="menu" menu="file-menu">File</button>
    <menu type="context" id="file-menu">
      <menuitem label="New..." onclick="newFile()">
      <menuitem label="Save..." onclick="saveFile()">
    </menu>
  </li>
  <li>
    <button type="menu" menu="edit-menu">Edit</button>
    <menu type="context" id="edit-menu">
      <menuitem label="Cut..." onclick="cutEdit()">
      <menuitem label="Copy..." onclick="copyEdit()">
      <menuitem label="Paste..." onclick="pasteEdit()">
    </menu>
  </li>
</menu>
```
