TOPICS: Element.getAttributeNode
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getAttributeNode()`

Returns the specified attribute of the specified element, as an `Attr` node.

## Syntax

```javascript
var attrNode = element.getAttributeNode(attrName);
```

- `attrNode` is an `Attr` node for the attribute.
- `attrName` is a string containing the name of the attribute.

## Examples

```javascript
// html: <div id="top" />
let t = document.getElementById("top");
let idAttr = t.getAttributeNode("id");
alert(idAttr.value == "top")
```
