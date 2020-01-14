TOPICS: Document.createComment
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createComment()`

**`createComment()`** creates a new comment node, and returns it.

## Syntax

```javascript
CommentNode = document.createComment(data);
```

| parameter | Description |
| :-- | :-- |
| `data` | A string containing the data to be added to the Comment. |

## Examples

```javascript
var docu = new DOMParser().parseFromString('<xml></xml>',  'application/xml');
var comment = docu.createComment('This is a not-so-secret comment in your document');

docu.getElementsByTagName('xml')[0].appendChild(comment);

alert(new XMLSerializer().serializeToString(docu));
// Displays: <xml><!--This is a not-so-secret comment in your document--></xml>
```
