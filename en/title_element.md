TOPICS: <title>

# HTML Title Element: `<title>`

The HTML `<title>` element defines the document's **title** that is shown in a browser's *title
bar* or a *page's tab*. It only contains text and TOPICS within the element are ignored.

## `<title>` Meta

|  |  |
| :-- | :-- |
| **Content categories** | *Metadata content*. |
| **Permitted content** | Text that is not inter-element whitespace. |
| **Tag omission** | Both opening and closing TOPICS are required. Note that leaving off `</title>` should cause the browser to ignore the rest of the page. |
| **Permitted parents** | A [`<head>`](/en/webfrontend/<head>/) element that contains no other `<title>` element. |
| **Permitted ARIA roles** | None |
| **DOM interface** | **`HTMLTitleElement`** |

## Usage Notes

The `<title>` element is always used within a page's [`<head>`](/en/webfrontend/<head>/) block.

### Page titles and SEO

The contents of a page title can have significant implications for
**[[search engine optimization]]** (**SEO**). In general, a longer, descriptive title will perform
better than short or uninspired titles. Not only is the content of the title one of the components
used by algorithms to decide the order in which to list pages in search results, but the title is
the initial "hook" by which you grab the attention of readers glancing at the search results page.

A few guidelines and tips for composing good titles:

- Avoid one or two word titles. Use a descriptive phrase, or a term/definition pairing for glossary
or reference-style pages.
- Search engines will typically display somewhere around the first *55-60* characters of a page title.
Text beyond that may be lost, so try not to have titles longer than that. If you must use a longer title,
make sure the important parts come earlier and that nothing critical is in the part of the title
that is likely to be dropped.
- Avoid special characters when possible; not all browsers will display them the same way.
For example, "`<`" often winds up displayed in the window title bar as "`&lt;`" (the HTML less-than entity).
- **Don't use "keyword blobs."** If your title is just a list of words, algorithms will
often artificially reduce your page's position in the search results.
- Try to make sure your titles are as unique as possible within your own site. Duplicate—or
near-duplicate—titles can contribute to inaccurate search results.
