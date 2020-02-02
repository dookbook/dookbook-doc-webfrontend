TOPICS: Document.write
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.write()`

The **`Document.write()`** method writes a string of text to a document stream opened by `document.open()`.

!!! warn "Note"
    as `document.write` writes to the document **stream**, calling `document.write` on a closed
    (loaded) document automatically calls `document.open`, which will clear the document.

## Syntax

```javascript
document.write(markup);
```

| parameter | Description |
| :-- | :-- |
| `markup` | A string containing the text to be written to the document. |

## Examples

```html
<html>
<head>
  <title>write example</title>
  <script>
    function newContent() {
      document.open();
      document.write("<h1>Out with the old - in with the new!</h1>");
      document.close();
    }
  </script>
</head>
<body onload="newContent();">
  <p>Some original document content.</p>
</body>
</html>
```

## Notes

Writing to a document that has already loaded without calling `document.open()` will automatically
call `document.open`. Once you have finished writing, it is recommended to call `document.close()` to
tell the browser to finish loading the page. The text you write is parsed into the document's
structure model. In the example above, the h1 element becomes a node in the document.

If the `document.write()` call is embedded within an inlined HTML `<script>` tag, then it will
not call `document.open()`. For example:

```html
<script>
  document.write("<h1>Main title</h1>")
</script>
```

!!! warn "Note"
    `document.write` and `document.writeln` do not work in XHTML documents (you'll get a "Operation
    is not supported" `[NS_ERROR_DOM_NOT_SUPPORTED_ERR]` error in the error console). This happens
    when opening a local file with the `.xhtml` file extension or for any document served with an
    `application/xhtml+xml` MIME type. More information is available in the W3C XHTML FAQ.

!!! warn "Note"
    `document.write` in deferred or asynchronous scripts will be ignored, and you'll get a message
    like "A call to `document.write()` from an asynchronously-loaded external script was ignored" in
    the error console.

!!! warn "Note"
    In Edge only, calling `document.write` more than once in an `<iframe>` causes the error SCRIPT70:
    Permission denied.

!!! warn "Note"
    Starting in 55, Chrome will not execute `<script>` elements injected via `document.write()` in
    case of an HTTP cache miss for users on a 2G connection. See here for a list of the conditions
    that need to be met for this to be true.
