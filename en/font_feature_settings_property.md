TOPICS: font-feature-settings property

# CSS property: `font-feature-settings`

The CSS **`font-feature-settings`** property allows you to control the advanced printing features
in OpenType fonts.

!!! warn ""
    Web developers should use short tag propertys like [**`font-variant`**](/en/webfrontend/font-variant_property)
    or related shorthand logo propertys as much as possible, similar to `font-variant-ligatures`,
    `font-variant-caps`, `font-variant-east-asian`, `font-variant-alternates`, `font-variant-numeric`
    or `font-variant-position`.
    This property is a relatively low-level functional interface, used to solve some special functional
    requirements because there is no other way to access and set certain features of OpenType fonts.
    In particular, it should be noted that this CSS property should not be used to enable capital conversion.

## Property value

| Property value | Description |
| :--- | :--- |
| **`normal`** | The text is laid out using default settings. |
| **feature-tag-value** | When rendering text, a list of OpenType element tag values is passed to the text layout engine to enable or disable font features. The label is always `<string>` of 4 ASCII characters. If it is a character beyond U + 20-U + 7E code point range or the number of characters is incorrect, the entire property is invalid. <br>The value is a positive integer. The two keywords `on` and `off` are synonyms for `1` and `0` respectively. If no value is set, the default value is `1`. For non-Boolean OpenType functions (for example, stylistic substitution), this value means that a specific glyph is selected; for Boolean values, it is a switch. |

## Examples

```css
/* Use lowercase alternate glyphs */
.smallcaps { font-feature-settings: "smcp" on; }

/* Convert both uppercase and lowercase to lowercase (also affects punctuation) */
.allsmallcaps { font-feature-settings: "c2sc", "smcp"; }

/* Enable historical form */
.hist { font-feature-settings: "hist"; }

/* Disable common ligatures, usually enabled by default */
.noligs { font-feature-settings: "liga" 0; }

/* Enable table (isometric) graphics */
td.tabular { font-feature-settings: "tnum"; }

/* Enable automatic scoring */
.fractions { font-feature-settings: "frac"; }

/* Use the second available slash character */
.swash { font-feature-settings: "swsh" 2; }

/* Enable Style Set 7 */
.fancystyle {
  font-family: Gabriola; /* Available on Windows 7 and Mac OS */
  font-feature-settings: "ss07";
}
```
