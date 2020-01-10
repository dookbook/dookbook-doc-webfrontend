TOPICS: document
        document.body
        document.characterSet
        document.compatMode
        document.contentType
        document.currentScript
        document.defaultView
        document.designMode
        document.dir
        document.doctype
        document.documentElement
        document.documentURI
        Document.domain
        document.embeds
        Document.forms
        document.mozFullScreenEnabled
        Document.head
        Document.hidden
        document.images
        document.implementation
        document.lastModified
        Document.links
        Document.location
        Document.plugins
        document.readyState
        document.referrer
        Document.scripts
        Document.scrollingElement
        Document.title
        document.URL
        Document.visibilityState
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript document 对象: `document`

`Document` 接口表示任何在浏览器中载入的网页，并作为网页内容的入口，也就是DOM 树。DOM 树包含了像 [`<body>`](/zh-hans/webfrontend/<body>) 、
[`<table>`](/zh-hans/webfrontend/<table>) 这样的元素，以及大量其他元素。它向网页文档本身提供了全局操作功能，能解决如何获取页面的 URL ，如何在文档中创建一个新的元素这样的问题。

`Document` 接口描述了任何类型的文档的通用属性与方法。根据不同的文档类型（例如HTML、XML、SVG，...），还能使用更多 API：使用 `"text/html"` 作为内容类型
（content type）的 HTML 文档，还实现了 `HTMLDocument` 接口，而 XML 和 SVG 文档则（额外）实现了 `XMLDocument` 接口。

## `document.body`

返回当前文档中的`<body>`元素或者`<frameset>`元素.

语法

```javascript
var objRef = document.body;
document.body = objRef;
```

示例

```javascript
// 如果HTML结构为<body id="oldBodyElement"></body>,则:
alert(document.body.id); // "oldBodyElement"

var aNewBodyElement = document.createElement("body");

aNewBodyElement.id = "newBodyElement";
document.body = aNewBodyElement;
alert(document.body.id); // "newBodyElement"
```

`document.body`是包含当前页面内容的元素,对于拥有[`<body>`](/zh-hans/webfrontend/<body>)元素的文档来说,返回的是[`<body>`](/zh-hans/webfrontend/<body>)元素,对于一个拥有`<frameset>`元素的文档来说,返回的是最外层的`<frameset>`元素.

该属性是可写的,且为该属性赋的值必须是一个[`<body>`](/zh-hans/webfrontend/<body>)元素.

## `document.characterSet`

**`Document.characterSet`** 只读属性返回当前文档的字符编码。该字符编码是用于渲染此文档的字符集，可能与该页面指定的编码不同。（用户可以重写编码方式。）

!!! warn ""
    `document.charset` 和 `document.inputEncoding` 属性是 `document.characterSet` 的遗留别名。不要再使用它们。

语法

```javascript
var string = document.characterSet
```

示例

```javascript
<button onclick="alert(document.characterSet);">查看字符集</button>
//返回当前文档的字符集,比如"ISO-8859-1" 或者 "UTF-8"
```

## `document.compatMode`

表明当前文档的渲染模式是混杂模式还是"标准模式".

语法

```javascript
mode = document.compatMode
```

- 如果文档处于“混杂模式”，则该属性值为`"BackCompat"`
- 如果文档处于“标准模式”或者“准标准模式(almost standards mode)”，则该属性为`"CSS1Compat"`

示例

```javascript
if (document.compatMode == "BackCompat") {
  // 渲染模式为混杂模式
}
```

还有另外一种渲染模式, Gecko的"准标准模式", 该模式和标准规范模式的区别仅为表格单元内的图片布局方式不同. 且该模式的类型字符串仍为: "CSS1Compat".

## `document.contentType`

返回当前文档的Content-Type(MIME)类型.

语法

```javascript
contentType = document.contentType;
```

该属性为只读.

该属性的返回值是浏览器检测到的,不一定是直接读取HTTP响应头中的或者`HTML`中`meta`标签指定的值.

## `document.currentScript`

返回其所包含的脚本中正在被执行的 [`<script>`](/zh-hans/webfrontend/<script>) 元素.

语法

```javascript
var curScriptElement = document.currentScript;
```

示例

下例演示了如何检测当前正在执行脚本的 [`<script>`](/zh-hans/webfrontend/<script>) 元素是否是以异步模式执行的.

```javascript
if (document.currentScript.async) {
  console.log("Executing asynchronously");
} else {
  console.log("Executing synchronously");
}
```

值得注意的是,如果当前正在执行的代码是处在某个回调函数或者事件处理函数中的,那么 `currentScript` 属性不会指向包含那个函数的
[`<script>`](/zh-hans/webfrontend/<script>) 元素,而是会返回 `null`.

## `document.defaultView`

在浏览器中，该属性返回当前 `document` 对象所关联的 `window` 对象，如果没有，会返回 `null`。

语法

```javascript
var win = document.defaultView;
```

该属性只读.

## `document.designMode`

**`document.designMode`** 控制整个文档是否可编辑。有效值为 `"on"` 和 `"off"` 。根据规范，该属性默认为 `"off"` 。Firefox 遵循此标准。
早期版本的 Chrome 和 IE默认为 `"inherit"` 。从 Chrome 43 开始，默认值为 `"off"` ，并且不再支持  `"inherit"`。在 IE6 到 IE10 中，该值为大写。

语法

```javascript
var mode = document.designMode;
document.designMode = "on" || "off";
```

示例

使一个 `<iframe>` 的文档可编辑：

```javascript
iframeNode.contentDocument.designMode = "on";
```

## `document.dir`

**`Document.dir`** 的本质是`DOMString`，代表了文档的文字朝向，是从左到右(默认)还是从右到左。

`'rtl'(right to left)`代表从右到左，`'ltr'(left to right)`代表从左到右。

语法

```javascript
console.log(document.dir);// "" (译者添加)
document.dir = "ltr"//(默认);
document.dir = "rtl";
dirStr = document.dir;
document.dir = dirStr;
```

## `document.doctype`

返回当前文档关联的文档类型定义(DTD). 返回的对象实现了 `DocumentType` 接口。使用 `DOMImplementation.createDocumentType()` 方法可以创建一个`DocumentType`类型的对象。

语法

```javascript
doctype = document.doctype;
```

- `doctype` 是一个只读属性.

示例

```javascript
var doctypeObj = document.doctype;

console.log(
  "doctypeObj.name: "           + doctypeObj.name            + "\n" +
  "doctypeObj.internalSubset: " + doctypeObj.internalSubset  + "\n" +
  "doctypeObj.publicId: "       + doctypeObj.publicId        + "\n" +
  "doctypeObj.systemId: "       + doctypeObj.systemId
);
```

## `document.documentElement`

**`Document.documentElement`** 是一个会返回文档对象（`document`）的根元素的只读属性（如HTML文档的 `<html>` 元素）。

语法

```javascript
var element = document.documentElement;
```

示例

```javascript
const rootElement = document.documentElement;
const firstTier = rootElement.childNodes;

// firstTier 是由根元素的所有子节点组成的一个 NodeList
for (let i = 0; i < firstTier.length; i++) {
   // 使用根节点的每个子节点
   // 如 firstTier[i]
}
```

对于任何非空 HTML 文档，调用 `document.documentElement` 总是会返回一个 `<html>` 元素，且它一定是该文档的根元素。借助这个只读属性，能方便地获取到任意文档的根元素。

HTML 文档通常包含一个子节点 `<html>`，但在它前面可能还有个 DOCTYPE 声明。XML 文档通常包含多个子节点：根元素，`DOCTYPE` 声明，和 processing instructions。

所以，应当使用 `document.documentElement` 来获取根元素, 而不是 `document.firstChild`。

## `document.documentURI`

`Document` 接口的属性 `documentURI` 以字符串的形式返回文档的位置（location）。

在最初的DOM3定义中，这个属性是可读/写的。在现代的DOM标准（DOM4）中，它是只读的。

语法

```javascript
var string = document.documentURI;
```

HTML 文档有一个 `document.URL` 属性返回同样的值。但是不像 URL，`documentURI` 适用于所有类型的文档。

## `Document.domain`

获取/设置当前文档的原始域部分, 用于 同源策略.

语法

```javascript
var domainString = document.domain;
document.domain = string;
```

示例

```javascript
// 对于文档 www.example.xxx/good.html,
// 以下脚本会关闭窗口
var badDomain = "www.example.xxx";

if (document.domain == badDomain)
   window.close(); // 这只是一个样例 - window.close()有时候会失效
// 对于URI http://developer.mozilla.org/en/docs/DOM
// 以下设置会把变量domain设定为string "developer.mozilla.org"
var domain = document.domain;
```

如果当前文档的域无法识别，那么`domain`属性会返回`null`。

在根域范围内，Mozilla允许你把`domain`属性的值设置为它的上一级域。例如，在 `developer.mozilla.org` 域内，可以把`domain`设置为 `"mozilla.org"`
但不能设置为 `"mozilla.com"` 或者`"org"`。

Mozilla 会区分 `document.domain` 属性 **从没有被设定过值** 和 **被显示的设定为跟该文档的URL的domain一致的值**，尽管这两种状况下，该属性会返回同样的值。
两个文档，只有在 `document.domain` 都被设定为同一个值，表明他们打算协作；或者都没有设定 `document.domain` 属性并且URL的域是一致的 (如何判断一致)，
这两种条件下，一个文档才可以去访问另一个文档。如果不是因为这个特殊的策略，每一个站点都会成为他的子域的XSS攻击的对象（例如，`https://bugzilla.mozilla.org` 可以被来自
`https://bug*.bugzilla.mozilla.org` 站点的bug附件攻击）。

## `document.embeds`

`Document` 接口的只读属性 `embeds` 返回当前文档内的 [`<embed>`](/zh-hans/webfrontend/<embed>) **HTML**
[`<object>`](/zh-hans/webfrontend/<object>) 元素列表

语法

```javascript
nodeList = document.embeds
```

一个 `HTMLCollection` 类型的值

## `Document.forms`

`forms` 返回当前文档中的 [`<form>`](/zh-hans/webfrontend/<form>) 元素的一个集合(一个 HTMLCollection)。

语法

```javascript
let collection = document.forms;
```

例子: 获取表单信息

```javascript
<html>

<head>
<title> document.forms example</title>
</head>

<body>
<form id="robby">
 <input type="button" onclick="alert(document.forms[0].id);"
 value="robby's form" />
</form>

<form id="dave">
 <input type="button" onclick="alert(document.forms[1].id);"
 value="dave's form" />
</form>

<form id="paul">
 <input type="button" onclick="alert(document.forms[2].id);"
 value="paul's form" />
</form>

</body>
</html>
```

例子: 获取表单内的元素

```javascript
var selectForm = document.forms[index];
var selectFormElement = document.forms[index].elements[index];
```

## `document.mozFullScreenEnabled`

返回一个布尔值,表明浏览器是否支持全屏模式. 全屏模式只在那些不包含窗口化的插件的页面中可用.对于一个[`<iframe>`](/zh-hans/webfrontend/<iframe>)元素中的页面,则它必需拥有mozallowfullscreen属性.

语法

```javascript
var isFullScreenAvailable = document.mozFullScreenEnabled;
```

如果当前文档可以进入全屏模式,则`isFullScreenAvailable``为true`

例子

```javascript
function requestFullScreen() {
  if (document.mozFullScreenEnabled) {
    videoElement.requestFullScreen();
  } else {
    console.log('你的浏览器不支持全屏模式!');
  }
}
```

## `Document.head`

返回当前文档中的 [`<head>`](/zh-hans/webfrontend/<head>) 元素。如果有多个 [`<head>`](/zh-hans/webfrontend/<head>) 元素，则返回第一个。

语法

```javascript
var objRef = document.head;
示例节
// HTML部分源码为: <head id="my-document-head">
var aHead = document.head;

alert(aHead.id); // "my-document-head";

alert( document.head === document.querySelector("head") ); // true
```

`document.head` 是个只读属性，为该属性赋值只会静默失败，如果在严格模式中，则会抛出`TypeError`异常。

## `Document.hidden`

`Document.hidden` （只读属性）返回布尔值，表示页面是（`true`）否（`false`）隐藏。

语法

```javascript
var string = document.hidden
```

例子

```javascript
document.addEventListener("visibilitychange", function() {
  console.log( document.hidden );
  // Modify behavior...
});
```

## `document.images`

`Document` 接口的只读属性`images`返回当前文档中所有 `image` 元素的集合.

语法

```javascript
var imageCollection = document.images;
```

一个 `HTMLCollection`，提供了包含在该文档中的所有`images`元素实时的列表。 集合中的每条代表了一个单`image`元素的`HTMLImageElement`

你可以在返回的结果中使用JavaScript 数组符号('`[]`'，译注)，或者`item()` 方法去获取集合中的每个元素。下面方法是等价的：

```javascript
firstImage = imageCollection.item(0);

firstImage = imageCollection[0];
```

例子

该例是一次通过遍历图片列表找到名称为`"banner.gif"`的图片。

```javascript
var ilist = document.images;
for(var i = 0; i < ilist.length; i++) {
  if(ilist[i].src == "banner.gif") {
    // 发现了banner图片
  }
}
```

## `document.implementation`

返回一个和当前文档相关联的`DOMImplementation`对象。

语法

```javascript
DOMImpObj = document.implementation;
```

示例

```javascript
var modName = "HTML";
var modVer = "2.0";
var conformTest = document.implementation.hasFeature( modName, modVer );

alert( "DOM " + modName + " " + modVer + " supported?: " + conformTest );

// alerts with: "DOM HTML 2.0 supported?: true" if DOM Level 2 HTML module is supported.
```

W3C的DOM1级建议值规定了一种检测浏览器对某个DOM模型是否支持的方法——`hasFeature`方法。如果它可用的话，那么`DOMImplementation`接口的其他方法就可以为操作文档以外的内容提供一些服务了。例如，`DOMImplementation`接口包含一个`createDocumentType`方法，它可以为实例管理的文档创建对应的DTD文档定义。

## `document.lastModified`

返回一个字符串,其中包含了当前文档的最后修改日期和时间.

语法

```javascript
var string = document.lastModified;
```

示例

```javascript
dump(document.lastModified);
// 返回: Tuesday, July 10, 2001 10:19:42
```

需要注意的是,作为一个字符串,`lastModified` 不能很容易的被用于与该文档的修改日期做比较.

## `Document.links`

`links` 属性返回一个文档中所有具有 href 属性值的 [`<area>`](/zh-hans/webfrontend/<area>) 元素与
[`<a>`](/zh-hans/webfrontend/<a>) 元素的集合。

语法

```javascript
nodeList = document.links
```

返回值

一个 `HTMLCollection`。

示例

```javascript
var links = document.links;
for(var i = 0; i < links.length; i++) {
  var linkHref = document.createTextNode(links[i].href);
  var lineBreak = document.createElement("br");
  document.body.appendChild(linkHref);
  document.body.appendChild(lineBreak);
}
```

## `Document.location`

`Document.location` 是一个只读属性，返回一个 `Location` 对象，包含有文档的 URL 相关的信息，并提供了改变该 URL 和加载其他 URL 的方法。

尽管 `Document.location` 是一个只读的 `Location` 对象，你也能够赋给它一个 `DOMString`。这意味着你能够赋给 `document.location` 字符串，
大多数情况下像这样使用：`document.location = 'http://www.example.com'`，也可写为`document.location.href = 'http://www.example.com'`。

只是想获取字符串形式的 URL，可以使用只读属性 `document.URL`。

如果当前文档不在浏览上下文中，则返回值为`null`。

语法

```javascript
locationObj = document.location
document.location = 'http://www.mozilla.org' // Equivalent to document.location.href = 'http://www.mozilla.org'
```

示例

```javascript
dump(document.location);
// Prints a string like
// "http://www.example.com/juicybits.html" to the console
```

## `Document.plugins`

`Document`接口的插件只读属性返回一个`HTMLCollection` 对象，该对象包含一个或多个`HTMLEmbedElements`表示当前文档中的`<embed>` 元素。

!!! warn ""
    对于已安装的插件列表，请使用 `NavigatorPlugins.plugins` 插件。

语法

```html
embedArrayObj = document.plugins
```

值

一个 `HTMLCollection`, 如果文档中没有嵌入则为`null`。

## `document.readyState`

一个 `document` 的 **`Document.readyState`** 属性描述了文档的加载状态。

当该属性值发生变化时，会在 `document` 对象上触发`readystatechange`事件。

值

一个文档的 `readyState` 可以是以下之一：

|  |  |
| :-- | :-- |
| **`loading`/正在加载** | `document` 仍在加载。
| **`interactive`/可交互** | 文档已被解析，"正在加载"状态结束，但是诸如图像，样式表和框架之类的子资源仍在加载。
| **`complete`/完成** | 文档和所有子资源已完成加载。表示 `load` 状态的事件即将被触发。

当这个属性的值变化时，`document` 对象上的`readystatechange` 事件将被触发。

语法

```javascript
let string = document.readyState;
// "complete"
```

例子

不同的准备状态

```javascript
switch (document.readyState) {
  case "loading":
    // 表示文档还在加载中，即处于“正在加载”状态。
    break;
  case "interactive":
    // 文档已经结束了“正在加载”状态，DOM元素可以被访问。
    // 但是像图像，样式表和框架等资源依然还在加载。
    var span = document.createElement("span");
    span.textContent = "A <span> element.";
    document.body.appendChild(span);
    break;
  case "complete":
    // 页面所有内容都已被完全加载.
    let CSS_rule = document.styleSheets[0].cssRules[0].cssText;
    console.log(`The first CSS rule is: ${CSS_rule }`);
    break;
}
```

```javascript
// 模拟 DOMContentLoaded/ jquery ready
document.onreadystatechange = function () {
  if (document.readyState === "interactive") {
    initApplication();
  }
}
```

```javascript
// 模拟 load 事件
document.onreadystatechange = function () {
  if (document.readyState === "complete") {
    initApplication();
  }
}
```

## `document.referrer`

**`Document.referrer`** 返回 跳转或打开到当前页面 的页面的 URI。

语法

```javascript
var referrer = document.referrer;
```

属性值

如果用户直接打开了这个页面（不是通过页面跳转，而是通过地址栏或者书签等打开的），则该属性为空字符串。由于该属性只是返回一个字符串，所以不能够通过该属性引用页面的 DOM。

在`<iframe>`内，`Document.referrer`最初将设置为与父窗口的`Window.location`的`href`相同的值。

## `Document.scripts`

返回一个`HTMLCollection`对象,包含了当前文档中所有`<script>`元素的集合.

语法

```javascript
var scriptList = document.scripts;
```

`scriptList`是一个`HTMLCollection`对象.你可以像使用数组一样通过索引来获取其中包含的`<script>`元素.

例子

下例演示了如何查看当前页面是否包含有`<script>`元素.

```javascript
var scripts = document.scripts;

if (scripts.length) {
  alert("该页面存在script标签!");
}
```

## `Document.scrollingElement`

`scrollingElement` （ `Document` 的只读属性）返回滚动文档的 `Element` 对象的引用。 在标准模式下, 这是文档的根元素, `document.documentElement`.

当在怪异模式下， `scrollingElement` 属性返回 HTML body 元素（若不存在返回 `null` ）。

语法

```javascript
var element = document.scrollingElement;
```

示例

```javascript
var scrollElm = document.scrollingElement;
scrollElm.scrollTop = 0;
```

## `Document.title`

获取或设置文档的标题。

语法

```javascript
var docTitle = document.title;
```

`title` 是一个包含 `document` 标题的字符串。如果通过设置 `document.title` 将标题覆盖，则返回覆盖后的值。否则返回标签里指定的标题

```javascript
document.title = newTitle;
```

`newTitle` 是文档的新标题。赋值操作影响 `document.title` 的返回值，文档的显示标题（即窗口或标签页顶部的标题栏），另外还会影响文档的 DOM，即改变 HTML 文档中
`<title>` 元素的内容。

示例

```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
</head>
<body>

<script>
alert(document.title); // 显示 "Hello World!"
document.title = "Goodbye World!";
alert(document.title); // 显示 "Goodbye World!"
</script>

</body>
</html>
```

备注

在 Gecko 中，该属性适应于 HTML、SVG、XML 和其他文档。

对于 HTML 文档来说，`document.title` 的初始值是 `<title>` 元素的文本内容。对于 XML 来说，它是 `window` 或其他顶级 XML 元素的 `title` 属性的值。

在 XML 里，在文档完全加载之前访问 `document.title`，会有未定义行为（`document.title` 可能返回一个空字符串，并且设置 `document.title` 也无效）。

## `document.URL`

返回当前文档的URL地址

语法

```javascript
string = document.URL
```

备注

该属性的值和DOM Level 0中的`document.location.href` 属性的值是相等的.然而 `document.location.href` 是可写的,
`document.URL` 是只读的.

`document.documentURI` 也返回与该属性相同的值,不过它在非HTML文档中也可以使用.

## `Document.visibilityState`

**`Document.visibilityState`** （只读属性）, 返回`document`的可见性, 即当前可见元素的上下文环境. 由此可以知道当前文档(即为页面)是在背后, 或是不可见的隐藏的标签页，或者(正在)预渲染.可用的值如下：

- `'visible'` : 此时页面内容至少是部分可见. 即此页面在前景标签页中，并且窗口没有最小化.
- `'hidden'` : 此时页面对用户不可见. 即文档处于背景标签页或者窗口处于最小化状态，或者操作系统正处于 '锁屏状态' .
- `'prerender'` : 页面此时正在渲染中, 因此是不可见的（出于`document.hidden`的目的被认为是隐藏的）. 文档只能从此状态开始，永远不能从其他值变为此状态.注意: 浏览器支持是可选的.
- `'unloaded'` : 页面从内存中卸载清除. 注意: 浏览器支持是可选的.
当此属性的值改变时, 会递交 `visibilitychange` 事件给`Document`.

典型用法是防止当页面正在渲染时加载资源, 或者当页面在背景中或窗口最小化时禁止某些活动.

语法

```javascript
var string = document.visibilityState
```

示例

```javascript
document.addEventListener("visibilitychange", function() {
  console.log( document.visibilityState );
  // Modify behavior...
});
```
