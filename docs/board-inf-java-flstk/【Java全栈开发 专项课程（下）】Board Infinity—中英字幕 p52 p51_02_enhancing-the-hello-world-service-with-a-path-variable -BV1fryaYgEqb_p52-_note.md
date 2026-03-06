# Java全栈开发：P52：使用路径变量增强Hello World服务 🚀

在本节课中，我们将学习如何创建一个控制器，并在其中添加REST API，同时学习如何传递路径变量。我们将从创建一个基本的Spring Boot应用开始，逐步构建带有不同端点的控制器。

## 概述

我们将创建一个Spring Boot应用，并定义一个`RestController`。在这个控制器中，我们将编写两个处理HTTP GET请求的方法。之后，我们将运行应用并通过浏览器测试这些API端点。

## 创建项目结构与控制器

首先，我们需要建立项目的基础结构。在`src/main/java`目录下，创建我们的基础包。

**代码示例：创建基础包**
```java
package com.pabna.guvani;
```

接下来，我们创建主应用类。为了清晰起见，我们将其命名为`Application.java`，它包含启动Spring Boot应用的`main`方法。

**代码示例：主应用类**
```java
@SpringBootApplication
public class Application {
    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}
```

现在，我们来创建控制器。你可以在基础包下创建，也可以新建一个子包。这里我们在`com.pabna.guvani`包下创建一个名为`controllers`的子包。

**操作步骤：**
1.  右键点击`src/main/java`目录。
2.  选择 `New` -> `Package`。
3.  输入包名：`com.pabna.guvani.controllers`。

在`controllers`包内，我们创建一个名为`HelloWorldController`的类。由于这是一个Spring Boot应用，并且我们要创建REST API，我们需要使用`@RestController`注解来标记这个类。

**代码示例：创建控制器类**
```java
package com.pabna.guvani.controllers;

import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloWorldController {
    // 后续将在这里添加方法
}
```

## 定义REST API端点

上一节我们创建了控制器类，本节中我们来看看如何在其中定义处理请求的方法。我们将创建两个处理HTTP GET请求的端点。

`@RestController`注解表明这个类的所有方法返回的数据都将直接写入HTTP响应体。为了映射HTTP GET请求到特定的处理方法，我们需要使用`@GetMapping`注解。

以下是我们要添加的两个方法：

**代码示例：定义GET请求处理方法**
```java
import org.springframework.web.bind.annotation.GetMapping;

@RestController
public class HelloWorldController {

    @GetMapping("/")
    public String message() {
        return "Welcome to Spring Boot application";
    }

    @GetMapping("/hello")
    public String helloWorld() {
        return "Hello World";
    }
}
```
*   **`message()`方法**：映射到根路径`/`。当访问应用首页时，会返回欢迎信息。
*   **`helloWorld()`方法**：映射到路径`/hello`。当访问此路径时，会返回“Hello World”。

## 运行与测试应用

![](img/065883a5d985a882b60d8e6582cd93ae_1.png)

我们已经定义了两个API端点，现在需要启动应用并进行测试。Spring Boot应用可以通过运行主类`Application`中的`main`方法来启动。

启动后，应用默认会在`8080`端口运行。请确保该端口未被占用。

![](img/065883a5d985a882b60d8e6582cd93ae_3.png)

启动成功后，我们可以通过浏览器来测试我们的API。

以下是测试步骤：

1.  打开浏览器。
2.  测试根路径：在地址栏输入 `http://localhost:8080/`。页面应显示“Welcome to Spring Boot application”。
3.  测试 `/hello` 路径：在地址栏输入 `http://localhost:8080/hello`。页面应显示“Hello World”。

通过以上步骤，我们验证了两个REST端点工作正常。

## 总结

本节课中我们一起学习了Spring Boot REST控制器的基础知识。我们创建了一个`@RestController`，并使用`@GetMapping`注解定义了两个处理HTTP GET请求的方法，分别响应根路径`/`和`/hello`的请求。最后，我们成功运行了应用并通过浏览器测试了这些API端点。

![](img/065883a5d985a882b60d8e6582cd93ae_5.png)

在接下来的课程中，我们将学习如何创建数据模型（Model/Bean），并将其注入到控制器中，以构建更符合实际场景的请求处理逻辑。