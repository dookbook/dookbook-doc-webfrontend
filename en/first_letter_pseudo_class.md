TOPICS: :first-letter

# CSS Pseudo-Class: `:first-letter`

The **`:first-letter`** CSS pseudo-class is used to specify the style of the **first letter** of an element.

!!! warn "Note"
    The `first-letter` selector is only available in block-level elements.

## Example

```html
<h1>Welcome to My Homepage</h1>
<p>My name is Donald.</p>
<p>I live in Duckburg.</p>
<p>My best friend is Mickey.</p>
```

```css
p:first-letter {
  font-size:200%;
  color:#8A2BE2;
}
```
