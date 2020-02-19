TOPICS: :default
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:default`

The **`:default`** CSS pseudo-class selects form elements that are the default in a group of
related elements.

What this selector matches is defined in HTML Standard §4.16.3 Pseudo-classes — it may match the
[`<button>`](/en/webfrontend/<button>), `<input type="checkbox">`, `<input type="radio">`, and
[`<option>`](/en/webfrontend/<option>) elements:

- A default option element is the first one with the `selected` attribute, or the first enabled
option in DOM order. `multiple` [`<select>`](/en/webfrontend/<select>)s can have more than one
`selected` option, so all will match `:default`.
- `<input type="checkbox">` and `<input type="radio">` match if they have the `checked` attribute.
- [`<button>`](/en/webfrontend/<button>) matches if it is a [`<form>`](/en/webfrontend/<form>)’s
default submission button: the first [`<button>`](/en/webfrontend/<button>) in DOM order that belongs
to the form. (This also applies to [`<input>`](/en/webfrontend/<input>) types that submit forms,
like image or submit.)

## Example

```html
<fieldset>
  <legend>Favorite season</legend>

  <input type="radio" name="season" id="spring">
  <label for="spring">Spring</label>

  <input type="radio" name="season" id="summer" checked>
  <label for="summer">Summer</label>

  <input type="radio" name="season" id="fall">
  <label for="fall">Fall</label>

  <input type="radio" name="season" id="winter">
  <label for="winter">Winter</label>
</fieldset>
```

```css
input:default {
  box-shadow: 0 0 2px 1px coral;
}

input:default + label {
  color: coral;
}
```
