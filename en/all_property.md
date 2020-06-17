TOPICS: all property

# CSS Property: `all`

CSS **`all`** All property except the [`unicode-bidi`](/en/webfrontend/unicode-bidi_property) and [`direction`](/en/webfrontend/direction_property)
shorthand property **reset to their initial values**, or **inherited values**.

## Property value

| Property value | Description |
| :--- | :--- |
| **`initial`** | Modify all element property or parent element values to their initial values. |
| **`inherit`** | Modify all element property or the value of the parent element to the value of its parent element. |
| **`unset`** | Modify all element property or parent element values to their parent element values (if inherited) or their initial values. |

## Examples

```css
html {
  font-size: small;
  color: blue;
}

#ex1 {
  background-color: yellow;
  color: red;
}

#ex2 {
  background-color: yellow;
  color: red;
  all: inherit;
}

#ex3 {
  background-color: yellow;
  color: red;
  all: initial;
}

#ex4 {
  background-color: yellow;
  color: red;
  all: unset;
}
```

```html
<p>No all Property:</p>
<div id="ex1">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</div>

<p>all: inherit:</p>
<div id="ex2">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</div>

<p>all: initial:</p>
<div id="ex3">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</div>

<p>all: unset:</p>
<div id="ex4">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</div>
```
