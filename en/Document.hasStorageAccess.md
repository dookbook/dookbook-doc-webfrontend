TOPICS: Document.hasStorageAccess
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.hasStorageAccess()`

The **`hasStorageAccess()`** method of the `Document` interface returns a `Promise` that resolves with
a boolean value indicating whether the document has access to its first-party storage.

## Syntax

```javascript
Promise<boolean> hasStorageAccess()
```

**parameter**: No parameters

## Return value

A `Promise` that resolves with a boolean value indicating whether the document has access to its
first-party storage.

If the promise gets resolved and a user gesture event was being processed when the function was
originally called, the resolve handler will run as if a user gesture was being processed, so it
will be able to call APIs that require user activation.

## Examples

```javascript
document.hasStorageAccess().then(hasAccess => {
  if (hasAccess) {
    // storage access has been granted already.
  } else {
    // storage access hasn't been granted already;
    // you may want to call requestStorageAccess().
  }
});
```

## Specifications

The API is currently only at the proposal stage — the standardization process has yet to begin.
You can currently find specification details of the API at Apple's Introducing Storage Access API
blog post, and WHATWG HTML issue 3338 — Proposal: Storage Access API.
