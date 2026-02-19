CSE 331 软件设计与实现

# CSE 331 的 Eclipse 参考

目录：

+   介绍

+   Eclipse 快速参考

+   使用正确版本的 JDK

## 介绍

Eclipse 是一个集成开发环境，对 Java 有很好的支持。除了各种方便编写 Java 代码的功能（如自动完成和代码重构），它还内置支持 JUnit 和 Ant — 这些是我们在 CSE 331 中使用的工具。

Eclipse（版本 4.2）已经安装在 CSE 部门机器（以及部门虚拟机）上。查看这里了解如何在家中使用 Eclipse。

您可以在[Eclipse 的在线文档](http://www.eclipse.org/documentation/)中了解更多关于 Eclipse 功能的信息和获取帮助。

## Eclipse 快速参考

这里有一些可以让您在 Eclipse 中更轻松的技巧：

| 自动补全 | `Ctrl-Space`让 Eclipse 帮助您完成您已经开始的一些代码。Eclipse 可以完成很多事情：

+   变量，方法名，类名

    +   `ArrayL` Ctrl-Space    -->  `ArrayList`

    +   `random.next`  Ctrl-Space  -->  `random.nextInt`

+   构造函数和方法参数

    +   `new ArrayList(`    Ctrl-Space  --> `ArrayList`的构造函数弹出菜单

    +   `random.nextInt(`   Ctrl-Space --> 显示`nextInt`的参数的工具提示

+   需要重写的方法

    +   `class Foo extends Bar {`    `Ctrl-Space` --> `Bar`可以被重写的方法菜单

|

| 整理导入语句 | `Ctrl-Shift-O`（O 代表 Organize）会自动更新类的顶部`import`语句，添加需要从其他包导入的类，并删除不再使用的类。如果一个类名不明确 — 例如，`List`可能是`java.util.List`和`java.awt.List` — 那么 Eclipse 会弹出对话框询问您想要哪一个。 |
| --- | --- |
| 查找 Java API 文档 | 当光标位于类名或方法名上时，按`Shift-F2`（您必须配置此功能以指定 API 文档的位置）。 |
| 注释/取消注释代码块 | `Ctrl-/`注释高亮显示的区域。`Ctrl-\`取消注释高亮显示的区域。 |
| 重命名或移动包，类，方法和变量（更新所有引用） | 当光标位于包/类/方法/变量上时，按`Alt-Shift-R`（重命名）或`Alt-Shift-V`（移动）。或者，在包资源管理器中右键单击任何包，类，方法或变量，选择**重构** ? **重命名**进行重命名，或选择**重构** ? **移动**将其放入另一个包或类中。 |
| 删除当前行 | 当光标位于要删除的行时，按`Ctrl-D`。 |
| 为自己标记 TODO 项目 | 以 TODO 开头的注释可以让你留下关于需要修复的代码片段的备注。Eclipse 会自动将注释放在任务窗格中，即显示编译错误的窗格。（如果你看不到任务窗格，请使用 **Window** ? **Show View** ? **Tasks**。）你可以通过在任务窗格中双击快速跳转到 TODO 项目或编译错误。 |
| 生成 get() 和 set() 方法 | 确保你想要创建 get() 和 set() 方法的字段在类中已声明，然后右键单击并使用 **Source** ? **Generate Getter and Setter**。 |
| 运行最近运行过的类或单元测试 | Eclipse 工具栏上的小“播放”图标 ![](img/218b9346e6b3408bb5f2f389b3b6b66e.jpg) 运行你刚刚运行过的最后一个类或单元测试。点击下拉菜单查看最近运行的历史记录。 |
| 关闭控制台自动提升 | 当在 Eclipse 下运行的程序写入标准输出（比如通过 `println`），Eclipse 会提升“控制台”视图。这可能在运行测试或使用连续测试时很烦人。要关闭此功能，请转到 **Window** ? **Preferences** ? **Run/Debug** ? **Console** 并取消选中“程序写入标准输出时显示”。 |
| Emacs 键绑定 | 如果你喜欢在编辑代码时使用 Emacs 键绑定，请执行：**Window** ? **Preferences...**? **General** ? **Keys** ? **Modify** 并将 **Scheme** 设置为 **Emacs**。 |

## 使用正确版本的 JDK

如果出现错误，比如

```
java.lang.UnsupportedClassVersionError: utils/tests/LabelledParameterized : Unsupported major.minor version 51.0
     at java.lang.ClassLoader.defineClass1(Native Method)

```

在编译或运行测试时，如果出现问题，那么你可能使用了错误版本的 Java。CSE331 使用 Java 7。使用错误版本的 Java 的常见原因是在遵循我们的设置说明时出错，或者在此之后对 Eclipse 设置进行了不正确的更改。

以下可能会解决问题：

右键单击你的项目 ? 属性 ? Java 构建路径 ? 库选项卡 ? 移除 JRE 和 JUnit 库（但保留 `junit-4.11.jar`）? 点击“添加库” ? JRE 系统库 ? 工作区默认 JRE（jdk1.7.0）? 完成

如有问题或疑问，请联系：cse331-staff@cs.washington.edu。
