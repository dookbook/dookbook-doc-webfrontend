TOPICS: String.toUpperCase
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.toUpperCase()`

**`toUpperCase()`** 方法返回一个将调用字符串转换为大写形式的值。（如果这个值不是字符串则会被变成字符串）

该交互式示例的源存储在GitHub存储库中。 如果您想为交互式示例项目做出贡献，请克隆[https://github.com/mdn/interactive-examples](https://github.com/mdn/interactive-examples)并向我们发送请求请求。

## 语法

```javascript
str.toUpperCase()
```

**参数**: 没有参数

**返回值**: 一个表示调用字串转换成大写格式的新字符串。

### 异议

|  |  |
| :-- | :-- |
| `TypeError` | 当调用`null`或`undefined`时，例如, `String.toUpperCase.call(undefined)`. |

## 描述

`toUpperCase` 将调用该方法的字符串值转换为大写形式，并返回。`toUpperCase` 方法不影响字符串本身的值因为JavaScript的`strings`是`immutable`的（不可改变的）。

## 示例

### 使用 `toUpperCase()`

```javascript
​console.log( "alphabet".toUpperCase() ); // "ALPHABET"
```

### 将非字符串形式的 `this` 值转换成字符串

这个方法会将任何非字符串形式的值转换成字符串, 当你把这个值的 `this` 设置成一个不是字符串的值时:

```javascript
const a = String.prototype.toUpperCase.call({
  toString: function toString() {
    return 'abcdef';
  }
});

const b = String.prototype.toUpperCase.call(true);

// prints out 'ABCDEF TRUE'.
console.log(a, b);
```
