TOPICS: :focus-within
        :focus

# CSS Pseudo-Class: `:focus-within`、`:focus`

The **`:focus-within`** CSS pseudo-class represents an element that has received focus or contains
an element that has received focus. In other words, it represents an element that is itself matched
by the `:focus` pseudo-class or has a descendant that is matched by `:focus`. (This includes descendants
in shadow trees.)

This selector is useful, to take a common example, for highlighting an entire
[`<form>`](/en/webfrontend/<form>) container when the user focuses on one of its
[`<input>`](/en/webfrontend/<input>) fields.

The **`:focus`** CSS pseudo-class represents an element (such as a form input) that has received
focus. It is generally triggered when the user clicks or taps on an element or selects it with the
keyboard's !!!tab!!! key.

## Example: `:focus-within`

In this example, the form will receive special coloring styles when either text input receives focus.

```html
<p>Try typing into this form.</p>

<form>
  <label for="given_name">Given Name:</label>
  <input id="given_name" type="text">
  <br>
  <label for="family_name">Family Name:</label>
  <input id="family_name" type="text">
</form>
```

```css
form {
  border: 1px solid;
  color: gray;
  padding: 4px;
}

form:focus-within {
  background: #ff8;
  color: black;
}

input {
  margin: 4px;
}
```

## Example: `:focus`

```html
<input class="red-input" value="I'll be red when focused."><br>
<input class="blue-input" value="I'll be blue when focused.">
```

```css
.red-input:focus {
  background: yellow;
  color: red;
}

.blue-input:focus {
  background: yellow;
  color: blue;
}
```
