TOPICS: :scope

# CSS Pseudo-Class: `:scope`

The **`:scope`** CSS pseudo-class represents elements that are **a reference point for selectors**
to match against.

Currently, when used in a stylesheet, `:scope` is the same as *`:root`*, since there is not at this
time a way to explicitly establish a `<scoped>` element. When used from a DOM API such as
`querySelector()`, `querySelectorAll()`, `matches()`, or `Element.closest()`, `:scope` matches the
element you called the method on.

## Identity match

In this simple example, we demonstrate that using the `:scope` pseudo-class from the
`Element.matches()` method matches the element on which it's called.

```javascript
let paragraph = document.getElementById("para");
let output = document.getElementById("output");

if (paragraph.matches(":scope")) {
  output.innerText = "Yep, the element is its own scope as expected!";
}
```

```html
<p id="para">
  This is a paragraph. It is not an interesting paragraph. Sorry about that.
</p>
<p id="output"></p>
```

## Direct children

A situation where the `:scope` pseudo-class prove to be useful is when you need to get direct
descendant of an already retrieved `Element`.

```javascript
var context = document.getElementById('context');
var selected = context.querySelectorAll(':scope > div');

document.getElementById('results').innerHTML = Array.prototype.map.call(selected, function (element) {
    return '#' + element.getAttribute('id');
}).join(', ');
```

```html
<div id="context">
    <div id="element-1">
        <div id="element-1.1"></div>
        <div id="element-1.2"></div>
    </div>
    <div id="element-2">
        <div id="element-2.1"></div>
    </div>
</div>
<p>
    Selected elements ids :
    <span id="results"></span>
</p>
```
