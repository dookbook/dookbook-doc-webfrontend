TOPICS: :nth-child()
        :nth-last-child()
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:nth-child()`、`:nth-last-child()`

The **`:nth-child()`** CSS pseudo-class matches elements based on their position in a group of siblings.

The **`:nth-last-child()`** CSS pseudo-class matches elements based on their position among a group
of siblings, counting from the end.

## parameter

*n* can be a number, a keyword, or a formula.

## Example

```html
<p>The first paragraph.</p>
<p>The second paragraph.</p>
<p>The third paragraph.</p>
<p>The fourth paragraph.</p>
```

```css
p:nth-child(1) {
  background:#ff0000;
}

p:nth-last-child(1) {
  background:#ff0000;
}
```
