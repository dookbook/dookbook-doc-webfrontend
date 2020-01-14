TOPICS: Document.close
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.close()`

The **`Document.close()`** method finishes writing to a document, opened with [`Document.open()`](/en/webfrontend/document.open).

## Syntax

```javascript
document.close();
```

## Examples

```javascript
// Open a document to write to it
document.open();

// Write the content of the document
document.write("<p>The one and only content.</p>");

// Close the document
document.close();
```
