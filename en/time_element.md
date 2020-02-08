TOPICS: <time>
        <time> datetime attribute

# HTML Time Element: `<time>`

The **HTML `<time>` element** represents a **specific period in time**.

It may represent one of the following:

- A time on a **24-hour** clock.
- A precise date in the **Gregorian calendar** (with optional time and timezone information).
- A valid time duration.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content*.|
| **Permitted content** | *Phrasing content*.|
| **Tag omission** | None, both the starting and ending tag are mandatory.|
| **Permitted parents** | Any element that accepts *phrasing content*.|
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLTimeElement`** |

## Attributes

This element supports the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| **`datetime`** | This attribute indicates the **time and/or date** of the element and must be in one of the formats described below. |

## Usage Notes

This element is for presenting dates and times in a **machine readable** format,
allowing for better search engine results
or custom features such as reminders. For example, this can
help a user agent offer to add an event to a user's calendar.

This element should not be used for dates prior to the introduction of the Gregorian calendar
(due to complications in calculating those dates).

The datetime value (the machine-readable value of the datetime) is the value of the element’s
**`datetime`** attribute, which must be in the proper format (see below). If the element does not have
a `datetime` attribute, **it must not have any element descendants**, and the datetime value is the
element’s child text content.

## Valid Datetime Values

| `datetime` Value | Description |
| :-- | :-- |
| `2020`<br>`0001` | a valid **year** string. |
| `2020-01` | a valid **month** string. |
| `2020-01-01` | a valid **date** string. |
| `01-01` | a valid **yearless date** string. |
| `2020-W47` | a valid **week** string. |
| `18:00`<br>`18:00:00`<br>`18:00:00.929` | a valid **time** string. |
| `2020-01-01T18:00:00.929`<br>`2020-01-01 18:00:00.929` | a valid **local date and time** string. |
| `2020-01-01T18:00:00.929Z`<br>`2020-01-01T18:00:00.929-0400`<br>`2020-01-01T18:00:00.929-04:00`<br>`2020-01-01 18:00:00.929Z`<br>`2020-01-01 18:00:00.929-0400`<br>`2020-01-01 18:00:00.929-04:00` | a valid **global date and time** string. |
| `PT4H18M3S` | a valid **duration** string. |

## Simple Example

```html
<p>The concert starts at <time datetime="2018-07-07T20:00:00">20:00</time>.</p>

<p>The concert took place on <time
  datetime="2001-05-15T19:00">May 15</time>.</p>
```
