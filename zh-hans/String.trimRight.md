TOPICS: String.trimRight
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.trimRight()`

**`trimEnd()`** 方法从一个字符串的末端移除空白字符。**`trimRight()`** 是这个方法的别名。

该交互式示例的源存储在GitHub存储库中。 如果您想为交互式示例项目做出贡献，请克隆[https://github.com/mdn/interactive-examples](https://github.com/mdn/interactive-examples)并向我们发送请求请求。

## 语法

```javascript
str.trimEnd();
str.trimRight();
```

**参数**: 没有参数

**返回值**: 一个新字符串，表示从调用字串的末（右）端除去空白。

## 描述

`trimEnd()` / `trimRight()`方法移除原字符串右端的连续空白符并返回，`trimEnd()` / `trimRight()`方法并不会直接修改原字符串本身。

### 别名

为了与 [`String.padEnd`] 等函数保持一致，标准方法名称为`trimEnd`。 但是，出于Web兼容性原因，`trimRight`仍然是`trimEnd`的别名。 在某些引擎中，这意味着：

```javascript
String.prototype.trimRight.name === "trimEnd";
```

## 示例

### 使用 `trimEnd()`

下面的例子输出了小写的字符串`"   foo"`:

```javascript
var str = "   foo  ";

alert(str.length); // 8

str = str.trimRight();  // 或写成str = str.trimEnd();
console.log(str.length); // 6
console.log(str);       // '   foo'
```
