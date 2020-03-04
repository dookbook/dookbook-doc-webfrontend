TOPICS: <link>
        <link> href attribute
        <link> rel attribute
        <link> type attribute
        <link> sizes attribute
        <link> media attribute
        <link> title attribute
        <link> as attribute
        <link> disabled attribute
        <link> importance attribute
        <link> integrity attribute
        <link> hreflang attribute

# HTML External Resource Link Element: `<link>`

The **HTML External Resource Link element (`<link>`)** specifies relationships between the current
document and an **external resource**. This element is most commonly used to link to **stylesheets**,
but is also used to establish site icons (both "**favicon**" style icons and icons for the **home screen**
and **apps** on mobile devices) among other things.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Metadata content*. If `itemprop` is present: *flow content* and *phrasing content*. |
| **Permitted content** | None, it is an empty element. |
| **Tag omission** | As it is a void element, the start tag must be present and the end tag must not be present |
| **Permitted parents** | Any element that accepts metadata elements. If `itemprop` is present: any element that accepts phrasing content. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLLinkElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`href`** | This attribute specifies **the URL of the linked resource**. A [[URL]] can be *absolute* or *relative*.
| **`rel`** | Specifies the **relationship** between the current document and the linked document/resource. |
| *`type`* | This attribute is used to define the type of content of the link. The value of this attribute should be a MIME type like `text/html`, `text/css`. The common usage of this attribute is to define the linked style sheet. The most commonly used value is `text/css` indicating CSS. |
| *`sizes`* | The link attribute size is defined and only works for the attribute `rel =" icon "`. It may have the following values: <br>1. `any`, which means that the icon can be scaled to any size ** in vector format, such as `image/svg+xml`. <br>2. A space-separated list, the format of each list is `sizes="16x16"` or `sizes="16x16 32x32"`. |
| *`media`* | Specifies on which device the linked document will be displayed. |
| *`title`* | This attribute has special semantics on the `<link>` element. When used on a `<link rel="stylesheet">` it defines a **preferred** or an **alternate stylesheet**. Incorrectly using it may cause the stylesheet to be ignored. |
| `as` | This attribute is only used when rel="preload" or rel="prefetch" has been set on the `<link>` element. It specifies the type of content being loaded by the `<link>`, which is necessary for content prioritization, request matching, application of correct content security policy, and setting of correct Accept request header. |
| `disabled` |For `rel="stylesheet"` only, the `disabled` Boolean attribute indicates whether or not the described stylesheet should be loaded and applied to the document. If `disabled` is specified in the HTML when it is loaded, the stylesheet will not be loaded during page load. Instead, the stylesheet will be loaded on-demand, if and when the `disabled` attribute is changed to `false` or removed.<br>Once the stylesheet has been loaded, however, changes made to the value of the `disabled` property no longer have any relationship to the value of the `StyleSheet.disabled` property. Changing the value of this property instead simply enables and disables the stylesheet form being applied to the document.<br>This differs from `StyleSheet'`s `disabled` property; changing it to `true` removes the stylesheet from the document's `document.styleSheets` list, and doesn't automatically reload the stylesheet when it's toggled back to `false`. |
| `importance` | Indicates the relative importance of the resource. Priority hints are delegated using the values:<br>**`auto`**: Indicates no preference. The browser may use its own heuristics to decide the priority of the resource.<br>**`high`**: Indicates to the browser that the resource is of high priority.<br>**`low`**: Indicates to the browser that the resource is of low priority.<br>**Note:** The `importance` attribute may only be used for the `<link>` element if `rel="preload"` or `rel="prefetch"` is present. |
| `integrity` | Contains inline metadata — a base64-encoded cryptographic hash of the resource (file) you’re telling the browser to fetch. The browser can use this to verify that the fetched resource has been delivered free of unexpected manipulation. See Subresource Integrity. |
| `hreflang` | This attribute indicates the language of the linked resource. It is purely advisory. Allowed values are determined by BCP47. Use this attribute only if the href attribute is present. |

### Non-standard attributes

| Attribute | Description |
| :-- | :-- |
| `methods` |The value of this attribute provides information about the functions that might be performed on an object. The values generally are given by the HTTP protocol when it is used, but it might (for similar reasons as for the `title` attribute) be useful to include advisory information in advance in the link.</br> For example, the browser might choose a different rendering of a link as a function of the methods specified; something that is searchable might get a different icon, or an outside link might render with an indication of leaving the current site. This attribute is not well understood nor supported, even by the defining browser, Internet Explorer 4.|
| `prefetch` | This attribute identifies a resource that might be required by the next navigation and that the user agent should retrieve it. This allows the user agent to respond faster when the resource is requested in the future.|

### Outdated

| Attribute | Description |
| :-- | :-- |
| `charset` | **HTML5 is not supported.** Defines the character encoding of the linked document.|
| `rev` | **HTML5 is not supported.** Defines the relationship between the linked document and the current document.|
| `target` | **HTML5 is not supported.** Defines where to load the linked document.|

## The value of `rel` of `<link>`

| Value | Description |
| :-- | :-- |
| `stylesheet` | The URL of the style sheet to import. |
| `icon` | Import the icon representing the document. |
| `prefetch` | Specifies that the target resource should be cached. |
| `search` | Link to a search tool for documents. |
| `alternate` | Link to an alternative version of the document (such as a printed page, translation, or mirror). |
| `author` | Link to the author of the document. |
| `help` | Link to help documentation. |
| `license` | Link to copyright information for this document. |
| `next` | Indicates that the document is part of a collection and the next document in the collection is the referenced document. |
| `prev` | Indicates that the document is part of a collection and the previous document in the collection is the referenced document. |

## Including a stylesheet

To link an external stylesheet, you'd include a `<link>` element inside your [`<head>`](/en/webfrontend/<head>)
to include a stylesheet in a page, and use the following syntax:

```html
<head>
  <link href="style.css" rel="stylesheet">
</head>
```

This simple example provides the path to the `stylesheet` inside an `href` attribute, and a `rel`
attribute with a value of `stylesheet`.

## Providing alternative stylesheets

You can also specify alternative style sheets.

The user can choose which style sheet to use by choosing it from browsers' menu.
This provides a way for users to see multiple versions of a page.

```html
<link href="default.css" rel="stylesheet" title="Default Style">
<link href="fancy.css" rel="alternate stylesheet" title="Fancy">
<link href="basic.css" rel="alternate stylesheet" title="Basic">
```

## Providing icons for different usage contexts

You can include links to several different icons on the same page, and the browser will choose which
one works best for its particular context using the `rel` and `sizes` values as hints.

!!! info "Note"
    Most icon formats are only able to store one single icon; therefore most of the time the
    sizes contains only one entry. MS's ICO format does, as well as Apple's ICNS. ICO is more ubiquitous;
    you should definitely use it.

```html
<!-- third-generation iPad with high-resolution Retina display: -->
<link rel="apple-touch-icon-precomposed" sizes="144x144" href="favicon144.png">

<!-- iPhone with high-resolution Retina display: -->
<link rel="apple-touch-icon-precomposed" sizes="114x114" href="favicon114.png">

<!-- first- and second-generation iPad: -->
<link rel="apple-touch-icon-precomposed" sizes="72x72" href="favicon72.png">

<!-- non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
<link rel="apple-touch-icon-precomposed" href="favicon57.png">

<!-- basic favicon -->
<link rel="icon" href="favicon32.png">
```

## Conditionally loading resources with media queries

You can provide a media type or query inside a `media` attribute; this resource will then only be
loaded if the media condition is true. For example:

```html
<link href="print.css" rel="stylesheet" media="print">
<link href="mobile.css" rel="stylesheet" media="all">
<link href="desktop.css" rel="stylesheet" media="screen and (min-width: 600px)">
<link href="highres.css" rel="stylesheet" media="screen and (min-resolution: 300dpi)">
```

## Stylesheet Load Events

You can determine when a style sheet has been loaded by watching for a load event to fire on it;
similarly, you can detect if an error has occurred while processing a
style sheet by watching for an `error` event:

```html
<script>
var myStylesheet = document.querySelector('#my-stylesheet');

myStylesheet.onload = function() {
  // Do something interesting; the sheet has been loaded
}

myStylesheet.onerror = function() {
  console.log("An error occurred loading the stylesheet!");
}
</script>

<link rel="stylesheet" href="mystylesheet.css" id="my-stylesheet">
```

!!! warn "Note"
    The `load` event fires once the stylesheet and all of its imported content has been loaded and parsed,
    and immediately before the styles start being applied to the content.

## `<link>` `media` value

### Device

| Value | Description |
| :-- | :-- |
| `all` | *Default.* Suitable for all devices.|
| `aural` | Speech synthesizer.|
| `braille` | Braille feedback device.|
| `handheld` | Handheld device (small screen, limited bandwidth).|
| `projection` | projector.|
| `print` | Print preview mode/print page.|
| `screen` | Computer screen.|
| `tty` | Teletypes and similar media using monospaced character grids.|
| `tv` | TV type equipment (low resolution, limited scrolling capabilities).|

### Value

| Value | Description |
| :-- | :-- |
| `width` | Specifies the width of the target display area.|
| `height` | Specifies the height of the target display area.|
| `device-width` | Specifies the width of the target display/paper.|
| `device-height` | Specifies the heigh of the target display/paper.|
| `aspect-ratio` |Specifies the width/height ratio of the target display area.</br>Such as:`media="screen and (aspect-ratio:16/9)"`.|
| `device-aspect-ratio` | Specifies the `device-width`/`device-height` ratio of the target display/paper.|
| `color` | Specifies the `bits`/`color` of the target display.|
| `color-index` | Specifies the number of colors that the target display can handle.|
| `monochrome` | Specifies the `bits`/`pixel` in the monochrome frame buffer.</br>Such as:`media="screen and (monochrome:2)"`. |
| `resolution` | Specifies the pixel density (dpi or dpcm) of the target `display`/`paper`.</br>Such as:`media="print and (resolution:300dpi)"`.|
The above values can be prefixed with "`min-`" and "`max-`".
Such as:`media="screen and (min-width:500px)"`或`media="screen and (max-color-index:256)"`.

| Value | Description |
| :-- | :-- |
| `orientation` | Specifies the orientation of the target display/paper. Possible values: "`portrait`" or "`landscape`".</br>Such as:`media="all and (orientation: landscape)"`.|
| `scan` | Specifies the scanning method for `tv` displays. Possible values: "`progressive`" and "`interlace`".</br>Such as:`media="tv and (scan:interlace)"`.|
| `grid` | 规Specifies whether the output device is a grid or a bitmap. Possible values: "1" is the grid, otherwise "0".</br>Such as:`media="handheld and (grid:1)"`.|
