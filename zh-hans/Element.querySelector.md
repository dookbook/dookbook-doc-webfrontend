TOPICS: Element.querySelector
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.querySelector()`

返回与指定的选择器组匹配的元素的后代的第一个元素。

## 语法

```javascript
element = baseElement.querySelector(selectors);
```

- `element` 和 `baseElement` 是 `element` 对象.
- `selectors` 是一个CSS选择器字符串( `selectors` )

| 参数 | 说明 |
| :-- | :-- |
| `selectors` | 一组用来匹配`Element` `baseElement`后代元素的选择器selectors；必须是合法的CSS选择器，否则会引起语法错误。返回匹配指定选择器的第一个元素。

## 返回值

基础元素（baseElement）的子元素中满足指定选择器组的第一个元素。匹配过程会对整个结构进行，包括基础元素和他的后代元素的集合以外的元素，也就是说，选择器首先会应用到整个文档，而不是基础元素，来创建一个可能有匹配元素的初始列表。然后从结果元素中检查它们是否是基础元素的后代元素。第一个匹配的元素将会被`querySelector()`方法返回。

如果没有找到匹配项，返回值为`null`。

## 异常

|  |  |
| :-- | :-- |
| **`SyntaxError`** | 指定的选择器无效。

## 示例

### 查找一个具有特殊属性值的元素

在第一个例子中，会返回HTML文档里第一个没有`type`属性或者有值为`“text/css”`的`type`属性的`<style>`元素:

```javascript
let el = document.body.querySelector("style[type='text/css'], style:not([type])");
```

### 整个层次结构有效

下面的例子演示了在应用选择器时考虑整个文档的层次结构, 因此在定位匹配时仍然考虑指定的 `baseElement` 之外的级别。

```html
<div>
  <h5>Original content</h5>
  <p>
    inside paragraph
    <span>inside span</span>
    inside paragraph
  </p>
</div>
<div>
  <h5>Output</h5>
  <div id="output"></div>
</div>
```

```javascript
var baseElement = document.querySelector("p");
document.getElementById("output").innerHTML =
         (baseElement.querySelector("div span").innerHTML);
```

!!! warn "注意"
    尽管基础元素没有包括选择器中含有的 `div` 元素，选择器`"div span"`依旧匹配了其中的`<span>`元素。
