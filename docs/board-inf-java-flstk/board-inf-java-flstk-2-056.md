# 056：实现删除用户资源的DELETE方法 🗑️

![](img/0941ed8e7f92ccbf6630a78e4abb9834_0.png)

在本节课中，我们将学习如何为“学生”资源实现一个DELETE方法。我们将创建一个REST API端点，允许根据学生的“名字”从列表中删除对应的学生对象。

---

![](img/0941ed8e7f92ccbf6630a78e4abb9834_2.png)

## 概述

![](img/0941ed8e7f92ccbf6630a78e4abb9834_3.png)

上一节我们介绍了如何创建和获取学生资源。本节中，我们来看看如何实现删除操作。我们将创建一个使用`@DeleteMapping`注解的端点，它接收一个路径变量（学生名字），并从内存中的学生列表里移除匹配的对象。

## 实现DELETE方法

首先，我们需要在控制器类中创建一个新的方法。这个方法将使用`@DeleteMapping`注解，并指定一个路径，例如`/student/{firstName}`，其中`{firstName}`是一个路径变量。

以下是该方法的实现步骤：

1.  **定义方法签名**：方法返回类型为`void`，并接收一个`String`类型的参数，该参数使用`@PathVariable`注解绑定到URL中的`{firstName}`。
2.  **遍历学生列表**：我们需要遍历存储所有学生的列表。
3.  **匹配并删除**：在遍历过程中，检查每个学生对象的`firstName`属性是否与传入的路径变量匹配。如果匹配，则将该对象从列表中移除。

以下是具体的代码实现：

```java
@DeleteMapping(“/student/{firstName}”)
public void deleteStudent(@PathVariable String firstName) {
    for (Student student : students) {
        if (student.getFirstName().equals(firstName)) {
            students.remove(student);
            break; // 找到并删除后即可退出循环
        }
    }
}
```

**代码解释**：
*   `@DeleteMapping(“/student/{firstName}”)`：这定义了HTTP DELETE请求的端点URL模式。
*   `@PathVariable String firstName`：将URL路径中的`{firstName}`部分的值注入到方法参数`firstName`中。
*   循环`for (Student student : students)`：遍历名为`students`的列表（假设这是一个在类中已定义的`List<Student>`）。
*   `student.getFirstName().equals(firstName)`：检查当前遍历到的学生名字是否与要删除的名字一致。
*   `students.remove(student)`：从列表中移除这个学生对象。
*   `break`：找到并删除目标对象后，立即跳出循环，提高效率。

## 测试删除操作

理论实现后，我们需要进行测试来验证功能是否正常工作。

以下是测试步骤：

1.  重启Spring Boot应用程序。
2.  打开API测试工具（如Postman）。
3.  首先，使用一个GET请求查看当前所有学生，确认目标学生（例如“Kashfi”）存在。
4.  然后，构造一个DELETE请求。请求的URL应为：`http://localhost:8080/student/Kashfi`。
5.  发送请求后，应收到状态码为`200 OK`的响应，表示删除成功。
6.  最后，再次发送GET请求获取所有学生列表。此时，列表中应不再包含名为“Kashfi”的学生对象，从而确认删除操作已生效。

## 总结

本节课中我们一起学习了如何实现一个简单的DELETE API。我们创建了一个能够根据学生名字从内存列表中删除对应资源的方法，并通过测试验证了其功能。这是对资源进行“删”操作的基础。

![](img/0941ed8e7f92ccbf6630a78e4abb9834_5.png)

在下一个模块中，我们将探讨如何将这些操作（增、删、改、查）与真实的数据库集成，让数据持久化存储。