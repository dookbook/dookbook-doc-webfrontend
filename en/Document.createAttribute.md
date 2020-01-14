TOPICS: Document.createAttribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createAttribute()`

The **`Document.createAttribute()`** method creates a new attribute node, and returns it. The object
created a node implementing the `Attr` interface. The DOM does not enforce what sort of attributes can
be added to a particular element in this manner.

!!! warn ""
    The string given in parameter is converted to lowercase.

## Syntax

```javascript
attribute = document.createAttribute(name)
```

| parameter | Description |
| :-- | :-- |
| `name` | is a string containing the name of the attribute. |

**Return value**: A `Attr` node.

## Exceptions

- `INVALID_CHARACTER_ERR` if the parameter contains invalid characters for XML attribute.

## Examples

```javascript
var node = document.getElementById("div1");
var a = document.createAttribute("my_attrib");
a.value = "newVal";
node.setAttributeNode(a);
console.log(node.getAttribute("my_attrib")); // "newVal"
```
