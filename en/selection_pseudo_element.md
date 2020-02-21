TOPICS: ::selection
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Element: `::selection`

The **`::selection`** CSS pseudo-element
**applies styles to the part of a document that has been highlighted by the user**
(such as *clicking* and *dragging* the mouse across text).

## Allowable properties

Only certain CSS properties can be used with `::selection`:

- `color`
- `background-color`
- `cursor`
- `caret-color`
- `outline` and its longhands
- `text-decoration` and its associated properties
- `text-emphasis-color`
- `text-shadow`

!!! error ""
    In particular, `background-image` is ignored.

## Example

```html
This text has special styles when you highlight it.
<p>Also try selecting text in this paragraph.</p>
```

```css
/* Make selected text gold on a red background */
::selection {
  color: gold;
  background-color: red;
}

/* Make selected text in a paragraph white on a blue background */
p::selection {
  color: white;
  background-color: blue;
}
```
