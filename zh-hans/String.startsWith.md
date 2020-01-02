TOPICS: String.startsWith
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.startsWith()`

**`startsWith()`** 方法用来判断当前字符串是否以另外一个给定的子字符串开头，并根据判断结果返回 `true` 或 `false`。

## 语法

```javascript
str.startsWith(searchString[, position])
```

| 参数 | 说明 |
| :-- | :-- |
| `searchString` | 要搜索的子字符串。|
| `position` 可选 | 在 `str` 中搜索 `searchString` 的开始位置，默认值为 `0`，也就是真正的字符串开头处。|

**返回值**: 如果在字符串的开头找到了给定的字符则返回`true`;否则, 返回`false`.

## 描述

这个方法能够让你确定一个字符串是否以另一个字符串开头。

这个方法区分大小写。

## 示例

### 使用 `startsWith()`

```javascript
var str = "To be, or not to be, that is the question.";

alert(str.startsWith("To be"));         // true
alert(str.startsWith("not to be"));     // false
alert(str.startsWith("not to be", 10)); // true
```

## Polyfill

此方法已被添加至 ECMAScript 2015 规范之中，但可能不能在所有的现行 JavaScript 实现中使用。不过，你可以用以下的代码段为 `String.startsWith()` 制作 Polyfill：

```javascript
if (!String.prototype.startsWith) {
    Object.defineProperty(String.prototype, 'startsWith', {
        value: function(search, pos) {
            pos = !pos || pos < 0 ? 0 : +pos;
            return this.substring(pos, pos + search.length) === search;
        }
    });
}
```

Mathias Bynens 在 Github 上提供了一份更为稳定有效（完全符合 ES2015 规范），但性能略差、代码紧凑性微减的 PolyFill。
