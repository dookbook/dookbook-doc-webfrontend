TOPICS: onmouseleave
        mouseleave
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `mouseleave` Event

The **`onmouseleave`** property of the `GlobalEventHandlers` mixin is the `EventHandler` for
processing `mouseleave` events.

The `mouseleave` event is fired when a pointing device (usually a mouse) is moved off the element
that has the listener attached.

## Syntax

```javascript
element.onmouseleave = handlerFunction;
var handlerFunction = element.onmouseleave;
```

`handlerFunction` is either `null` or a JavaScript function specifying the handler for the event.

## Examples

```html
<img onmouseenter="bigImg(this)" onmouseleave="normalImg(this)" border="0" src="smiley.gif" alt="Smiley" width="32" height="32">
<p>
The bigImg () function is triggered when the user moves the mouse pointer over the image.</p>
<p>
The normalImg () function is triggered when the user moves the mouse pointer out of the image.</p>
<script>
function bigImg(x) {
  x.style.height = "64px";
  x.style.width = "64px";
}
function normalImg(x) {
  x.style.height = "32px";
  x.style.width = "32px";
}
</script>
```
