TOPICS: oncuechange
        cuechange
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `cuechange` Event

The **`oncuechange`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for
processing `cuechange` events.

The `cuechange` event fires when a `TextTrack` has changed the currently displaying cues. The event
is sent to both the `TextTrack` and to the `<track>` element the track is being presented by, if any;
in the latter case, its handler is on an `HTMLTrackElement` object.

## Syntax

```javascript
element.oncuechange = handlerFunction;
var handlerFunction = element.oncuechange;
```

`handlerFunction` is either `null` or a JavaScript function specifying the handler for the event.
