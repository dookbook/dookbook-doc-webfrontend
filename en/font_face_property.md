TOPICS: @font-face property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `@font-face`

The **@font-face** CSS at-rule specifies a custom font with which to display text; the font can be
loaded from either a remote server or a locally-installed font on the user's own computer. If the
`local()` function is provided, specifying a font name to look for on the user's computer, and the
user agent finds a match, that local font is used. Otherwise, the font resource specified using the
`url()` function is downloaded and used.

By allowing authors to provide their own fonts, `@font-face` makes it possible to design content
without being limited to the so-called "web-safe" fonts (that is, the fonts which are so common
that they're considered to be universally available). The ability to specify the name of a
locally-installed font to look for and use makes it possible to customize the font beyond the
basics while making it possible to do so without relying on an Internet connection.

It's common to use both `url()` and `local()` together, so that the user's installed copy of the font
is used if available, falling back to downloading a copy of the font if it's not found on the
user's device.

The `@font-face` at-rule may be used not only at the top level of a CSS, but also inside any
CSS conditional-group at-rule.

```css
@font-face {
  font-family: "Open Sans";
  src: url("/fonts/OpenSans-Regular-webfont.woff2") format("woff2"),
       url("/fonts/OpenSans-Regular-webfont.woff") format("woff");
}
```

## Examples

This example simply specifies a downloadable font to use, applying it to the entire
[`<body>`](/en/webfrontend/<body>) of the document:

```html
<html>
<head>
  <title>Web Font Sample</title>
  <style type="text/css" media="screen, print">
    @font-face {
      font-family: "Bitstream Vera Serif Bold";
      src: url("https://mdn.mozillademos.org/files/2468/VeraSeBd.ttf");
    }

    body { font-family: "Bitstream Vera Serif Bold", serif }
  </style>
</head>
<body>
  This is Bitstream Vera Serif Bold.
</body>
</html>
```

In this example, the user's local copy of "Helvetica Neue Bold" is used; if the user does not have
that font installed (two different names are tried), then the downloadable font named
"MgOpenModernaBold.ttf" is used instead:

```css
@font-face {
  font-family: MyHelvetica;
  src: local("Helvetica Neue Bold"),
       local("HelveticaNeue-Bold"),
       url(MgOpenModernaBold.ttf);
  font-weight: bold;
}
```
