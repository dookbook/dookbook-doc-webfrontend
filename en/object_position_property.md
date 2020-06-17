TOPICS: object-position property

# CSS Property: `object-position`

The CSS property **`object-position`** specifies the content of **replaceable elements**, here we call
it **object** (that is, *object* in *`object-position`*), in its **Position in content box**. The part
of the replaceable element's content box that is not covered by the object will display the background
of the element (**background**).

You can also use the [**`object-fit`**](/en/webfrontend/object-fit_property) property to change the
intrinsic (original: intrinsic) **size** (ie it **The adjustment method**, using *stretching* and
**zooming** to make the object better fit the **content box of the element**.

## Property value

| Property value | Description |
| :--- | :--- |
| **position** | Use **1-4 values** to define the positioning of the element in the 2D plane it is in. Relative or absolute offsets can be used. |

!!! warn "Note"
    These positioning methods allow the object of the replaced element to be positioned outside the
    content box.

## Examples

Here we see that HTML contains two [`<img>`](/en/webfrontend/<img>) elements, each of which displays
the MDN logo.

```html
<img id="object-position-1" src="https://mdn.mozillademos.org/files/12668/MDN.svg" alt="MDN Logo"/>
<img id="object-position-2" src="https://mdn.mozillademos.org/files/12668/MDN.svg" alt="MDN Logo"/>
```

```css
img {
  width: 300px;
  height: 250px;
  border: 1px solid black;
  background-color: silver;
  margin-right: 1em;
  : none;
}

#object-position-1 {
  object-position: 10px;
}

#object-position-2 {
  object-position: 100% 10%;
}
```

The position of the first image is that its left edge is embedded with 10 pixels from the left edge
of the element frame. The position of the second image is that its right edge is flush with the right
edge of the element frame and is located at a position 10% below the height of the element frame.
