TOPICS: letter-spacing property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `letter-spacing`

The **`letter-spacing`** CSS property sets **the spacing behavior between text characters**.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`normal`** | The normal letter spacing for the current font. Unlike a value of `0`, this keyword allows the user agent to alter the space between characters in order to justify text. |
| length | Specifies extra inter-character space in addition to the default space between characters. Values may be negative, but there may be implementation-specific limits. User agents may not further increase or decrease the inter-character space in order to justify text. |

## Examples

```css
.normal   { letter-spacing: normal; }
.em-wide  { letter-spacing: 0.4em; }
.em-wider { letter-spacing: 1em; }
.em-tight { letter-spacing: -0.05em; }
.px-wide  { letter-spacing: 6px; }
```

```html
<p class="normal">letter spacing</p>
<p class="em-wide">letter spacing</p>
<p class="em-wider">letter spacing</p>
<p class="em-tight">letter spacing</p>
<p class="px-wide">letter spacing</p>
```
