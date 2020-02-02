TOPICS: Document.getElementsByTagNameNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.getElementsByTagNameNS()`

Returns a list of elements with the given tag name belonging to the given namespace. The complete
document is searched, including the root node.

## Syntax

```javascript
elements = document.getElementsByTagNameNS(namespace, name)
```

- *elements* is a live `NodeList` (but see the note below) of found elements in the order they
appear in the tree.

| parameter | Description |
| :-- | :-- |
| `namespace` | is the namespace URI of elements to look for. |
| `name` | is either the local name of elements to look for or the special value `*`, which matches all elements. |

!!! warn "Note"
    While the W3C specification says elements is a NodeList, this method returns a `HTMLCollection`
    both in Gecko and Internet Explorer. Opera returns a NodeList, but with a namedItem method
    implemented, which makes it similar to a HTMLCollection. As of January 2012, only in WebKit
    browsers is the returned value a pure NodeList.

!!! warn "Note"
    Currently parameters in this method are case-sensitive, but they were case-insensitive in
    Firefox 3.5 and before. See the developer release note for Firefox 3.6 and a note in Browser
    compatibility section in `Element.getElementsByTagNameNS` for details.

## Examples

In the following example `getElementsByTagNameNS` starts from a particular parent element, and
searches topdown recursively through the DOM from that parent element, looking for child elements
matching the tag `name` parameter.

Note that when the node on which `getElementsByTagName` is invoked is not the document node, in
fact the `element.getElementsByTagNameNS` method is used.

To use the following example, just copy/paste it into a new file saved with the `.xhtml` extension.

```html
<html xmlns="http://www.w3.org/1999/xhtml">

<head>
<title>getElementsByTagNameNS example</title>

<script type="text/javascript">

function getAllParaElems()
{
  var allParas = document.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "p");

  var num = allParas.length;

  alert("There are " + num + " &lt;p&gt; elements in this document");
}


function div1ParaElems()
{
  var div1 = document.getElementById("div1")
  var div1Paras = div1.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "p");

  var num = div1Paras.length;

  alert("There are " + num + " &lt;p&gt; elements in div1 element");
}


function div2ParaElems()
{
  var div2 = document.getElementById("div2")
  var div2Paras = div2.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "p");

  var num = div2Paras.length;

  alert("There are " + num + " &lt;p&gt; elements in div2 element");
}

</script>
</head>

<body style="border: solid green 3px">
<p>Some outer text</p>
<p>Some outer text</p>

  <div id="div1" style="border: solid blue 3px">
    <p>Some div1 text</p>
    <p>Some div1 text</p>
    <p>Some div1 text</p>

    <div id="div2" style="border: solid red 3px">
    <p>Some div2 text</p>
    <p>Some div2 text</p>
    </div>
  </div>

<p>Some outer text</p>
<p>Some outer text</p>

<button onclick="getAllParaElems();">
 show all p elements in document</button><br />

<button onclick="div1ParaElems();">
 show all p elements in div1 element</button><br />

<button onclick="div2ParaElems();">
 show all p elements in div2 element</button>

</body>
</html>
```

## Potential Workaround for other browsers which do not support

If the desired browser did not support XPath, another approach (such as traversing the DOM through
all its children, identifying all @xmlns instances, etc.) would be necessary to find all tags with
the desired local name and namespace, but XPath is much faster. (To accommodate Explorer, one could
call an XPath wrapper instead of the XPath in the function below (as Explorer supports XPath with a
different API), such as this wrapper class.)

```javascript
function getElementsByTagNameNSWrapper (ns, elName, doc, context) {
 if (!doc) {
  doc = document;
 }
 if (!context) {
  context = doc;
 }

 var result = doc.evaluate('//*[local-name()="'+elName+'" and namespace-uri() = "'+ns+'"]', context, null, XPathResult.ORDERED_NODE_SNAPSHOT_TYPE, null);

  var a = [];
  for(var i = 0; i < result.snapshotLength; i++) {
    a[i] = result.snapshotItem(i);
  }
  return a;
}
```
