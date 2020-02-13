TOPICS: onmouseenter
        mouseenter
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `mouseenter` Event

The **`onmouseenter`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for
processing **`mouseenter`** events.

The **`mouseenter`** event is fired when a pointing device (usually a mouse) is moved over the element
that has the listener attached.

## Syntax

```javascript
element.onmouseenter = handlerFunction;
var handlerFunction = element.onmouseenter;
```

`handlerFunction` is either `null` or a JavaScript function specifying the handler for the event.
