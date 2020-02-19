TOPICS: <iframe>
        <iframe> src attribute
        <iframe> width attribute
        <iframe> height attribute
        <iframe> name attribute
        <iframe> srcdoc attribute
        <iframe> sandbox attribute
        <iframe> seamless attribute

# HTML Inline Frame Element: `<iframe>`

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
| **Content categories** | *Flow content*, *phrasing content*, *embedded content*, *interactive content*, *palpable content*.|
| **Permitted content** | *Fallback content*, i.e. content that is normally not rendered, but that browsers not supporting the `<iframe>` element will render. (RSS readers and email clients often show the *fallback content* instead.)|
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts *embedded content*.|
| **Permitted ARIA roles** | **`application`**, **`document`**, **`img`** |
| **DOM interface** | **`HTMLIFrameElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`src`** | Specifies the URL of the document to display in `<iframe>` |
| **`width`** | The width of the frame. The default value is 300.|
| **`height`** | The height of the frame. The default value is 150. |
| `name` | Specifies the name of `<iframe>`. Used to reference an element in JavaScript, either as the value of the `target` attribute of an [`<a>`](/en/webfrontend/<a>) or [`<form>`](/en/webfrontend/<form>) element, or as the value of the `formtarget` attribute of an [`<input>`](/en/webfrontend/<input>) or [`<button>`](/en/webfrontend/<button>). |
| `srcdoc` | Specifies the HTML content of the page to be displayed in the `<iframe>` to override the content of the `src` attribute. If the browser does not support the `srcdoc` attribute, it will fall back to the URL in the `src` attribute. |
| `sandbox` | This attribute enables some additional restrictions on the content rendered in the `<iframe>` frame. |
| `seamless` | Specifies that `<iframe>` looks like part of the parent document. |

## value of the `sandbox` attribute of `<iframe>`

If an empty string is specified (`sandbox=""`), this attribute enables some additional restrictions
on the content rendered in the `<iframe>` frame.

The value of the `sandbox` property can be either an empty string (all restrictions will be enabled)
or a series of specified strings separated by spaces.

| Value | Description |
| :-- | :-- |
| `""` | Enable all constraints |
| `allow-forms` | Allow form submission. |
| `allow-scripts` | Allow script execution. |
| `allow-popups` | Allow popups (eg: `window.open`, `target = "_ blank"`, `showModalDialog`). If this keyword is not used, the corresponding function is automatically disabled.|
| `allow-modals` | Allows embedded browsing contexts to open modal windows.|
| `allow-orientation-lock` | Allow embedded browsing context to lock screen orientation (e.g. horizontal or vertical orientation for smartphones, tablets) |
| `allow-same-origin` | Allows content to be treated as a normal source. If this keyword is not used, the embedded content will be treated as a separate source.|
| `allow-top-navigation` | Allows embedded browsing context to navigate (load) content to the top-level browsing context. |

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

## Example: A simple `<iframe>`

An `<iframe>` in action. After creating the frame, when the user clicks a button,
its title is displayed in an alert.

```html
<iframe src="https://mdn-samples.mozilla.org/snippets/html/iframe-simple-contents.html"
        title="iframe Example 1"
        width="400"
        height="300">
</iframe>
```

## Example: Open a link in an `<iframe>` in another tab

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
