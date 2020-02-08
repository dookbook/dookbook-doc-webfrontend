TOPICS: oncancel
        cancel
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `cancel` Event

The **`oncancel`** property of the `GlobalEventHandlers` mixin is an `EventHandler` for processing
`cancel` events sent to a [`<dialog>`](/en/webfrontend/<dialog>) element.

The `cancel` event fires when the user indicates a wish to dismiss a [`<dialog>`](/en/webfrontend/<dialog>).
This event handler prevents the event from bubbling, so any parent handlers are not notified of the event.

## Syntax

```javascript
target.oncancel = functionRef;
```

`functionRef` is a function name or a function expression. The function receives an `Event` object
as its sole argument.

Only one `oncancel` handler can be assigned to an object at a time. You may prefer to use the
`EventTarget.addEventListener()` method instead, since it's more flexible.
