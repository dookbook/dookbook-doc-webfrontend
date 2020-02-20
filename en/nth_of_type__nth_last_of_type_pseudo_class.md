TOPICS: :nth-of-type()
        :nth-last-of-type()
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:nth-of-type()`、`:nth-last-of-type()`

The **`:nth-of-type(n)`** CSS pseudo-class matches elements of a given type, based on their position
among a group of siblings.

The **`:nth-last-of-type(n)`** CSS pseudo-class matches elements of a given type, based on their
position among a group of siblings, counting from the end.

## parameter

*n* can be a number, a keyword, or a formula.

## Example: `:nth-of-type()`

```html
<div>
  <div>This element isn't counted.</div>
  <p>1st paragraph.</p>
  <p>2nd paragraph.</p>
  <div>This element isn't counted.</div>
  <p>3rd paragraph.</p>
  <p>4th paragraph.</p>
</div>
```

```css
/* Odd paragraphs */
p:nth-of-type(2n+1) {
  color: red;
}

/* Even paragraphs */
p:nth-of-type(2n) {
  color: blue;
}

/* First paragraph */
p:nth-of-type(1) {
  font-weight: bold;
}
```

## Example: `:nth-last-of-type()`

```html
<div>
  <span>This is a span.</span>
  <span>This is another span.</span>
  <em>This is emphasized.</em>
  <span>Wow, this span gets limed!!!</span>
  <strike>This is struck through.</strike>
  <span>Here is one last span.</span>
</div>
```

```css
span:nth-last-of-type(2) {
  background-color: lime;
}
```
