TOPICS: Element.getAttributeNames

# `Element.getAttributeNames()`

`Element`接口的 **`releasePointerCapture()`** 方法释放（停止）指针捕获，该捕获先前是为特定（PointerEvent）指针设置的。

有关指针捕获的说明以及如何为特定元素设置指针的方法，请参见[`Element.setPointerCapture()`](/zh-hans/webfrontend/Element.setPointerCapture)方法。

## 语法

```javascript
targetElement.releasePointerCapture(pointerId);
```

| 参数 | 说明 |
| :-- | :-- |
| `pointerId` | 一个`PointerEvent`对象的`pointerId`. |

**返回值**：此方法返回`undefined`。

## 例外情况

| 例外情况 | 说明 |
| :-- | :-- |
| `InvalidPointerId` | `pointerId`与任何活动指针都不匹配.|

## 示例

本示例在您按下[`<div>`](/zh-hans/webfrontend/<div>)时将其设置。 这样，即使指针移到其边界之外，也可以水平滑动该元素。

```html
<div id="slider">SLIDE ME</div>
```

```css
div {
  width: 140px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #fbe;
}
```

```javascript
function beginSliding(e) {
  slider.onpointermove = slide;
  slider.setPointerCapture(e.pointerId);
}

function stopSliding(e) {
  slider.onpointermove = null;
  slider.releasePointerCapture(e.pointerId);
}

function slide(e) {
  slider.style.transform = `translate(${e.clientX - 70}px)`;
}

const slider = document.getElementById('slider');

slider.onpointerdown = beginSliding;
slider.onpointerup = stopSliding;
```
