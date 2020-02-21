TOPICS: :indeterminate

# CSS Pseudo-Class: `:indeterminate`

The **`:indeterminate`** CSS pseudo-class represents any *form element* **whose state is indeterminate**.

For example, `radio` and `checkbox` elements can be toggled between checked and unchecked, but
sometimes in an indeterminate state, neither selected nor unchecked. Similarly, there is an
HTML5 [**`<progress>`**](/en/webfrontend/<progress>) tag. When the percentage of completion is unknown,
the progress bar ([**`<progress>`**](/en/webfrontend/<progress>) ) can be in an indeterminate state.

- **`<input type="checkbox">`** elements whose `indeterminate` property is set to `true` by JavaScript
- **`<input type="radio">`** elements, when all radio buttons with the same `name` value in the
form are unchecked
- Progress bar [**`<progress>`**](/en/webfrontend/<progress>) element without `value` attribute

## Example: Checkbox & radio button

This example applies special styles to the labels associated with indeterminate form fields.

```html
<div>
  <input type="checkbox" id="checkbox">
  <label for="checkbox">This label starts out lime.</label>
</div>
<div>
  <input type="radio" id="radio">
  <label for="radio">This label starts out lime.</label>
</div>
```

```css
input:indeterminate + label {
  background: lime;
}
```

```javascript
var inputs = document.getElementsByTagName("input");

for (var i = 0; i < inputs.length; i++) {
  inputs[i].indeterminate = true;
}
```

## Example: Progress bar

```html
<progress>
```

```css
progress {
  margin: 4px;
}

progress:indeterminate {
  opacity: 0.5;
  background-color: lightgray;
  box-shadow: 0 0 2px 1px red;
}
```
