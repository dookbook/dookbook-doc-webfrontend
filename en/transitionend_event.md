TOPICS: ontransitionend
        transitionend
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `transitionend` Event

The **`ontransitionend`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that
processes **`transitionend`** events.

The **`transitionend`** event is sent to when a CSS transition completes.

!!! warn ""
    If the transition is removed from its target node before the transition completes execution,
    the `transitionend` event won't be generated. One way this can happen is by changing the value
    of the `transition-property` attribute which applies to the target. Another is if the `display`
    attribute is set to `"none"`.

## Syntax

```javascript
var transitionEndHandler = target.ontransitionend;

target.ontransitionend = Function
```

A `Function` to be called when a `transitionend` event occurs indicating that a CSS `transition` has
completed on the `target`, where the target object is an HTML element (`HTMLElement`), document
(`Document`), or window (`Window`). The function receives as input a single parameter: a `TransitionEvent`
object describing the event which occurred; the event's `TransitionEvent.elapsedTime` property's
value should be the same as the value of `transition-duration`.

!!! warn ""
    `elapsedTime` does not include time prior to the `transition` effect beginning; that means that
    the value of `transition-delay` doesn't affect the value of `elapsedTime`, which is zero until
    the delay period ends and the animation begins.

## Example

In this example, we use the `transitionrun` and `transitionend` events to detect when the `transition`
begins and ends, to cause a text update to occur during the `transition`. This could also be used to
trigger animations or other effects, to allow chaining of reactions.

This simply creates a [`<div>`](/en/webfrontend/<div>) which we'll style with CSS below to make
into a box that resizes and changes color and such.

```html
<div class="box"></div>
```

The CSS below styles the box and applies a `transition` effect which makes the box's color and size
change, and causes the box to rotate, while the mouse cursor hovers over it.

```css
.box {
  margin-left: 70px;
  margin-top: 30px;
  border-style: solid;
  border-width: 1px;
  display: block;
  width: 100px;
  height: 100px;
  background-color: #0000FF;
  color: #FFFFFF;
  padding: 20px;
  font: bold 1.6em "Helvetica", "Arial", sans-serif;
  transition: width 2s, height 2s, background-color 2s, transform 2s, color 2s;
}

.box:hover {
  background-color: #FFCCCC;
  color: #000000;
  width: 200px;
  height: 200px;
  transform: rotate(180deg);
}
```

Next, we need to establish our event handlers to change the text content of the box when the
`transition` begins and ends.

```javascript
let box = document.querySelector(".box");
box.ontransitionrun = function(event) {
  box.innerHTML = "Zooming...";
}
box.ontransitionend = function(event) {
  box.innerHTML = "Done!";
}
```
