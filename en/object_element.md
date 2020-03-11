TOPICS: <object>

# HTML Embed Object Element: `<object>`

The **HTML embed object element** (**`<object>`**) represents an external resource,
which can be treated as an *image* (use *[`img`](/en/webfrontend/<img>)* instead),
a *nested browsing context*, or *a resource to be handled by a plugin*.

The original purpose of `object` is to replace the [`img`](/en/webfrontend/<img>) and
[`applet`](/en/webfrontend/<applet>) elements. However, this was **not achieved** due to
vulnerabilities and lack of browser support.

Browser object support depends on *the object type*. Unfortunately, mainstream browsers all use
different code to load the same object type.
Fortunately, the `object` object provides the solution. If the `object` element is not displayed,
the code between `<object>` and `</ object>` is executed. In this way, we can *nest multiple `object`
elements (one for each browser)*.
|  |  |
| :-- | :-- |
| **Content categories** | Flow content; phrasing content; embedded content, palpable content; if the element has a `usemap` attribute, interactive content; listed, submittable form-associated element.|
| **Permitted content** | zero or more [`<param>`](/en/webfrontend/<param>) elements, then transparent.|
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts embedded content.|
| **Permitted ARIA roles** | `application`, `document`, `image` |
| **DOM interface** | `HTMLObjectElement` |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `data` | The address of the resource as a valid URL. At least one of `data` and `type` must be defined.
| `form` | The form element, if any, that the object element is associated with (its form owner). The value of the attribute must be an ID of a `<form>` element in the same document.
| `height` | The height of the displayed resource, in CSS pixels. -- (Absolute values only. NO percentages)
| `name` | The name of valid browsing context (HTML5), or the name of the control (HTML 4).
| `type` | The content type of the resource specified by data. At least one of data and type must be defined.
| `typemustmatch` | This Boolean attribute indicates if the `type` attribute and the actual content type of the resource must match to be used.
| `usemap` | A hash-name reference to a [`<map>`](/en/webfrontend/<map>) element; that is a '#' followed by the value of a `name` of a `map` element.
| `width` | The width of the display resource, in CSS pixels. -- (Absolute values only. NO percentages)

### Obsolete attributes

| Attribute | Description |
| :-- | :-- |
| ~~`archive`~~ | **Obsolete**,A space-separated list of URIs for archives of resources for the object. |
| ~~`border`~~ | **Obsolete**,The width of a border around the control, in pixels. |
| ~~`classid`~~ | **Obsolete**,The URI of the object's implementation. It can be used together with, or in place of, the **`data` attribute**.|
| ~~`codebase`~~ | **Obsolete**,The base path used to resolve relative URIs specified by `classid`, `data`, or `archive`. If not specified, the default is the base URI of the current document. |
| ~~`codetype`~~ | **Obsolete**,The content type of the data specified by `classid`. |
| ~~`declare`~~ | **Obsolete**,The presence of this Boolean attribute makes this element a declaration only. The object must be instantiated by a subsequent `<object>`element. In HTML5, repeat the `<object>` element completely each that that the resource is reused. |
| ~~`standby`~~ | **Obsolete**,A message that the browser can show while loading the object's implementation and data. |
| ~~`tabindex`~~ | **Obsolete**,The position of the element in the tabbing navigation order for the current document. |

## Examples

### Embed a flash movie

```html
<!-- Embed a flash movie -->
<object data="movie.swf"
  type="application/x-shockwave-flash"></object>

<!-- Embed a flash movie with parameters -->
<object data="movie.swf" type="application/x-shockwave-flash">
  <param name="foo" value="bar">
</object>
```
