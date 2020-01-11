TOPICS: Element.closest
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.closest()`

**`Element.closest()`** 方法用来获取：匹配特定选择器且离当前元素最近的祖先元素（也可以是当前元素本身）。如果匹配不到，则返回 null。

## 语法

```javascript
var elt = element.closest(selectors);
```

| 参数 | 说明 |
| :-- | :-- |
| `selectors` | 是指定的选择器，比如 `"p:hover, .toto + q"`。|
| `element` | 表示当前元素。|

**返回值**: `elt` 是查询到的祖先元素，也可能是 `null`。

## 异常

如果传入的选择器不合法，则抛出 `SyntaxError` 异常。

## 示例

```html
<article>
  <div id="div-01">Here is div-01
    <div id="div-02">Here is div-02
      <div id="div-03">Here is div-03</div>
    </div>
  </div>
</article>
```

```javascript
var el = document.getElementById('div-03');

var r1 = el.closest("#div-02");  
// 返回 id 为 div-02 的那个元素

var r2 = el.closest("div div");  
// 返回最近的拥有 div 祖先元素的 div 祖先元素，这里的话就是 div-03 元素本身

var r3 = el.closest("article > div");  
// 返回最近的拥有父元素 article 的 div 祖先元素，这里的话就是 div-01

var r4 = el.closest(":not(div)");
// 返回最近的非 div 的祖先元素，这里的话就是最外层的 article
```

## 兼容

部分浏览器并不支持`Element.closest()`，但却支持了`element.matches()`（或拥有私有前缀，如IE9+），一个polyfill案例：

```javascript
if (!Element.prototype.matches)
    Element.prototype.matches = Element.prototype.msMatchesSelector ||
                                Element.prototype.webkitMatchesSelector;

if (!Element.prototype.closest)
    Element.prototype.closest = function(s) {
        var el = this;
        if (!document.documentElement.contains(el)) return null;
        do {
            if (el.matches(s)) return el;
            el = el.parentElement;
        } while (el !== null);
        return null;
    };
```

然而，如果你需要兼容到IE8，那么随后这个polyfill将会非常缓慢地运行到结束。并且，IE8只支持CSS2.1的选择器，并且使网页运行非常缓慢。

```javascript
if (window.Element && !Element.prototype.closest) {
    Element.prototype.closest =
    function(s) {
        var matches = (this.document || this.ownerDocument).querySelectorAll(s),
            i,
            el = this;
        do {
            i = matches.length;
            while (--i >= 0 && matches.item(i) !== el) {};
        } while ((i < 0) && (el = el.parentElement));
        return el;
    };
}
```
