TOPICS: Element.scrollBy
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.scrollBy()`

The **`scrollBy()`** method of the `Element` interface scrolls an element by the given amount.

## Syntax

```javascript
element.scrollBy(x-coord, y-coord);
element.scrollBy(options)
```

- `x-coord` is the horizontal pixel value that you want to scroll by.
- `y-coord` is the vertical pixel value that you want to scroll by.

or

- `options` is a `ScrollToOptions` dictionary.

## Examples

```javascript
// scroll an element
element.scrollBy(300, 300);
```

Using `options`:

```javascript
element.scrollBy({
  top: 100,
  left: 100,
  behavior: 'smooth'
});
```
