## JSON
**JSON（JavaScript Object Notation）** 是一种通过普通字符串描述数据的手段，用于表示有结构的数据。类似于编程语言中字面量的概念，语法上跟JavaScript的字面量非常相似（字面量 是代码中表述数据的手段），也是现如今用的最多的数据格式。

### JSON数据类型
    1、null---->null
    
    2、string---->"hello json"
    
    3、number---->2048
    
    4、boolean---->true
    
    5、object----->
    
      {
        "name": "zce",
        "age": 18,
        "gender": true,
        "girl_friend": null
       }
    
     6、array---->["zhangsan", "lisi", "wangwu"]
     
### 注意：
1. JSON 中属性名称必须用双引号包裹
2. JSON 中表述字符串必须使用双引号
3. JSON 中不能有单行或多行注释
4. JSON 没有  undefined 这个值

**ps:JSON中的两种方法   

1、JSON.parse(text[, reviver])----将JSON数据转换为 JavaScript 对象

*参数说明：

**text**:必需， 一个有效的 JSON 字符串。

**reviver**: 可选，一个转换结果的函数， 将为对象的每个成员调用此函数。

2、JSON.stringify(value[, replacer[, space]])-----将 JavaScript 对象转换为字符串

*参数说明：

**value**:必需， 要转换的 JavaScript 值（通常为对象或数组）。

**replacer**:可选。用于转换结果的函数或数组。

如果 replacer 为函数，则 JSON.stringify 将调用该函数，并传入每个成员的键和值。使用返回值而不是原始值。如果此函数返回 undefined，则排除成员。根对象的键是一个空字符串：""。

如果 replacer 是一个数组，则仅转换该数组中具有键值的成员。成员的转换顺序与键在数组中的顺序一样。当 value 参数也为数组时，将忽略 replacer 数组。

**space**:
可选，文本添加缩进、空格和换行符，如果 space 是一个数字，则返回值文本在每个级别缩进指定数目的空格，如果 space 大于 10，则文本缩进 10 个空格。space 也可以使用非数字，如：\t。
