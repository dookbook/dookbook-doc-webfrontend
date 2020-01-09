TOPICS: document
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript document Object: `document`

## 属性

### `document.body`

The **`Document.body`** property represents the `<body>` or `<frameset>` node of the current
document, or `null` if no such element exists.

Syntax

```javascript
var objRef = document.body;
document.body = objRef;
```

Example

```javascript
// Given this HTML: <body id="oldBodyElement"></body>
alert(document.body.id); // "oldBodyElement"

var aNewBodyElement = document.createElement("body");

aNewBodyElement.id = "newBodyElement";
document.body = aNewBodyElement;
alert(document.body.id); // "newBodyElement"
```

Notes

`document.body` is the element that contains the content for the document. In documents with
`<body>` contents, returns the `<body>` element, and in frameset documents, this returns the
outermost `<frameset>` element.

Though `body` is settable, setting a new body on a document will effectively remove all the current
children of the existing `<body>` element.

### `document.characterSet`

The **`Document.characterSet`** read-only property returns the character encoding of the document
that it's currently rendered with. (A character encoding is a set of characters and how to interpret
bytes into those characters.)

!!! warn ""
    A “character set” and a “character encoding” are related, but different. Despite the name of
    this property, it returns the encoding.

Users can override the developer-specified encoding inside the Content-Type header or inline like
`<meta charset="utf-8">`, such as with Firefox's !!!View → Text Encoding!!! menu. This override is
provided to fix incorrect developer-specified encodings that result in garbled text.

!!! warn ""
    The properties `document.charset` and `document.inputEncoding` are legacy aliases for
    `document.characterSet`. Do not use them any more.

Syntax

```javascript
var string = document.characterSet;
```

Examples

```html
<button onclick="console.log(document.characterSet);">
  Log character encoding
</button>
<!-- displays document's character encoding in the dev console, such as "ISO-8859-1" or "UTF-8" -->
```

### `document.compatMode`

The **`Document.compatMode`** property indicates whether the document is rendered in Quirks mode
or Standards mode.

Syntax

```javascript
mode = document.compatMode;
```

Values

|  |  |
| :-- | :-- |
| `mode` | Is an enumerated value that can be:<br>1. `"BackCompat"` if the document is in quirks mode.<br>2. `"CSS1Compat"` if the document is in no-quirks (also known as "standards") mode or limited-quirks (also known as "almost standards") mode.

!!! warn "Note"
    All these modes are now standardized, so the older "standards" and "almost standards" names
    are nonsensical and no longer used in standards.

Example

```javascript
if (document.compatMode == "BackCompat") {
  // in Quirks mode
}
```

### `document.contentType`

The **`Document.contentType`** read-only property returns the MIME type that the document is being
rendered as. This may come from HTTP headers or other sources of MIME information, and might be
affected by automatic type conversions performed by either the browser or extensions.

!!! warn "Note"
    This property is unaffected by `<meta>` elements.

Syntax

```javascript
contentType = document.contentType;
```

Value

`contentType` is a read-only property.

### `document.currentScript`

The **`Document.currentScript`** property returns the `<script>` element whose script is currently
being processed and isn't a JavaScript module. (For modules use `import.meta` instead.)

It's important to note that this will not reference the `<script>` element if the code in the
script is being called as a callback or event handler; it will only reference the element while
it's initially being processed.

Syntax

```javascript
var curScriptElement = document.currentScript;
```

Example

This example checks to see if the script is being executed asynchronously:

```javascript
if (document.currentScript.async) {
  console.log("Executing asynchronously");
} else {
  console.log("Executing synchronously");
}
```

### `document.defaultView`

In browsers, **`document.defaultView`** returns the `window` object associated with a document,
or `null` if none is available.

Syntax

```javascript
var win = document.defaultView;
```

This property is read-only.

### `document.designMode`

**`document.designMode`** controls whether the entire document is editable. Valid values are
`"on"` and `"off"`. According to the specification, this property is meant to default to `"off"`.
Firefox follows this standard. The earlier versions of Chrome and IE default to `"inherit"`.
Starting in Chrome 43, the default is `"off"` and `"inherit"` is no longer supported. In IE6-10,
the value is capitalized.

Syntax

```javascript
var mode = document.designMode;
document.designMode = "on" || "off";
```

Example

Make an `<iframe>`'s document editable:

```javascript
iframeNode.contentDocument.designMode = "on";
```

### `document.dir`

The **`Document.dir`** property is a DOMString representing the directionality of the text of the
document, whether left to right (default) or right to left. Possible values are `'rtl'`, right to
left, and `'ltr'`, left to right.

Syntax

```javascript
dirStr = document.dir;
document.dir = dirStr;
```

### `document.doctype`

Returns the Document Type Declaration (DTD) associated with current document. The returned object
implements the `DocumentType` interface. Use `DOMImplementation.createDocumentType()` to create a `DocumentType`.

Syntax

```javascript
doctype = document.doctype;
```

- `doctype` is a read-only property.

Example

```javascript
var doctypeObj = document.doctype;

console.log(
  "doctypeObj.name: "           + doctypeObj.name            + "\n" +
  "doctypeObj.internalSubset: " + doctypeObj.internalSubset  + "\n" +
  "doctypeObj.publicId: "       + doctypeObj.publicId        + "\n" +
  "doctypeObj.systemId: "       + doctypeObj.systemId
);
```

### `document.documentElement`

**`Document.documentElement`** returns the [`Element`](/en/webfrontend/Element) that is the root
element of the `document` (for example, the [`<html>`](/en/webfrontend/<html>) element for HTML documents).

Syntax

```javascript
var element = document.documentElement;
```

Example

```javascript
var rootElement = document.documentElement;
var firstTier = rootElement.childNodes;

// firstTier is the NodeList of the direct children of the root element
for (var i = 0; i < firstTier.length; i++) {
   // do something with each direct kid of the root element
   // as firstTier[i]
}
```

!!! warn "Notes"
    For any non-empty HTML document, `document.documentElement` will always be an `<html>` element.
    For any non-empty XML document, `document.documentElement` will always be whatever element is
    the root element of the document.

### `document.documentURI`

The **`documentURI`** property of the `Document` interface returns the document location as a string.

As originally defined in DOM3 this attribute read/write. In the modern DOM Standard it is read only.

Syntax

```javascript
var string = document.documentURI;
```

!!! warn "Notes"
    Documents also have a `document.URL` property which returns the same value.

### `Document.domain`

The **`domain`** property of the `Document` interface gets/sets the domain portion of the origin of
the current document, as used by the same origin policy.

If this property is successfully set, the port part of the origin is also set to `null`.

Syntax

```javascript
var domainString = document.domain;
document.domain = domainString;
```

Value

The domain portion of the current document's origin.

Exceptions

|  |  |
| :-- | :-- |
| **`SecurityError`** | An attempt has been made to set domain under one of the following conditions:<br>1. The document is inside a sandboxed `<iframe>`<br>2. The document has no browsing context<br>3. The document's effective domain is `null`<br>4. The given value is not equal to the document's effective domain (or it is not a registerable domain suffix of it)<br>5. The document-domain Feature-Policy is enabled

Examples

Getting the domain

For the URI `http://developer.mozilla.org/en-US/docs/Web`, this example sets currentDomain to the
string `"developer.mozilla.org"`.

```javascript
var currentDomain = document.domain;
```

Closing a window

If a document, such as `www.example.xxx/good.html`, has the domain of `"www.example.xxx"`, this
example attempts to close the window.

```javascript
var badDomain = "www.example.xxx";

if (document.domain == badDomain) {
  // Just an example: window.close() sometimes has no effect
  window.close();
}
```

### `document.embeds`

The **`embeds`** read-only property of the `Document` interface returns a list of the embedded
[`<object>`](/en/webfrontend/<object>) elements within the current document.

Syntax

```javascript
nodeList = document.embeds
```

Value

An `HTMLCollection`.

### `Document.forms`

The **`forms`** read-only property of the Document interface returns an HTMLCollection listing all
the [`<form>`](/en/webfrontend/<form>) elements contained in the document.

!!! warn "Note"
    Similarly, you can access a list of a form's component user input elements using the
    `HTMLFormElement.elements` property.

Syntax

```javascript
collection = document.forms;
```

Value

An HTMLCollection object listing all of the document's forms. Each item in the collection is a
`HTMLFormElement` representing a single [`<form>`](/en/webfrontend/<form>) element.

If the document has no forms, the returned collection is empty, with a length of zero.

Examples

Getting form information

```html
<!DOCTYPE html>
<html lang="en">

<head>
<title>document.forms example</title>
</head>

<body>

<form id="robby">
  <input type="button" onclick="alert(document.forms[0].id);" value="robby's form" />
</form>

<form id="dave">
  <input type="button" onclick="alert(document.forms[1].id);" value="dave's form" />
</form>

<form id="paul">
  <input type="button" onclick="alert(document.forms[2].id);" value="paul's form" />
</form>

</body>
</html>
Getting an element from within a formSection
var selectForm = document.forms[index];
var selectFormElement = document.forms[index].elements[index];
Named form accessSection
<!DOCTYPE html>
<html lang="en">
<head>
  <title>document.forms example</title>
</head>

<body>

<form name="login">
  <input name="email" type="email">
  <input name="password" type="password">
  <button type="submit">Log in</button>
</form>

<script>
  var loginForm = document.forms.login; // Or document.forms['login']
  loginForm.elements.email.placeholder = 'test@example.com';
  loginForm.elements.password.placeholder = 'password';
</script>
</body>
</html>
```

### `document.mozFullScreenEnabled`

The read-only **`fullscreenEnabled`** property on the `Document` interface indicates whether or not
full-screen mode is available. Full-screen mode is available only for a page that has no windowed
plug-ins in any of its documents, and if all [`<iframe>`](/en/webfrontend/<iframe>) elements which
contain the document have their `allowfullscreen` attribute set.

Although this property is read-only, it will not throw if it is modified (even in strict mode);
the setter is a no-operation and it will be ignored.

Syntax

```javascript
var isFullscreenAvailable = document.fullscreenEnabled;
```

Value

A `Boolean` value which is `true` if the document and the elements within can be placed into
full-screen mode by calling `Element.requestFullscreen()`. If full-screen mode isn't available,
this value is false.

Example

In this example, before attempting to request full-screen mode for a [`<video>`](/en/webfrontend/<video>)
element, the value of `fullscreenEnabled` is checked, in order to avoid making the attempt when not available.

```javascript
function requestFullScreen() {
  if (document.fullscreenEnabled) {
    videoElement.requestFullScreen();
  } else {
    console.log('Your browser cannot use fullscreen right now');
  }
}
```

### `Document.head`

The **`head`** read-only property of the `Document` interface returns the [`<head>`](/en/webfrontend/<head>)
element of the current document.

Syntax

```javascript
var objRef = document.head;
```

Value

An `HTMLHeadElement`.

Example

```html
<!doctype html>
<head id="my-document-head">
  <title>Example: using document.head</title>
</head>

<script>
  var theHead = document.head;

  console.log(theHead.id); // "my-document-head";

  console.log( theHead === document.querySelector("head") ); // true
</script>
```

Notes

`document.head` is read-only. Trying to assign a value to this property will fail silently or,
in Strict Mode, throws a `TypeError` .

### `Document.hidden`

The **`Document.hidden`** read-only property returns a Boolean value indicating if the page is
considered hidden or not.

Syntax

```javascript
var boolean = document.hidden
```

Examples

```javascript
document.addEventListener("visibilitychange", function() {
  console.log( document.hidden );
  // Modify behavior...
});
```

### `document.images`

The **`images`** read-only property of the `Document` interface returns a collection of the images
in the current HTML document.

Syntax

```javascript
var imageCollection = document.images;
```

Value

An `HTMLCollection` providing a live list of all of the images contained in the current document.
Each entry in the collection is an `HTMLImageElement` representing a single image element.

Usage notes

You can use either JavaScript array notation or the `item()` method on the returned collection to
access the items in the collection. The following are equivalent:

```javascript
firstImage = imageCollection.item(0);

firstImage = imageCollection[0];
```

Example

This example looks through the list of images and finds one whose name is `"banner.gif"`.

```javascript
var ilist = document.images;

for(var i = 0; i < ilist.length; i++) {
    if(ilist[i].src == 'banner.gif') {
        // found the banner
    }
}
```

### `document.implementation`

The **`Document.implementation`** property returns a `DOMImplementation` object associated with
the current document.

Syntax

```javascript
DOMImpObj = document.implementation;
```

Example

```javascript
var modName = "HTML";
var modVer = "2.0";
var conformTest = document.implementation.hasFeature( modName, modVer );

alert( "DOM " + modName + " " + modVer + " supported?: " + conformTest );

// alerts with: "DOM HTML 2.0 supported?: true" if DOM Level 2 HTML module is supported.
```

A list of module names (e.g., Core, HTML, XML, etc.) is available in the DOM Level 2 Conformance Section.

Notes

The W3C's DOM Level 1 Recommendation only specified the `hasFeature` method, which is one way to
determine if a DOM module is supported by a browser. If available, other `DOMImplementation`
methods provide services for controlling things outside of a single document. For example, the
`DOMImplementation` interface includes a `createDocumentType` method with which DTDs can be
created for one or more documents managed by the implementation.

### `document.lastModified`

The **`lastModified`** property of the `Document` interface returns a string containing the date
and time on which the current document was last modified.

Syntax

```javascript
var string = document.lastModified;
```

Examples

This example alerts the value of lastModified.

```javascript
alert(document.lastModified);
// returns: Tuesday, December 16, 2017 11:09:42
```

Transforming lastModified into a Date object

This example transforms `lastModified` into a [`Date`](/en/webfrontend/Date) object.

```javascript
let oLastModif = new Date(document.lastModified);
```

Transforming lastModified into milliseconds

This example transforms `lastModified` into the number of milliseconds since January 1, 1970, 00:00:00,
local time.

```javascript
let nLastModif = Date.parse(document.lastModified);
```

Notes

Note that as a string, `lastModified` cannot easily be used for comparing the modification dates of
documents. Here is a possible example of how to show an alert message when the page changes

```javascript
if (Date.parse(document.lastModified) > parseFloat(document.cookie.replace(/(?:(?:^|.*;)\s*last_modif\s*\=\s*([^;]*).*$)|^.*$/, "$1") || "0")) {
  document.cookie = "last_modif=" + Date.now() + "; expires=Fri, 31 Dec 9999 23:59:59 GMT; path=" + location.pathname;
  alert("This page has changed!");
}
```

…the same example, but skipping the first visit:

```javascript
var
  nLastVisit = parseFloat(document.cookie.replace(/(?:(?:^|.*;)\s*last_modif\s*\=\s*([^;]*).*$)|^.*$/, "$1")),
  nLastModif = Date.parse(document.lastModified);

if (isNaN(nLastVisit) || nLastModif > nLastVisit) {
  document.cookie = "last_modif=" + Date.now() + "; expires=Fri, 31 Dec 9999 23:59:59 GMT; path=" + location.pathname;

  if (isFinite(nLastVisit)) {
    alert("This page has been changed!");
  }
}
```

### `Document.links`

The **`links`** read-only property of the `Document` interface returns a collection of all [`<area>`](/en/webfrontend/<area>)
elements and [`<a>`](/en/webfrontend/<a>) elements in a document with a value for the href attribute.

Syntax

```javascript
nodeList = document.links
```

Value

An `HTMLCollection`.

Example

```javascript
var links = document.links;
for(var i = 0; i < links.length; i++) {
  var linkHref = document.createTextNode(links[i].href);
  var lineBreak = document.createElement("br");
  document.body.appendChild(linkHref);
  document.body.appendChild(lineBreak);
}
```

### `Document.location`

The **`Document.location`** read-only property returns a `Location` object, which contains
information about the URL of the document and provides methods for changing that URL and loading
another URL.

Though `Document.location` is a read-only Location object, you can also assign a `DOMString` to it.
This means that you can work with document.location as if it were a string in most cases:
`document.location = 'http://www.example.com'` is a synonym of `document.location.href = 'http://www.example.com'`.

To retrieve just the URL as a string, the read-only `document.URL` property can also be used.

If the current document is not in a browsing context, the returned value is `null`.

Syntax

```javascript
locationObj = document.location
document.location = 'http://www.mozilla.org' // Equivalent to document.location.href = 'http://www.mozilla.org'
```

Examples

```javascript
console.log(document.location);
// Prints a string like
// "http://www.example.com/juicybits.html" to the console
```

### `Document.plugins`

The **`plugins`** read-only property of the Document interface returns an HTMLCollection object
containing one or more HTMLEmbedElements representing the [`<embed>`](/en/webfrontend/<embed>)
elements in the current document.

!!! warn ""
    For a list of installed plugins, use NavigatorPlugins.plugins instead.

Syntax

```javascript
embedArrayObj = document.plugins
```

Value

An `HTMLCollection`, or `null` if there are no embeds in the document.

### `document.readyState`

The **`Document.readyState`** property describes the loading state of the `document`.

When the value of this property changes, a `readystatechange` event fires on the `document` object.

Syntax

```javascript
var string = document.readyState;
```

Values

The `readyState` of a document can be one of following:

|  |  |
| :-- | :-- |
| **`loading`** | The `document` is still loading. |
| **`interactive`** | The document has finished loading and the document has been parsed but sub-resources such as images, stylesheets and frames are still loading. |
| **`complete`** | The document and all sub-resources have finished loading. The state indicates that the `load` event is about to fire. |

Examples

Different states of readiness

```javascript
switch (document.readyState) {
  case "loading":
    // The document is still loading.
    break;
  case "interactive":
    // The document has finished loading. We can now access the DOM elements.
    // But sub-resources such as images, stylesheets and frames are still loading.
    var span = document.createElement("span");
    span.textContent = "A <span> element.";
    document.body.appendChild(span);
    break;
  case "complete":
    // The page is fully loaded.
    console.log("The first CSS rule is: " + document.styleSheets[0].cssRules[0].cssText);
    break;
}
```

readystatechange as an alternative to DOMContentLoaded event

```javascript
// Alternative to DOMContentLoaded event
document.onreadystatechange = function () {
  if (document.readyState === 'interactive') {
    initApplication();
  }
}
```

readystatechange as an alternative to load event

```javascript
// Alternative to load event
document.onreadystatechange = function () {
  if (document.readyState === 'complete') {
    initApplication();
  }
}
```

readystatechange as event listener to insert or modify the DOM before DOMContentLoaded

```javascript
document.addEventListener('readystatechange', event => {
  if (event.target.readyState === 'interactive') {
    initLoader();
  }
  else if (event.target.readyState === 'complete') {
    initApp();
  }
});
```

### `document.referrer`

The **`Document.referrer`** property returns the URI of the page that linked to this page.

Syntax

```javascript
var referrer = document.referrer;
```

Value

The value is an empty string if the user navigated to the page directly (not through a link, but,
for example, by using a bookmark). Because this property returns only a string, it doesn't give you
document object model (DOM) access to the referring page.

Inside an [`<iframe>`](/en/webfrontend/<iframe>), the `Document.referrer` will initially be set to
the same value as the `href` of the parent window's `Window.location`.

### `Document.scripts`

The **`scripts`** property of the `Document` interface returns a list of the
[`<script>`](/en/webfrontend/<script>) elements in the document. The returned object is an `HTMLCollection`.

Syntax

```javascript
var scriptList = document.scripts;
```

Value

An `HTMLCollection`. You can use this just like an array to get all the elements in the list.

Example

This example looks to see if the page has any [`<script>`](/en/webfrontend/<script>) elements.

```javascript
let scripts = document.scripts;

if (scripts.length) {
  alert('This page has scripts!');
}
```

### `Document.scrollingElement`

The **`scrollingElement`** read-only property of the `Document` interface returns a reference to the
`Element` that scrolls the document. In standards mode, this is the root
element of the document, `document.documentElement`.

When in quirks mode, the `scrollingElement` attribute returns the HTML `body` element if it exists
and is not potentially scrollable, otherwise it returns null.

Syntax

```javascript
var element = document.scrollingElement;
```

Example

```javascript
var scrollElm = document.scrollingElement;
scrollElm.scrollTop = 0;
```

### `Document.title`

The **`document.title`** property gets or sets the current title of the document.

Syntax

```javascript
var docTitle = document.title;
```

docTitle is a string containing the document's title. If the title was overridden by setting
`document.title`, it contains that value. Otherwise, it contains the title specified in the markup
(see the Notes below).

```javascript
document.title = newTitle;
```

`newTitle` is the new title of the document. The assignment affects the return value of
`document.title`, the title displayed for the document (e.g. in the titlebar of the window or tab),
and it also affects the DOM of the document (e.g. the content of the `<title>` element in an HTML document).

Example

```html
<!DOCTYPE html>
<html>
<head>
  <title>Hello World!</title>
</head>
<body>

  <script>
    alert(document.title); // displays "Hello World!"
    document.title = "Goodbye World!";
    alert(document.title); // displays "Goodbye World!"
  </script>

</body>
</html>
```

Notes

This property applies to HTML, SVG, XUL, and other documents in Gecko.

For HTML documents the initial value of `document.title` is the text content of the `<title>`
element. For XUL it's the value of the `title` attribute of the `<xul:window>` or other
top-level XUL element.

In XUL, accessing `document.title` before the document is fully loaded has undefined behavior:
`document.title` may return an empty string and setting `document.title` may have no effect.

### `document.URL`

The **`URL`** read-only property of the `Document` interface returns the document location as a string.

Syntax

```javascript
var string = document.URL
```

Example

```javascript
document.getElementById("url").textContent = document.URL;
```

```html
<p id="urlText">
  URL:<br/>
  <span id="url">URL goes here</span>
</p>
```

### `Document.visibilityState`

The **`Document.visibilityState`** read-only property returns the visibility of the `document`,
that is in which context this element is now visible. It is useful to know if the document is in
the background or an invisible tab, or only loaded for pre-rendering. Possible values are:

|  |  |
| :-- | :-- |
| **`'visible'`** | The page content may be at least partially visible. In practice this means that the page is the foreground tab of a non-minimized window.
| **`'hidden'`** | The page content is not visible to the user. In practice this means that the document is either a background tab or part of a minimized window, or the OS screen lock is active.
| **`'prerender'`** | The page content is being prerendered and is not visible to the user (considered hidden for purposes of `document.hidden`). The document may start in this state, but will never transition to it from another value. Note: This was removed from the standard. Check compatibility table for details.

When the value of this property changes, the `visibilitychange` event is sent to the `Document`.

Typical use of this can be to prevent the download of some assets when the document is solely
prerendered, or stop some activities when the document is in the background or minimized.

Syntax

```javascript
var string = document.visibilityState
```

Examples

```javascript
document.addEventListener("visibilitychange", function() {
  console.log( document.visibilityState );
  // Modify behavior...
});
```
