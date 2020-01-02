TOPICS: BigInt

# JavaScript `BigInt` Object

`BigInt`是一种内置对象，它提供了一种方法来表示大于`253 - 1`的整数。
这原本是[[JavaScript]]中可以用[`Number`](/zh-hans/webfrontend/Number)表示的最大数字。`BigInt`可以表示任意大的整数。

## 描述

可以用在一个整数字面量后面加`n`的方式定义一个`BigInt` ，如：`10n`，或者调用函数`BigInt()`。

```JavaScript
const theBiggestInt = 9007199254740991n;

const alsoHuge = BigInt(9007199254740991);
// ↪ 9007199254740991n

const hugeString = BigInt("9007199254740991");
// ↪ 9007199254740991n

const hugeHex = BigInt("0x1fffffffffffff");
// ↪ 9007199254740991n

const hugeBin = BigInt("0b11111111111111111111111111111111111111111111111111111");
// ↪ 9007199254740991n
```

它在某些方面类似于 [`Number`](/zh-hans/webfrontend/Number) ，但是也有几个关键的不同点：
不能用于 [`Math`](/zh-hans/webfrontend/Math) 对象中的方法；
不能和任何 [`Number`](/zh-hans/webfrontend/Number) 实例混合运算，两者必须转换成同一种类型。
在两种类型来回转换时要小心，因为 `BigInt` 变量在转换成 [`Number`](/zh-hans/webfrontend/Number) 变量时可能会丢失精度。

### 类型信息

使用`typeof`测试时，`BigInt`对象返回`"bigint"` ：

```JavaScript
typeof 1n === 'bigint'; // true
typeof BigInt('1') === 'bigint'; // true
```

使用`Object`包装后， `BigInt`被认为是一个普通的`"object"`：

``` JavaScript
typeof Object(1n) === 'object'; // true
```

### 运算

以下操作符可以和`BigInt`一起使用： `+`、`*`、`-`、`**`、`%` 。除`>>>`（无符号右移）之外的
 [位操作](/zh-hans/webfrontend/Bitwise_Operators) 也可以支持。因为`BigInt`都是有符号的，`>>>`（无符号右移）不能用于`BigInt`。
 为了兼容[asm.js](https://github.com/tc39/proposal-bigint/blob/master/ADVANCED.md#dont-break-asmjs) ，
 `BigInt`不支持单目(`+`) 运算符。

```JavaScript
const previousMaxSafe = BigInt(Number.MAX_SAFE_INTEGER);
// ↪ 9007199254740991

const maxPlusOne = previousMaxSafe + 1n;
// ↪ 9007199254740992n

const theFuture = previousMaxSafe + 2n;
// ↪ 9007199254740993n, this works now!

const multi = previousMaxSafe * 2n;
// ↪ 18014398509481982n

const subtr = multi – 10n;
// ↪ 18014398509481972n

const mod = multi % 10n;
// ↪ 2n

const bigN = 2n ** 54n;
// ↪ 18014398509481984n

bigN * -1n
// ↪ –18014398509481984n
```

`/` 操作符对于整数的运算也没问题。可是因为这些变量是 `BigInt` 而不是 `BigDecimal` ，该操作符结果会向零取整，也就是说不会返回小数部分。

!!! warn ""
    当使用`BigInt`时，带小数的运算会被取整。

```JavaScript
const expected = 4n / 2n;
// ↪ 2n

const rounded = 5n / 2n;
// ↪ 2n, not 2.5n
```

### 比较

`BigInt` 和 [`Number`](/zh-hans/webfrontend/Number) 不是严格相等的，但是宽松相等的。

```JavaScript
0n === 0
// ↪ false

0n == 0
// ↪ true
```

[`Number`](/zh-hans/webfrontend/Number) 和 `BigInt` 可以进行比较。

```JavaScript
1n < 2
// ↪ true

2n > 1
// ↪ true

2 > 2
// ↪ false

2n > 2
// ↪ false

2n >= 2
// ↪ true
```

两者也可以混在一个数组内并排序。

```JavaScript
const mixed = [4n, 6, -12n, 10, 4, 0, 0n];
// ↪  [4n, 6, -12n, 10, 4, 0, 0n]

mixed.sort();
// ↪ [-12n, 0, 0n, 10, 4n, 4, 6]
```

注意被`Object`包装的`BigInts`使用`object`的比较规则进行比较，只用同一个对象在比较时才会相等。

```JavaScript
0n === Object(0n); // false
Object(0n) === Object(0n); // false

const o = Object(0n);
o === o // true
```

### 条件

`BigInt` 在需要转换成 [`Boolean`](/zh-hans/webfrontend/Boolean) 的时表现跟 [`Number`](/zh-hans/webfrontend/Number)
 类似：如通过 [`Boolean`](/zh-hans/webfrontend/Boolean) 函数转换；
 用于 [`logical operators`](/zh-hans/webfrontend/Logical_Operator)  `||`, `&&`, 和 `!` 的操作数；
 或者用于在像 [`if statement`](/zh-hans/webfrontend/if_else_statement)  这样的条件语句中。

```JavaScript
if (0n) {
  console.log('Hello from the if!');
} else {
  console.log('Hello from the else!');
}

// ↪ "Hello from the else!"

0n || 12n
// ↪ 12n

0n && 12n
// ↪ 0n

Boolean(0n)
// ↪ false

Boolean(12n)
// ↪ true

!12n
// ↪ false

!0n
// ↪ true
```

## 构造器

| 方法 | 说明 |
| :-- | :-- |
|**`BigInt()`**| 创建`BigInt`对象。|

## 静态方法

| 方法 | 说明 |
| :-- | :-- |
| **`BigInt.asIntN()`** | 将`BigInt`值转换为一个\\(-2^{width-1}\\)与\\(2^{width-1}-1\\)之间的有符号整数。|
| **`BigInt.asUintN()`** | 将一个`BigInt`值转换为`0`与\\(2^{width}-1\\)之间的无符号整数。|

## 实例方法

| 方法 | 说明 |
| :-- | :-- |
|**`BigInt.toLocaleString()`**|返回此数字的 language-sensitive 形式的字符串。覆盖 [`Object.toLocaleString()`](/zh-hans/webfrontend/Object.toLocaleString) 方法。|
|**`BigInt.toString()`**|返回以指定基数(base)表示指定数字的字符串。覆盖 [`Object.toString()`](/zh-hans/webfrontend/Object.toString) 方法。|
|**`BigInt.valueOf()`**|返回指定对象的基元值。 覆盖 [`Object.valueOf()`](/zh-hans/webfrontend/Object.valueOf) 方法。|

## 使用建议

### 转化

由于在 [`Number`](/zh-hans/webfrontend/Number) 与 `BigInt` 之间进行转换会损失精度，
因而建议仅在值可能大于2^53^ 时使用 `BigInt` 类型，并且不在两种类型之间进行相互转换。

### 密码学

由于对`BigInt`的操作不是常数时间的，因而`BigInt`不适合用于密码学。

### 在 JSON 中使用

对任何`BigInt`值使用[`JSON.stringify()`](/zh-hans/glossary/JSON) 都会引发`TypeError`，
因为默认情况下`BigInt`值不会在[[JSON]]中序列化。但是，如果需要，可以实现`toJSON`方法：

```JavaScript
BigInt.prototype.toJSON = function() { return this.toString(); }
```

`JSON.stringify` 现在生成如下字符串，而不是抛出异常:

```JavaScript
JSON.stringify(BigInt(1));
// '"1"'
```

## 例子

### 计算素数

```JavaScript
// Returns true if passed BigInt is a prime number
function isPrime(p) {
  for (let i = 2n; i * i <= p; i++) {
    if (p % i === 0n) return false;
  }
  return true;
}

// Takes a BigInt as an argument, returns nth prime number as BigInt
function nthPrime(nth) {
  let maybePrime = 2n;
  let prime = 0n;
  
  while (nth >= 0n) {
    if (isPrime(maybePrime)) {
      nth--;
      prime = maybePrime;
    }
    maybePrime++;
  }
  
  return prime;
}

nthPrime(20n)
// ↪ 73n
```
