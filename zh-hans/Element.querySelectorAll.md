TOPICS: Element.querySelectorAll

# `Element.querySelectorAll()`

`ParentNode` 混合定义了 **`querySelectorAll()`** 方法 返回一个 `NodeList` 表示元素的列表，把当前的元素作为根与指定的选择器组相匹配。

如果只需要一个结果，请考虑使用 `querySelector()` 方法。

!!! warn "注意"
    此方法实现为`Element.querySelectorAll()`，`Document.querySelectorAll()`和`DocumentFragment.querySelectorAll()`

## 语法

```javascript
elementList = parentNode.querySelectorAll(selectors);
```

| 参数 | 说明 |
| :-- | :-- |
| `selectors` | 一个或多个CSS选择器，这些选择器由逗号隔开。

!!! warn "注意"
    不属于标准CSS语法的字符必须使用反斜杠字符进行转义。 由于JavaScript还使用反斜杠转义，因此在使用这些字符编写字符串文字时必须格外小心。 有关更多信息，请参见转义特殊字符。

## 示例

要获取文档中所有`<p>`元素的`NodeList`：

```javascript
var matches = document.querySelectorAll("p");
```

这个例子返回了所有 `class` 为 `"note"` 或者 `"alert"` 的 `div` 元素的一个列表:

```javascript
var matches = document.querySelectorAll("div.note, div.alert");
```

在这里，我们得到一个`<p>`元素的列表，这些元素的直接父元素是类为`"highlighted"`的`div`，并且位于ID为`"test"`的容器内。

```javascript
var container = document.querySelector("#test");
var matches = container.querySelectorAll("div.highlighted > p");
```

本示例使用属性选择器返回文档中包含名为`"data-src"`的属性的`iframe`元素的列表：

```javascript
var matches = document.querySelectorAll("iframe[data-src]");
```

在这里，属性选择器用于返回ID为`"userlist"`的列表中包含的列表项的列表，列表中的列表项具有`"data-active"`属性，其值为`"1"`：

```javascript
var container = document.querySelector("#userlist");
var matches = container.querySelectorAll("li[data-active=1]");
```

## 用户须知

`querySelectorAll()` 的行为不同于大多数常见的JavaScript DOM库，这可能会导致意外结果。

考虑此HTML及其三个嵌套的`<div>`块。

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

在此示例中，当在具有类`"select"`的`<div>`上下文中选择`".outer .inner"`时，即使`.outer`不是基类的后代，仍会找到具有类`".inner"`的元素。 进行搜索的元素
（`".select"`）。默认情况下，`querySelectorAll()` 仅验证选择器中的最后一个元素是否在搜索范围内。

`:scope`伪类恢复预期的行为，仅匹配基础元素后代的选择器：

```javascript
var select = document.querySelector('.select');
var inner = select.querySelectorAll(':scope .outer .inner');
inner.length; // 0
```
