TOPICS: will-change property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS Property: `will-change`

The CSS **`will-change`** property provides a way for web developers to tell the browser what changes
the element will make, so that the browser can prepare for the corresponding optimization in advance
before the element property actually changes . This kind of optimization can prepare a part of the
complicated calculation work in advance, making the page response more rapid and sensitive.

It is not easy to use this property well:

- **Don't apply `will-change` to too many elements**: The browser has tried its best to optimize
everything that can be optimized. There are some more powerful optimizations. If combined with
**`will-change`**, it may consume a lot of machine resources. If it is overused, it may cause
*pages to respond slowly* or *consumption of a lot of resources*.

- **Use sparingly**: Usually, when the element is restored to its original state, the browser will
discard the optimization work done before. However, if the **`will-change`** property is explicitly
declared directly in the style sheet, it means that the target element may change frequently, and
the browser will save the optimization work longer than before. So the best practice is to switch
the value of **`will-change`** through the script before and after the element changes.

- **Don't apply `will-change` optimization prematurely**: If your page has no problem with performance,
don’t add **`will-change`** property to squeeze a little bit of speed. **`will-change`** was
originally designed as a final optimization method to try to solve existing performance problems.
It should not be used to prevent performance problems. Excessive use of **`will-change`** will result
in a large amount of memory usage and will lead to a more complicated rendering process, because the
browser will try to prepare for possible changes. This can lead to more serious performance problems.

- **Give it enough work time**: This property is used to let the page developer tell the browser
which property may change. Then the browser can choose to do some optimization work in advance
before the change occurs. So it is very important to give the browser a little time to really do
these optimizations. When using it, you need to try to find some methods to know the possible
changes of the element in advance, and then add **`will-change`** property to it.

## Property value

| Property Value | Description |
| :--- | :--- |
| **`auto`** | It means that there is no specific specification of which property will change. The browser needs to guess it by itself, and then use some conventional methods that the browser often uses to optimize. |
| **scroll-position** | Indicates that the developer hopes to **change the position of the scroll bar** or **animate it** in the near future. |
| **contents** | Indicates that the developer hopes to **change something in the element content** in the near future**, or animate them**. |
| **custom-ident** | Indicates that the developer hopes to **change the specified property name** or **animate it** in the near future. If the property name is abbreviated, it represents all the abbreviated or fully written property corresponding to it. |

## Examples

```css
.sidebar {
  will-change: transform;
}
```

The above example adds the **`will-change`** property directly to the style sheet, which will cause
the browser to keep the corresponding optimization work in memory all the time. This is actually
unnecessary. We have seen why we should avoid it before. Such an approach. Here is another example
showing how to use scripts to properly apply the **`will-change`** property. In most scenarios,
you should do this.

```javascript
var el = document.getElementById('element');

// Set the will-change property to the element when the mouse moves over the element
el.addEventListener('mouseenter', hintBrowser);
// Clear the will-change property when the CSS animation ends
el.addEventListener('animationEnd', removeHint);

function hintBrowser() {
  // Fill in the CSS property names you know that will change in the CSS animation
  this.style.willChange = 'transform, opacity';
}

function removeHint() {
  this.style.willChange = 'auto';
}
```

However, if an application will turn pages when the keyboard is pressed, such as albums or slideshows,
its pages are very large and complicated. In this case, write **`will-change`** in the style sheet.
Is appropriate. This will make the browser prepare the transition animation in advance, and when the
keyboard is pressed, you can immediately see the flexible and light animation.

```css
.slide {
  will-change: transform;
}
```
