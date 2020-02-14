TOPICS: onplay
        play
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `play` Event

The **`onplay`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for processing
**`play`** events.

## Syntax

```javascript
element.onplay = handlerFunction;
var handlerFunction = element.onplay;
```

`handlerFunction` should be either `null` or a JavaScript function specifying the handler for the event.

## Example

This example shows two ways to use `onpointercancel` to handle an element's `pointercancel` events.

```html
<p>This example demonstrates how to assign an "onplay" event to a video element.</p>

<video controls onplay="alertPlay()">
  <source src="mov_bbb.mp4" type="video/mp4">
  <source src="mov_bbb.ogg" type="video/ogg">
  Your browser does not support HTML5 video.
</video>

<p>Video courtesy of <a href="http://www.bigbuckbunny.org/" target="_blank">Big Buck Bunny</a>.</p>

<script>
function alertPlay() {
  alert("The video has started to play.");
}
</script>
```
