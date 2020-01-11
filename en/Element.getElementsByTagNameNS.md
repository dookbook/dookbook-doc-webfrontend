TOPICS: Element.getElementsByTagNameNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getElementsByTagNameNS()`

The **`Element.getElementsByTagNameNS()`** method returns a live `HTMLCollection` of elements with
the given tag name belonging to the given namespace. It is similar to [`Document.getElementsByTagNameNS`](/en/webfrontend/Document.getElementsByTagNameNS),
except that its search is restricted to descendants of the specified element.

## Syntax

```javascript
elements = element.getElementsByTagNameNS(namespaceURI, localName)
```

- `elements` is a live `HTMLCollection` of found elements in the order they appear in the tree.
- `element` is the element from where the search should start. Note that only the descendants of
this element are included in the search, not the node itself.
- `namespaceURI` is the namespace URI of elements to look for (see [`Element.namespaceURI`](/en/webfrontend/Element.namespaceURI)
and `Attr.namespaceURI`). For example, if you need to look for XHTML elements, use the XHTML namespace
URI, `http://www.w3.org/1999/xhtml`.
- `localName` is either the local name of elements to look for or the special value `"*"`, which
- matches all elements (see [`Element.localName`](/en/webfrontend/Element.localName) and `Attr.localName`).

## Examples

```javascript
// check the alignment on a number of cells in a table in an XHTML document.
var table = document.getElementById("forecast-table");
var cells = table.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "td");

for (var i = 0; i < cells.length; i++) {
    var axis = cells[i].getAttribute("axis");
    if (axis == "year") {
        // grab the data
    }
}
Specifi
```
