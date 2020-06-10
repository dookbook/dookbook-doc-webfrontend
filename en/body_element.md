TOPICS: <body>

# HTML Sectioning Root Element: `<body>`

## `<body>`

The HTML `<body>` Element represents the *content* of an [[HTML]] document. There can be **only
one** `<body>` element in a document.

## `<body>` Meta

|  |  |
| :-- | :-- |
| **Content categories** | *Sectioning root*. |
| **Permitted content** | *Flow content*. |
| **Tag omission** | The start tag may be omitted if the first thing inside it is not a space character, comment, [`<script>`](/en/webfrontend/<script>) element or [`<style>`](/en/webfrontend/<style>) element. The end tag may be omitted if the `<body>` element has contents or has a start tag, and is not immediately followed by a comment.|
| **Permitted parents** | It must be the second element of an [`<html>`](/en/webfrontend/<html>/) element. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLBodyElement`** <br>The `<body>` element exposes the **`HTMLBodyElement`** interface.<br>You can access the `<body>` element through the `document.body` property. |

## `<body>` Attributes

| Attributes | Description |
| :--- | :--- |
| `onafterprint` | Function to call after the user has printed the document. |
| `onbeforeprint` | Function to call when the user requests printing of the document. |
| `onbeforeunload` | Function to call when the document is about to be unloaded. |
| `onblur` | Function to call when the document loses focus. |
| `onerror` | Function to call when the document fails to load properly. |
| `onfocus` | Function to call when the document receives focus. |
| `onhashchange` | Function to call when the fragment identifier part (starting with the hash (`#`) character) of the document's current address has changed. |
| `onlanguagechange` | Function to call when the preferred languages changed. |
| `onload` | Function to call when the document has finished loading. |
| `onmessage` | Function to call when the document has received a message. |
| `onoffline` | Function to call when network communication has failed. |
| `ononline` | Function to call when network communication has been restored. |
| `onpopstate` | Function to call when the user has navigated session history. |
| `onredo` | Function to call when the user has moved forward in undo transaction history. |
| `onresize` | Function to call when the document has been resized. |
| `onstorage` | Function to call when the storage area has changed. |
| `onundo` | Function to call when the user has moved backward in undo transaction history. |
| `onunload` | Function to call when the document is going away. |

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<body>`  | support | support | support |
