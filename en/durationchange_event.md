TOPICS: ondurationchange
        durationchange
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `durationchange` Event

The **`ondurationchange`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for
processing **`durationchange`** events.

The `durationchange` event is fired when the `duration` attribute has been updated.

## Syntax

```javascript
element.ondurationchange = handlerFunction;
var handlerFunction = element.ondurationchange;
```

`handlerFunction` is either `null` or a JavaScript function specifying the handler for the event.
