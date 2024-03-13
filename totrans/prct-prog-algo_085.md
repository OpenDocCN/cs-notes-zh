# 1.2   数据抽象

> 原文：[`algs4.cs.princeton.edu/12oop`](https://algs4.cs.princeton.edu/12oop)

## 面向对象编程。

Java 编程主要基于构建数据类型。这种编程风格被称为*面向对象编程*，因为它围绕着*对象*的概念展开，一个持有数据类型值的实体。使用 Java 的原始类型，我们主要限于操作数字的程序，但使用引用类型，我们可以编写操作字符串、图片、声音或 Java 标准库或我们的书站上提供的数百种其他抽象的程序。比预定义数据类型库更重要的是，Java 编程中可用的数据类型范围是开放的，因为您可以定义自己的数据类型。

+   *数据类型。* *数据类型* 是一组值和对这些值的一组操作。

+   *抽象数据类型。* *抽象数据类型* 是一个其内部表示对客户端隐藏的数据类型。

+   *对象。* *对象* 是一个可以取一个数据类型值的实体。对象具有三个基本属性：对象的*状态*是来自其数据类型的值；对象的*标识*区分一个对象与另一个对象；对象的*行为*是数据类型操作的效果。在 Java 中，*引用*是访问对象的机制。

+   *应用程序编程接口（API）。* 为了指定抽象数据类型的行为，我们使用一个*应用程序编程接口*（API），它是一个*构造函数*和*实例方法*（操作）的列表，每个操作的效果都有一个非正式描述，就像这个`Counter`的 API 一样：![Counter 的 API](img/344b9a06b18c58fbb94d74ac0211ac3f.png)

+   *客户端。* 客户端是使用数据类型的程序。

+   *实现。* 实现是实现 API 中指定的数据类型的代码。

## 使用抽象数据类型。

客户端不需要知道数据类型是如何实现的才能使用它。

+   *创建对象。* 每个数据类型值都存储在一个对象中。要创建（或*实例化*)一个单独的对象，我们通过使用关键字`new`来调用一个*构造函数*。每当客户端使用`new`时，系统会为对象分配内存空间，初始化其值，并返回对对象的引用。![构造函数](img/746f5c4141d5ccd9aa55cd809fe8618a.png)

+   *调用实例方法。* 实例方法的目的是操作数据类型的值。实例方法具有静态方法的所有属性：参数按值传递，方法名称可以重载，它们可能有返回值，并且可能会引起副作用。它们具有表征它们的附加属性：*每次调用都与一个对象关联*。![实例方法](img/78b0bb3e5e88a4b117f28dd57ebeb198.png)

+   *使用对象。* 声明为我们提供了在代码中可以使用的对象的变量名。要使用给定的数据类型，我们：

    +   声明类型的变量，用于引用对象

    +   使用关键字`new`来调用创建该类型对象的构造函数

    +   使用对象名称来调用实例方法，可以作为语句或在表达式中

    例如，Flips.java 是一个 Counter.java 客户端，它接受一个命令行参数`T`并模拟`T`次硬币翻转。

+   *赋值语句。* 具有引用类型的赋值语句会创建引用的副本（而不会创建新对象）��这种情况被称为*别名*：两个变量都引用同一个对象。别名是 Java 程序中常见的错误来源，如下例所示：

    ```
    Counter c1 = new Counter("ones");
    c1.increment();
    Counter c2 = c1;
    c2.increment(); 
    StdOut.println(c1);

    ```

    该代码打印字符串`"2 ones"`。

+   *对象作为参数。* 您可以将对象作为参数传递给方法。Java 将调用程序中的参数值的*副本*传递给方法。这种安排称为*按值传递*。如果您将一个指向`Counter`类型对象的引用传递给方法，Java 将传递该引用的副本。因此，该方法无法更改原始引用（使其指向不同的`Counter`），但可以更改对象的值，例如通过使用引用调用`increment()`。

+   *对象作为返回值。* 您还可以将对象作为方法的返回值。该方法可能会返回作为参数传递给它的对象，就像 FlipsMax.java 中的情况，或者它可能创建一个对象并返回对其的引用。这种能力很重要，因为 Java 方法只允许一个返回值——使用对象使我们能够编写代码，实际上返回多个值。

+   *数组是对象。* 在 Java 中，任何非原始类型的值都是对象。特别是，数组是对象。与字符串一样，对数组有特殊的语言支持：声明、初始化和索引。与任何其他对象一样，当我们将数组传递给方法或在赋值语句的右侧使用数组变量时，我们只是复制数组引用，而不是数组本身的副本。

+   *对象数组。* 数组条目可以是任何类型。当我们创建一个对象数组时，需要分两步进行：使用数组构造函数的括号语法创建数组；为数组中的每个对象创建一个标准构造函数。Rolls.java 模拟掷骰子，使用`Counter`对象数组来跟踪每个可能值出现的次数。

## 抽象数据类型的示例。

+   *几何对象。* 面向对象编程的一个自然示例是为几何对象设计数据类型。

    +   Point2D.java 是用于平面上的点的数据类型。

    +   Interval1D.java 是用于一维区间的数据类型。

    +   Interval2D.java 是用于二维区间的数据类型。

+   *信息处理。* 抽象数据类型提供了一个自然的机制来组织和处理信息。信息

    +   Date.java 是一个表示日期、月份和年份的���据类型。

    +   Transaction.java 是一个表示客户、日期和金额的数据类型。

+   *累加器。* Accumulator.java 定义了一个 ADT，为客户提供了维护数据值的运行平均值的能力。例如，我们在本书中经常使用这种数据类型来处理实验结果。VisualAccumulator.java 是一个增强版本，还会绘制数据（灰色）和运行平均值（红色）。

+   *字符串。* Java 的`String`数据类型是一个重要且有用的 ADT。`String`是`char`值的索引序列。`String`有几十种实例方法，包括以下内容：![string api](img/5fc6fdf8cebc832d05976fd4bfa5a8d1.png)`String`有特殊的语言支持用于初始化和连接：我们可以使用字符串字面量来创建和初始化字符串，而不是使用构造函数；我们可以使用`+`运算符来连接字符串，而不是调用`concat()`方法。

+   *输入和输出再探讨。* 第 1.1 节的`StdIn`、`StdOut`和`StdDraw`库的一个缺点是它们限制了我们在任何给定程序中只能使用一个输入文件、一个输出文件和一个绘图。通过面向对象编程，我们可以定义类似的机制，允许我们在一个程序中使用*多个*输入流、输出流和绘图。具体来说，我们的标准库包括支持多个输入和输出流的数据类型 In.java、Out.java 和 Draw.java。

## 实现抽象数据类型。

我们使用 Java 类来实现 ADTs，将代码放在与类同名的文件中，后面跟着.java 扩展名。文件中的第一条语句声明*实例变量*，定义数据类型的值。在实例变量之后是*构造函数*和*实例方法*，实现对数据类型值的操作。

+   *实例变量.* 为了定义数据类型的值（每个对象的状态），我们声明实例变量的方式与声明局部变量的方式非常相似。每个实例变量对应着许多值（对应数据类型的每个实例对象）。每个声明都由*可见性修饰符*修饰。在 ADT 实现中，我们使用`private`，使用 Java 语言机制来强制执行 ADT 的表示应该对客户端隐藏，还可以使用`final`，如果该值在初始化后不会更改。

+   *构造函数.* 构造函数建立对象的标识并初始化实例变量。构造函数总是与类同名。我们可以重载名称并具有具有不同签名的多个构造函数，就像方法一样。如果没有定义其他构造函数，则隐式存在一个默认无参数构造函数，没有参数，并将实例值初始化为默认值。原始数值类型的默认值为 0，`boolean`为`false`，`null`。

+   *实例方法.* 实例方法指定数据类型的操作。每个实例方法都有一个返回类型，一个*签名*（指定其名称和参数变量的类型和名称），以及一个*主体*（包括一系列语句，包括一个*返回*语句，将返回类型的值提供给客户端）。当客户端调用方法时，参数值（如果有）将用客户端值初始化，语句将执行直到计算出返回值，并将该值返回给客户端。实例方法可以是*public*（在 API 中指定）或*private*（用于组织计算且不可用于客户端）。![类的解剖图](img/f2ba62b6f6a93c8b5b768867b234b4a9.png)

+   *作用域.* 实例方法使用三种类型的变量：参数变量，局部变量和实例变量。前两者与静态方法相同：参数变量在方法签名中指定，并在调用方法时用客户端值初始化，局部变量在方法主体内声明和初始化。参数变量的作用域是整个方法；局部变量的作用域是定义它们的块中的后续语句。实例变量保存类中对象的数据类型值，其作用域是整个类（在存在歧义时，可以使用`this`前缀来标识实例变量）。![作用域](img/e367d827323d269b2efc6b128f5e9c3d.png)

## 设计抽象数据类型。

我们将与设计数据类型相关的重要信息放在一个地方供参考，并为本书中的实现奠定基础。

+   *封装.* 面向对象编程的一个特点是它使我们能够将数据类型封装在其实现中，以促进客户端和数据类型实现的分开开发。封装实现了模块化编程。

+   *设计 APIs.* 在构建现代软件中最重要且最具挑战性的步骤之一是设计 APIs。理想情况下，API 将清晰地阐明所有可能输入的行为，包括副作用，然后我们将有软件来检查实现是否符合规范。不幸的是，理论计算机科学中的一个基本结果，即*规范问题*，意味着这个目标实际上是不可能实现的。在设计 API 时存在许多潜在的陷阱：

    +   过于难以实现，使得开发变得困难或不可能。

    +   过于难以使用，导致复杂的客户端代码。

    +   过于狭窄，省略了客户端需要的方法。

    +   过于广泛，包含许多任何客户端都不需要的方法。

    +   过于一般，提供没有用的抽象。

    +   过于具体，提供的抽象太过模糊，无用。

    +   过于依赖特定表示，因此不能使客户端代码摆脱表示的细节。

    总之，为客户端提供他们需要的方法，而不是其他方法。

+   *算法和 ADT.* 数据抽象自然适合于算法的研究，因为它帮助我们提供一个框架，可以精确指定算法需要完成的任务以及客户端如何使用算法。例如，我们在本章开头的白名单示例自然地被视为 ADT 客户端，基于以下操作：

    +   从给定值数组构造一个 SET。

    +   确定给定值是否在集合中。

    这些操作封装在 StaticSETofInts.java 和 Allowlist.java 中。

+   *接口继承.* Java 提供了语言支持来定义对象之间的关系，称为*继承*。我们考虑的第一种继承机制称为*子类型化*，它允许我们通过在*接口*中指定一组每个实现类必须包含的共同方法来指定否则无关的类之间的关系。我们使用接口继承进行*比较*和*迭代*。![本书中使用的 Java 接口](img/96a2e8b80288d8f2b26f4203a0afa1fe.png)

+   *实现继承.* Java 还支持另一种继承机制，称为*子类化*，这是一种强大的技术，使程序员能够在不从头开始重写整个类的情况下更改行为和添加功能。这个想法是定义一个��承实例方法和实例变量的新类（*子类*），从另一个类（*超类*）继承。我们在本书中避免使用子类化，因为它通常违反封装。这种方法的某些残留物内置在 Java 中，因此不可避免：具体来说，每个类都是[Object](http://download.oracle.com/javase/6/docs/api/java/lang/Object.html)的子类。![本书中使用的 Object 继承方法](img/4207c9ba2f346a59ed043551cf3f3bb6.png)

+   *字符串转换.* 每种 Java 类型都从[Object](http://download.oracle.com/javase/6/docs/api/java/lang/Object.html)继承了`toString()`。这种约定是 Java 自动将连接运算符`+`的一个操作数转换为`String`的基础，只要另一个操作数是`String`。我们通常包含重写默认`toString()`的实现，如 Date.java 和 Transaction.java。

+   *包装类型.* Java 提供了内置的引用类型，称为*包装类型*，每种原始类型对应一个：

    | **基本类型** | **包装类型** |
    | --- | --- |
    | `boolean` | [Boolean](http://download.oracle.com/javase/6/docs/api/java/lang/Boolean.html) |
    | `byte` | [Byte](http://download.oracle.com/javase/6/docs/api/java/lang/Byte.html) |
    | `char` | [Character](http://download.oracle.com/javase/6/docs/api/java/lang/Character.html) |
    | `double` | [Double](http://download.oracle.com/javase/6/docs/api/java/lang/Double.html) |
    | `float` | [Float](http://download.oracle.com/javase/6/docs/api/java/lang/Float.html) |
    | `int` | [Integer](http://download.oracle.com/javase/6/docs/api/java/lang/Integer.html) |
    | `long` | [Long](http://download.oracle.com/javase/6/docs/api/java/lang/Long.html) |
    | `short` | [Short](http://download.oracle.com/javase/6/docs/api/java/lang/Short.html) |

    Java 在必要时会自动将基本类型转换为包装类型（*autoboxing*）并在需要时转换回来（*auto-unboxing*）。

+   *相等性.* 两个对象相等意味着什么？如果我们用 `(a == b)` 测试相等性，其中 `a` 和 `b` 是相同类型的引用变量，我们正在测试它们是否具有相同的标识：是否*引用*相等。典型的客户端更希望能够测试*数据类型值*（对象状态）是否相同。每个 Java 类型都从 [Object](http://download.oracle.com/javase/6/docs/api/java/lang/Object.html) 继承了 `equals()` 方法。Java 为标准类型（如 `Integer`、`Double` 和 `String`）以及更复杂类型（如 [java.io.File](http://download.oracle.com/javase/6/docs/api/java/io/File.html) 和 [java.net.URL](http://download.oracle.com/javase/6/docs/api/java/net/URL.html)）提供了自然的实现。当我们定义自己的数据类型时，我们需要重写 `equals()`。Java 的约定是 `equals()` 必须是一个*等价关系*：

    +   *自反性*: `x.equals(x)` 成立。

    +   *对称性*: `x.equals(y)` 成立当且仅当 `y.equals(x)` 成立。

    +   *传递性*: 如果 `x.equals(y)` 和 `y.equals(z)` 成立，则 `x.equals(z)` 也成立。

    此外，它必须以 `Object` 作为参数，并满足以下属性。

    +   *一致性*: 多次调用 `x.equals(y)` 一致地返回相同的值，前提是没有修改任何对象。

    +   *非空*: `x.equals(null)` 返回 false。

    遵循这些 Java 约定可能会有些棘手，就像 Date.java 和 Transaction.java 中所示的那样。

+   *内存管理.* Java 最重要的特性之一是其能够*自动*管理内存。当一个对象不再被引用时，它被称为*孤立的*。Java 跟踪孤立的对象，并将它们使用的内存返回给一个空闲内存池。以这种方式回收内存被称为*垃圾回收*。

+   *不可变性.* 一个*不可变*的数据类型具有一个特性，即对象的值在构造后永远不会改变。相比之下，*可变*的数据类型操作旨在改变的对象值。Java 为帮助强制实现不可变性提供了 `final` 修饰符。当你声明一个变量为 `final` 时，你承诺只能在初始化程序或构造函数中为其分配一个值。试图修改 `final` 变量的值的代码会导致编译时错误。

    Vector.java 是一个用于向量的不可变数据类型。为了保证不可变性，它*防御性地复制*了可变的构造函数参数。

+   *异常和错误*是处理我们无法控制的意外错误的破坏性事件。我们已经遇到了以下异常和错误：

    +   [ArithmeticException](http://download.oracle.com/javase/6/docs/api/java/lang/ArithmeticException.html)。当发生异常的算术条件（例如整数除以零）时抛出。

    +   [ArrayIndexOutOfBoundsException](http://download.oracle.com/javase/6/docs/api/java/lang/ArrayIndexOutOfBoundsException.html)。当使用非法索引访问数组时抛出。

    +   [NullPointerException](http://download.oracle.com/javase/6/docs/api/java/lang/NullPointerException.html)。当需要对象而使用 `null` 时抛出。

    +   [OutOfMemoryError](http://download.oracle.com/javase/6/docs/api/java/lang/OutOfMemoryError.html)。当 Java 虚拟机无法分配对象因为内存不足时抛出。

    +   [StackOverflowError](http://download.oracle.com/javase/6/docs/api/java/lang/StackOverflowError.html)。当递归方法递归太深时抛出。

    你也可以创建自己的异常。最简单的一种是终止程序执行并打印错误消息的 [RuntimeException](http://download.oracle.com/javase/6/docs/api/java/lang/RuntimeException.html)。

    ```
    throw new RuntimeException("Error message here.");

    ```

+   *断言* 是在我们开发的代码中验证我们所做假设的布尔表达式。如果表达式为 false，程序将终止并报告错误消息。例如，假设您有一个计算值，可能用于���引到数组中。如果这个值为负，它将在稍后引起`ArrayIndexOutOfBoundsException`。但如果您编写代码

    ```
    assert index >= 0; 

    ```

    您可以确定发生错误的地方。默认情况下，断言是禁用的。您可以通过使用`-enableassertions`标志（简写为`-ea`）从命令行启用它们。断言用于调试：您的程序不应依赖断言进行正常操作，因为它们可能被禁用。

#### Q + A.

Q. Java 中是否有真正的不可变类？

如果使用反射，可以访问任何类的`private`字段并更改它们。程序 MutableString.java 演示了如何改变一个`String`。程序 MutableInteger.java 证明了即使实例变量是 final，这也是正确的。

#### 练习

1.  编写一个 Point2D.java 客户端，从命令行获取一个整数值 N，在单位正方形内生成 N 个随机点，并计算最近一对点之间的距离。

1.  以下代码片段打印什么？

    ```
    String string1 = "hello";
    String string2 = string1;
    string1 = "world";
    StdOut.println(string1);
    StdOut.println(string2);

    ```

    *解决方案：*

    ```
    world
    hello

    ```

1.  如果一个字符串 s 是字符串 t 的*circular rotation*，那么当字符被任意数量的位置循环移位时，它们匹配；例如，ACTGACG 是 TGACGAC 的循环移位，反之亦然。检测这种条件在基因组序列研究中很重要。编写一个程序，检查两个给定的字符串 s 和 t 是否彼此的循环移位。

    *解决方案：* `(s.length() == t.length()) && (s.concat(s).indexOf(t) >= 0)`

1.  以下递归函数返回什么？

    ```
    public static String mystery(String s) {
        int N = s.length();
        if (N <= 1) return s;
        String a = s.substring(0, N/2);
        String b = s.substring(N/2, N);
        return mystery(b) + mystery(a);
    }

    ```

    *解决方案：* 字符串的反转。

1.  使用我们的 Date.java 的实现作为模型，开发一个 Transaction.java 的实现。

1.  使用我们在 Date.java 中的`equals()`的实现作为模型，为 Transaction.java 开发一个`equals()`的实现。

#### 创意问题

1.  **有理数。** 为有理数实现一个不可变的数据类型 Rational.java，支持加法、减法、乘法和除法。![有理数的 API](img/326bdf1a1c3ca8a918594ae536bb4576.png)您不必担心溢出测试，但使用两个表示分子和分母的`long`值作为实例变量，以限制溢出的可能性。使用欧几里得算法确保分子和分母永远没有任何公因数。包括一个测试客户端，测试所有方法。

1.  **累加器的样本方差。** 验证以下代码，为 Accumulator.java 添加`var()`和`stddev()`方法，计算作为`addDataValue()`参数呈现的数字的均值、样本方差和样本标准差。

    *参考：* 这里有一个很好的[解释](http://www.johndcook.com/standard_deviation.html)这种一次性方法，最早由 Welford 在 1962 年发现。这种方法可以应用于计算偏度、峰度、回归系数和皮尔逊相关系数。

1.  **解析。** 为您的 Date.java 和 Transaction.java 实现开发解析构造函数，使用下表中给出的格式的单个`String`参数指定初始化值。![Date 和 Transaction 的解析](img/95c0298309fe07196f4bda8469fa7ba3.png)
