TOPICS: Document.getElementsByClassName
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.getElementsByClassName()`

The **`getElementsByClassName`** method of `Document` interface returns an array-like object of all
child elements which have all of the given class names. When called on the `document` object, the
complete document is searched, including the root node. You may also call `getElementsByClassName()`
on any element; it will return only elements which are descendants of the specified root element with
the given class names.

## Syntax

```javascript
var elements = document.getElementsByClassName(names); // or:
var elements = rootElement.getElementsByClassName(names);
```

- `elements` is a live `HTMLCollection` of found elements.
- `getElementsByClassName` can be called on any element, not only on the `document`. The element on
which it is called will be used as the root of the search.

| parameter | Description |
| :-- | :-- |
| `names` | is a string representing the list of class names to match; class names are separated by whitespace |

## Examples

Get all elements that have a class of `'test'`

```javascript
document.getElementsByClassName('test')
```

Get all elements that have both the `'red'` and `'test'` classes

```javascript
document.getElementsByClassName('red test')
```

Get all elements that have a class of `'test'`, inside of an element that has the ID of `'main'`:

```javascript
document.getElementById('main').getElementsByClassName('test')
```

Get the first element with a class of `'test'`, or undefined if there is no matching element:

```javascript
document.getElementsByClassName('test')[0]
```

We can also use methods of Array.prototype on any `HTMLCollection` by passing the `HTMLCollection` as
the method's this value. Here we'll find all div elements that have a class of `'test'`:

```javascript
var testElements = document.getElementsByClassName('test');
var testDivs = Array.prototype.filter.call(testElements, function(testElement){
  return testElement.nodeName === 'DIV';
});
```

## Get the first element whose class is `'test'`

This is the most commonly used method of operation.

```html
<html>
<body>
  <div id="parent-id">
    <p>hello world 1</p>
    <p class="test">hello world 2</p>
    <p>hello world 3</p>
    <p>hello world 4</p>
  </div>

  <script>
    var parentDOM = document.getElementById("parent-id");

    var test = parentDOM.getElementsByClassName("test"); // a list of matching elements, *not* the element itself
    console.log(test); //HTMLCollection[1]

    var testTarget = parentDOM.getElementsByClassName("test")[0]; // the first element, as we wanted
    console.log(testTarget); //<p class="test">hello world 2</p>
  </script>
</body>
</html>
```

## Multiple Classes Example

`document.getElementsByClassName` works very similarly to `document.querySelector` and
`document.querySelectorAll`. Only elements with ALL of the classNames specified are selected.

```html
<span class="orange fruit">Orange Fruit</span>
<span class="orange juice">Orange Juice</span>
<span class="apple juice">Apple Juice</span>
<span class="foo bar">Something Random</span>
<textarea id="resultArea" style="width:100%;height:7em"></textarea>
```

```javascript
// getElementsByClassName selects partial matches
var allOrangeJuiceByClass = document.getElementsByClassName('orange juice');
var result = "document.getElementsByClassName('orange juice')";
for (var i=0, len=allOrangeJuiceByClass.length|0; i<len; i=i+1|0) {
    result += "\n  " + allOrangeJuiceByClass[i].textContent;
}


// querySelector only selects full complete matches
var allOrangeJuiceQuery = document.querySelectorAll('.orange.juice');
result += "\n\ndocument.querySelectorAll('.orange.juice')";
for (var i=0, len=allOrangeJuiceQuery.length|0; i<len; i=i+1|0) {
    result += "\n  " + allOrangeJuiceQuery[i].textContent;
}

document.getElementById("resultArea").value = result;
```
