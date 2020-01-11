TOPICS: Element.removeAttributeNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.removeAttributeNS()`

The **`removeAttributeNS()`** method of the `Element` interface removes the specified attribute
from an element.

## Syntax

```javascript
element.removeAttributeNS(namespace, attrName);
```

- `namespace` is a string that contains the namespace of the attribute.
- `attrName` is a string that names the attribute to be removed from the current node.

## Examples

```javascript
// Given:
//   <div id="div1" xmlns:special="http://www.mozilla.org/ns/specialspace"
//     special:specialAlign="utterleft" width="200px" />
d = document.getElementById("div1");
d.removeAttributeNS("http://www.mozilla.org/ns/specialspace", "specialAlign");
// Now: <div id="div1" width="200px" />
```
