TOPICS: oncanplaythrough
        canplaythrough
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `canplaythrough` Event

The **`oncanplaythrough`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for
processing `canplaythrough` events.

The `canplaythrough` event is fired when the user agent can play the media and estimates that
enough data has been loaded to play the media up to its end without having to stop for further
buffering of content.

## Syntax

```javascript
element.oncanplaythrough = handlerFunction;
var handlerFunction = element.oncanplaythrough;
```

`handlerFunction` is either `null` or a JavaScript function specifying the handler for the event.
