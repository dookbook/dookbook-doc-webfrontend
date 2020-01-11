TOPICS: Element.querySelectorAll
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.querySelectorAll()`

The `ParentNode` mixin defines the **`querySelectorAll()`** method as returning a NodeList
representing a list of elements matching the specified group of selectors which are descendants
of the object on which the method was called.

If you need only a single result, consider the `querySelector()` method instead.

!!! warn "Note"
    This method is implemented as `Element.querySelectorAll()`, `Document.querySelectorAll()`, and `DocumentFragment.querySelectorAll()`

## Syntax

```javascript
elementList = parentNode.querySelectorAll(selectors);
```

| parameter | Description |
| :-- | :-- |
| `selectors` | A `DOMString` containing one or more selectors to match against. This string must be a valid CSS selector string; if it's not, a `SyntaxError` exception is thrown. See Locating DOM elements using selectors for more information about using selectors to identify elements. Multiple selectors may be specified by separating them using commas.

!!! warn "Note"
    Characters which are not part of standard CSS syntax must be escaped using a backslash character.
    Since JavaScript also uses backslash escaping, special care must be taken when writing string
    literals using these characters. See Escaping special characters for more information.

## Return value

A non-live `NodeList` containing one `Element` object for each descendant node that matches at
least one of the specified selectors.

!!! warn "Note"
    If the specified `selectors` include a CSS pseudo-element, the returned list is always empty.

## Exceptions

|  |  |
| :-- | :-- |
| **`SyntaxError`** | The syntax of the specified `selectors` string is not valid.

## Examples

To obtain a NodeList of all of the [`<p>`](/en/webfrontend/<p>) elements in the document:

```javascript
var matches = document.querySelectorAll("p");
```

This example returns a list of all [`<div>`](/en/webfrontend/<div>) elements within the document
with a class of either `"note"` or `"alert"`:

```javascript
var matches = document.querySelectorAll("div.note, div.alert");
```

Here, we get a list of [`<p>`](/en/webfrontend/<p>) elements whose immediate parent element is a
div with the class `"highlighted"` and which are located inside a container whose ID is `"test"`.

```javascript
var container = document.querySelector("#test");
var matches = container.querySelectorAll("div.highlighted > p");
```

This example uses an attribute selector to return a list of the `iframe` elements in the document
that contain an attribute named `"data-src"`:

```javascript
var matches = document.querySelectorAll("iframe[data-src]");
```

Here, an attribute selector is used to return a list of the list items contained within a list
whose ID is `"userlist"` which have a `"data-active"` attribute whose value is `"1"`:

```javascript
var container = document.querySelector("#userlist");
var matches = container.querySelectorAll("li[data-active=1]");
```

## User notes

`querySelectorAll()` behaves differently than most common JavaScript DOM libraries, which might lead
to unexpected results.

Consider this HTML, with its three nested [`<div>`](/en/webfrontend/<div>) blocks.

```html
<div class="outer">
  <div class="select">
    <div class="inner">
    </div>
  </div>
</div>
```

```javascript
var select = document.querySelector('.select');
var inner = select.querySelectorAll('.outer .inner');
inner.length; // 1, not 0!
```

In this example, when selecting `".outer .inner`" in the context the [`<div>`](/en/webfrontend/<div>)
with the class `"select"`, the element with the class `".inner"` is still found, even though `.outer`
is not a descendant of the base element on which the search is performed (`".select"`). By default,
`querySelectorAll()` only verifies that the last element in the selector is within the search scope.

The `:scope` pseudo-class restores the expected behavior, only matching selectors on descendants of
the base element:

```javascript
var select = document.querySelector('.select');
var inner = select.querySelectorAll(':scope .outer .inner');
inner.length; // 0
```
