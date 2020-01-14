TOPICS: Document.createElement
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createElement()`

在一个 HTML 文档中，**`Document.createElement()`** 方法创建由 `tagName` 指定的HTML元素，或一个`HTMLUnknownElement`，如果`tagName`不被识别。

在一个 XML 文档中，它创建指定的XUL元素。在其他文档中，它创建一个具有null命名空间URI的元素。

要显式指定元素的命名空间URI，请使用 [`document.createElementNS()`](/zh-hans/webfrontend/document.createElementNS)。

## 语法

```javascript
let element = document.createElement(tagName[, options]);
```

| 参数 | 说明 |
| :-- | :-- |
| `tagName` | 指定要创建元素类型的字符串,创建元素时的`nodeName`使用`tagName`的值为初始化,该方法不接受使用限定名称(如:`"html:a"`),在HTML文档上调用`createElement()`方法创建元素之前会将`tagName`转化成小写,在Firefox, Opera 和 Chrome内核中. `createElement(null)` 等同于 `createElement("null")` |
| `options` | 一个可选的参数 `ElementCreationOptions` 是包含一个属性名为 `is` 的对象, 该对象的值是用 `customElements.define()`方法定义过的一个自定义元素的标签名。 为了向前兼容较老版本的 [Custom Elements specification](https://www.w3.org/TR/custom-elements/), 有一些浏览器会允许你传一个值为自定义元素的标签名的字符串作为该参数的值. 可以看 [Extending native HTML elements](https://developers.google.com/web/fundamentals/primers/customelements/#extendhtml) 仔细了解如何使用该参数。<br>这个新元素会有一个 `is` 属性，该属性值为自定义元素的标签名。注意，自定义元素是一项只在某些浏览器可用的实验性特性。

## 返回值

新的元素`[Element]`.

- `element` 是创建的`Element`对象。
- `tagName` 指定将要创建的元素类型的字符串。创建的`element的nodeName`会被初始化为`tagName的`值。该方法不接受带条件的元素名字(例如: `html:a`)。
- `options` 是一个可选的 `ElementCreationOptions` 对象. 如果这个对象被定义并赋予了一个 `is` 特性，则创建的`element`的 `is` 属性会被初始化为这个
特性的值. 如果这个对象没有 `is` 特性，则值为空.

## 示例

创建一个新的`<div>`并且插入到ID为`“div1`”的元素前。

```html
<!DOCTYPE html>
<html>
<head>
  <title>||Working with elements||</title>
</head>
<body>
  <div id="div1">The text above has been created dynamically.</div>
</body>
</html>
```

```javascript
// 文档body元素onload事件, 执行addElement()方法
document.body.onload = addElement;

function addElement () {
  // 创建一个新的div元素
  // 并且给它一个文本
  let newDiv = document.createElement("div");
  let newContent = document.createTextNode("Hi there and greetings!");
  // 添加文本节点 到这个新的div元素.
  newDiv.appendChild(newContent);

  // 添加这个新的元素和它的文本 到 DOM
  let currentDiv = document.getElementById("div1");
  document.body.insertBefore(newDiv, currentDiv);
}

// html和javascript用起来没有问题的, 但是两者之间大概沒有组合起来, 所以下面显示是空白的.

// 实例效果, 看如下注释

// 初始html
//The text above has been created dynamically.

// 加载javascript之后
//Hi there and greetings!
//The text above has been created dynamically.
```

## 注意

- 当在一个被标记为HTML文档的文档对象上执行时，`createElement()`优先将参数转换为小写。
- 当创建一个带限制条件的元素时，请使用`document.createElementNS()`。
- Gecko 2.0(Firefox 4 / Thunderbird 3.3 / SeaMonkey 2.1)之前,quirks模式下tagName可以包含尖括号(<和>)；从Gecko2.0开始，该方法在quirks模式和标准模式下表现一致。
- 从Gecko19.0开始，`createElement(null)`和`createElement("null")`相同。注意`Opera`将`null`字符串化，但是Chrome和IE都会抛出错误。
- 从Gecko22.0(Firefox 22.0 / Thunderbird 22.0 / SeaMonkey 2.19)开始，当参数为`"bgsounds"`, `"multicol"`,
或`"image"`时，`createElement()` 不再使用`HTMLSpanElement`接口， 参数为`"bgsound"` 和 `"multicol"`时，使用`HTMLUnknownElement`，
为`“image”`时使用`HTMLElement` `HTMLElement`。
- `createElement` 的Gecko实现不遵循XML和XHTML的DOM说明文档: 创建元素的`localName`和`namespaceURI`不会被设置为`null`.
- `is` 属性是 [Custom Elements](https://www.w3.org/TR/custom-elements/#attr-is) W3C Working Draft 的一部分，
同时，该属性是一个只在部分浏览器上可用的试验性特性。
