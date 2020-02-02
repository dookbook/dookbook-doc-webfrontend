TOPICS: Document.hasFocus
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.hasFocus()`

The **`hasFocus()`** method of the `Document` interface returns a `Boolean` value indicating whether
the document or any element inside the document has focus. This method can be used to determine whether
the active element in a document has focus.

!!! warn ""
    When viewing a document, an element with focus is always the active element in the document,
    but an active element does not necessarily have focus. For example, an active element within
    a popup window that is not the foreground doesn't have focus.

## Syntax

```javascript
var focused = document.hasFocus();
```

**Return value**: `false` if the active element in the document has no focus; `true` if the active
element in the document has focus.

## Examples

This example checks whether the document has focus every 300 milliseconds. To test the functionality
of `hasFocus()`, click on the button to open a new window, and try switching between the two pages.

```html
<p id="log">Awaiting focus check.</p>
<button onclick="openWindow()">Open a new window</button>
```

```javascript
function checkPageFocus() {
  let body = document.querySelector('body');
  let log = document.getElementById('log');

  if (document.hasFocus()) {
    log.textContent = 'This document has the focus.';
    body.style.background = '#fff';
  }
  else {
    log.textContent = 'This document does not have the focus.';
    body.style.background = '#ccc';
  }
}

function openWindow() {
  window.open('https://developer.mozilla.org/', 'MDN', 'width=640,height=320,left=150,top=150');
}

// Check page focus every 300 milliseconds
setInterval(checkPageFocus, 300);
```
