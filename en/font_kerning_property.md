TOPICS: font-kerning property

# CSS Property: `font-kerning`

CSS **`font-kerning`** property sets whether to use **storage information stored in the font**.

Kerning defines the distribution of letters. For fonts with well-defined kerning, the kerning
characteristics make the letter distribution more uniform and the reading experience better. As
shown in the figure below, the example on the left does not apply kerning, but the right side uses:
**`font-kerning`** property is specified by the following keywords.

## Property value

| Property value | Description |
| :--- | :--- |
| **`auto`** | The browser decides whether to use font kerning. For example, some browsers will disable kerning in the case of small fonts, because this will reduce the readability of the text. |
| **`normal`** | The kerning information in the font must be applied. |
| **`none`** | Disable kerning information in fonts. |

## Examples

```html
<div id="kern"></div>
<div id="nokern"></div>
<textarea id="input">AV T. ij</textarea>
```

```css
div {
  font-size: 2rem;
  font-family: serif;
}

#nokern {
  font-kerning: none;
}

#kern {
  font-kerning: normal;
}
```

```javascript
var input  = document.getElementById('input'),
    kern   = document.getElementById('kern'),
    nokern = document.getElementById('nokern');

input.addEventListener('keyup', function() {
  kern.textContent = input.value; /* update content */
  nokern.textContent = input.value;
});

kern.textContent = input.value; /* Initialize content */
nokern.textContent = input.value;
```
