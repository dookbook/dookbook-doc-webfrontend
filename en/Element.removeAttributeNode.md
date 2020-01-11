TOPICS: Element.removeAttributeNode
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.removeAttributeNode()`

The **`removeAttributeNode()`** method of the `Element` object removes the specified attribute
from the current element.

## Syntax

```javascript
removedAttr = element.removeAttributeNode(attributeNode)
```

- `attributeNode` is the `Attr` node that needs to be removed.
- `removedAttr` is the removed `Attr` node.

## Examples

```javascript
// Given: <div id="top" align="center" />
var d = document.getElementById("top");
var d_align = d.getAttributeNode("align");
d.removeAttributeNode(d_align);
// align is now removed: <div id="top" />
```

## Notes

If the removed attribute has a default value, it is immediately replaced. The replacing attribute
has the same namespace URI and local name, as well as the original prefix, when applicable.

There is no `removeAttributeNodeNS` method; the `removeAttributeNode` method can remove both namespaced
attributes and non-namespaced attributes.
