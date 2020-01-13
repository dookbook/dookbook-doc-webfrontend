TOPICS: Element.setAttributeNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.setAttributeNS()`

**`setAttributeNS`** adds a new attribute or changes the value of an attribute with the given
namespace and name.

## Syntax

```javascript
element.setAttributeNS(namespace, name, value)
```

- `namespace` is a string specifying the namespace of the attribute.
- `name` is a string identifying the attribute by its qualified name; that is, a namespace prefix
followed by a colon followed by a local name.
- `value` is the desired string value of the new attribute.

## Examples

```javascript
let d = document.getElementById('d1');
d.setAttributeNS('http://www.mozilla.org/ns/specialspace', 'align', 'center');
```
