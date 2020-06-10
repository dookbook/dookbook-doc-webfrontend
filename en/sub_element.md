TOPICS: <sub>

# HTML Subscript element: `<sub>`

The **HTML Subscript element** (**`<sub>`**) specifies inline text which should be displayed as **subscript**
for solely typographical reasons. Subscripts are typically rendered with a
lowered baseline using smaller text.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content*. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts *phrasing content*.|
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

The `<sub>` element should be used only for **typographical reasons** — that is,
to change the position of the text to comply with typographical conventions or standards,
rather than solely for presentation or appearance purposes.

For example, using `<sub>` to style the name of a company which uses altered baselines in their
wordmark would not be appropriate; instead, [[CSS]] should be used (likely the
*`vertical-align`* property, such as *`vertical-align: sub`* or,
to more precisely control the baseline shift, `vertical-align: -25%`.

Appropriate use cases for `<sub>` include (but aren't necessarily limited to):

- Marking up *footnote numbers*. See Footnote numbers for an example as below.
- Marking up *the subscript in mathematical variable numbers* (although you may also consider using a
*MathML* formula for this). See Variable subscripts for an example as below.
- Denoting the number of atoms of a given element within a *chemical formula* (such as every
developer's best friend, C~8~H~10~N~4~O~2~,
otherwise known as "caffeine"). See Chemical formulas.

## Examples

### Footnote Numbers

Traditional footnotes are denoted using numbers which are rendered in subscript.
This is a common use case for `<sub>`:

```html
<p>According to the computations by Nakamura, Johnson, and
Mason<sub>1</sub> this will result in the complete annihilation
of both particles.</p>
```

### Variable Subscripts

In mathematics, families of variables related to the same concept (such as distances along the same
axis) are represented using the same variable name with a subscript following. For example:

```html
<p>The horizontal coordinates' positions along the X-axis are
represented as <var>x<sub>1</sub></var> ... <var>x<sub>n</sub></var>.</p>
```

### Chemical Formulas

When writing a chemical formula, such as H~2~0, the number of atoms of a given element
within the described molecule is represented using a subscripted number; in the case of water,
the subscripted "2" indicates that there are two atoms of hydrogen in the molecule.

```html
<p>The chemical formula of water: H<sub>2</sub>O</p>
```

### Another Example

```html
<p>Almost every developer's favorite molecule is
C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>, which is
commonly known as "caffeine."</p>
```

## Browser compatibility

| - | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `<sub>` | support | support | support |
