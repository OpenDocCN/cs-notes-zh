Java全栈开发：24：三元运算符

![](img/c61cdd70decde1e633c990c0397f4dac_0.png)

在本节课中，我们将要学习Java中的三元运算符。三元运算符是`if-else`语句的一种简洁写法，它包含三个操作数，能够根据条件判断返回两个表达式中的一个结果。

![](img/c61cdd70decde1e633c990c0397f4dac_2.png)

上一节我们介绍了条件判断语句，本节中我们来看看如何使用三元运算符来简化代码。

三元运算符的基本语法如下：
```
条件 ? 表达式1 : 表达式2
```
其中，`条件`是一个布尔表达式。如果条件为`true`，则运算符返回`表达式1`的结果；如果条件为`false`，则返回`表达式2`的结果。

为了更好地理解其用法，我们来看一个具体的例子。

假设我们有一个布尔变量`isAuthenticated`，用于记录用户是否已通过身份验证。我们的目标是：如果用户已认证，则显示“登录成功”的消息；否则，显示“未登录”的消息。

以下是使用三元运算符实现此逻辑的代码示例：
```java
boolean isAuthenticated = true;
String result = isAuthenticated ? "You are logged in successfully." : "You are not logged in.";
System.out.println(result);
```
在这段代码中：
*   `isAuthenticated` 是条件。
*   如果 `isAuthenticated` 为 `true`，则 `result` 变量被赋值为 `"You are logged in successfully."`。
*   如果 `isAuthenticated` 为 `false`，则 `result` 变量被赋值为 `"You are not logged in."`。
*   最后，打印出 `result` 变量的值。

运行这段代码，由于`isAuthenticated`被设置为`true`，因此控制台将输出“You are logged in successfully.”。

![](img/c61cdd70decde1e633c990c0397f4dac_4.png)

![](img/c61cdd70decde1e633c990c0397f4dac_6.png)

本节课中我们一起学习了三元运算符。它是一种非常实用的语法糖，能够将简单的`if-else`判断浓缩为一行代码，使程序更加简洁易读。记住其语法 `条件 ? 表达式1 : 表达式2` 并在合适的场景应用即可。