TOPICS: text-justify property

# CSS Property: `text-justify`

The **`text-justify`** CSS property sets **what type of justification should be applied to text** when
**`text-align: justify;`** is set on an element.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`none`** | The text justification is turned off. This has the same effect as not setting text-align at all, although it is useful if you need to turn justification on and off for some reason. |
| **`auto`** | The browser chooses the best type of justification for the current situation based on a balance between performance and quality, but also on what is most appropriate for the language of the text (e.g., English, CJK languages, etc.). This is the default justification used if text-justify is not set at all. |
| **`inter-word`** | The text is justified by adding space between words (effectively varying word-spacing), which is most appropriate for languages that separate words using spaces, like English or Korean. |
| **`inter-character`** | The text is justified by adding space between characters (effectively varying letter-spacing), which is most appropriate for languages like Japanese. |

## Examples

```css
p {
  font-size: 1.5em;
  border: 1px solid black;
  padding: 10px;
  width: 95%;
  margin: 10px auto;
  text-align: justify;
}

.none {
  text-justify: none;
}

.auto {
  text-justify: auto;
}

.word {
  text-justify: inter-word;
}

.char {
  text-justify: inter-character;
}
```

```html
<p class="none">text-justify: none —
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ornare maximus vehicula. Duis nisi velit, dictum id mauris vitae, lobortis pretium quam. Quisque sed nisi pulvinar, consequat justo id, feugiat leo. Cras eu elementum dui.</p>
<p class="auto">text-justify: auto —
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ornare maximus vehicula. Duis nisi velit, dictum id mauris vitae, lobortis pretium quam. Quisque sed nisi pulvinar, consequat justo id, feugiat leo. Cras eu elementum dui.</p>
<p class="dist">text-justify: distribute —
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ornare maximus vehicula. Duis nisi velit, dictum id mauris vitae, lobortis pretium quam. Quisque sed nisi pulvinar, consequat justo id, feugiat leo. Cras eu elementum dui.</p>
<p class="word">text-justify: inter-word —
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ornare maximus vehicula. Duis nisi velit, dictum id mauris vitae, lobortis pretium quam. Quisque sed nisi pulvinar, consequat justo id, feugiat leo. Cras eu elementum dui.</p>
<p class="char">text-justify: inter-character —
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ornare maximus vehicula. Duis nisi velit, dictum id mauris vitae, lobortis pretium quam. Quisque sed nisi pulvinar, consequat justo id, feugiat leo. Cras eu elementum dui.</p>
```
