TOPICS: <style>
        <style> type attribute
        <style> scoped attribute
        <style> title attribute
        <style> media attribute

# HTML Style Information Element: `<style>`

The **HTML `<style>` element** contains style information for a document, or part of a document.
It contains CSS, which is applied to the contents of the document containing the `<style>` element.

The `<style>` element can be included inside the [`<head>`](/en/webfrontend/<head>) or [`<body>`](/en/webfrontend/<body>)
of the document, and the styles will still be applied, however it is recommended that you include your
styles in the [`<head>`](/en/webfrontend/<head>) for organizational purposes — it is a lot better to
separate your content from your presentation as much as possible. Even better, put your styles in
external stylesheets and apply them using [`<link>`](/en/webfrontend/<link>) elements.

If you include multiple `<style>` and [`<link>`](/en/webfrontend/<link>) elements in your document,
they will be applied to the DOM in the order they are included in the document — make sure you
include them in the correct order, to avoid unexpected cascade issues.

In the same manner as [`<link>`](/en/webfrontend/<link>) elements, `<style>` elements can include
media attributes that contain media queries, allowing you to selectively apply internal stylesheets
to your document depending on media features such as viewport width.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Metadata content*, and if the `scoped` attribute is present: *flow content*. |
| **Permitted content** | Text content matching the `type` attribute, that is `text/css`. |
| **Tag omission** | Neither tag is omissible. |
| **Permitted parents** | Any element that accepts *metadata content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLStyleElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `type` | This attribute defines the styling language as a [[MIME]] type (charset should not be specified). This attribute is optional and defaults to `text/css` if it is not specified — there is very little reason to include this in modern web documents. |
| `scoped` | If the attribute is present, the style is applied to its parent element; if it is not present, it is applied to the entire document. |
| `title` | This attribute specifies alternative style sheet sets. |
| `media` | This attribute defines which media the style should be applied to. Its value is a media query, which defaults to `all` if the attribute is missing. |

## A simple stylesheet

In the following example, we apply a very simple stylesheet to a document:

```html
<!doctype html>
<html>
<head>
<style>
p {
  color: red;
}
</style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```

## Multiple style elements

In this example we've included two `<style>` elements — notice how the conflicting declarations
in the later `<style>` element override those in the earlier one, if they have equal specificity.

```html
<!doctype html>
<html>
<head>
  <style>
  p {
    color: white;
    background-color: blue;
    padding: 5px;
    border: 1px solid black;
  }
  </style>
  <style>
  p {
    color: blue;
    background-color: yellow;
  }
  </style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```

## Including a media query

In this example we build on the previous one, including a media attribute on the second `<style>`
element so it is only applied when the viewport is less than 500px in width.

```html
<!doctype html>
<html>
<head>
  <style>
    p {
      color: white;
      background-color: blue;
      padding: 5px;
      border: 1px solid black;
    }
  </style>
  <style media="all and (max-width: 500px)">
    p {
      color: blue;
      background-color: yellow;
    }
  </style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<style>`| support | support | support |
