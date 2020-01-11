TOPICS: Element.getBoundingClientRect
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getBoundingClientRect()`

The **`Element.getBoundingClientRect()`** method returns the size of an element and its position
relative to the viewport.

## Syntax

```javascript
domRect = element.getBoundingClientRect();
```

The returned value is a `DOMRect` object which is the union of the rectangles returned by
`getClientRects()` for the element, i.e., the CSS border-boxes associated with the element. The
result is the smallest rectangle which contains the entire element, with read-only `left`, `top`,
`right`, `bottom`, `x`, `y`, `width`, and `height` properties describing the overall border-box in
pixels. Properties other than `width` and `height` are relative to the top-left of the viewport.

Empty border-boxes are completely ignored. If all the element's border-boxes are empty, then a
rectangle is returned with a `width` and `height` of zero and where the `top` and `left` are the
top-left of the `border-box` for the first CSS box (in content order) for the element.

![rect](/media/webfrontend__rect.png)

The amount of scrolling that has been done of the viewport area (or any other scrollable element)
is taken into account when computing the bounding rectangle. This means that the rectangle's boundary
edges (`top`, `right`, `bottom`, `left`) change their values every time the scrolling position
changes (because their values are relative to the viewport and not absolute).

If you need the bounding rectangle relative to the top-left corner of the document, just add the
current scrolling position to the `top` and `left` properties (these can be obtained using
`window.scrollX` and `window.scrollY`) to get a bounding rectangle which is independent from
the current scrolling position.

### Cross-browser fallback

Scripts requiring high cross-browser compatibility can use window.pageXOffset and `window.pageYOffset`
instead of `window.scrollX` and `window.scrollY`. Scripts without access to these properties can use
code like this:

```javascript
// For scrollX
(((t = document.documentElement) || (t = document.body.parentNode))
  && typeof t.scrollLeft == 'number' ? t : document.body).scrollLeft
// For scrollY
(((t = document.documentElement) || (t = document.body.parentNode))
  && typeof t.scrollTop == 'number' ? t : document.body).scrollTop
```

## Examples

```javascript
// rect is a DOMRect object with eight properties: left, top, right, bottom, x, y, width, height
var rect = obj.getBoundingClientRect();
```
