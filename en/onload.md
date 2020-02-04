TOPICS: onload
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `onload`

The **`onload`** property of the `GlobalEventHandlers` mixin is an `EventHandler` that processes
`load` events on a `Window`, `XMLHttpRequest`, `<img>` element, etc.

The `load` event fires when a given resource has loaded.

## Syntax

```javascript
window.onload = funcRef;
```

`functionRef` is the handler function to be called when the window’s `load` event fires.

## Examples

```javascript
window.onload = function() {
  init();
  doSomethingElse();
};
```

```html
<!doctype html>
<html>
  <head>
    <title>onload test</title>
    // ES5
    <script>
      function load() {
        console.log("load event detected!");
      }
      window.onload = load;
    </script>
    // ES2015(aka: ES6)
    <script>
      const load = () => {
        console.log("load event detected!");
      }
      window.onload = load;
    </script>
  </head>
  <body>
    <p>The load event fires when the document has finished loading!</p>
  </body>
</html>
```

## Notes

The `load` event fires at the end of the document loading process. At this point, all of the objects
in the document are in the DOM, and all the images, scripts, links and sub-frames have finished loading.

There are also DOM Events like `DOMContentLoaded` and `DOMFrameContentLoaded` (which can be handled
using `EventTarget.addEventListener()`) which are fired after the DOM for the page has been constructed,
but do not wait for other resources to finish loading.
