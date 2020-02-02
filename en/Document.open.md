TOPICS: Document.open
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.open()`

The **`Document.open()`** method opens a document for writing.

This does come with some side effects. For example:

- All event listeners currently registered on the document, nodes inside the document, or the
document's window are removed.
- All existing nodes are removed from the document.

## Syntax

```javascript
document.open();
```

**parameter**: No parameters

**Return value**: A `Document` object instance.

## Examples

The following simple code opens the document and replaces its content with a number of different
HTML fragments, before closing it again.

```javascript
document.open();
document.write("<p>Hello world!</p>");
document.write("<p>I am a fish</p>");
document.write("<p>The number is 42</p>");
document.close();
```

## Notes

An automatic `document.open()` call happens when `document.write()` is called after the page has loaded.

For years Firefox and Internet Explorer additionally erased all JavaScript variables, etc., in
addition to removing all nodes. This is no longer the case.

## Gecko-specific notes

Starting with Gecko 1.9, this method is subject to the same same-origin policy as other properties,
and does not work if doing so would change the document's origin.

Starting with Gecko 1.9.2, `document.open()` uses the principal of the document whose URI it uses,
instead of fetching the principal off the stack. As a result, you can no longer call `document.write()`
into an untrusted document from chrome, even using wrappedJSObject. See Security check basics for
more about principals.

## Three-argument `document.open()`

There is a lesser-known and little-used three-argument version of `document.open()` , which is an
alias of `Window.open()` (see its page for full details).

This call, for example opens github.com in a new window, with its opener set to `null`:

```javascript
document.open('https://www.github.com','', 'noopener=true')
```

## Two-argument `document.open()`

Browsers used to support a two-argument `document.open()`, with the following signature:

```javascript
document.open(type, replace)
```

Where `type` specified the MIME type of the data you are writing (e.g. `text/html`) and replace if
set (i.e. a string of `"replace"`) specified that the history entry for the new document would replace
the current history entry of the document being written to.

This form is now obsolete; it won't throw an error, but instead just forwards to `document.open()`
(i.e. is the equivalent of just running it with no arguments).  The history-replacement behavior now
always happens.
