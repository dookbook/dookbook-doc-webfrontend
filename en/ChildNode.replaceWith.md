TOPICS: ChildNode.replaceWith
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `ChildNode.replaceWith()`

The **`ChildNode.replaceWith()`** method replaces this `ChildNode` in the children list of its parent
with a set of `Node` or `DOMString` objects. `DOMString` objects are inserted as equivalent `Text` nodes.

## Syntax

```javascript
[Throws, Unscopable]
void ChildNode.replaceWith((Node or DOMString)... nodes);
```

| parameter | Description |
| :-- | :-- |
| `nodes` | A set of `Node` or `DOMString` objects to replace.

## Exceptions

- `HierarchyRequestError`: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Using `replaceWith()`

```javascript
var parent = document.createElement("div");
var child = document.createElement("p");
parent.appendChild(child);
var span = document.createElement("span");

child.replaceWith(span);

console.log(parent.outerHTML);
// "<div><span></span></div>"
```

### `ChildNode.replaceWith()` is unscopable

The `replaceWith()` method is not scoped into the `with` statement.

```javascript
with(node) {
  replaceWith("foo");
}
// ReferenceError: replaceWith is not defined
```

## Polyfill

You can polyfill the `replaceWith()` method in Internet Explorer 10+ and higher with the following code:

```javascript
function ReplaceWithPolyfill() {
  'use-strict'; // For safari, and IE > 10
  var parent = this.parentNode, i = arguments.length, currentNode;
  if (!parent) return;
  if (!i) // if there are no arguments
    parent.removeChild(this);
  while (i--) { // i-- decrements i and returns the value of i before the decrement
    currentNode = arguments[i];
    if (typeof currentNode !== 'object'){
      currentNode = this.ownerDocument.createTextNode(currentNode);
    } else if (currentNode.parentNode){
      currentNode.parentNode.removeChild(currentNode);
    }
    // the value of "i" below is after the decrement
    if (!i) // if currentNode is the first argument (currentNode === arguments[0])
      parent.replaceChild(currentNode, this);
    else // if currentNode isn't the first
      parent.insertBefore(currentNode, this.previousSibling);
  }
}
if (!Element.prototype.replaceWith)
    Element.prototype.replaceWith = ReplaceWithPolyfill;
if (!CharacterData.prototype.replaceWith)
    CharacterData.prototype.replaceWith = ReplaceWithPolyfill;
if (!DocumentType.prototype.replaceWith)
    DocumentType.prototype.replaceWith = ReplaceWithPolyfill;
```
