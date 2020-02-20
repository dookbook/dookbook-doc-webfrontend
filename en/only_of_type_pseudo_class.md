TOPICS: :only-of-type
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:only-of-type`

The **`:only-of-type`** CSS pseudo-class represents an element that has no siblings of the same type.

## Example

```html
<main>
  <div>I am `div` #1.</div>
  <p>I am the only `p` among my siblings.</p>
  <div>I am `div` #2.</div>
  <div>I am `div` #3.
    <i>I am the only `i` child.</i>
    <em>I am `em` #1.</em>
    <em>I am `em` #2.</em>
  </div>
</main>
```

```css
main :only-of-type {
  color: red;
}
```
