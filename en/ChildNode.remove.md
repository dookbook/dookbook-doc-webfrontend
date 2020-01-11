TOPICS: ChildNode.remove
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `ChildNode.remove()`

The **`ChildNode.remove()`** method removes the object from the tree it belongs to.

## Syntax

```javascript
node.remove();
```

## Examples

### Using `remove()`

```html
<div id="div-01">Here is div-01</div>
<div id="div-02">Here is div-02</div>
<div id="div-03">Here is div-03</div>
```

```javascript
var el = document.getElementById('div-02');
el.remove(); // Removes the div with the 'div-02' id
```

### `ChildNode.remove()` is unscopable

The `remove()` method is not scoped into the with statement.

```javascript
with(node) {
  remove();
}
// ReferenceError: remove is not defined
```

## Polyfill

You can polyfill the `remove()` method in Internet Explorer 9 and higher with the following code:

```javascript
// from:https://github.com/jserz/js_piece/blob/master/DOM/ChildNode/remove()/remove().md
(function (arr) {
  arr.forEach(function (item) {
    if (item.hasOwnProperty('remove')) {
      return;
    }
    Object.defineProperty(item, 'remove', {
      configurable: true,
      enumerable: true,
      writable: true,
      value: function remove() {
        if (this.parentNode === null) {
          return;
        }
        this.parentNode.removeChild(this);
      }
    });
  });
})([Element.prototype, CharacterData.prototype, DocumentType.prototype]);
```
