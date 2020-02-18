TOPICS: id attribute

# HTML Global Attribute: `id`

The **`id`** [global attribute](/en/webfrontend/HTML_Global_Attributes) defines a unique identifier
(`ID`) for an HTML element. Can be used as a link anchor to change or style elements with the
specified `id` via JavaScript (HTML DOM) or via CSS.

!!! error ""
    This attribute's value is an opaque string: this means that web authors must not use it to convey
    human-readable information.

`id`'s value must not contain whitespace (spaces, tabs etc.). Browsers treat non-conforming IDs that
contain whitespace as if the whitespace is part of the ID. In contrast to the `class` attribute,
which allows space-separated values, elements can only have one single ID value.

!!! warn "Note"
    Using characters except [[ASCII]] letters, digits, `'_'`, `'-'` and `'.'` may cause compatibility
    problems, as they weren't allowed in HTML 4. Though this restriction has been lifted in HTML5,
    But for compatibility, the `ID` should start with the letters `A-Z` or `a-z`.

## Example

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Simple example</title>
<script>
function displayResult() {
  document.getElementById("myHeader").innerHTML="Have a nice day!";
}
</script>
<style>
#myHeader {
  font-size: 28px;
  color: red;
}
</style>
</head>
<body>

<h1 id="myHeader">Hello World!</h1>
<button onclick="displayResult()">Edit text</button>

</body>
</html>
```

## See also

- All HTML [global attributes](/en/webfrontend/HTML_Global_Attributes).
- [`Element.id`](/en/webfrontend/Element.id) that reflects this attribute.
