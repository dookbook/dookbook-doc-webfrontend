TOPICS: <img>
        <img> src attribute
        <img> alt attribute
        <img> width attribute
        <img> height attribute
        <img> srcset attribute
        <img> sizes attribute
        <img> usemap attribute

# HTML Image Element: `<img>`

The **HTML `<img>` element** embeds an **image** into the document. It is a *replaced element*.

!!! warn "Prompt"
    Technically, images are not inserted into HTML pages, but instead are linked to HTML pages. The
    `<img>` tag is used to create placeholders for the referenced image.
    Add an image to a link to another document by nesting `<img>` tags within the [`<a>`](/en/webfrontend/<a>)
    tag.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content Categories** | *Flow Content*, *Phrasing Content*, *Embedded Content*, *Palpable Content*. If the element has a *[`usemap`](/en/webfrontend/<map>)* attribute, it also is a part of the *interactive content* category.|
| **Permitted Content** | None, it is an **[empty element](/en/webfrontend/empty_element)**.|
| **Tag Omission** | Must have a start tag and must not have an end tag.|
| **Permitted parents** | Any element that accepts *embedded content*.|
| **Permitted ARIA roles** | Any |
| **DOM Interface** | **`HTMLImageElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_attributes).

| Attribute | Description |
| :-- | :-- |
| **`src`** | (**required**) The image URL. This attribute is mandatory for the `<img>` element. On browsers supporting `srcset`, `src` is treated like a candidate image with a pixel density descriptor `1x` unless an image with this pixel density descriptor is already defined in `srcset`, or unless `srcset` contains `w` descriptors. |
| **`alt`** | This attribute defines an **alternative text description** of the image, which isn't mandatory but is incredibly useful for accessibility — screen readers read this description out to their users so they know what the image shows, and it is also displayed on the page if the image can't be loaded for some reason. |
| **`width`** | The intrinsic **width** of the image *in pixels*. |
| **`height`** | The intrinsic **height** of the image *in pixels*. |
| **`srcset`** | A list of one or more strings *separated by commas* indicating **a set of possible image sources** for the user agent to use. |
| **`sizes`** | A list of one or more strings *separated by commas* indicating **a set of source sizes**. If the `srcset` attribute is absent, or contains no values with a width (`w`) descriptor, then the `sizes` attribute has no effect. |
| **`usemap`** | The partial URL (starting with `'#'`) of an **image map** associated with the element.<br>Note: **You cannot use this attribute if the `<img>` element is a descendant of an [`<a>`](/en/webfrontend/<a>) or [`<button>`](/en/webfrontend/<button>) element.** See [`<map>` and `<area>`](/en/webfrontend/<map>) elements. |
| `crossorigin` |This enumerated attribute indicates if the fetching of the related image must be done using CORS or not. CORS-enabled images can be reused in the [`<canvas>`](/en/webfrontend/<canvas>) element without being "tainted." The allowed values are: |
| `ismap` | This Boolean attribute indicates whether the image is part of a server-side `map`.If so, the exact coordinates of the click will be sent to the server.<br>**Instructions for use:**<br>This attribute is only allowed if the `<img>` element is a descendant of a `<a>` element with a valid `href` attribute. |

### Deprecated attribute

| Attribute | Description |
| :-- | :-- |
| ~~`align`~~ |（**Obsolete**）Aligns the image with its surrounding context. Use the **`float` and/or `vertical-align`** CSS properties instead of this attribute.|
| ~~`border`~~ |（**Obsolete**）The width of a border around the image. Use the **`border`** CSS property instead.|
| ~~`hspace`~~ |（**Obsolete**）The number of pixels of white space on the left and right of the image. Use the **`margin`** CSS property instead.|
| ~~`longdesc`~~ |（**Obsolete**）A link to a more detailed description of the image. Possible values are a URL or an element `id`.<br> *Note: This attribute is mentioned in the latest W3C version, HTML 5.2, but has been removed from the WHATWG’s [HTML Living Standard](https://html.spec.whatwg.org/multipage/embedded-content.html#the-img-element) . It has an uncertain future; authors should use a WAI-ARIA alternative such as `aria-describedby` or `aria-details`. |
| ~~`name`~~ |（**Obsolete**）A name for the element. Use the **`id` attribute** instead.|
| ~~`vspace`~~ |（**Obsolete**）The number of pixels of white space above and below the image. Use the `margin` CSS property instead.|

### Anonymous

A cross-origin request (i.e., with `Origin` HTTP header) is performed, but no credential is sent
(i.e., no cookie, X.509 certificate, or HTTP Basic authentication). If the server does not
give credentials to the origin site (by not setting the `Access-Control-Allow-Origin` HTTP header),
the image will be tainted and its usage restricted.

### Use-Credentials

A cross-origin request (i.e., with the `Origin` HTTP header) performed along with credentials
sent (i.e., a cookie, certificate, or HTTP Basic authentication). If the server does not give
credentials to the origin site (through the `Access-Control-Allow-Credentials` HTTP header),
the image will be tainted and its usage restricted.

If the attribute is not present, the resource is fetched without a CORS request (i.e., without
sending the `Origin` HTTP header), preventing its non-tainted usage in [`<canvas>`](/en/webfrontend/<canvas>)
elements. If invalid, it is handled as if the `anonymous` value was used. See CORS settings attributes
for additional information.

| Attribute | Description |
| :-- | :-- |
| `decoding` | Provides an image decoding hint to the browser. The allowed values are:<br>`sync`<br>1、Decode the image synchronously for atomic presentation with other content.<br>`async`<br>1、Decode the image asynchronously to reduce delay in presenting other content.<br>`auto`<br>1、Default mode, which indicates no preference for the decoding mode. The browser decides what is best for the user.<br>`height`<br>1、The intrinsic height of the image in pixels.<br>`importance`<br>1、Indicates the relative importance of the resource. Priority hints are delegated using the values:<br>1、`auto`: Indicates **no preference**. The browser may use its own heuristics to decide the priority of the image.<br>2.`high`: Indicates to the browser that the image is of **high** priority.<br>3.`low`: Indicates to the browser that the image is of **low** priority. |
| `intrinsicsize` | This attribute tells the browser to ignore the actual intrinsic size of the image and pretend it’s the size specified in the attribute. Specifically, the image would raster at these dimensions and `naturalWidth`/`naturalHeight` on images would return the values specified in this attribute. Explainer, examples
| `ismap` | This Boolean attribute indicates that the image is part of a server-side map. If so, the precise coordinates of a click are sent to the server.<br>**Note:** This attribute is allowed only if the `<img>` element is a descendant of an [`<a>`](/en/webfrontend/<a>) element with a valid `href` attribute.
| `referrerpolicy` | A string indicating which referrer to use when fetching the resource:<br>1、`no-referrer`: The `Referer` header will not be sent.<br>2、`no-referrer-when-downgrade`: No Referer header will be sent when navigating to an origin without TLS (HTTPS). This is a user agent’s default behavior if no policy is otherwise specified.<br>3、`origin`: The Referer header will include the page of origin's scheme, the host, and the port.<br>4、`origin-when-cross-origin`: Navigating to other origins will limit the included referral data to the scheme, the host and the port, while navigating from the same origin will include the referrer's full path.<br>5、`unsafe-url`: The Referer header will include the origin and the path, but not the fragment, password, or username. This case is unsafe because it can leak origins and paths from TLS-protected resources to insecure origins.

There are many other attributes that can be specified to achieve various purposes, for example:

- Referrer/CORS control for security purposes; see `crossorigin` and `referrerpolicy`.

## Basic Usage

!!! warn "**`alt`** Usage"
    Browsers do not always display the image referenced by the element.
    This is the case for non-graphical browsers
    (including those used by people with visual impairments), if the user chooses not to display images,
    or if the browser cannot display the image because it is invalid or an unsupported type.
    In these cases, the browser may replace the image with the text defined in this element's
    **`alt`** attribute.
    You should, for these reasons and others, provide a useful value for `alt` whenever possible.

!!! warn "Note"
    Omitting **`alt`** attribute altogether indicates that the image is a key part of the content,
    and no textual equivalent is available. Setting this attribute to an empty string (`alt=""`)
    indicates that this image is not a key part of the content (decorative),and that non-visual browsers
    may omit it from rendering.

The following simple example embeds an image into the page, and includes alternative
text to improve accessibility.

```html
<img src="https://dookbook.info/static/img/logo-tail.svg" alt="Dookbook logo">

<!-- absolute path of local filesystem  -->
<img src="/static/img/logo-tail.svg" alt="Dookbook logo">

<!-- relative path of local filesystem -->
<img src="static/img/logo-tail.svg" alt="Dookbook logo">
```

## Supported Image Formats

The HTML standard doesn't give a list of image formats that must be supported, so each user agent
supports a different set of formats.

| UA | Supported Image Formats |
| :-- | :-- |
| [Chrome](/en/glossary/Google_Chrome) | [[PNG]], [[JPEG]], [[GIF]] (including animated GIFs), [BMP](http://en.wikipedia.org/wiki/BMP_file_format), [ICO](http://en.wikipedia.org/wiki/ICO_%28file_format%29), [[WebP]], [[SVG]], APNG |
| [Safari](/en/glossary/Apple_Safari) | [[PNG]], [[JPEG]], [[GIF]] (including animated GIFs), [BMP](http://en.wikipedia.org/wiki/BMP_file_format), [ICO](http://en.wikipedia.org/wiki/ICO_%28file_format%29), ~~WebP~~, [[SVG]], APNG |
| Firefox | [[PNG]], [[JPEG]], [[GIF]] (including animated GIFs), [BMP](http://en.wikipedia.org/wiki/BMP_file_format), [ICO](http://en.wikipedia.org/wiki/ICO_%28file_format%29), [[WebP]], [[SVG]], APNG|

## Image Loading Errors

If an error occurs while trying to load or render an image, and an `onerror` event handler has
been configured to handle the `error` event, that event handler will get called. This can happen
in a number of situations, including:

- The `src` attribute is empty or [null](/en/glossary/null/).
- The specified `src` URL is the same as the URL of the page the user is currently on.
- The specified image is corrupted in some way that prevents it from being loaded.
- The specified image's metadata is corrupted in such a way that it's impossible to retrieve its
dimensions, and no dimensions were specified in the `<img>` element's attributes.
- The specified image is in a format not supported by the user agent.

## Image Link

This example shows how to turn the image into a link.

```html
<a href="https://dookbook.info">
  <img src="https://dookbook.info/static/img/logo-tail.svg" alt="Visit the Dookbook site">
</a>
```

## Image with Specified Height and Width

Use the **`height`** and **`width`** properties to specify the image height and width.

```html
<img src="https://dookbook.info/static/img/logo-tail.svg" alt="Dookbook Logo" height="128" width="256">
```

## Using the `srcset` attribute

Value of **`srcset`** attribute is a list of one or more strings *separated by commas* indicating
**a set of possible image sources** for the user agent to use. Each string  is composed of:

1. a URL to an image
2. optionally, whitespace followed by one of:
    - **A width descriptor**, or a positive integer directly followed by **`w`**.
      The width descriptor is divided by the source size given in the *`sizes`* attribute to
      calculate the effective pixel density.
    - **A pixel density descriptor**, which is a positive floating point number directly followed by
      **`x`**.
    - If no descriptor is specified, the source is assigned the default descriptor: `1x`.

It is incorrect to mix width descriptors and pixel density descriptors in the same `srcset`
attribute. Duplicate descriptors (for instance, two sources in the same `srcset` which are both
described with `2x`) are also invalid.

The user agent selects any one of the available sources at its discretion. This provides them with
significant leeway to tailor their selection based on things like user preferences or [[bandwidth]] conditions.

In this example we include a **`srcset`** attribute containing a reference to a high-resolution version
of the logo; this will be loaded instead of the `src` image on high-resolution devices. The image
referenced in the `src` attribute is counted as a `1x` candidate in user agents that support `srcset`.

```html
<img src="dookbook-logo-tail.svg" alt="Dookbook Logo" srcset="dookbook-logo-tail.svg 2x">
```

## Responsive Image Hints Using `sizes` and `srcset` Attributes

Value of **`sizes`** attribute is a list of one or more strings *separated by commas* indicating
**a set of source sizes**. Each source size consists of

1. a **media condition**. This must be omitted for the last item.
2. a **source size value**. Source size values specify the intended display size of the image.
   User agents use the current source size to select one of the sources supplied by the `srcset`
   attribute, when those sources are described using *width descriptors* (*`w`*) . The selected
   source size affects the intrinsic size of the image (the image’s display size if no CSS styling
   is applied).

The `src` attribute is ignored in user agents that support `srcset` when *`w`* descriptors are
included. When the (`max-width: 600px`) media condition matches, the `200px` wide image will be loaded
(it is the one that matches `200px` most closely), otherwise the other image will be loaded.

```html
<img src="logo-200.png"
     alt="Logo"
     srcset="logo-200.png 200w,logo-400.png 400w"
     sizes="(max-width: 600px) 200px, 50vw">
```

See the [`<picture>`](/en/webfrontend/<picture>) element.

## Accessibility Concerns

### Authoring meaningful alternate descriptions (`alt` attribute)

An **`alt`** attribute's value should clearly and concisely describe the image's content. It should not
describe the presence of the image itself, or the file name of the image. If the `alt` attribute is
purposefully left off because the image has no textual equivalent, consider alternate methods for
presenting the content the image is trying to communicate.

Don't

```html
<img alt="An image" src="logo.jpg">
```

Do

```html
<img alt="A Logo" src="logo.jpg">
```

When an `alt` attribute is not present on an image, some screen readers may announce the image's
*file name* instead. This can be a confusing experience if the file name
isn't representative of the image's contents.

### The `title` attribute

The **[`title`](/en/webfrontend/title_attribute)** attribute is not an acceptable substitute for an
*`alt`* attribute. Additionally,
avoid duplicating the `alt` attribute's value in a `title` attribute declared on the same image.
Doing so may cause some screen readers to announce the description twice, creating a confusing experience.

The `title` attribute should also not be used as supplemental captioning information to
accompany an image's `alt` description. If an image needs a caption, use a combination of the
*[`<figure>`](/en/webfrontend/<figure>)* and *[`<figcaption>`](/en/webfrontend/<figcaption>)* elements.

### Difference between `alt` and `title` attributes

The ** `alt` attribute ** in the picture is a text prompt that appears when the picture is not
displayed properly.

The **[`title`](/en/webfrontend/title_attribute)**  property in the image is a text hint when the
mouse is moved over the element.

## Styling With CSS

`<img>` is a replaced element; it has a `display` value of `inline` by default,
but its default dimensions are defined by the embedded image's intrinsic values. You can set
properties like `border`/`border-radius`, `padding`/`margin`,
`width`/`height`, etc. on an image.

Often however it is a good idea to set images to `display: block;` so that you have maximum control
over the styling (e.g. `margin: 0 auto` doesn't work on inline images, and it is easier to place
images in context with surrounding elements when they are block-level).

`<img>` has no baseline, so when images are used in an inline formatting context with
`vertical-align: baseline`, the bottom of the image will be placed on the container's baseline.

You can use the `object-position` property to position the image within the element's box,
and the `object-fit` property to adjust the sizing of the image within the box (for example,
whether the image should fit the box or fill it even if clipping is required).

Depending on its *type*, an image may have an intrinsic *width* and *height*. For some image types, however,
intrinsic dimensions are not necessary. SVG images, for instance, may have no intrinsic dimensions if
their root [`<svg>`](/en/webfrontend/<svg>) element doesn't have a `width` or `height` set on it.
