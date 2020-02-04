TOPICS: onanimationend
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onanimationend`

The `onanimationend` property of the `GlobalEventHandlers` mixin is the `EventHandler` for processing
`animationend` events.

The `animationend` event fires when a CSS animation reaches the end of its active period (which is
calculated as `animation-duration * animation-iteration-count`) + `animation-delay`).

## Syntax

```javascript
var animEndHandler = target.onanimationend;

target.onanimationend = Function
```

A `Function` to be called when an `animationend` event occurs indicating that a CSS animation has
begun on the `target`, where the target object is an HTML element (`HTMLElement`), document (`Document`),
or window (`Window`). The function receives as input a single parameter: an `AnimationEvent` object
describing the event which occurred.

## Example

Leaving out some bits of the CSS that don't matter for the discussion here, let's take a look at
the styles for the box that we're animating. First is the box itself. We set its size, position,
color, and layout. Note that there's nothing there about animation. That's because we don't want
the box to start animating right away. We'll add the `animation` style later to start animating the box.

```css
#box {
  width: var(--boxwidth);
  height: var(--boxwidth);
  left: 0;
  top: 0;
  border: 1px solid #7788FF;
  margin: 0;
  position: relative;
  background-color: #2233FF;
  display: flex;
  justify-content: center;
}
```

The animation sequence is described next. First, the `"slideAnimation"` class, which establishes the
`animation` that will cause the box to move over the course of five seconds, one time, using the
`"slideBox"` keyframe set. The keyframes are defined next; they describe an `animation` which causes
the box to migrate from the top-left corner of the container to the bottom-right corner.

```css
.slideAnimation {
  animation: 5s ease-in-out 0s 1 slideBox;
}

@keyframes slideBox {
  from {
    left:0;
    top:0;
  }
  to {
    left:calc(100% - var(--boxwidth));
    top:calc(100% - var(--boxwidth))
  }
}
```

Since the CSS describes the animation but doesn't connect it to the box, we'll need some JavaScript
code to do that.  We'll get to that shortly.

JavaScript content

Before we get to the animation code, we define a function which logs information to a box on the
user's screen. We'll use this to show information about the events we receive. Note the use of `AnimationEvent.animationName`
and `AnimationEvent.elapsedTime` to get information about the event which occurred.

```javascript
function log(msg, event) {
  let logBox = document.getElementById("log");

  logBox.innerHTML += msg;

  if (event) {
    logBox.innerHTML += " <code>"+ event.animationName +
        "</code> at time " + event.elapsedTime.toFixed(2) +
        " seconds.";
  }

  logBox.innerHTML += "\n";
};
```

Then we set up the event handlers for the `animationstart` and `animationend` events:

```javascript
let box = document.getElementById("box");

box.onanimationstart = function(event) {
  log("Animation started", event);
}

box.onanimationend = function(event) {
  log("Animation stopped", event);
};
```

Finally, we set up a handler for a click on the button that runs the animation:

```javascript
document.getElementById("play").addEventListener("click", function(event) {
  document.getElementById("box").className = "slideAnimation";
  event.target.style.display = "none";
}, false);
```

This sets the class of the box we want to animate to the class that contains the `animation`
description, then hides the play button because this example will only run the animation once.
For information about why, and how to support running an animation more than once, see Run an
animation again in CSS Animations tips and tricks.
