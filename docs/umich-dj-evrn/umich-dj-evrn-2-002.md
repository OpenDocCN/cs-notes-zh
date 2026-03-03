# 002：市场平台初始设置与安装 🛠️

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_0.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_1.png)

在本节课中，我们将学习如何为“市场平台”作业进行初始设置与安装。我们将从GitHub获取一个预配置的Django项目，在PythonAnywhere上创建新项目，配置MySQL数据库，并完成应用的初始部署。

## 概述

我们将按照GitHub仓库中的说明，一步步完成市场平台应用的初始设置。这个过程包括克隆代码库、检查虚拟环境、安装依赖、配置数据库以及部署应用。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_3.png)

## 环境检查与准备

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_5.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_7.png)

首先，我们需要确保已经准备好正确的开发环境。这包括检查PythonAnywhere上的虚拟环境。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_9.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_10.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_11.png)

以下是检查虚拟环境的步骤：
1.  打开PythonAnywhere的“Consoles”标签页。
2.  启动一个新的Bash控制台。
3.  运行命令检查虚拟环境目录：`ls -la ~/.virtualenvs/`
4.  如果看到类似 `ve-django5-2` 的目录，说明虚拟环境已存在。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_13.png)

上一节我们确认了开发环境，本节中我们来看看如何获取项目代码。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_15.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_16.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_17.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_19.png)

## 获取项目代码

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_21.png)

我们将从GitHub克隆预配置的市场平台项目代码。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_23.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_25.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_27.png)

在Bash控制台中，执行以下命令：
1.  进入Django项目目录：`cd ~/django_projects`
2.  克隆GitHub仓库：`git clone https://github.com/csev/dj4e-market`
3.  克隆完成后，进入项目目录：`cd market`

现在，文件列表中应该会出现一个名为 `market` 的新目录，其中包含了项目的基础结构。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_29.png)

## 安装项目依赖

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_30.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_31.png)

项目代码包含一个 `requirements.txt` 文件，列出了所有必需的Python包。

在项目目录下，执行以下命令来安装依赖：
1.  激活虚拟环境（如果尚未激活）：`source ~/.virtualenvs/ve-django5-2/bin/activate`
2.  升级pip工具：`pip install --upgrade pip`
3.  安装项目依赖：`pip install -r requirements.txt`
4.  验证Django版本：`python -m django --version`

如果一切顺利，你将看到Django 5.2已安装成功。

## 配置数据库

市场平台应用将使用MySQL数据库，而不是默认的SQLite，以获得更好的性能。

以下是配置MySQL数据库的步骤：
1.  在PythonAnywhere控制面板，进入“Databases”标签页。
2.  初始化MySQL（如果尚未初始化）。
3.  创建一个新的数据库，命名为 `market`。
4.  返回项目，编辑配置文件 `market/config/settings.py`。
5.  找到 `DATABASES` 设置部分。
6.  注释掉默认的SQLite配置，并确保MySQL配置正确。配置示例如下：

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'market',
        'USER': '你的PythonAnywhere用户名',
        'PASSWORD': '你的数据库密码',
        'HOST': '你的用户名.mysql.pythonanywhere-services.com',
    }
}
```

7.  保存文件后，运行检查命令：`python manage.py check`，确保没有错误。

## 应用数据库迁移

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_33.png)

配置好数据库连接后，需要将Django的数据模型同步到新的MySQL数据库中。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_35.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_37.png)

在项目目录下，执行以下命令：
1.  生成迁移文件：`python manage.py makemigrations`
2.  应用迁移，创建数据库表：`python manage.py migrate`

你可以通过MySQL控制台执行 `SHOW TABLES;` 来验证所有表是否已成功创建。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_39.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_41.png)

## 创建管理员账户

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_43.png)

新的数据库需要创建一个超级用户来访问Django管理后台。

运行以下命令创建管理员：
`python manage.py createsuperuser`
按照提示输入用户名（例如 `admin`）、邮箱（可选）和密码。

## 配置Web应用

最后一步是在PythonAnywhere上配置Web应用，使其指向我们的新项目。

1.  进入“Web”标签页。
2.  找到你的Django Web应用配置。
3.  将“代码”和“工作目录”路径修改为指向 `~/django_projects/market`。
4.  在WSGI配置文件中，找到引用项目设置的部分，将其从 `mysite.settings` 修改为 `config.settings`。
5.  保存所有更改，并点击绿色的“重载”按钮使配置生效。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_45.png)

配置完成后，访问你的网站URL（例如 `yourusername.pythonanywhere.com`），应该能看到市场平台的主页。访问 `/admin` 并使用刚才创建的超级用户账号登录，可以进入管理后台。

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_47.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_48.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_50.png)

## 总结

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_52.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_53.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_55.png)

![](img/d3d2d5080524ffb4df2b6b165c3a69b5_56.png)

本节课中我们一起学习了市场平台Django应用的完整初始设置流程。我们完成了从GitHub克隆项目、安装依赖、配置MySQL数据库、执行数据迁移、创建管理员账户到最终部署上线的所有关键步骤。现在，你的应用已经搭建在一个更强大的MySQL数据库之上，并做好了进一步开发的功能基础。在接下来的课程中，我们将基于此基础构建市场平台的具体功能。