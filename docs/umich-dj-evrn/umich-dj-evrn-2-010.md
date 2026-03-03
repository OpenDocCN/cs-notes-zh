# 010：部署Django应用

![](img/933c6d9730bf80687391d3d7f40dea69_0.png)

## 概述

在本节课中，我们将学习如何部署一个Django应用到生产环境。部署是将开发完成的应用程序发布到服务器，使其能够被互联网上的用户访问的过程。我们将涵盖从准备应用到配置服务器的关键步骤。

---

## 准备部署环境

上一节我们介绍了Django应用开发的基础。本节中我们来看看如何为部署做准备。部署前，需要确保你的应用代码是稳定且经过测试的。

以下是部署前需要完成的准备工作列表：

*   **冻结依赖项**：使用 `pip freeze > requirements.txt` 命令生成项目依赖列表。
*   **设置环境变量**：将敏感信息（如SECRET_KEY、数据库密码）从代码中移出，改为从环境变量读取。
*   **配置静态文件**：确保 `STATIC_ROOT` 和 `STATIC_URL` 设置正确，以便收集静态文件。
*   **选择数据库**：将开发用的SQLite数据库迁移到更适用于生产的数据库，如PostgreSQL或MySQL。
*   **关闭调试模式**：在部署环境中，务必将 `DEBUG` 设置为 `False`。

完成这些步骤后，你的应用就基本具备了部署的条件。

---

## 选择部署平台

准备好了应用，接下来我们需要选择一个地方来托管它。不同的平台有不同的优势和配置方式。

以下是几种常见的Django部署平台选项：

*   **PaaS（平台即服务）**：例如Heroku、PythonAnywhere。它们管理服务器基础设施，简化了部署流程。
*   **VPS（虚拟专用服务器）**：例如DigitalOcean、Linode、AWS EC2。提供完整的服务器控制权，需要自行配置所有软件。
*   **容器化部署**：使用Docker将应用及其环境打包成容器，然后部署到Kubernetes或AWS ECS等服务上。

对于初学者，从PaaS开始通常是最简单快捷的方式。

---

## 部署流程示例（以Heroku为例）

我们以Heroku这个流行的PaaS为例，来看一个简化的部署流程。这个过程涉及将代码推送到云端并配置运行环境。

以下是使用Heroku部署的核心步骤：

![](img/933c6d9730bf80687391d3d7f40dea69_2.png)

1.  **创建Heroku账户并安装CLI工具**。
2.  **在项目根目录创建 `Procfile` 文件**，定义启动命令：`web: gunicorn your_project_name.wsgi`。
3.  **使用Git初始化仓库**，并将代码提交。
4.  **通过CLI登录Heroku并创建应用**：`heroku create your-app-name`。
5.  **将代码推送到Heroku**：`git push heroku main`。
6.   运行数据库迁移：`heroku run python manage.py migrate`。
7.  收集静态文件：`heroku run python manage.py collectstatic`。
8.  **打开应用**：`heroku open`。

通过以上步骤，你的Django应用就应该成功上线了。

---

## 总结

![](img/933c6d9730bf80687391d3d7f40dea69_4.png)

本节课中我们一起学习了部署Django应用的核心知识。我们从部署前的准备工作开始，讨论了如何整理依赖和配置。接着，我们比较了不同的部署平台，并最终以Heroku为例，一步步完成了一个实际的部署流程。记住，部署是一个需要耐心和细致操作的过程，多实践几次就会变得更加熟练。