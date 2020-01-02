TOPICS: String.toLocaleLowerCase
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `String.toLocaleLowerCase()`

**`toLocaleLowerCase()`** 方法根据任何指定区域语言环境设置的大小写映射，返回调用字符串被转换为小写的格式。

## 语法

```javascript
str.toLocaleLowerCase()
str.toLocaleLowerCase(locale)
str.toLocaleLowerCase([locale, locale, ...])
```

| 参数 | 说明 |
| :-- | :-- |
| `locale` 可选 | 参数 `locale` 指明要转换成小写格式的特定语言区域。 如果以一个数组 [`Array`](/zh-hans/webfrontend/Array) 形式给出多个`locales`, 最合适的地区将被选出来应用（参见[best available locale](https://tc39.github.io/ecma402/#sec-bestavailablelocale)）。默认的`locale`是主机环境的当前区域(`locale`)设置。|

**返回值**: 根据任何特定于语言环境的案例映射规则将被调用字串转换成小写格式的一个新字符串。

### 例外情况

- 如果`locale`参数不是有效的语言标签，则会抛出`RangeError`（“无效的语言标签：xx_yy”）。
- 如果数组元素不是字符串类型，则抛出`TypeError`（“语言环境参数中的无效元素”）。

## 描述

`toLocaleLowerCase()` 方法返回根据任意区域语言大小写映射集而转换成小写格式的字符串。`toLocaleLowerCase()` 并不会影响字符串原本的值。在大多数情况下，
该方法和调用 [`toLowerCase()`](/zh-hans/webfrontend/String.toLowerCase) 的结果相同，但是在某些区域环境中，比如土耳其语，它的大小写映射并不遵循在Unicode中的默认的大小写映射，因此会有一个不同的结果。

## 示例

### 使用 `toLocaleLowerCase()`

```javascript
'ALPHABET'.toLocaleLowerCase(); // 'alphabet'

'\u0130'.toLocaleLowerCase('tr') === 'i';    // true
'\u0130'.toLocaleLowerCase('en-US') === 'i'; // false

let locales = ['tr', 'TR', 'tr-TR', 'tr-u-co-search', 'tr-x-turkish'];
'\u0130'.toLocaleLowerCase(locales) === 'i'; // true
```
