# 软件工程：004：Ruby基础与REST API入门 🚀

![](img/188385e4e33c07762ebb26c392632fa9_1.png)

![](img/188385e4e33c07762ebb26c392632fa9_3.png)

![](img/188385e4e33c07762ebb26c392632fa9_5.png)

![](img/188385e4e33c07762ebb26c392632fa9_7.png)

在本节课中，我们将要学习Ruby编程语言的一些核心概念，并初步了解RESTful API的设计原则。我们将从Ruby的独特语法和面向对象特性开始，然后过渡到如何设计和使用Web API。

![](img/188385e4e33c07762ebb26c392632fa9_9.png)

![](img/188385e4e33c07762ebb26c392632fa9_11.png)

![](img/188385e4e33c07762ebb26c392632fa9_13.png)

---

![](img/188385e4e33c07762ebb26c392632fa9_15.png)

![](img/188385e4e33c07762ebb26c392632fa9_16.png)

## Ruby语言基础 🛠️

![](img/188385e4e33c07762ebb26c392632fa9_18.png)

![](img/188385e4e33c07762ebb26c392632fa9_20.png)

上一节我们介绍了课程安排和课堂工具，本节中我们来看看Ruby语言的一些基本特性和设计哲学。

![](img/188385e4e33c07762ebb26c392632fa9_22.png)

![](img/188385e4e33c07762ebb26c392632fa9_24.png)

### 一切都是方法调用

在Ruby中，一个核心概念是：**一切皆是方法调用**。当你看到 `a.b` 这样的表达式时，`b` 是对象 `a` 的一个方法，而不是一个属性或字段。

```ruby
# 例如，数字相加
1 + 2
# 实际上等价于：
1.+(2)
```

这意味着Ruby的操作符（如 `+`, `-`, `[]`）实际上都是定义在对象上的方法，这赋予了语言极大的灵活性和一致性。

### 类与实例变量

Ruby是面向对象的语言。以下是定义一个简单类的方法：

![](img/188385e4e33c07762ebb26c392632fa9_26.png)

![](img/188385e4e33c07762ebb26c392632fa9_28.png)

```ruby
class SavingsAccount
  def initialize(starting_balance)
    @balance = starting_balance
  end

  def balance
    @balance
  end

  def balance=(new_amount)
    @balance = new_amount
  end
end
```

*   `initialize` 是构造方法。
*   `@balance` 是实例变量（以 `@` 开头）。
*   `balance` 和 `balance=` 分别是获取和设置 `@balance` 值的方法。Ruby允许 `balance = 100` 这样的语法来调用 `balance=` 方法。

为了简化这种常见的“获取器”和“设置器”模式，Ruby提供了 `attr_accessor` 方法。

```ruby
class SavingsAccount
  attr_accessor :balance

  def initialize(starting_balance)
    @balance = starting_balance
  end
end
```

`attr_accessor :balance` 这一行会自动为我们创建 `balance` 和 `balance=` 两个方法。

### 真值与假值

![](img/188385e4e33c07762ebb26c392632fa9_30.png)

![](img/188385e4e33c07762ebb26c392632fa9_31.png)

在条件判断中，Ruby的规则非常简单：

![](img/188385e4e33c07762ebb26c392632fa9_33.png)

*   只有 `nil` 和 `false` 被视为 **假**。
*   **其他所有值**，包括 `0` 和空字符串 `""`，都被视为 **真**。

![](img/188385e4e33c07762ebb26c392632fa9_35.png)

```ruby
if 0
  puts “0 is truthy!” # 这行会被执行
end

![](img/188385e4e33c07762ebb26c392632fa9_37.png)

![](img/188385e4e33c07762ebb26c392632fa9_39.png)

if nil
  puts “This will not print.”
end
```

![](img/188385e4e33c07762ebb26c392632fa9_41.png)

![](img/188385e4e33c07762ebb26c392632fa9_43.png)

### 方法的返回值

Ruby方法会**隐式返回**最后一条表达式的值。`return` 关键字是可选的。

```ruby
def greet
  “Hello” # 该方法返回字符串 “Hello”
end

def silent_method
  # 该方法没有最后一行表达式，返回 nil
end
```

---

## 互动问答与理解 🤔

![](img/188385e4e33c07762ebb26c392632fa9_45.png)

![](img/188385e4e33c07762ebb26c392632fa9_47.png)

以下是关于Ruby实例变量访问的一个思考题，帮助我们巩固理解。

![](img/188385e4e33c07762ebb26c392632fa9_49.png)

**问题**：给定以下类定义，哪些方式可以合法地访问 `@student_name` 实例变量的值？
```ruby
class Student
  attr_accessor :name
  def initialize(name)
    @student_name = name.capitalize
  end
end
```
**选项**:
A. `my_student.@student_name`
B. `my_student.name`
C. `my_student.name()`
D. `my_student.student_name`

**解析**：
*   **A** 非法。在Ruby中，不能直接通过 `对象.@变量名` 的语法访问实例变量。
*   **B 和 C** 合法。`attr_accessor :name` 创建了 `name` 方法，用于获取 `@name` 实例变量的值。括号 `()` 在Ruby中是可选的。
*   **D** 非法。代码中并未定义 `student_name` 这个方法。实例变量 `@student_name` 和通过 `attr_accessor` 创建的 `name` 方法访问的 `@name` 是**两个不同的变量**。

![](img/188385e4e33c07762ebb26c392632fa9_51.png)

![](img/188385e4e33c07762ebb26c392632fa9_52.png)

![](img/188385e4e33c07762ebb26c392632fa9_54.png)

![](img/188385e4e33c07762ebb26c392632fa9_56.png)

![](img/188385e4e33c07762ebb26c392632fa9_58.png)

这个例子强调了Ruby通过方法访问数据的“统一访问原则”，以及 `attr_accessor` 的工作方式。

---

## 从Ruby到Web API 🌐

![](img/188385e4e33c07762ebb26c392632fa9_60.png)

理解了Ruby的基本操作后，我们来看看如何用它来构建和与Web服务交互。现代Web开发的核心之一就是RESTful API。

![](img/188385e4e33c07762ebb26c392632fa9_62.png)

### 什么是REST？

REST（Representational State Transfer）是一种设计Web API的架构风格。它强调以下三点：
1.  **资源**：API操作的核心对象（如`/books`, `/users`）。
2.  **操作**：通过HTTP方法（GET, POST, PUT/PATCH, DELETE）定义要对资源执行的动作。
3.  **数据**：请求和响应中需要携带的额外信息（如参数、请求体）。

### CRUD操作与HTTP方法

大多数对资源的操作可以归结为经典的CRUD模式，它们与HTTP方法有典型的对应关系：

| 操作 | HTTP方法 | 典型用途 | Rails控制器方法 |
| :--- | :--- | :--- | :--- |
| **C**reate (创建) | POST | 创建新资源 | `create` |
| **R**ead (读取) | GET | 获取单个资源 | `show` |
| **U**pdate (更新) | PUT/PATCH | 更新现有资源 | `update` |
| **D**elete (删除) | DELETE | 删除资源 | `destroy` |
| **列表/索引** | GET | 获取资源集合 | `index` |

例如，一个图书管理API可能包含以下端点：
*   `GET /books` - 获取所有图书列表（索引）。
*   `GET /books/123` - 获取ID为123的图书详情（读取）。
*   `POST /books` - 创建一本新图书（创建）。
*   `PUT /books/123` - 更新ID为123的图书信息（更新）。
*   `DELETE /books/123` - 删除ID为123的图书（删除）。

### 理解API文档

阅读API文档时，需要关注：
*   **端点URL**：例如 `/books/{book_id}`。
*   **HTTP方法**：例如 `GET`。
*   **参数**：哪些是必需的（如 `book_id`），哪些是可选的（如 `format=json`）。
*   **响应格式**：通常是JSON，也可能是XML或HTML。

**关键点**：仅凭一个URL示例无法判断参数的必填性。必须查阅官方文档或实际测试。

---

## 总结 📚

本节课中我们一起学习了：
1.  **Ruby的核心特性**：包括“一切皆是方法调用”的原则、类的定义、实例变量与 `attr_accessor`、真值假值规则以及方法返回值。
2.  **RESTful API设计基础**：理解了资源、HTTP方法和CRUD操作之间的对应关系，这是构建和消费现代Web服务的基础。

![](img/188385e4e33c07762ebb26c392632fa9_64.png)

这些知识是后续学习Sinatra（一个简单的Ruby Web框架）和Rails（一个全功能的Ruby Web框架）的重要基石。请务必通过课后作业和实践来巩固理解。