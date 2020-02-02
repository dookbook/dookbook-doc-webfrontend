TOPICS: Document.getElementsByName
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.getElementsByName()`

The **`getElementsByName()`** method of the Document object returns a NodeList Collection of
elements with a given name in the document.

## Syntax

```javascript
var elements = document.getElementsByName(name);
```

- elements is a live `NodeList` Collection, meaning it automatically updates as new elements with the
same `name` are added to/removed from the document.

| parameter | Description |
| :-- | :-- |
| `name` | is the value of the `name` attribute of the element(s). |

## Examples

```html
<!DOCTYPE html>
<html lang="en">
<title>Example: using document.getElementsByName</title>

<input type="hidden" name="up">
<input type="hidden" name="down">

<script>
  var up_names = document.getElementsByName("up");
  console.log(up_names[0].tagName); // displays "INPUT"
</script>
</html>
```

## Notes

The `name` attribute can only be applied in (X)HTML documents.

The returned `NodeList` Collection contains all elements with the given `name`, such as `<meta>`,
`<object>`, and even elements which do not support the `name` attribute at all.

!!! error ""
    The **`getElementsByName`** method works differently in IE10 and below. There, `getElementsByName()`
    also returns elements that have an `id` attribute with the specified value. Be careful not to use
    the same string as both a `name` and an `id`.

!!! error ""
    The **`getElementsByName`** method works differently in IE. There, `getElementsByName()` does
    not return all elements which may not have a `name` attribute (such as `<span>`).

!!! error ""
    Both IE and Edge return an `HTMLCollection`, not a `NodeList`
