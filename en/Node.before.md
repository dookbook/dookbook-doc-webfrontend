TOPICS: Node.before
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Node.before()`

The **`Node.before()`** method inserts a set of `Node` or `DOMString` objects in the children
list of this `ChildNode`'s parent, just before this `ChildNode`. `DOMString` objects are inserted as
equivalent `Text` nodes.

## Syntax

```javascript
[Throws, Unscopable]
void Node.before((Node or DOMString)... nodes);
```

| parameter | Description |
| :-- | :-- |
| `nodes` | A set of `Node` or `DOMString` objects to insert. |

### Exceptions

- `HierarchyRequestError`: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Inserting an element

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);
var span = document.createElement("span");

child.before(span);

console.log(parent.outerHTML);
// "<div><span></span><p></p></div>"
```

### Inserting text

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);

child.before("Text");

console.log(parent.outerHTML);
// "<div>Text<p></p></div>"
```

### Inserting an element and text

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);
var span = document.createElement("span");

child.before(span, "Text");

console.log(parent.outerHTML);
// "<div><span></span>Text<p></p></div>"
```

### `Node.before()` is unscopable

The `before()` method is not scoped into the with statement. See `Symbol.unscopables` for more information.

```javascript
with(node) {
  before("foo");
}
// ReferenceError: before is not defined
```

## Polyfill

You can polyfill the `before()` method in Internet Explorer 9 and higher with the following code:

```javascript
// from: https://github.com/jserz/js_piece/blob/master/DOM/ChildNode/before()/before().md
(function (arr) {
  arr.forEach(function (item) {
    if (item.hasOwnProperty('before')) {
      return;
    }
    Object.defineProperty(item, 'before', {
      configurable: true,
      enumerable: true,
      writable: true,
      value: function before() {
        var argArr = Array.prototype.slice.call(arguments),
          docFrag = document.createDocumentFragment();

        argArr.forEach(function (argItem) {
          var isNode = argItem instanceof Node;
          docFrag.appendChild(isNode ? argItem : document.createTextNode(String(argItem)));
        });

        this.parentNode.insertBefore(docFrag, this);
      }
    });
  });
})([Element.prototype, CharacterData.prototype, DocumentType.prototype]);
```
