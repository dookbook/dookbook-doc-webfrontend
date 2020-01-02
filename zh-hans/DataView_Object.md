TOPICS: DataView
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `DataView` Object

`DataView` 视图是一个可以从 二进制 [`ArrayBuffer`](/zh-hans/webfrontend/ArrayBuffer) 对象中读写多种数值类型的底层接口，
使用它时，不用考虑不同平台的 [[字节序]] 问题。

```JavaScript
// create an ArrayBuffer with a size in bytes
const buffer = new ArrayBuffer(16);

// Create a couple of views
const view1 = new DataView(buffer);
const view2 = new DataView(buffer,12,4); //from byte 12 for the next 4 bytes
view1.setInt8(12, 42); // put 42 in slot 12

console.log(view2.getInt8(0));
// expected output: 42
```

## 语法

```JavaScript
new DataView(buffer [, byteOffset [, byteLength]])
```

### 参数

| 参数 | 说明 |
| :-- | :-- |
|**`buffer`**|一个 已经存在的 [`ArrayBuffer`](/zh-hans/webfrontend/ArrayBuffer) 或 [`SharedArrayBuffer`](/zh-hans/webfrontend/SharedArrayBuffer)  对象，`DataView` 对象的数据源。|
|**`byteOffset`** (*可选*)|此 `DataView` 对象的第一个字节在 `buffer` 中的字节偏移。如果未指定，则默认从第一个字节开始。|
|**`byteLength`** (*可选*)|此 `DataView` 对象的字节长度。如果未指定，这个视图的长度将匹配`buffer`的长度。|

### 返回值

一个表示指定数据缓存区的新`DataView` 对象。（这句话也许不是非常有助于说明清楚）

你可以把返回的对象想象成一个二进制字节缓存区 `array buffer` 的“解释器” —— 它知道如何在读取或写入时正确地转换字节码。这意味着它能在二进制层面处理整数与浮点转化、字节顺序等其他有关的细节问题。

### 异常

| 异常 | 说明 |
| :-- | :-- |
|**[`RangeError`](/zh-hans/webfrontend/RangeError)**| 如果 `byteOffset` 或者 `byteLength` 参数的值导致视图超出了 `buffer` 的结束位置就会抛出此异常。例如，假设 `buffer` （缓冲对象）是 `16` 字节长度，`byteOffset` 参数为 `8`，`byteLength` 参数为 `10`，这个错误就会抛出，这是因为结果视图试图超出 `buffer` 对象的总长度 `2` 个字节。|

## 描述

### Endianness（字节序）

需要多个字节来表示的数值，在存储时其字节在内存中的相对顺序依据平台架构的不同而不同，参照 [[Endianness]]。而使用 `DataView` 的访问函数时，不需要考虑平台架构中所使用的是哪种字节序。

```JavaScript
var littleEndian = (function() {
  var buffer = new ArrayBuffer(2);
  new DataView(buffer).setInt16(0, 256, true /* littleEndian */);
  // Int16Array uses the platform's endianness.
  return new Int16Array(buffer)[0] === 256;
})();
console.log(littleEndian); // true or false
```

### 64 位整数值

因为 JavaScript 目前不包含对 64 位整数值支持的标准，所以 `DataView` 不提供原生的 64 位操作。作为变通，您可以实现自己的 `getUint64()` 函数，以获得精度高达
[`Number.MAX_SAFE_INTEGER`](/zh-hans/webfrontend/Number.MAX_SAFE_INTEGER) 的值，可以满足某些特定情况的需求。

```JavaScript
function getUint64(dataview, byteOffset, littleEndian) {
  // split 64-bit number into two 32-bit (4-byte) parts
  const left =  dataview.getUint32(byteOffset, littleEndian);
  const right = dataview.getUint32(byteOffset+4, littleEndian);

  // combine the two 32-bit values
  const combined = littleEndian? left + 2**32*right : 2**32*left + right;

  if (!Number.isSafeInteger(combined))
    console.warn(combined, 'exceeds MAX_SAFE_INTEGER. Precision may be lost');

  return combined;
}
```

或者，如果需要填满 64 位，可以创建一个 [`BigInt`](/zh-hans/webfrontend/BigInt) 。
此外，尽管原生 `BigInt` 要比用户端的库中模拟的 `BigInt` 快得多，但在 JavaScript 中，BigInt 总是比 32 位整数慢得多，这是因为 `BigInt` 的大小是可变的。

```JavaScript
const BigInt = window.BigInt, bigThirtyTwo = BigInt(32), bigZero = BigInt(0);
function getUint64BigInt(dataview, byteOffset, littleEndian) {
  // split 64-bit number into two 32-bit (4-byte) parts
  const left = BigInt(dataview.getUint32(byteOffset|0, !!littleEndian)>>>0);
  const right = BigInt(dataview.getUint32((byteOffset|0) + 4|0, !!littleEndian)>>>0);

  // combine the two 32-bit values and return
  return littleEndian ? (right<<bigThirtyTwo)|left : (left<<bigThirtyTwo)|right;
}
```

## 属性

所有 `DataView` 实例都继承自 `DataView.prototype`，
并且允许向 `DataView` 对象中添加额外属性。

| 属性| 说明 |
| :-- | :-- |
|**DataView.prototype.constructor**|指定用来生成原型的构造函数.初始化值是标准内置`DataView`构造器。|
|**[`DataView.buffer`](/zh-hans/webfrontend/DataView.buffer)** *(只读)*|被视图引入的 [`ArrayBuffer`](zh-hansn/webfrontend/ArrayBuffer)，创建实例的时候已固化因此是只读的。|
|**[`DataView.byteLength`](/zh-hans/webfrontend/DataView.byteLength)** *(只读)*|从 [`ArrayBuffer`](zh-hansn/webfrontend/ArrayBuffer) 中读取的字节长度，创建实例的时候已固化因此是只读的。|
|**[`DataView.byteOffset`](/zh-hans/webfrontend/DataView.byteOffset)** *(只读)*|从 [`ArrayBuffer`](zh-hansn/webfrontend/ArrayBuffer) 读取时的偏移字节长度，创建实例的时候已固化因此是只读的。|

## 方法

### 读

| 方法 | 说明 |
| :-- | :-- |
|**[`DataView.getInt8()`](/zh-hans/webfrontend/DataView.getInt8)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处获取一个8-bit数(一个字节)。|
|**[`DataView.getUint8()`](/zh-hans/webfrontend/DataView.getUint8)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处获取一个8-bit数(无符号字节)。|
|**[`DataView.getInt16()`](/zh-hans/webfrontend/DataView.getInt16)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处获取一个16-bit数(短整型)。|
|**[`DataView.getUint16()`](/zh-hans/webfrontend/DataView.getUint16)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处获取一个16-bit数(无符号短整型)。|
|**[`DataView.getInt32()`](/zh-hans/webfrontend/DataView.getInt32)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处获取一个32-bit数(长整型)。|
|**[`DataView.getUint32()`](/zh-hans/webfrontend/DataView.getUint32)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处获取一个32-bit数(无符号长整型)。|
|**[`DataView.getFloat32()`](/zh-hans/webfrontend/DataView.getFloat32)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处获取一个32-bit数(浮点型)。|
|**[`DataView.getFloat64()`](/zh-hans/webfrontend/DataView.getFloat64)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处获取一个64-bit数(双精度浮点型)。|
|**[`DataView.getBigInt64()`](/zh-hans/webfrontend/DataView.getBigInt64)**|从`DateView`其实位置以byte为计数的指定偏移量(`byteOffset`)处获取一个64-bit数(长 长)|
|**[`DataView.getBigUint64()`](/zh-hans/webfrontend/DataView.getBigUint64)**|从`DateView`其实位置以byte为计数的指定偏移量(`byteOffset`)处获取一个无符号64-bit数（无符号 长 长）。|

### 写

| 方法 | 说明 |
| :-- | :-- |
|**[`DataView.setInt8()`](/zh-hans/webfrontend/DataView..setInt8)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处储存一个8-bit数(一个字节)。|
|**[`DataView.setUint8()`](/zh-hans/webfrontend/DataView.setUint8)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处储存一个8-bit数(无符号字节)。|
|**[`DataView.setInt16()`](/zh-hans/webfrontend/DataView.setInt16)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处储存一个16-bit数(短整型)。|
|**[`DataView.setUint16()`](/zh-hans/webfrontend/DataView.setUint16)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处储存一个16-bit数(无符号短整型)。|
|**[`DataView.setInt32()`](/zh-hans/webfrontend/DataView.setInt32)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处储存一个32-bit数(长整型)。|
|**[`DataView.setUint32()`](/zh-hans/webfrontend/DataView.setUint32)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处储存一个32-bit数(无符号长整型)。|
|**[`DataView.setFloat32()`](/zh-hans/webfrontend/DataView.setFloat32)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处储存一个32-bit数(浮点型)。|
|**[`DataView.setFloat64()`](/zh-hans/webfrontend/DataView.setFloat64)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处储存一个64-bit数(双精度浮点型)。|
|**[`DataView.setBigInt64()`](/zh-hans/webfrontend/DataView.setBigInt64)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处储存一个64-bit数(长 长)。|
|**[`DataView.setBigUint64()`](/zh-hans/webfrontend/DataView.setBigUint64)**|从`DataView`起始位置以byte为计数的指定偏移量(`byteOffset`)处储存一个无符号64-bit数(无符号 长 长)。|

## 示例

```JavaScript
var buffer = new ArrayBuffer(16);
var view = new DataView(buffer, 0);

view.setInt16(1, 42);
view.getInt16(1); // 42
```
