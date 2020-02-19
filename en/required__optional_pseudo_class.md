TOPICS: :required
        :optional
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:required`、`:optional`

The **`:required`** CSS pseudo-class represents any [`<input>`](/en/webfrontend/<input>), [`<select>`](/en/webfrontend/<select>),
or [`<textarea>`](/en/webfrontend/<textarea>) element that has the `required` attribute set on it.

The **`:optional`** CSS pseudo-class represents any [`<input>`](/en/webfrontend/<input>),
[`<select>`](/en/webfrontend/<select>), or [`<textarea>`](/en/webfrontend/<textarea>) element that
does not have the required attribute set on it.

## Example

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
input:required {
  background-color: yellow;
}

input:optional {
  background-color: yellow;
}
```
