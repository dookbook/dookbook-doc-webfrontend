TOPICS: String.toLowerCase
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.toLowerCase()`

**`toLowerCase()`** 会将调用该方法的字符串值转为小写形式，并返回。

## 语法

```javascript
str.toLowerCase()
```

**参数**: 没有参数

**返回值**: 一个新的字符串，表示串转换为小写的调用字符。

## 描述

`toLowerCase` 会将调用该方法的字符串值转为小写形式，并返回。`toLowerCase` 不会影响字符串本身的值。

## 示例

### 使用 `toLowerCase()`

```javascript
console.log('中文简体 zh-CN || zh-Hans'.toLowerCase());
// 中文简体 zh-cn || zh-hans

​console.log( "ALPHABET".toLowerCase() );
// "alphabet"
```
