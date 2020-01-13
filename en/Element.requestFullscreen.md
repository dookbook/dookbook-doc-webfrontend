TOPICS: Element.requestFullscreen
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.requestFullscreen()`

The **`Element.requestFullscreen()`** method issues an asynchronous request to make the element be
displayed in full-screen mode.

It's not guaranteed that the element will be put into full screen mode. If permission to enter full
screen mode is granted, the returned `Promise` will resolve and the element will receive a
`fullscreenchange` event to let it know that it's now in full screen mode. If permission is denied,
the promise is rejected and the element receives a `fullscreenerror` event instead. If the element
has been detached from the original document, then the document receives these events instead.

Earlier implementations of the Fullscreen API would always send these events to the document rather
than the element, and you may need to be able to handle that situation. Check Browser compatibility
in fullscreen for specifics on when each browser made this change.

!!! warn "Note"
    This method must be called while responding to a user interaction or a device
    orientation change; otherwise it will fail.

## Syntax

```javascript
var Promise = Element.requestFullscreen(options);
```

| parameter | Description |
| :-- | :-- |
| `options` Optional | A `FullscreenOptions` object  providing options that control the behavior of the transition to full-screen mode. Currently, the only option is `navigationUI`, which controls whether or not to show navigation UI while the element is in full-screen mode. The default value is `"auto"`, which indicates that the browser should decide what to do. |

## Return value

A `Promise` which is resolved with a value of `undefined` when the transition to full screen is complete.

## Exceptions

Rather than throw a traditional exception, the `requestFullscreen()` procedure announces error
conditions by rejecting the Promise it has returned. The rejection handler receives one of the
following exception values:

`TypeError`

The `TypeError` exception may be delivered in any of the following situations:

- The document containing the element isn't fully active; that is, it's not the current active document.
- The element is not contained by a document.
- The element is not permitted to use the `"fullscreen"` feature, either because of Feature Policy
configuration or other access control features.
- The element and its document are the same node.

## Usage notes

### Compatible elements

An element that you wish to place into full-screen mode has to meet a small number of simple requirements:

- It must be one of the standard HTML elements or `<svg>` or `<math>`.
- It is not a `<dialog>` element.
- It must either be located within the top-level document or in an `<iframe>` which has the
`allowfullscreen` attribute applied to it.

Additionally, of course, the Feature Policy `"fullscreen"` permission must be granted.

### Detecting full-screen activation

You can determine whether or not your attempt to switch to full-screen mode is successful by using
the `Promise` returned by `requestFullscreen()`, as seen in the Example below.

To learn when other code has toggled full-screen mode on and off, you should establish listeners for
the `fullscreenchange` event on the `Document`. It's also important to listen for `fullscreenchange`
to be aware when, for example, the user manually toggles full-screen mode, or when the user switches
applications, causing your application to temporarily exit full-screen mode.

## Examples

This function toggles the first [`<video>`](/en/webfrontend/<video>) element found in the document
into and out of full-screen mode.

```javascript
function toggleFullscreen() {
  let elem = document.querySelector("video");

  if (!document.fullscreenElement) {
    elem.requestFullscreen().catch(err => {
      alert(`Error attempting to enable full-screen mode: ${err.message} (${err.name})`);
    });
  } else {
    document.exitFullscreen();
  }
}
```

If the document isn't already in full-screen mode—detected by looking to see if [`document.fullscreenElement`](/en/webfrontend/document.fullscreenElement)
has a value—we call the video's `requestFullscreen()` method. We don't need to do anything special
if successful, but if the request fails, our promise's `catch()` handler presents an alert with an
appropriate error message.

If, on the other hand, full-screen mode is already in effect, we call [`document.exitFullscreen()`](/en/webfrontend/document.exitFullscreen)
to disable full-screen mode.
