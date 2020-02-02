TOPICS: <ul>
        <li>

# HTML 无序列表： `<ul>`

**HTML 无序列表元素** (**`<ul>`**) 表示一个无序列表。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，如果 `<ul>` 包含至少一个 `<li>` 元素，那么它就是*可触知内容*。|
| **允许的内容** | 零个或多个 **`<li>`** 元素，可以嵌套使用 *[`<ol>`](/zh-hans/webfrontend/<ol>)* 与 *`<ul>`* 元素。|
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 任何接受*流式内容*的元素 |
| **允许的 ARIA 角色** | `directory`, `group`, `listbox`, `menu`, `menubar`, `radiogroup`, `tablist`, `toolbar`, `tree`, `presentation` |
| **DOM 接口** | **`HTMLUListElement`** |

## 属性

此元素仅含有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| ~~`compact`~~ | （**废弃**。使用CSS **`line-height`** 代替，值默认`80%`）此布尔属性提示列表是否需要被渲染为更紧凑的样式。用户代理决定如何解释这个属性，且并非所有浏览器都支持它。|
| ~~`type`~~ | （**废弃**。使用CSS **`list-style-type`** 代替。）规定列表的项目符号的类型。值为：*`circle`*，*`disc`*，*`square`*，*`triangle`* (定义在WebTV接口)。|

## 使用说明

- `<ul>` 元素用来将没有数字顺序的一组数据进行分组，并且它们的数字顺序是没有意义的。举个例子，无序列表的列表项通常通过一个字符进行装饰，这些字符的形式可以是点，圆乃至方形．虽然这个字符没有
直接在页面上定义，但是可以用与之相关的 CSS 对其进行操作，例如使用 `list-style-type` 属性。
- 在 [`<ol>`](/zh-hans/webfrontend/<ol>) 和 `<ul>` 元素中，嵌套列表没有深度和嵌套顺序的限制。
[`<ol>`](/zh-hans/webfrontend/<ol>) 和 `<ul>` 元素二者都代表一组数据，不过它们彼此是有区别的，ol元素中的顺序是有意义的。如果想确定你到底需要使用哪一个列表元素，你可以试着去改变数据的顺序。如果想表达的语义改变了，你就需要使用ol元素，否则你该使用ul元素。

## `<li>`

**HTML `<li>` 元素** （或称 HTML 列表条目元素） 用于表示列表里的条目。它必须包含在一个父元素里：一个有序列表([`<ol>`](/zh-hans/webfrontend/<ol>))，一个无序列表(`<ul>`)，
或者一个菜单 ([`<menu>`](/zh-hans/webfrontend/<menu>))。在菜单或者无序列表里，列表条目通常用点排列显示；在有序列表里，列表条目通常在左边显示按升序排列的计数，例如数字或者字母。

|  |  |
| :-- | :-- |
| 内容类别 | 无 |
| **允许的内容** | 流式内容 |
| **标签省略** | 如果列表元素的后面紧随另一个 `<li>` 元素，或者它的父元素中没有更多内容，结束标签可以省略。|
| **允许的父元素** | `<ul>`、[`<ol>`](/zh-hans/webfrontend/<ol>)、 或者 [`<menu>`](/zh-hans/webfrontend/<menu>) 元素。过时的 [`<dir>`](/zh-hans/webfrontend/<dir>) 也可以作为父元素，但是并不提倡。|
| **DOM 接口** | HTMLLIElement |
| **元素类型** | 块级 |

| 属性 | 描述 |
| :-- | :-- |
| `value` | 这个整数型属性表明了本 `<li>` 元素在有序列表 （由 [`<ol>`](/zh-hans/webfrontend/<ol>) 元素定义）中的序号。本属性值只能用数字，即使列表使用罗马数字或字母来展示。随后的列表条目会从设置的值开始计数。value 属性对于无序列表 (`<ul>`) 或者菜单 ([`<menu>`](/zh-hans/webfrontend/<menu>)) 无效。|

## 示例

### 简单的例子

```html
<ul>
  <li>first item</li>
  <li>second item</li>
  <li>third item</li>
</ul>
```

### 嵌套列表

```html
<ul>
  <li>first item</li>
  <li>second item      <!-- Look, the closing </li> tag is not placed here! -->
    <ul>
      <li>second item first subitem</li>
      <li>second item second subitem      <!-- Same for the second nested unordered list! -->
        <ul>
          <li>second item second subitem first sub-subitem</li>
          <li>second item second subitem second sub-subitem</li>
          <li>second item second subitem third sub-subitem</li>
        </ul>
      </li>           <!-- Closing </li> tag for the li that contains the third unordered list -->
      <li>second item third subitem</li>
    </ul>
  </li>               <!-- Here is the closing </li> tag -->
  <li>third item</li>
</ul>
```

### 嵌套 `<ul>` 和 `<ol>`

```html
<ul>
  <li>first item</li>
  <li>second item      <!-- Look, the closing </li> tag is not placed here! -->
    <ol>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ol>
  </li>                <!-- Here is the closing </li> tag -->
  <li>third item</li>
</ul>
```
