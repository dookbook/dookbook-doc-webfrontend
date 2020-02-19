TOPICS: :checked
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:checked`

The **`:checked`** CSS pseudo-class selector represents any **`radio`** (`<input type="radio">`),
**`checkbox`** (`<input type="checkbox">`), or **`option`** ([`<option>`](/en/webfrontend/<option>)
in a [`<select>`](/en/webfrontend/<select>)) element that is checked or toggled to an `on` state.

The user can engage this state by checking/selecting an element, or disengage it by
unchecking/deselecting the element.

!!! warn "Note"
    Because browsers often treat `<option>`s as replaced elements, the extent to which they can be
    styled with the `:checked` pseudo-class varies from browser to browser.

## Basic example

```html
<div>
  <input type="radio" name="my-input" id="yes">
  <label for="yes">Yes</label>

  <input type="radio" name="my-input" id="no">
  <label for="no">No</label>
</div>

<div>
  <input type="checkbox" name="my-checkbox" id="opt-in">
  <label for="opt-in">Check me!</label>
</div>

<select name="my-select" id="fruit">
  <option value="opt1">Apples</option>
  <option value="opt2">Grapes</option>
  <option value="opt3">Pears</option>
</select>
```

```css
div,
select {
  margin: 8px;
}

/* Labels for checked inputs */
input:checked + label {
  color: red;
}

/* Radio element, when checked */
input[type="radio"]:checked {
  box-shadow: 0 0 0 3px orange;
}

/* Checkbox element, when checked */
input[type="checkbox"]:checked {
  box-shadow: 0 0 0 3px hotpink;
}

/* Option elements, when selected */
option:checked {
  box-shadow: 0 0 0 3px lime;
  color: red;
}
```

## Toggling elements with a hidden checkbox

This example utilizes the `:checked` pseudo-class to let the user toggle content based on the
state of a checkbox, all without using JavaScript.

```html
<input type="checkbox" id="expand-toggle" />

<table>
  <thead>
    <tr><th>Column #1</th><th>Column #2</th><th>Column #3</th></tr>
  </thead>
  <tbody>
    <tr class="expandable"><td>[more text]</td><td>[more text]</td><td>[more text]</td></tr>
    <tr><td>[cell text]</td><td>[cell text]</td><td>[cell text]</td></tr>
    <tr><td>[cell text]</td><td>[cell text]</td><td>[cell text]</td></tr>
    <tr class="expandable"><td>[more text]</td><td>[more text]</td><td>[more text]</td></tr>
    <tr class="expandable"><td>[more text]</td><td>[more text]</td><td>[more text]</td></tr>
  </tbody>
</table>

<label for="expand-toggle" id="expand-btn">Toggle hidden rows</label>
```

```css
/* Hide the toggle checkbox */
#expand-toggle {
  display: none;
}

/* Hide expandable content by default */
.expandable {
  visibility: collapse;
  background: #ddd;
}

/* Style the button */
#expand-btn {
  display: inline-block;
  margin-top: 12px;
  padding: 5px 11px;
  background-color: #ff7;
  border: 1px solid;
  border-radius: 3px;
}

/* Show hidden content when the checkbox is checked */
#expand-toggle:checked ~ * .expandable {
  visibility: visible;
}

/* Style the button when the checkbox is checked */
#expand-toggle:checked ~ #expand-btn {
  background-color: #ccc;
}
```
