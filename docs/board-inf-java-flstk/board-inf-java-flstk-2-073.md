# 073：Spring Security Hello World 演示 🛡️

![](img/d3bcbf8768fe1b33834b6bd4b1c478d9_0.png)

在本节课中，我们将学习Spring Security的基础知识，并通过一个“Hello World”级别的演示来了解其基本工作原理。我们将看到如何创建一个简单的Spring Boot应用，其中包含公开页面和受保护页面，并体验Spring Security提供的默认登录和认证流程。

## 概述

Spring Security是一个功能强大且高度可定制的身份验证和访问控制框架。它主要用于保护基于Spring的应用程序。本节课的演示将展示Spring Security的默认行为：如何自动保护应用程序端点，以及如何通过内置的登录表单进行用户认证。

## 项目演示与目标

首先，我们来看一下本次演示项目的预期行为。当我们运行这个Spring Security应用程序时，它会根据访问的URL路径提供不同的安全级别。

以下是项目中的两个主要端点：

*   **公开页面** (`/public`): 此页面无需登录即可访问，仅请求一些基本信息。
*   **受保护页面** (`/secured`): 此页面受到Spring Security的保护，未经认证的用户将被重定向到登录页面。

运行应用后，如果访问公开页面，可以直接看到表单并提交数据。然而，如果尝试访问受保护页面，系统会要求我们进行登录。登录成功后，才能看到受保护页面的内容。

![](img/d3bcbf8768fe1b33834b6bd4b1c478d9_2.png)

## 实现步骤解析

上一节我们看到了项目的运行效果，本节中我们来看看为了实现这个效果，需要进行哪些关键配置和编码工作。由于在视频中逐行编写所有代码会非常冗长，因此这里将概述核心实现步骤，完整的代码可以参考视频描述或附件。

以下是实现此演示的主要步骤：

1.  **创建Spring Boot项目**：使用Spring Initializr创建一个新的Spring Boot项目，并添加`Spring Web`和`Spring Security`依赖。
2.  **配置安全规则**：在配置类中，通过重写`SecurityFilterChain` Bean来定义URL的访问规则。例如，将`/public`路径设置为允许所有访问（`permitAll`），而其他所有请求（如`/secured`）都需要认证。
3.  **创建控制器**：编写一个简单的控制器（`@Controller`），用于处理`/public`和`/secured`页面的请求，并返回对应的视图名称。
4.  **创建视图模板**：使用Thymeleaf等模板引擎创建`public.html`和`secured.html`页面，用于展示内容。
5.  **理解默认认证**：Spring Security提供了默认的用户名（`user`）和一个在控制台生成的随机密码。为了演示，我们可以在`application.properties`文件中配置一个固定的用户名和密码，例如：
    ```properties
    spring.security.user.name=KB
    spring.security.user.password=KB1234
    ```

通过以上步骤，我们就构建了一个具备基础安全功能的Spring Boot应用。当用户访问受保护资源时，Spring Security会自动拦截请求并展示其内置的登录表单。

## 核心概念与代码

在这个简单的演示中，最核心的概念是**安全过滤链**的配置。它决定了哪些请求路径需要被保护，哪些可以公开访问。

以下是一个简化的配置示例，展示了如何区分公开路径和受保护路径：

```java
@Configuration
@EnableWebSecurity
public class SecurityConfig {

    @Bean
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
        http
            .authorizeHttpRequests((authz) -> authz
                .requestMatchers("/public").permitAll() // 公开页面，允许所有访问
                .anyRequest().authenticated() // 其他所有请求都需要认证
            )
            .formLogin(withDefaults()); // 使用默认的登录表单
        return http.build();
    }
}
```

*   **`permitAll()`**: 表示匹配该路径的请求不需要任何安全约束。
*   **`authenticated()`**: 表示匹配该路径的请求需要用户已成功认证。
*   **`formLogin(withDefaults())`**: 启用Spring Security默认的基于表单的登录。

## 总结

![](img/d3bcbf8768fe1b33834b6bd4b1c478d9_4.png)

![](img/d3bcbf8768fe1b33834b6bd4b1c478d9_6.png)

本节课中，我们一起学习了Spring Security的入门知识。我们通过一个“Hello World”演示，直观地看到了Spring Security如何为Spring Boot应用提供开箱即用的安全保护。我们了解了如何通过简单的配置来定义公开和受保护的资源路径，并体验了其内置的认证流程。这个演示是理解更复杂安全配置（如自定义用户详情服务、角色权限控制等）的坚实基础。在接下来的课程中，我们将深入探讨如何定制这些安全特性。