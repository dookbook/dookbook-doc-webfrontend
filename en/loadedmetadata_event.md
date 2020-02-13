TOPICS: onloadedmetadata
        loadedmetadata
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `loadedmetadata` Event

The **`onloadedmetadata`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for
processing **`loadedmetadata`** events.

The **`loadedmetadata`** event is fired when the metadata has been loaded.

## Syntax

```javascript
element.onloadedmetadata = handlerFunction;
var handlerFunction = element.onloadedmetadata;
```

`handlerFunction` should be either `null` or a JavaScript function specifying the handler for the event.
