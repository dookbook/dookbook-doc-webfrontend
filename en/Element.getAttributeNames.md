TOPICS: Element.getAttributeNames
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getAttributeNames()`

The **`getAttributeNames()`** method of the `Element` interface returns the attribute names of the
element as an [`Array`](/en/webfrontend/Array) of strings. If the element has no attributes it
returns an empty array.

Using `getAttributeNames()` along with `getAttribute()`, is a memory-efficient and performant
alternative to accessing `Element.attributes`.

## Syntax

```javascript
let attributeNames = element.getAttributeNames();
```

## Examples

```javascript
// Iterate over element's attributes
for (let name of element.getAttributeNames()) {
  let value = element.getAttribute(name);
  console.log(name, value);
}
```

## Polyfill

```javascript
if (Element.prototype.getAttributeNames == undefined) {
  Element.prototype.getAttributeNames = function () {
    var attributes = this.attributes;
    var length = attributes.length;
    var result = new Array(length);
    for (var i = 0; i < length; i++) {
      result[i] = attributes[i].name;
    }
    return result;
  };
}
```
