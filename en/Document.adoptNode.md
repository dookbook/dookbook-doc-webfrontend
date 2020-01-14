TOPICS: Document.adoptNode
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.adoptNode()`

**`Document.adoptNode()`** transfers a node from another document into the method's document.
The adopted node and its subtree is removed from its original document (if any), and its
`ownerDocument` is changed to the current document. The node can then be inserted into the current document.

## Syntax

```javascript
node = document.adoptNode(externalNode);
```

| parameter | Description |
| :-- | :-- |
| `node` | The adopted node that now has this document as its `ownerDocument`. The node's `parentNode` is `null`, since it has not yet been inserted into the document tree. Note that `node` and `externalNode` are the same object after this call. |
| `externalNode` | The node from another document to be adopted. |

## Examples

```javascript
var iframe = document.querySelector('iframe');
var iframeImages = iframe.contentDocument.querySelectorAll('img');
var newParent = document.getElementById('images');

iframeImages.forEach(function(imgEl) {
  newParent.appendChild(document.adoptNode(imgEl));
});
```

## Notes

Nodes from external documents should be cloned using [`document.importNode()`](/en/webfrontend/document.importNode)
(or adopted using `document.adoptNode()`) before they can be inserted into the current document.
For more on the `Node.ownerDocument` issues, see the [W3C DOM FAQ](http://www.w3.org/DOM/faq.html#ownerdoc).

Firefox doesn't currently enforce this rule (it did for a while during the development of Firefox 3,
but too many sites break when this rule is enforced). We encourage Web developers to fix their code
to follow this rule for improved future compatibility.
