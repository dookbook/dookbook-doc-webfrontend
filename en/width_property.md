TOPICS: width property

# CSS Property: `width`

The **`width`** CSS property sets an element's width. By default, it sets the width of the content area,
but if `box-sizing` is set to `border-box`, it sets the width of the border area.

The `min-width` and `max-width` properties override `width`.

## Property Value

| Property Value | Description |
| `length` | Defines the width as an absolute value. |
| `percentage` | Defines the width as a percentage of the containing block's width. |
| `auto` | The browser will calculate and select a width for the specified element. |
| `max-content` | The intrinsic preferred width. |
| `min-content` | The intrinsic minimum width. |

## Example: Default width

```css
p.goldie {
  background: gold;
}
```

```html
<p class="goldie">The Mozilla community produces a lot of great software.</p>
```

## Example: `px` and `em`

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

## Example: Percentage

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

## Example: `max-content`

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

## Example: `min-content`

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
