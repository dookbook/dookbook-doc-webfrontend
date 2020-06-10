TOPICS: <small>

# HTML Small Font Element: `<small>`

The **HTML `<small>` element** makes the text **font size one size smaller** (for example, from large
to medium, or from small to x-small) down to the browser's minimum font size.  In HTML5, this
element is repurposed to represent *side-comments* and *small print*, including *copyright* and
*legal text*,independent of its styled presentation.
If the enclosed font is already the smallest size supported by the font model, the `<small>` tag will
have no effect.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content* |
| **Permitted content** | *Phrasing content* |
| **Tag omission** | None, must have both a start tag and an end tag.|
| **Permitted parents** | Any element that accepts *phrasing content*, or any element that accepts *flow content*.|
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Examples

### Example 1

```html
<p>This is the first sentence.
  <small>This whole sentence is in small letters.</small>
</p>
```

### Example 2 (CSS alternative)

```html
<p>This is the first sentence.
  <span style="font-size:0.8em;">This whole sentence is in small letters.</span>
</p>
```

## Notes

Although the `<small>` element, like the [`<b>`](/en/webfrontend/<b>) and
[`<i>`](/en/webfrontend/<i>) elements, may be perceived to violate the principle of separation
between structure and presentation, all three are valid in HTML5. Authors are encouraged to use
their best judgement when determining whether to use `<small>` or [[CSS]].

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<small>` | support | support | support |
