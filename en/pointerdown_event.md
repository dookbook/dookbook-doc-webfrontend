TOPICS: onpointerdown
        pointerdown
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointerdown` Event

The `GlobalEventHandlers` event handler **`onpointerdown`** is used to specify the event handler for
the **`pointerdown`** event, which is fired when the pointing device is initially pressed. This event
can be sent to `Window`, [`Document`](/en/webfrontend/Document), and
[`Element`](/en/webfrontend/Element) objects.

This is functionally equivalent to the `mousedown` event when generated due to user activity with a
mouse or mouse-compatible device. If the `pointerdown` event isn't canceled through a call to
`preventDefault()`, most user agents will fire a `mousedown` event, so that sites not using pointer
events will work.

You can also use `addEventListener()` to add a listener for `pointerdown` events.

## Syntax

```javascript
target.onpointerdown = downHandler;

var downHandler = target.onpointerdown;
```

A `Function` to handle the `pointerdown` event for the target [`Element`](/en/webfrontend/Element),
[`Document`](/en/webfrontend/Document), or `Window`. It receives as input the `PointerEvent`
describing the pointerdown event.

## Example

This example demonstrates how to watch for and act upon `pointerdown` events using `onpointerdown`.
You could also use `addEventListener()`, of course.

First, let's look at the JavaScript code that handles the `pointerdown` event.

```javascript
var targetBox = document.getElementById("target");

targetBox.onpointerdown = handleDown;

function handleDown(evt) {
  var action;

  switch(evt.pointerType) {
    case "mouse":
      action = "clicking";
      break;
    case "pen":
      action = "tapping";
      break;
    case "touch":
      action = "touching";
      break;
    default:
      action = "interacting with";
      break;
  }

  targetBox.innerHTML = "<strong>Thanks for " + action + " me!</strong>";
  evt.preventDefault();
}
```

This simply uses `onpointerdown` to establish the function `handleDown()` as the event handler for
pointer down events.

The `handleDown()` function, in turn, looks at the value of `pointerType` to determine what kind of
pointing device was used, then uses that information to customize a string to replace the contents
of the target box.

Then the event's `preventDefault()` method is called to ensure that the `mousedown` event isn't
triggered, potentially causing events to be handled twice if we had a handler for those events in
case Pointer Event support is missing.

We also have a handler for `pointerup` events:

```javascript
targetBox.onpointerup = handleUp;

function handleUp(evt) {
  targetBox.innerHTML = "Tap me, click me, or touch me!";
  evt.preventDefault();
}
```

This code's job is to just restore the original text into the target box after the user's interaction
with the element ends (for example, when they release the mouse button, or when they lift the stylus
or finger from the screen).

In addition, the event's `preventDefault()` method is called to ensure that the mouseup event isn't
triggered unnecessarily.

The HTML is extremely simple:

```html
<div id="target">
  Tap me, click me, or touch me!
</div>
```

The CSS simply sets up the appearance of the target, and doesn't affect its functionality at all.

```css
#target {
  width: 400px;
  height: 30px;
  text-align: center;
  font: 16px "Open Sans", "Helvetica", sans-serif;
  color: white;
  background-color: blue;
  border: 2px solid darkblue;
  cursor: pointer;
  user-select: none;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
}
```
