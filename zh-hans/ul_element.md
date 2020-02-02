TOPICS: <ul>
        <li>

# HTML 无序列表： `<ul>`, `<li>`

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
| ~~`compact`~~ | （**废弃**。使用CSS属性 **`line-height`** 代替，默认值`80%`）此布尔属性提示列表是否需要被渲染为更紧凑的样式。用户代理决定如何解释这个属性，且并非所有浏览器都支持它。|
| ~~`type`~~ | （**废弃**。使用CSS属性 **`list-style-type`** 代替。）规定列表的项目符号的类型。值为：*`circle`*，*`disc`*，*`square`*，*`triangle`* (定义在WebTV接口)。|

## HTML 列表条目元素 `<li>`

|  |  |
| :-- | :-- |
| **内容类别** | 无 |
| **允许的内容** | *流式内容* |
| **标签省略** | 如果列表元素的后面紧随另一个 `<li>` 元素，或者它的父元素中没有更多内容，结束标签可以省略。|
| **DOM 接口** | **`HTMLLIElement`** |

## 示例

### 简单的无序列表

```html
<ul>
  <li>first item</li>
  <li>second item</li>
  <li>third item</li>
</ul>
```

### 嵌套的无序列表

```html
<ul>
  <li>first item</li>
  <li>second item      <!-- 注意，此处没有关闭 </li> -->
    <ul>
      <li>second item first subitem</li>
      <li>second item second subitem      <!-- 第二个无序列表嵌套 -->
        <ul>
          <li>second item second subitem first sub-subitem</li>
          <li>second item second subitem second sub-subitem</li>
          <li>second item second subitem third sub-subitem</li>
        </ul>
      </li>           <!-- 关闭第三层无序列表 -->
      <li>second item third subitem</li>
    </ul>
  </li>               <!-- 关闭第二层无序列表 -->
  <li>third item</li>
</ul>
```

### 嵌套 `<ul>` 和 `<ol>`

```html
<ul>
  <li>first item</li>
  <li>second item      <!-- 此处未关闭 </li> -->
    <ol>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ol>
  </li>                <!-- 此处才关闭 </li> -->
  <li>third item</li>
</ul>
```
