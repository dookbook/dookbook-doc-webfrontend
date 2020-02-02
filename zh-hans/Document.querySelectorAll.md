TOPICS: Document.querySelectorAll
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.querySelectorAll()`

返回与指定的选择器组匹配的文档中的元素列表 (使用深度优先的先序遍历文档的节点)。返回的对象是 `NodeList` 。

!!! warn "注意"
    此方法基于`Node` 混合的 `querySelectorAll()` 实现。

## 语法

```javascript
elementList = parentNode.querySelectorAll(selectors);
```

| 参数 | 说明 |
| :-- | :-- |
| `selectors` | 一个 `DOMString` 包含一个或多个匹配的选择器。这个字符串必须是一个合法的 CSS selector 如果不是，会抛出一个 `SyntaxError` 错误 |

!!! warn "注意"
    必须使用反斜杠字符转义不属于标准CSS语法的字符。 由于JavaScript也使用反斜杠转义，因此在使用这些字符编写字符串文字时必须特别小心。

**返回值**: 一个静态 `NodeList`，包含一个与至少一个指定选择器匹配的元素的`Element`对象，或者在没有匹配的情况下为空`NodeList`

!!! warn "注意"
    如果`selectors`参数中包含 CSS伪元素，则返回的列表始终为空。

## 获取匹配列表

要获取文档中所有`<p>`元素的`NodeList`。

```javascript
var matches = document.querySelectorAll("p");
```

此示例返回文档中所有`<div>`元素的列表，其中class包含`"note"`或`"alert"`：

```javascript
var matches = document.querySelectorAll("div.note, div.alert");
```

在这里，我们得到一个`<p>`元素的列表，其直接父元素是一个class为`"highlighted"`的div，并且位于ID为`"test"`的容器内。

```javascript
var container = document.querySelector("#test");
var matches = container.querySelectorAll("div.highlighted > p");
```

此示例使用属性选择器返回文档中属性名为`"data-src"`的iframe元素列表：

```javascript
var matches = document.querySelectorAll("iframe[data-src]");
```

这里，属性选择器用于返回ID为`"userlist"`的列表中包含值为"1"的`"data-active"`属性的元素

```javascript
var container = document.querySelector("#userlist");
var matches = container.querySelectorAll("li[data-active='1']");
```

## 访问匹配项

一旦返回匹配元素的`NodeList`，就可以像任何数组一样检查它。 如果数组为空（即，其length属性为0），则找不到匹配项。

否则，您只需使用标准数组方法来访问列表的内容。 您可以使用任何常见的循环语句，例如：

```javascript
var highlightedItems = userList.querySelectorAll(".highlighted");

highlightedItems.forEach(function(userItem) {
  deleteUser(userItem);
});
```

## 用户备注

`querySelectorAll()` 的行为与大多数常见的JavaScript DOM库不同，这可能会导致意外结果。

考虑这个HTML及其三个嵌套的`<div>`块

```html
<div class="outer">
  <div class="select">
    <div class="inner">
    </div>
  </div>
</div>
```

```javascript
var select = document.querySelector('.select');
var inner = select.querySelectorAll('.outer .inner');
inner.length; // 1, not 0!
```

在这个例子中，当在`<div>`上下文中选择带有`"select"`类的`".outer .inner"`时，仍然会找到类`".inner"`的元素，即使`.outer`不是基类的后代 执行搜索的元素
（`".select"`）。默认情况下，`querySelectorAll()`仅验证选择器中的最后一个元素是否在搜索范围内。

`:scope` 伪类符合预期的行为，只匹配基本元素后代的选择器：

```javascript
var select = document.querySelector('.select');
var inner = select.querySelectorAll(':scope .outer .inner');
inner.length; // 0
```
