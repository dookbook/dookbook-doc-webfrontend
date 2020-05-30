TOPICS: <meta>

# HTML Metadata Element: `<meta>`

The HTML `<meta>` element represents **metadata** that cannot be represented by other HTML meta-related
elements, like [`<base>`](/en/webfrontend/<base>), [`<link>`](/en/webfrontend/<link>),
[`<script>`](/en/webfrontend/<script>), [`<style>`](/en/webfrontend/<style>) or [`<title>`](/en/webfrontend/<title>).

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | Metadata content. If the `itemprop` attribute is present: *flow content*, *phrasing content*. |
| **Permitted content** | None, it is an empty element. |
| **Tag omission** | As it is a void element, the start tag must be present and the end tag must not be present. |
| **Permitted parents** | [`<meta charset>`](/en/webfrontend/<meta>_charset_attribute), [`<meta http-equiv>`](/en/webfrontend/<meta>_http-equiv_attribute): a [`<head>`](/en/webfrontend/<head>) element. If the `http-equiv` is not an encoding declaration, it can also be inside a [`<noscript>`](/en/webfrontend/<noscript>) element, itself inside a [`<head>`](/en/webfrontend/<head>) element. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLMetaElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

!!! warn "Note"
    The attribute [`name`](/en/webfrontend/<meta>_name_attribute) has a specific meaning for the
    `<meta>` element, and the `itemprop` attribute must not be set on the same `<meta>` element that
    has any existing [`name`](/en/webfrontend/<meta>_name_attribute), [`http-equiv`](/en/webfrontend/<meta>_http-equiv_attribute)
    or [`charset`](/en/webfrontend/<meta>_charset_attribute) attributes.

| Attribute | Description |
| :-- | :-- |
| **[`charset`](/en/webfrontend/<meta>_charset_attribute)** | This attribute declares the page's **[[character encoding]]**. |
| **[`http-equiv`](/en/webfrontend/<meta>_http-equiv_attribute)** | Defines a **HTTP pragma directive**. The attribute is named *"`http-equiv`(alent)"* because all the allowed values are names of particular **HTTP headers**. |
| **[`name`](/en/webfrontend/<meta>_name_attribute)** | This attribute defines the **name of a piece of document-level metadata**. It should not be set if one of the attributes `itemprop`, [`http-equiv`](/en/webfrontend/<meta>_http-equiv_attribute) or [`charset`](/en/webfrontend/<meta>_charset_attribute) is also set. |
| **`content`** | This attribute contains the value for the [`http-equiv`](/en/webfrontend/<meta>_http-equiv_attribute) or [`name`](/en/webfrontend/<meta>_name_attribute) attribute, depending on which is used. |

## Notes

Depending on the attributes set, the kind of metadata can be one of the following:

- If [`name`](/en/webfrontend/<meta>_name_attribute) is set, it is document-level metadata, applying
  to the whole page.
- If [`http-equiv`](/en/webfrontend/<meta>_http-equiv_attribute) is set, it is a pragma directive —
  information normally given by the web
server about how the web page is served.
- If [`charset`](/en/webfrontend/<meta>_charset_attribute) is set, it is a charset declaration — the
  character encoding used by the webpage.
- If `itemprop` is set, it is user-defined metadata — transparent for the user-agent as the
semantics of the metadata is user-specific.

## Example

```html
<html>
<head>
<meta charset="utf-8">
<title>Dookbook</title>
<!--Define web page description:-->
<meta name="description" content="Developers' Cookbook ">
<!--Define document keywords for search engines:-->
<meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">
<!--Define page author:-->
<meta name="author" content="dookbook">
</head>
<body>
<p>All meta tags are displayed in the head section</p>
</body>

```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<meta>`| support | support | support |
