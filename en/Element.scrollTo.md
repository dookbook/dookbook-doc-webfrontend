TOPICS: Element.scrollTo
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.scrollTo()`

The **`scrollTo()`** method of the `Element` interface scrolls to a particular set of coordinates
inside a given element.

## Syntax

```javascript
element.scrollTo(x-coord, y-coord)
element.scrollTo(options)
```

- `x-coord` is the pixel along the horizontal axis of the element that you want displayed in the
upper left.
- `y-coord` is the pixel along the vertical axis of the element that you want displayed in the
upper left.

or

- `options` is a `ScrollToOptions` dictionary.

## Examples

```javascript
element.scrollTo(0, 1000);
```

Using `options`:

```javascript
element.scrollTo({
  top: 100,
  left: 100,
  behavior: 'smooth'
});
```
