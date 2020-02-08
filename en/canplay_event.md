TOPICS: oncanplay
        canplay
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `canplay` Event

The **`oncanplay`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for
processing `canplay` events.

The `canplay` event is fired when the user agent can play the media, but estimates that not enough
data has been loaded to play the media up to its end without having to stop for further buffering
of content.

## Syntax

```javascript
element.oncanplay = handlerFunction;
var handlerFunction = element.oncanplay;
```

`handlerFunction` is either `null` or a JavaScript function specifying the handler for the event.
