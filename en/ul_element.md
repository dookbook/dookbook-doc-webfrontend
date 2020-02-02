TOPICS: <ul>
        <li>

# HTML Unordered List Element: `<ul>`, `<li>`

The **HTML `<ul>` element** represents an **unordered list** of items, typically rendered as a
bulleted list.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, and if the `<ul>` element's children include at least one `<li>` element, *Palpable content*.
| **Permitted content** | zero or more **`<li>`** elements, which in turn often contain nested *[`<ol>`](/en/webfrontend/<ol>)* or *`<ul>`* elements.
| **Tag omission** | None, both the starting and ending tag are mandatory.
| **Permitted parents** | Any element that accepts *flow content*.
| **Permitted ARIA roles** | `directory`, `group`, `listbox`, `menu`, `menubar`, `radiogroup`, `tablist`, `toolbar`, `tree`, `presentation` |
| **DOM interface** | **`HTMLUListElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| ~~`compact`~~ | (**Deprecated**) This Boolean attribute hints that the list should be rendered in a compact style. The interpretation of this attribute depends on the user agent and it doesn't work in all browsers.
| ~~`type`~~ | (**Deprecated**) Used to set the bullet style for the list. The values: *`circle`*, *`disc`*, *`square`*, *`triangle`* (defined in WebTV interface). |

## HTML List Item Element: `<li>`

|  |  |
| :-- | :-- |
| **Content categories** | None. |
| **Permitted content** | *Flow content*. |
| **Tag omission** | The end tag can be omitted if the list item is immediately followed by another `<li>` element, or if there is no more content in its parent element. |
| **Permitted ARIA roles** | `menuitem` `menuitemcheckbox`, `menuitemradio`, `option`, `presentation`, `radio`, `separator`, `tab`, `treeitem` |
| **DOM interface** | **`HTMLLIElement`** |

## Examples

### Simple example

```html
<ul>
  <li>first item</li>
  <li>second item</li>
  <li>third item</li>
</ul>
```

### Nesting list

```html
<ul>
  <li>first item</li>
  <li>second item
  <!-- Look, the closing </li> tag is not placed here! -->
    <ul>
      <li>second item first subitem</li>
      <li>second item second subitem
      <!-- Same for the second nested unordered list! -->
        <ul>
          <li>second item second subitem first sub-subitem</li>
          <li>second item second subitem second sub-subitem</li>
          <li>second item second subitem third sub-subitem</li>
        </ul>
      </li> <!-- Closing </li> tag for the li that
                  contains the third unordered list -->
      <li>second item third subitem</li>
    </ul>
  <!-- Here is the closing </li> tag -->
  </li>
  <li>third item</li>
</ul>
```

### Nested `<ul>` and `<ol>`

```html
<ul>
  <li>first item</li>
  <li>second item
  <!-- Look, the closing </li> tag is not placed here! -->
    <ol>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ol>
  <!-- Here is the closing </li> tag -->
  </li>
  <li>third item</li>
</ul>
```
