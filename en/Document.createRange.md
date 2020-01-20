TOPICS: Document.createRange
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createRange()`

The **`Document.createRange()`** method returns a new Range object.

## Syntax

```javascript
range = document.createRange();
```

- `range` is the created `Range` object.

## Examples

```javascript
let range = document.createRange();

range.setStart(startNode, startOffset);
range.setEnd(endNode, endOffset);
```

## Notes

Once a `Range` is created, you need to set its boundary points before you can make use of most of
its methods.
