TOPICS: ParentNode.prepend
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `ParentNode.prepend()`

The **`ParentNode.prepend()`** method inserts a set of `Node` objects or `DOMString` objects before
the first child of the `ParentNode`. `DOMString` objects are inserted as equivalent `Text` nodes.

## Syntax

```javascript
ParentNode.prepend(...nodesToPrepend);
```

| parameter | Description |
| :-- | :-- |
| `nodesToPrepend` | One or more nodes to insert before the first child node currently in the `ParentNode`. Each node can be specified as either a `Node` object or as a string; strings are inserted as new `Text` nodes. |

**Return value**: `undefined`.

## Exceptions

- `HierarchyRequestError`: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Prepending an element

```javascript
var parent = document.createElement("div");
var p = document.createElement("p");
var span = document.createElement("span");
parent.append(p);
parent.prepend(span);

console.log(parent.childNodes); // NodeList [ <span>, <p> ]
```

### Prepending text

```javascript
var parent = document.createElement("div");
parent.append("Some text");
parent.prepend("Headline: ");

console.log(parent.textContent); // "Headline: Some text"
```

### Appending an element and text

```javascript
var parent = document.createElement("div");
var p = document.createElement("p");
parent.prepend("Some text", p);

console.log(parent.childNodes); // NodeList [ #text "Some text", <p> ]
```

### `ParentNode.prepend()` is unscopable

The `prepend()` method is not scoped into the with statement.

```javascript
var parent = document.createElement("div");

with(parent) {
  prepend("foo");
}
// ReferenceError: prepend is not defined
```

## Polyfill

You can polyfill the `prepend()` method if it's not available:

```javascript
// Source: https://github.com/jserz/js_piece/blob/master/DOM/ParentNode/prepend()/prepend().md
(function (arr) {
  arr.forEach(function (item) {
    if (item.hasOwnProperty('prepend')) {
      return;
    }
    Object.defineProperty(item, 'prepend', {
      configurable: true,
      enumerable: true,
      writable: true,
      value: function prepend() {
        var argArr = Array.prototype.slice.call(arguments),
          docFrag = document.createDocumentFragment();

        argArr.forEach(function (argItem) {
          var isNode = argItem instanceof Node;
          docFrag.appendChild(isNode ? argItem : document.createTextNode(String(argItem)));
        });

        this.insertBefore(docFrag, this.firstChild);
      }
    });
  });
})([Element.prototype, Document.prototype, DocumentFragment.prototype]);
```
