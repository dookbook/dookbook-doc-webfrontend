TOPICS: Element.attachShadow
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.attachShadow()`

The **`Element.attachShadow()`** method attaches a shadow DOM tree to the specified element and
returns a reference to its `ShadowRoot`.

## Syntax

```javascript
var shadowroot = element.attachShadow(shadowRootInit);
```

| parameter | Description |
| :-- | :-- |
| `shadowRootInit` | A `ShadowRootInit` dictionary, which can contain the following fields:<br>`mode`: A string specifying the encapsulation mode for the shadow DOM tree. This can be one of:<br>1. `open`: Elements of the shadow root are accessible from JavaScript outside the root, for example using `Element.shadowRoot`: `element.shadowRoot; // Returns a ShadowRoot obj`<br>2. `closed`: Denies access to the node(s) of a closed shadow root from JavaScript outside it: `element.shadowRoot; // Returns null` |
| `delegatesFocus` | A `boolean` that, when set to `true`, specifies behavior that mitigates custom element issues around focusability. When a non-focusable part of the shadow DOM is clicked, the first focusable part is given focus, and the shadow host is given any available :focus styling. |

**Return value**: Returns a `ShadowRoot` object or `null`.

## Examples

You can see that we use `attachShadow()` in the middle of the code to create a shadow root, which we
then attach our custom element's contents to.

```javascript
// Create a class for the element
class WordCount extends HTMLParagraphElement {
  constructor() {
    // Always call super first in constructor
    super();

    // count words in element's parent element
    var wcParent = this.parentNode;

    function countWords(node){
      var text = node.innerText || node.textContent
      return text.trim().split(/\s+/g).length;
    }

    var count = 'Words: ' + countWords(wcParent);

    // Create a shadow root
    var shadow = this.attachShadow({mode: 'open'});

    // Create text node and add word count to it
    var text = document.createElement('span');
    text.textContent = count;

    // Append it to the shadow root
    shadow.appendChild(text);

    // Update count when element content changes
    setInterval(function() {
      var count = 'Words: ' + countWords(wcParent);
      text.textContent = count;
    }, 200)
  }
}

// Define the new element
customElements.define('word-count', WordCount, { extends: 'p' });
```
