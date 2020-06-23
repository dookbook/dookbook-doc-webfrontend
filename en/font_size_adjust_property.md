TOPICS: font-size-adjust property

# CSS Property: `font-size-adjust`

The CSS **`font-size-adjust`** property defines the font size **should depend on lowercase letters**,
not uppercase letters. When the font is small, the readability of the font is mainly determined by the
size of the lowercase letters, which can be adjusted through this option.

When the preferred font of [**`font-family`**](/en/webfrontend/font-family_property) is not available,
if the size ratio of the alternative font (the ratio of the size of lowercase letters to the font size)
is larger When there is a difference, readability can become a big issue.

In order to be compatible with browsers that do not support **`font-size-adjust`**, the value of this
property should be defined as [**`font-size`**](/en/webfrontend/font-size_property) The factor by
which the value is to be multiplied. This means that the defined value should be the size ratio of
the preferred font.

For example, the real effect of this style sheet definition is to define that the size of lowercase
letters should be `7px` high (`0.5` × `14px`).

```css
font-size: 14px;
font-size-adjust: 0.5;
```

## Property value

| Property value | Description |
| :--- | :--- |
| **`none`** | The font size is determined only according to the `font-size` property. |
| **number** | Define the font based on the result of multiplying the lowercase letter size (based on the font's x-height--the distance between the baseline and the main line in the Western font design--determined) for this value multiplied by [**`font-size`**](/en/webfrontend/font-family_property). <br><br>The number should be [**`font-family`**](/en/webfrontend/font-family_property) the preferred font size ratio (the ratio of x-height to font size). This means that when the preferred font is available, regardless of whether the browser supports **`font-size-adjust`**, the text will be displayed as the size of [**`font-size`**](/en/webfrontend/font-size_property). |

## Examples

```css
p {
  font: 12px Verdana, "DejaVu Sans", sans-serif;
  font-size-adjust: 0.58;
}
```
