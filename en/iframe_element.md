TOPICS: <iframe>

# `<iframe>`

The **HTML Inline Frame element (`<iframe>`)** represents a nested browsing context, embedding
another HTML page into the current one.

Each embedded browsing context has its own session history and document. The browsing context that
embeds the others is called the parent browsing context. The topmost browsing context — the one with
no parent — is usually the browser window, represented by the Window object.

!!! error ""
    Because each browsing context is a complete document environment, every `<iframe>` in a page requires
    increased memory and other computing resources. While theoretically you can use as many
    `<iframe>`s as you like, check for performance problems.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *embedded content*, *interactive content*, *palpable content*. |
| **Permitted content** | Fallback content, i.e. content that is normally not rendered, but that browsers not supporting the `<iframe>` element will render. (RSS readers and email clients often show the fallback content instead.) |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *embedded content*. |
| **Permitted ARIA roles** | `application`, `document`, `img`. |
| **DOM interface** | **`HTMLIFrameElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `allow` | Specifies a feature policy for the `<iframe>`. |
| `allowfullscreen` | Set to `true` if the `<iframe>` can activate fullscreen mode by calling the `requestFullscreen()` method.<br>**Note:** This attribute is considered a legacy attribute and redefined as allow="fullscreen". |
| `allowpaymentrequest` | Set to `true` if a cross-origin `<iframe>` should be allowed to invoke the Payment Request API.<br>**Note:** This attribute is considered a legacy attribute and redefined as `allow="payment"`. |
| `csp` | A Content Security Policy enforced for the embedded resource. See `HTMLIFrameElement.csp` for details. |
| `height` | The height of the frame in CSS pixels. Default is `150`. |
| `importance` | The download priority of the resource in the `<iframe>`'s `src` attribute. Allowed values:<br>`auto (default)`<br>No preference. The browser uses its own heuristics to decide the priority of the resource.<br>`high`<br>The resource should be downloaded before other lower-priority page resources.<br>`low`<br>The resource should be downloaded after other higher-priority page resources.
| `name` |A targetable name for the embedded browsing context. This can be used in the target attribute of the [`<a>`](/en/webfrontend/<a>), [`<form>`](/en/webfrontend/<form>), or [`<base>`](/en/webfrontend/<base>) elements; the formtarget attribute of the [`<input>`](/en/webfrontend/<input>) or [`<button>`](/en/webfrontend/<button>) elements; or the windowName parameter in the `window.open()` method. |
| `referrerpolicy` | Indicates which referrer to send when fetching the frame's resource:<br>`no-referrer`: The Referer header will not be sent.<br>`no-referrer-when-downgrade` (default): The `Referer` header will not be sent to origins without TLS (HTTPS).<br>`origin`: The sent referrer will be limited to the origin of the referring page: its scheme, host, and port.<br>`origin-when-cross-origin`: The referrer sent to other origins will be limited to the scheme, the host, and the port. Navigations on the same origin will still include the path.<br>`same-origin`: A referrer will be sent for same origin, but cross-origin requests will contain no referrer information.<br>`strict-origin`: Only send the origin of the document as the referrer when the protocol security level stays the same (HTTPS→HTTPS), but don't send it to a less secure destination (HTTPS→HTTP).<br>`strict-origin-when-cross-origin`: Send a full URL when performing a same-origin request, only send the origin when the protocol security level stays the same (HTTPS→HTTPS), and send no header to a less secure destination (HTTPS→HTTP).<br>`unsafe-url`: The referrer will include the origin and the path (but not the fragment, password, or username). This value is unsafe, because it leaks origins and paths from TLS-protected resources to insecure origins. |
| `sandbox` | Applies extra restrictions to the content in the frame. The value of the attribute can either be empty to apply all restrictions, or space-separated tokens to lift particular restrictions:<br>`allow-forms`: Allows the resource to submit forms. If this keyword is not used, form submission is blocked.<br>`allow-modals`: Lets the resource [open modal windows](https://html.spec.whatwg.org/multipage/origin.html#sandboxed-modals-flag).<br>`allow-orientation-lock`: Lets the resource lock the screen orientation.<br>`allow-pointer-lock`: Lets the resource use the Pointer Lock API.<br>`allow-popups`: Allows popups (such as `window.open()`, `target="_blank"`, or `showModalDialog()`). If this keyword is not used, the popup will silently fail to open.<br>`allow-popups-to-escape-sandbox`: Lets the sandboxed document open new windows without those windows inheriting the sandboxing. For example, this can safely sandbox an advertisement without forcing the same restrictions upon the page the ad links to.<br>`allow-presentation`: Lets the resource start a presentation session.<br>`allow-same-origin`: If this token is not used, the resource is treated as being from a special origin that always fails the same-origin policy.<br>`allow-scripts`: Lets the resource run scripts (but not create popup windows).<br>`allow-storage-access-by-user-activation` : Lets the resource request access to the parent's storage capabilities with the Storage Access API.<br>`allow-top-navigation`: Lets the resource navigate the top-level browsing context (the one named _top).<br>`allow-top-navigation-by-user-activation`: Lets the resource navigate the top-level browsing context, but only if initiated by a user gesture.<br>`allow-downloads-without-user-activation` : Allows for downloads to occur without a gesture from the user.<br>**Notes about sandboxing:**<br>When the embedded document has the same origin as the embedding page, it is strongly discouraged to use both allow-scripts and allow-same-origin, as that lets the embedded document remove the sandbox attribute — making it no more secure than not using the sandbox attribute at all.<br>Sandboxing is useless if the attacker can display content outside a sandboxed iframe — such as if the viewer opens the frame in a new tab. Such content should be also served from a separate origin to limit potential damage.<br>The sandbox attribute is unsupported in Internet Explorer 9 and earlier. |
| `src` | The URL of the page to embed. Use a value of about:blank to embed an empty page that conforms to the same-origin policy. Also note that programatically removing an `<iframe>`'s src attribute (e.g. via `Element.removeAttribute()`) causes `about:blank` to be loaded in the frame in Firefox (from version 65), Chromium-based browsers, and Safari/iOS. |
| `srcdoc` | Inline HTML to embed, overriding the `src` attribute. If a browser does not support the srcdoc attribute, it will fall back to the URL in the `src` attribute. |
| `width` | The width of the frame in CSS pixels. Default is `300`.<br>**Non-standard attributes**: |
| `mozbrowser` | See bug 1318532 for exposing this to WebExtensions in Firefox. |

Makes the `<iframe>` act like a top-level browser window. See Browser API for details.
**Available only to WebExtensions**.

## Scripting

Inline frames, like `<frame>` elements, are included in the `window.frames` pseudo-array.

With the DOM `HTMLIFrameElement` object, scripts can access the `window` object of
the framed resource via the `contentWindow` property. The `contentDocument` property
refers to the `document` inside the `<iframe>`, same as `contentWindow.document`.

From the inside of a frame, a script can get a reference to its parent window with `window.parent`.

Script access to a frame's content is subject to the same-origin policy. Scripts cannot access most
properties in other window objects if the script was loaded from a different origin, including
scripts inside a frame accessing the frame's parent. Cross-origin communication can be
achieved using `Window.postMessage()`.

## Positioning and scaling

As a replaced element, the position, alignment, and scaling of the embedded document within
the `<iframe>` element's box, can be adjusted with the `object-position`
and `object-fit` properties.

## Examples

### A simple `<iframe>`

An `<iframe>` in action. After creating the frame, when the user clicks a button,
its title is displayed in an alert.

```html
<iframe src="https://mdn-samples.mozilla.org/snippets/html/iframe-simple-contents.html"
        title="iframe Example 1"
        width="400"
        height="300">
</iframe>
```

### Open a link in an `<iframe>` in another tab

In this example, a Google map is displayed in a frame;

```html
<iframe id="Example2"
    title="iframe Example 2"
    width="400" height="300"
    style="border:none;"
    src="https://maps.google.com/maps?f=q&source=s_q&q=buenos+aires&sll=37.0625,-95.677068&sspn=38.638819,80.859375&t=h&hnear=Buenos+Aires,+Argentina&z=11&ll=-34.603723,-58.381593&output=embed">
</iframe>
```

## Accessibility Concerns

People navigating with assistive technology such as a screen reader can use the
`title` attribute on an `iframe` to label its content.
The title's value should concisely describe the embedded content:

```html
<iframe title="Wikipedia page for Avocados" src="https://en.wikipedia.org/wiki/Avocado"></iframe>
```

Without this title, they have to navigate into the `iframe` to determine what its embedded content is.
This context shift can be confusing and time-consuming, especially for pages with multiple
`<iframe>`s and/or if embeds contain interactive content like video or audio.
