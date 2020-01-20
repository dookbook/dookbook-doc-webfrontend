TOPICS: Document.createProcessingInstruction
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createProcessingInstruction()`

**`createProcessingInstruction()`** generates a new processing instruction node and returns it.

The new node usually will be inserted into an XML document in order to accomplish anything with it,
such as with `node.insertBefore`.

## Syntax

```javascript
piNode = document.createProcessingInstruction(target, data)
```

- `piNode` is the resulting `ProcessingInstruction` node.

| parameter | Description |
| :-- | :-- |
| `target` | is a string containing the first part of the processing instruction (i.e., `<?target … ?>`) |
| `data` | is a string containing any information the processing instruction should carry, after the target. The data is up to you, but it can't contain `?>`, since that closes the processing instruction. |

## Exceptions

`DOM_INVALID_CHARACTER`

Throws if either of the following are true:

- The processing instruction `target` is invalid — it should be a valid XML name that doesn't contain
"XML", "XML", or any case combination of the two, other than standardized ones such
as `<?xml-stylesheet ?>`.
- The closing processing instruction sequence (`?>`) is part of the `data`.

## Examples

```javascript
var doc = new DOMParser().parseFromString('<foo />', 'application/xml');
var pi = doc.createProcessingInstruction('xml-stylesheet', 'href="mycss.css" type="text/css"');

doc.insertBefore(pi, doc.firstChild);

console.log(new XMLSerializer().serializeToString(doc));
// Displays: <?xml-stylesheet href="mycss.css" type="text/css"?><foo/>
```
