TOPICS: list-style property
        list-style-type property
        list-style-image property
        list-style-position property

# CSS 列表属性 (`list-style`)

In HTML, there are two types of HTML lists:

- **Unordered list** - List items are marked with **special graphics** (such as **small black dots**,
**small boxes**, etc.)
- **Ordered List** - List items are marked with **number** or **letter**

Set list item tag properties as follows

| Property | Description |
| :--- | :--- |
| **`list-style`** | Set **all list** properties, it is shorthand properties |
| **`list-style-type`** | Set the element **list item's mark** (such as **number**, **letter**, etc.)|
| **`list-style-image`** | Set element **list-marked picture** |
| **`list-style-position`** | Set how to **draw list item tags relative to the content of the object** |

## `list-style-type` Property Value

| Property Value | Description |
| :--- | :--- |
| **`none`** | Unmarked |
| **`disc`** | default. Marked **filled circle** |
| **`circle`** | The mark is **hollow circle** |
| **`square`** | Marked **filled square** |
| **`decimal`** | Mark is **number** |
| **`decimal-leading-zero`** | **Numbers starting with 0**. (01, 02, 03, etc.)|
| **`lower-roman`** | **Lowercase Roman numerals** (i, ii, iii, iv, v, etc.) |
| **`upper-roman`** | **Capital Roman numerals** (I, II, III, IV, V, etc.) |
| **`lower-alpha`** | **Lowercase English letters** (a, b, c, d, e, etc.) |
| **`upper-alpha`** | **Capital English letters** (A, B, C, D, E, etc.) |
| **`lower-greek`** | **lowercase Greek letters** (alpha, beta, gamma, etc.) |
| **`lower-latin`** | **Lowercase Latin letters** (a, b, c, d, e, etc.) |
| **`upper-latin`** | **Uppercase Latin letters** (A, B, C, D, E, etc.)|
| **`hebrew`** | **Traditional Hebrew Numbering** |
| **`armenian`** | **Traditional Armenian Numbering** |
| **`georgian`** | **Traditional Georgia Numbering** (an, ban, gan, etc.) |
| **`cjk-ideographic`** | **Simple Ideographic Numbers** |
| **`hiragana`** | The marks are: **a, i, u, e, o, ka, ki**, etc. (Japanese Katakana) |
| **`katakana`** | The marks are: **A, I, U, E, O, KA, KI** and so on. (Japanese Katakana) |
| **`hiragana-iroha`** | The marks are: **i, ro, ha, ni, ho, he, to** and so on. (Japanese Katakana) |
| **`katakana-iroha`** | The marks are: **I, RO, HA, NI, HO, HE, TO**, etc. (Japanese Katakana) |

## `list-style-image` Property Value

| Property Value | Description |
| :--- | :--- |
| **URL** | The path of the image. |
| **`none`** | Default. No graphics are displayed. |

## `list-style-position` Property Value

| Property Value | Description |
| :--- | :--- |
| **`inside`** | List item tags are placed within the text and the surrounding text is aligned according to the tags. |
| **`outside`** | Defaults. Keep the mark to the left of the text. List item tags are placed outside the text and the surrounding text is not aligned with the tags. |

## Example

!!! warn "Note"
    **`list-style-type`** and **`list-style-image`** can only take effect at the same time

```html
List 1
<ul class="one">
  <li>List Item1</li>
  <li>List Item2</li>
  <li>List Item3</li>
</ul>
List 2
<ol class="two">
  <li>List Item A</li>
  <li>List Item B</li>
  <li>List Item C</li>
</ol>
```

```css
ul li, ol li {
  border: 1px solid #000;
}

ul {
  /* Indicates that the list item is marked with a picture and placed in the left text */
  list-style: url('sqpurple.gif') inside;
}

ol {
  /* Indicates that list items are numbered */
  list-style-type: decimal;

  /* Indicates that the list item mark is placed outside the text on the left */
  list-style-position: outside;
}
```
