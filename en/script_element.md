TOPICS: <script>

# `<script>`

The **HTML `<script>` element** is used to embed or reference executable code; this is typically
used to embed or refer to JavaScript code. The `<script>` element can also be used with other
languages, such as WebGL's GLSL shader programming language.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Metadata content*, *Flow content*, *Phrasing content*. |
| **Permitted content** | Dynamic script such as `text/javascript`. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *metadata content*, or any element that accepts *phrasing content*. |
| **Permitted ARIA** | roles None |
| **DOM interface** | **`HTMLScriptElement` ** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `async` | This is a Boolean attribute indicating that the browser should, if possible, load the script asynchronously.<br>**error:** This attribute must not be used if the `src` attribute is absent (i.e. for inline scripts). If it is included in this case it will have no effect.<br>Browsers usually assume the worst case scenario and load scripts synchronously, (i.e. `async="false"`) during HTML parsing.<br>Dynamically inserted scripts (using `document.createElement()`) load asynchronously by default, so to turn on synchronous loading (i.e. scripts load in the order they were inserted) set `async="false"`.<br>See Browser compatibility for notes on browser support. See Also Async scripts for asm.js. |
| `crossorigin` | Normal script elements pass minimal information to the `window.onerror` for scripts which do not pass the standard CORS checks. To allow error logging for sites which use a separate domain for static media, use this attribute. See CORS settings attributes for a more descriptive explanation of its valid arguments. |
| `defer` | This Boolean attribute is set to indicate to a browser that the script is meant to be executed after the document has been parsed, but before firing `DOMContentLoaded`.<br>Scripts with the `defer` attribute will prevent the `DOMContentLoaded` event from firing until the script has loaded and finished evaluating.<br>**error:** This attribute must not be used if the src attribute is absent (i.e. for inline scripts), in this case it would have no effect. To achieve a similar effect for dynamically inserted scripts use `async="false"` instead. Scripts with the `defer` attribute will execute in the order in which they appear in the document. |
| `integrity` | This attribute contains inline metadata that a user agent can use to verify that a fetched resource has been delivered free of unexpected manipulation. See Subresource Integrity. |
| `nomodule` | This Boolean attribute is set to indicate that the script should not be executed in browsers that support ES2015 modules — in effect, this can be used to serve fallback scripts to older browsers that do not support modular JavaScript code. |
| `nonce` |A cryptographic nonce (number used once) to whitelist inline scripts in a script-src Content-Security-Policy. The server must generate a unique nonce value each time it transmits a policy. It is critical to provide a nonce that cannot be guessed as bypassing a resource's policy is otherwise trivial. |
| `referrerpolicy` | Indicates which referrer to send when fetching the script, or resources fetched by the script:<br>`no-referrer`: The `Referer` header will not be sent.<br>`no-referrer-when-downgrade` (default): The `Referer` header will not be sent to origins without TLS (HTTPS).<br>`origin`: The sent referrer will be limited to the origin of the referring page: its scheme, host, and port.<br>`origin-when-cross-origin`: The referrer sent to other origins will be limited to the scheme, the host, and the port. Navigations on the same origin will still include the path.<br>`same-origin`: A referrer will be sent for same origin, but cross-origin requests will contain no referrer information.<br>`strict-origin`: Only send the origin of the document as the referrer when the protocol security level stays the same (e.g. HTTPS→HTTPS), but don't send it to a less secure destination (e.g. HTTPS→HTTP).<br>`strict-origin-when-cross-origin`: Send a full URL when performing a same-origin request, but only send the origin when the protocol security level stays the same (e.g.HTTPS→HTTPS), and send no header to a less secure destination (e.g. HTTPS→HTTP).<br>`unsafe-url`: The referrer will include the origin and the path (but not the fragment, password, or username). This value is unsafe, because it leaks origins and paths from TLS-protected resources to insecure origins.<br>**Note:** An empty string value (`""`) is both the default value, and a fallback value if `referrerpolicy` is not supported. If `referrerpolicy` is not explicitly specified on the `<script>` element, it will adopt a higher-level referrer policy, i.e. one set on the whole document or domain. If a higher-level policy is not available, the empty string is treated as being equivalent to `no-referrer-when-downgrade`. |
| `src` | This attribute specifies the URI of an external script; this can be used as an alternative to embedding a script directly within a document.<br>**error:**If a `script` element has a `src` attribute specified, it should not have a script embedded inside its TOPICS since it can lead to unexpected behavior. The unexpected behavior is because it is only the JavaScript in the file referenced in the `src` attribute that will be added to the HTML page. |
| `type` | This attribute indicates the type of script represented. The value of this attribute will be in one of the following categories. |

- **Omitted or a JavaScript MIME type**: This indicates the script is JavaScript. The HTML5
specification urges authors to omit the attribute rather than provide a redundant MIME type.
In earlier browsers, this identified the scripting language of the embedded or
imported (via the `src` attribute) code. JavaScript MIME types are listed in the specification.
- **module**: Causes the code to be treated as a JavaScript module. The processing of the script
contents is not affected by the `charset` and `defer` attributes. For information on using `module`,
see our JavaScript modules guide.
- **Any other value**: The embedded content is treated as a data block which won't be processed by
the browser. Developers must use a valid MIME type that is not a JavaScript MIME type to denote data
blocks. The `src` attribute will be ignored.

!!! warn "Don't try this at home"
    Note: in Firefox you could specify the version of JavaScript contained in a `<script>`
    element by including a non-standard `version` parameter inside the type attribute — for example
    `type="text/javascript;version=1.8"`. This has been removed in Firefox 59 (see bug 1428745).

## Notes

Scripts without `async` , `defer` or `type="module"` attributes, as well as inline scripts,
are fetched and executed immediately, before the browser continues to parse the page.

The script should be served with the `text/javascript` MIME type, but browsers are lenient and
only block them if the script is served with an image type (`image/*`); a video type (`video/*`);
an audio (`audio/*`) type; or `text/csv`. If the script is blocked, an `error` is sent to the
element, if not a `load` event is sent.

## Examples

### Basic Usage

These examples show how to import script using the `<script>` element in both HTML4 and HTML5.

```html
<!-- HTML4 -->
<script type="text/javascript" src="javascript.js"></script>

<!-- HTML5 -->
<script src="javascript.js"></script>
```

### Module Fallback

Browsers that support the `module` value for the `type` attribute ignore any script with a `nomodule`
attribute. That enables you to use module scripts while also providing `nomodule`-marked fallback
scripts for non-supporting browsers.

```html
<script type="module" src="main.js"></script>
<script nomodule src="fallback.js"></script>
```
