TOPICS: white-space property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `white-space`

The **`white-space`** CSS property sets **how white space inside an element is handled**.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`normal`** | Sequences of white space are collapsed. Newline characters in the source are handled the same as other white space. Lines are broken as necessary to fill line boxes. |
| **`nowrap`** | Collapses white space as for normal, but suppresses line breaks (text wrapping) within the source. |
| **`pre`** | Sequences of white space are preserved. Lines are only broken at newline characters in the source and at <br> elements. |
| **`pre-wrap`** | Sequences of white space are preserved. Lines are broken at newline characters, at <br>, and as necessary to fill line boxes. |
| **`pre-line`** | Sequences of white space are collapsed. Lines are broken at newline characters, at <br>, and as necessary to fill line boxes. |

The following table summarizes the behavior of the various `white-space` values:

| - | **New lines** | **Spaces and tabs** | **Text wrapping** | **End-of-line spaces** |
| :--- | --- | --- | --- | --- |
| `normal` | Collapse | Collapse | Wrap | Remove |
| `nowrap` | Collapse | Collapse | No wrap | Remove |
| `pre` | Preserve | Preserve | No wrap | Preserve |
| `pre-wrap` | Preserve | Preserve | Wrap | Hang |
| `pre-line` | Preserve | Collapse | Wrap | Remove |

## Examples

```css
p { white-space: normal; }
p { white-space: nowrap; }
p { white-space: pre; }
p { white-space: nowrap; }
p { white-space: pre-wrap; }
p { white-space: pre-line; }
```

```html
<p>This is some      text. This is some text. This is some text.
    This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.</p>
```
