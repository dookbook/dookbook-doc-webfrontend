TOPICS: Float64Array
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `Float64Array` Object

The `Float64Array` typed array represents an array of 64-bit floating point numbers
(corresponding to the C double data type) in the platform byte order.
If control over byte order is needed, use [`DataView`](/en/webfrontend/DataView) instead.
The contents are initialized to `0`. Once established,
you can reference elements in the array using the object's methods,
or using standard array index syntax (that is, using bracket notation).

## Syntax

```JavaScript
new Float64Array(); // new in ES2017
new Float64Array(length);
new Float64Array(typedArray);
new Float64Array(object);
new Float64Array(buffer [, byteOffset [, length]]);
```

For more information about the constructor syntax and the parameters, see [`TypedArray`](/en/webfrontend/TypedArray).

## Properties

| Properties | Description |
| :-- | :-- |
|**[`Float64Array.BYTES_PER_ELEMENT`](/en/webfrontend/TypedArray.BYTES_PER_ELEMENT)**|Returns a number value of the element size. `4` in the case of an `Float64Array`.|
|**`Float64Array.length`**|Static length property whose value is `3`. For the actual length (number of elements), see `Float64Array.prototype.length`.|
|**[`Float64Array.name`](/en/webfrontend/TypedArray.name)**|Returns the string value of the constructor name. In the case of the `Float64Array` type: `"Float64Array"`.|
|**`Float64Array.prototype`**|Prototype for the [`TypedArray`](/en/webfrontend/TypedArray) objects.|

## Methods

| Methods | Description |
| :-- | :-- |
|**[`Float64Array.from()`](/en/webfrontend/TypedArray.from)**|Creates a new `Float64Array` from an array-like or iterable object. See also [`Array.from()`](/en/webfrontend/Array.from).|
|**[`Float64Array.of()`](/en/webfrontend/TypedArray.of)**|Creates a new `Float64Array` with a variable number of arguments. See also [`Array.of()`](/en/webfrontend/Array.from).|

## Float64Array prototype

All `Float64Array` objects inherit from `TypedArray.prototype`.

### Prototype Properties

| Properties | Description |
| :-- | :-- |
|**`Float64Array.prototype.constructor`**|Returns the function that created an instance's prototype. This is the `Float64Array` constructor by default.|
|**[`Float64Array.buffer`](/en/webfrontend/TypedArray.buffer)** *(read only)*|Returns the [`ArrayBuffer`](/en/webfrontend/ArrayBuffer) referenced by the `Float64Array` Fixed at construction time and thus read only.|
|**[`Float64Array.byteLength`](/en/webfrontend/TypedArray.byteLength)** *(read only)*|Returns the length (in bytes) of the `Float64Array` from the start of its [`ArrayBuffer`](/en/webfrontend/ArrayBuffer). Fixed at construction time and thus read only.|
|**[`Float64Array.byteOffset`](/en/webfrontend/TypedArray.byteOffset)** *(read only)*|Returns the offset (in bytes) of the `Float64Array` from the start of its [`ArrayBuffer`](/en/webfrontend/ArrayBuffer). Fixed at construction time and thus read only.|
|**[`Float64Array.length`](/en/webfrontend/TypedArray.length)** *(read only)*|Returns the number of elements hold in the `Float64Array`. Fixed at construction time and thus read only.|

### Prototype Methods

| Methods | Description |
| :-- | :-- |
|**[`Float64Array.copyWithin()`](/en/webfrontend/TypedArray.copyWithin)**|Copies a sequence of array elements within the array. See also[`Array.copyWithin()`](/en/webfrontend/Array.copyWithin)。|
|**[`Float64Array.entries()`](/en/webfrontend/TypedArray.entries)**|Returns a new `Array Iterator` object that contains the key/value pairs for each index in the array. See also[`Array.entries()`](/en/webfrontend/Array.entries)。|
|**[`Float64Array.every()`](/en/webfrontend/TypedArray.every)**|Tests whether all elements in the array pass the test provided by a function. See also[`Array.every()`](/en/webfrontend/Array.every)。|
|**[`Float64Array.fill()`](/en/webfrontend/TypedArray.fill)**|Fills all the elements of an array from a start index to an end index with a static value. See also[`Array.fill()`](/en/webfrontend/Array.fill)。|
|**[`Float64Array.filter()`](/en/webfrontend/TypedArray.filter)**|Creates a new array with all of the elements of this array for which the provided filtering function returns true. See also[`Array.filter()`](/en/webfrontend/Array.filter)。|
|**[`Float64Array.find()`](/en/webfrontend/TypedArray.find)**|Returns the found value in the array, if an element in the array satisfies the provided testing function or `undefined` if not found. See also [`Array.find()`](/en/webfrontend/Array.find)。|
|**[`Float64Array.findIndex()`](/en/webfrontend/TypedArray.findIndex)**|Returns the found index in the array, if an element in the array satisfies the provided testing function or `-1` if not found. See also [`Array.findIndex()`](/en/webfrontend/Array.findIndex)。|
|**[`Float64Array.forEach()`](/en/webfrontend/TypedArray.forEach)**|Calls a function for each element in the array. See also [`Array.forEach()`](/en/webfrontend/Array.forEach)。|
|**[`Float64Array.includes()`](/en/webfrontend/TypedArray.includes)**|Determines whether a typed array includes a certain element, returning `true` or `false` as appropriate. See also[`Array.includes()`](/en/webfrontend/Array.includes)。|
|**[`Float64Array.indexOf()`](/en/webfrontend/TypedArray.indexOf)**|Returns the first (least) index of an element within the array equal to the specified value, or `-1` if none is found. See also[`Array.indexOf()`](/en/webfrontend/Array.indexOf)。|
|**[`Float64Array.join()`](/en/webfrontend/TypedArray.join)**|Joins all elements of an array into a string. See also [`Array.join()`](/en/webfrontend/Array.join)。|
|**[`Float64Array.keys()`](/en/webfrontend/TypedArray.keys)**|Returns a new Array Iterator that contains the keys for each index in the array. See also[`Array.keys()`](/en/webfrontend/Array.keys)。|
|**[`Float64Array.lastIndexOf()`](/en/webfrontend/TypedArray.lastIndexOf)**|Returns the last (greatest) index of an element within the array equal to the specified value, or `-1` if none is found. See also [`Array.lastIndexOf()`](/en/webfrontend/Array.lastIndexOf)。|
|**[`Float64Array.map()`](/en/webfrontend/TypedArray.map)**|Creates a new array with the results of calling a provided function on every element in this array. See also [`Array.map()`](/en/webfrontend/Array.map)。|
|**[`Float64Array.move()`](/en/webfrontend/TypedArray.move)**| Former non-standard version of [`Float64Array.copyWithin()`](/en/webfrontend/TypedArray.copyWithin). |
|**[`Float64Array.reduce()`](/en/webfrontend/TypedArray.reduce)**|Apply a function against an accumulator and each value of the array (from left-to-right) as to reduce it to a single value. See also [`Array.reduce()`](/en/webfrontend/Array.reduce)。|
|**[`Float64Array.reduceRight()`](/en/webfrontend/TypedArray.reduceRight)**|Apply a function against an accumulator and each value of the array (from right-to-left) as to reduce it to a single value. See also [`Array.reduceRight()`](/en/webfrontend/Array.reduceRight)。|
|**[`Float64Array.reverse()`](/en/webfrontend/TypedArray.reverse)**|Reverses the order of the elements of an array — the first becomes the last, and the last becomes the first. See also  [`Array.reverse()`](/en/webfrontend/Array.reverse)。|
|**[`Float64Array.set()`](/en/webfrontend/TypedArray.set)**|Stores multiple values in the typed array, reading input values from a specified array.|
|**[`Float64Array.slice()`](/en/webfrontend/TypedArray.slice)**|Extracts a section of an array and returns a new array. See also [`Array.slice()`](/en/webfrontend/Array.slice)。|
|**[`Float64Array.some()`](/en/webfrontend/TypedArray.some)**|Returns `true` if at least one element in this array satisfies the provided testing function. See also [`Array.some()`](/en/webfrontend/Array.some)。|
|**[`Float64Array.sort()`](/en/webfrontend/TypedArray.sort)**|Sorts the elements of an array in place and returns the array. See also [`Array.sort()`](/en/webfrontend/Array.sort)。|
|**[`Float64Array.subarray()`](/en/webfrontend/TypedArray.subarray)**|Returns a new `Float64Array` from the given start and end element index.|
|**[`Float64Array.values()`](/en/webfrontend/TypedArray.values)**|Returns a new Array Iterator object that contains the values for each index in the array. See also [`Array.values()`](/en/webfrontend/Array.values)。|
|**[`Float64Array.toLocaleString()`](/en/webfrontend/TypedArray.toLocaleString)**|Returns a localized string representing the array and its elements. See also [`Array.toLocaleString()`](/en/webfrontend/Array.toLocaleString)。|
|**[`Float64Array.toString()`](/en/webfrontend/TypedArray.toString)**|Returns a string representing the array and its elements. See also [`Array.toString()`](/en/webfrontend/Array.toString)。|
|**[`Float64Array[@@iterator]()`](/en/webfrontend/TypedArray[@@iterator])**|Returns a new Array Iterator object that contains the values for each index in the array.|

## Examples

Different ways to create a `Float64Array`:

```JavaScript
// From a length
var float64 = new Float64Array(2);
float64[0] = 42;
console.log(float64[0]); // 42
console.log(float64.length); // 2
console.log(float64.BYTES_PER_ELEMENT); // 8

// From an array
var arr = new Float64Array([21,31]);
console.log(arr[1]); // 31

// From another TypedArray
var x = new Float64Array([21, 31]);
var y = new Float64Array(x);
console.log(y[0]); // 21

// From an ArrayBuffer
var buffer = new ArrayBuffer(32);
var z = new Float64Array(buffer, 0, 4);

// From an iterable
var iterable = function*(){ yield* [1,2,3]; }();
var float64 = new Float64Array(iterable);
// Float64Array[1, 2, 3]
```
