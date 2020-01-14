TOPICS: Document.createCDATASection
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createCDATASection()`

**`createCDATASection()`** creates a new `CDATA` section node, and returns it.

## Syntax

```javascript
var CDATASectionNode = document.createCDATASection(data);
```

- `CDATASectionNode` is a `CDATA` Section node.
- `data` is a string containing the data to be added to the `CDATA` Section.

## Examples

```javascript
var docu = new DOMParser().parseFromString('<xml></xml>', 'application/xml')

var cdata = docu.createCDATASection('Some <CDATA> data & then some');

docu.getElementsByTagName('xml')[0].appendChild(cdata);

alert(new XMLSerializer().serializeToString(docu));
// Displays: <xml><![CDATA[Some <CDATA> data & then some]]></xml>
```

## Notes

- This will only work with XML, not HTML documents (as HTML documents do not support CDATA sections);
attempting it on an HTML document will throw `NOT_SUPPORTED_ERR`.
- Will throw a `NS_ERROR_DOM_INVALID_CHARACTER_ERR` exception if one tries to submit the closing CDATA
sequence (`"]]>"`) as part of the data, so unescaped user-provided data cannot be safely used
without with this method getting this exception (`createTextNode()` can often be used in its place).
