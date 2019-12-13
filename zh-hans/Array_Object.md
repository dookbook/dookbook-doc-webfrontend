TOPICS: Array
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn
         

# JavaScript Array Object

JavaScript的 `Array` 对象是用于构造数组的全局对象，数组是类似于列表的高阶对象。

## 描述

数组是一种类列表对象，它的原型中提供了遍历和修改元素的相关操作。JavaScript 数组的长度和元素类型都是非固定的。因为数组的长度可随时改变，并且其数据在内存中也可以不连续，所以 JavaScript 数组不一定是密集型的，这取决于它的使用方式。一般来说，数组的这些特性会给使用带来方便，但如果这些特性不适用于你的特定使用场景的话，可以考虑使用类型数组 `TypedArray`。

只能用整数作为数组元素的索引，而不能用字符串。后者称为[关联数组](/zh-hans/webfrontend/Associative_array)。使用非整数并通过方括号或点号来访问或设置数组元素时，所操作的并不是数组列表中的元素，而是数组对象属性集合上的变量。数组对象的属性和数组元素列表是分开存储的，并且数组的遍历和修改操作也不能作用于这些命名属性。

## 常用操作

### 创建数组
```
var fruits = ['Apple', 'Banana'];

console.log(fruits.length);
//2

```
### 通过索引访问数组元素
```
var first = fruits[0];
// Apple

var last = fruits[fruits.length - 1];
// Banana
```
### 遍历数组
```
fruits.forEach(function (item, index, array) {
    console.log(item, index);
});
// Apple 0
// Banana 1
```
### 添加元素到数组的末尾
```
var newLength = fruits.push('Orange');
// newLength:3; fruits: ["Apple", "Banana", "Orange"] 
```
### 删除数组末尾的元素
```
var last = fruits.pop(); // remove Orange (from the end)
// last: "Orange"; fruits: ["Apple", "Banana"];
```
### 删除数组最前面（头部）的元素
```
var first = fruits.shift(); // remove Apple from the front
// first: "Apple"; fruits: ["Banana"];
```
### 添加元素到数组的头部
```
var newLength = fruits.unshift('Strawberry') // add to the front
// ["Strawberry", "Banana"];
```
### 找出某个元素在数组中的索引
```
fruits.push('Mango');
// ["Strawberry", "Banana", "Mango"]

var pos = fruits.indexOf('Banana');
// 1
```
### 通过索引删除某个元素
```
var removedItem = fruits.splice(pos, 1); // this is how to remove an item

// ["Strawberry", "Mango"]
```
### 从一个索引位置删除多个元素
```
var vegetables = ['Cabbage', 'Turnip', 'Radish', 'Carrot'];
console.log(vegetables); 
// ["Cabbage", "Turnip", "Radish", "Carrot"]

var pos = 1, n = 2;

var removedItems = vegetables.splice(pos, n);
// this is how to remove items, n defines the number of items to be removed,
// from that position(pos) onward to the end of array.

console.log(vegetables); 
// ["Cabbage", "Carrot"] (the original array is changed)

console.log(removedItems); 
// ["Turnip", "Radish"]
```
### 复制一个数组
```
var shallowCopy = fruits.slice(); // this is how to make a copy 
// ["Strawberry", "Mango"]
```

## 语法
```
[element0, element1, ..., elementN]
new Array(element0, element1[, ...[, elementN]])
new Array(arrayLength)
```

### 参数
**`elementN`**:  `Array`构造器会根据给定的元素创建一个 JavaScript 数组，但是当仅有一个参数且为数字时除外（详见下面的 `arrayLength` 参数）。注意，后面这种情况仅适用于用 `Array` 构造器创建数组，而不适用于用方括号创建的数组字面量。

**`arrayLength`**:  一个范围在 0 到 232-1 之间的整数，此时将返回一个 `length` 的值等于 `arrayLength` 的数组对象（言外之意就是该数组此时并没有包含任何实际的元素，不能理所当然地认为它包含 `arrayLength` 个值为 `undefined` 的元素）。如果传入的参数不是有效值，则会抛出 `RangeError` 异常。


### 访问数组元素
JavaScript 数组的索引是从0开始的，**第一个元素的索引为0，最后一个元素的索引等于该数组的长度减1**。如果指定的索引是一个无效值，JavaScript 数组并不会报错，而是会返回 `undefined`。
```
var arr = ['this is the first element', 'this is the second element', 'this is the last element'];
console.log(arr[0]);              // 打印 'this is the first element'
console.log(arr[1]);              // 打印 'this is the second element'
console.log(arr[arr.length - 1]); // 打印 'this is the last element'
```

虽然数组元素可以看做是数组对象的属性，就像 `toString` 一样，但是下面的写法是错误的，运行时会抛出 `SyntaxError` 异常，而原因则是使用了非法的属性名：
```
console.log(arr.0); // a syntax error
```

并不是 JavaScript 数组有什么特殊之处，而是因为在 JavaScript 中，**以数字开头的属性不能用点号引用，必须用方括号**。比如，如果一个对象有一个名为 3d 的属性，那么只能用方括号来引用它。下面是具体的例子：
```
var years = [1950, 1960, 1970, 1980, 1990, 2000, 2010];
console.log(years.0);   // 语法错误
console.log(years[0]);  // √
renderer.3d.setTexture(model, 'character.png');     // 语法错误
renderer['3d'].setTexture(model, 'character.png');  // √
```

注意在 3d 那个例子中，引号是必须的。你也可以将数组的索引用引号引起来，比如 `years[2]` 可以写成 `years['2']`。 `years[2]` 中的 `2` 会被 JavaScript 解释器通过调用 `toString` 隐式转换成字符串。正因为这样，'2' 和 '02' 在 years 中所引用的可能是不同位置上的元素。而下面这个例子也可能会打印 `true`：
```
console.log(years['2'] != years['02']);
```

类似地，如果对象的属性名称是保留字（最好不要这么做！），那么就只能通过字符串的形式用方括号来访问（从 firefox 40.0a2 开始也支持用点号访问了）：
```
var promise = {
  'var'  : 'text',
  'array': [1, 2, 3, 4]
};

console.log(promise['var']);
```

### length 和数字下标之间的关系
JavaScript 数组的 `length` 属性和其数字下标之间有着紧密的联系。数组内置的几个方法（例如 `join()`、`slice()`、`indexOf()` 等）都会考虑 `length` 的值。另外还有一些方法（例如 `push()`、`splice()` 等）还会改变 `length` 的值。
```
var fruits = [];
fruits.push('banana', 'apple', 'peach');

console.log(fruits.length); // 3
```
使用一个合法的下标为数组元素赋值，并且该下标超出了当前数组的大小的时候，解释器会同时修改 `length` 的值：
```
fruits[5] = 'mango';
console.log(fruits[5]); // 'mango'
console.log(Object.keys(fruits));  // ['0', '1', '2', '5']
console.log(fruits.length); // 6
```

也可以显式地给 `length` 赋一个更大的值：
```
fruits.length = 10;
console.log(Object.keys(fruits)); // ['0', '1', '2', '5']
console.log(fruits.length); // 10
```
而为 `length` 赋一个更小的值则会删掉一部分元素：
```
fruits.length = 2;
console.log(Object.keys(fruits)); // ['0', '1']
console.log(fruits.length); // 2
```
这一节的内容在 `Array.length` 中有更详细的介绍。

### 正则匹配结果所返回的数组
使用正则表达式匹配字符串可以得到一个数组。这个数组中包含本次匹配的相关信息和匹配结果。`RegExp.exec`、`String.match`、`String.replace` 都会返回这样的数组。看下面的例子和例子下面的表格：
```
// 匹配1个 d 后面紧跟着至少1个 b，再后面又跟着1个 d 的子串，
// 并且需要记住子串中匹配到的 b 和最后的 d （通过正则表达式中的分组），
// 同时在匹配时忽略大小写

myRe = /d(b+)(d)/i;
myArray = myRe.exec("cdbBdbsbz");
```
该正则匹配返回的数组包含以下属性和元素：

|属性/元素|说明|示例|
| :------------- | :--- | :--- |
|`input`|只读属性，原始字符串|`cdbBdbsbz`|
|`index`|只读属性，匹配到的子串在原始字符串中的索引|1|
|`[0]`|只读元素，本次匹配到的子串|dbBd|
|`[1], ...[n]`|只读元素，正则表达式中所指定的分组所匹配到的子串，其数量由正则中的分组数量决定，无最大上限|`	[1]: bB [2]: d`|

## 属性
**`Array.length`**:  `Array` 构造函数的 `length` 属性，其值为`1`（注意该属性为静态属性，不是数组实例的 `length` 属性）。

**`get Array[@@species]`**:  返回 `Array` 构造函数。


## 方法
**`Array.from()`**:  从类数组对象或者可迭代对象中创建一个新的数组实例。

**`Array.isArray()`**:  用来判断某个变量是否是一个数组对象。

**`Array.of()`**:  根据一组参数来创建新的数组实例，支持任意的参数数量和类型。

## 数组实例
所有数组实例都会从 `Array.prototype` 继承属性和方法。修改 `Array` 的原型会影响到所有的数组实例。如果将非标准的方法添加到数组对象可能会导致很多其他问题。

`Array.prototype`本身就是一个`Array`：
```
Array.isArray(Array.prototype); // true
```


### 属性
**`Array.prototype.constructor`**:  所有的数组实例都继承了这个属性，它的值就是 `Array`，表明了所有的数组都是由 `Array` 构造出来的。

**`Array.prototype.length`**:  上面说了，因为 `Array.prototype` 也是个数组，所以它也有 `length` 属性，这个值为 `0`，因为它是个空数组。

**`Array.prototype[@@unscopables]`**:  通过数组的原型对象可以为所有数组对象添加属性。

### 方法

**(一) 修改器方法**, 下面的这些方法会改变调用它们的对象自身的值：

**`Array.prototype.copyWithin()`**:   在数组内部，将一段元素序列拷贝到另一段元素序列上，覆盖原有的值。*(这是一个实验性的API,请尽量不要在生产环境中使用它)*

**`Array.prototype.fill()`**:   将数组中指定区间的所有元素的值，都替换成某个固定的值。*(这是一个实验性的API,请尽量不要在生产环境中使用它)*

**`Array.prototype.pop()`**:  删除数组的最后一个元素，并返回这个元素。

**`Array.prototype.push()`**:  在数组的末尾增加一个或多个元素，并返回数组的新长度。

**`Array.prototype.reverse()`**:  颠倒数组中元素的排列顺序，即原先的第一个变为最后一个，原先的最后一个变为第一个。

**`Array.prototype.shift()`**:  删除数组的第一个元素，并返回这个元素。

**`Array.prototype.sort()`**:  对数组元素进行排序，并返回当前数组。

**`Array.prototype.splice()`**:  在任意的位置给数组添加或删除任意个元素。

**`Array.prototype.unshift()`**:  在数组的开头增加一个或多个元素，并返回数组的新长度。

**(二) 访问方法**, 下面的这些方法绝对不会改变调用它们的对象的值，只会返回一个新的数组或者返回一个其它的期望值。

**`Array.prototype.concat()`**:  返回一个由当前数组和其它若干个数组或者若干个非数组值组合而成的新数组。

**`Array.prototype.includes() `**:  判断当前数组是否包含某指定的值，如果是返回 `true`，否则返回 `false`。*(这是一个实验性的API,请尽量不要在生产环境中使用它)*

**`Array.prototype.indexOf()`**:  返回数组中第一个与指定值相等的元素的索引，如果找不到这样的元素，则返回 `-1`。

**`Array.prototype.join()`**:  连接所有数组元素组成一个字符串。

**`Array.prototype.lastIndexOf()`**:  返回数组中最后一个（从右边数第一个）与指定值相等的元素的索引，如果找不到这样的元素，则返回 `-1`。

**`Array.prototype.slice()`**:  抽取当前数组中的一段元素组合成一个新数组。

**`Array.prototype.toSource() `**:  返回一个表示当前数组字面量的字符串。遮蔽了原型链上的 `Object.prototype.toSource() `方法。*(这个API尚未标准化)*

**`Array.prototype.toString()`**:  返回一个由所有数组元素组合而成的字符串。遮蔽了原型链上的 `Object.prototype.toString()` 方法。

**`Array.prototype.toLocaleString()`**:  返回一个由所有数组元素组合而成的本地化后的字符串。遮蔽了原型链上的 `Object.prototype.toLocaleString()` 方法。


**(三) 迭代方法**, 在下面的众多遍历方法中，有很多方法都需要指定一个回调函数作为参数。在每一个数组元素都分别执行完回调函数之前，数组的length属性会被缓存在某个地方，所以，如果你在回调函数中为当前数组添加了新的元素，那么那些新添加的元素是不会被遍历到的。此外，如果在回调函数中对当前数组进行了其它修改，比如改变某个元素的值或者删掉某个元素，那么随后的遍历操作可能会受到未预期的影响。总之，不要尝试在遍历过程中对原数组进行任何修改，虽然规范对这样的操作进行了详细的定义，但为了可读性和可维护性，请不要这样做。

**`Array.prototype.forEach()`**:  为数组中的每个元素执行一次回调函数。

**`Array.prototype.entries() `**:  返回一个数组迭代器对象，该迭代器会包含所有数组元素的键值对。

**`Array.prototype.every()`**:  如果数组中的每个元素都满足测试函数，则返回 `true`，否则返回 `false`。

**`Array.prototype.some()`**:  如果数组中至少有一个元素满足测试函数，则返回 `true`，否则返回 `false`。

**`Array.prototype.filter()`**:  将所有在过滤函数中返回 `true` 的数组元素放进一个新数组中并返回。

**`Array.prototype.find() `**:  找到第一个满足测试函数的元素并返回那个元素的值，如果找不到，则返回 `undefined`。

**`Array.prototype.findIndex() `**:  找到第一个满足测试函数的元素并返回那个元素的索引，如果找不到，则返回 `-1`。

**`Array.prototype.keys() `**:  返回一个数组迭代器对象，该迭代器会包含所有数组元素的键。

**`Array.prototype.map()`**:  返回一个由回调函数的返回值组成的新数组。

**`Array.prototype.reduce()`**:  从左到右为每个数组元素执行一次回调函数，并把上次回调函数的返回值放在一个暂存器中传给下次回调函数，并返回最后一次回调函数的返回值。

**`Array.prototype.reduceRight()`**:  从右到左为每个数组元素执行一次回调函数，并把上次回调函数的返回值放在一个暂存器中传给下次回调函数，并返回最后一次回调函数的返回值。

**`Array.prototype.values() `**:  返回一个数组迭代器对象，该迭代器会包含所有数组元素的值。

**`Array.prototype[@@iterator]() `**:  和上面的 `values()` 方法是同一个函数。


## 示例
### 创建数组

下面这个例子创建了一个长度为 `0` 的数组 `msgArray`，然后给 `msgArray[0]` 和 `msgArray[99]` 赋值，从而导致数组长度变为了 `100`。
```
var msgArray = [];
msgArray[0] = 'Hello';
msgArray[99] = 'world';

if (msgArray.length === 100) {
  console.log('The length is 100.');
}
```

### 创建二维数组
下面的例子创建了一个代表国际象棋棋盘的二维数组，然后将 `(6, 4)` 上的 `Pawn （卒）`拷贝到 `(4, 4)` 位置，而原本 `(6, 4)` 位置则被设置为空格。

```
var board = [ 
  ['R','N','B','Q','K','B','N','R'],
  ['P','P','P','P','P','P','P','P'],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  [' ',' ',' ',' ',' ',' ',' ',' '],
  ['p','p','p','p','p','p','p','p'],
  ['r','n','b','q','k','b','n','r'] ];

console.log(board.join('\n') + '\n\n');

// Move King's Pawn forward 2
board[4][4] = board[6][4];
board[6][4] = ' ';
console.log(board.join('\n'));
```
下面是输出：
```
R,N,B,Q,K,B,N,R
P,P,P,P,P,P,P,P
 , , , , , , , 
 , , , , , , , 
 , , , , , , , 
 , , , , , , , 
p,p,p,p,p,p,p,p
r,n,b,q,k,b,n,r

R,N,B,Q,K,B,N,R
P,P,P,P,P,P,P,P
 , , , , , , , 
 , , , , , , , 
 , , , ,p, , , 
 , , , , , , , 
p,p,p,p, ,p,p,p
r,n,b,q,k,b,n,r
```

### 用数组将一组值以表格形式显示
```
values = [];
for (var x = 0; x < 10; x++){
 values.push([
  2 ** x,
  2 * x ** 2
 ])
};
console.table(values)
```
结果为：
```
0	1	0
1	2	2
2	4	8
3	8	18
4	16	32
5	32	50
6	64	72
7	128	98
8	256	128
9	512	162
```
（第一列为索引）
