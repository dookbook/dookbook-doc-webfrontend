TOPICS: Element
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript Element Object: `element`

## 属性

### `Element.accessKey`

The **`Element.accessKey`** property sets the keystroke which a user can press to jump to a given element.

!!! warn ""
    The `Element.accessKey` property is seldom used because of its multiple conflicts with already
    present key bindings in browsers. To work around this, browsers implement accesskey behavior if
    the keys are pressed with other "qualifying" keys (such as !!!Alt!!! + accesskey).

### `Element.attributes`

The **`Element.attributes`** property returns a live collection of all attribute nodes registered
to the specified node. It is a `NamedNodeMap`, not an `Array`, so it has no `Array` methods and the
`Attr` nodes' indexes may differ among browsers. To be more specific, `attributes` is a key/value
pair of strings that represents any information regarding that attribute.

Syntax

```javascript
var attr = element.attributes;
```

Example

```javascript
// Get the first <p> element in the document
var para = document.getElementsByTagName("p")[0];
var atts = para.attributes;
```

Enumerating elements attributes

Numerical indexing is useful for going through all of an element's attributes.
The following example runs through the attribute nodes for the element in the document with id
"paragraph", and prints each attribute's value.

```html
<!DOCTYPE html>

<html>

 <head>
  <title>Attributes example</title>
  <script type="text/javascript">
   function listAttributes() {
     var paragraph = document.getElementById("paragraph");
     var result = document.getElementById("result");

     // First, let's verify that the paragraph has some attributes
     if (paragraph.hasAttributes()) {
       var attrs = paragraph.attributes;
       var output = "";
       for(var i = attrs.length - 1; i >= 0; i--) {
         output += attrs[i].name + "->" + attrs[i].value;
       }
       result.value = output;
     } else {
       result.value = "No attributes to show";
     }
   }
  </script>
 </head>

<body>
 <p id="paragraph" style="color: green;">Sample Paragraph</p>
 <form action="">
  <p>
    <input type="button" value="Show first attribute name and value"
      onclick="listAttributes();">
    <input id="result" type="text" value="">
  </p>
 </form>
</body>
</html>
```

### `ParentNode.childElementCount`

The **`ParentNode.childElementCount`** read-only property returns an unsigned long representing the
number of child elements of the given element.

!!! warn ""
    This property was initially defined in the `ElementTraversal` pure interface. As this interface
    contained two distinct set of properties, one aimed at `Node` that have children, one at those
    that are children, they have been moved into two separate pure interfaces, `ParentNode` and
    `ChildNode`. In this case, `childElementCount` moved to `ParentNode`. This is a fairly
    technical change that shouldn't affect compatibility.

Syntax

```javascript
var count = node.childElementCount;
```

|  |  |
| :-- | :-- |
| **`count`** | The return value, which is an unsigned long (simply an integer) type.
| **`node`** | An object representing a Document, DocumentFragment, or Element.

Example

```javascript
var foo = document.getElementById('foo');
if (foo.childElementCount > 0) {
  // Do something
}
```

### `ParentNode.children`

The `ParentNode` property **`children`** is a read-only property that returns a live `HTMLCollection`
which contains all of the child `elements` of the node upon which it was called.

Syntax

```javascript
var children = node.children;
```

Value

An `HTMLCollection` which is a live, ordered collection of the DOM elements which are children of
`node`. You can access the individual child nodes in the collection by using either the `item()`
method on the collection, or by using JavaScript array-style notation.

If the node has no element `children`, then `children` is an empty list with a `length` of `0`.

Example

```javascript
const foo = document.getElementById('foo');
for (let i = 0; i < foo.children.length; i++) {
  console.log(foo.children[i].tagName);
}
```

Polyfill

```javascript
// Overwrites native 'children' prototype.
// Adds Document & DocumentFragment support for IE9 & Safari.
// Returns array instead of HTMLCollection.
;(function(constructor) {
  if (constructor &&
    constructor.prototype &&
    constructor.prototype.children == null) {
    Object.defineProperty(constructor.prototype, 'children', {
      get: function() {
        var i = 0, node, nodes = this.childNodes, children = [];
        while (node = nodes[i++]) {
          if (node.nodeType === 1) {
            children.push(node);
          }
        }
        return children;
      }
    });
  }
})(window.Node || window.Element);
```

### `Element.classList`

The **`Element.classList`** is a read-only property that returns a live `DOMTokenList` collection
of the `class` attributes of the element. This can then be used to manipulate the class list.

Using `classList` is a convenient alternative to accessing an element's list of classes as a
space-delimited string via `element.className`.

Syntax

```javascript
const elementClasses = elementNodeReference.classList;
```

Returns

A `DOMTokenList` representing the contents of the element's `class` attribute. If the `class`
attribute is not set or empty, it returns `0`.

The `DOMTokenList` itself is read-only, although you can modify it using the `add()` and `remove()` methods.

Examples

```javascript
const div = document.createElement('div');
div.className = 'foo';

// our starting state: <div class="foo"></div>
console.log(div.outerHTML);

// use the classList API to remove and add classes
div.classList.remove("foo");
div.classList.add("anotherclass");

// <div class="anotherclass"></div>
console.log(div.outerHTML);

// if visible is set remove it, otherwise add it
div.classList.toggle("visible");

// add/remove visible, depending on test conditional, i less than 10
div.classList.toggle("visible", i < 10 );

console.log(div.classList.contains("foo"));

// add or remove multiple classes
div.classList.add("foo", "bar", "baz");
div.classList.remove("foo", "bar", "baz");

// add or remove multiple classes using spread syntax
const cls = ["foo", "bar"];
div.classList.add(...cls);
div.classList.remove(...cls);

// replace class "foo" with class "bar"
div.classList.replace("foo", "bar");
```

### `Element.className`

The **`className`** property of the `Element` interface gets and sets the value of the `class`
attribute of the specified element.

Syntax

```javascript
var cName = elementNodeReference.className;
elementNodeReference.className = cName;
```

- `cName` is a string variable representing the class or space-separated classes of the current element.

Example

```javascript
let el = document.getElementById('item');

if (el.className === 'active'){
  el.className = 'inactive';
} else {
  el.className = 'active';
}
```

Notes

The name `className` is used for this property instead of `class` because of conflicts with the
"class" keyword in many languages which are used to manipulate the DOM.

`className` can also be an instance of `SVGAnimatedString` if the `element` is an `SVGElement`.
It is better to get/set the `className` of an element using `Element.getAttribute` and `Element.setAttribute`
if you are dealing with SVG elements. However, take into account that `Element.getAttribute` returns
`null` instead of `""` if the `element` has an empty `class` attribute.

```javascript
elm.setAttribute('class', elm.getAttribute('class'))
```

!!! warn ""
    The `class` is an **HTML Attribute**, while the `className` is a **DOM Property**.

### `Element.clientHeight`

The **`Element.clientHeight`** read-only property is zero for elements with no CSS or inline layout
boxes; otherwise, it's the inner height of an element in pixels. It includes padding but excludes
borders, margins, and horizontal scrollbars (if present).

`clientHeight` can be calculated as: CSS height + CSS padding - height of horizontal scrollbar (if present).

!!! warn "Note"
    This property will round the value to an integer. If you need a fractional value, use `element.getBoundingClientRect()`.

Syntax

```javascript
var intElemClientHeight = element.clientHeight;
```

`intElemClientHeight` is an integer corresponding to the `clientHeight` of `element` in pixels.
The `clientHeight` property is read–only.

Example

![Dimensions-client](/media/webfrontend__Dimensions-client.png)

### `Element.clientLeft`

The width of the left border of an element in pixels. It includes the width of the vertical
scrollbar if the text direction of the element is right–to–left and if there is an overflow
causing a left vertical scrollbar to be rendered. `clientLeft` does not include the left margin or
the left padding. `clientLeft` is read-only.

Gecko-based applications support `clientLeft` starting with Gecko 1.9 (Firefox 3, implemented in
bug 111207). This property is not supported in Firefox 2 and earlier.

When `layout.scrollbar.side` preference is set to 1 or to 3 and when the text-direction is set to RTL,
then **the vertical scrollbar is positioned on the left** and this impacts the way clientLeft is computed.

!!! warn "Note"
    This property will round the value to an integer. If you need a fractional value, use `element.getBoundingClientRect()`.

Syntax

```javascript
var left = element.clientLeft;
```

### `Element.clientTop`

The width of the top border of an element in pixels. It is a read-only, integer property of element.

As it happens, all that lies between the two locations (`offsetTop` and client area top) is the
element's border. This is because the `offsetTop` indicates the location of the top of the border
(not the margin) while the client area starts immediately below the border, (client area includes
padding.) Therefore, the **`clientTop`** value will always equal the integer portion of the `.getComputedStyle()`
value for "border-top-width". (Actually might be `Math.round(parseFloat())`.) For example, if the
computed "border-top-width" is zero, then clientTop is also zero.

!!! warn "Note"
    This property will round the value to an integer. If you need a fractional value, use `element.getBoundingClientRect()`.

Gecko-based applications support `clientTop` starting with Gecko 1.9 (Firefox 3, implemented in
bug 111207). This property is not supported in Firefox 2 and earlier.

Syntax

```javascript
var top = element.clientTop;
```

### `Element.clientWidth`

The **`Element.clientWidth`** property is zero for inline elements and elements with no CSS;
otherwise, it's the inner width of an element in pixels. It includes padding but excludes borders,
margins, and vertical scrollbars (if present).

!!! warn "Note"
    This property will round the value to an integer. If you need a fractional value, use `element.getBoundingClientRect()`.

Syntax

```javascript
var intElemClientWidth = element.clientWidth;
```

`intElemClientWidth` is an integer corresponding to the `clientWidth` of `element` in pixels. The
`clientWidth` property is read–only.

Example

![Dimensions-client](/media/webfrontend__Dimensions-client.png)

### `Element.firstElementChild`

The **`ParentNode.firstElementChild`** read-only property returns the object's first child `Element`,
or `null` if there are no child elements.

!!! warn ""
    This property was initially defined in the `ElementTraversal` pure interface. As this
    interface contained two distinct set of properties, one aimed at `Node` that have children,
    one at those that are children, they have been moved into two separate pure interfaces,
    `ParentNode` and `ChildNode`. In this case, `firstElementChild` moved to `ParentNode`.
    This is a fairly technical change that shouldn't affect compatibility.

Syntax

```javascript
var element = node.firstElementChild;
```

Example

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

### `Element.id`

The **`id`** property of the `Element` interface represents the element's identifier, reflecting the
`id` global attribute.

If the `id` value is not the empty string, it must be unique in a document.

The `id` is often used with `getElementById()` to retrieve a particular element. Another
common case is to use an element's ID as a selector when styling the document with CSS.

!!! warn "Note"
    Identifiers are case-sensitive, but you should avoid creating IDs that differ only in the capitalization.

Syntax

```javascript
var idStr = element.id; // Get the id
element.id = idStr; // Set the id
```

- `idStr` is the identifier of the element.

### `element.innerHTML`

The `Element` property **`innerHTML`** gets or sets the HTML or XML markup contained within the element.

!!! warn "Note"
    If a [`<div>`](/en/webfrontend/<div>), [`<span>`](/en/webfrontend/<span>), or `<noembed>` node
    has a child text node that includes the characters `(&)`, `(<)`, or `(>)`, `innerHTML` returns
    these characters as the HTML entities `"&amp;"`, `"&lt;"` and `"&gt;"` respectively. Use
    `Node.textContent` to get a raw copy of these text nodes' contents.

To insert the HTML into the document rather than replace the contents of an element, use the method i`nsertAdjacentHTML()`.

Syntax

```javascript
const content = element.innerHTML;

element.innerHTML = htmlString;
```

Value

A `DOMString` containing the HTML serialization of the element's descendants. Setting the value of
`innerHTML` removes all of the element's descendants and replaces them with nodes constructed by
parsing the HTML given in the string htmlString.

Exceptions

|  |  |
| :-- | :-- |
| **`SyntaxError`** | An attempt was made to set the value of `innerHTML` using a string which is not properly-formed HTML.
| **`NoModificationAllowedError`** | An attempt was made to insert the HTML into a node whose parent is a `Document`.

Usage notes

The `innerHTML` property can be used to examine the current HTML source of the page, including any
changes that have been made since the page was initially loaded.

Reading the HTML contents of an element

Reading `innerHTML` causes the user agent to serialize the HTML or XML fragment comprised of the
elment's descendants. The resulting string is returned.

```javascript
let contents = myElement.innerHTML;
```

This lets you look at the HTML markup of the element's content nodes.

!!! warn "Note"
    The returned HTML or XML fragment is generated based on the current contents of the element,
    so the markup and formatting of the returned fragment is likely not to match the original page markup.

Replacing the contents of an element

Setting the value of `innerHTML` lets you easily replace the existing contents of an element
with new content.

For example, you can erase the entire contents of a document by clearing the contents of the
document's `body` attribute:

```javascript
document.body.innerHTML = "";
```

This example fetches the document's current HTML markup and replaces the `"<"` characters with the
HTML entity `"&lt;"`, thereby essentially converting the HTML into raw text. This is then wrapped in
a `<pre>` element. Then the value of `innerHTML` is changed to this new string. As a result, the
document contents are replaced with a display of the page's entire source code.

```javascript
document.documentElement.innerHTML = "<pre>" +
         document.documentElement.innerHTML.replace(/</g,"&lt;") +
            "</pre>";
```

Operational details

What exactly happens when you set value of `innerHTML`? Doing so causes the user agent to
follow these steps:

1. The specified value is parsed as HTML or XML (based on the document type), resulting in a
`DocumentFragment` object representing the new set of DOM nodes for the new elements.
1. If the element whose contents are being replaced is a `<template>` element, then the
`<template>` element's `content` attribute is replaced with the new
`DocumentFragment` created in step `1`.
1. For all other elements, the element's contents are replaced with the nodes in the new `DocumentFragment`.

Security considerations

It is not uncommon to see `innerHTML` used to insert text into a web page. There is potential for
this to become an attack vector on a site, creating a potential security risk.

```javascript
const name = "John";
// assuming 'el' is an HTML DOM element
el.innerHTML = name; // harmless in this case

// ...

name = "<script>alert('I am John in an annoying alert!')</script>";
el.innerHTML = name; // harmless in this case
```

Although this may look like a cross-site scripting attack, the result is harmless. HTML5 specifies
that a `<script>` tag inserted with `innerHTML` should not execute.

However, there are ways to execute JavaScript without using `<script>` elements, so there is
still a security risk whenever you use `innerHTML` to set strings over which you have no control.
For example:

```javascript
const name = "<img src='x' onerror='alert(1)'>";
el.innerHTML = name; // shows the alert
```

For that reason, it is recommended that you do not use `innerHTML` when inserting plain text;
instead, use `Node.textContent`. This doesn't parse the passed content as HTML, but instead
inserts it as raw text.

!!! error "Warning"
    If your project is one that will undergo any form of security review, using `innerHTML` most
    likely will result in your code being rejected. For example, if you use `innerHTML` in a browser
    extension and submit the extension to addons.mozilla.org, it will not pass the automated review process.

Example

This example uses `innerHTML` to create a mechanism for logging messages into a box on a web page.

```javascript
function log(msg) {
  var logElem = document.querySelector(".log");

  var time = new Date();
  var timeStr = time.toLocaleTimeString();
  logElem.innerHTML += timeStr + ": " + msg + "<br/>";
}

log("Logging mouse events inside this container...");
```

The `log()` function creates the log output by getting the current time from a `Date` object using
`toLocaleTimeString()`, and building a string with the timestamp and the message text. Then the
message is appended to the box with the class `"log"`.

We add a second method that logs information about `MouseEvent` based events (such as
`mousedown`, `click`, and `mouseenter`):

```javascript
function logEvent(event) {
  var msg = "Event <strong>" + event.type + "</strong> at <em>" +
            event.clientX + ", " + event.clientY + "</em>";
  log(msg);
}
```

Then we use this as the event handler for a number of mouse events on the box that contains our log:

```javascript
var boxElem = document.querySelector(".box");

boxElem.addEventListener("mousedown", logEvent);
boxElem.addEventListener("mouseup", logEvent);
boxElem.addEventListener("click", logEvent);
boxElem.addEventListener("mouseenter", logEvent);
boxElem.addEventListener("mouseleave", logEvent);
```

The HTML is quite simple for our example.

```html
<div class="box">
  <div><strong>Log:</strong></div>
  <div class="log"></div>
</div>
```

The `<div>` with the class `"box"` is just a container for layout purposes, presenting the contents
with a box around it. The `<div>` whose class is `"log"` is the container for the log text itself.

The following CSS styles our example content.

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

### `Element.lastElementChild`

The **`ParentNode.lastElementChild`** read-only property returns the object's last child `Element`
or `null` if there are no child elements.

!!! warn ""
    This property was initially defined in the `ElementTraversal` pure interface. As this
    interface contained two distinct set of properties, one aimed at `Node` that have children,
    one at those that are children, they have been moved into two separate pure interfaces,
    `ParentNode` and `ChildNode`. In this case, `lastElementChild` moved to `ParentNode`. This is
    a fairly technical change that shouldn't affect compatibility.

Syntax

```javascript
var element = node.lastElementChild;
```

Example

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

### `Element.localName`

The **`Element.localName`** read-only property returns the local part of the qualified name of an element.

!!! warn ""
    In previous DOM specifications this API was defined within the `Node` interface.

Syntax

```javascript
name = element.localName
```

Return value

A `DOMString` representing the local part of the element's qualified name.

Example

(Must be served with XML content type, such as `text/xml` or `application/xhtml+xml`.)

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

Notes

The local name of a node is that part of the node's qualified name that comes after the colon.
Qualified names are typically used in XML as part of the namespace(s) of the particular XML
documents. For example, in the qualified name `ecomm:partners`, `partners` is the local name and
`ecomm` is the prefix:

```html
<ecomm:business id="soda_shop" type="brick_n_mortar" xmlns:ecomm="http://example.com/ecomm">
  <ecomm:partners>
    <ecomm:partner id="1001">Tony's Syrup Warehouse
    </ecomm:partner>
  </ecomm:partner>
</ecomm:business>
```

!!! warn "Note"
    In Gecko 1.9.2 and earlier, the property returns the upper-cased version of the local name for
    HTML elements in HTML DOMs (as opposed to XHTML elements in XML DOMs). In later versions, in
    compliance with HTML5, the property returns in the case of the internal DOM storage, which
    is lower case for both HTML elements in HTML DOMs and XHTML elements in XML DOMs. The `tagName`
    property continues to return in the upper case for HTML elements in HTML DOMs.

### `Element.name`

**`name`** gets or sets the `name` property of an element in the DOM. It only applies to the
following elements: `<a>`, `<applet>`, `<button>`, `<form>`, `<frame>`, `<iframe>`, `<img>`,
`<input>`, `<map>`, `<meta>`, `<object>`, `<param>`, `<select>`, and `<textarea>`.

!!! warn "Note"
    The `name` property doesn't exist for other elements; unlike `tagName` and `nodeName`, it is not
    a property of the `Node`, `Element` or `HTMLElement` interfaces.

`name` can be used in the `document.getElementsByName()` method, a form and with the form elements
collection. When used with a form or elements collection, it may return a single element or a collection.

Syntax

```javascript
HTMLElement.name = string
let elName = HTMLElement.name

let fControl = HTMLFormElement.elementName
let controlCollection = HTMLFormElement.elements.elementName
```

Example

```html
<form action="" name="formA">
  <input type="text" value="foo">
</form>

<script type="text/javascript">

  // Get a reference to the first element in the form
  let formElement = document.forms['formA'].elements[0]

  // Give it a name
  formElement.name = 'inputA'

  // Show the value of the input
  alert(document.forms['formA'].elements['inputA'].value)

</script>
```

Notes

In Internet Explorer (IE), the `name` property of DOM objects created using `document.createElement()`
can't be set or modified.

### `Element.namespaceURI`

The **`Element.namespaceURI`** read-only property returns the namespace URI of the element, or
`null` if the element is not in a namespace.

!!! warn ""
    Before DOM4 this API was defined within the `Node` interface.

Syntax

```javascript
namespace = element.namespaceURI
```

Example

In this snippet, an element is being examined for its `localName` and its `namespaceURI`. If the
`namespaceURI` returns the XUL namespace and the `localName` returns "browser", then the node is
understood to be a XUL `<browser/>`.

```javascript
if (element.localName == "browser" &&
    element.namespaceURI == "http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul") {
  // this is a XUL browser
}
```

Notes

This is not a computed value that is the result of a namespace lookup based on an examination of
the namespace declarations in scope. The namespace URI of a node is frozen at the node creation time.

In Firefox 3.5 and earlier, the namespace URI for HTML elements in HTML documents is `null`. In later
versions, in compliance with HTML5, it is [http://www.w3.org/1999/xhtml](http://www.w3.org/1999/xhtml)
as in XHTML.

You can create an element with the specified `namespaceURI` using the DOM Level 2 method `document.createElementNS`.

The DOM does not handle or enforce namespace validation per se. It is up to the DOM application to
do any validation necessary. Also note that the namespace prefix, once it is associated with a
particular element, cannot be changed.

### `element.nextElementSibling`

The **`NonDocumentTypeChildNode.nextElementSibling`** read-only property returns the element
immediately following the specified one in its parent's children list, or `null` if the specified
element is the last one in the list.

Syntax

```javascript
var nextNode = elementNodeReference.nextElementSibling;
```

Example

```html
<div id="div-01">Here is div-01</div>
<div id="div-02">Here is div-02</div>

<script type="text/javascript">
  var el = document.getElementById('div-01').nextElementSibling;
  console.log('Siblings of div-01:');
  while (el) {
    console.log(el.nodeName);
    el = el.nextElementSibling;
  }
</script>
```

This example outputs the following into the console when it loads:

```html
Siblings of div-01:
DIV
SCRIPT
```

### `element.outerHTML`

The **`outerHTML`** attribute of the `Element` DOM interface gets the serialized HTML fragment
describing the element including its descendants. It can also be set to replace the element with
nodes parsed from the given string.

To only obtain the HTML representation of the contents of an element, or to replace the contents of
an element, use the `innerHTML` property instead.

Syntax

```javascript
var content = element.outerHTML;

element.outerHTML = htmlString;
```

Value

Reading the value of `outerHTML` returns a `DOMString` containing an HTML serialization of the
`element` and its descendants. Setting the value of `outerHTML` replaces the `element` and all of
its descendants with a new DOM tree constructed by parsing the specified `htmlString`.

Exceptions

|  |  |
| :-- | :-- |
| **`SyntaxError`** | An attempt was made to set `outerHTML` using an HTML string which is not valid.
| **`NoModificationAllowedError`** | An attempt was made to set `outerHTML` on an element which is a direct child of a `Document`, such as `Document.documentElement`.

Examples

Getting the value of an element's `outerHTML` property:

```javascript
// HTML:
// <div id="d"><p>Content</p><p>Further Elaborated</p></div>

d = document.getElementById("d");
console.log(d.outerHTML);

// the string '<div id="d"><p>Content</p><p>Further Elaborated</p></div>'
// is written to the console window
```

Replacing a node by setting the `outerHTML` property:

```javascript
// HTML:
// <div id="container"><div id="d">This is a div.</div></div>

container = document.getElementById("container");
d = document.getElementById("d");
console.log(container.firstChild.nodeName); // logs "DIV"

d.outerHTML = "<p>This paragraph replaced the original div.</p>";
console.log(container.firstChild.nodeName); // logs "P"

// The #d div is no longer part of the document tree,
// the new paragraph replaced it.
```

Notes

If the element has no parent element, setting its `outerHTML` property will not change it or its
descendants. Many browsers will also throw an exception. For example:

```javascript
var div = document.createElement("div");
div.outerHTML = "<div class=\"test\">test</div>";
console.log(div.outerHTML); // output: "<div></div>"
```

Also, while the element will be replaced in the document, the variable whose `outerHTML` property
was set will still hold a reference to the original element:

```javascript
var p = document.getElementsByTagName("p")[0];
console.log(p.nodeName); // shows: "P"
p.outerHTML = "<div>This div replaced a paragraph.</div>";
console.log(p.nodeName); // still "P";
```

### `Element.part`

The **`part`** property of the `Element` interface represents the part identifier(s) of the element
(i.e. set using the `part` attribute), returned as a `DOMTokenList`. These can be used to style
parts of a shadow DOM, via the `::part` pseudo-element.

Syntax

```javascript
let elementPartList = element.part
```

Examples

The following excerpt is from our shadow-part example. Here the `part` attribute is used to find the
shadow parts, and the `part` property is then used to change the part identifiers of each tab so the
correct styling is applied to the active tab when tabs are clicked.  

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

### `Element.prefix`

The **`Element.prefix`** read-only property returns the namespace prefix of the specified element,
or `null` if no prefix is specified.

!!! warn ""
    Before DOM4 this API was defined within the `Node` interface.

Syntax

```javascript
string = element.prefix
```

Examples

The following logs "`x`" to the console.

```html
<x:div onclick="console.log(this.prefix)"/>
```

Notes

This will only work when a namespace-aware parser is used, i.e. when a document is served with an
XML MIME type. This will not work for HTML documents.

### `Element.previousElementSibling`

The **`NonDocumentTypeChildNode.previousElementSibling`** read-only property returns the `Element`
immediately prior to the specified one in its parent's children list, or `null` if the specified
element is the first one in the list.

Syntax

```javascript
prevNode = elementNodeReference.previousElementSibling;
```

Example

```html
<div id="div-01">Here is div-01</div>
<div id="div-02">Here is div-02</div>
<li>This is a list item</li>
<li>This is another list item</li>
<div id="div-03">Here is div-03</div>

<script>
  let el = document.getElementById('div-03').previousElementSibling;
  document.write('<p>Siblings of div-03</p><ol>');
  while (el) {
    document.write('<li>' + el.nodeName + '</li>');
    el = el.previousElementSibling;
  }
  document.write('</ol>');
</script>
```

This example outputs the following into the page when it loads:

```html
Siblings of div-03

   1. LI
   2. LI
   3. DIV
   4. DIV
```

### `Element.scrollHeight`

The **`Element.scrollHeight`** read-only property is a measurement of the height of an element's
content, including content not visible on the screen due to overflow.

The scrollHeight value is equal to the minimum height the element would require in order to fit all
the content in the viewport without using a vertical scrollbar. The height is measured in the same
way as `clientHeight`: it includes the element's padding, but not its border, margin or horizontal
scrollbar (if present). It can also include the height of pseudo-elements such as `::before` or
`::after`. If the element's content can fit without a need for vertical scrollbar, its
`scrollHeight` is equal to `clientHeight`

!!! warn ""
    This property will round the value to an integer. If you need a fractional value, use `Element.getBoundingClientRect()`.

Syntax

```javascript
var intElemScrollHeight = element.scrollHeight;
```

*intElemScrollHeight* is a variable storing an integer corresponding to the scrollHeight pixel
value of the element. The scrollHeight property is read-only.

Example

![scrollHeight](/media/webfrontend__scrollHeight.png)

Problems and solutions

Determine if an element has been totally scrolled

The following equivalence returns `true` if an element is at the end of its scroll, `false` if it isn't.

```javascript
element.scrollHeight - element.scrollTop === element.clientHeight
```

When the container does not scroll, but has overflowing children, these checks determine if the
container can scroll:

```javascript
window.getComputedStyle(element).overflowY === 'visible'
window.getComputedStyle(element).overflowY !== 'hidden'
```

scrollHeight Demo

Associated with the `onscroll` event, this equivalence can be useful to determine whether a user
has read a text or not (see also the `element.scrollTop` and `element.clientHeight` properties).
For example:

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
    <input type="checkbox" id="agree" name="accept" />
    <label for="agree">I agree</label>
    <input type="submit" id="nextstep" value="Next" />
  </p>
</form>
```html

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

### `Element.scrollLeft`

he **`Element.scrollLeft`** property gets or sets the number of pixels that an element's content is
scrolled from its left edge.

If the element's `direction` is `rtl` (right-to-left), then `scrollLeft` is `0` when the scrollbar is
at its rightmost position (at the start of the scrolled content), and then increasingly negative
as you scroll towards the end of the content.

!!! error ""
    On systems using display scaling, `scrollLeft` may give you a decimal value.

Syntax

```javascript
Getting the valueSection
// Get the number of pixels scrolled
var sLeft = element.scrollLeft;
```

`sLeft` is an integer representing the number of pixels that `element` has been scrolled from the
left edge.

Setting the value

```javascript
// Set the number of pixels scrolled
element.scrollLeft = 10;
```

`scrollLeft` can be specified as any integer value. However:

- If the element can't be scrolled (e.g., it has no overflow), `scrollLeft` is set to 0.
- If specified as a value less than 0 (greater than 0 for right-to-left elements), `scrollLeft`
is set to `0`.
- If specified as a value greater than the maximum that the content can be scrolled, `scrollLeft`
- is set to the maximum.

Example

```html
<div id="container">
  <div id="content">Click the button to slide right!</div>
</div>

<button id="slide" type="button">Slide right</button>
```

```css
#container {
  width: 100px;
  height: 100px;
  border: 1px solid #ccc;
  overflow-x: scroll;
}

#content {
  width: 250px;
  background-color: #ccc;
}
```

```javascript
const button = document.getElementById('slide');

button.onclick = function () {
  document.getElementById('container').scrollLeft += 20;
};
```

### `Element.scrollTop`

The **`Element.scrollTop`** property gets or sets the number of pixels that an element's content
is scrolled vertically.

An element's `scrollTop` value is a measurement of the distance from the element's top to its
topmost visible content. When an element's content does not generate a vertical scrollbar, then its
`scrollTop` value is `0`.

!!! error ""
    On systems using display scaling, scrollTop may give you a decimal value.

Syntax

```javascript
// Get the number of pixels scrolled.
var intElemScrollTop = someElement.scrollTop;
```

After running this code, `intElemScrollTop` is an integer corresponding to the number of pixels that
the `element`'s content has been scrolled upwards.

```javascript
// Set the number of pixels scrolled.
element.scrollTop = intValue;
```

`scrollTop` can be set to any integer value, with certain caveats:

- If the element can't be scrolled (e.g. it has no overflow or if the element has a property of
"**non-scrollable**"), `scrollTop` is `0`.
- `scrollTop` doesn't respond to negative values; instead, it sets itself back to `0`.
- If set to a value greater than the maximum available for the element, `scrollTop` settles itself to
the maximum value.

![scrollTop](/media/webfrontend__scrollTop.png)

### `Element.scrollWidth`

The **`Element.scrollWidth`** read-only property is a measurement of the width of an element's content,
including content not visible on the screen due to overflow.

The `scrollWidth` value is equal to the minimum width the element would require in order to fit all
the content in the viewport without using a horizontal scrollbar. The width is measured in the same
way as `clientWidth`: it includes the element's padding, but not its border, margin or vertical
scrollbar (if present). It can also include the width of pseudo-elements such as `::before` or
`::after`. If the element's content can fit without a need for horizontal scrollbar, its
`scrollWidth` is equal to `clientWidth`

!!! warn ""
    This property will round the value to an integer. If you need a fractional value, use `element.getBoundingClientRect()`.

Syntax

```javascript
var xScrollWidth = element.scrollWidth;
```

*`xScrollWidth`* is the width of the `content` of element in pixels.

Example

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

### `Element.shadowRoot`

The **`Element.shadowRoot`** read-only property represents the shadow root hosted by the element.
Use `Element.attachShadow()` to add a shadow root to an existing element.

Syntax

```javascript
var shadowroot = element.shadowRoot;
```

Value

A `ShadowRoot` object instance, or `null` if the associated shadow root was attached with its mode
set to closed. (See `Element.attachShadow()` for further details).

Examples

The following snippets are taken from our life-cycle-callbacks example (see it live also), which
creates an element that displays a square of a size and color specified in the element's attributes.

Inside the `<custom-square>` element's class definition we include some life cycle callbacks that
make a call to an external function, `updateStyle()`, which actually applies the size and color to
the element. You'll see that we are passing it `this` (the custom element itself) as a parameter.

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

In the `updateStyle()` function itself, we get a reference to the shadow DOM using
`Element.shadowRoot`. From here we use standard DOM traversal techniques to find the `<style>`
element inside the shadow DOM and then update the CSS found inside it:

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

### `Element.slot`

The **`slot`** property of the `Element` interface returns the name of the shadow DOM slot the
element is inserted in.

A slot is a placeholder inside a web component that users can fill with their own markup (see
Using templates and slots for more information).

Syntax

```javascript
var aString = element.slot
element.slot = aString
```

Value

A `DOMString`.

Examples

we create a trivial custom element example called `<my-paragraph>` in which a shadow root is attached
and then populated using the contents of a template that contains a slot named `my-text`.

When `<my-paragraph>` is used in the document, the slot is populated by a slotable element by
including it inside the element with a `slot` attribute with the value `my-text`. Here is one such example:

```html
<my-paragraph>
  <span slot="my-text">Let's have some different text!</span>
</my-paragraph>
```

In our JavaScript file we get a reference to the `<span>` shown above, then log a reference to
the name of the corresponding `<slot>` element.

```javascript
let slottedSpan = document.querySelector('my-paragraph span')
console.log(slottedSpan.slot); // logs 'my-text'
```

### `Element.tagName`

The **`tagName`** read-only property of the `Element` interface returns the tag name of the element
on which it's called. For example, if the element is an `<img>`, its `tagName` property is `"IMG"`
(for HTML documents; it may be cased differently for XML/XHTML documents).

Syntax

```javascript
elementName = Element.tagName;
```

Value

A string indicating the element's tag name. This string's capitalization depends on the document type:

- For DOM trees which represent HTML documents, the returned tag name is always in the canonical
upper-case form. For example, tagName called on a `<div>` element returns "DIV".
- The tag names of elements in an XML DOM tree are returned in the same case in which they're
written in the original XML file. If an XML document includes a tag `"<SomeTag>"`,
then the `tagName` property's value is `"SomeTag"`.

For `Element` objects, the value of `tagName` is the same as the value of the `nodeName` property
the element object inherits from `Node`.

Example

```html
<span id="born">When I was born...</span>
```

```javascript
var span = document.getElementById("born");
console.log(span.tagName);
```

In XHTML (or any other XML format), the original case will be maintained, so `"span"` would be
output in case the original tag name was created lowercase. In HTML, `"SPAN"` would be output
instead regardless of the case used while creating the original document.
