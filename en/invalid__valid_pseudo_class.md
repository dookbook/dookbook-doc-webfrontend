TOPICS: :invalid
        :valid
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:invalid`

The **`:invalid`** CSS pseudo-class represents any [*`<input>`*](/en/webfrontend/<input>) or other
[*`<form>`*](/en/webfrontend/<form>) element whose contents fail to validate.

The **`:valid`** CSS pseudo-class represents any [*`<input>`*](/en/webfrontend/<input>) or other [*`<form>`*](/en/webfrontend/<form>)
element whose contents validate successfully. This allows to easily make valid fields adopt an
appearance that helps the user confirm that their data is formatted properly.

## Example

This example presents a simple form that colors elements green when they validate and red when they don't.

```html
<form>
  <div class="field">
    <label for="url_input">Enter a URL:</label>
    <input type="url" id="url_input">
  </div>

  <div class="field">
    <label for="email_input">Enter an email address:</label>
    <input type="email" id="email_input" required>
  </div>
</form>
```

```css
label {
  display: block;
  margin: 1px;  
  padding: 1px;
}

.field {
  margin: 1px;
  padding: 1px;
}

input:invalid {
  background-color: #ffdddd;
}

form:invalid {
  border: 5px solid #ffdddd;
}

input:valid {
  background-color: #ddffdd;
}

form:valid {
  border: 5px solid #ddffdd;
}
  
input:required {
  border-color: #800000;
  border-width: 3px;
}

input:required:invalid {
  border-color: #c00000;
}
```
