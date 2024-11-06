# 迷你 Python 介绍

## 介绍

此时，您应该对 Scheme 和 Racket 中的编程原理非常熟悉了。现在是将这些知识转换为一种新语言的时候了！进入 Python。这比您项目 4 规范中的 Python 介绍要详细一些，但仍然相当基本。完成一个应该使另一个变得轻松。享受吧！

## 作业

作业提示散布在整个课程中，旨在在您学习的同时进行一些小练习。这是[模板](https://drive.google.com/open?id=0Bx-YJoc_dDDGQjhHSnNlRDNkaTg)。本课程的作业部分将提供更多详细信息！

## 安装

我们将在本课程中使用 Python 3（具体来说是 3.5 版本）。这与 Python 2 不相等。如果您已经安装了 Python 3，则可以跳过以下内容。在您的终端启动 python 后，会显示您已安装的版本，请在那里检查。

### Anaconda（推荐的安装方法）

Anaconda 是 Python 的一个发行版，它将 Python 与其他一些有用的库（如 [NumPy](https://en.wikipedia.org/wiki/NumPy)）打包在一起。Anaconda 还使安装更多扩展变得更容易，并自动将 python 添加到计算机的路径变量中。

请从此链接安装 Python 3.5：https://www.continuum.io/downloads 并选择阅读 [这个](http://conda.pydata.org/docs/py2or3.html) 以更加了解 conda 及其强大之处。

通过其他方法获取 Python 3.5 也可以，这只是一种推荐的方法。如果遇到任何问题，请咨询谷歌和 StackOverflow！

## 加载和运行 Python

如果您已正确安装 Python 3，则应该能够通过终端使用命令 `python` 启动它。您应该会看到三个大于号 `>>>`，表示 python 解释器正在接受输入！如果遇到问题，请检查是否已设置路径环境变量以指向您的安装位置（如果不确定是什么意思，请尝试谷歌！），并确保删除任何其他路径以指向较旧的 python 版本。如果您使用的是 mac，请参阅 [此链接](http://superuser.com/questions/770696/how-to-update-macs-system-python)。

```
MyComputer ~ $ python
Python 3.5.1 |Anaconda 2.4.1 (64-bit)| (default, Jan 29 2016, 15:01:46) [MSC v.1900 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()
MyComputer ~ $ 
```

如果您有一个文件想要在 python 中运行，可以在终端中输入“python”，然后是文件路径和“-i”标志，以加载文件并交互式运行 python。如果缺少 -i 标志，python 将加载文件，运行它，然后退出。

```
MyComputer ~ $ python python_hw.py -i
>>> 
```

## 资源

不需要阅读！只是更多帮助和指导的参考：

+   [官方 Python 3 指南和文档](https://docs.python.org/3/tutorial/index.html)

+   [Python Wikibook](https://en.wikibooks.org/wiki/Python_Programming)

+   [迷你 Python 示例](https://wiki.python.org/moin/SimplePrograms)

+   [谷歌](https://google.com)

准备好后，继续下一节！
