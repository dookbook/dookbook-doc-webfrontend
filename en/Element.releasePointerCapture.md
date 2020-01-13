TOPICS: Element.releasePointerCapture
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.releasePointerCapture()`

The **`releasePointerCapture()`** method of the Element interface releases (stops) pointer capture
that was previously set for a specific (PointerEvent) pointer.

See the [`Element.setPointerCapture()`](/en/webfrontend/Element.setPointerCapture) method for a
description of pointer capture and how to set it for a particular element.

## Syntax

```javascript
targetElement.releasePointerCapture(pointerId);
```

| parameter | Description |
| :-- | :-- |
| `pointerId` | The `pointerId` of a `PointerEvent` object. |

**Return value**: This method returns `undefined`.

## Exceptions

| Exception | Explanation |
| :-- | :-- |
| `InvalidPointerId` | pointerId does not match any of the active pointers. |

## Example

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
