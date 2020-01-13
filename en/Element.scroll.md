TOPICS: Element.scroll
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.scroll()`

The **`scroll()`** method of the `Element` interface scrolls the element to a particular set of
coordinates inside a given element.

## Syntax

```javascript
element.scroll(x-coord, y-coord)
element.scroll(options)
```

- `x-coord` is the pixel along the horizontal axis of the element that you want displayed in the
upper left.
- `y-coord` is the pixel along the vertical axis of the element that you want displayed in the
upper left.

or

- `options` is a `ScrollToOptions` dictionary.

## Examples

```javascript
// Put the 1000th vertical pixel at the top of the element
element.scroll(0, 1000);
```

Using `options`:

```javascript
element.scroll({
  top: 100,
  left: 100,
  behavior: 'smooth'
});
```
