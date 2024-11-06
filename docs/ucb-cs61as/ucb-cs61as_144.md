# 控制措施

## If、Elif、Else

条件语句使用 if、elif 和 else 语句形成。if 语句由谓词和一个在谓词满足时执行的主体组成。Elif 是“else if”的缩写，用于第一个 if 语句之外的任何其他条件。elif 语句的构造与 if 语句类似。else 语句跟随所有 if 和 elif 语句，当之前的所有条件语句都不满足时触发。

If、elif 和 else 使用缩进和冒号适当地阻止代码。完成后，您需要一个空行，与第一行具有相同的缩进，以关闭条件语句，当您直接输入到解释器时。

```
>>> if False:
...    3
... elif True:
...    4
... else:
...    5
...
4 
```

+   第 1 行：（0 个空格缩进）if 条件

+   第 2 行：（3 个空格缩进）if 主体

+   第 3 行：（0 个空格缩进）else if 条件

+   第 4 行：（3 个空格缩进）else if 主体

+   第 5 行：（0 个空格缩进）else

+   第 6 行：（3 个空格缩进）else 主体

+   第 7 行：（0 个空格缩进）空行关闭 if 块并调用评估

+   第 8 行：返回 4（跳过 if 情况，触发 elif 情况，永远不会到达 else 情况）

请注意，没有使用返回语句。这是因为条件语句在过程定义之外。在函数体内，您期望“return 3”而不是“3”等等，如果这是期望的返回值。

> **作业问题 3：Fizz Buzz**
> 
> 编写一个程序，打印从 1 到 n 的整数（n 是程序的参数）。但是对于三的倍数，打印“Fizz”而不是数字，对于五的倍数，打印“Buzz”。对于既是三的倍数又是五的倍数的数字，打印“FizzBuzz”。

## 循环和范围

在 python 中，支持循环。循环多次执行一个代码块或一行代码。循环对于希望通过一个序列或重复一个操作的情况非常有用---使用循环进行迭代，而不是递归。`for`循环控制迭代次数以对应要迭代的序列的条目。`while`循环通过谓词控制迭代次数。

在循环中可以调用某些控制语句来停止并跳出循环，或者跳到下一个迭代。`break`执行前者，`continue`执行后者。如果需要示例，请查阅在线资源。

### While 循环

While 循环包含一个谓词，在每次迭代开始之前检查。如果谓词不满足，则 while 循环停止。while 块使用冒号和缩进来指示哪一行是头部，哪些是主体

```
>>> x = 0
>>> while x < 3:
...    print("repeat")
...    x += 1
...
hello
hello
hello
>>> x #check what x is
3 
```

+   第 1 行：设置一个变量 x 等于零

+   第 2 行：（0 个空格）带有 x 小于 3 的条件的 While 头部

+   第 3 行：（3 个空格）While 主体行调用打印

+   第 4 行：（3 个空格）While 主体行将 x 增加 1（x += 1 与 x = x + 1 相同）

+   第 5 行：（0 个空格）空行关闭 While 块并评估该块

+   第 6 行：当 x = 0 时打印 hello。

+   第 7 行：当 x = 1 时打印 hello。

+   第 8 行：当 x = 2 时打印 hello。

+   第 9 行：检查 x 的值。

+   第 10 行：返回 x 的值为 3（这不是小于 3）

> **作业问题 4：白雪公主和七个小矮人**
> 
> 编写一个名为`snow_white`的程序，它接受两个数字作为参数，第一个是`num_chants`，第二个是`max_sing`。
> 
> 该程序：
> 
> 1.  交替打印"heigh"和"ho"。
> 1.  
> 1.  每唱完`num_chants`次"heigh"或者"ho"后，打印"its off to work we go"。
> 1.  
> 1.  在唱了"it's off to work we go" `max_sing`次后停止打印。
> 1.  
> 例子：每唱完`5`次交替出现的"hi"和"ho"之间打印"it's off to work we go"，最多`2`次。
> 
> ```
> >>> snow_white(5, 2)
> heigh
> ho
> heigh
> ho
> heigh
> it's off to work we go
> ho
> heigh
> ho
> heigh
> ho
> it's off to work we go 
> ```
> 
> 使用 while 循环（可能还有控制语句）来实现此行为。
> 
> **作业问题 5：将第一个奇数推后（来自 CS10）**
> 
> 写一个名为`push_first_odd_back`的函数，它以列表作为参数。该函数应该将第一个奇数放到输入列表的末尾。不要返回新列表 - 实际上，这个函数不应该返回任何东西，它只应该修改输入列表。（提示：使用 while 循环）

### 对于循环

For 循环包含一个变量和一个序列（稍后详细介绍）。每次迭代时，变量的值都会更改为序列中的下一个值。与其他多行块一样，for 循环由冒号和缩进限定，并在空行处完成。在 for 循环的主体中，您可以访问被迭代的变量的值。

`range`函数创建一个数字序列，然后可以在`for`循环中用于控制。Range 接受一个开始、结束和增量，以创建一个包含开始和增量条目的序列，但不包括结束。如果没有提供，range 将默认开始为零，增量为一。现在，只在`for`循环的上下文中使用`range`，在后面的课程中，我们将深入探讨`range`的工作原理。

提示：如果你想要 x 次迭代并且实际上不打算使用迭代变量，可以使用`range(x)`。 

```
>>> for i in range(2): #same as do two times
...    print "hello"
...
hello
hello 
```

```
>>> for i in range(3): #i is 0 then 1 then 2
...    print i
...
0
1
2 
```

```
>>> for i in range(2, 6, 2): #start at 2, stop before 6, skip 2
...    print(i)
...
2
4 
```

你也可以在 range 的位置使用字符串或列表作为要迭代的序列。

```
>>> sum = 0
>>> for number in [1,5,8]: #iterating over a list
...    sum += number
...
>>> sum
14 
```

```
>>> longer_string = ""
>>> for letter in "apple": #iterating over string
...    longer_string += letter * 3
...
>>> longer_string
'aaappppppllleee' 
```

> **作业问题 6：猫和狗**
> 
> 编写一个程序，如果字符串中的"cat"和"dog"出现的次数相同，则返回 True。
> 
> ```
> cat_dog('catdog') → True
> cat_dog('catcat') → False
> cat_dog('1cat1cadodog') → True 
> ```
