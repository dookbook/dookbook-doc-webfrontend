TOPICS: Document.createElementNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createElementNS()`

Creates an element with the specified namespace URI and qualified name.

To create an element without specifying a namespace URI, use the `createElement()` method.

## Syntax

```javascript
node = document.adoptNode(externalNode);
```

| parameter | Description |
| :-- | :-- |
| `namespaceURI` | A string that specifies the namespace URI to associate with the element. The `namespaceURI` property of the created element is initialized with the value of namespaceURI. See Valid Namespace URIs. |
| `qualifiedName` | A string that specifies the type of element to be created. The `nodeName` property of the created element is initialized with the value of qualifiedName. |
| `options` | An optional `ElementCreationOptions` object containing a single property named `is`, whose value is the tag name for a custom element previously defined using `customElements.define()`. For backwards compatibility with previous versions of the Custom Elements specification, some browsers will allow you to pass a string here instead of an object, where the string's value is the custom element's tag name. See Extending native HTML elements for more information on how to use this parameter.<br>The new element will be given an is attribute whose value is the custom element's tag name. Custom elements are an experimental feature only available in some browsers.|

**Return value**: The new `Element`.

## Important Namespace URIs

- HTML [http://www.w3.org/1999/xhtml](http://www.w3.org/1999/xhtml)
- SVG [http://www.w3.org/2000/svg](http://www.w3.org/1999/xhtml)
- MathML [http://www.w3.org/1998/Math/MathML](http://www.w3.org/1998/Math/MathML)

## Examples

This creates a new `<div>` element in the XHTML namespace and appends it to the vbox element.
Although this is not an extremely useful XUL document, it does demonstrate the use of elements
from two different namespaces within a single document:

```html
<?xml version="1.0"?>
<page xmlns="http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul"
      xmlns:html="http://www.w3.org/1999/xhtml"
      title="||Working with elements||"
      onload="init()">

<script type="application/javascript"><![CDATA[
 let container;
 let newdiv;
 let txtnode;

 function init(){
   container = document.getElementById("ContainerBox");
   newdiv = document.createElementNS("http://www.w3.org/1999/xhtml", "div");
   txtnode = document.createTextNode("This is text that was constructed dynamically with createElementNS and createTextNode then inserted into the document using appendChild.");
   newdiv.appendChild(txtnode);
   container.appendChild(newdiv);
 }

]]></script>

 <vbox id="ContainerBox" flex="1">
  <html:div>
   The script on this page will add dynamic content below:
  </html:div>
 </vbox>

</page>
```

!!! warn ""
    The example given above uses inline script which is not recommended in XHTML documents. This
    particular example is actually an XUL document with embedded XHTML, however, the recommendation
    still applies.
