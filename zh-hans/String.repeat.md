TOPICS: String.repeat
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.repeat()`

**`repeat()`** 构造并返回一个新字符串，该字符串包含被连接在一起的指定数量的字符串的副本。

## 语法

```javascript
/**
 * str: String
 * count: Number
 */

let resultString = str.repeat(count);
```

| 参数 | 说明 |
| :-- | :-- |
| `count` | 介于`0`和正无穷大之间的整数 : `[0, +∞)` 。表示在新构造的字符串中重复了多少遍原字符串。|

**返回值**: 包含指定字符串的指定数量副本的新字符串。

### 例外情况

- `RangeError`: 重复次数不能为负数。
- `RangeError`: 重复次数必须小于 `infinity`，且长度不会大于最长的字符串。

## 示例

```javascript
"abc".repeat(-1)     // RangeError: repeat count must be positive and less than inifinity
"abc".repeat(0)      // ""
"abc".repeat(1)      // "abc"
"abc".repeat(2)      // "abcabc"
"abc".repeat(3.5)    // "abcabcabc" 参数count将会被自动转换成整数.
"abc".repeat(1/0)    // RangeError: repeat count must be positive and less than inifinity

({toString : () => "abc", repeat : String.prototype.repeat}).repeat(2)
//"abcabc",repeat是一个通用方法,也就是它的调用者可以不是一个字符串对象.
```

## 填充

此方法已添加到ECMAScript 2015规范中，并且可能尚未在所有JavaScript实现中可用。然而，你可以使用以下代码段对 `String.prototype.repeat()` 进行填充：

```javascript
if (!String.prototype.repeat) {
  String.prototype.repeat = function(count) {
    'use strict';
    if (this == null) {
      throw new TypeError('can\'t convert ' + this + ' to object');
    }
    var str = '' + this;
    count = +count;
    if (count != count) {
      count = 0;
    }
    if (count < 0) {
      throw new RangeError('repeat count must be non-negative');
    }
    if (count == Infinity) {
      throw new RangeError('repeat count must be less than infinity');
    }
    count = Math.floor(count);
    if (str.length == 0 || count == 0) {
      return '';
    }
    // 确保 count 是一个 31 位的整数。这样我们就可以使用如下优化的算法。
    // 当前（2014年8月），绝大多数浏览器都不能支持 1 << 28 长的字符串，所以：
    if (str.length * count >= 1 << 28) {
      throw new RangeError('repeat count must not overflow maximum string size');
    }
    var rpt = '';
    for (;;) {
      if ((count & 1) == 1) {
        rpt += str;
      }
      count >>>= 1;
      if (count == 0) {
        break;
      }
      str += str;
    }
    return rpt;
  }
}
```
