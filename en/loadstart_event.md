TOPICS: onloadstart
        loadstart
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `loadstart` Event

The **`onloadstart`** property of the `GlobalEventHandlers` mixin is an `EventHandler` representing
the code to be called when the **`loadstart`** event is raised (when progress has begun on the
loading of a resource.)

## Syntax

```javascript
img.onloadstart = funcRef;
```

`funcRef` is the handler function to be called when the resource's `loadstart` event fires.

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
