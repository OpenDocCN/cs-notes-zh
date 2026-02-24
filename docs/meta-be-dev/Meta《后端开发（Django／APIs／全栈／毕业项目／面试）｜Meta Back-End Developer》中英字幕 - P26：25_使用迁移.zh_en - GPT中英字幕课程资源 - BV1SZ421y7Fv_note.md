# Django后端开发：P26：使用迁移 🚀

在本节课中，我们将学习如何在Django项目中使用迁移。迁移是Django管理数据库模式变更的核心工具，它允许开发者像管理代码版本一样管理数据库结构的变化。我们将重点掌握两个核心命令：`makemigrations` 和 `migrate`，并了解如何查看生成的SQL语句以及回滚迁移。

---

![](img/8ead6cbc352e6c1e72c4a1df778c8a29_1.png)

## 项目准备

首先，我已经在VS Code中创建了一个Django项目，其中包含一个名为`myapp`的应用。在`models.py`文件中，我定义了一个名为`MenuItem`的模型类。这个类在SQL中等同于一张数据表，它包含三个属性：`name`、`course`和`year`，每个属性都对应一个特定的字段类型。

在开始应用迁移之前，必须确保项目设置已正确配置。具体来说，需要将`myapp`添加到项目文件夹中`settings.py`文件内的`INSTALLED_APPS`列表中。检查确认后，准备工作就完成了。

---

## 生成与应用迁移

现在回到`models.py`文件。应用迁移的第一步是生成迁移文件，这通过运行以下命令完成：

```bash
python manage.py makemigrations
```

执行后，Django会显示一条消息，表明它正在为`myapp`创建迁移，并会生成一个名为`0001_initial.py`的迁移文件。这个文件记录了模型`MenuItem`的初始结构。

生成了迁移文件后，下一步是将其应用到数据库。运行以下命令：

![](img/8ead6cbc352e6c1e72c4a1df778c8a29_3.png)

```bash
python manage.py migrate
```

执行此命令后，Django会执行迁移文件中定义的所有SQL操作，从而在数据库中创建相应的表。

![](img/8ead6cbc352e6c1e72c4a1df778c8a29_5.png)

---

## 理解迁移命令

![](img/8ead6cbc352e6c1e72c4a1df778c8a29_7.png)

![](img/8ead6cbc352e6c1e72c4a1df778c8a29_8.png)

为了确保理解清晰，我们来区分这两个命令的作用。

`makemigrations` 命令是Django准备模型变更的方式。它分析模型的当前状态与上一次迁移状态的差异，并生成一个包含这些变更的Python脚本（即迁移文件）。你可以将其理解为**生成SQL命令**的阶段。

`migrate` 命令则是**执行这些SQL命令**的阶段。它读取迁移文件，并将其中的操作（如创建表、修改字段等）应用到实际的数据库中。

例如，执行`makemigrations`后，可能会在项目根目录生成一个SQLite数据库文件（如`db.sqlite3`），而`migrate`命令则负责在这个数据库文件中创建具体的表结构。

运行`migrate`命令后，会在应用目录下创建一个名为`migrations`的文件夹，里面保存了所有迁移记录文件。打开第一个迁移文件`0001_initial.py`，可以看到其中定义了表名、列名以及一个自动生成的主键字段`id`。

---

## 修改模型与生成新迁移

现在我们已经知道如何使用`makemigrations`和`migrate`来执行迁移。但如果我想修改模型呢？例如，假设我想将`MenuItem`模型中的`course`属性更名为`category`。

首先，在`models.py`文件中进行修改并保存。然后，必须再次运行`makemigrations`命令来为这次变更生成新的迁移文件。

```bash
python manage.py makemigrations
```

Django会检测到字段名的变化，并提示确认：“Was `menu_item.course` renamed to `menu_item.category`? (y/N)”。输入`y`并回车确认。

此时，`migrations`文件夹中会生成第二个迁移文件（例如`0002_rename_course_menu_item_category.py`）。打开这个文件，可以看到其中包含了重命名字段的操作代码。

让我们再做一次修改，将`name`属性改为`item_name`。保存文件后，再次运行`makemigrations`命令并确认变更。Django会清晰地描述所做的更改，并生成第三个迁移文件。

---

## 查看与回滚迁移

为了查看所有已执行和待执行的迁移，可以使用以下命令：

```bash
python manage.py showmigrations
```

在终端输出中，应用`myapp`下方会列出所有迁移文件。`[X]`标记表示该迁移已被应用（即已执行`migrate`）。由于我们尚未对最新的两次修改执行`migrate`，因此最后两个迁移文件前没有`[X]`标记。运行`python manage.py migrate`后，再次查看，所有迁移前都会显示`[X]`。

有时，我们可能需要回退到之前的某个迁移状态。这可以通过指定迁移文件名来实现。例如，要回退到`0001`版本，可以运行：

```bash
python manage.py migrate myapp 0001 --plan
```

`--plan`标志用于预览回退将执行的操作，而不会实际执行。预览信息会显示将把`item_name`改回`name`，`category`改回`course`。确认无误后，移除`--plan`标志再次执行命令即可完成回滚。请注意，回滚操作直接影响数据库，但不会自动修改你的`models.py`文件。

---

## 查看生成的SQL

最后一个有用的命令是`sqlmigrate`，它可以显示特定迁移文件将生成的原始SQL语句。这对于理解Django在底层做了什么非常有帮助。

```bash
python manage.py sqlmigrate myapp 0003
```

执行后，终端会输出对应的SQL语句。例如，对于第三个迁移（重命名`name`为`item_name`），你会看到类似`ALTER TABLE ... RENAME COLUMN ...`的SQL语句。

![](img/8ead6cbc352e6c1e72c4a1df778c8a29_10.png)

对于Django开发者而言，迁移是一个极其强大的工具，它使得对数据模型进行版本控制成为可能，让数据库结构的演进变得安全、可追踪。

---

## 总结 📝

![](img/8ead6cbc352e6c1e72c4a1df778c8a29_12.png)

本节课中，我们一起学习了Django迁移的核心操作。我们掌握了使用`makemigrations`命令生成迁移文件，以及使用`migrate`命令将变更应用到数据库。我们还学习了如何通过修改模型来生成新的迁移，如何使用`showmigrations`查看迁移状态，以及如何利用`migrate`命令回滚到特定版本。最后，我们使用`sqlmigrate`命令探查了Django生成的底层SQL语句，加深了对迁移机制的理解。迁移功能是Django ORM的重要组成部分，能有效管理数据库模式的迭代与变更。