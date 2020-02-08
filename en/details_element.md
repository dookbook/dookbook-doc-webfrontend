TOPICS: <details>
        <summary>

# `<details>`

The **HTML Details Element (`<details>`)** creates a disclosure widget in which information is
visible only when the widget is toggled into an "open" state. A summary or
label can be provided using the `<summary>` element.

A disclosure widget is typically presented onscreen using a small triangle which rotates (or twists)
to indicate open/closed status, with a label next to the triangle. If the first child of the
`<details>` element is a `<summary>`, the contents of the `<summary>` element are
used as the label for the disclosure widget.

!!! warn "Don't try this at home"
    Note: The common use of a triangle which rotates or twists around to represent opening or closing
    the widget is why these are sometimes called "twisties."

A `<details>` widget can be in one of two states. The default closed state displays only the triangle
and the label inside `<summary>` (or a user agent-defined default string if no `<summary>`).
This might look like the following:

Here we see a standard disclosure widget with the label "System Requirements", in its default closed
state. When the user clicks on the widget, or focuses it then presses the space bar,
it "twists" open, revealing its contents:

From there, you can use CSS to style the disclosure widget, and you can programmatically open and
close the widget by setting/removing its open attribute.

By default when closed, the widget is only tall enough to display the disclosure triangle and summary.
When open, it expands to display the details contained within.

!!! warn "Don't try this at home"
    Note: Unfortunately, at this time there's no built-in way to animate the
    transition between open and closed.

Fully standards-compliant implementations automatically apply the CSS `display: list-item` to the
`<summary>` element. You can use this to customize its appearance further.
See Customizing the disclosure widget for further details.

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *sectioning root*, *interactive content*, *palpable conten*t. |
| **Permitted content** | One `<summary>` element followed by *flow content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLDetailsElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `open` | This Boolean attribute indicates whether or not the details — that is, the contents of the `<details>` element — are currently visible. The default, `false`, means the details are not visible. |

## Events

In addition to the usual events supported by HTML elements, the `<details>` element supports the
`toggle` event, which is dispatched to the `<details>` element whenever its state changes
between open and closed. It is sent after the state is changed, although if the state changes
multiple times before the browser can dispatch the event,
the events are coalesced so that only one is sent.

You can listen for the `toggle` event to detect when the widget changes state:

```javascript
details.addEventListener("toggle", event => {
  if (details.open) {
    /* the element was toggled open */
  } else {
    /* the element was toggled closed */
  }
});
```

## `<summary>`

The **HTML Disclosure Summary element (`<summary>`)** element specifies a summary, caption,
or legend for a `<details>` element's disclosure box. Clicking the `<summary>` element toggles the
state of the parent `<details>` element open and closed.

|  |  |
| :-- | :-- |
| **Permitted content** | *Phrasing content* or one element of *Heading content*. |
| **Tag omission** | None, both the start tag and the end tag are mandatory. |
| **Permitted parents** | The `<details>` element. |
| **Permitted ARIA roles** | `button` |
| **DOM interface** | **`HTMLElement`** |

## Usage Notes

The `<summary>` element's contents can be any heading content, plain text,
or HTML that can be used within a paragraph.

A `<summary>` element may only be used as the first child of a `<details>` element. When the user
clicks on the summary, the parent `<details>` element is toggled open or closed, and then a
`toggle` event is sent to the `<details>` element, which can be used to
let you know when this state change occurs.

### Default label text

If a `<details>` element's first child is not a `<summary>` element, the user agent will use a
default string (typically "Details") as the label for the disclosure box.

### Default style

Per the HTML specification, the default style for `<summary>` elements includes `display: list-item`.
This makes it possible to change or remove the icon displayed as the disclosure widget next to the
label from the default, which is typically a triangle.

You can also change the style to `display: block` to remove the disclosure triangle.

See the Browser compatibility section for details, as not all
browsers support full functionality of this element yet.

## Examples

### A simple disclosure example

This example shows a `<details>` element with no provided summary.

```html
<details>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

In this situation, the browser will use a default summary string (usually "Details"). Here's what
your browser does with it:

### Providing a summary

This example adds a summary to the above example by using the `<summary>` element inside `<details>`,
like this:

```html
<details>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

### Creating an open disclosure box

To start the `<details>` box in its open state, add the Boolean `open` attribute:

```html
<details open>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

### Customizing the appearance

Now let's apply some CSS to customize the appearance of the disclosure box.

```css
details {
  font: 16px "Open Sans", "Arial", sans-serif;
  width: 620px;
}

details > summary {
  padding: 2px 6px;
  width: 15em;
  background-color: #ddd;
  border: none;
  box-shadow: 3px 3px 4px black;
}

details > p {
  border-radius: 0 0 10px 10px;
  background-color: #ddd;
  padding: 2px 6px;
  margin: 0;
  box-shadow: 3px 3px 4px black;
}
```

This CSS creates a look similar to a tabbed interface, where clicking the
tab opens it to reveal its contents.

```html
<details>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

### Customizing the disclosure widget

The disclosure triangle itself can be customized, although this is not as broadly supported.
There are variations in how browsers support this customization due to experimental implementations
as the element was standardized, so we'll have to use multiple approaches for a while.

The `<summary>` element supports the `list-style` shorthand property and its longhand properties,
such as `list-style-type`, to change the disclosure triangle to whatever you choose
(usually with `list-style-image`). For example,
we can remove the disclosure widget icon by setting `list-style: none`.

Chrome doesn't support this yet, however, so we also need to use its
non-standard `::-webkit-details-marker` pseudo-element to customize the appearance in that browser.

```css
details {
  font: 16px "Open Sans", "Arial", sans-serif;
  width: 620px;
}

details > summary {
  padding: 2px 6px;
  width: 15em;
  background-color: #ddd;
  border: none;
  box-shadow: 3px 3px 4px black;
  list-style: none;
}

details > summary::-webkit-details-marker {
  display: none;
}

details > p {
  border-radius: 0 0 10px 10px;
  background-color: #ddd;
  padding: 2px 6px;
  margin: 0;
  box-shadow: 3px 3px 4px black;
}
```

This CSS creates a look similar to a tab interface, where activating the
tab expands and opens it to reveal its contents.

```html
<details>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```
