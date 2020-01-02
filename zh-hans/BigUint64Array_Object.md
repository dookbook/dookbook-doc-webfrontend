TOPICS: BigUint64Array
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `BigUint64Array` Obejct

`BigUint64Array`类型数组表示一个平台字节顺序的64位有符号整型数组。
如果需要控制字符顺序，请使用[`DataView`](/zh-hans/webfrontend/DataView)替代。内容初始化为`0n`。
创建之后可以使用对象中的方法或使用标准数组索引语法(括号表示法)来获取数组中的元素。

## 语法

```JavaScript
new BigUint64Array();
new BigUint64Array(length);
new BigUint64Array(typedArray);
new BigUint64Array(object);
new BigUint64Array(buffer [, byteOffset [, length]]);
```

有关构造函数语法和参数的更多信息，请查看[`TypedArray`](/zh-hans/webfrontend/TypedArray)。

## 属性

| 属性| 说明 |
| :-- | :-- |
|**[`BigUint64Array.BYTES_PER_ELEMENT`](/zh-hans/webfrontend/TypedArray.BYTES_PER_ELEMENT)** | 返回元素大小的数值， 如果是`BigUint64Array`， 则数值为`8`。|
|**BigUint64Array.length**|固定的长度属性，值为`3`。有关实际长度（元素数量），请参见`BigUint64Array.prototype.length`.|
|**[`BigUint64Array.name`](/zh-hans/webfrontend/BigUint64Array.name)**|返回构造函数名称的字符串。 如果是`BigUint64Array`类型，则为`"BigUint64Array"`。|
|**`BigUint64Array.prototype`**|[`TypedArray`](/zh-hans/webfrontend/TypedArray)对象的原型。|

## 方法

| 方法| 说明 |
| :-- | :-- |
|**[`BigUint64Array.from()`](/zh-hans/webfrontend/TypedArray.from)**|从类似数组或可迭代的对象创建一个新的`BigUint64Array`。 参见 [`Array.from()`](/zh-hans/webfrontend/Array.from)。|
|**[`BigUint64Array.of()`](/zh-hans/webfrontend/TypedArray.of)**|创建一个新的`BigUint64Array`, 其具有可变数量的参数。参见 [`Array.of()`](/zh-hans/webfrontend/Array.of)。|

## BigUint64Array原型

所有的`BigUint64Array`对象均继承自`TypedArray.prototype`。

### 原型属性

| 属性| 说明 |
| :-- | :-- |
|**`BigUint64Array.prototype.constructor`**|返回创建实例原型的函数。 默认情况下，返回`BigUint64Array`构造函数。|
|**[`BigUint64Array.buffer`](/zh-hans/webfrontend/TypedArray.buffer)** (*只读*)|返回`BigUint64Array`引用的[`ArrayBuffer`](/zh-hans/webfrontend/ArrayBuffer)。这是在构建时固定的，因此是只读的。|
|**[`BigUint64Array.byteLength`](/zh-hans/webfrontend/TypedArray.byteLength)** (*只读*)|返回`BigUint64Array`从其[`ArrayBuffer`](/zh-hans/webfrontend/ArrayBuffer)开始的长度（以字节为单位）。 这是在构建时固定的，因此是只读的。|
|**[`BigUint64Array.byteOffset`](/zh-hans/webfrontend/TypedArray.byteOffset)** (*只读*)|返回`BigUint64Array`从其[`ArrayBuffer`](/zh-hans/webfrontend/ArrayBuffer)开始处的偏移量（以字节为单位）。这是在构建时固定的，因此是只读的。|
|**[`BigUint64Array.length`](/zh-hans/webfrontend/TypedArray.length)** (*只读*)|返回保存在`BigUint64Array`中的元素数量。这是在构建时固定的，因此是只读的。|

### 原型方法

| 方法 | 说明 |
| :-- | :-- |
|**[`BigUint64Array.copyWithin()`](/zh-hans/webfrontend/TypedArray.copyWithin)**|在数组内部，将一段元素序列拷贝到另一段元素序列上，覆盖原有的值。参见[`Array.copyWithin()`](/zh-hans/webfrontend/Array.copyWithin)。|
|**[`BigUint64Array.entries()`](/zh-hans/webfrontend/TypedArray.entries)**|返回一个数组迭代器对象，该迭代器会包含所有数组元素的键值对。参见 [`Array.entries()`](/zh-hans/webfrontend/Array.entries)。|
|**[`BigUint64Array.every()`](/zh-hans/webfrontend/TypedArray.every)**|测试数组中的所有元素是否通过测试函数。参见 [`Array.every()`](/zh-hans/webfrontend/Array.every)。|
|**[`BigUint64Array.fill()`](/zh-hans/webfrontend/TypedArray.fill)**| 将数组中指定区间的所有元素的值，都替换成某个固定的值。。参见 [`Array.fill()`](/zh-hans/webfrontend/Array.fill)。|
|**[`BigUint64Array.filter()`](/zh-hans/webfrontend/TypedArray.filter)**|将所有在过滤函数中返回 `true` 的数组元素放进一个新数组中并返回。参见 [`Array.filter()`](/zh-hans/webfrontend/Array.filter)。|
|**[`BigUint64Array.find()`](/zh-hans/webfrontend/TypedArray.find)**|找到第一个满足测试函数的元素并返回那个元素的值，如果找不到，则返回 `undefined`。 参见 [`Array.find()`](/zh-hans/webfrontend/Array.find)。|
|**[`BigUint64Array.findIndex()`](/zh-hans/webfrontend/TypedArray.findIndex)**|找到第一个满足测试函数的元素并返回那个元素的索引，如果找不到，则返回 `-1`。 参见 [`Array.findIndex()`](/zh-hans/webfrontend/Array.findIndex)。|
|**[`BigUint64Array.forEach()`](/zh-hans/webfrontend/TypedArray.forEach)**|为数组中的每个元素执行一次回调函数。 参见[`Array.forEach()`](/zh-hans/webfrontend/Array.forEach)。|
|**[`BigUint64Array.includes()`](/zh-hans/webfrontend/TypedArray.includes)**|判断当前数组是否包含某指定的值，如果是返回 `true`，否则返回 `false`。参见 [`Array.includes()`](/zh-hans/webfrontend/Array.includes)。|
|**[`BigUint64Array.indexOf()`](/zh-hans/webfrontend/TypedArray.indexOf)**|返回数组中第一个与指定值相等的元素的索引，如果找不到这样的元素，则返回 `-1`。参见 [`Array.indexOf()`](/zh-hans/webfrontend/Array.indexOf)。|
|**[`BigUint64Array.join()`](/zh-hans/webfrontend/TypedArray.join)**|连接所有数组元素组成一个字符串。 参见 [`Array.join()`](/zh-hans/webfrontend/Array.join)。|
|**[`BigUint64Array.keys()`](/zh-hans/webfrontend/TypedArray.keys)**|返回一个数组迭代器对象，该迭代器会包含所有数组元素的键。 参见 [`Array.keys()`](/zh-hans/webfrontend/Array.keys)。|
|**[`BigUint64Array.lastIndexOf()`](/zh-hans/webfrontend/TypedArray.lastIndexOf)**|返回数组中最后一个（从右边数第一个）与指定值相等的元素的索引，如果找不到这样的元素，则返回 `-1`。 参见 [`Array.lastIndexOf()`](/zh-hans/webfrontend/Array.lastIndexOf)。|
|**[`BigUint64Array.map()`](/zh-hans/webfrontend/TypedArray.map)**|返回一个由回调函数的返回值组成的新数组。 参见 [`Array.map()`](/zh-hans/webfrontend/Array.map)。|
|**[`BigUint64Array.reduce()`](/zh-hans/webfrontend/TypedArray.reduce)**|从左到右为每个数组元素执行一次回调函数，并把上次回调函数的返回值放在一个暂存器中传给下次回调函数，并返回最后一次回调函数的返回值。参见 [`Array.reduce()`](/zh-hans/webfrontend/Array.reduce)。|
|**[`BigUint64Array.reduceRight()`](/zh-hans/webfrontend/TypedArray.reduceRight)**|从右到左为每个数组元素执行一次回调函数，并把上次回调函数的返回值放在一个暂存器中传给下次回调函数，并返回最后一次回调函数的返回值。参见 [`Array.reduceRight()`](/zh-hans/webfrontend/Array.reduceRight)。|
|**[`BigUint64Array.reverse()`](/zh-hans/webfrontend/TypedArray.reverse)**|颠倒数组中元素的排列顺序，即原先的第一个变为最后一个，原先的最后一个变为第一个。 参见 [`Array.reverse()`](/zh-hans/webfrontend/Array.reverse)。|
|**[`BigUint64Array.set()`](/zh-hans/webfrontend/TypedArray.set)**|将多个值存储在类型化数组中，从指定数组中读取输入值。|
|**[`BigUint64Array.slice()`](/zh-hans/webfrontend/TypedArray.slice)**|抽取当前数组中的一段元素组合成一个新数组。 参见 [`Array.slice()`](/zh-hans/webfrontend/Array.slice)。|
|**[`BigUint64Array.some()`](/zh-hans/webfrontend/TypedArray.some)**|如果数组中至少有一个元素满足测试函数，则返回 `true`，否则返回 `false`。 参见 [`Array.some()`](/zh-hans/webfrontend/Array.some)。|
|**[`BigUint64Array.sort()`](/zh-hans/webfrontend/TypedArray.sort)**|对数组元素进行排序，并返回当前数组。 参见 [`Array.sort()`](/zh-hans/webfrontend/Array.sort)。|
|**[`BigUint64Array.subarray()`](/zh-hans/webfrontend/TypedArray.subarray)**|从给定的开始索引和结束索引返回一个新的`BigUint64Array`。|
|**[`BigUint64Array.values()`](/zh-hans/webfrontend/TypedArray.values)**|返回一个数组迭代器对象，该迭代器会包含所有数组元素的值。 参见 [`Array.values()`](/zh-hans/webfrontend/Array.values)。|
|**[`BigUint64Array.toLocaleString()`](/zh-hans/webfrontend/TypedArray.toLocaleString)**|返回一个由所有数组元素组合而成的本地化后的字符串。 参见 [`Array.toLocaleString()`](/zh-hans/webfrontend/Array.toLocaleString)。|
|**[`BigUint64Array.toString()`](/zh-hans/webfrontend/TypedArray.toString)**|返回一个由所有数组元素组合而成的字符串。 参见 [`Array.toString()`](/zh-hans/webfrontend/Array.toString)。|
|**[`BigUint64Array[@@iterator]()`](/zh-hans/webfrontend/TypedArray[@@iterator])**|返回一个数组迭代器对象，该迭代器会包含所有数组元素的值。|

## 示例

创建`BigUint64Array`的不同方法:

```JavaScript
// From a length
var biguint64 = new BigUint64Array(2);
biguint64[0] = 42n;
console.log(biguint64[0]); // 42n
console.log(biguint64.length); // 2
console.log(biguint64.BYTES_PER_ELEMENT); // 8

// From an array
var arr = new BigUint64Array([21n,31n]);
console.log(arr[1]); // 31n

// From another TypedArray
var x = new BigUint64Array([21n, 31n]);
var y = new BigUint64Array(x);
console.log(y[0]); // 21n

// From an ArrayBuffer
var buffer = new ArrayBuffer(32);
var z = new BigUint64Array(buffer, 0, 4);

// From an iterable
var iterable = function*(){ yield* [1n, 2n, 3n]; }();
var biguint64 = new BigUint64Array(iterable);
// BigUint64Array[1n, 2n, 3n]
```
