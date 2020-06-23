TOPICS: object-fit property

# CSS Property: `object-fit`

The CSS **`object-fit`** property specifies **the content of the replaceable element** how it should
fit into the **height** and **width-determined frame** it uses.

You can use the [**`object-position`**](/en/webfrontend/object-position_property) property to
**switch the content object of the replaced element** the **alignment** within the element frame.

## Property value

| Property value | Description |
| :--- | :--- |
| **`contain`** | The replaced content will be scaled to maintain its aspect ratio when the element's content box is filled. The entire object retains its aspect ratio while filling the box, so if the aspect ratio does not match the aspect ratio of the box, the object will be added with "black borders". |
| **`cover`** | The replaced content fills the entire content box of the element while maintaining its aspect ratio. If the aspect ratio of the object does not match the content frame, the object will be clipped to fit the content frame. |
| **`fill`** | The replaced content just fills the content box of the element. The entire object will completely fill this box. |If the aspect ratio of the object does not match the content frame, the object will be stretched to fit the content frame. |
| **`none`** | The replaced content will keep its original size. |
| **`scale-down`** | The size of the content is the same as one of *`none`* or *`contain`*, depending on who gets the smaller object size between them. |

## Examples

```html
<div>
  <h2>object-fit: fill</h2>
  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="fill"/>

  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="fill narrow"/>

  <h2>object-fit: contain</h2>
  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="contain"/>

  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="contain narrow"/>

  <h2>object-fit: cover</h2>
  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="cover"/>

  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="cover narrow"/>

  <h2>object-fit: none</h2>
  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="none"/>

  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="none narrow"/>

  <h2>object-fit: scale-down</h2>
  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="scale-down"/>

  <img src="https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png" alt="MDN Logo" class="scale-down narrow"/>

</div>
```

```css
h2 {
  font-family: Courier New, monospace;
  font-size: 1em;
  margin: 1em 0 0.3em;
}

div {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-items: flex-start;
  height: 940px;
}

img {
  width: 150px;
  height: 100px;
  border: 1px solid #000;
}

.narrow {
  width: 100px;
  height: 150px;
  margin-top: 10px;
}

.fill {
  object-fit: fill;
}

.contain {
  object-fit: contain;
}

.cover {
  object-fit: cover;
}

.none {
  object-fit: none;
}

.scale-down {
  object-fit: scale-down;
}
```
