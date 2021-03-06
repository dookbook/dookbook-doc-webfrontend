TOPICS: <table>
        <thead>
        <tbody>
        <tfoot>
        <th>
        <tr>
        <td>
        <caption>
        <colgroup>
        <col>
        <col> span attribute
        <table> align attribute
        <table> bgcolor attribute

# HTML Table Element: `<table>`

The **HTML `<table>` element** represents **tabular data** — that is, information presented in a
**two-dimensional table** comprised of *rows* and *columns* of *cells* containing data.

The **`<tr>`** element defines **a row of cells** in a table. The row's cells can then be
established using a mix of
**`<td>`** (**data cell**, a cell of a table that contains data) and **`<th>`**
(**header cell**, a cell as header of a group of table cells) elements.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content* |
| **Permitted content** | In this order:<br>1. an optional **`<caption>`** element,<br>2. zero or more **`<colgroup>`** elements,<br>3. an optional **`<thead>`** element,<br>4. either one of the following: 4.1) zero or more **`<tbody>`** elements, 4.2) one or more `<tr>` elements, 4.3) an optional **`<tfoot>`** element<br>. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *flow content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLTableElement`** |

## Attributes

This element includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attributes | Description |
| :-- | :-- |
| `border` |Specifies whether the table cell has a border.|
| ~~`align`~~ | (**Obsolete**, use [[CSS]] instead) Specifies the **alignment** of the table relative to surrounding elements.|
| ~~`bgcolor`~~ | (**Obsolete**, use [[CSS]] instead) Specifies the **background color** of the table. |
| ~~`cellpadding`~~ | (**Not supported**, use [[CSS]] instead) Specifies the **space** between the cell edge and its content. |
| ~~`cellspacing`~~ | (**Not supported**, use [[CSS]] instead) Specifies the **space** between cells.。|
| ~~`frame`~~ | (**Not supported**, use [[CSS]] instead) Specifies which part of the **outer border** is visible.|
| ~~`rules`~~ | (**Not supported**, use [[CSS]] instead) Specifies which part of the **inner border** is visible.|

## Simple Table without Header

```html
<!-- Example: Simple table -->
<table>
  <tr>
    <td>Data: Row 1, Col 1</td>
    <td>Data: Row 1, Col 2</td>
  </tr>
  <tr>
    <td>Data: Row 2, Col 1</td>
    <td>Data: Row 2, Col 2</td>
  </tr>
</table>
```

## Simple Table with Header

```html
<!-- Example: Simple table with header -->
<table>
  <tr>
    <th>Header: Col 1</th>
    <th>Header: Col 2</th>
  </tr>

  <tr>
    <td>Data: Row 1, Col 1</td>
    <td>Data: Row 1, Col 2</td>
  </tr>
  <tr>
    <td>Data: Row 2, Col 1</td>
    <td>Data: Row 2, Col 2</td>
  </tr>
</table>
```

The **`<th>`** defines **a cell as header of a group of table cells**.
The exact nature of this group is defined by the **`scope`** and **`headers`** attributes.

### Table with Caption

By supplying a **`<caption>`** element whose value clearly and concisely describes the table's purpose,
it helps the people decide if they need to read the rest of the table content or skip over it.

**Accessibility Concerns**: This helps people navigating with the aid of assistive technology
such as a screen reader, people
experiencing low vision conditions, and people with cognitive concerns.

```html
<!-- Example: Table with Caption (or Title) -->
<table>
  <caption>Table Caption (or Title)</caption>

  <tr>
    <th>Header: Col 1</th>
    <th>Header: Col 2</th>
  </tr>
  <tr>
    <td>Data: Row 1, Col 1</td>
    <td>Data: Row 1, Col 2</td>
  </tr>
  <tr>
    <td>Data: Row 2, Col 1</td>
    <td>Data: Row 2, Col 2</td>
  </tr>
</table>
```

The **HTML Table Caption element** (**`<caption>`**) specifies **the caption (or title) of a table**,
and if used is always the **first** child of a `<table>`.
Its styling and physical position relative to
the table may be changed using the [[CSS]] **`caption-side`** and **`text-align`** properties.

More WAI tutorials, please refer to [Caption & Summary • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/caption-summary/).

## Table with `<thead>`, `<tfoot>` and `<tbody>`

The **`<thead>`** element defines a set of rows defining **the head of the columns** of the table.

The **`<tbody>`** encapsulates a set of table rows (*`<tr>`* elements),
indicating that they comprise the body of the table (`<table>`).

The **`<tfoot>`** element defines a set of rows summarizing the columns of the table.

```html
<!-- Example: Table with thead, tfoot, and tbody -->
<table>
  <caption>Table Caption (or Title)</caption>

  <thead>
    <tr>
      <th>Header content 1</th>
      <th>Header content 2</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Body content 1</td>
      <td>Body content 2</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td>Footer content 1</td>
      <td>Footer content 2</td>
    </tr>
  </tfoot>
</table>
```

## Table with Column Group

The **HTML Column Group element** (**`<colgroup>`**) defines **a group of columns** within a table.

The **`<col>`** element defines a column within a table and is used for defining common
semantics on all common cells. It is generally found within a *`<colgroup>`* element.

```html
<!-- Example: Table with Column Group -->
<table>
  <caption>Table Caption (or Title)</caption>
  <colgroup>
    <col class="column1">
    <col class="columns2plus3" span="2">
  </colgroup>
  <tr>
    <th>Lime</th>
    <th>Lemon</th>
    <th>Orange</th>
  </tr>
  <tr>
    <td>Green</td>
    <td>Yellow</td>
    <td>Orange</td>
  </tr>
</table>
```

## Accessibility Concerns

### Scoping rows and columns

The `scope` attribute on header elements is redundant in simple contexts, because scope is inferred.
However, some assistive technologies may fail to draw correct inferences, so specifying header scope
may improve user experiences. In complex tables, scope can be specified so as to provide necessary
information about the cells related to a header.

```html
<table>
  <caption>Color names and values</caption>
  <tbody>
    <tr>
      <th scope="col">Name</th>
      <th scope="col">HEX</th>
      <th scope="col">HSLa</th>
      <th scope="col">RGBa</th>
    </tr>
    <tr>
      <th scope="row">Teal</th>
      <td><code>#51F6F6</code></td>
      <td><code>hsla(180, 90%, 64%, 1)</code></td>
      <td><code>rgba(81, 246, 246, 1)</code></td>
    </tr>
    <tr>
      <th scope="row">Goldenrod</th>
      <td><code>#F6BC57</code></td>
      <td><code>hsla(38, 90%, 65%, 1)</code></td>
      <td><code>rgba(246, 188, 87, 1)</code></td>
    </tr>
  </tbody>
</table>
```

Providing a declaration of `scope="col"` on a `<th>` element will help describe that the cell is at
the top of a column. Providing a declaration of `scope="row"` on a `<td>` element will help describe
that the cell is the first in a row.

- [MDN Tables for visually impaired users](https://wiki.developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced#Tables_for_visually_impaired_users)
- [Tables with two headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/multi-level/)
- [Tables with irregular headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/irregular/)
- [H63: Using the scope attribute to associate header cells and data cells in data tables | W3C Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H63.html)

### Complicated tables

Assistive technology such as screen readers may have difficulty parsing tables that are so complex
that header cells can’t be associated in a strictly horizontal or vertical way. This is typically
indicated by the presence of the `colspan` and `rowspan` attributes.

Ideally, consider alternate ways to present the table's content, including breaking it apart into a
collection of smaller, related tables that don't have to rely on using the `colspan` and `rowspan`
attributes. In addition to helping people who use assistive technology understand the table's content,
this may also benefit people with cognitive concerns who may have difficulty understanding the
associations the table layout is describing.

If the table cannot be broken apart, use a combination of the `id` and `headers`
attributes to programmatically associate each table cell with the header(s) the cell is associated with.

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<table>`| support | support | support |
| `<tr>` | support | support | support |
| `<td>`| support | support | support |
| `<th>`| support | support | support |
| `<caption>`| support | support | support |
| `<thead>`| support | support | support |
| `<tbody>`| support | support | support |
| `<tfoot>`| support | support | support |
| `<col>`| support | support | support |
| `<colgroup>` | support | support | support |

- [MDN Tables for visually impaired users](https://wiki.developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced#Tables_for_visually_impaired_users)
- [Tables with multi-level headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/multi-level/)
- [H43: Using id and headers attributes to associate data cells with header cells in data tables | Techniques for W3C WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H43.html)
