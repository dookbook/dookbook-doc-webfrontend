TOPICS: width property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `width`

The **`width`** CSS property sets an element's width. By default, it sets the width of the content area,
but if `box-sizing` is set to `border-box`, it sets the width of the border area.

The `min-width` and `max-width` properties override `width`.

## Syntax

```css
/* <length> values */
width: 300px;
width: 25em;

/* <percentage> value */
width: 75%;

/* Keyword values */
width: max-content;
width: min-content;
width: fit-content(20em);
width: auto;

/* Global values */
width: inherit;
width: initial;
width: unset;
```

## Attribute Value

| Attribute Value | Description |
| `length` | Defines the width as an absolute value. |
| `percentage` | Defines the width as a percentage of the containing block's width. |
| `auto` | The browser will calculate and select a width for the specified element. |
| `max-content` | The intrinsic preferred width. |
| `min-content` | The intrinsic minimum width. |

## Default width

```css
p.goldie {
  background: gold;
}
```

```html
<p class="goldie">The Mozilla community produces a lot of great software.</p>
```

## `px` and `em`

```css
.px_length {
  width: 200px;
  background-color: red;
  color: white;
  border: 1px solid black;
}

.em_length {
  width: 20em;
  background-color: white;
  color: red;
  border: 1px solid black;
}
```

```html
<div class="px_length">Width measured in px</div>
<div class="em_length">Width measured in em</div>
```

## PercentageSection

```css
.percent {
  width: 20%;
  background-color: silver;
  border: 1px solid red;
}
```

```html
<div class="percent">Width in percentage</div>
```

## `max-content`

```css
p.maxgreen {
  background: lightgreen;
  width: intrinsic;           /* Safari/WebKit 使用了非标准的名称 */
  width: -moz-max-content;    /* Firefox/Gecko */
  width: -webkit-max-content; /* Chrome */
}
```

```html
<p class="maxgreen">The Mozilla community produces a lot of great software.</p>
```

## `min-content`

```css
p.minblue {
  background: lightblue;
  width: -moz-min-content;    /* Firefox */
  width: -webkit-min-content; /* Chrome */
}
```

```html
<p class="minblue">The Mozilla community produces a lot of great software.</p>
```
