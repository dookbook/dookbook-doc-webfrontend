TOPICS: onended
        ended
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `ended` Event

The **`onended`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for processing
**`ended`** events.

The `ended` event is fired when playback has stopped because the end of the media was reached.

## Syntax

```javascript
element.onended = handlerFunction;
var handlerFunction = element.onended;
```

`handlerFunction` is either `null` or a JavaScript function specifying the handler for the event.
