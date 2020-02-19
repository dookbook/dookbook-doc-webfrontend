TOPICS: :first-child
        :last-child
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Pseudo-Class: `:first-child`、`:last-child`

The **`:first-child`** CSS pseudo-class represents the first element among a group of sibling elements.
As originally defined, the selected element had to have a parent. Beginning with Selectors Level 4,
this is no longer required.

The **`:last-child`** CSS pseudo-class represents the last element among a group of sibling elements.
As originally defined, the selected element had to have a parent. Beginning with Selectors Level 4,
this is no longer required.

## Basic example

```html
<div>
  <p>This text is selected!</p>
  <p>This text isn't selected.</p>
</div>

<div>
  <h2>This text isn't selected: it's not a `p`.</h2>
  <p>This text isn't selected.</p>
</div>
```

```css
p:first-child {
  color: lime;
  background-color: black;
  padding: 5px;
}

p:last-child {
  color: #ff0;
  background-color: red;
  padding: 5px;
}
```

## Example: Styling a list

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3
    <ul>
      <li>Item 3.1</li>
      <li>Item 3.2</li>
      <li>Item 3.3</li>
    </ul>
  </li>
</ul>
```

```css
ul li {
  color: blue;
}

ul li:first-child {
  border: 1px solid blue;
  color: blue;
}

ul li:first-child {
  color: red;
  font-weight: bold;
}
```
