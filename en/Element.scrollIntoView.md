TOPICS: Element.scrollIntoView
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.scrollIntoView()`

The `Element` interface's **`scrollIntoView()`** method scrolls the element's parent container such
that the element on which `scrollIntoView()` is called is visible to the user

## Syntax

```javascript
element.scrollIntoView();
element.scrollIntoView(alignToTop); // Boolean parameter
element.scrollIntoView(scrollIntoViewOptions); // Object parameter
```

| parameter | Description |
| :-- | :-- |
| `alignToTop` Optional | Is a `Boolean` value:<br><br>1. If `true`, the top of the element will be aligned to the top of the visible area of the scrollable ancestor. Corresponds to `scrollIntoViewOptions: {block: "start", inline: "nearest"}`. This is the default value.<br><br>2. If `false`, the bottom of the element will be aligned to the bottom of the visible area of the scrollable ancestor. Corresponds to `scrollIntoViewOptions: {block: "end", inline: "nearest"}`.
| `scrollIntoViewOptions` Optional | Is an Object with the following properties:<br><br>1. **`behavior`** Optional<br>Defines the transition animation.<br>One of `"auto"` or `"smooth"`. Defaults to `"auto"`.<br><br>2. **`block`** Optional<br>Defines vertical alignment.<br>One of `"start"`, `"center"`, `"end"`, or `"nearest"`. Defaults to `"start"`.<br><br>3. **`inline`** Optional<br>Defines horizontal alignment.<br>One of `"start"`, `"center"`, `"end"`, or `"nearest"`. Defaults to `"nearest"`. |

## Examples

```javascript
var element = document.getElementById("box");

element.scrollIntoView();
element.scrollIntoView(false);
element.scrollIntoView({block: "end"});
element.scrollIntoView({behavior: "smooth", block: "end", inline: "nearest"});
```

## Notes

The element may not be scrolled completely to the top or bottom depending on the layout of other elements.
