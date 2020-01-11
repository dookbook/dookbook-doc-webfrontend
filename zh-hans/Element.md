TOPICS: Element
        Element.accessKey
        Element.attributes
        ParentNode.childElementCount
        ParentNode.children
        Element.classList
        Element.className
        Element.clientHeight
        Element.clientLeft
        Element.clientTop
        Element.clientWidth
        Element.firstElementChild
        Element.id
        element.innerHTML
        Element.lastElementChild
        Element.localName
        Element.name
        Element.namespaceURI
        element.nextElementSibling
        element.outerHTML
        Element.part
        Element.prefix
        Element.previousElementSibling
        Element.scrollHeight
        Element.scrollLeft
        Element.scrollTop
        Element.scrollWidth
        Element.shadowRoot
        Element.slot
        Element.tagName
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript Element 对象: `element`

**`Element`** 是一个通用性非常强的基类，所有 [`Document`](/zh-hans/webfrontend/Document) 对象下的对象都继承自它。这个接口描述了所有相同种类的
元素所普遍具有的方法和属性。一些接口继承自 `Element` 并且增加了一些额外功能的接口描述了具体的行为。例如， `HTMLElement` 接口是所有 HTML 元素的基本接口，而 `SVGElement`
接口是所有 SVG 元素的基础。大多数功能是在这个类的更深层级（hierarchy）的接口中被进一步制定的。

在 Web 平台的领域以外的语言，比如 XML，通过 `XMLElement` 接口，同样也实现了 `Element` 接口。

## `Element.accessKey`

元素的 **`Element.accessKey`** 属性设置了这样一个按键——用户通过敲击这个键把焦点跳转到这个元素上。

!!! warn "注"
    `Element.accessKey` 属性很少使用，因为它很容易与现代浏览器自带的快捷键冲突。为了解决这个问题，浏览器约定`accessKey`键与特定按键一起按
    （比如 !!!Alt!!! + !!!accessKey!!!）来生效快捷键行为。

## `Element.attributes`

**`Element.attributes`** 属性返回该元素所有属性节点的一个实时集合。该集合是一个 `NamedNodeMap` 对象，不是一个数组，所以它没有 数组 的方法，其包含的 属性
节点的索引顺序随浏览器不同而不同。更确切地说，`attributes` 是字符串形式的名/值对，每一对名/值对对应一个属性节点。

语法

```javascript
var attr = element.attributes;
```

示例

基本示例

```javascript
// 获取文档中的第一个 <p> 元素
var para = document.getElementsByTagName("p")[0];
var atts = para.attributes;`
```

遍历元素的属性

索引有利于遍历一个元素的所有属性。

在以下例子中会遍历文档中 id 为 "paragraph" 的元素的属性节点，并打印出来。

```html
<!DOCTYPE html>

<html>

 <head>
  <title>Attributes example</title>
  <script type="text/javascript">
   function listAttributes() {
     var paragraph= document.getElementById("paragraph");
     var result= document.getElementById("result");

     // First, let's verify that the paragraph has some attributes
     if (paragraph.hasAttributes()) {
       var attrs = paragraph.attributes;
       var output= "";
       for(var i=attrs.length-1; i>=0; i--) {
         output+= attrs[i].name + "->" + attrs[i].value;
       }
       result.value = output;
     } else {
       result.value = "没有属性可显示"
     }
   }
  </script>
 </head>

<body>
 <p id="paragraph" style="color: green;">Sample Paragraph</p>
 <form action="">
  <p>
    <input type="button" value="显示属性及其值"
      onclick="listAttributes();">
    <input id="result" type="text" value="">
  </p>
 </form>
</body>
</html>
```

## `ParentNode.childElementCount`

**`ParentNode.childElementCount`** 只读属性返回一个无符号长整型数字，表示给定元素的子元素数。

!!! warn ""
    此属性最初是在`ElementTraversal`纯接口中定义的。 由于此接口包含两组不同的属性，一组针对具有子项的`Node`，一组针对具有子项的属性，因此它们已被移入两个单独的纯接口，
    即`ParentNode`和`ChildNode`。 在这种情况下，`childElementCount`移到了`ParentNode`。 这是一项相当技术性的更改，不应影响兼容性。

语法

```javascript
var count = node.childElementCount;
var elCount = elementNodeReference.childElementCount;
```

|  |  |
| :-- | :-- |
| `count` | 将返回值保留为无符号长（简单地为整数）类型。|
| `node` | 是表示`Document`，`DocumentFragment`或`Element`的对象。|

示例

```javascript
var foo = document.getElementById("foo");
if (foo.childElementCount > 0) {
    // do something
}
```

下例演示了一个元素节点的`childElementCount`属性以及`children`属性的用法.

```html
<head>
<script type="text/javascript">
  function GetChildCount () {
    var container = document.getElementById ("container");

    var childCount = 0;
    //如果支持childElementCount属性
    if ('childElementCount' in container) {
      childCount = container.childElementCount;
    }
    else {
      //如果支持children属性,IE6/7/8
      //译者注:没有判断nodeType是否为1,可能包含注释节点.
      if (container.children) {
        childCount = container.children.length;
      }
      else {  //,如果都不支持,Firefox 3.5之前版本
        var child = container.firstChild;
        while (child) {
          if (child.nodeType == 1 /*Node.ELEMENT_NODE*/) {
            childCount++;
          }
          child = child.nextSibling;
        }
      }
    }

    alert ("The number of child elements is " + childCount);
  }
</script>
</head>
<body>
  <div id="container" style="width:300px; background-color:#a0d0e0;">
    Some text inside the container.
    <input type="text" size="40" value="a child element of the container" />
    <div>
      <div>a descendant element of the container</div>
      <div>another descendant element of the container</div>
    </div>
  </div>
  <br /><br />
  <button onclick="GetChildCount ();">Get the number of container's child elements</button>
</body>
```

## `ParentNode.children`

**`ParentNode.children`** 是一个只读属性，返回 一个`Node`的子`elements` ，是一个动态更新的 `HTMLCollection`。

语法

```javascript
var children = node.children;
var elList = elementNodeReference.children;
```

`children` 属性为只读属性，对象类型为 `HTMLCollection`，你可以使用 `elementNodeReference.children[1].nodeName` 来获取某个子元素的标签名称。

示例

```javascript
// parg是一个指向<p>元素的对象引用
if (parg.childElementCount)
// 检查这个<p>元素是否有子元素
// 译者注:childElementCount有兼容性问题
 {
   var children = parg.children;
   for (var i = 0; i < children.length; i++)
   {
   // 通过children[i]来获取每个子元素
   // 注意:List是一个live的HTMLCollection对象,在这里添加或删除parg的子元素节点,都会立即改变List的值.
   };
 };
```

## `Element.classList`

**`Element.classList`** 是一个只读属性，返回一个元素的类属性的实时 `DOMTokenList` 集合。

相比将 `element.className` 作为以空格分隔的字符串来使用，classList 是一种更方便的访问元素的类列表的方法。

语法

```javascript
const elementClasses = elementNodeReference.classList;
```

`elementClasses` 是一个 `DOMTokenList` 表示  `elementNodeReference` 的类属性 。如果类属性未设置或为空，那么 `elementClasses.length`
返回 `0`。虽然 `element.classList` 本身是只读的，但是你可以使用 `add()` 和 `remove()` 方法修改它。

示例

```javascript
const div = document.createElement('div');
div.className = 'foo';

// 初始状态：<div class="foo"></div>
console.log(div.outerHTML);

// 使用 classList API 移除、添加类值
div.classList.remove("foo");
div.classList.add("anotherclass");

// 得到；<div class="anotherclass"></div>
console.log(div.outerHTML);

// 如果 visible 类值已存在，则移除它，否则添加它
div.classList.toggle("visible");

// add/remove visible, depending on test conditional, i less than 10
div.classList.toggle("visible", i < 10 );

console.log(div.classList.contains("foo"));

// 添加或移除多个类值
div.classList.add("foo", "bar", "baz");
div.classList.remove("foo", "bar", "baz");

// 使用展开语法添加或移除多个类值
const cls = ["foo", "bar"];
div.classList.add(...cls);
div.classList.remove(...cls);

// 将类值 "foo" 替换成 "bar"
div.classList.replace("foo", "bar");
```

## `Element.className`

**`className`** 获取或设置指定元素的class属性的值。

语法

```javascript
let cName = elementNodeReference.className;

elementNodeReference.className = cName;
```

- `cName`是一个字符串变量,表示当前元素的`class`属性的值,可以是由空格分隔的多个`class`属性值.

示例

```javascript
let elm = document.getElementById("div1");

if (elm.className == "fixed") {
  // 跳过class属性为特定值的元素
  goNextElement();
}
```

!!! warn ""
    使用名称`className`而不是`class`作为属性名,是因为"class" 在JavaScript中是个保留字.

## `Element.clientHeight`

这个属性是只读属性，对于没有定义`CSS`或者内联布局盒子的元素为`0`，否则，它是元素内部的高度(单位像素)，包含内边距，但不包括水平滚动条、边框和外边距。

`clientHeight` 可以通过 CSS `height` + CSS `padding` - 水平滚动条高度 (如果存在)来计算.

!!! warn "备注"
    此属性会将获取的值四舍五入取整数。如果你需要小数结果, 请使用 `element.getBoundingClientRect()`.

语法

```javascript
var h = element.clientHeight;
```

返回整数 `h`，表示 `element` 的 `clientHeight`（单位像素）。

`clientHeight` 是只读的.

示例

![Dimensions-client](/media/webfrontend__Dimensions-client.png)

## `Element.clientLeft`

表示一个元素的左边框的宽度，以像素表示。如果元素的文本方向是从右向左（RTL, right-to-left），并且由于内容溢出导致左边出现了一个垂直滚动条，则该属性包括滚动条的宽度。
`clientLeft` 不包括左外边距和左内边距。`clientLeft` 是只读的。

语法

```javascript
var left = element.clientLeft;
```

## `Element.clientTop`

一个元素顶部边框的宽度（以像素表示）。不包括顶部外边距或内边距。`clientTop` 是只读的。

语法

```javascript
var top = element.clientTop;
```

## `Element.clientWidth`

只读属性

内联元素以及没有 CSS 样式的元素的 **`clientWidth`** 属性值为 `0`。**`Element.clientWidth`** 属性表示元素的内部宽度，以像素计。该属性包括内边距，但不包括垂直滚动条（如果有）、边框和外边距。

该属性值会被四舍五入为一个整数。如果你需要一个小数值，可使用 `element.getBoundingClientRect()`。

语法

```javascript
var intElemClientWidth = element.clientWidth;
```

`intElemClientWidth` 是一个整数，表示元素的 `clientWidth`。

示例

![Dimensions-client](/media/webfrontend__Dimensions-client.png)

## `Element.firstElementChild`

**`ParentNode.firstElementChild`** 只读属性，返回对象的第一个子 元素, 如果没有子元素，则为`null`。

!!! warn ""
    他的属性最初是在`element`遍历纯接口中定义的。由于这个接口包含两组不同的属性，一个针对具有子元素的`Node`，一个针对子元素的属性，因此它们被移动到两个单独的纯接口中，`ParentNode`和`ChildNode`。在本例中，`firstElementChild`移动到ParentNode。这是一个相当技术性的更改，不应该影响兼容性。

语法

```javascript
var element = node.firstElementChild;
```

例子

```html
<ul id="foo">
  <li>First  (1)</li>
  <li>Second (2)</li>
  <li>Third  (3)</li>
</ul>

<script>
var foo = document.getElementById('foo');
// yields: First  (1)
console.log(foo.firstElementChild.textContent);
</script>
```

## `Element.id`

**`Element`** 接口的 `id` 属性表示元素的标识符，与全局属性 `id` 对应。

同一文档中，若 `id` 的值不是空字符串 `""`，便必须是独特的；也就是说，不同元素的 `ID` 必须是不同的。

这有助于让常用的 `getElementById` 方法通过 `id` 的值找到对应的单个元素。另外，在 CSS 中，`ID` 可作为选择器使用，详见：ID 选择器。

!!! warn "注意"
    虽然 ID 是区分大小写的, 但是不应该同时使用仅大小写有不同的 ID  值。

语法

```javascript
var idStr = element.id; // Get the id
element.id = idStr; // Set the id
```

- `idStr`，元素的 ID 属性值。

## `element.innerHTML`

**`Element.innerHTML`** 属性设置或获取HTML语法表示的元素的后代。

!!! warn "注意"
    如果一个 [`<div>`](/zh-hans/webfrontend/<div>), [`<span>`](/zh-hans/webfrontend/<span>), 或
    `<noembed>` 节点有一个文本子节点，该节点包含字符 `(&)`, `(<)`,  或`(>)`, `innerHTML`
    将这些字符分别返回为`&amp;`, `&lt;` 和 `&gt;` 。使用`Node.textContent`  可获取一个这些文本节点内容的正确副本。

如果要向一个元素中插入一段 HTML，而不是替换它的内容，那么请使用 `insertAdjacentHTML()` 方法。

语法

```javascript
const content = element.innerHTML;
element.innerHTML = htmlString;
```

值

`DOMString` 包含元素后代的HTML序列。设置元素的 `innerHTML` 将会删除所有该元素的后代并以上面给出的 `htmlString` 替代。

例外

|  |  |
| :-- | :-- |
| **`SyntaxError`** | 当 HTML 没有被正确标记时，设置 `innerHTML` 将会抛出语法错误。
| **`NoModificationAllowedError`** | 当父元素是 `Document` 时，设置 `innerHTML` 将会提示不允许修改。

使用说明

`innerHTML` 属性可以用来检查当前页面自最初加载到当前的 HTML 源码的变化。

获取元素的HTML

获取 `innerHTML` 会导致用户代理序列化 由元素后代组成的 HTML 或者 XML 。返回结果字符串。

```javascript
let contents = myElement.innerHTML;
```

查看元素内容节点的 HTML 标记。

!!! warn "注"
    返回的 HTML 或者 XML 片段是基于当前元素的内容生成的，所以返回的标记和格式可能与原始页面的标记不匹配。

替换元素的内容

设置 `innerHTML` 的值可以让你轻松地将当前元素的内容替换为新的内容。

举个例子来说，你可以通过文档 `body`  属性删除 `body` 的全部内容。

```javascript
document.body.innerHTML = "";
```

下面这个例子，首先获取文档当前的 HTML 标记并替换 `"<"` 字符为 HTML 实体 `"&lt;"`，从本质上来看，它是将 HTML 转换成原始文本，将其包裹在 `<pre>` 元素中。
然后 `innerHTML` 的值被替换成新的字符串。最后，文档的内容被替换为页面显示源码。

```javascript
document.documentElement.innerHTML = "<pre>" +
         document.documentElement.innerHTML.replace(/</g,"&lt;") +
            "</pre>";
```

其他：

当给 `innerHTML` 设置一个值的时候到底发生了什么？用户代理按照以下步骤：

1. 给定的值被解析为 HTML 或者 XML （取决于文档类型），结果就是 `DocumentFragment` 对象代表元素新设置的 DOM 节点。
2. 如果元素内容被替换成 `<template>`  元素，`<template>` 元素的 `content` 属性会被替换为步骤1中创建的新的 `DocumentFragment。`
3. 对于其他所有元素，元素的内容都被替换为新的 `DocumentFragment`节点。

安全问题

用 `innerHTML` 插入文本到网页中并不罕见。但这有可能成为网站攻击的媒介，从而产生潜在的安全风险问题。

```javascript
const name = "John";
// assuming 'el' is an HTML DOM element
el.innerHTML = name; // harmless in this case

// ...

name = "<script>alert('I am John in an annoying alert!')</script>";
el.innerHTML = name; // harmless in this case
```

尽管这看上去像 cross-site scripting 攻击，结果并不会导致什么。HTML 5 中指定不执行由 `innerHTML` 插入的 `<script>` 标签。

然而，有很多不依赖 `<script>` 标签去执行 JavaScript 的方式。所以当你使用`innerHTML` 去设置你无法控制的字符串时，这仍然是一个安全问题。例如：

```javascript
const name = "<img src='x' onerror='alert(1)'>";
el.innerHTML = name; // shows the alert
```

基于这个原因，当插入纯文本时，建议不要使用 `innerHTML` 。取而代之的是使用 `Node.textContent` ，它不会把给定的内容解析为 HTML，它仅仅是将原始文本插入给定的位置。

!!! error "警告"
    如果你的项目将要经过各种形式的安全检查的话，使用 `innerHTML` 可能导致代码被拒绝。例如，如果你在浏览器扩展中使用 `innerHTML` 并将扩展提交到
    addons.mozilla.org 的话，它将会在自动审核过程中被拒绝。

例子

这个例子使用 `innerHTML` 创建一种机制用于将消息记录到网页上的框中。

```javascript
function log(msg) {
  var logElem = document.querySelector(".log");

  var time = new Date();
  var timeStr = time.toLocaleTimeString();
  logElem.innerHTML += timeStr + ": " + msg + "<br/>";
}

log("Logging mouse events inside this container...");
```

`log()` 函数通过 `Date` 对象的 `toLocaleTimeString()` 方法获取当前时间，然后将消息文本和时间戳放一起构建一个字符串，最后将其追加到具有 “log” 类的框上。

现在添加第二个方法：记录基于事件 (比如 `mousedown`, `click`, 和 `mouseenter`) 的 `MouseEvent` 的信息。

```javascript
function logEvent(event) {
  var msg = "Event <strong>" + event.type + "</strong> at <em>" +
            event.clientX + ", " + event.clientY + "</em>";
  log(msg);
}
```

然后我们使用它作为包含我们消息的框上的鼠标事件的事件处理程序：

```javascript
var boxElem = document.querySelector(".box");

boxElem.addEventListener("mousedown", logEvent);
boxElem.addEventListener("mouseup", logEvent);
boxElem.addEventListener("click", logEvent);
boxElem.addEventListener("mouseenter", logEvent);
boxElem.addEventListener("mouseleave", logEvent);
```

HTML

这个例子的 HTML 代码就相当简洁了：

```html
<div class="box">
  <div><strong>Log:</strong></div>
  <div class="log"></div>
</div>
```

具有 “box” 类的 `<div>` 容器仅仅是出于布局考虑，用一个框来展示其内容。具有 “log” 类的 `<div>` 元素是作为消息本身的内容框。

```css
.box {
  width: 600px;
  height: 300px;
  border: 1px solid black;
  padding: 2px 4px;
  overflow-y: scroll;
  overflow-x: auto;
}

.log {
  margin-top: 8px;
  font-family: monospace;
}
```

## `Element.lastElementChild`

只读属性 **`ParentNode.lastElementChild`** 返回对象的最后一个子元素，如果没有子元素，则返回 `null`

!!! warn ""
    此属性最初是在`ElementTraversal`纯接口中定义的。由于此接口包含两组不同的属性，一组针对具有子项的`Node`，一组针对具有子项的属性，因此它们已被移入两个单独的纯接口，
    即`ParentNode和ChildNode`。在这种情况下，`lastElementChild`移到了`ParentNode`。 这是一项相当技术性的更改，不应影响兼容性。

语法

```javascript
var element = node.lastElementChild;
```

例子

```html
<ul id="foo">
  <li>First  (1)</li>
  <li>Second (2)</li>
  <li>Third  (3)</li>
</ul>

<script>
var foo = document.getElementById('foo');
// yields: Third  (3)
console.log(foo.lastElementChild.textContent);
</script>
```

## `Element.localName`

**`Element.localName`** 只读属性，返回本地名称的.

!!! warn ""
    在DOM4之前这个API定义在`Node`接口。

语法

```javascript
name = element.localName
```

`DOMString` 返回元素限定名的本地部分。

示例

(必须配合XML文档类型, 如 `text/xml` 或 `application/xhtml+xml`.)

```html
<html xmlns="http://www.w3.org/1999/xhtml"
      xmlns:svg="http://www.w3.org/2000/svg">
<head>
  <script type="application/javascript"><![CDATA[
  function test() {
    var text = document.getElementById('text');
    var circle = document.getElementById('circle');

    text.value = "<svg:circle> has:\n" +
                 "localName = '" + circle.localName + "'\n" +
                 "namespaceURI = '" + circle.namespaceURI + "'";
  }
  ]]></script>
</head>
<body onload="test()">
  <svg:svg version="1.1"
    width="100px" height="100px"
    viewBox="0 0 100 100">
    <svg:circle cx="50" cy="50" r="30" style="fill:#aaa" id="circle"/>
  </svg:svg>
  <textarea id="text" rows="4" cols="55"/>
</body>
</html>
```

节点的本地名称是节点限定名的一部分出现在冒号之后. 限定名通常当作特定XML文档命名空间的一部分.例如在限定名 ecomm:partners中 partners是本地名,ecomm是前缀。

```html
<ecomm:business id="soda_shop" type="brick_n_mortar" xmlns:ecomm="http://example.com/ecomm">
  <ecomm:partners>
    <ecomm:partner id="1001">Tony's Syrup Warehouse
    </ecomm:partner>
  </ecomm:partner>
</ecomm:business>
```

!!! warn "提示"
    在 Gecko 1.9.2 之前, 此属性返回HTML DOM的HTML元素本地名称的大写版本 (而不是XML DOM的HTML元素). 在最后一个版本,
    符合HTML5规范下, 当HTML DOM的HTML或XML DOMs的XHTML的小写元素时此属性返回内部DOM storage。`tagName` 属性仍然返回HTML DOM的HTML元素本地名称的大写版本.

## `Element.name`

**`name`** 获取或设置一个 DOM 对象的 `name` 属性；它只能应用于下列元素：`<a>`, `<applet>`, `<button>`, `<form>`, `<frame>`,
`<iframe>`, `<img>`, `<input>`, `<map>`, `<meta>`, `<object>`, `<param>`, `<select>`, and `<textarea>`.

需要注意的是，`name` 属性在其他类型元素上不存在。它不是 `Element` 或 `HTMLElement` 接口的一个属性。

`Name` 可被使用于 `document.getElementsByName()` 方法，`form` 以及表单元素集合。当使用于表单或表单元素时，可能返回一个单独的元素或一个元素集合。

语法

```javascript
HTMLElement.name = string;
var elName = HTMLElement.name;

var fControl = HTMLFormElement.elementName;
var controlCollection = HTMLFormElement.elements.elementName;
```

例子

```html
<form action="" name="formA">
  <input type="text" value="foo">
</form>

<script type="text/javascript">

  // 获取表单中第一个元素的引用
  var formElement = document.forms['formA'].elements[0];

  // 设置一个 name
  formElement.name = 'inputA';

  // 显示 input 的 value 值
  alert(document.forms['formA'].elements['inputA'].value);

</script>
```

!!! info "备注"
    在 IE6 中，使用 `document.createElement()` 方法创建的 DOM 对象的 `name` 属性不能被更改。

## `Element.namespaceURI`

**`Element.namespaceURI`** 是一个只读属性，它返回元素的命名空间，若该元素不在命名空间中则返回null .

!!! warn ""
    在DOM4之前， 这个 API 在接口 `Node` 中定义.

语法

```javascript
namespace = element.namespaceURI
```

例子

在这段代码中，我们检查了元素的`localName和namespaceURI`。如果 `namespaceURI` 返回 `XML` 命名空间，
`localName` 返回`"browser"`，于是这个节点被理解为是一个`XML` `<browser/>`。

```javascript
if (element.localName == "browser" &&
    element.namespaceURI == "http://www.mozilla.org/keymaster/gatekeeper/there.is.only.XML") {
  // this is a XML browser
}
```

!!! warn "注意"
    这不是一个计算值，它是基于范围内的名称空间声明检查的名称空间查找的结果。节点命名空间在节点创建时被冻结。
    在Firefox 3.5 以及之前的版本， HTML文档中的HTML元素的名称空间URI为 null。 在更早的版本中, 符合HTML5，
    它是[http://www.w3.org/1999/xhtml](http://www.w3.org/1999/xhtml) 如 XHTML。
    您可以使用DOM Level 2方法指定的`namespaceURI`创建一个元素 `document.createElementNS`。
    DOM本身不处理或执行名称空间验证。 它由DOM应用程序完成，以执行任何必要的验证。注意，名称空间前缀一旦与某个特定元素相关联，就不能更改。

## `element.nextElementSibling`

`nextElementSibling` 返回当前元素在其父元素的子元素节点中的后一个元素节点,如果该元素已经是最后一个元素节点,则返回`null`,该属性是只读的.

语法

```javascript
var nextNode = elementNodeReference.nextElementSibling;
```

例子

```html
<div id="div-01">Here is div-01</div>
<div id="div-02">Here is div-02</div>

<script type="text/javascript">
  var el = document.getElementById('div-01').nextElementSibling;
  document.write('<p>Siblings of div-01</p><ol>');
  while (el) {
    document.write('<li>' + el.nodeName + '</li>');
    el = el.nextElementSibling;
  }
  document.write('</ol>');
</script>
```

上面的例子会输出以下内容:

```html
Siblings of div-01

   1. DIV
   2. SCRIPT
   3. P
   4. OL
```

## `element.outerHTML`

`element`  DOM接口的`outerHTML`属性获取描述元素（包括其后代）的序列化HTML片段。它也可以设置为用从给定字符串解析的节点替换元素。

要仅获取元素内容的HTML表示形式或替换元素的内容，请使用 `innerHTML` 属性

语法

```javascript
let content = element.outerHTML;
```

返回时，内容包含描述元素及其后代的序列化HTML片段。

```javascript
element.outerHTML = content;
```

将元素替换为通过使用元素的父作为片段解析算法的上下文节点解析字符串内容生成的节点。

例子

获取一个元素的`outerHTML`属性的值：

```javascript
// HTML:
/*
<div id="d">
    <p>Content</p>
    <p>Further Elaborated</p>
</div>
*/

const d = document.getElementById("d");
console.log(d.outerHTML);

/*
    字符串 '<div id="d"><p>Content</p><p>Further Elaborated</p></div>'
    被显示到控制台窗口
*/
```

通过设置`outerHTML`属性来替换节点：

```javascript
// HTML:
/*
<div id="container">
    <div id="d">This is a div.</div>
</div>
*/

let container = document.getElementById("container");
let d = document.getElementById("d");

console.log(container.firstChild.nodeName);
// logs "div"

d.outerHTML = "<p>This paragraph replaced the original div.</p>";

console.log(container.firstChild.nodeName);
// logs "P"

/*
    #d div不再是文档树的一部分，新段替换了它。
    (不在页面中显示,但仍然在内存中)
*/
```

注意事项

如果元素没有父元素，即如果它是文档的根元素，则设置其`outerHTML`属性将抛出一个带有错误代码 `NO_MODIFICATION_ALLOWED_ERR` 的 `DOMException` 。例如：

```javascript
document.documentElement.outerHTML = "test";  
// 抛出一个 DOMException
```

此外，虽然元素将在文档中被替换，设置了outerHTML属性的变量仍将保持对原始元素的引用：

```javascript
let p = document.getElementsByTagName("p")[0];
console.log(p.nodeName);
// 显示: "P"
p.outerHTML = "<div>This div replaced a paragraph.</div>";

console.log(p.nodeName);
// 仍然为: "P";
```

## `Element.part`

元素接口的 **`part`** 属性代表元素的部分标识符（即使用`part`属性设置），以`DOMTokenList`的形式返回。 这些可以通过`::part`伪元素用于设置阴影DOM的样式。

语法

```javascript
let elementPartList = element.part
```

示例

以下摘录来自我们的阴影部分示例。这里的`part`属性用于查找阴影部分，而`part`属性则用于更改每个选项卡的部件标识符，以便在单击选项卡时将正确的样式应用于活动选项卡。

```javascript
let tabs = [];
let children = this.shadowRoot.children;

for(let elem of children) {
  if(elem.getAttribute('part')) {
    tabs.push(elem);
  }
}

tabs.forEach((tab) => {
  tab.addEventListener('click', (e) => {
    tabs.forEach((tab) => {
      tab.part = 'tab';
    })
    e.target.part = 'tab active';
  })

  console.log(tab.part);
})
```

## `Element.prefix`

`Element.prefix` 只读属性返回指定元素的命名空间前缀，如果未指定前缀，则返回`null`。

!!! warn
    在DOM4之前，该API是在 Node  interface 中定义的。

语法

```javascript
string = element.prefix
```

示例

以下将"`x`"记录到控制台。

```html
<x:div onclick="console.log(this.prefix)"/>
```

仅当使用支持名称空间的解析器时，即使用XML MIME类型提供文档时，这才起作用。 这不适用于HTML文档。

## `Element.previousElementSibling`

**`previousElementSibling`** 返回当前元素在其父元素的子元素节点中的前一个元素节点,如果该元素已经是第一个元素节点,则返回`null`,该属性是只读的.

语法

```javascript
var prevNode = elementNodeReference.previousElementSibling;
```

例子

```html
<div id="div-01">Here is div-01</div>
<div id="div-02">Here is div-02</div>
<li>This is a list item</li>
<li>This is another list item</li>
<div id="div-03">Here is div-03</div>

<script type="text/javascript">
  var el = document.getElementById('div-03').previousElementSibling;
  document.write('<p>Siblings of div-03</p><ol>');
  while (el) {
    document.write('<li>' + el.nodeName + '</li>');
    el = el.previousElementSibling;
  }
  document.write('</ol>');
</script>
```

上面的例子会输出以下内容:

```html
Siblings of div-03

   1. LI
   2. LI
   3. DIV
   4. DIV
```

## `Element.scrollHeight`

**`Element.scrollHeight`** 这个只读属性是一个元素内容高度的度量，包括由于溢出导致的视图中不可见内容。

`scrollHeight` 的值等于该元素在不使用滚动条的情况下为了适应视口中所用内容所需的最小高度。 没有垂直滚动条的情况下，`scrollHeight`值与元素视图填充所有内容所需要的最小值
`clientHeight`相同。包括元素的`padding`，但不包括元素的`border`和`margin`。`scrollHeight`也包括 `::before` 和 `::after`这样的伪元素。

!!! warn ""
    属性将会对值四舍五入取整。如果需要小数值，使用`Element.getBoundingClientRect()`.

语法

```javascript
var intElemScrollHeight = document.getElementById(id_attribute_value).scrollHeight;
```

`intElemScrollHeight` 存储着与元素`scrollHeight`像素值对应的一个整数。`scrollHeight`是一个只读属性。

示例

![scrollHeight](/media/webfrontend__scrollHeight.png)

问题与解决方案

判定元素是否滚动到底

如果元素滚动到底，下面等式返回true，没有则返回`false`.

```javascript
element.scrollHeight - element.scrollTop === element.clientHeight
```

当容器不滚动但有溢出的子容器时，这些检查可以确定容器能否滚动：

```javascript
window.getComputedStyle(element).overflowY === 'visible' window.getComputedStyle(element).overflowY !== 'hidden'
```

`scrollHeight` 演示

监听 `onscroll` 事件，这个等式可以用来判定用户是否阅读过文本。（参考 `element.scrollTop` 和 `element.clientHeight`属性）。例如：

```html
<form name="registration">
  <p>
    <textarea id="rules">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum at laoreet magna.
Aliquam erat volutpat. Praesent molestie, dolor ut eleifend aliquam, mi ligula ultrices sapien, quis cursus
neque dui nec risus. Duis tincidunt lobortis purus eu aliquet. Quisque in dignissim magna. Aenean ac lorem at
velit ultrices consequat. Nulla luctus nisi ut libero cursus ultrices. Pellentesque nec dignissim enim. Phasellus
ut quam lacus, sed ultricies diam. Vestibulum convallis rutrum dolor, sit amet egestas velit scelerisque id.
Proin non dignissim nisl. Sed mi odio, ullamcorper eget mattis id, malesuada vitae libero. Integer dolor lorem,
mattis sed dapibus a, faucibus id metus. Duis iaculis dictum pulvinar. In nisi nibh, dapibus ac blandit at, porta
at arcu. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Praesent
dictum ipsum aliquet erat eleifend sit amet sollicitudin felis tempus. Aliquam congue cursus venenatis. Maecenas
luctus pellentesque placerat. Mauris nisl odio, condimentum sed fringilla a, consectetur id ligula. Praesent sem
sem, aliquet non faucibus vitae, iaculis nec elit. Nullam volutpat, lectus et blandit bibendum, nulla lorem congue
turpis, ac pretium tortor sem ut nibh. Donec vel mi in ligula hendrerit sagittis. Donec faucibus viverra fermentum.
Fusce in arcu arcu. Nullam at dignissim massa. Cras nibh est, pretium sit amet faucibus eget, sollicitudin in
ligula. Vivamus vitae urna mauris, eget euismod nunc. Aenean semper gravida enim non feugiat. In hac habitasse
platea dictumst. Cras eleifend nisl volutpat ante condimentum convallis. Donec varius dolor malesuada erat
consequat congue. Donec eu lacus ut sapien venenatis tincidunt. Quisque sit amet tellus et enim bibendum varius et
a orci. Donec aliquet volutpat scelerisque. Proin et tortor dolor. Ut aliquet, dolor a mattis sodales, odio diam
pulvinar sem, egestas pretium magna eros vitae felis. Nam vitae magna lectus, et ornare elit. Morbi feugiat, ipsum
ac mattis congue, quam neque mollis tortor, nec mollis nisl dolor a tortor. Maecenas varius est sit amet elit
interdum quis placerat metus posuere. Duis malesuada justo a diam vestibulum vel aliquam nisi ornare. Integer
laoreet nisi a odio ornare non congue turpis eleifend. Cum sociis natoque penatibus et magnis dis parturient montes,
nascetur ridiculus mus. Cras vulputate libero sed arcu iaculis nec lobortis orci fermentum.
    </textarea>
  </p>
  <p>
    <input type="checkbox" name="accept" id="agree" />
    <label for="agree">I agree</label>
    <input type="submit" id="nextstep" value="Next" />
  </p>
</form>
```

```css
#notice {
  display: inline-block;
  margin-bottom: 12px;
  border-radius: 5px;
  width: 600px;
  padding: 5px;
  border: 2px #7FDF55 solid;
}

#rules {
  width: 600px;
  height: 130px;
  padding: 5px;
  border: #2A9F00 solid 2px;
  border-radius: 5px;
}
```

```javascript
function checkReading () {
  if (checkReading.read) {
    return;
  }
  checkReading.read = this.scrollHeight - this.scrollTop === this.clientHeight;
  document.registration.accept.disabled = document.getElementById("nextstep").disabled = !checkReading.read;
  checkReading.noticeBox.innerHTML = checkReading.read ? "Thank you." : "Please, scroll and read the following text.";
}

onload = function () {
  var oToBeRead = document.getElementById("rules");
  checkReading.noticeBox = document.createElement("span");
  document.registration.accept.checked = false;
  checkReading.noticeBox.id = "notice";
  oToBeRead.parentNode.insertBefore(checkReading.noticeBox, oToBeRead);
  oToBeRead.parentNode.insertBefore(document.createElement("br"), oToBeRead);
  oToBeRead.onscroll = checkReading;
  checkReading.call(oToBeRead);
}
```

## `Element.scrollLeft`

**`Element.scrollLeft`** 属性可以读取或设置元素滚动条到元素左边的距离。

注意如果这个元素的内容排列方向（`direction`） 是`rtl` (right-to-left) ，那么滚动条会位于最右侧（内容开始处），并且`scrollLeft`值为`0`。此时，当你从右到左拖动滚动条时，`scrollLeft`会从`0`变为负数（这个特性在chrome浏览器中不存在）。

语法

```javascript
//获取滚动条到元素左边的距离
var sLeft = element.scrollLeft;
```

`sLeft` 是一个整数，代表元素滚动条距离元素左边多少像素。

```javascript
//设置滚动条滚动了多少像素
element.scrollLeft = 10;
```

`scrollLeft` 可以是任意整数，然而：

- 如果元素不能滚动（比如：元素没有溢出），那么 `scrollLeft` 的值是`0`。
- 如果给`scrollLeft` 设置的值小于`0`，那么 `scrollLeft` 的值将变为0。
- 如果给`scrollLeft` 设置的值大于元素内容最大宽度，那么 `scrollLeft` 的值将被设为元素最大宽度。

例子

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <style>
        #container {
            border: 1px solid #ccc; height: 100px; overflow: scroll; width: 100px;
        }
        #content {
            background-color: #ccc; width: 250px;
        }
    </style>
    <script>
        document.addEventListener('DOMContentLoaded', function () {
            var button = document.getElementById('slide');
            button.onclick = function () {
                document.getElementById('container').scrollLeft += 20;
            };
        }, false);
    </script>
</head>
<body>
    <div id="container">
        <div id="content">Lorem ipsum dolor sit amet.</div>
    </div>
    <button id="slide" type="button">Slide</button>
</body>
</html>
```

## `Element.scrollTop`

**`Element.scrollTop`** 属性可以获取或设置一个元素的内容垂直滚动的像素数。

一个元素的 `scrollTop` 值是这个元素的顶部到视口可见内容（的顶部）的距离的度量。当一个元素的内容没有产生垂直方向的滚动条，那么它的 `scrollTop` 值为`0`。

语法

```javascript
// 获得滚动的像素数
var  intElemScrollTop = someElement.scrollTop;
```

运行此代码后，`intElemScrollTop` 是一个整数，即`element`的内容向上滚动的像素数。

```javascript
// 设置滚动的距离
element.scrollTop = intValue;
```

`scrollTop` 可以被设置为任何整数值，同时注意：

- 如果一个元素不能被滚动（例如，它没有溢出，或者这个元素有一个"non-scrollable"属性）， `scrollTop`将被设置为`0`。
- 设置`scrollTop`的值小于`0`，`scrollTop` 被设为`0`
- 如果设置了超出这个容器可滚动的值, `scrollTop` 会被设为最大值.

例子

![scrollTop](/media/webfrontend__scrollTop.png)

## `Element.scrollWidth`

**`Element.scrollWidth`** 这个只读属性是元素内容宽度的一种度量，包括由于`overflow`溢出而在屏幕上不可见的内容。
`scrollWidth`值等于元素在不使用水平滚动条的情况下适合视口中的所有内容所需的最小宽度。 宽度的测量方式与`clientWidth`相同：它包含元素的内边距，但不包括边框，外边距或垂直滚动条
（如果存在）。 它还可以包括伪元素的宽度，例如`::before`或`::after`。 如果元素的内容可以适合而不需要水平滚动条，则其`scrollWidth`等于`clientWidth`

!!! warn ""
    1. 这个属性会进行四舍五入并返回整数，如果你需要小数形式的值，使用`element.getBoundingClientRect()`.
    2. 在实际测试过程中，谷歌获取的 `Element.scrollWidth` 和 IE，火狐下获取的 `Element.scrollWidth` 并不相同

语法

```javascript
var xScrollWidth = element.scrollWidth;
```

`xScrollWidth` 的值是元素的内容宽度。

例子

```html
<!DOCTYPE html>
<html>
<head>
  <title>Example</title>
  <style>
    div {
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
    }

    #aDiv {
      width: 100px;
    }

    button {
      margin-bottom: 2em;
    }
  </style>
</head>

<body>
  <div id="aDiv">
    FooBar-FooBar-FooBar-FooBar
  </div>
  <button id="aButton">
    Check for overflow
  </button>
  
  <div id="anotherDiv">
    FooBar-FooBar-FooBar-FooBar
  </div>
  <button id="anotherButton">
    Check for overflow
  </button>
</body>
<script>
  var buttonOne = document.getElementById('aButton'),
  buttonTwo = document.getElementById('anotherButton'),
  divOne = document.getElementById('aDiv'),
  divTwo = document.getElementById('anotherDiv');

  //check to determine if an overflow is happening
  function isOverflowing(element) {
      return (element.scrollWidth > element.offsetWidth);
  }

  function alertOverflow(element) {
      if (isOverflowing(element)) {
          alert('Contents are overflowing the container.');
      } else {
          alert('No overflows!');
      }
  }

  buttonOne.addEventListener('click', function() {
      alertOverflow(divOne);
  });

  buttonTwo.addEventListener('click', function() {
      alertOverflow(divTwo);
  });
</script>
</html>
```

## `Element.shadowRoot`

**`Element.shadowRoot`** 是只读属性，表示元素挂载的shadow root。可以使用 `Element.attachShadow()`) 给一个已存在的元素添加shadow root。

语法

```javascript
var shadowroot = element.shadowRoot;
```

值

可以是一个`ShadowRoot`实例对象，但如果一个shadow root的 mode被设置为 `closed`那么它的值将会是 `null`。

示例

在`<custom-square>`标签的class定义中我们在生命周期的回调函数里调用了一些外部方法——`updateStyle()`，正是这个函数使得我们添加的正方形元素可以改变大小和颜色。你可以看到我们将this（即我们创建的正方形元素本身）作为一个参数传入了这个方法。

```javascript
connectedCallback() {
  console.log('Custom square element added to page.');
  updateStyle(this);
}

attributeChangedCallback(name, oldValue, newValue) {
  console.log('Custom square element attributes changed.');
  updateStyle(this);
}
```

在`updateStyle()`函数中我们通过`Element.shadowRoot`获取到了Shadow DOM引用。在这里我们利用了标准的DOM遍历技巧来获取在Shadow DOM中`<style>`元素并更新了其中的CSS样式：

```javascript
function updateStyle(elem) {
  const shadow = elem.shadowRoot;
  const childNodes = Array.from(shadow.childNodes);

  childNodes.forEach(childNode => {
    if (childNode.nodeName === 'STYLE') {
      childNode.textContent = `
        div {
          width: ${elem.getAttribute('l')}px;
          height: ${elem.getAttribute('l')}px;
          background-color: ${elem.getAttribute('c')};
        }
      `;
    }
  });
}
```

## `Element.slot`

`Element`接口的 **`slot`** 属性会返回已插入元素所在的Shadow DOM `slot`的名称。

Slot是存在于web component内部的占位符，用户可以通过slot属性在web component的内部插入自定义的标记文本。

语法

```javascript
var aString = element.slot
element.slot = aString
```

示例

我们创建了一个简单的自定义元素叫做 `<my-paragraph>`，并为它添加了shadow root，然后使用一个包含以 `my-text`为名称的`slot`的`template`来填充它。

当 `<my-paragraph>` 在文档中被使用时，`slot`标签中的内容会被填充到拥有`slot="my-text"`属性的元素之中，我们称这种元素为slotable element。（事实上可以看作是拥有`slot`属性的元素被填充到了`template`中有`<slot>`标签存在的地方）请看下面的示例：

```html
<my-paragraph>
  <span slot="my-text">Let's have some different text!</span>
</my-paragraph>
```

在JavaScript代码中我们获取到上面代码中的`span`的引用，然后将对应的 `<slot>` 元素的引用的名称打印在控制台中。

```javascirpt
let slottedSpan = document.querySelector('my-paragraph span')
console.log(slottedSpan.slot); // logs 'my-text'
```

## `Element.tagName`

返回当前元素的标签名

语法

```html
elementName = element.tagName
elementName 是一个字符串,包含了element元素的标签名.
```

在XML (或者其他基于XML的语言,比如XHTML,XML)文档中,`tagName`的值会保留原始的大小写. 在HTML文档中, `tagName`会返回其大写形式. 对于元素节点来说,`tagName`属性的值和`nodeName`属性的值是相同的.

例子

假设给定下面的源码

```html
<span id="born">When I was born...</span>
```

然后运行下面的脚本

```javascript
var span = document.getElementById("born");
alert(span.tagName);
```

在XHTML中 (或者其他的XML格式文件中), 会弹出小写的"span".而在HTML中, 会弹出大写的"SPAN".
