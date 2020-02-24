TOPICS: text-overflow property

# CSS Property: `text-overflow`

The **`text-overflow`** CSS property sets how hidden overflow content is signaled to users. It can
be clipped, display an ellipsis (`'…'`), or display a custom string.

The `text-overflow` property doesn't force an overflow to occur. To make text overflow its container
you have to set other CSS properties: `overflow` and `white-space`.

The text-overflow property only affects content that is overflowing a block container element in
its inline progression direction (not text overflowing at the bottom of a box, for example).

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`clip`** | The default for this property. This keyword value will truncate the text at the limit of the content area, therefore the truncation can happen in the middle of a character. To clip at the transition between characters you can specify `text-overflow` as an empty string, if that is supported in your target browsers: `text-overflow: '';`. |
| **`ellipsis`** | This keyword value will display an ellipsis (`'…'`, U+2026 HORIZONTAL ELLIPSIS) to represent clipped text. The ellipsis is displayed inside the content area, decreasing the amount of text displayed. If there is not enough space to display the ellipsis, it is clipped. |

## Examples

```css
p {
  width: 200px;
  border: 1px solid;
  padding: 2px 5px;

  /* BOTH of the following are required for text-overflow */
  white-space: nowrap;
  overflow: hidden;
}

.overflow-visible {
  white-space: initial;
}

.overflow-clip {
  text-overflow: clip;
}

.overflow-ellipsis {
  text-overflow: ellipsis;
}

.overflow-string {
  /* Not supported in most browsers,
     see the 'Browser compatibility' section below */
  text-overflow: " ..]";
}
```

```html
<p class="overflow-visible">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>

<p class="overflow-clip">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>

<p class="overflow-ellipsis">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>

<p class="overflow-string">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
```
