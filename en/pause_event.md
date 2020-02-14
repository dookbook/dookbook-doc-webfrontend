TOPICS: onpause
        pause
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pause` Event

The **`onpause`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for processing
**`pause`** events.

The **`pause`** event is fired when media playback has been paused.

## Syntax

```javascript
element.onpause = handlerFunction;
var handlerFunction = element.onpause;
```

`handlerFunction` should be either `null` or a JavaScript function specifying the handler for the event.
