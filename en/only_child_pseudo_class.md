TOPICS: :only-child

# CSS Pseudo-Class: `:only-child`

CSS pseudo-class **`:only-child`** matches elements **without any sibling element**s, for example:
an element that contains only one element

## Basic example

```html
<div>
  <div>I am an only child.</div>
</div>

<div>
  <div>I am the 1st sibling.</div>
  <div>I am the 2nd sibling.</div>
  <div>I am the 3rd sibling, <div>but this is an only child.</div></div>
</div>
```

```css
div:only-child {
  color: red;
}

div {
  display: inline-block;
  margin: 6px;
  outline: 1px solid;
}
```

## A list example

```html
<ol>
  <li>First
    <ul>
      <li>This list has just one element.</li>
    </ul>
  </li>
  <li>Second
    <ul>
      <li>This list has three elements.</li>
      <li>This list has three elements.</li>
      <li>This list has three elements.</li>
    </ul>
  </li>
</ol>
```

```css
li li {
  list-style-type: disc;
}

li:only-child {
  color: red;
  list-style-type: square;
}
```
