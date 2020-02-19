TOPICS: :in-range
        :out-of-range

# CSS Pseudo-Class: `:in-range`、`:out-of-range`

The **`:in-range`** CSS pseudo-class represents an [*`<input>`*](/en/webfrontend/<input>) element
whose current value is **within the range limits** specified by the **`min`** and **`max`** attributes.

The **`:out-of-range`** CSS pseudo-class represents an [*`<input>`*](/en/webfrontend/<input>) element
whose current value is **outside the range limits** specified by the **`min`** and **`max`** attributes.

## Example

```html
<form action="" id="form1">
  <ul>Values between 1 and 10 are valid.
    <li>
      <input id="value1" name="value1" type="number" placeholder="1 to 10" min="1" max="10" value="12">
      <label for="value1">Your value is </label>
    </li>
  </ul>
</form>
```

```css
li {
  list-style: none;
  margin-bottom: 1em;
}

input {
  border: 1px solid black;
}

input:in-range {
  background-color: rgba(0, 255, 0, 0.25);
}

input:out-of-range {
  background-color: rgba(255, 0, 0, 0.25);
  border: 2px solid red;
}

input:in-range + label::after {
  content: 'okay.';
}

input:out-of-range + label::after {
  content: 'out of range!';
}
```
