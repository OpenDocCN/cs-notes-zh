# 增量测试

当你写程序时，很容易写完整个程序，然后开始调试它。

一般来说，这是非常糟糕的策略。最好在编写每个函数后立即测试每个函数。

只有第一个函数正确工作后，才继续处理下一个函数。

在 Kotlin 中，我们可以使用交互模式来交互式测试函数。我们在交互模式中使用 :load 命令。同样的命令允许我们在对代码进行更改后重新加载它：

```
$ ktc
Welcome to Kotlin version 1.0.1-2 (JRE 1.7.0_95-b00)
Type :help for help, :quit for quit
>>> :load triangle.kts
>>> triangle(3)
*
**
***
>>> triangle(5)
*
**
***
****
*****

```

#### 一个完整的例子：科拉茨问题

让我们以一个例子，所谓的科拉茨问题，来练习增量测试。

考虑遵循以下规则的整数序列：

\[ n_{i+1} = \left\{ \begin{array}{ll} 3n_i + 1 & \text{如果 $n_i$ 是奇数}\\ n_i/2 & \text{如果 $n_i$ 是偶数} \end{array} \right. \]

如果提供一个起始值 \(n_0\)，这将确定一个完整的序列。以下是一些示例，起始值为 5、34、7 和 672：

```
5 16 8 4 2 1
34 17 52 26 13 40 20 10 5 16 8 4 2 1
7 22 11 34 17 52 26 13 40 20 10 5 16 8 4 2 1
672 336 168 84 42 21 64 32 16 8 4 2 1

```

你可以注意到所有四个示例序列都达到了数字 1（然后当然序列开始循环：1 4 2 1 4 2 1 4 2 1...）。

有人猜测这总是成立：对于任何起始值，序列都会到达 1。

我们想对这个猜想进行一些实验，例如实验性地确定哪个起始值给出了长链。因此，我们希望编写函数，给定起始值后，可以打印出整个序列，并可以打印出达到 1 之前的步数。

让我们从基本函数开始：给定 \(n_i\)，计算下一个数字 \(n_{i+1}\)。我创建了一个文件 [collatz.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/07-collatz/collatz1.kts)，内容如下：

```
fun next(n: Int): Int = 
  if (n % 2 == 0)
    n / 2
  else
    3 * n + 1

```

我们通过加载文件并检查它是否正确处理奇偶情况来测试此函数：

```
$ ktc
Welcome to Kotlin version 1.0.1-2 (JRE 1.7.0_95-b00)
Type :help for help, :quit for quit
>>> :load collatz.kts
>>> next(1)
4
>>> next(4)
2
>>> next(2)
1
>>> next(5)
16
>>> next(16)
8
>>> next(52)
26
>>> next(123417432)
61708716
>>> next(123417431)
370252294

```

看起来函数工作正常，所以下一步是编写一个函数，从给定的起始值开始打印整个序列。我们将函数 collatz 添加到我们的文件中：

```
fun collatz(n0: Int) {
  var n = n0
  while (n != 1) {
    print(n)
    print(" ")
    n = next(n)
  }
}

```

我重新加载文件并在一个例子上进行测试：

```
>>> :load collatz.kts
>>> collatz(5)
5 16 8 4 2

```

然后我注意到我的错误：循环没有打印最终的 1。所以我把我的函数改成了如下形式（[collatz.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/07-collatz/collatz2.kts)）：

```
fun collatz(n0: Int) {
  var n = n0
  while (n != 1) {
    print(n)
    print(" ")
    n = next(n)
  }
  println(1)
}

```

然后我可以继续通过重新加载文件并重试来进行测试：

```
>>> :load collatz.kts
>>> collatz(5)
5 16 8 4 2 1
>>> collatz(16)
16 8 4 2 1
>>> collatz(17)
17 52 26 13 40 20 10 5 16 8 4 2 1
>>> collatz(27)
27 82 41 124 62 31 94 47 142 71 214 107 322 161 484 242 121 364 182 91
274 137 412 206 103 310 155 466 233 700 350 175 526 263 790 395 1186
593 1780 890 445 1336 668 334 167 502 251 754 377 1132 566 283 850 425
1276 638 319 958 479 1438 719 2158 1079 3238 1619 4858 2429 7288 3644
1822 911 2734 1367 4102 2051 6154 3077 9232 4616 2308 1154 577 1732
866 433 1300 650 325 976 488 244 122 61 184 92 46 23 70 35 106 53 160
80 40 20 10 5 16 8 4 2 1

```

现在看起来工作得很好。

下一个函数将计算从给定的起始值开始到达 1 所经历的步骤数：

```
fun collatzCount(n0: Int): Int {
  var n = n0
  var count = 0
  while (n != 1) {
    n = next(n)
    count += 1
  }
  return count
}

```

我通过将结果与 collatz 的输出进行比较来测试这一点：

```
>>> :load collatz.kts
>>> collatz(5)
5 16 8 4 2 1
>>> collatzCount(5)
5
>>> collatz(16); collatzCount(16)
16 8 4 2 1
4

```

最后，我将编写一个函数，它尝试所有从 2 到给定最大值 \(n\) 之间的起始值，并报告具有最长序列的起始值（[collatz3.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/07-collatz/collatz3.kts)）：

```
fun findMax(n: Int) {
  var maxCount = 0
  var maxStart = 1
  for (i in 2 .. n) {
    val count = collatzCount(i)
    if (count > maxCount) {
      maxCount = count
      maxStart = i
    }
  }
  println("Starting at $maxStart needs $maxCount steps.")
}

```

这是测试此函数的结果：

```
>>> :load collatz3.kts
>>> findMax(100)
Starting at 97 needs 118 steps.
>>> findMax(500)
Starting at 327 needs 143 steps.
>>> findMax(1000)
Starting at 871 needs 178 steps.
>>> findMax(2000)
Starting at 1161 needs 181 steps.
>>> findMax(4000)
Starting at 3711 needs 237 steps.
>>> findMax(10000)
Starting at 6171 needs 261 steps.
>>> findMax(20000)
Starting at 17647 needs 278 steps.
>>> findMax(40000)
Starting at 35655 needs 323 steps.
>>> findMax(80000)
Starting at 77031 needs 350 steps.

```

#### 单元测试

对于大型程序，通常为每个函数或类编写一个单独的测试程序是很常见的。这些测试程序称为单元测试。

有些程序员甚至在编写代码之前就编写测试！

即使程序完成后，单元测试仍然很有用。所有软件都需要维护。每当对软件进行更改时，我们可以再次运行单元测试，以确保我们没有破坏任何东西。

在许多软件项目中，单元测试是自动化的，并且每晚运行，以确保白天进行的更改没有引入任何新的错误。

我们不会要求您在 CS109 中编写单元测试，但您应该养成测试函数的习惯。通常可以通过手动交互式测试。但是，当您需要超过两三行代码来测试一个函数时，编写额外的测试函数是有意义的。将它们保留在您的代码中，这样以后在进行更改时可以再次使用它们来检查您的程序。
