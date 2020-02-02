TOPICS: Document.writeln
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.writeln()`

Writes a string of text followed by a newline character to a document.

## Syntax

```javascript
document.writeln(line);
```

| parameter | Description |
| :-- | :-- |
| `line` | is string containing a line of text. |

## Examples

```javascript
document.writeln("<p>enter password:</p>");
```

## Notes

`document.writeln` is the same as `document.write` but adds a newline.

!!! warn "Note"
    `document.writeln` (like `document.write`) does not work in XHTML documents (you'll get a
    "Operation is not supported" (`NS_ERROR_DOM_NOT_SUPPORTED_ERR`) error on the error console).
    This is the case if opening a local file with a `.xhtml` file extension or for any document
    served with an `application/xhtml+xml` MIME type. More information is available in the
    W3C XHTML FAQ.
