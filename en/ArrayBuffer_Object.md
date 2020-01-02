TOPICS: ArrayBuffer
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `ArrayBuffer` Object

The `ArrayBuffer` object is used to represent a generic, fixed-length raw binary data buffer.

It is an array of bytes, often referred to in other languages as a "byte array".

You cannot directly manipulate the contents of an ArrayBuffer;
instead, you create one of the [typed array objects](/en/webfrontend/TypedArray
or a [`DataView`](/en/webfrontend/DataView) object which represents the buffer in a specific format,
and use that to read and write the contents of the buffer.

```JavaScript
// create an ArrayBuffer with a size in bytes
const buffer = new ArrayBuffer(8);

console.log(buffer.byteLength);
// expected output: 8
```

## Syntax

```JavaScript
new ArrayBuffer(length)
```

### Parameters

| Parameters | Description |
| :-- | :--|
|**`length`**| The size, in bytes, of the array buffer to create.|

### Return value

 A new `ArrayBuffer` object of the specified size. Its contents are initialized to `0`.

### Exceptions

A [`RangeError`](/en/webfrontend/RangeError) is thrown if the length is larger than
[`Number.MAX_SAFE_INTEGER (>= 2 ** 53)`](/en/webfrontend/Number.MAX_SAFE_INTEGER) or negative.

## Description

The `ArrayBuffer` constructor creates a new `ArrayBuffer` of the given length in bytes.

### Getting an array buffer from existing data

- [From a Base64 string](/en/webfrontend/Base64)
- [From a local file](/en/webfrontend/FileReader)

## Properties

| Properties | Description |
| :-- | :--|
|**`ArrayBuffer.length`**| The `ArrayBuffer` constructor's length property whose value is `1`.|
|**[`get ArrayBuffer[@@species`]](/en/webfrontend/get_ArrayBuffer[@@species])**| The constructor function that is used to create derived objects.|
|**`ArrayBuffer.prototype`**|Allows the addition of properties to all `ArrayBuffer` objects.|

## Methods

| Methods | Description |
| :-- | :--|
|**[`ArrayBuffer.isView(arg)`](/en/webfrontend/ArrayBuffer.isView)**| Returns `true` if arg is one of the `ArrayBuffer` views, such as typed array objects or a `DataView`. Returns `false` otherwise.|
|**[`ArrayBuffer.transfer(oldBuffer [, newByteLength])`](/en/webfrontend/ArrayBuffer.transfer)**|Returns a new `ArrayBuffer` whose contents are taken from the oldBuffer's data and then is either truncated or zero-extended by `newByteLength`.*(This is an experimental API that should not be used in production code)*|
|**[`ArrayBuffer.slice()`](/en/webfrontend/ArrayBuffer.slice)**| Has the same functionality as [`ArrayBuffer.slice()`](/en/webfrontend/ArrayBuffer.slice).*(This API has not been standardized)*|

## Instances

All `ArrayBuffer` instances inherit from `ArrayBuffer.prototype`.

### Instances Properties

| Properties | Description |
| :-- | :--|
|**`ArrayBuffer.constructor`**| Specifies the function that creates an object's prototype. The initial value is the standard built-in `ArrayBuffer` constructor.|
|**[`ArrayBuffer.byteLength`](/en/webfrontend/ArrayBuffer.byteLength)**|(Read only) The size, in bytes, of the array. This is established when the array is constructed and cannot be changed. Read only.|

### Instances Methods

| Methods | Description |
| :-- | :--|
|**[`ArrayBuffer.slice()`](/en/webfrontend/ArrayBuffer.slice)**|  Returns a new `ArrayBuffer` whose contents are a copy of this ArrayBuffer's bytes from `begin`, inclusive, up to `end`, exclusive. If either `begin` or `end` is negative, it refers to an index from the end of the array, as opposed to from the beginning.|

## Example

In this example, we create a 8-byte buffer with a
[`Int32Array`](/en/webfrontend/Int32Array) view referring to the buffer:

```Instances
var buffer = new ArrayBuffer(8);
var view   = new Int32Array(buffer);
```

## Compatibility notes

Starting with ECMAScript 2015,
`ArrayBuffer` constructors require to be constructed with a [new operator](/en/webfrontend/new_operator).
 Calling an `ArrayBuffer` constructor as a function without [new](/en/webfrontend/new_operator),
 will throw a [`TypeError`](/en/webfrontend/TypeError) from now on.

```Instances
var dv = ArrayBuffer(10);
// TypeError: calling a builtin ArrayBuffer constructor
// without new is forbidden
var dv = new ArrayBuffer(10);
```
