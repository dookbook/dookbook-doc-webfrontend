TOPICS: String.toString
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.toString()`

**`toString()`** 方法返回指定对象的字符串形式。

## 语法

```javascript
str.toString()
```

**参数**: 没有参数

**返回值**: 一个表示调用对象的字符串。

## 描述

[`String`](/zh-hans/webfrontend/String) 对象覆盖了 [`Object`](/zh-hans/webfrontend/Object) 对象的 `toString`
方法；并没有继承 [`Object.toString()`]。对于 [`String`](/zh-hans/webfrontend/String) 对象，`toString` 方法返回该对象的字符串形式，
和 [`String.valueOf()`](/zh-hans/webfrontend/String.valueOf) 方法返回值一样。

## 示例

### 使用 `toString()`

下例输出一个字符串对象（String object）的字符串值：

```javascript
var x = new String("Hello world");

alert(x.toString())      // 输出 "Hello world"
```
