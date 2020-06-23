TOPICS: touch-action property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `touch-action`

The CSS **`touch-action`** property is used to set **how the touch screen user manipulates the area
of the element** (for example, the built-in zoom function of the browser).

By default, pan (scroll) and zoom gestures are handled exclusively by the browser. Applications
using `Pointer_events` will receive a
`pointercancel` event. By explicitly specifying which gestures the browser should handle, the
application can provide its own behavior for the remaining gestures in the `pointermove` and `pointerup`
listeners. Applications that use `Touch_events` disable the browser from handling gestures by calling
`preventDefault()`, but touch operations should also be used to ensure that the browser understands
the application’s intent before calling any event listeners.

When the gesture begins, the browser intersects the touch action value of the touched element and
all of its ancestors until a touch action value that implements the gesture (in other words, the
first contains the scroll element). This means that in practice, touch actions are generally only
applicable to a single element with some custom behavior, without the need to explicitly specify
touch actions on any descendants of that element. After the gesture starts, the change of the touch
action value will not have any effect on the current gesture behavior.

## Property value

**`touch-action`** property can be specified as:

- Any of the keywords **`auto`**, **`none`**, **`manipulation`**, or
- Zero or any keyword **`pan-x`**, **`pan-left`**, **`pan-right`**, plus zero or any keyword
**`pan-y`**, **`pan-up`**, **`pan-down`**, plus optional keyword **`pinch-zoom`**.

| Property Value | Description |
| :--- | :--- |
| **`auto`** | When a touch event occurs on an element, the browser decides which operations to perform, such as smoothing and zooming the viewport. |
| **`none`** | When a touch event occurs on an element, no operation is performed. |
| **`pan-x`** | Enable **one-finger horizontal pan gesture**. Can be used in combination with **`pan-y`**, **`pan-up`**, **`pan-down`** and/or **`pinch-zoom`**. |
| **`pan-y`** | Enable **single finger vertical pan gesture**. Can be used in combination with **`pan-x`**, **`pan-left`**, **`pan-right`** and/or **`pinch-zoom`**. |
| **`manipulation`** | The browser **only allows scrolling** and **continuous zooming**. Any other behavior supported by the `auto` value is not supported. **Enable panning** and **zoom out zoom gestures**, but disable other non-standard gestures, such as double-tap to zoom. Disabling the double-click zoom function can reduce the need for the browser to delay generating a click event when the user taps the screen. This is an alias for "`pan-x` `pan-y` `pinch-zoom`" (it still works for compatibility). |
| **`pan-left`**, **`pan-right`**, **`pan-up`**, **`pan-down`** | Enable one-finger gestures that start scrolling in the specified direction. Once scrolling begins, the direction may still be reversed. Please note that scrolling "pan-up" means that the user is dragging their finger down onto the screen surface, and likewise **`pan-left`** means the user dragging their finger to the right. Multiple directions can be combined unless there is a simpler representation (for example, "`pan-left` `pan-right`" is invalid, because "`pan-x`" is simpler, and "`pan-left` `pan- down`" effective). |
| **`pinch-zoom`** | Enable multi-finger pan and zoom pages. This can be combined with any translation value. |

## Examples

The most common usage is to disable all gestures on the element (and its non-scrollable descendants)
to use the drag-and-drop and zoom behaviors provided by itself (such as a map or game surface).

```css
#map {
  touch-action: none;
}
```

Another common mode is to use pointer events to handle horizontally rotating image carousels, but do
not want to interfere with the vertical scrolling or zooming of the web page.

```css
.image-carousel {
  width: 100%;
  height: 150px;
  touch-action: pan-y pinch-zoom;
}
```

**Touch action** is also often used to completely resolve the delay of click events caused by
support for double-click zoom gestures.

```css
html {
  touch-action: manipulation;
}
```
