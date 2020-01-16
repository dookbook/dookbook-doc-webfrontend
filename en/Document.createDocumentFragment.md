TOPICS: Document.createDocumentFragment
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createDocumentFragment()`

Creates a new empty `DocumentFragment` into which DOM nodes can be added to build an offscreen DOM tree.

## Syntax

```javascript
var fragment = document.createDocumentFragment();
```

## Value

A newly created, empty, `DocumentFragment` object, which is ready to have nodes inserted into it.

## Usage notes

`DocumentFragments` are DOM `Node` objects which are never part of the main DOM tree. The usual use
case is to create the document fragment, append elements to the document fragment and then append the
document fragment to the DOM tree. In the DOM tree, the document fragment is replaced by all its children.

Since the document fragment is in memory and not part of the main DOM tree, appending children to it
does not cause page reflow (computation of element's position and geometry). Historically, using
document fragments could result in better performance.

You can also use the `DocumentFragment` constructor to create a new fragment:

```javascript
let fragment = new DocumentFragment();
```

## Examples

This example creates a list of major web browsers in a `DocumentFragment`, then adds the new DOM
subtree to the document to be displayed.

```html
<ul id="ul">
</ul>
```

```javascript
var element  = document.getElementById('ul'); // assuming ul exists
var fragment = document.createDocumentFragment();
var browsers = ['Firefox', 'Chrome', 'Opera',
    'Safari', 'Internet Explorer'];

browsers.forEach(function(browser) {
  var li = document.createElement('li');
  li.textContent = browser;
  fragment.appendChild(li);
});

element.appendChild(fragment);
```
