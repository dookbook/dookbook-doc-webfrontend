TOPICS: <meter>
        <meter> value attribute
        <meter> min attribute
        <meter> max attribute
        <meter> low attribute
        <meter> high attribute
        <meter> optimum attribute
        <meter> form attribute

# HTML 度量（尺度）元素 `<meter>`

**HTML 度量（尺度）元素** (**`<meter>`**)用来显示**已知范围的标量值或者分数值**。比如：磁盘使用情况，查询结果的相关性等。

!!! warn ""
    `<meter>` 不能作为一个进度条来使用,进度条[`<progress>`](/zh-hans/webfrontend/<progress>)标签。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*可标记内容*，*可触知内容*。 |
| **允许的内容** | *短语内容*，但其后代中不得包含 `<meter>` 元素。 |
| **标签遗漏** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 任何接受 *短语内容* 的元素。 |
| **允许的 ARIA 角色** | 没有 |
| **DOM 接口** | **`HTMLMeterElement`** |

## 属性

该元素包含所有的[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`value`** | **必需**，定义**当前的数值**。如果设置了最小值和最大值（分别由 *`min`* 属性和 *`max`* 属性定义），它必须介于 *`min`* 值和 *`max`* 值之间。如果没有设置或者格式有误，值即为 *`0`*。如果给定的值不在 *`min`* 值和 *`max`* 值之间，它的值就等于它最接近的一端的值。 |
| **`min`** | 定义了**范围的最小值**。默认为 *`0`*。 |
| **`max`** | 定义了**范围的最大值**。默认为 *`1`*。 |
| **`low`** | 定义了**低值区间的上限值**。如果设置了，它必须大于 *`min`* 值，同时不能大于 *`high`* 值和 *`max`* 值。未设置，或者小于 *`min`* 值，其值即为 *`min`* 值。 |
| **`high`** | 定义了**高值区间的下限值**。如果设置了，它必须小于 *`max`* 值，同时必须大于 *`low`* 值和 *`min`* 值。未设置，或者大于 *`max`* 值，其值即为 *`max`* 值。 |
| **`optimum`** | 定义了**最优或最佳值**。它必须在正确的范围内（由 *`min`* 属性和 *`max`* 属性值定义）。当使用了 *`low`* 和 *`high`* 属性时，它指明哪一个取值范围是更好的。假设它介于`min`值和`low`值之间，那么低值区间就被认为是更佳的取值范围。 |
| `form` | 指定**所属的一个或多个表单**。|

## 简单示例

```html
<p>Heat the oven to <meter min="200" max="500"
  value="350">350 degrees</meter>.</p>
```

## 指示范围的示例

请注意，此示例未指定 `min` 属性，这是允许的，它的默认值是 `0`。

```html
<p>He got a <meter low="69" high="80" max="100"
  value="84">B</meter> on the exam.</p>
```

## 关联表单的示例

```html
<form action="/demo_form" method="post" id="form_id">
 用户名: <input type="text" name="username"><br>
 <input type="submit" value="提交">
</form>

<meter form="form_id" name="x1" min="0" low="40" high="90" max="100" value="95"></meter>
```
