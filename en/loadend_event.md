TOPICS: onloadend
        loadend
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `loadend` Event

The **`onloadend`** property of the `GlobalEventHandlers` mixin is an `EventHandler` representing
the code to be called when the **`loadend`** event is raised (when progress has stopped on the
loading of a resource.)

## Syntax

```javascript
img.onloadend = funcRef;
```

`funcRef` is the handler function to be called when the resource's `loadend` event fires.

## Example

```html
<img src="myImage.jpg">
```

```javascript
// 'loadstart' fires first, then 'load', then 'loadend'

image.addEventListener('load', function(e) {
  console.log('Image loaded');
});

image.addEventListener('loadstart', function(e) {
  console.log('Image load started');
});

image.addEventListener('loadend', function(e) {
  console.log('Image load finished');
});
```
