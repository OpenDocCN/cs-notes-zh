# 面向所有人的Web应用程序：30：JavaScript对象表示法详解 🎯

在本节课中，我们将要学习JavaScript对象表示法，即JSON。JSON是一种轻量级的数据交换格式，它基于JavaScript的语法，但独立于语言，被广泛用于不同编程语言之间的数据传输。

![](img/958f4f17c02e436586cc9638f354754b_1.png)

## 概述 📋

JSON是一种用于序列化和传输数据的格式。它源自JavaScript定义常量的语法，但因其简洁和易读性，现已成为跨语言数据交换的通用标准。本节将详细介绍JSON的语法、在JavaScript中的使用，以及如何在PHP中生成JSON并通过jQuery在JavaScript中接收和解析它。

## JSON语法基础

上一节我们介绍了JSON的概念，本节中我们来看看它的具体语法。JSON语法是JavaScript常量语法的一个简化子集。

JSON支持以下几种数据类型：
*   **字符串**：用双引号包裹的文本。
*   **数字**：整数或浮点数。
*   **布尔值**：`true` 或 `false`。
*   **数组**：用方括号 `[]` 表示的有序值列表。
*   **对象**：用花括号 `{}` 表示的无序键值对集合。
*   `null`：表示空值。

以下是JSON语法的核心结构：

**对象（Object）**
```json
{
  "key1": "value1",
  "key2": 123,
  "key3": true
}
```

![](img/958f4f17c02e436586cc9638f354754b_3.png)

**数组（Array）**
```json
["value1", "value2", "value3"]
```

![](img/958f4f17c02e436586cc9638f354754b_5.png)

JSON的强大之处在于可以任意嵌套这些结构。例如，一个对象的值可以是另一个对象或数组。

```json
{
  "name": "张三",
  "skills": {
    "programming": ["PHP", "JavaScript"],
    "language": "中文"
  }
}
```

![](img/958f4f17c02e436586cc9638f354754b_7.png)

## JavaScript中的对象与JSON

在深入使用JSON之前，理解JavaScript中对象的特性很重要。JavaScript中的对象本质上就是键值对的集合，这与许多其他语言中的“字典”或“关联数组”概念类似。

![](img/958f4f17c02e436586cc9638f354754b_9.png)

JavaScript提供了两种访问对象属性的语法，它们是等效的：
*   **点表示法**：`object.key`
*   **方括号表示法**：`object[“key”]`

例如：
```javascript
let balls = { soccer: “round”, baseball: “hard” };
console.log(balls.soccer); // 输出: round
console.log(balls[“baseball”]); // 输出: hard
```

![](img/958f4f17c02e436586cc9638f354754b_11.png)

![](img/958f4f17c02e436586cc9638f354754b_13.png)

![](img/958f4f17c02e436586cc9638f354754b_15.png)

JSON语法正是受到了JavaScript中定义对象常量（即直接量）写法的启发。在JavaScript中，一段符合JSON语法的字符串可以直接被解析为对象。

![](img/958f4f17c02e436586cc9638f354754b_17.png)

## 在PHP中生成JSON

既然JSON用于跨语言通信，我们来看看如何在服务器端的PHP中生成JSON数据。PHP内置了强大的JSON支持。

以下是使用PHP生成JSON的步骤：
1.  在PHP中创建一个数组（关联数组或索引数组）。
2.  使用 `json_encode()` 函数将PHP数组转换为JSON格式的字符串。
3.  输出（`echo`）这个字符串。

![](img/958f4f17c02e436586cc9638f354754b_19.png)

示例代码 (`json.php`)：
```php
<?php
// 创建一个PHP关联数组
$data = array(
    “first” => “first thing”,
    “second” => “second thing”
);
// 将数组编码为JSON字符串
$json_output = json_encode($data);
// 输出JSON字符串
echo $json_output;
?>
```
当访问这个PHP文件时，浏览器会收到一个纯文本响应：`{“first”:”first thing”,”second”:”second thing”}`。这就是标准的JSON数据。

## 使用jQuery获取并解析JSON

现在，我们有了一个能输出JSON的PHP接口。接下来，我们看看如何在客户端的JavaScript中，使用jQuery来获取这个JSON数据并自动将其解析为JavaScript对象。

以下是实现此功能的关键步骤：
1.  使用 `$.getJSON()` 方法向服务器（我们的 `json.php`）发起GET请求。
2.  该方法在收到响应后，会自动将返回的JSON字符串解析成JavaScript对象或数组。
3.  在回调函数中，我们可以直接使用点表示法或方括号表示法来访问解析后的数据。

![](img/958f4f17c02e436586cc9638f354754b_21.png)

示例代码 (`index.php` 中的JavaScript部分)：
```javascript
$(document).ready(function(){
    // 发起GET请求获取JSON数据
    $.getJSON(‘json.php’, function(data) {
        // 回调函数，`data` 是已解析的JavaScript对象
        console.log(data); // 在控制台查看整个对象
        // 访问对象中的属性
        $(‘#output’).html(data.first); // 将 “first thing” 显示在页面上
    });
});
```
这个过程非常高效。`$.getJSON()` 帮我们处理了网络请求和JSON解析的复杂细节，开发者只需关心数据到达后如何处理。

## 总结 🎉

![](img/958f4f17c02e436586cc9638f354754b_23.png)

本节课中我们一起学习了JSON的核心知识。我们了解到JSON是一种基于文本、独立于语言的数据交换格式。我们探讨了其基本语法，并认识到它在JavaScript中既是可执行代码，也是序列化格式。更重要的是，我们实践了如何在PHP端使用 `json_encode()` 生成JSON数据，以及如何在JavaScript端利用jQuery的 `$.getJSON()` 方法轻松获取并自动解析这些数据，从而实现前后端之间的无缝通信。这套流程极大简化了现代Web应用中的数据交换工作。