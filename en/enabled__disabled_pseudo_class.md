TOPICS: :enabled
        :disabled
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:enabled`、`:disabled`

The **`:enabled`** CSS pseudo-class represents any enabled element. An element is enabled if it can
be activated (selected, clicked on, typed into, etc.) or accept focus. The element also has a disabled
state, in which it can't be activated or accept focus.

The **`:disabled`** CSS pseudo-class represents any disabled element. An element is disabled if it
can't be activated (selected, clicked on, typed into, etc.) or accept focus. The element also has an
enabled state, in which it can be activated or accept focus.

## Example

The following example makes the color of text and button [`<input>`](/en/webfrontend/<input>)s green
when enabled, and gray when disabled. This helps the user understand which elements can be interacted
with.

```html
<form action="url_of_form">
  <label for="FirstField">First field (enabled):</label>
  <input type="text" id="FirstField" value="Lorem"><br>

  <label for="SecondField">Second field (disabled):</label>
  <input type="text" id="SecondField" value="Ipsum" disabled="disabled"><br>

  <input type="button" value="Submit">
</form>
```

```css
input:enabled {
  color: #2b2;
}

input:disabled {
  color: #aaa;
}
```
