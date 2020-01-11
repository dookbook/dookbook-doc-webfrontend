TOPICS: Element.setPointerCapture
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.setPointerCapture()`

The **`setPointerCapture()`** method of the `Element` interface is used to designate a specific
element as the capture target of future pointer events. Subsequent events for the pointer will be
targeted at the capture element until capture is released (via [`Element.releasePointerCapture()`](/en/webfrontend/Element.releasePointerCapture)).

!!! warn ""
    When pointer capture is set, `pointerover`, `pointerout` `pointerenter`, and `pointerleave` events
    are only generated when crossing the boundary of the capture target. This has the effect of suppressing
    these events on all other elements.

## Overview of pointer capture

Pointer capture allows events for a particular pointer event (`PointerEvent`) to be re-targeted to a
particular element instead of the normal (or hit test) target at a pointer's location. This can be used
to ensure that an element continues to receive pointer events even if the pointer device's contact
moves off the element (such as by scrolling or panning).

## Syntax

```javascript
targetElement.setPointerCapture(pointerId);
```

| parameter | Description |
| :-- | :-- |
| `pointerId` | The `pointerId` of a `PointerEvent` object.|

**Return value**: This method returns `undefined`.

## Exceptions

| Exception | Explanation |
| `InvalidPointerId` | pointerId does not match any of the active pointers.|

## Examples

This example sets pointer capture on a [`<div>`](/en/webfrontend/<div>) when you press down on it.
This lets you slide the element horizontally, even when you pointer moves outside of its boundaries.

```html
<div id="slider">SLIDE ME</div>
```

```css
div {
  width: 140px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #fbe;
}
```

```javascript
function beginSliding(e) {
  slider.onpointermove = slide;
  slider.setPointerCapture(e.pointerId);
}

function stopSliding(e) {
  slider.onpointermove = null;
  slider.releasePointerCapture(e.pointerId);
}

function slide(e) {
  slider.style.transform = `translate(${e.clientX - 70}px)`;
}

const slider = document.getElementById('slider');

slider.onpointerdown = beginSliding;
slider.onpointerup = stopSliding;
```
