TOPICS: <source>

# `<source>`

The **HTML `<source>` element** specifies multiple media resources for the [`<picture>`](/en/webfrontend/<picture>),
the [`<audio>`](/en/webfrontend/<audio>) element, or the [`<video>`](/en/webfrontend/<video>) element.
It is an **empty element**, meaning that it has no content and does not have a closing tag. It is
commonly used to serve the same media content in multiple formats supported by different browsers.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | None. |
| **Permitted content** | None, it is an empty element. |
| **Tag omission** | It must have start tag, but must not have an end tag. |
| **Permitted parents** | A media element—[`<audio>`](/en/webfrontend/<audio>) or [`<video>`](/en/webfrontend/<video>)—and it must be placed before any flow content or [`<track>`](/en/webfrontend/<track>) element. <br>A [`<picture>`](/en/webfrontend/<picture>) element, and it must be placed before the `<img>` element. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLSourceElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `sizes` | Is a list of source sizes that describes the final rendered width of the image represented by the source. Each source size consists of a comma-separated list of media condition-length pairs. This information is used by the browser to determine, before laying the page out, which image defined in `srcset` to use.<br>The `sizes` attribute has an effect only when the `<source>` element is the direct<br>child of a [`<picture>`](/en/webfrontend/<picture>) element. |
| `src` | Required for [`<audio>`](/en/webfrontend/<audio>) and [`<video>`](/en/webfrontend/<video>), address of the media resource. The value of this attribute is ignored when the `<source>` element is placed inside a [`<picture>`](/en/webfrontend/<picture>) element. |
| `srcset` | A list of one or more strings separated by commas indicating a set of possible images represented by the source for the browser to use. Each string is composed of:<br>1. one URL to an image,<br>2. a width descriptor, that is a positive integer directly followed by `'w'`. The default value, if missing, is the infinity.<br>3. a pixel density descriptor, that is a positive floating number directly followed by `'x'`. The default value, if missing, is `1x`.<br><br>Each string in the list must have at least a width descriptor or a pixel density descriptor to be valid. Among the list, there must be only one string containing the same tuple of width descriptor and pixel density descriptor.<br>The browser chooses the most adequate image to display at a given point of time.<br>The srcset attribute has an effect only when the `<source>` element is the direct<br>child of a [`<picture>`](/en/webfrontend/<picture>) element. |
| `type` | The MIME-type of the resource, optionally with a `codecs` parameter. See RFC 4281 for information about how to specify codecs. |
| `media` | Media query of the resource's intended media; this should be used only in a [`<picture>`](/en/webfrontend/<picture>) element.<br>If the `type` attribute isn't specified, the media's type is retrieved from the server and checked to see if the user agent can handle it; if it can't be rendered, the next `<source>` is checked. If the `type` attribute is specified, it's compared against the types the user agent can present, and if it's not recognized, the server doesn't even get queried; instead, the next `<source>` element is checked at once. |

## Examples

### Video Example

This example demonstrates how to offer a video in Ogg format for users whose browsers support
Ogg format, and a QuickTime format video for users whose browsers support that. If the `audio` or
`video` element is not supported by the browser, a notice is displayed instead.  If the browser
supports the element but does not support any of the specified formats, an `error` event is raised
and the default media controls (if enabled) will indicate an error. See Also the list of
media formats supported by the audio and video elements in various browsers.

```html
<video controls>
  <source src="foo.webm" type="video/webm">
  <source src="foo.ogg" type="video/ogg">
  <source src="foo.mov" type="video/quicktime">
  I'm sorry; your browser doesn't support HTML5 video.
</video>
```

For more examples, see Using audio and video in Firefox.

### Picture Example

```html
<picture>
   <source srcset="mdn-logo-wide.png" media="(min-width: 800px)">
   <source srcset="mdn-logo-medium.png" media="(min-width: 600px)">
   <img src="mdn-logo-narrow.png" alt="MDN">
</picture>
```

With the [`<picture>`](/en/webfrontend/<picture>) element, you must always include an
[`<img>`](/en/webfrontend/<img>) with a fallback image, with an `alt` attribute to ensure accessibility.
