# 023：部署Django应用

## 概述
在本节课中，我们将学习如何将开发完成的Django应用部署到生产环境，使其能够被互联网上的用户访问。部署是项目开发的最后一步，也是至关重要的一步。

上一节我们介绍了Django应用的开发与调试，本节中我们来看看如何让应用上线运行。

---

## 核心概念：服务器与WSGI
为了让Django应用在互联网上运行，我们需要一个Web服务器和一个应用服务器接口。在Python世界中，这通常通过WSGI（Web Server Gateway Interface）协议来实现。

一个简单的WSGI应用示例如下：
```python
def application(environ, start_response):
    start_response('200 OK', [('Content-Type', 'text/html')])
    return [b'Hello, World!']
```
对于Django，我们使用其自带的`wsgi.py`文件作为WSGI入口点。

---

## 部署准备步骤
在开始部署前，需要完成一些准备工作。以下是部署前必须检查的清单：

1.  **设置DEBUG模式**：在生产环境中，必须将`DEBUG`设置为`False`。
    ```python
    # settings.py
    DEBUG = False
    ```

2.  **配置ALLOWED_HOSTS**：指定允许访问该应用的域名或IP地址列表。
    ```python
    # settings.py
    ALLOWED_HOSTS = [‘yourdomain.com‘, ‘www.yourdomain.com‘]
    ```

3.  **收集静态文件**：使用Django的`collectstatic`命令将各个应用中的静态文件集中到一个目录，便于Web服务器处理。
    ```bash
    python manage.py collectstatic
    ```

4.  **配置数据库**：确保生产环境数据库（如PostgreSQL、MySQL）已正确设置，并更新`settings.py`中的`DATABASES`配置。

---

## 选择部署方式
Django应用有多种部署方式，每种方式适用于不同的场景和需求。

以下是几种常见的部署方案：

*   **传统服务器部署**：在Linux服务器（如Ubuntu）上手动配置Nginx、Gunicorn/uWSGI和数据库。这种方式可控性强，适合学习和高定制化需求。
*   **平台即服务**：使用Heroku、PythonAnywhere、Google App Engine等PaaS平台。它们简化了服务器管理，适合快速部署和小型项目。
*   **容器化部署**：使用Docker将应用及其依赖打包成容器，然后在任何支持Docker的环境（如AWS、阿里云）中运行。这种方式保证了环境一致性，易于扩展。

---

## 示例：使用Gunicorn和Nginx部署
让我们以最常见的Linux服务器手动部署为例，了解其基本流程。

上一节我们列出了部署前的准备工作，本节中我们来看看具体的服务器软件配置。

1.  **安装Gunicorn**：Gunicorn是一个Python WSGI HTTP服务器，用于运行Django应用。
    ```bash
    pip install gunicorn
    ```

2.  **测试运行Gunicorn**：在项目根目录下，使用以下命令测试应用是否能通过Gunicorn运行。
    ```bash
    gunicorn your_project_name.wsgi:application
    ```

3.  **配置Nginx**：Nginx作为反向代理服务器，处理静态文件请求并将动态请求转发给Gunicorn。需要编辑Nginx的站点配置文件。
    ```nginx
    # /etc/nginx/sites-available/your_project
    server {
        listen 80;
        server_name yourdomain.com;

        location /static/ {
            alias /path/to/your/staticfiles/;
        }

        location / {
            proxy_pass http://127.0.0.1:8000;
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
        }
    }
    ```

4.  **使用进程管理器**：为了让Gunicorn在后台持续运行，可以使用systemd或Supervisor来管理进程。

---

## 总结
本节课中我们一起学习了Django应用部署的核心知识和基本流程。我们了解了WSGI接口的作用，掌握了部署前的关键配置步骤，并浏览了从传统服务器到PaaS平台的多种部署方式。最后，我们以Gunicorn结合Nginx的方案为例，演示了部署的核心操作步骤。成功部署后，你的Django应用就将正式在互联网上提供服务了。