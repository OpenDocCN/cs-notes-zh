# 惰性评估和生成器 TA DAH，你完成了！

## 惰性评估

对不起，这是一个话题的小跳跃。你从第 12 课跳过了这部分，所以我们在这里做一个快速介绍。

惰性评估是正常顺序评估的实现，与应用顺序评估相对。回顾一下，在第 1 课中，我们开始讨论评估模型时，我们注意到 Scheme 是一种应用顺序语言，即当应用过程时，Scheme 过程的所有参数都会被评估。相比之下，正常顺序语言延迟评估过程参数，直到实际参数值被需要。延迟评估过程参数直到最后可能的时刻（例如，直到它们被原始操作需要时）被称为惰性评估。

Python 类似于 Scheme。当你定义一个过程并用参数调用它时。所有参数在主体评估之前都会被评估。

考虑该过程

```
def try(a, b):
    if a == 0:
       return True
    else:
       return b 
```

评估`try(0, 1/0)`将触发除零错误，因为参数都会首先被评估。

在惰性评估中，不会发生错误。评估表达式将返回 1，因为参数`1/0`永远不会被评估，因为它从未在原始过程中使用，也没有返回。

`if`在直接使用时是一个惰性过程。如果你尝试：

```
$ python
>>> if 0 == 0:
...    True
... else:
...    1/0
...
True 
```

看到 True 被返回，因为我们永远不需要评估 1/0，所以我们永远不会出错！所有这些都是可能的，因为`if`在评估过程中被处理为一个特殊形式（想想第 11 课的 mc-eval）。为了在每个过程调用中获得这种行为，我们必须改变 Python 中 eval 和 apply 的工作方式。我们只有在返回或原始使用时才立即评估过程应用的参数，而不是在将其传递给 apply 之前立即评估参数。

如果你对在解释器中实现惰性评估有更深入的了解感兴趣，请阅读原始第 12 课的[内容](http://www.cs61as.org/textbook/an-interpreter-with-lazy-evaluation.html)。

如果你想尝试在 Python 中使用惰性评估包装器的实现，请查看这个[网站](http://blitiri.com.ar/p/python/)上的 lazy.py 模块。

## 范围和生成器

我们一直在`for`循环中使用`range()`，但我们并没有想过它是如何工作的。Range 是一个惰性的不可变序列。在幕后，通过 range 创建的序列中的元素直到需要它们时才被创建。不相信我吗？尝试`print(range(4)`和`print([0, 1, 2, 3])`。

我们可以通过生成器的使用创建类似于`range()`的序列。在 Python 中，生成器是通过计算并根据需要`yield`下一个值来创建序列的函数。它们类似于 Scheme 中的流，是一种惰性序列，而不是急切枚举的列表。

生成器是[可迭代的](https://docs.python.org/3/tutorial/classes.html#iterators)，所以你可以在 for 循环中使用它们，就像我们使用 range()一样。你也可以在任何生成器过程上调用`next(generator)`来获取后续元素。然而，生成器不能被多次迭代。一旦你用完了序列，它就消失了。如果你尝试在用完的生成器上调用`next()`，你会收到一个`StopIteration`错误消息。

想一想为什么我们想要生成器。[为什么不总是使用列表？](https://www.google.com/search?q=when+to+use+generators+in+python)

`yield`是我们创建生成器而不是函数的过程。你会使用`yield`而不是`return`。现在举个例子：

```
def gen_to(n):
    for i in range(n+1):
        yield i 
```

现在尝试使用 for 循环打印每个元素：

```
gen_to_7 = gen_to(7)
for i in gen_to(7):
    print(i) 
```

现在尝试调用`next`：

```
next(gen_to_7) 
```

啊哈！`StopIteration`错误！

现在是一个无限生成器！尝试`print`和通过调用`next`来遍历。

```
def gen_forever():
    i = -1
    while true:
        i += 1
        yield i 
```

> **作业问题 10：成长的烦恼（指数增长）**
> 
> 编写一个名为`gen_exp()`的生成器，接受一个数字 n，并从 n 开始生成（永远）n 的指数 n 的指数 n。 
> 
> 例如，`gen_exp(2)`的前几个元素应该是 2，(2²)，((2²)^ 2)，(((2²)^ 2) ^ 2)

# 完成啦！

## 更多酷炫的东西！如果你喜欢学习 Python，你应该深入了解。

+   [导入模块](https://docs.python.org/3/tutorial/modules.html)像[数学模块...太棒了](https://docs.python.org/3/library/math.html)。查看[此链接](https://docs.python.org/3/library/index.html)以获取 Python 3.5 捆绑的模块库的广泛目录。

+   [海龟图形](https://docs.python.org/3/library/turtle.html)

+   [科学数学内容](http://www.scipy.org/)，已经随 Anaconda 发行版安装
