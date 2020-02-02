TOPICS: Document.importNode
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.importNode()`

The `Document` object's **`importNode()`** method creates a copy of a `Node` or `DocumentFragment`
from another document, to be inserted into the current document later.

The imported node is not yet included in the document tree. To include it, you need to call an
insertion method such as `appendChild()` or `insertBefore()` with a node that is currently in
the document tree.

Unlike `document.adoptNode()`, the original node is not removed from its original document. The
imported node is a clone of the original.

## Syntax

```javascript
const importedNode = document.importNode(externalNode [, deep]);
```

| parameter | Description |
| :-- | :-- |
| `externalNode` | The external `Node` or `DocumentFragment` to import into the current document. |
| `deep` Optional | A Boolean which controls whether to include the entire DOM subtree of the `externalNode` in the import.<br>1. If `deep` is set to `true`, then `externalNode` and all of its descendants are copied.<br>2. If `deep` is set to `false`, then only `externalNode` is imported — the new node has no children. |

!!! warn "Note"
    In the DOM4 specification, deep was an optional argument with a default value of `true`.
    **This default has changed in the latest spec!** The new default value is `false`.
    Best Practice: Though it's still an optional argument, you should always provide the `deep`
    argument for backward and forward compatibility.
    1. With Gecko 28.0 (Firefox 28 / Thunderbird 28 / SeaMonkey 2.25 / Firefox OS 1.3), the console
    warns developers not to omit the argument.
    2. Starting with Gecko 29.0 (Firefox 29 / Thunderbird 29 / SeaMonkey 2.26)), a shallow clone is
    defaulted instead of a deep clone.

**Return value**: The copied `importedNode` in the scope of the importing document.

!!! warn "Note"
    `importedNode`'s `Node.parentNode` is `null`, since it has not yet been inserted into the
    document tree!

## Examples

```javascript
const iframe  = document.querySelector("iframe");
const oldNode = iframe.contentWindow.document.getElementById("myNode");
const newNode = document.importNode(oldNode, true);
document.getElementById("container").appendChild(newNode);
```

## Notes

Before they can be inserted into the current document, nodes from external documents should either be:

- cloned using `document.importNode()`; or
- adopted using `document.adoptNode()`.

!!! warn "Best Practice"
    Although Firefox doesn't currently enforce this rule, we encourage you to follow this rule for
    improved future compatibility.

For more on the `Node.ownerDocument` issues, see the W3C DOM FAQ.
