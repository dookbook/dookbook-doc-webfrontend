TOPICS: String.trimLeft
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.trimLeft()`

**`trimStart()`** 方法从字符串的开头删除空格。**`trimLeft()`** 是此方法的别名。

该交互式示例的源存储在GitHub存储库中。 如果您想为交互式示例项目做出贡献，请克隆[https://github.com/mdn/interactive-examples](https://github.com/mdn/interactive-examples)并向我们发送请求请求。

## 语法

```javascript
str.trimStart();
str.trimLeft();
```

**参数**: 没有参数

**返回值**: 一个新字符串，表示从其开头（左端）除去空格的调用字符串。

## 描述

`trimStart()` / `trimLeft()`方法移除原字符串左端的连续空白符并返回，`trimStart()` / `trimLeft()`方法并不会直接修改原字符串本身。

### 别名

为了与 [`String.padStart`](/zh-hans/webfrontend/String.padStart) 等函数保持一致，标准方法名称为`trimStart`。 但是，出于Web兼容性原因，`trimLeft`仍然是`trimStart`的别名。在某些引擎中，这意味着：

```javascript
String.prototype.trimLeft.name === "trimStart";
```

## 示例

### 使用 `trimStart()`

下面的例子输出了小写的字符串`"foo  "`：

```javascript
var str = "   foo  ";

console.log(str.length); // 8

str = str.trimStart() // 等同于str = str.trimLeft();
console.log(str.length); // 5
console.log(str);        // 'foo  '
```
