TOPICS: onerror
        error
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `error` Event

The **`onerror`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`error` events.

Error events are fired at various targets for different kinds of errors:

- When a **JavaScript runtime error** (including syntax errors and exceptions thrown within handlers)
occurs, an `error` event using interface `ErrorEvent` is fired at window and `window.onerror()` is
invoked (as well as handlers attached by `window.addEventListener` (not only capturing)).
- When a resource (such as an [`<img>`](/en/webfrontend/<img>) or [`<script>`](/en/webfrontend/<script>))
**fails to load**, an error event using interface `Event` is fired at the element that initiated the
load, and the `onerror()` handler on the element is invoked. These error events do not bubble up to
window, but (at least in Firefox) can be handled with a `window.addEventListener` configured with
useCapture set to True.

Installing a global `error` event handler is useful for automated collection of error reports.

## Syntax

For historical reasons, different arguments are passed to window.onerror and `element.onerror` handlers
(as well as on error-type `window.addEventListener` handlers).

### `window.onerror`

```javascript
window.onerror = function(message, source, lineno, colno, error) { ... }
```

Function parameters:

- `message`: error message (string). Available as `event` (sic!) in HTML `onerror=""` handler.
- `source`: URL of the script where the error was raised (string)
- `lineno`: Line number where error was raised (number)
- `colno`: Column number for the line where the error occurred (number)
- `error`: Error Object (object)

When the function returns `true`, this prevents the firing of the default event handler.

### `window.addEventListener('error')`

```javascript
window.addEventListener('error', function(event) { ... })
```

`event` of type `ErrorEvent` contains all the information about the event and the error.

### `element.onerrorSection`

```javascript
element.onerror = function(event) { ... }
```

`element.onerror` accepts a function with a single argument of type `Event`.

A good example for this is when you are using an image tag, and need to specify a backup image in
case the one you need is not available on the server for any reason.

```html
<img src="imagenotfound.gif" onerror="this.onerror=null;this.src='imagefound.gif';" />
```

The reason we have the `this.onerror=null` in the function is that the browser will be stuck in an
endless loop if the onerror image itself generates an error.

## Notes

When an `error` occurs in a script, loaded from a different origin, the details of the error are not
reported to prevent leaking information. Instead the error reported is simply **`"Script error."`** This
behavior can be overriden in some browsers using the `crossorigin` attribute on `<script>` and having
the server send the appropriate CORS HTTP response headers.  A workaround is to isolate `"Script error."`
and handle it knowing that the error detail is only viewable in the browser console and not accessible
via JavaScript.

```javascript
window.onerror = function (msg, url, lineNo, columnNo, error) {
  var string = msg.toLowerCase();
  var substring = "script error";
  if (string.indexOf(substring) > -1){
    alert('Script Error: See Browser Console for Detail');
  } else {
    var message = [
      'Message: ' + msg,
      'URL: ' + url,
      'Line: ' + lineNo,
      'Column: ' + columnNo,
      'Error object: ' + JSON.stringify(error)
    ].join(' - ');

    alert(message);
  }

  return false;
};
```

When using the inline HTML markup (`<body onerror="alert('an error occurred')">`), the HTML
specification requires arguments passed to `onerror` to be named `event`, `source`, `lineno`,
`colno`, `error`. In browsers that have not implemented this requirement, they can still be obtained
via `arguments[0]` through `arguments[2]`.
