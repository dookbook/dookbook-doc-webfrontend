TOPICS: Node.append
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Node.append()`

The **`Node.append()`** method inserts a set of `Node` objects or `DOMString` objects after
the last child of the `ParentNode`. `DOMString` objects are inserted as equivalent Text nodes.

Differences from `Node.appendChild()`:

- `Node.append()` allows you to also append `DOMString` objects, whereas `Node.appendChild()`
only accepts `Node` objects.
- `Node.append()` has no return value, whereas `Node.appendChild()` returns the appended
`Node` object.
- `Node.append()` can append several nodes and strings, whereas `Node.appendChild()` can only
append one node.

## Syntax

```javascript
// [Throws, Unscopable]
Node.append(...nodesOrDOMStrings) // returns undefined
```

| parameter | Description |
| :-- | :-- |
| `nodes` | A set of `Node` or `DOMString` objects to insert. |

### Exceptions

- `HierarchyRequestError`: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Appending an element

```javascript
let parent = document.createElement("div")
let p = document.createElement("p")
parent.append(p)

console.log(parent.childNodes) // NodeList [ <p> ]
```

### Appending text

```javascript
let parent = document.createElement("div")
parent.append("Some text")

console.log(parent.textContent) // "Some text"
```

### Appending an element and text

```javascript
let parent = document.createElement("div")
let p = document.createElement("p")
parent.append("Some text", p)

console.log(parent.childNodes) // NodeList [ #text "Some text", <p> ]
```

### `Node.append()` is unscopable

The `append()` method is not scoped into the with statement. See `Symbol.unscopables` for more information.

```javascript
let parent = document.createElement("div")

with(parent) { ]
  append("foo")
}
// ReferenceError: append is not defined
```

### Polyfill

You can polyfill the `append()` method in Internet Explorer 9 and higher with the following code:

```javascript
// Source: https://github.com/jserz/js_piece/blob/master/DOM/ParentNode/append()/append().md
(function (arr) {
  arr.forEach(function (item) {
    if (item.hasOwnProperty('append')) {
      return;
    }
    Object.defineProperty(item, 'append', {
      configurable: true,
      enumerable: true,
      writable: true,
      value: function append() {
        var argArr = Array.prototype.slice.call(arguments),
          docFrag = document.createDocumentFragment();

        argArr.forEach(function (argItem) {
          var isNode = argItem instanceof Node;
          docFrag.appendChild(isNode ? argItem : document.createTextNode(String(argItem)));
        });

        this.appendChild(docFrag);
      }
    });
  });
})([Element.prototype, Document.prototype, DocumentFragment.prototype]);
```
