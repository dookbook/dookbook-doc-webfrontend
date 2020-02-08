TOPICS: onfullscreenchange
        fullscreenchange
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `fullscreenchange` Event

The `Document` interface's **`onfullscreenchange`** property is an event handler for the
**`fullscreenchange`** event that is fired immediately before a document transitions into or out of
full-screen mode.

## Syntax

```javascript
targetDocument.onfullscreenchange = fullscreenChangeHandler;
```

An event handler which is invoked whenever the document receives a `fullscreenchange` event,
indicating that the document is transitioning into or out of full-screen mode.

## Usage notes

The `fullscreenchange` event does not directly specify whether the transition is into or out of
full-screen mode, so your event handler should look at the value of `Document.fullscreenElement`.
If it's `null`, the event indicates a transition out of full-screen mode. Otherwise, the specified
element is about to take over the screen.

## Example

```javascript
document.onfullscreenchange = function ( event ) {
  console.log("FULL SCREEN CHANGE")
};
document.documentElement.onclick = function () {
  // requestFullscreen() must be in an event handler or it will fail
  document.documentElement.requestFullscreen();
}
```
