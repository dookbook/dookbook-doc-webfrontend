TOPICS: Document.createTreeWalker
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createTreeWalker()`

The **`Document.createTreeWalker()`** creator method returns a newly created `TreeWalker` object.

## Syntax

```javascript
document.createTreeWalker(root, whatToShow[, filter[, entityReferenceExpansion]]);
```

| parameter | Description |
| :-- | :-- |
| `root` | A root `Node` of this `TreeWalker` traversal. Typically this will be an element owned by the document. |
| `whatToShow` Optional | A `unsigned long` representing a bitmask created by combining the constant properties of `NodeFilter`. It is a convenient way of filtering for certain types of node. It defaults to `0xFFFFFFFF` representing the SHOW_ALL constant. |
| `filter` Optional | A `NodeFilter`, that is an object with a method `acceptNode`, which is called by the `TreeWalker` to determine whether or not to accept a node that has passed the `whatToShow` check. |

## `whatToShow` Supported values for parameters

| Constant | Numerical value | Description |
| `NodeFilter.SHOW_ALL` | `-1` (that is the max value of `unsigned long`) | Shows all nodes. |
| `NodeFilter.SHOW_COMMENT` | 128 | Shows `Comment` nodes. |
| `NodeFilter.SHOW_DOCUMENT` | 256 | Shows `Document` nodes. |
| `NodeFilter.SHOW_DOCUMENT_FRAGMENT` | 1024 | Shows `DocumentFragment` nodes. |
| `NodeFilter.SHOW_DOCUMENT_TYPE` | 512 | Shows `DocumentType` nodes. |
| `NodeFilter.SHOW_ELEMENT` | 1 | Shows `Element` nodes. |
| `NodeFilter.SHOW_PROCESSING_INSTRUCTION` | 64 | Shows `ProcessingInstruction` nodes. |
| `NodeFilter.SHOW_TEXT` | 4 | Shows `Text` nodes. |

**Return value**: A new `TreeWalker` object.

## Example

The following example goes through all nodes in the body, reduces the set of nodes to elements,
simply passes through as acceptable each node (it could reduce the set in the `acceptNode()` method
instead), and then makes use of tree walker iterator that is created to advance through the nodes
(now all elements) and push them into an array.

```javascript
var treeWalker = document.createTreeWalker(
  document.body,
  NodeFilter.SHOW_ELEMENT,
  { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
  false
);

var nodeList = [];

while(treeWalker.nextNode()) nodeList.push(treeWalker.currentNode);
```
