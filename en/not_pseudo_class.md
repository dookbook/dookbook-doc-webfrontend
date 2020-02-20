TOPICS: :not()
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:not()`

The **`:not()`** CSS pseudo-class represents elements that do not match a list of selectors. Since
it prevents specific items from being selected, it is known as the negation pseudo-class.

- `:not` pseudo-class may not be nested, which means that `:not(:not(...))` is invalid.
- Since pseudo-elements are not simple selectors, they are not a valid arguments to `:not()`, selectors
like `:not(p::before)` will not work.
- Useless selectors can be written using this pseudo-class. For example, `:not(*)` matches any element
which is not an element, so the rule will never be applied.
- This pseudo-class can increase the specificity of a rule. For example, `#foo:not(#bar)` will match
the same element as the simpler `#foo`, but has a higher specificity.
- `:not(.foo)` will match anything that isn't .foo, including [`<html>`](/en/webfrontend/<html>) and
[`<body>`](/en/webfrontend/<body>).
- This selector only applies to one element; you cannot use it to exclude all ancestors. For instance,
`body :not(table)` a will still apply to links inside of a table, since [`<tr>`](/en/webfrontend/<tr>)
will match with the `:not()` part of the selector.

## Syntax

The `:not()` pseudo-class requires a comma-separated list of one or more selectors as its argument.
The list must not contain another negation selector or a pseudo-element.

!!! error ""
    The ability to list more than one selector is experimental and not yet widely supported.

```css
/* Selects any element that is NOT a paragraph */
:not(p) {
  color: blue;
}
```

## Example

```html
<p>I am a paragraph.</p>
<p class="fancy">I am so very fancy!</p>
<div>I am NOT a paragraph.</div>
```

```css
.fancy {
  text-shadow: 2px 2px 3px gold;
}

/* <p> elements that are not in the class `.fancy` */
p:not(.fancy) {
  color: green;
}

/* Elements that are not <p> elements */
body :not(p) {
  text-decoration: underline;
}

/* Elements that are not <div> and not <span> elements */
body :not(div):not(span) {
  font-weight: bold;
}

/* Elements that are not `.crazy` or `.fancy` */
/* Note that this syntax is not well supported yet. */
body :not(.crazy, .fancy) {
  font-family: sans-serif;
}
```
