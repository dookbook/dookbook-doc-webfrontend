TOPICS: :first
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:first`

The **`:first`** CSS pseudo-class, used with the  `@page` at-rule, represents the first page of a
printed document.

!!! warn "Note"
    You can't change all CSS properties with this pseudo-class. You can only change the margins,
    `orphans`, `widows`, and page breaks of the document. Furthermore, you may only use absolute-length
    units when defining the margins. All other properties will be ignored.

## Example

```html
<p>First Page.</p>
<p>Second Page.</p>
<button>Print!</button>
```

```css
@page :first {
  margin-left: 50%;
  margin-top: 50%;
}

p {
  page-break-after: always;
}
```

```javascript
document.querySelector("button").addEventListener('click', () => {
  window.print();
});
```
