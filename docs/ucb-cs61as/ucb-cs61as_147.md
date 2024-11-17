# Python 作业

截止日期为 2016 年 4 月 28 日晚上 11:59（太平洋时间）

（但你可能应该在项目 4 之前/期间完成这个）

## 模板

在此处下载[链接](https://drive.google.com/open?id=0Bx-YJoc_dDDGQjhHSnNlRDNkaTg)。

## 自动评分程序

抱歉！目前还没有自动评分程序。尽量测试你的作业，你将会被宽容地评分。为了努力而给你 A。如果时间允许，将会有自动评分程序。

## 练习

**作业问题 1: 淘气字符串**

当你在字符串内部不正确使用引号时返回的错误消息是什么？

提供一个例子并解释错误信息。

* * *

**作业问题 2: 水果和蔬菜**

`x = ["apple", "banana", "carrot"]`

写一行代码，当执行时返回“apples bananas and carrots”。

* * *

**作业问题 3: Fizz Buzz**

编写一个程序，打印从 1 到 n（n 是该过程的参数）的整数。但对于三的倍数，打印“Fizz”而不是数字，对于五的倍数，打印“Buzz”。对于既是三的倍数又是五的倍数的数字，打印“FizzBuzz”。

* * *

**作业问题 4: 白雪公主和七个小矮人**

编写一个名为`snow_white`的程序，它接受两个数字作为参数，第一个是`num_chants`，第二个是`max_sing`。

该程序：1. 交替打印“heigh”“ho” 2. 在“heigh”或“ho”的`num_chants`后打印“我们去工作” 3. 在打印“it's off to work we go” `max_sing`次后停止打印

例子：应该在每`5`次交替他和他之间打印"我们去工作"。

```
snow_white(5, 2)
heigh
ho
heigh
ho
heigh
it's off to work we go
ho
heigh
ho
heigh
ho
it's off to work we go 
```

使用 while 循环（可能还有控制语句）来实现这种行为。

* * *

**作业问题 5: 将第一个奇数推回（取自 CS10）**

编写一个名为`push_first_odd_back`的函数，它接受一个列表作为参数。该函数应该将第一个奇数放在输入列表的末尾。不要返回一个新列表 - 实际上，这个函数不应该返回任何东西，它只应该修改输入列表。（提示：使用 while 循环）

* * *

**作业问题 6: 猫和狗**

编写一个程序，在给定的字符串中，如果字符串"cat"和"dog"出现的次数相同，则返回 True。

```
cat_dog('catdog') → True
cat_dog('catcat') → False
cat_dog('1cat1cadodog') → True 
```

* * *

**作业问题 7: 字符频率**

编写一个名为`char_freq()`的函数，它接受一个字符串并构建其中包含的字符的频率列表。将频率列表表示为一个 Python 字典，其中每个字母作为一个键，存储该字母出现的次数。

尝试使用类似`char_freq("abbabcbdbabdbdbabababcbcbab")`的东西。

* * *

**作业问题 8.1: 凯撒密码**

编写一个名为`rotate_letters()`的函数，它接受一个数字并创建一个新的映射，将小写字母偏移该数字。将新的���射作为字典返回，原始字母映射到移位后的字母。例如，`rotate_letters(2)`将映射`'a'`->`'c'`，`'b'`->`'d'`，`'c'`->`'e'`等等。

**作业问题 8.2: 凯撒密码**

编写一个函数`decode_cipher()`，它接受一个字母映射的字典和一个密码字符串（仅包含小写字母）。返回通过字典中的映射替换每个字符而创建的解码字符串。例如，`decode_cipher(rotate_letters(2), "abc")`应返回`"cde"`。

使用这个函数解码`"jbj fpurzr vf terng"`，假设字母已经被移动了 13 位。

* * *

**作业问题 9: 记忆化阶乘**

以类似于`memo_fib`的方式编写一个记忆化累积阶乘过程。你必须使用递归。

累积阶乘 5 = 5! * 4! * 3! * 2! * 1!

* * *

**作业问题 10: 成长的痛苦（指数增长）**

编写一个生成器`gen_exp()`，它接受一个数字 n，并生成（永远）从 n 开始的 n 的 n 的 n 的指数。例如，`gen_exp(2)`的前几个元素应该是 2，(2²)，((2²)^ 2)，(((2²)^ 2) ^ 2)

* * *

## 提交你的作业！

请将作业提交为 python_hw 而不是 hw12。请在 2016 年 4 月 1 日之后（而不是之前）提交！

查看此指南获取说明。它涵盖了基本的终端命令和作业提交。

如果你在提交作业时遇到任何问题，请不要犹豫向助教求助！