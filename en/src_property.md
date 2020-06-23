TOPICS: src property

# CSS Font data resource property: `src`

**The `src`** descriptor in **`@font-face`** specifies the resource containing **font data**. **`@font-face`**
This property needs to be specified in the rule.

Its value is a prioritized, comma-separated external reference or locally installed font name. When
a font is required, the user agent (meaning browser) will use the first reference value that can be
successfully activated in a comma-separated reference set. If the font contains invalid data or the
local font resource does not exist, the user agent will ignore the current font and load the next font.

Like other URLs in CSS, the URL can be relative, in which case it is resolved relative to the
location of the style sheet that contains the **`@font-face`** rule. For SVG fonts, the URL points
to the element defined in the document that contains the SVG font. If element reference is omitted,
the first defined font is referenced by default. Similarly, the font container only loads one of the
fonts given by the **`@font-face`** rule. The fragment identifier is used to indicate the font to be
loaded. If the container format lacks the defined fragment identifier scheme, a simple 1-based index
scheme will be used (for example: the first font is "font-collection#1" and the second font is
"font-collection#2" ,and many more).

| Property value | Description |
| :--- | :--- |
| **`url() format()`** | Specify an external reference consisting of **`url`**, and then use the **`format()`** function to describe the optional hint of the format of the font resource referenced by the URL. The format hint contains a comma-separated list of format strings that represent well-known font formats. If the user agent does not support the specified format, it will skip downloading font resources. If no format hint is provided, font resources are always downloaded. |
| **`local()`** | Use the **`local()`** function to specify the name of a locally installed font, which uniquely identifies a single font in a larger series. The name can optionally be enclosed in quotation marks.|

## Examples

```css
@font-face {
  font-family: examplefont;
  /* url value */
  src: url(https://somewebsite.com/path/to/font.woff); /* Absolute URL */
  src: url(path/to/font.woff);                         /* Relative URL */
  src: url(path/to/font.woff) format("woff");          /* Explicit format */
  src: url('path/to/font.woff');                       /* Reference URL */
  src: url(path/to/svgfont.svg#example);               /* Fragment recognition font */

  /* Font name value */
  src: local(font);      /* Unquoted names */
  src: local(some font); /* Name contains spaces */
  src: local("font");    /* Reference name */

  /* Multiple projects */
  src: local(font), url(path/to/font.svg) format("svg"),
       url(path/to/font.woff) format("woff"),
       url(path/to/font.otf) format("opentype");
}
```
