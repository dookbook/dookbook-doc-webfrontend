TOPICS: Document.createNodeIterator
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createNodeIterator()`

Returns a new `NodeIterator` object.

## Syntax

```javascript
var nodeIterator = document.createNodeIterator(root, whatToShow, filter);
```

| parameter | Description |
| :-- | :-- |
| `root` | The root node at which to begin the `NodeIterator`'s traversal. |
| `whatToShow` | Is an optional `unsigned long` representing a bitmask created by combining the constant properties of `NodeFilter`. It is a convenient way of filtering for certain types of node. It defaults to `0xFFFFFFFF` representing the `SHOW_ALL` constant. |
| `filter` | An object implementing the `NodeFilter` interface; its `acceptNode()` method will be called for each node in the subtree based at root which is accepted as included by the whatToShow flag to determine whether or not to include it in the list of iterable nodes (a simple callback function may also be used instead). The method should return one of `NodeFilter.FILTER_ACCEPT`, `NodeFilter.FILTER_REJECT`, or `NodeFilter.FILTER_SKIP`. See the Example. |

!!! warn "Note"
    Prior to Gecko 12.0 (Firefox 12.0 / Thunderbird 12.0 / SeaMonkey 2.9), this method accepted an
    optional fourth parameter (`entityReferenceExpansion`) that is not part of the DOM4 specification,
    and has therefore been removed. This parameter indicated whether or not the children of entity
    reference nodes were visible to the iterator. Since such nodes were never created in browsers,
    this paramater had no effect.

| Constant | Numerical value | Description |
| :--- | :--- | :--- |
| `NodeFilter.SHOW_ALL` | `-1` (that is the max value of `unsigned long`) | Shows all nodes. |
| `NodeFilter.SHOW_COMMENT` | `128` | Shows `Comment` nodes. |
| `NodeFilter.SHOW_DOCUMENT` | `256` | Shows `Document` nodes. |
| `NodeFilter.SHOW_DOCUMENT_FRAGMENT` | `1024` | Shows `DocumentFragment` nodes. |
| `NodeFilter.SHOW_DOCUMENT_TYPE` | `512` | Shows `DocumentType` nodes. |
| `NodeFilter.SHOW_ELEMENT` | `1` | Shows `Element` nodes. |
| `NodeFilter.SHOW_PROCESSING_INSTRUCTION` | `64` | Shows `ProcessingInstruction` nodes. |
| `NodeFilter.SHOW_TEXT` | `4` | Shows `Text` nodes. |

## Examples

```javascript
var nodeIterator = document.createNodeIterator(
  document.body,
  NodeFilter.SHOW_ELEMENT,
  function(node) {
      return node.nodeName.toLowerCase() === 'p' ? NodeFilter.FILTER_ACCEPT : NodeFilter.FILTER_REJECT;
  }
);
var pars = [];
var currentNode;

while (currentNode = nodeIterator.nextNode()) {
  pars.push(currentNode);
}
```
