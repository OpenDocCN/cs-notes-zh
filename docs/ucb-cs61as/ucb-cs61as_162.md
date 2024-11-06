# 作业 14

要处理下一个作业问题中的思想，你应该首先

`(load "~cs61as/lib/concurrency.scm")`

## 练习 1

练习[3.38](http://mitpress.mit.edu/sicp/full- text/book/book-Z-H-23.html#%_thm_3.38)，[3.39, 3.40, 3.41, 3.42](http://mitpress.mit.edu/sicp/full- text/book/book-Z-H-23.html#%_thm_3.39)，[3.44](http://mitpress.mit.edu/sicp /full-text/book/book-Z-H-23.html#%_thm_3.44)，[3.46, 3.48](http://mitpress.mit.edu/sicp/full- text/book/book-Z-H-23.html#%_thm_3.46)，由阿贝尔森和苏斯曼

## 练习 2：链接 Mapreduce

编写函数`real-most-frequent`，接受一个键值对列表，其中键是文件名，值是来自该文件的行（就像我们的 all-songs 示例）。我们的输出再次是一个**单一**键值对列表。你可能想要重用我们在课程中定义的任何函数。

```
>(real-most-frequent all-songs)
((i . 4)) 
```

## 练习 3：使用流进行 Mapreduce

我们当前的 mapreduce 是使用列表的。现实生活中的 mapreduce 处理的是非常大的数据集：大到列表无法容纳。解决这个问题的一种方法是使用流而不是列表来进行 mapreduce。你可以在这里找到我们的适用于流的 mapreduce 版本这里或者在"~cs61as/lib/mapreduce/streammapreduce.scm"中找到

有什么改变？我们的 map、sort-into-buckets 和 filter 现在可以与流一起工作。作为用户，你需要提供什么？就像之前做过的那样，mapper 和 reducer。mapper 和 reducer 发生了什么变化？**它们没有**。mapper 和 reducer 的行为不会改变。你可以加载文件并尝试`(mapreduce mapper reducer 0 all-songs)`，其中 mapper 和 reducer 是你在课程中定义的。它们会以相同的方式工作。唯一的区别是，如果 all-songs 很大，我们之前的版本会崩溃，而我们的流版本仍然能够处理它

## 练习 4：你想成为最强的吗？

你可以访问所有 744 只宝可梦数据的流这里和"~cs61as/lib/mapreduce/pokemon_data"。`streammapreduce.scm`应该会自动加载它，并将变量"data"定义为你的输入。键是宝可梦的国家编号，值是一个区域编号、名称、名称（是的，它出现两次），以及它们拥有的类型列表。例如，第一个元素是`(1 1 bulbasaur bulbasaur grass poison)`，所以它的国家编号是 1，区域编号是 1，名称是 bulbasaur，类型是'grass'和'poison'。宝可梦可以有 1 或 2 种类型。这里有一个只有一种类型的例子：`(4 4 charmander charmander fire)`。你可以在加载文件后在解释器中输入`(ss data)`来查看输入。

定义 mapper、reducer 和基本情况，使得调用`(mapreduce mapper reducer base-case data)`会返回一个键值对列表，其中键是不同类型，值表示数据集中该类型的宝可梦出现的次数。最终结果应该产生以下结果（任意顺序）：

```
((grass . 86) (dragon . 39) (normal . 99) (flying . 93) (poison . 59) (ice . 35) (fire . 58) (ghost . 37) (psychic . 77) (electric . 47) (water . 124) (fairy . 35) (bug . 70) (steel . 42) (ground . 62) (rock . 54) (fighting . 45) (dark . 44)) 
```

## 提交您的作业！

有关说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果您在提交作业时遇到任何问题，请不要犹豫向助教求助！
