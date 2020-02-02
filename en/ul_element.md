TOPICS: <ul>
        <li>

# HTML Unordered List Element: `<ul>`

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

## `<li>`

The **HTML `<li>` element** is used to represent an item in a list. It must be contained in a
parent element: an ordered list ([`<ol>`](/en/webfrontend/<ol>)), an unordered list (`<ul>`), or a menu
([`<menu>`](/en/webfrontend/<menu>)). In menus and unordered lists,
list items are usually displayed using bullet points.
In ordered lists, they are usually displayed with an ascending counter on the left,
such as a number or letter.

|  |  |
| :-- | :-- |
| **Content categories** | None. |
| **Permitted content** | Flow content. |
| **Tag omission** | The end tag can be omitted if the list item is immediately followed by another `<li>` element, or if there is no more content in its parent element. |
| **Permitted parents** | An `<ul>`, [`<ol>`](/en/webfrontend/<ol>), or [`<menu>`](/en/webfrontend/<menu>) element. Though not a conforming usage, the obsolete [`<dir>`](/en/webfrontend/<dir>) can also be a parent. |
| **Permitted ARIA roles** | `menuitem` `menuitemcheckbox`, `menuitemradio`, `option`, `presentation`, `radio`, `separator`, `tab`, `treeitem` |
| **DOM interface** | `HTMLLIElement` |

| Attribute | Description |
| :-- | :-- |
| `value` | This integer attribute indicates the current ordinal value of the list item as defined by the [`<ol>`](/en/webfrontend/<ol>) element. The only allowed value for this attribute is a number, even if the list is displayed with Roman numerals or letters. List items that follow this one continue numbering from the value set. The value attribute has no meaning for unordered lists (`<ul>`) or for menus ([`<menu>`](/en/webfrontend/<menu>)).<br>**Note:** This attribute was deprecated in HTML4, but reintroduced in HTML5.<br>**Note:** Prior to Gecko 9.0, negative values were incorrectly converted to 0. Starting in Gecko 9.0 all integer values are correctly parsed.
| `type` | This character attribute indicates the numbering type:<br>`a`: lowercase letters<br>`A`: uppercase letters<br>`i`: lowercase Roman numerals<br>`I`: uppercase Roman numerals<br>`1`: numbers
  
This type overrides the one used by its parent [`<ol>`](/en/webfrontend/<ol>) element, if any.

!!! warn "Don't try this at home"
    Usage note: This attribute has been deprecated: use the CSS `list-style-type` property instead.

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
