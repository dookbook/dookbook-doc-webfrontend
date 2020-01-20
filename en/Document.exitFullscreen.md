TOPICS: Document.exitFullscreen
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.exitFullscreen()`

The `Document` method **`exitFullscreen()`** requests that the element on this document which is
currently being presented in full-screen mode be taken out of full-screen mode, restoring the
previous state of the screen. This usually reverses the effects of a previous call to `Element.requestFullscreen()`.

The exception is if another element was already in full-screen mode when the current element was
placed into full-screen mode using `requestFullscreen()`. In that case, the previous full-screen
element is restored to full-screen status instead. In essence, a stack of full-screen elements is maintained.

## Syntax

```javascript
exitPromise = document.exitFullscreen();
```

**Return value**: A `Promise` which is resolved once the user agent has finished exiting full-screen
mode. If an error occurs while attempting to exit full-screen mode, the `catch()` handler for the
promise is called.

## Examples

This example causes the current document to toggle in and out of a full-screen presentation whenever
the mouse button is clicked within it.

```javascript
document.onclick = function (event) {
  if (document.fullscreenElement) {
    document.exitFullscreen()
      .then(() => console.log("Document Exited form Full screen mode"))
      .catch((err) => console.error(err))
  } else {
    document.documentElement.requestFullscreen()
  }
}
```

!!! warn "Note"
    For a more complete example, see the `Example` in `Element.requestFullscreen()`.
