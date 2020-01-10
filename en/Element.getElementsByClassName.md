TOPICS: Element.getElementsByClassName
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getElementsByClassName()`

The `Element` method **`getElementsByClassName()`** returns a live `HTMLCollection` which contains
every descendant element which has the specified class name or names.

The method `getElementsByClassName()` on the `Document` interface works essentially the same way,
except it acts on the entire document, starting at the document root.

## Syntax

```javascript
var elements = element.getElementsByClassName(names);
```

| parameter | Description |
| :-- | :-- |
| `names` | A `DOMString` containing one or more class names to match on, separated by whitespace. |

**Return value**: An `HTMLCollection` providing a live-updating list of every element which is a
member of every class in `names`.

## Usage notes

As always, the returned collection is live, meaning that it always reflects the current state of
the DOM tree rooted at the element on which the function was called. As new elements that match
`names` are added to the subtree, they immediately appear in the collection. Similarly, if an
existing element that doesn't match `names` has its set of classes adjusted so that it matches, it
immediately appears in the collection.

The opposite is also true; as elements no longer match the set of names, they are immediately
removed from the collection.

!!! warn ""
    In quirks mode, the class names are compared in a case-insensitive fashion. Otherwise,
    they're case sensitive.

## Examples

### Matching a single class

To look for elements that include among their classes a single specified class, we just provide that
class name when calling `getElementsByClassName()`:

```javascript
element.getElementsByClassName('test');
```

This example finds all elements that have a class of `test`, which are also a descendant of the
element that has the id of `main`:

```javascript
document.getElementById('main').getElementsByClassName('test');
```

### Matching multiple classes

To find elements whose class lists include both the `red` and `test` classes:

```javascript
element.getElementsByClassName('red test');
```

### Examining the results

You can use either the `item()` method on the returned `HTMLCollection` or standard array syntax to
examine individual elements in the collection. However **the following code will not work** as one might
expect because `"matches"` will change as soon as any `"colorbox"` class is removed.

```javascript
var matches = element.getElementsByClassName('colorbox');

for (var i=0; i<matches.length; i++) {
  matches[i].classList.remove('colorbox');
  matches.item(i).classList.add('hueframe');
}
```

Instead, use another method, such as:

```javascript
var matches = element.getElementsByClassName('colorbox');

while (matches.length > 0) {
  matches.item(0).classList.add('hueframe');
  matches[0].classList.remove('colorbox');
}
```

This code finds descendant elements with the `"colorbox"` class, adds the class `"hueframe"`, by
calling `item(0)`, then removes `"colorbox"` (using array notation). Another element (if any are
left) will then become `item(0)`.

### Filtering the results using array methods

We can also use methods of `Array.prototype` on any `HTMLCollection` by passing the `HTMLCollection`
as the method's `this` value. Here we'll find all [`<div>`](/en/webfrontend/<div>) elements that
have a class of `test`:

```javascript
var testElements = document.getElementsByClassName('test');
var testDivs = Array.prototype.filter.call(testElements, function(testElement) {
  return testElement.nodeName === 'DIV';
});
```
