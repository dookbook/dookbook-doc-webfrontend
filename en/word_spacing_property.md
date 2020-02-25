TOPICS: word-spacing property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `word-spacing`

The **`word-spacing`** CSS property sets **the length of space between words and between tags**.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`normal`** | The normal inter-word spacing, as defined by the current font and/or the browser. |
| length | Specifies extra spacing in addition to the intrinsic inter-word spacing defined by the font. |
| **`%`** | Specifies extra spacing as a percentage of the affected character’s advance width. |

## Examples

```css
#mozdiv1 {
  word-spacing: 15px;
}

#mozdiv2 {
  word-spacing: 5em;
}
```

```html
<div id="mozdiv1">Here are many words...</div>
<div id="mozdiv2">...and many more!</div>
```
