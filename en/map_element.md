TOPICS: <map>
        <area>
        <map> name attribute
        <area> href attribute
        <area> shape attribute
        <area> coords attribute
        <area> target attribute
        <area> rel attribute
        <area> download attribute
        <area> type attribute
        <area> hreflang attribute
        <area> ping attribute

# HTML Image Map: `<map>` and `<area>`

The **HTML `<map>` element** is used with **`<area>`** elements to define an
**image map** (a *clickable link area*).

The **HTML `<area>` element** defines a **hot-spot region** on an image, and optionally associates it
with a **hypertext link**. This element is used only within a *`<map>`* element.

## Technical Summary for `<map>`

|  |  |
| :-- | :-- |
| **Content Categories** | *Flow content*, *phrasing content*, *palpable content*. |
| **Permitted content** | Any *transparent* element. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLMapElement`** |

## Technical Summary for `<area>`

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*.|
| **Permitted content** | None, it is an **[[empty element]]**.|
| **Tag omission** | Must have a start tag and must not have an end tag.|
| **Permitted parents** | Any element that accepts *phrasing content*. The `<area>` element must have an ancestor `<map>`, but it need not be a direct parent. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLAreaElement`** |

## Attributes of `<map>`

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`name`** | The attribute gives the map a name so that it can be referenced. The attribute **must be present** and must have a non-empty value with **no space characters**. The value of the `name` attribute must not be a compatibility-caseless match for the value of the `name` attribute of another `<map>` element in the same document. **If the *`id`* attribute is also specified, both attributes must have the same value.**

## Attributes of `<area>`

| Attribute | Description |
| :-- | :-- |
| **`href`** | The **hyperlink target for the area**. Its value is a valid [[URL]]. In HTML 4, either this attribute or the *`nohref`* attribute must be present in the element. In HTML 5, this attribute may be omitted; if so, the area element does not represent a hyperlink. |
| **`alt`** | A **text string alternative** to display on browsers that do not display images. The text should be phrased so that it presents the user with the same kind of choice as the image would offer when displayed without the alternative text. In HTML 4, this attribute is required, but may be the empty string (`""`). In HTML 5, this attribute is required only if the *`href`* attribute is used. |
| **`shape`** | The **shape of the associated hot spot**. |
| **`coords`** | A set of values specifying the **coordinates of the hot-spot region**. The number and meaning of the values depend upon the value specified for the *`shape`* attribute. |
| `target` | This attribute specifies **where to display the linked resource**. See *[`<a>`](/en/webfrontend/<a>)* for a full description of the `target` attribute. |
| `rel` | For anchors containing the *`href`* attribute, this attribute specifies the **relationship of the target object to the link object**. See *[`<a>`](/en/webfrontend/<a>)* for a full description of the `rel` attribute. |
| `download` | This attribute, if present, indicates that the author intends the hyperlink to be used for **downloading a resource**. See *[`<a>`](/en/webfrontend/<a>)* for a full description of the `download` attribute. |
| `type` | Specifies **the media type in the form of a [[MIME]] type** for the linked URL. *It is purely advisory, with no built-in functionality*. |
| `hreflang` | Indicates the **language of the linked resource**. See *[`<a>`](/en/webfrontend/<a>)* for a full description of the `hreflang` attribute. |
| `ping` | Contains a *space-separated* list of URLs to which, when the hyperlink is **followed**, `POST` requests with the body PING will be sent by the browser (in the background). Typically used for **tracking**. Same with the `ping` attribute of [`<a>`](/en/webfrontend/<a>) |
| `referrerpolicy` | A string indicating which referrer to use when fetching the resource:<br>`"no-referrer"` meaning that the Referer: header will not be sent.<br>`"no-referrer-when-downgrade"` meaning that no `Referer:` header will be sent when navigating to an origin without TLS (HTTPS). This is a user agent’s default behavior, if no policy is otherwise specified.<br>`"origin"` meaning that the referrer will be the origin of the page, that is roughly the scheme, the host and the port.<br>`"origin-when-cross-origin"` meaning that navigations to other origins will be limited to the scheme, the host and the port, while navigations on the same origin will include the referrer's path.<br>`"unsafe-url"` meaning that the referrer will include the origin and the path (but not the fragment, password, or username). This case is unsafe because it can leak origins and paths from TLS-protected resources to insecure origins.

## Values of `shape` and `coords` Attributes

| Values of `shape` Attribute | Description | Specification | Values of `coords` Attribute |
| :--: | :-- | :--: | :--: |
| **`rect`** | *rectangular* region | HTML4, HTML5 | two `x,y` pairs: *`left, top`*, *`right, bottom`* |
| **`circle`** | *circular* region | HTML4, HTML5 | `x,y,r` where `x,y` is a pair specifying the center of the circle and `r` is a value for the radius |
| **`poly`** | *polygon* | HTML4, HTML5 | a set of `x,y` pairs for each point in the polygon: `x1,y1,x2,y2,x3,y3,` and so on.
| **`default`** | the *entire* region beyond any defined shapes | HTML4, HTML5 |

In HTML4, the values of *`coords`* are numbers of pixels or percentages, if a percent sign (`%`) is appended;
in HTML5, the values are numbers of *CSS pixels*.

## Example for Image Map

```html
<img src="url" alt="replacement text" title="hint text" usemap="#map-id">
<map id="map-id">
  <area shape="rect"
        coords="leftTop-x,leftTop-y,rightBottom-x,rightBottom-y"
        alt="replacement text 1" title="hint text 1" href="url-1">
  <area shape="circle"
        coords="center-x,center-y,radius"
        alt="replacement text 2" title="hint text 2" href="url-2">
  <area shape="circle" coords="center-x2,center-y2,radius2">
</map>
```
