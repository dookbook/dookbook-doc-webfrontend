TOPICS: Atomics
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# JavaScript `Atomics` Object

`Atomics` 对象提供了一组静态方法用来对 [`SharedArrayBuffer`](/zh-hans/webfrontend/SharedArrayBuffer) 对象进行原子操作。

这些原子操作属于 `Atomics` 模块。与一般的全局对象不同，`Atomics` 不是构造函数，因此不能使用 [`new`](/zh-hans/webfrontend/new_operator) 操作符调用，
也不能将其当作函数直接调用。Atomics 的所有属性和方法都是静态的（与 [`Math`](/zh-hans/webfrontend/Math) 对象一样）。

## 属性

| 属性 | 说明 |
| :-- | :-- |
|**`Atomics[Symbol.toStringTag]`**|该属性的值为“Atomics”。|

## 方法

### 原子操作

多个共享内存的线程能够同时读写同一位置上的数据。原子操作会确保正在读或写的数据的值是符合预期的，即下一个原子操作一定会在上一个原子操作结束后才会开始，其操作过程不会中断。

| 方法 | 说明 |
| :-- | :-- |
|**[`Atomics.add()`](/zh-hans/webfrontend/Atomics.add)**| 将指定位置上的数组元素与给定的值相加，并返回相加前该元素的值。|
|**[`Atomics.and()`](/zh-hans/webfrontend/Atomics.and)**| 将指定位置上的数组元素与给定的值相与，并返回与操作前该元素的值。|
|**[`Atomics.compareExchange()`](/zh-hans/webfrontend/Atomics.compareExchange)**| 如果数组中指定的元素与给定的值相等，则将其更新为新的值，并返回该元素原先的值。|
|**[`Atomics.exchange()`](/zh-hans/webfrontend/Atomics.exchange)**| 将数组中指定的元素更新为给定的值，并返回该元素更新前的值。|
|**[`Atomics.load()`](/zh-hans/webfrontend/Atomics.load)**| 返回数组中指定元素的值。|
|**[`Atomics.or()`](/zh-hans/webfrontend/Atomics.or)**| 将指定位置上的数组元素与给定的值相或，并返回或操作前该元素的值。|
|**[`Atomics.store()`](/zh-hans/webfrontend/Atomics.store)**|将数组中指定的元素设置为给定的值，并返回该值。|
|**[`Atomics.sub()`](/zh-hans/webfrontend/Atomics.sub)**| 将指定位置上的数组元素与给定的值相减，并返回相减前该元素的值。|
|**[`Atomics.xor()`](/zh-hans/webfrontend/Atomics.xor)**| 将指定位置上的数组元素与给定的值相异或，并返回异或操作前该元素的值。|

### 等待和唤醒

[`wait()`](/zh-hans/webfrontend/Atomics.wait) 和 [`notify()`](/zh-hans/webfrontend/Atomics.notify) 方法采用的是
 Linux 上的 futexes 模型（fast user-space mutex，快速用户空间互斥量），可以让进程一直等待直到某个特定的条件为真，主要用于实现阻塞。

| 方法 | 说明 |
| :-- | :-- |
|**[`Atomics.wait()`](/zh-hans/webfrontend/Atomics.wait)**| 检测数组中某个指定位置上的值是否仍然是给定值，是则保持挂起直到被唤醒或超时。返回值为 `"ok"`、`"not-equal"` 或 `"time-out"`。调用时，如果当前线程不允许阻塞，则会抛出异常（大多数浏览器都不允许在主线程中调用 [`wait()`](/zh-hans/webfrontend/Atomics.wait)）。|
|**[`Atomics.notify()`](/zh-hans/webfrontend/Atomics.notify)**| 唤醒等待队列中正在数组指定位置的元素上等待的线程。返回值为成功唤醒的线程数量。|
|**[`Atomics.isLockFree(size)`](/zh-hans/webfrontend/Atomics.isLockFree)**| 可以用来检测当前系统是否支持硬件级的原子操作。对于指定大小的数组，如果当前系统支持硬件级的原子操作，则返回 `true`；否则就意味着对于该数组，Atomics 对象中的各原子操作都只能用锁来实现。此函数面向的是技术专家。|

## 兼容性提示

直到 Firefox 48，最新的 API 名称和语意都还没有实现。FirFox 46 到 FireFox 48 之间主要有以下变化:

- 移除了方法 `Atomics.futexWakeOrRequeue()` 和 `Atomics.fence()` （bug(1259544)、bug(1225028)）。
- `Atomics.wait()` 和 `Atomics.wake()` 方法名称已改为 `Atomics.futexWait()` 和 `Atomics.futexWake()`
  （bug 1260910）。注意：之前的名称在 49 版本之后已被移除（bug 1262062）。在版本63中, `Atomics.wake()`被重命名为`Atomics.notify()`。
- 移除了属性 `Atomics.OK`、 `Atomics.TIMEDOUT`、 `Atomics.NOTEQUA`L。`Atomics.wait()` 方法现在返回字符串 `"ok"`、
  `"timed-out"` 和 `"not-equal"` （bug 1260835）。
- `Atomics.wake()` 方法的 count 参数的默认值从 `0` 变为 `+Infinity`（bug 1253350）。
