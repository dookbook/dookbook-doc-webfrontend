TOPICS: <ol>
        <li>
        <ol> reversed attribute
        <ol> start attribute

# HTML Ordered List Element: `<ol>`

The **HTML `<ol>` element** represents an **ordered list of items**, typically rendered as a
numbered list.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, and if the `<ol>` element's children include at least one `<li>` element, *palpable content*.
| **Permitted content** | Zero or more **`<li>`** elements, which in turn often contain nested *`<ol>`* or *[`<ul>`](/en/webfrontend/<ul>)* elements.
| **Tag omission** | None, both the starting and ending tag are mandatory.
| **Permitted parents** | Any element that accepts *flow content*.
| **Permitted ARIA roles** | `directory`, `group`, `listbox`, `menu`, `menubar`, `radiogroup`, `tablist`, `toolbar`, `tree`, `presentation` |
| **DOM interface** | **`HTMLOListElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`reversed`** | This *Boolean* attribute specifies that the items of the list are specified in **reversed order**. |
| **`start`** | This *integer* attribute specifies the **start value for numbering** the individual list items. Although the ordering type of list elements might be Roman numerals, such as XXXI, or letters, the value of start is always represented as a number. To start numbering elements from the letter `"C"`, use `<ol start="3">`.<br>**Note:** This attribute was deprecated in HTML 4, but reintroduced in HTML 5.
| ~~`compact`~~ | (**Deprecated**. CSS property **`line-height`** shoule be used instead, default value is `80%`.) This Boolean attribute hints that the list should be rendered in a **compact style**. The interpretation of this attribute depends on the user agent and it doesn't work in all browsers.
| ~~`type`~~ | (**Deprecated**. CSS property **`list-style-type`** should be used instead.) Indicates the numbering type:<br>*`'a'`* indicates lowercase letters,<br>*`'A'`* indicates uppercase letters,<br>*`'i'`* indicates lowercase Roman numerals,<br>*`'I'`* indicates uppercase Roman numerals,<br>and *`'1'`* indicates numbers (default). |

## Usage Notes

- There is no limitation to the depth and alternation of nested lists defined with the `<ol>` and
[`<ul>`](/en/webfrontend/<ul>) elements.
- The `<ol>` and [`<ul>`](/en/webfrontend/<ul>) both represent a list of items.
They differ in the way that,
with the `<ol>` element, the order is meaningful. As a rule of thumb to determine which one to use,
try changing the order of the list items; if the meaning is changed, the `<ol>` element should be used,
else the *[`<ul>`](/en/webfrontend/<ul>)* is adequate.

## HTML List Item Element: `<li>`

|  |  |
| :-- | :-- |
| **Content categories** | None. |
| **Permitted content** | *Flow content*. |
| **Tag omission** | The end tag can be omitted if the list item is immediately followed by another `<li>` element, or if there is no more content in its parent element. |
| **Permitted ARIA roles** | `menuitem` `menuitemcheckbox`, `menuitemradio`, `option`, `presentation`, `radio`, `separator`, `tab`, `treeitem` |
| **DOM interface** | **`HTMLLIElement`** |

### Attributes of `<li>`

| Attribute | Description |
| :-- | :-- |
| `value` | This *integer* attribute indicates the current ordinal value of the list item as defined by the `<ol>` element. The only allowed value for this attribute is a number, even if the list is displayed with Roman numerals or letters. List items that follow this one continue numbering from the value set.<br>**Note:** This attribute was deprecated in HTML 4, but reintroduced in HTML 5.

## Examples

For more detailed examples, see the `<ol>` and [`<ul>`](/en/webfrontend/<ul>) pages.

### Simple Ordered List

```html
<ol>
  <li>first item</li>
  <li>second item</li>
  <li>third item</li>
</ol>
```

### Ordered List with a Custom Attributes

```html
<ol start="3">
  <li>third item</li>
  <li>fourth item</li>
  <li>fifth item</li>
</ol>
```

### Nested Ordered List

```html
<ol>
  <li>first item</li>
  <li>second item      <!-- Look, the closing </li> tag is not placed here! -->
    <ol>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ol>
  </li>                <!-- Here is the closing </li> tag -->
  <li>third item</li>
</ol>
```

### Nested `<ol>` and `<ul>`

```html
<ol>
  <li>first item</li>
  <li>second item      <!-- Look, the closing </li> tag is not placed here! -->
    <ul>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ul>
  </li>                <!-- Here is the closing </li> tag -->
  <li>third item</li>
</ol>
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<ol>`| support | support | support |
| `<li>`| support | support | support |
