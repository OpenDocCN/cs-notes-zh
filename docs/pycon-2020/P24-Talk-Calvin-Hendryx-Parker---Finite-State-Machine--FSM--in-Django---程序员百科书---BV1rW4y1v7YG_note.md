# Django 有限状态机：P24：教程

![](img/6ba0083ebb8f3ca374d19a39c98b6f6c_0.png)

## 概述
在本教程中，我们将学习如何在 Django 项目中实现有限状态机。有限状态机是一种用于管理对象状态和状态间转换的强大模式，特别适用于建模业务流程和工作流。我们将从基本概念开始，逐步深入到如何在 Django 中应用它，包括定义状态、创建转换、设置权限以及生成可视化图表。

---

## 什么是工作流？
工作流是一系列为完成特定任务而进行的交互。它们在现实生活和软件应用中无处不在。例如，申请带薪休假时，你会提交请求，该请求随后被批准或拒绝，从而进入新的状态。

我们已经非常熟悉现实生活中的工作流，但需要学习如何在应用程序中建模这些相同类型的工作流。这就是有限状态机发挥作用的地方。

---

## 什么是有限状态机？
有限状态机是一种用于设计计算机程序行为的简单状态机模型。具体来说，它由有限数量的状态以及连接这些状态的转换组成。转换是关键，它定义了一系列从一个状态开始、到另一个（或同一个）状态结束的动作。

让我们从一个简单的例子开始。考虑一个最简单的发布模型，例如一个联系人管理系统的发布流程。它可能包含两个状态：`private`（私有）和`published`（已发布）。状态之间的转换由带箭头的线表示，例如“发布”或“撤回”。

在这个简单的例子中，我们没有显示谁被允许执行什么操作。在软件中，这一点变得非常重要，因为你希望设置条件守卫，只允许特定用户在特定时间执行特定操作。

---

## 何时使用工作流状态而非布尔值？
有时，开发者可能想使用布尔标志（如 `is_published`）来建模状态。在某些简单情况下这是有效的，但当应用程序复杂性增加时，仅有两个状态通常不足以建模现实中发生的事情。

例如，你的数据库中的行可能正在被某个外部程序处理。你可能有竞争条件。因此，你可能希望为这个第三方进程选择所有项目，将它们从“未处理”状态放入“处理中”状态，然后再放入“已处理”状态，以便追踪。

将这个概念扩展到协作场景，用户可能希望只与特定用户共享信息。我们希望能够拥有与权限相关的工作流状态。例如，你可能只希望对象的创建者可以编辑它，但当它进入“已发布”状态时，你可能希望匿名网站用户可以查看它，同时可能不希望所有者直接编辑已发布的内容，而是需要通过一个审查工作流将其“撤回”或提交复审。

---

## 现实世界中的复杂工作流示例
理论讨论已经足够，让我们看看现实世界的例子。许多人都曾是大学生，如果你曾经换过专业，你就会知道这个过程有多痛苦，它通常涉及大量纸质流程。

我们曾为当地一所社区大学做一个项目，旨在将更改专业的请求流程自动化并搬到线上。如果你仔细观察这个过程，它从“进行中”状态开始。学生提交更改专业的请求后，请求进入“待审查”状态。之后可能会有多个状态：例如，从“待审查”状态，它可以转到“信息不完整”状态，然后返回给学生补充信息；或者被标记为“完整”，由院长接受，然后通过剩余的工作流状态；它也可以直接进入“被拒绝”状态。

这个工作流可能很复杂，涉及许多不同的状态和转换。图中的所有圆圈代表工作流状态，所有箭头代表特定的转换。

---

## 工作流中的权限与自动化
我们不仅可以将工作流应用于更改大学课程等业务流程，还可以用于其他场景，例如在研究网站上提交病例报告以供发表，并让报告通过审查流程。

观察一个病例报告工作流的图表。对象的初始状态在左上角（例如“草稿”）。有趣的是，图表中有箭头返回到相同的状态。这可以用来追踪和记录数据库中项目何时被“保存”。“保存”操作或转换只是将其带回到原始工作流状态，主要用于追踪它被保存的时间和频率，或者当项目本身发生修改时，这可能会触发系统内部的其他行为。

大圆圈是我们的状态，箭头是我们的转换。颜色可以表示谁有权编辑项目。例如，在“草稿”状态，对象的所有者可以编辑和保存；在“处理中”状态，只有审核者可以编辑和重新提交对象。

关键点在于：**谁能在何时何地做什么**。此外，转换实际上可以导致返回到相同的工作流状态。另一件需要考虑的事情是，一些工作流转换可以是自动的，由触发器触发。通常，触发器是应用程序中的最终用户点击按钮，但也可能是外部进程。例如，在会员注册网站中，用户填写表单后，系统可以自动验证表单并触发状态转换。

---

## 为什么在 Django 中需要有限状态机框架？
Django 是一个固执己见的框架，但在角色和权限领域，它并不是非常固执己见。它提供了一些简单的角色（如“staff”和“admin”），但其余部分由开发者决定。权限逻辑通常非正式地分散在代码中——在模型、视图、管理命令、表单和中间件里进行检查。

如果没有一个框架，用于保护项目或确定谁可以做什么的代码会分散在各处，导致难以维护的“意大利面条式代码”。一个框架可以帮助我们，尤其是在处理“谁能在何时做什么”这种棘手问题时。

使用框架的额外好处是，我们可以轻松地开始记录“谁在何时做了什么”，从而建立审计线索。

---

## 介绍 Django FSM
我们首先采用“胖模型”的开发方式，Django 实际上鼓励创建拥有大量字段和方法的“胖模型”。`django-fsm` 是一个可重用的 Django 应用，它代表“有限状态机”。它很好，因为它有助于让团队中的每个人在思想上保持一致，了解如何控制应用程序中对象的状态。

`django-fsm` 的基础包括：
1.  一个自定义模型字段：`FSMField`。
2.  一个用于转换的 Python 装饰器：`@transition`。
3.  通过类贡献添加到模型类中的便捷方法。

当你创建一个字段并开始用 `@transition` 装饰模型上的方法（如 `edit`、`publish` 或 `submit`）时，类贡献机制会自动在你的模型中添加一些方法来收集信息，例如有哪些可用的转换、所有转换是什么、有哪些状态等。

---

### 添加 FSM 字段
向现有模型添加工作流状态非常简单。你只需在模型中添加一个字段。

```python
from django_fsm import FSMField, transition

class Article(models.Model):
    # ... 其他字段 ...
    state = FSMField(default='draft', protected=True)
```

`FSMField` 是一个基于文本的字段，用于存储各种工作流状态的字符串。还有一个 `FSMIntegerField`，如果你想存储枚举状态集。我们配置了哪些是可能和可用的工作流状态，以及什么是默认状态（即模型新实例创建时的初始状态）。

通常，我们会在 Django 应用中创建一个模块，在其中定义一个类来封装所有关于工作流状态的信息。

```python
class STATES:
    DRAFT = 'draft'
    REVIEW = 'review'
    PUBLISHED = 'published'
    # ... 其他状态 ...

    CHOICES = (
        (DRAFT, '草稿'),
        (REVIEW, '审核中'),
        (PUBLISHED, '已发布'),
        # ...
    )
```

然后在模型字段中使用它：
```python
state = FSMField(default=STATES.DRAFT, choices=STATES.CHOICES, protected=True)
```

---

### 创建状态转换
在这些工作流状态之间移动，需要通过转换来完成。直接更改数据库字段可能会导致意外的副作用。转换是我们模型上的方法，并用 `@transition` 装饰器标记。

```python
@transition(field=state, source=STATES.DRAFT, target=STATES.DRAFT)
def edit(self):
    """编辑文章，但保持在草稿状态。"""
    # 这里可以执行编辑相关的逻辑，例如更新修改时间
    self.save()
```

观察这个转换：
*   `field`：指定转换影响哪个字段（这里是 `state`）。
*   `source`：转换的源状态。
*   `target`：转换成功后的目标状态。
*   `permission`：一个可调用对象，用于检查谁可以执行此转换。
*   `conditions`：一个可调用对象列表，所有条件都必须满足才能执行转换。

确保所有状态更改都通过转换进行。如果你通过 Django 管理后台手动更改 `state` 字段的值，将会绕过转换中应该发生的任何副作用（例如调用外部系统或发送电子邮件）。

这是一个更复杂的转换示例，它会在转换过程中设置其他变量并触发操作：

```python
@transition(
    field=state,
    source=STATES.AUTHOR_REVIEW,
    target=STATES.ADMIN_REVIEW,
    permission=lambda instance, user: instance.author == user
)
def approve_by_author(self):
    """作者批准，进入管理员审核状态。"""
    self.author_approved = True
    self.admin_approved = False
    # 触发发送邮件等操作
    send_approval_email(self)
```

---

### 设置权限和条件
权限和条件用于控制谁可以在何时执行转换。

```python
def can_submit(instance, user):
    """检查当前用户是否是文章的作者。"""
    return instance.author == user

@transition(
    field=state,
    source=STATES.DRAFT,
    target=STATES.REVIEW,
    permission=can_submit
)
def submit_for_review(self):
    """提交审核。"""
    pass
```

条件可以是更复杂的逻辑：

```python
def can_edit(instance, user):
    """检查用户是否有权编辑。"""
    # 如果是草稿状态，且用户是作者
    if instance.state == STATES.DRAFT and instance.author == user:
        return True
    # 如果是管理员审核状态，且用户是工作人员
    elif instance.state == STATES.ADMIN_REVIEW and user.is_staff:
        return True
    else:
        return False

@transition(
    field=state,
    source=[STATES.DRAFT, STATES.ADMIN_REVIEW],
    target=STATES.DRAFT,
    conditions=[can_edit]
)
def edit(self):
    """编辑文章。"""
    pass
```

这些权限和条件不仅用于后端验证，还可以在前端用于动态确定应向用户显示哪些操作按钮。

---

### 便捷方法与信号
`django-fsm` 通过类贡献向你的模型添加了一些便捷方法：

*   `get_all_state_transitions()`: 获取模型中声明的所有转换。
*   `get_available_user_state_transitions(user)`: 获取当前用户可用的转换。

这些方法可以用于在前端动态构建用户界面。

此外，`django-fsm` 还提供了信号，允许你在转换发生前后以松耦合的方式执行操作：

```python
from django_fsm.signals import pre_transition, post_transition

def transition_handler(sender, instance, name, source, target, **kwargs):
    print(f"{sender.__name__} 对象 {instance.id} 从 {source} 转换到 {target} (通过 {name})")
    # 这里可以执行其他操作，如记录日志、发送通知等

pre_transition.connect(transition_handler)
post_transition.connect(transition_handler)
```

---

### 处理当前用户与审计日志
在转换中，知道当前用户是谁很重要，尤其是用于权限检查和审计。然而，转换可能从管理命令或外部服务调用，此时没有“当前请求”。建议使用 `django-cuser` 这样的中间件来设置和获取当前用户。

对于审计日志，`django-fsm` 提供了一个额外的装饰器 `@fsm_log`，可以轻松记录所有转换。

```python
from django_fsm import FSMField, transition
from django_fsm_log.decorators import fsm_log_by

class Article(models.Model):
    state = FSMField(default='draft')

    @fsm_log_by
    @transition(field=state, source='draft', target='review')
    def submit(self):
        pass
```

启用 `django-fsm-log` 后，它会在数据库中提供一个表，记录对象上发生的所有转换：谁、在何时、调用了什么转换。

---

### 集成到 Django 管理后台
如果你想在 Django 管理后台中管理 FSM 字段，可以使用 `django-fsm-admin`。它可以强制 FSM 字段只能通过转换按钮来操作，而不是直接编辑字段值，从而确保模型状态的一致性。

---

### 生成工作流图表
`django-fsm` 内置了一个很棒的工具，可以从代码生成工作流图表。你需要安装 `graphviz` 模块。

```bash
# 安装 graphviz 系统库和 Python 包
# Ubuntu/Debian
sudo apt-get install graphviz
# macOS
brew install graphviz

pip install graphviz django-fsm[graph]
```

然后运行管理命令生成图表：

```bash
python manage.py graph_transitions -o workflow.png
```

这个命令会生成一个PNG图像文件，直观地展示你的模型状态和转换。这对于与业务人员沟通和验证业务流程非常有帮助。

---

## 总结
在本教程中，我们一起学习了有限状态机在 Django 中的应用。我们从工作流和 FSM 的基本概念开始，探讨了为何简单的布尔标志不足以应对复杂场景。接着，我们深入介绍了 `django-fsm` 库，学习了如何：
1.  使用 `FSMField` 在模型中定义状态字段。
2.  使用 `@transition` 装饰器创建状态转换方法。
3.  通过 `permission` 和 `conditions` 参数控制转换的访问权限。
4.  利用便捷方法和信号来增强功能。
5.  集成审计日志 (`django-fsm-log`) 和管理后台支持 (`django-fsm-admin`)。
6.  从代码自动生成可视化的工作流图表。

![](img/6ba0083ebb8f3ca374d19a39c98b6f6c_2.png)

通过使用 `django-fsm`，你可以以一种清晰、可维护的方式在 Django 项目中建模复杂的工作流和业务流程，确保状态转换受控、可审计，并且逻辑集中，避免代码分散。