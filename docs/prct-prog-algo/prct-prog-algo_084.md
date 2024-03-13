# 1.1   编程模型

> 原文：[`algs4.cs.princeton.edu/11model`](https://algs4.cs.princeton.edu/11model)

本节正在大规模施工中。

我们对算法的研究基于将它们作为用 Java 编程语言编写的程序来实现。我们这样做有几个原因： 

+   我们的程序是算法的简洁、优雅和完整描述。

+   您可以运行程序来研究算法的属性。

+   您可以立即将算法应用于应用程序中。

## 原始数据类型和表达式。

*数据类型*是一组值和对这些值的一组操作。以下四种原始数据类型是 Java 语言的基础：

+   *整数*，带有算术运算（`int`）

+   *实数*，再次带有算术运算（`double`）

+   *布尔值*，值集合为{ *true*, *false* }，带有逻辑运算（`boolean`）

+   *字符*，您键入的字母数字字符和符号（`char`）

一个 Java 程序操作用*标识符*命名的*变量*。每个变量与数据类型关联，并存储其中一个可允许的数据类型值。我们使用*表达式*来应用与每种类型相关的操作。

> ![Java 程序的基本构建块](img/378d01fbb7e15d39954b60ae7109b2f6.png)

以下表总结了 Java 的`int`、`double`、`boolean`和`char`数据类型的值集合和最常见操作。

> ![Java 中的原始数据类型](img/4be9cb1f9a222ffe63f6b7e6debe0855.png)

+   *表达式。* 典型表达式为*中缀*。当一个表达式包含多个运算符时，*优先级顺序*指定它们应用的顺序：运算符`*`和`/`（以及`%`）的优先级高于（在`+`和`-`运算符之前应用）；在逻辑运算符中，`!`具有最高优先级，其次是`&&`，然后是`||`。通常，相同优先级的运算符是*左结合*（从左到右应用）。您可以使用括号来覆盖这些规则。

+   *类型转换。* 如果不会丢失信息，数字会自动提升为更包容的类型。例如，在表达式`1 + 2.5`中，`1`被提升为`double`值`1.0`，表达式求值为`double`值<t>3.5。*强制转换*是将一个类型的值转换为另一个类型的指令。例如`(int) 3.7`是`3`。将`double`转换为`int`会朝向零截断。</t>

+   *比较。* 以下*混合类型*运算符比较相同类型的两个值并产生一个`boolean`值：

    +   *等于*（`==`)

    +   *不等于*（`!=`)

    +   *小于*（`<`)

    +   *小于或等于*（`<=`)

    +   *大于*（`>`）

    +   *大于或等于*（`>=`)

+   *其他原始类型。* Java 的`int`有 32 位表示；Java 的`double`类型有 64 位表示。Java 还有五种额外的原始数据类型：

    +   64 位整数，带有算术运算（`long`）

    +   16 位整数，带有算术运算（`short`）

    +   16 位字符，带有算术运算（`char`）

    +   8 位整数，带有算术运算（`byte`）

    +   32 位单精度实数，带有算术运算（`float`）

## 语句。

一个 Java 程序由*语句*组成，通过创建和操作变量、为它们分配数据类型值以及控制这些操作的执行流程来定义计算。

+   *声明*创建指定类型的变量并用标识符命名它们。Java 是一种*强类型*语言，因为 Java 编译器会检查一致性。变量的*作用域*是程序中定义它的部分。

+   *赋值*将数据类型值（由表达式定义）与变量关联。

+   *初始化声明*将声明与赋值结合在一起，以初始化变量的同时声明变量。

+   *隐式赋值。* 当我们的目的是相对于当前值修改变量的值时，可以使用以下快捷方式：

    +   递增/递减运算符：代码`i++`是`i = i + 1`��简写。代码`++i`相同，只是在递增/递减之后取表达式值，而不是之前。

    +   其他复合运算符：代码`i /= 2`是`i = i/2`的简写。

+   *条件语句*提供了对执行流程的简单改变——根据指定条件在两个块中的一个中执行语句。

+   *循环*提供了对执行流程的更深刻改变——只要给定条件为真，就执行块中的语句。我们将循环中的语句称为循环的*主体*。

+   *中断和继续。* Java 支持在 while 循环中使用的两个额外语句：

    +   `break`语句，立即退出循环

    +   `continue`语句，立即开始循环的下一次迭代

+   *关于符号。* 许多循环遵循这种方案：将索引变量初始化为某个值，然后使用`while`循环来测试涉及索引变量的循环继续条件，其中`while`循环中的最后一条语句递增索引变量。您可以使用 Java 的`for`符号简洁地表示这样的循环。

+   *单语句块。* 如果条件或循环中的语句块只有一个语句，则大括号可以省略。

以下表格说明了不同类型的 Java 语句。

> ![Java 语句](img/722b40d160d70d2577710c1c756c01d8.png)

## 数组。

*数组*存储相同类型的值序列。如果有`N`个值，我们可以使用符号`a[i]`来引用`i`的值，其中`i`的值从`0`到`N-1`。

+   *创建和初始化数组。* 在 Java 程序中创建数组涉及三个不同的步骤：

    +   声明数组名称和类型。

    +   创建数组。

    +   初始化数组值。

+   *默认数组初始化。* 为了节省代码，我们经常利用 Java 的默认数组初始化约定，并将所有三个步骤合并为一个语句。数值类型的默认初始值为零，`boolean`类型的默认值为`false`。

+   *初始化声明。* 我们可以在编译时指定初始化值，通过在大括号之间列出逗号分隔的文字值。

    > ![声明、创建和初始化数组](img/d9f46a6ab5affa421fd6735d765a34f3.png)

+   *使用数组。* 一旦创建数组，其大小就固定了。程序可以使用代码`a.length`引用数组`a[]`的长度。Java 进行*自动边界检查*——如果您使用非法索引访问数组，程序将以[ArrayIndexOutOfBoundsException](http://download.oracle.com/javase/6/docs/api/java/lang/ArrayIndexOutOfBoundsException.html)终止。

+   *别名。* 数组名称指代整个数组——如果我们将一个数组名称分配给另一个数组名称，则两者都指代同一个数组，如下面的代码片段所示。

    ```
    int[] a = new int[N];
    ...
    a[i] = 1234;
    ...
    int[] b = a;
    ...
    b[i] = 5678;   // a[i] is now 5678.

    ```

    这种情况被称为*别名*，可能导致微妙的错误。

+   *二维数组。* 在 Java 中，二维数组是一维数组的数组。二维数组可能是*不规则的*（其数组的长度可能各不相同），但我们通常使用（对于适当的参数 M 和 N）M×N 的二维数组。要引用二维数组`a[][]`中第`i`行第`j`列的条目，我们使用表示法`a[i][j]`。

## 静态方法。

许多编程语言中称静态方法为*函数*，因为它们可以像数学函数一样运行。每个静态方法是一系列语句，当调用静态方法时，这些语句将依次执行。

+   *定义静态方法。* *方法* 封装了一系列语句定义的计算。方法接受*参数*（给定数据类型的值）并计算某种数据类型的*返回值*或引起*副作用*。每个静态方法由*签名*和*主体*组成。

    > ![静态方法的解剖](img/bde2f4984f0c95d1d28a964988dde65e.png)

+   *调用静态方法。* 对静态方法的调用是其名称，后跟用逗号分隔的括号中指定参数值的表达式。当调用方法时，其参数变量将用调用中相应表达式的值初始化。`return`语句终止静态方法，将控制返回给调用者。如果静态方法要计算一个值，那么该值必须在`return`语句中指定。

+   *方法的属性。* Java 方法具有以下特点：

    +   *参数按值传递。* 调用函数时，参数值会被完全评估，并且生成的值会*复制*到参数变量中。这被称为*按值传递*。数组（和其他对象）引用也是按值传递的：方法无法更改引用，但可以更改数组中的条目（或对象的值）。

    +   *方法名可以重载。* 类中的方法可以具有相同的名称，只要它们具有不同的签名。这个特性被称为*重载*。

    +   *方法具有单个返回值，但可能有多个返回语句。* Java 方法只能提供一个返回值。一旦到达第一个`return`语句，控制就会返回到调用程序。

    +   *方法可能具有副作用。* 方法可以使用关键字`void`作为其返回类型，以指示它没有返回值并产生副作用（消耗输入，产生输出，更改数组中的条目，或以其他方式更改系统的状态）。

+   *递归。* 递归方法是一种直接或间接调用自身的方法。在开发递归程序时有三个重要的经验法则：

    +   递归有一个*基本情况*。

    +   递归调用必须处理在某种意义上*更小*的子问题，以便递归调用收敛到基本情况。

    +   递归调用不应处理*重叠*的子问题。

+   *基本编程模型。* 一组静态方法的库是在 Java 类中定义的一组静态方法。Java 编程的基本模型是通过创建一组静态方法的库来解决特定的计算任务，其中一个方法被命名为`main()`。

+   *模块化编程。* 静态方法库使*模块化编程*成为可能，其中一个库中的静态方法可以调用其他库中定义的静态方法。这种方法有许多重要的优点。

    +   使用合理大小的模块进行工作

    +   共享和重用代码，而无需重新实现它

    +   替换改进的实现

    +   为解决编程问题开发适当的抽象模型

    +   本地化调试

+   *单元测试。* Java 编程中的最佳实践是在每个静态方法库中包含一个`main()`，用于测试库中的方法。

+   *外部库。* 我们使用来自三种不同类型的库的静态方法，每种库都需要（略有）不同的代码重用程序。

    +   `java.lang`中的标准系统库，包括`java.lang.Math`，`java.lang.Integer`和`java.lang.Double`。这些库在 Java 中始终可用。

    +   导入的系统库，如`java.util.Arrays`。程序开头需要一个`import`语句来使用这些库。

    +   本书中的库。按照这些说明添加 algs4.jar 到您的 Java 类路径。

    要从另一个库调用方法，我们在每次调用时在方法名前加上库名：`Math.sqrt()`，`Arrays.sort()`，`BinarySearch.rank()`和`StdIn.readInt()`。

* * *

## API。

+   *Java 库*。

+   *我们的标准库*。

+   *您自己的库*。

## 字符串。

> ![Java 的字符串数据类型](img/0cfe23791991f8d0600ec8ea8afdc269.png)

+   *连接*。

+   *转换*。

+   *自动转换*。

+   *命令行参数*。

## 输入和输出。

+   *命令和参数*。

    > ![命令的解剖](img/d935a2aa340362794deb522b3b29792c.png)

+   *标准输出。*

+   *格式化输出。*

    > ![printf 格式约定](img/f29c890587ef193bd05a6a17b35f95ab.png)

+   *标准输入。*

+   *重定向和管道。*

    > ![从命令行重定向和管道](img/81ea2418a373b920fa16ca0127c7f08b.png)

+   *从文件中输入和输出。*

+   *标准绘图。*

## 二分查找。

下面是一个完整的 Java 程序 BinarySearch.java，演示了我们编程模型的许多基本特性。它实现了一种称为*二分查找*的经典算法，并对其进行了*白名单过滤*应用的测试。![二分查找的解剖](img/8a70c20685ad1439fb1969bf61ad5075.png)静态方法`rank()`接受一个整数键和一个*排序的*`int`值数组作为参数，并在数组中返回键的索引，否则返回-1。它通过维护变量`lo`和`hi`来完成这个任务，使得如果键在`a[lo..hi]`中，则进入一个循环，测试间隔中的中间条目（在��引`mid`处）。如果键等于`a[mid]`，则返回值为`mid`；否则，该方法将间隔大小减半，如果键小于`a[mid]`，则查看左半部分，如果键大于`a[mid]`，则查看右半部分。当找到键或间隔为空时，该过程终止。![有序数组中的二分查找](img/32c264b93d2ae14592d880bbf67cfbba.png)

+   *开发客户端。*

+   *白名单。* 在测试中，我们使用样本文件 tinyAllowlist.txt，tinyText.txt，largeAllowlist.txt 和 largeText.txt。

+   *性能。*

* * *

## 输入和输出库。

这是我们在整本教材以及更多领域中使用的输入和输出库列表。

> | **程序** | **描述 / JAVADOC** |
> | --- | --- |
> | [StdIn.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/StdIn.java.html "从标准输入读取数字和文本") | [从标准输入读取数字和文本](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/StdIn.html "从标准输入读取数字和文本") |
> | [StdOut.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/StdOut.java.html "将数字和文本写入标准输出") | [将数字和文本写入标准输出](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/StdOut.html "将数字和文本写入标准输出") |
> | [StdDraw.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/StdDraw.java.html "在窗口中绘制几何形状") | [在窗口中绘制几何形状](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/StdDraw.html "在窗口中绘制几何形状") |
> | [StdAudio.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/StdAudio.java.html "创建、播放和操作声音") | [创建、播放和操作声音](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/StdAudio.html "创建、播放和操作声音") |
> | [StdRandom.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/StdRandom.java.html "生成随机数") | [生成随机数](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/StdRandom.html "生成随机数") |
> | [StdStats.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/StdStats.java.html "计算统计数据") | [计算统计数据](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/StdStats.html "计算统计数据") |
> | [StdArrayIO.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/StdArrayIO.java.html "读取和写入 1D 和 2D 数组") | [读取和写入 1D 和 2D 数组](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/StdArrayIO.html "读取和写入 1D 和 2D 数组") |
> | [In.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/In.java.html "从文件和 URL 读取数字和文本") | [从文件和 URL 读取数字和文本](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/In.html "从文件和 URL 读取数字和文本") |
> | [Out.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/Out.java.html "将数字和文本写入文件") | [将数字和文本写入文件](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/Out.html "将数字和文本写入文件") |
> | [Draw.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/Draw.java.html "绘制几何形状") | [绘制几何形状](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/Draw.html "绘制几何形状") |
> | [DrawListener.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/DrawListener.java.html "在 Draw 中支持键盘和鼠标事件") | [在 Draw 中支持键盘和鼠标事件](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/DrawListener.html "在 Draw 中支持键盘和鼠标事件") |
> | [Picture.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/Picture.java.html "处理数字图像") | [处理数字图像](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/Picture.html "处理数字图像") |
> | [Stopwatch.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/Stopwatch.java.html "测量运行时间") | [测量运行时间](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/Stopwatch.html "测量运行时间") |
> | [BinaryStdIn.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/BinaryStdIn.java.html "从标准输入读取位") | [从标准输入读取位](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/BinaryStdIn.html "从标准输入读取位") |
> | [BinaryStdOut.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/BinaryStdOut.java.html "将位写入标准输出") | [将位写入标准输出](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/BinaryStdOut.html "将位写入标准输出") |
> | [BinaryIn.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/BinaryIn.java.html "从文件和 URL 读取位") | [从文件和 URL 读取位](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/BinaryIn.html "从文件和 URL 读取位") |
> | [BinaryOut.java](https://algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/BinaryOut.java.html "将位写入文件") | [将位写入文件](https://algs4.cs.princeton.edu/code/javadoc/edu/princeton/cs/algs4/BinaryOut.html "将位写入文件") |

我们简要描述输入和输出库，并包含一个示例客户端。

## 标准输入和标准输出。

StdIn.java 和 StdOut.java 是用于从标准输入读取数字和文本并将数字和文本打印到标准输出的库。我们的版本比相应的 Java 版本具有更简单的接口（并提供一些技术改进）。RandomSeq.java 生成给定范围内的随机数。Average.java 从标准输入读取一系列实数，并在标准输出上打印它们的平均值。

```
% java Average
10.0 5.0 6.0 3.0 7.0 32.0
3.14 6.67 17.71
<Ctrl-d>
Average is 10.05777777777778

```

In.java 和 Out.java 是支持多个输入和输出流的面向对象版本，包括从文件或 URL 读取和写入文件。

## 标准绘图。

StdDraw.java 是一个易于使用的库，用于绘制几何形状，如点、线和圆。RightTriangle.java 绘制一个直角三角形和一个外接圆。

Draw.java 是支持在多个窗口中绘图的面向对象版本。

## 标准音频。

StdAudio.java 是一个易于使用的合成声音库。Tone.java 从命令行读取频率和持续时间，并为给定持续时间的给定频率声音化正弦波。

```
% java Tone 440.0 3.0

```

## 图像处理。

Picture.java 是一个易于使用的图像处理库。Scale.java 接受图片文件的名称和两个整数（宽度 w 和高度 h）作为命令行参数，并将图像缩放到 w-by-h。

|

&#124; **`% java Scale mandrill.jpg 298 298`** &#124;

![298-by-298](img/95f0af44f405ffe3f2f65e93dbf94a50.png) |

&#124; **`% java Scale mandrill.jpg 200 200`** &#124;

![200-by-400](img/58240b8d5e8f790d49c559f35b756231.png) |

&#124; **`% java Scale mandrill.jpg 200 400`** &#124;

![200-by-400](img/9824aa1013179a5af4c823fea58c53e9.png) |

#### 问答

**Q.** 使用一个好的洗牌算法有多重要？

**A.** 这里有一个[有趣的轶事](http://www.datamation.com/entdev/article.php/616221/How-We-Learned-to-Cheat-at-Online-Poker-A-Study-in-Software-Security.htm)，讲述了当你没有正确执行时会发生什么（尤其是在你的业务是在线扑克时！）。如果你经营一个在线赌场，这里是洗牌一副牌的推荐方法：（i）使用一个密码学安全的伪随机数生成器，（ii）为每张卡分配一个随机的 64 位数字，（iii）根据它们的数字对卡进行排序。

#### 创意问题

1.  **二项分布。** 估计方法调用`binomial1(100, 50, .25)`在 Binomial.java 中将使用的递归调用次数。开发一个基于在数组中保存计算值的更好的实现。

#### 网络练习

1.  **Sattolo's algorithm.** 编写一个程序 Sattolo.java，使用[Sattolo's algorithm](http://en.wikipedia.org/wiki/Fisher–Yates_shuffle#Sattolo.27s_algorithm)生成一个长度为 N 的均匀分布循环。

1.  **Wget.** 编写一个程序 Wget.java，从命令行指定的 URL 读取数据并将其保存在同名文件中。

    ```
    % java Wget http://introcs.cs.princeton.edu/data/codes.csv
    % more codes.csv
    United States,USA,00
    Alabama,AL,01
    Alaska,AK,02
    ...

    ```

1.  **直角三角形。** 编写一个客户端 RightTriangle.java，绘制一个直角三角形和一个外接圆。

    > `  % java RightTriangle`
    > 
    > ![直角三角形和外接圆](img/2f2d6b2b677f636648bcf37e13aa157b.png)

1.  **弹跳球。** 编写一个程序 BouncingBall.java，演示弹跳球的运动。

    > <BouncingBall.mov>
    > 
    > 您的浏览器不支持视频标记。
