# Django for Everybody：07_02_04：在Shell中使用Django模型演练 🐚

在本节课中，我们将学习如何在Django Shell中操作数据模型。我们将从设置环境开始，逐步演示如何创建、读取、更新和删除模型数据，让你直观地理解Django ORM的基本操作。

---

![](img/62ffef858791cf1e23e84bf8f96827a5_1.png)

## 环境准备与项目设置

上一节我们介绍了Django模型的概念，本节中我们来看看如何在交互式Shell中实际操作它们。首先，我们需要准备好开发环境。

我使用PythonAnywhere的Bash控制台，这是一个Linux环境。我认为每个人都应该学习Linux。

![](img/62ffef858791cf1e23e84bf8f96827a5_3.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_4.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_1.png)

首先，我进入主目录，使用`cd ..`命令返回上一级文件夹，然后使用`ls -l`命令查看文件夹列表。这里有一个名为`dj4e-samples`的文件夹，其中包含示例代码，你可以克隆它来编辑和查看文件，作为自己项目的参考。

![](img/62ffef858791cf1e23e84bf8f96827a5_3.png)
![](img/62ffef858791cf1e23e84bf8f96827a5_4.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_6.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_8.png)

我们进入该文件夹：
```bash
cd dj4e-samples
```

然后使用`git pull`命令从GitHub获取最新的代码。这样，如果我修复了示例代码中的任何错误，你总能获得最新版本。

![](img/62ffef858791cf1e23e84bf8f96827a5_10.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_6.png)

我已经执行过这个命令了。接下来，我需要切换到我的虚拟环境。你可能会注意到我之前没有激活虚拟环境，现在激活了。这是因为下一个命令是`pip`命令，最好在虚拟环境中运行，以免影响系统全局的Python安装。

![](img/62ffef858791cf1e23e84bf8f96827a5_12.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_8.png)

我切换到名为`django3`的虚拟环境：
```bash
source django3/bin/activate
```

![](img/62ffef858791cf1e23e84bf8f96827a5_10.png)

现在运行`pip`命令来安装项目所需的所有依赖包：
```bash
pip install -r requirements.txt
```

这个命令会安装一系列工具代码。看起来有些包已经安装过了，但运行它可以确保所有Python依赖都已就位。

![](img/62ffef858791cf1e23e84bf8f96827a5_12.png)

安装完成后，我使用`clear`命令清屏。接下来，运行一个在PythonAnywhere中常用的命令：
```bash
python3 manage.py check
```

![](img/62ffef858791cf1e23e84bf8f96827a5_14.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_15.png)

这个命令会读取`urls.py`、应用程序配置等文件，检查是否存在问题。如果检查通过，就可以继续；否则需要先修复错误。我们不想在检查未通过的情况下继续执行`makemigrations`，因为它会开始创建更改。

---

## 创建数据库迁移与表

`makemigrations`命令是Django读取所有`models.py`文件并创建迁移文件的过程。迁移文件不是SQL，而是Python代码。由于项目是从GitHub克隆的，所有迁移文件已经存在。当然，你也可以删除它们并从头开始重新生成。

`makemigrations`会读取像`users/models.py`这样的文件，然后创建迁移。接下来，我们将删除现有的数据库（一个SQLite3文件）并重新创建。以下是具体步骤：

首先，运行迁移命令：
```bash
python3 manage.py makemigrations
```

![](img/62ffef858791cf1e23e84bf8f96827a5_17.png)

然后，删除旧的数据库文件（如果存在），并应用迁移来创建新的数据库和表：
```bash
rm db.sqlite3
python3 manage.py migrate
```

![](img/62ffef858791cf1e23e84bf8f96827a5_18.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_17.png)
![](img/62ffef858791cf1e23e84bf8f96827a5_18.png)

你会看到，对于这个Django项目中的每个应用程序，它都在创建一系列表。例如，`users`应用的初始迁移会创建我们将要操作的表。

![](img/62ffef858791cf1e23e84bf8f96827a5_20.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_21.png)

---

## 启动Django Shell并进行操作

完成上述设置后，是时候启动Django Shell了：
```bash
python manage.py shell
```

这个命令会启动Django，加载所有Django库并读取所有配置文件。此时可能会出现一些错误，如果出现，需要返回去修复。`manage.py check`命令已经做了一部分检查，但现在Shell会加载你的`views.py`等文件。

在Shell中，你可以输入Python命令，但这些命令是在Django环境中执行的，不仅仅是纯Python，而是预加载了所有Django应用程序的Python环境。所以启动需要一点时间。

![](img/62ffef858791cf1e23e84bf8f96827a5_23.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_23.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_25.png)

现在我们可以开始操作了。首先，导入用户模型：
```python
from users.models import User
```

然后，创建一个新的用户对象。以下两个命令非常重要：
```python
u = User(name='Kristen', email='kristen@umich.edu')
u.save()
```

第一行命令`User(name='Kristen', email='...')`会在Django的Python内存中创建一个新的用户模型对象，并将其赋值给变量`u`。此时，它**尚未**存储到数据库中。

我们可以验证这一点：
```python
print(u.id)  # 输出：None
```

因为如果它被保存到数据库并获得一行记录，就会得到一个序列号（ID）。`u.save()`命令的作用是：将内存中`u`变量包含的数据存储到数据库中。

保存后，我们再查看ID：
```python
print(u.id)  # 输出：1
```

![](img/62ffef858791cf1e23e84bf8f96827a5_27.png)

现在可以看到它被存储到数据库中，ID为1。这些数字很简单，从1开始递增。让我们再添加几个人：
```python
u = User(name='Sally', email='sally@umich.edu')
u.save()
u = User(name='Ted', email='ted@umich.edu')
u.save()
u = User(name='Bob', email='bob@umich.edu')
u.save()
u = User(name='Chuck', email='csev@umich.edu')
u.save()
```

![](img/62ffef858791cf1e23e84bf8f96827a5_29.png)

现在，最后一个创建的`u`是Sally，我们可以查看她的信息：
```python
print(u.name)  # 输出：Sally
print(u.id)    # 输出：5
```

她是第五个。至此，我已经有五个模型对象被持久化存储到数据库中了。

![](img/62ffef858791cf1e23e84bf8f96827a5_31.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_31.png)

---

## 查询、过滤与删除数据

现在，如果我们想检索这些用户对象，可以这样做：
```python
users = User.objects.values()
print(users)
```

`User`是模型名，实际上是一个类。`objects`是它的一个属性，它有一个`values()`方法。执行后会返回一个**QuerySet**，它功能上类似于一个列表。列表里是一系列对象，看起来就像我们输入的数据，但这是从数据库中提取出来的。现在数据里包含了每个行的主键ID。

![](img/62ffef858791cf1e23e84bf8f96827a5_33.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_34.png)

我们可以添加过滤器，这类似于SQL中的WHERE子句：
```python
users = User.objects.filter(email='csev@umich.edu').values()
print(users)
```

这个模式是：`User.objects.filter(...).values()`。`filter`是一个方法，它返回的对象也有`values`方法，所以可以链式调用。这基本上是说“只给我邮箱是csev@umich.edu的记录”。返回的QuerySet是一个列表，现在应该只有一条记录（如果没有邮箱唯一性约束，也可能有多条）。

我们也可以删除记录。首先获取特定记录，然后在其上运行`delete`方法：
```python
user_to_delete = User.objects.filter(email='ted@umich.edu')
user_to_delete.delete()
```

这会删除Ted的记录。然后我们再次检索所有对象，可以看到Ted已经不见了：
```python
all_users = User.objects.values()
print(all_users)
```

![](img/62ffef858791cf1e23e84bf8f96827a5_39.png)
![](img/62ffef858791cf1e23e84bf8f96827a5_40.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_36.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_37.png)

---

## 更新数据与排序

![](img/62ffef858791cf1e23e84bf8f96827a5_39.png)

我们还可以更新数据。让我们检查一下之前那条记录，并更改名字。这是对数据库进行CRUD操作中的“更新”（Update）。
```python
user_to_update = User.objects.filter(email='csev@umich.edu')
user_to_update.update(name='Charles')
```

![](img/62ffef858791cf1e23e84bf8f96827a5_40.png)

现在，如果我们查询这条记录：
```python
updated_user = User.objects.filter(email='csev@umich.edu').values()
print(updated_user)
```

会发现名字已经从“Chuck”变成了“Charles”。这不仅仅是内存中的更改，Django已经将这一切写入了数据库。

![](img/62ffef858791cf1e23e84bf8f96827a5_42.png)
![](img/62ffef858791cf1e23e84bf8f96827a5_43.png)
![](img/62ffef858791cf1e23e84bf8f96827a5_44.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_42.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_43.png)

最后，我们还可以对结果进行排序。你可以按邮箱升序排列：
```python
users_asc = User.objects.order_by('email').values()
print(users_asc)
```

![](img/62ffef858791cf1e23e84bf8f96827a5_44.png)

或者降序排列：
```python
users_desc = User.objects.order_by('-name').values()
print(users_desc)
```

![](img/62ffef858791cf1e23e84bf8f96827a5_46.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_48.png)

以上就是在Python Shell中可以执行的一些操作。要退出Shell，请输入：
```python
quit()
```

![](img/62ffef858791cf1e23e84bf8f96827a5_48.png)

![](img/62ffef858791cf1e23e84bf8f96827a5_50.png)

---

## 总结 🎯

![](img/62ffef858791cf1e23e84bf8f96827a5_50.png)

本节课中我们一起学习了如何在Django Shell中操作模型。我们从设置虚拟环境和项目依赖开始，然后创建了数据库迁移和表。接着，我们在Shell中导入了模型，并演示了**创建**（`User().save()`）、**读取**（`User.objects.values()`）、**更新**（`.update()`）和**删除**（`.delete()`）数据的基本CRUD操作，最后还展示了如何使用过滤器（`.filter()`）和排序（`.order_by()`）。这些是使用Django ORM进行数据交互的核心技能，希望本教程对你有所帮助。