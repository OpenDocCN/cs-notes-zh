# Java编程和软件工程基础：2-5：添加新标签

![](img/91377d1c664b514a106cc1fbc7c06c1e_0.png)

在本节课中，我们将学习如何为Gladlib程序添加一个新的标签类别，例如“动词”。我们将通过修改源代码、创建新的数据文件和模板文件来完成这一过程。

---

上一节我们介绍了Gladlib程序的基本结构，本节中我们来看看如何为其添加一个全新的标签类别。

![](img/91377d1c664b514a106cc1fbc7c06c1e_2.png)

![](img/91377d1c664b514a106cc1fbc7c06c1e_3.png)

首先，我们需要一个新的模板文件。我使用了之前的标准模板文件 `madtemplate.txt`，并将其中的“S”和“dance”替换为“verb”和“verb”。这样，我就在原始故事中添加了“verb”标签来替换原有的占位符。这个新文件仍然命名为 `madtemplate.txt`。你可以使用任何文本编辑器来创建这个文件，例如Mac上的TextEdit或Windows上的Notepad++。

现在，我将使用之前的Gladlib程序，并逐步指出需要修改的位置。

![](img/91377d1c664b514a106cc1fbc7c06c1e_5.png)

我需要创建一个新的ArrayList来存储动词。我将遵循之前使用的命名约定，确保使用 `verbList` 来与 `adjectiveList`、`nounList` 等保持一致。

浏览源代码时，我发现这些ArrayList在 `initializeFromSource` 方法中被初始化，该方法由类的构造函数调用。因此，我需要初始化 `verbList`。它将通过调用 `readIt` 方法来初始化，传入数据源（可以是本地文件路径或URL）和文件名 `verb.txt`。

我还需要进行另一处修改。在判断标签类型的代码块中，除了已有的形容词、动物、名字等，我还需要添加对“verb”标签的处理。我将复制并粘贴现有的代码段，然后将标签名称替换为“verb”。我需要确保语法正确：如果标签是“verb”，我将从 `verbList` 中获取替换词。

![](img/91377d1c664b514a106cc1fbc7c06c1e_7.png)

以下是修改的核心代码部分：

![](img/91377d1c664b514a106cc1fbc7c06c1e_9.png)

```java
// 1. 声明实例变量
private ArrayList<String> verbList;

// 2. 在 initializeFromSource 方法中初始化
verbList = readIt(source + "/verb.txt");

// 3. 在 getSubstitute 方法或类似逻辑中添加处理分支
if (label.equals("verb")) {
    return getRandom(verbList);
}
```

接下来，我将编译我的程序。我知道这个程序会从 `madtemplate.txt` 中读取模板，而我已经修改了这个模板以包含 `<verb>` 标签。

编译完成后，我将在对象工作台上创建一个新的Gladlib对象，然后运行 `makeStory` 方法。第一次运行时，输出中出现了“unknown”，这表明程序找到了“verb”标签，但未能成功替换。回顾源代码，我发现 `verbList` 实例变量已声明，并在 `initializeFromSource` 中从 `verb.txt` 初始化。问题出在标签判断的代码中，我拼写有误。修正拼写错误后，我重新创建Gladlib对象并生成故事。

现在，输出变成了：“It's so loved to think and contemplate...”。为了确认程序确实在读取动词，我多运行了几次，得到了“ride and surrender”、“surrender and surrender”等不同的动词组合。请注意，我们尚未实现防止同一动词被重复使用的逻辑，所以有时会出现重复。

![](img/91377d1c664b514a106cc1fbc7c06c1e_11.png)

总结一下我们所做的步骤：
1.  在模板文件中添加新标签。
2.  在源代码中声明并初始化对应的ArrayList（`verbList`）。
3.  在标签处理逻辑中添加对新标签（“verb”）的判断和替换。
4.  创建包含新词汇的数据文件（`verb.txt`）。
5.  编译并测试程序。

本节课中我们一起学习了为Gladlib程序扩展新标签的完整流程。你掌握了如何修改模板、更新源代码以声明和初始化新的词汇列表，并在核心逻辑中集成对新标签的处理。通过遵循清晰的命名约定和结构，你可以轻松地为程序添加更多标签类别，如“副词”或“地点”。现在，你可以尝试添加自己的新标签了。