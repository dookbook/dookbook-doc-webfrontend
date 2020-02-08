TOPICS: <details>
        <summary>
        <details> open attribute

# HTML Details and Disclosure Summary: `<details>` and `<summary>`

The **HTML Details Element** (**`<details>`**) creates a *disclosure widget* in which information is
visible only when the widget is toggled into an "*open*" state.

The **HTML Disclosure Summary element** (**`<summary>`**) element
specifies a **summary**, **caption**, **label**,
or **legend** for a *`<details>`* element's disclosure box.

## `<details>` Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *sectioning root*, *interactive content*, *palpable content*. |
| **Permitted content** | One *`<summary>`* element followed by *flow content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLDetailsElement`** |

## `<summary>` Technical Summary

|  |  |
| :-- | :-- |
| **Permitted content** | *Phrasing content* or one element of *Heading content* |
| **Tag omission** | None, both the start tag and the end tag are mandatory. |
| **Permitted parents** | The *`<details>`* element. |
| **Permitted ARIA roles** | `button` |
| **DOM interface** | **`HTMLElement`** |

## `<details>` Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`open`** | This *Boolean* attribute indicates whether or not the details — that is, the contents of the `<details>` element — are currently **visible**. The default, *`false`*, means the details are not visible.

## Usage Notes

A disclosure widget is typically presented onscreen using a *small triangle* which *rotates* (or *twists*)
to indicate open/closed status, with a label next to the triangle.
If a *`<summary>`* exists, the contents of the `<summary>` element are
used as the label for the disclosure widget.
Otherwise, the user agent will use a default string (typically "*Details*")
as the label for the disclosure box.

A `<summary>` element may only be used as the first child of a `<details>` element.
Clicking the `<summary>` element toggles the
state of the widget open and closed.

## A simple disclosure example

This example shows a `<details>` element with no provided summary.

```html
<details>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

In this situation, the browser will use a default summary string (usually "*Details*").

## Example: Providing a summary

This example **adds a summary** to the above example by using the *`<summary>`* element inside `<details>`,
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

## Example: Creating an open disclosure box

To start the `<details>` box in its open state, add the Boolean **`open`** attribute:

```html
<details open>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

## CSS Style

You can use [[CSS]] to style the disclosure widget, and you can programmatically open and
close the widget by setting/removing its *`open`* attribute.

!!! warn ""
    Note: Unfortunately, at this time there's no built-in way to animate the
    transition between open and closed.

Fully standards-compliant implementations automatically apply the CSS **`display: list-item`** to the
*`<summary>`*, which is typically a triangle..
You can also change the style to **`display: block`** to remove the disclosure triangle.
You can use this to customize its appearance further.

Here is a example of **customizing the disclosure widget** for further details.

```html
<details>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

The disclosure triangle itself can be customized, although this is not as broadly supported.
There are variations in how browsers support this customization due to experimental implementations
as the element was standardized, so we'll have to use multiple approaches for a while.

The `<summary>` element supports the **`list-style`** shorthand property and its longhand properties,
such as *`list-style-type`*, to change the disclosure triangle to whatever you choose
(usually with *`list-style-image`*). For example,
we can remove the disclosure widget icon by setting *`list-style: none`*.

Chrome doesn't support this yet, however, so we also need to use its
non-standard **`::-webkit-details-marker`** pseudo-element to customize the appearance in that browser.

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

## `toggle` Event

In addition to the usual events supported by HTML elements, the `<details>` element supports the
**`toggle`** event, which is dispatched to the `<details>` element whenever its state changes
between *open* and *closed*. It is sent after the state is changed, although if the state changes
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
