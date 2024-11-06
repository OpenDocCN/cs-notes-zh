# 变量和定义

## 变量

要定义一个变量，请使用等号符号。（要检查相等性，使用双等号。）变量可以在过程定义内外定义。

```
>>> x = 1 #set x to be 1
>>> x
1
>>> x == 1 #check if x equals 1
True 
```

## 定义过程

要定义一个过程，请使用“def”。在 Python 中，缩进（行首的空格）和冒号是结构化 Python 代码的分隔符。因此，我们将使用缩进来指示过程的主体。完成后，如果你直接在解释器中输入，则需要一个与 def 行匹配缩进的空行来关闭定义块。

```
>>> def func(x):
...    x = x * 2
...    return x + 1
... 
>>> func(1)
3 
```

+   (0 space indentation) 函数头部分配函数名称和参数

+   (3 space indentation) 函数的主体将 x 值加倍并返回（x 的两倍）+ 1

+   (0 space indentation) 空行用于结束定义块

+   使用参数 x 为 1 调用 func

+   返回 3

注意我们如何使用 return 语句。return 会停止过程并将输出传回以显示。没有 return 语句的行不会传播到过程内部之外。一个恰当的类比是：return 语句类似于你大声说出来的话，而非 return 语句类似于你说话之前的思维。

如果你的主体是单个表达式，你可以在一行中编写过程定义。你仍然需要空行

```
>>> def func(x): return (x * 2) + 1
...
>>> func(2)
5 
```

+   (0 space indentation) 函数头部分配函数名称和参数以及单个表达式主体

+   (0 space indentation) 空行用于结束定义语句

+   使用参数 x 为 1 调用 func

+   返回 3
