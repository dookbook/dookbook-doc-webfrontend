TOPICS: :left
        :right

# CSS Pseudo-Class: `:left`

The **`:left`** CSS pseudo-class, used with the **`@page`** at-rule, represents all left-hand pages of
a printed document.

The **`:right`** CSS pseudo-class, used with the **`@page`** at-rule, represents all right-hand pages of
a printed document.

Whether a given page is "left" or "right" is determined by the major writing direction of the
document. For example, if the first page has a major writing direction of left-to-right then it
will be a `:right` page; if it has a major writing direction of right-to-left then it will be
a `:left` page.

!!! warn "Note"
    This pseudo-class can be used to change only the `margin`, `padding`, `border`, and `background`
    properties of the page box. All other properties will be ignored, and only the page box, not the
    document content on the page, will be affected.

## Example

```css
/* Selects any left-hand pages when printing */
@page :left {
  margin: 2in 3in;
}
```

```css
@page :right {
  margin: 2in 3in;
}
```
