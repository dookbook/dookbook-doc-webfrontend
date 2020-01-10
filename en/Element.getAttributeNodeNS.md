TOPICS: Element.getAttributeNodeNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getAttributeNodeNS()`

Returns the `Attr` node for the attribute with the given namespace and name.

## Syntax

```javascript
attributeNode = element.getAttributeNodeNS(namespace, nodeName)
```

- `attributeNode` is the node for specified attribute.
- `namespace` is a string specifying the namespace of the attribute.
- `nodeName` is a string specifying the name of the attribute.

## Notes

`getAttributeNodeNS` is more specific than `getAttributeNode` in that it allows you to specify
attributes that are part of a particular namespace. The corresponding setter method is `setAttributeNodeNS`.
