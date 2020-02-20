TOPICS: :root
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:root`

The **`:root`** CSS pseudo-class matches the root element of a tree representing the document.
In HTML, `:root` represents the [`<html>`](/en/webfrontend/<html>) element and is identical to the
selector `html`, except that its specificity is higher.

## Example

`:root` can be useful for declaring global CSS variables:

```css
:root {
  background: #ff0;
}
```
