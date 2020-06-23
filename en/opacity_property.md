TOPICS: opacity property

# CSS Transparency Property: `opacity`

The CSS **`opacity`** property specifies **the transparency of an element**.

When the value of the **`opacity`** property is applied to an element, the element (including its
contents) is treated as a whole, even if the value is not inherited by child elements. Therefore, an
element and the child elements it contains will have the same transparency as the element background,
even if the element and its child elements have different **`opacity`** property values.

Use the **`opacity`** property. When the property value is not **`1`**, the element will be placed
in a new cascading context.

## Property value

**number** is a numeric value in the range of **`0.0`** to **`1.0`**. This value includes and
represents the transparency of the channel, which is the value of the alpha channel. Any value that
overflows this value range, although valid, will be interpreted as the value closest to it within
the value range.

| Property value | Description |
| :--- | :--- |
| **`0`** | The element is completely transparent (ie the element is not visible). Any value between `0.0`-`1.0`. |
| **`1`** | The element is completely opaque (ie the background behind the element is not visible). |

## Basic example

```css
div { background-color: yellow; }

.light {
  opacity: 0.2;
}
.medium {
  opacity: 0.5;
}
.heavy {
  opacity: 0.9;
}
```

```html
<div class="light">You can barely see this.</div>
<div class="medium">This is easier to see.</div>
<div class="heavy">This is very easy to see.</div>
```

## The difference between `:hover` and `opacity`

```css
img.opacity {
  opacity: 1;
  filter: alpha(opacity=100); /* IE8 and lower */
  zoom: 1; /* Trigger "hasLayout" on ie7 and lower */
}

img.opacity:hover {
  opacity: 0.5;
  filter: alpha(opacity=50);
  zoom: 1;
}
```

```html
<img src="//developer.mozilla.org/media/img/mdn-logo.png"
     alt="MDN logo" width="128" height="146"
     class="opacity">
```
