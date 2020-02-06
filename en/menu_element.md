TOPICS: <menu>
        <menu> label attribute

# HTML Menu Element: `<menu>`

!!! warn "Experimental Technology"
    This is an **experimental technology**.
    Check the browser compatibility carefully before using this in production.
    Currently, no browser support it!

The **HTML `<menu>` element** represents **a group of commands** that a user can perform or activate.
This includes both *list menus*, which might appear across the top of a screen, as well as *context menus*,
such as those that might appear underneath a button after it has been clicked.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*. Additionally, if in the *list menu* state, *palpable content*. (*list menu* is the default state) |
| **Permitted content** | If the element is in the *list menu* state: *flow content*, or alternatively, zero or more occurrences of [`<li>`](/en/webfrontend/<li>), [`<script>`](/en/webfrontend/<script>), and [`<template>`](/en/webfrontend/<template>).<br>If the element is in the *context menu* state: zero or more occurrences, in any order, of `<menu>` (*context menu* state only), `<menuitem>`, [`<hr>`](/en/webfrontend/<hr>), [`<script>`](/en/webfrontend/<script>), and [`<template>`](/en/webfrontend/<template>). |
| **Tag omission**| None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLMenuElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`label`** | The **name of the menu** as shown to the user. Used within nested menus, to provide a label through which the submenu can be accessed. Must only be specified when the parent element is a `<menu>` in the *context menu* state.
| ~~`type`~~ | (**Obsolete**) This attribute indicates the **kind of menu** being declared, and can be one of two values.<br><br>**`context`**: Indicates the *popup menu* state, which represents a group of commands activated through another element. This value is the default if the attribute is missing and the parent element is also a `<menu>` element.<br><br>**`toolbar`**: Indicates the *toolbar state*, which represents a **toolbar consisting of a series of commands** for user interaction. This value is the default if the attribute is missing.

!!! error ""
    Menu buttons haven't been implemented in any known browsers yet. The `type` attribute on
    the `<menu>` element is now obsolete.

## Usage Notes

The `<menu>` and **[`<ul>`](/en/webfrontend/<ul>)** elements both represent an unordered list of items.
The key difference is that [`<ul>`](/en/webfrontend/<ul>) primarily contains items for display,
whilst `<menu>` is intended for interactive items, to act on.

!!! error ""
    [`<menuitem>`](/en/webfrontend/<menuitem>) element is obsolete.

This element was *deprecated* in HTML 4, but reintroduced in HTML 5.1 and the HTML living standard.

## Context Menu

!!! error "Be aware that this feature may cease to work at any time."
    This feature is **no longer recommended**. Though some browsers might still support it, it may have
    already been **removed** from the relevant web standards, may be in the process of being **dropped**,
    or may only be kept for compatibility purposes. Avoid using it, and update existing code.

Context menus consist of a `<menu>` element
which contains *[`<menuitem>`](/en/webfrontend/<menuitem>)* (**deprecated**) elements for each
selectable option in the menu, `<menu>` elements for submenus within the menu, and *[`<hr>`](/en/webfrontend/<hr>)*
elements for separator lines to break up the menu's content into sections.

Context menus are then
attached to the element they're activated from using either the associated element's *`contextmenu`*
attribute or, for button-activated menus attached to *[`<button>`](/en/webfrontend/<button>)* elements,
the *`menu`* attribute.

```html
<!-- A <div> element with a context menu -->
<div contextmenu="popup-menu">
  Right-click to see the adjusted context menu
</div>

<menu type="context" id="popup-menu">
  <menuitem>Action</menuitem>
  <menuitem>Another action</menuitem>
  <hr/>
  <menuitem>Separated action</menuitem>
</menu>
```

```css
div {
  width: 300px;
  height: 80px;
  background-color: lightgreen;
}
```

### Menu Button

Context menus are also for button-activated menus
attached to *[`<button>`](/en/webfrontend/<button>)* elements, the *`menu`* attribute.

```html
<!-- A button, which displays a menu when clicked. -->
<button type="menu" menu="popup-menu">
  Dropdown
</button>

<menu type="context" id="popup-menu">
  <menuitem>Action</menuitem>
  <menuitem>Another action</menuitem>
  <hr/>
  <menuitem>Separated action</menuitem>
</menu>
```

### Toolbar Menu

!!! error ""
    Toolbar menus haven't been implemented in any known browsers yet.

Toolbar menus consist of a `<menu>` element whose content is described in one of two ways:
either as an unordered list of items represented by *[`<li>`](/en/webfrontend/<li>)* elements
(each representing a command or option the user can utilize), or (if there are no
[`<li>`](/en/webfrontend/<li>) elements), flow content describing the available commands and options.

```html
<!-- A context menu for a simple editor,
   - containing two menu buttons. -->
<menu type="toolbar">
  <li>
    <button type="menu" menu="file-menu">File</button>
    <menu type="context" id="file-menu">
      <menuitem label="New..." onclick="newFile()">
      <menuitem label="Save..." onclick="saveFile()">
    </menu>
  </li>
  <li>
    <button type="menu" menu="edit-menu">Edit</button>
    <menu type="context" id="edit-menu">
      <menuitem label="Cut..." onclick="cutEdit()">
      <menuitem label="Copy..." onclick="copyEdit()">
      <menuitem label="Paste..." onclick="pasteEdit()">
    </menu>
  </li>
</menu>
```
