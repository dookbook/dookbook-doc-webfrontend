TOPICS: Element.closest
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.closest()`

Starting with the `Element` itself, the **`closest()`** method traverses parents (heading toward the
document root) of the `Element` until it finds a node that matches the provided selectorString.
Will return itself or the matching ancestor. If no such element exists, it returns `null`.

## Syntax

```javascript
var closestElement = targetElement.closest(selectors);
```

| parameter | Description |
| :-- | :-- |
| `selectors` | is a `DOMString` containing a selector list such as
`"p:hover, .toto + q"`. |

**Return value**: `closestElement` is the `Element` which is the closest ancestor of the selected
element. It may be `null`.

### Exceptions

- `SyntaxError` is thrown if the `selectors` is not a valid selector list string.

## Examples

```html
<article>
  <div id="div-01">Here is div-01
    <div id="div-02">Here is div-02
      <div id="div-03">Here is div-03</div>
    </div>
  </div>
</article>
```

```javascript
var el = document.getElementById('div-03');

var r1 = el.closest("#div-02");  
// returns the element with the id=div-02

var r2 = el.closest("div div");  
// returns the closest ancestor which is a div in div, here it is the div-03 itself

var r3 = el.closest("article > div");  
// returns the closest ancestor which is a div and has a parent article, here it is the div-01

var r4 = el.closest(":not(div)");
// returns the closest ancestor which is not a div, here it is the outmost article
```

## Polyfill

For browsers that do not support `Element.closest()`, but carry support for `element.matches()` (or
a prefixed equivalent, meaning IE9+), a polyfill exists:

```javascript
if (!Element.prototype.matches) {
  Element.prototype.matches = Element.prototype.msMatchesSelector ||
                              Element.prototype.webkitMatchesSelector;
}

if (!Element.prototype.closest) {
  Element.prototype.closest = function(s) {
    var el = this;

    do {
      if (el.matches(s)) return el;
      el = el.parentElement || el.parentNode;
    } while (el !== null && el.nodeType === 1);
    return null;
  };
}
```

However, if you really do require IE 8 support, then the following polyfill will do the job very
slowly, but eventually. However, it will only support CSS 2.1 selectors in IE 8, and it can cause
severe lag spikes in production websites.

```javascript
if (window.Element && !Element.prototype.closest) {
  Element.prototype.closest =
  function(s) {
    var matches = (this.document || this.ownerDocument).querySelectorAll(s),
        i,
        el = this;
    do {
      i = matches.length;
      while (--i >= 0 && matches.item(i) !== el) {};
    } while ((i < 0) && (el = el.parentElement));
    return el;
  };
}
```
