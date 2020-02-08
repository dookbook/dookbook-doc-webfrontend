TOPICS: onfullscreenerror
        fullscreenerror
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `fullscreenerror` Event

The **`Document.onfullscreenerror`** property is an event handler for the **`fullscreenerror`** event
that is sent to the  document when it fails to transition into full-screen mode after a prior call
to `Element.requestFullscreen()`.

## Syntax

```javascript
targetDocument.onfullscreenerror = fullscreenErrorHandler;
```

An event handler for the `fullscreenerror` event.

## Example

This example attempts to call `requestFullscreen()` outside of an event handler. Since `requestFullscreen()`
can only be called in response to user action, for security reasons, this will fail, causing the
`fullscreenerror` to be sent to the document.

```javascript
document.onfullscreenerror = function ( event ) {
  displayWarning("Unable to switch into full-screen mode.");
};

//....

document.documentElement.requestFullscreen();
```
