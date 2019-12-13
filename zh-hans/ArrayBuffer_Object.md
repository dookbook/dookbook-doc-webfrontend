TOPICS: ArrayBuffer
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn


# JavaScript ArrayBuffer Object

`ArrayBuffer` 对象用来表示通用的、固定长度的原始二进制数据缓冲区。`ArrayBuffer` 不能直接操作，而是要通过类型数组对象或 `DataView` 对象来操作，它们会将缓冲区中的数据表示为特定的格式，并通过这些格式来读写缓冲区的内容。

```
// create an ArrayBuffer with a size in bytes
const buffer = new ArrayBuffer(8);

console.log(buffer.byteLength);
// expected output: 8
```

## 语法
```
new ArrayBuffer(length)
```

### 参数
**`length`**: 要创建的 `ArrayBuffer` 的大小，单位为字节。

### 返回值
一个指定大小的 `ArrayBuffer` 对象，其内容被初始化为 `0`。

### 异常
如果 `length` 大于 `Number.MAX_SAFE_INTEGER（>= 2 ** 53）`或为负数，则抛出一个  `RangeError`  异常。


## 描述
`ArrayBuffer` 构造函数用来创建一个指定字节长度的 `ArrayBuffer` 对象。

### 以现有数据获取 ArrayBuffer

- 从 Base64 字符串
- 从本地文件


## 属性

**`ArrayBuffer.length`**: `ArrayBuffer` 构造函数的 `length` 属性，其值为`1`。

**`get ArrayBuffer[@@species]`**: 返回 `ArrayBuffer` 的构造函数。

**`ArrayBuffer.prototype`**: 通过 `ArrayBuffer` 的原型对象可以为所有 `ArrayBuffer` 对象添加属性。


## 方法

**`ArrayBuffer.isView(arg)`**: 如果参数是 `ArrayBuffer` 的视图实例则返回 `true`，例如 类型数组对象 或 `DataView` 对象；否则返回 `false`。

**`ArrayBuffer.transfer(oldBuffer [, newByteLength])`**: 返回一个新的 `ArrayBuffer` 对象，其内容取自 `oldBuffer` 中的数据，并且根据 `newByteLength` 的大小对数据进行截取或补 `0`。*(这是一个实验性的API,请尽量不要在生产环境中使用它)*

**`ArrayBuffer.slice()`**:  和 `ArrayBuffer.prototype.slice()` 功能相同。*(这个API尚未标准化)*


## ArrayBuffer 实例
所有 `ArrayBuffer `实例都会从 `ArrayBuffer.prototype` 继承属性和方法。

### 属性

**`ArrayBuffer.prototype.constructor`**: 指定函数，它创建一个对象的原型。其初始值是标准`ArrayBuffer`内置构造函数。

**`ArrayBuffer.prototype.byteLength`**: (只读) 数组的字节大小。在数组创建时确定，并且不可变更。只读。

### 方法
**`ArrayBuffer.prototype.slice()`**: 返回一个新的 `ArrayBuffer` ，它的内容是这个 `ArrayBuffer` 的字节副本，从`begin`（包括），到`end`（不包括）。如果`begin`或`end`是负数，则指的是从数组末尾开始的索引，而不是从头开始。


## 示例
下面的例子创建了一个 8 字节的缓冲区，并使用一个 `Int32Array` 来引用它：
```
var buffer = new ArrayBuffer(8);
var view   = new Int32Array(buffer);
```

## 兼容性提醒
从 ECMAScript 2015 开始，`ArrayBuffer` 对象需要用 [new](/zh-hans/webfrontend/new_operator) 运算符创建。如果调用构造函数时没有使用 [new](/zh-hans/webfrontend/new_operator)，将会抛出 `TypeError`  异常。

```
var dv = ArrayBuffer(10);
// TypeError: calling a builtin ArrayBuffer constructor 
// without new is forbidden
var dv = new ArrayBuffer(10);
```