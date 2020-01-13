TOPICS: Element.hasAttributes
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.hasAttributes()`

The **`hasAttributes()`** method of the `Element` interface returns a [`Boolean`](/en/webfrontend/Boolean)
indicating whether the current element has any attributes or not.

## Syntax

```javascript
var result = element.hasAttributes();
```

| parameter | Description |
| :-- | :-- |
| `result` | holds the return value `true` or `false`. |

## Examples

```javascript
let foo = document.getElementById('foo');
if (foo.hasAttributes()) {
  // Do something with 'foo.attributes'
}
```

## Polyfill

```javascript
;(function(prototype) {
  prototype.hasAttributes = prototype.hasAttributes || function() {
    return (this.attributes.length > 0);
  }
})(Element.prototype);
```
