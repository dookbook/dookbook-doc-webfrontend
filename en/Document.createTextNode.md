TOPICS: Document.createTextNode
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createTextNode()`

Creates a new `Text` node. This method can be used to escape HTML characters.

## Syntax

```javascript
var text = document.createTextNode(data);
```

- `text` is a `Text` node.
- `data` is a `string` containing the data to be put in the text node.

## Examples

```html
<!DOCTYPE html>
<html lang="en">
<head>
<title>createTextNode example</title>
<script>
function addTextNode(text) {
  var newtext = document.createTextNode(text),
      p1 = document.getElementById("p1");

  p1.appendChild(newtext);
}
</script>
</head>

<body>
  <button onclick="addTextNode('YES! ');">YES!</button>
  <button onclick="addTextNode('NO! ');">NO!</button>
  <button onclick="addTextNode('WE CAN! ');">WE CAN!</button>

  <hr />

  <p id="p1">First line of paragraph.</p>
</body>
</html>
```
