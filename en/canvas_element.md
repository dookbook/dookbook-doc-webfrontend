TOPICS: <canvas>

# `<canvas>`

Use the **HTML `<canvas>` element** with either the canvas scripting API
or the WebGL API to draw graphics and animations.

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *embedded content*, *palpable content*.|
| **Permitted content** | Transparent but with no interactive content descendants except for [`<a>`](/en/webfrontend/<a>) elements, [`<button>`](/en/webfrontend/<button>) elements, [`<input>`](/en/webfrontend/<input>) elements whose type attribute is checkbox, radio, or button. |
| **Tag omission**| None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLCanvasElement`** |

## Attributes

This element's attributes include the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `height` | The height of the coordinate space in CSS pixels. Defaults to 150. |
| `moz-opaque` | Lets the canvas know whether or not translucency will be a factor. If the canvas knows there's no translucency, painting performance can be optimized. This is only supported by Mozilla-based browsers; use the standardized `canvas.getContext('2d', { alpha: false })` instead. |
| `width` | The width of the coordinate space in CSS pixels. Defaults to 300. |

## Usage Notes

### Alternative Content

You may (and should) provide alternate content inside the `<canvas>` block. That content will be
rendered both on older browsers that don't support canvas and in browsers with JavaScript disabled.

### Required `</canvas>` tag

Unlike the [`<img>`](/en/webfrontend/<img>) element, the `<canvas>` element requires the
closing tag (`</canvas>`).

### Sizing the canvas using CSS versus HTML

The displayed size of the canvas can be changed using CSS, but if you do this the image is scaled
during rendering to fit the styled size, which can make the final graphics rendering end up being distorted.

It is better to specify your canvas dimensions by setting the `width` and `height` attributes
directly on the `<canvas>` elements, either directly in the HTML or by using JavaScript.

### Maximum canvas size

The maximum size of a `<canvas>` element is very large, but the exact size depends on the browser.
The following is some data we've collected from various tests and other sources (e.g. [Stack Overflow](https://stackoverflow.com/questions/6081483/maximum-size-of-a-canvas-element)):

| Browser | Maximum height | Maximum width | Maximum area |
| :-- | :-- | :-- | :-- |
| Chrome | 32,767 pixels | 32,767 pixels | 268,435,456 pixels (i.e., 16,384 x 16,384) |
| Firefox | 32,767 pixels | 32,767 pixels | 472,907,776 pixels (i.e., 22,528 x 20,992) |
| Safari  | 32,767 pixels | 32,767 pixels | 268,435,456 pixels (i.e., 16,384 x 16,384) |
| IE | 8,192 pixels | 8,192 pixels | ? |

!!! warn "Don't try this at home"
    Note: Exceeding the maximum dimensions or area renders the canvas
    unusable — drawing commands will not work.

## Examples

This code snippet adds a canvas element to your HTML document. A fallback text is provided if a
browser is unable to render the canvas, or if can't read a canvas. Providing a useful fallback text
or sub DOM helps to make the the canvas more accessible.

```html
<canvas id="canvas" width="300" height="300">
  An alternative text describing what your canvas displays.
</canvas>
```

Then in the JavaScript code, call `HTMLCanvasElement.getContext()` to get a drawing
context and start drawing onto the canvas:

```html
<script>
var canvas = document.getElementById('canvas');
var ctx = canvas.getContext('2d');
ctx.fillStyle = 'green';
ctx.fillRect(10, 10, 100, 100);
</script>
```

### Opaque canvas

If your canvas does not use transparency, you can tell the browser that your canvas is opaque,
this will be used internally to optimize rendering. To do this,
set `alpha` to `false` when getting the drawing context:

```html
<script>
var canvas = document.getElementById('canvas');
var ctx = canvas.getContext('2d', { alpha: false });
</script>
```

Before the alpha option was [standardized](https://wiki.whatwg.org/wiki/CanvasOpaque),
you could use the `moz-opaque`   attribute on the canvas tag. However, this only works in
Mozilla-based rendering engines and should be avoided; check [bug 878155](https://bugzilla.mozilla.org/show_bug.cgi?id=878155)
to track when this attribute will be removed.

```html
<canvas id="myCanvas" moz-opaque></canvas>
```

## Accessibility Concerns

The `<canvas>` element on its own is just a bitmap and does not provide information about any drawn
objects. Canvas content is not exposed to accessibility tools as semantic HTML is. In general,
you should avoid using canvas in an accessible website or app.
The following guides can help to make it more accessible.

- [MDN Hit regions and accessability](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Hit_regions_and_accessibility)
- [Canvas accessibility use cases](https://www.w3.org/WAI/PF/HTML/wiki/Canvas_Accessibility_Use_Cases)
- [Canvas element accessibility issues](https://www.w3.org/html/wg/wiki/AddedElementCanvas)
- [HTML5 Canvas Accessibility in Firefox 13 – by Steve Faulkner](http://www.paciellogroup.com/blog/2012/06/html5-canvas-accessibility-in-firefox-13/)
- [Best practices for interactive canvas elements](https://html.spec.whatwg.org/multipage/scripting.html#best-practices)
