# 3.3   设计数据类型

> 原文：[`introcs.cs.princeton.edu/java/33design`](https://introcs.cs.princeton.edu/java/33design)

在本节中，我们讨论*封装*、*不可变性*和*继承*，特别关注这些机制在*数据类型设计*中的应用，以实现模块化编程，促进调试，并编写清晰和正确的代码。

## 封装。

通过隐藏信息将客户端与实现分离的过程被称为*封装*。我们使用封装来实现模块化编程��促进调试，并澄清程序代码。

+   *复数再探.* ![极坐标表示](img/0747bc2d9355e592411282422db02eaa.png) Complex.java 与 Complex.java 具有相同的 API，只是它使用*极坐标* \(r (\cos \theta + i \sin \theta)\) 而不是*笛卡尔坐标* \(x + iy\) 表示复数。封装的思想是我们可以将其中一个程序替换为另一个而不改变客户端代码。

+   *私有.* 当你将一个实例变量（或方法）声明为`private`时，你使得任何客户端（另一个类中的代码）无法直接访问该实例变量（或方法）。这有助于强制封装。

+   *限制错误的潜力.* 封装还帮助程序员确保他们的代码按预期运行。要理解这个问题，考虑 Counter.java，它封装了一个单个整数，并确保唯一可以对该整数执行的操作是*加 1*。

    > ![计数器 API](img/425bb62facc3778099b32924bb7ff3e3.png)

    没有`private`修饰符，客户端可以编写如下代码：

    ```
    Counter counter = new Counter("Volusia");
    counter.count = -16022;

    ```

    使用`private`修饰符，像这样的代码将无法编译。

## 不可变性。

![不可变和可变数据类型](img/d9ca53c7d0d086d77e7b3b10ed75ceff.png) 如果一个数据类型的对象一旦创建就不能改变其数据类型值，则该对象是*不可变*的。一个*不可变数据类型*是其中所有对象都是不可变的数据类型。

+   *不可变性的优势.* 我们可以在赋值语句中使用不可变对象（或作为方法的参数和返回值）而不必担心它们的值会改变。这使得不可变类型更容易推理和调试。

+   *不可变性的代价.* 不可变性的主要缺点是必须为每个值创建一个新对象。

+   *最终.* 当你将一个实例变量声明为`final`时，你承诺只分配一次值。这有助于强制不可变性。

+   *引用类型.* `final` 访问修饰符不能保证可变类型的实例变量是不可变的。在这种情况下，你必须进行*防御性拷贝*。

## 空间向量。

![向量](img/0032311a95197dd29f29960fa72a53b2.png)  一个*空间向量*是一个具有*大小*和*方向*的抽象实体。 一系列*n*个实数足以指定*n*维空间中的一个向量。我们使用粗体字母如\( \boldsymbol{x} \)表示向量\( ( x_0, x_1, \; \ldots, \; x_{n-1}) \)。

+   *API.* 向量的基本操作是将两个向量相加，将一个向量乘以一个标量，计算两个向量的点积，以及计算大小和方向，如下所示：

    +   *加法*: \( \boldsymbol{x} + \boldsymbol{y} = ( x_0 + y_0, x_1 + y_1, \; \ldots, \; x_{n-1} + y_{n-1}) \)

    +   *向量缩放*: \( \alpha \boldsymbol{x} = (\alpha x_0, \alpha x_1, \; \ldots, \; \alpha x_{n-1}) \)

    +   *点积* \( \boldsymbol{x} \cdot \boldsymbol{y} = x_0y_0 + x_1y_1 + \, \ldots \, + x_{n-1}y_{n-1} \)

    +   *大小*: \( \left | \boldsymbol{x} \right | = \sqrt{x_0² + x_1² + \, \ldots \, + x_{n-1}²} \)

    +   *方向*: \( \boldsymbol{x} \,/\, \left | \boldsymbol{x} \right | = (x_0 \,/\, \left | \boldsymbol{x} \right |, x_1 \,/\, \left | \boldsymbol{x} \right |, \; \ldots, \; x_{n-1} \,/\, \left | \boldsymbol{x} \right |) \)

    这些基本的数学定义立即导致了一个 API：

    > ![向量 API](img/ccb39170a5f0e8c2263d0481300effab.png)

+   *实现。*Vector.java 是一个不可变的数据类型，实现了这个 API。在内部，它使用长度为*n*的数组来存储笛卡尔坐标。

+   *this 引用。*在实例方法（或构造函数）中，`this`关键字为我们提供了一种引用调用的对象的方式。例如，Vector 中的`magnitude()`方法以两种方式使用`this`关键字：调用`dot()`方法和作为`dot()`方法的参数。

    ```
    // return the magnitude of this Vector
    public double magnitude() {
        return Math.sqrt(this.dot(this));
    }

    ```

## 接口继承（子类型化）。

Java 提供了`interface`构造用于声明否则无关的类之间的关系，通过指定每个实现类必须包含的一组公共方法。接口使我们能够编写客户端程序，可以通过调用接口的公共方法来操作不同类型的对象。

+   *定义接口。*Function.java 为单变量实值函数定义了一个接口。

    ```
    public interface Function {
        public abstract double evaluate (double x);
    }

    ```

    接口的主体包含一个*抽象方法*列表。抽象方法是声明但不包含任何实现代码的方法；它只包含方法签名。您必须将 Java 接口保存在与接口名称匹配的文件中，扩展名为`.java`。

+   *实现接口。*要编写一个实现接口的类，您必须做两件事。

    +   在类声明中包含一个`implements`子句，其中包含接口的名称。

    +   实现接口中的每个抽象方法。

    例如，Square.java 和 GaussianPDF.java 实现了`Function`接口。

+   *使用接口。*接口是一个引用类型。因此，您可以声明变量的类型为接口的名称。当您这样做时，分配给该变量的任何对象必须是实现接口的类的实例。例如，类型为`Function`的变量可以存储类型为`Square`或`GaussianPDF`的对象。

    ```
    Function f1 = new Square();
    Function f2 = new GaussianPDF();
    Function f3 = new Complex(1.0, 2.0);   // compile-time error

    ```

    当接口类型的变量调用接口中声明的方法时，Java 知道调用哪个方法，因为它知道调用对象的类型。这种强大的编程机制称为*多态*或*动态分派*。

+   *绘制函数。*FunctionGraph.java 通过在*n*+1 个均匀间隔的点上对函数进行采样，在区间[*a*, *b*]中绘制实值函数*f*的图形。它适用于任何实现`Function`接口的足够平滑的函数`f`。

    > ![绘制函数图](img/6413348270fbdc0917bf7ac7889bcc4b.png)

+   *数值积分。*RectangleRule.java 使用*矩形法则*估计在区间(*a*, *b*)中的正实值函数*f*的积分。它适用于任何实现`Function`接口的足够平滑的函数`f`。

    > ![矩形法则](img/3244b4f0c7bf2b0e53736bdc61c0afc0.png)

+   *Lambda 表达式。*为了简化语法，Java 提供了一个强大的函数式编程特性，称为*lambda 表达式*。您应该将 lambda 表达式视为可以传递并稍后执行的代码块。在其最简单的形式中，lambda 表达式由三个元素组成：

    +   由逗号分隔的参数变量列表，括在括号中

    +   *lambda 运算符* `->`

    +   一个单一表达式，这是 lambda 表达式返回的值

    例如，以下 lambda 表达式实现了斜边函数：

    > ![lambda 表达式的解剖](img/9fd3e4ec1fb6072a7fbddb64ab41f0dc.png)

    我们主要使用 lambda 表达式作为实现*函数接口*（具有单个抽象方法的接口）的简洁方式。具体来说，您可以在需要函数接口对象的任何地方使用 lambda 表达式。例如，以下所有表达式都实现了 Function.java 接口：

    > ![函数接口](img/60babd1236056ffeb2c0b388240fec46.png)

    因此，您可以通过调用 `integrate(x -> x*x, 0, 10, 1000)` 来集成平方函数，而无需定义一个单独的`Square`类。

+   *内置接口.* Java 包含三个内置接口，我们将在本书后面考虑。

    +   接口[java.util.Comparable](https://docs.oracle.com/javase/8/docs/api/java/lang/Comparable.html)定义了一种比较同一类型对象的顺序，例如字符串的字母顺序或整数的升序。

    +   接口[java.util.Iterator](https://docs.oracle.com/javase/8/docs/api/java/util/Iterator.html)和[java.lang.Iterable](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html)使客户端能够在不依赖底层表示的情况下遍历集合中的项。

## 实现继承（子类化）。

Java 还支持另一种继承机制，称为*子类化*。其思想是定义一个新类（*子类*或*派生类*），从另一个类（*超类*或*基类*）继承实例变量（状态）和实例方法（行为），实现代码重用。通常，子类会重新定义或*覆盖*超类中的一些方法。例如，Java 为 GUI 组件提供了一个复杂的继承层次结构：

> ![Java GUI 元素的继承层次结构](img/79cf04ee6b9dff0a5b4b6be15a4f5766.png)

在这本书中，我们避免使用子类化，因为它违反了封装性和不可变性（例如，[脆弱基类问题](https://en.wikipedia.org/wiki/Fragile_base_class)和[圆-椭圆问题](https://en.wikipedia.org/wiki/Circle-ellipse_problem)）。

+   *Java 的 Object 超类.* Java 中内置了一些子类化的遗留问题，因此不可避免。具体来说，每个类都是[java.lang.Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html)的子类。在 Java 编程中，您经常会重写其中一个或多个继承的方法：

    > ![对象 API](img/df6e17af8ade51966127aea05c279980.png)

+   *字符串转换.* 每个 Java 类都继承了[`toString()`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#toString--) 方法，因此任何客户端都可以为任何对象调用 `toString()`。这个约定是 Java 自动将字符串连接运算符 `+` 的一���操作数转换为字符串的基础，只要另一个操作数是字符串。

+   *引用相等性.* 如果我们用 `(x == y)` 测试相等性，其中 `x` 和 `y` 是对象引用，我们正在测试它们是否具有相同的标识：即*对象引用*是否相等。

+   *对象相等性.* ![重写 toString()、equals() 和 hashCode()](img/6c5cf9c2d17d3b8e2682ef5d49e46dbd.png) [`equals()`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#equals-java.lang.Object-) 方法的目的是测试两个*对象*是否相等（对应于相同的数据类型值）。它必须实现一个*等价关系*：

    +   自反性：`x.equals(x)` 为 `true`。

    +   对称性：当且仅当 `x.equals(y)` 为 `true` 时，`y.equals(x)` 也为 `true`。

    +   传递性：如果 `x.equals(y)` 为 `true` 且 `y.equals(z)` 为 `true`，则 `x.equals(z)` 为 `true`。

    此外，以下两个属性必须成立：

    +   多次调用 `x.equals(y)` 返回相同的真值，前提是在调用之间没有修改任何对象。

    +   `x.equals(null)` 返回 `false`。

    重写 `equals()` 方法是意外复杂的，因为它的参数可以是任何类型的对象引用（或 `null`）。

+   *哈希。* [`hashCode()`](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html#hashCode--)方法的目的是支持*哈希*，这是一种将对象映射到整数（称为*哈希码*）的基本操作。它必须满足以下两个属性：

    +   如果`x.equals(y)`为`true`，则`x.hashCode()`等于`y.hashCode()`。

    +   多次调用`x.hashCode()`返回相同的整数，前提是对象在调用之间没有被修改。

    通常，我们使用哈希码将对象`x`映射到一个小范围内的整数，比如在`0`和`m-1`之间，使用这个*哈希函数*：

    ```
    private int hash(Object x) {
        return Math.abs(x.hashCode() % m);
    }

    ```

    值不相等的对象可以具有相同的哈希函数值，但我们期望哈希函数将`n`个典型对象分成大致相等大小的`m`组。

+   *包装类型。* ![包装类型](img/31ae0730f9e7379357052b0abf192a65.png) `toString()`，`hashCode()`和`equals()`方法仅适用于引用类型，而不适用于基本类型。例如，如果`x`是`Integer`类型的变量，则表达式`x.hashCode()`有效，但如果是`int`类型则无效。在我们希望将基本类型的值表示为对象的情况下，Java 提供了内置的引用类型，称为*包装类型*，每个基本类型对应一个。

+   *自动装箱和拆箱。* Java 自动在包装类型和相应的基本类型之间进行转换，因此您可以编写如下代码：

    ```
    Integer x = 17;  // Autoboxing (int -> Integer)
    int a = x;       // Unboxing   (Integer -> int)

    ```

## 应用程序：数据挖掘。

我们考虑一个*数据挖掘*应用程序，其目标是为每个文档关联一个称为*草图*的向量，以便不同的文档具有不同的草图，而相似的文档具有相似的草图。我们的 API 将这个概念抽象成方法`similarTo()`，它是一个介于 0（不相似）和 1（相似）之间的实数。参数*k*和*d*控制草图的质量。

> ![草图 API](img/c6313d389eedbb7a12e46cddd6181d4e.png)

+   *计算草图。* ![DNA 的草图](img/2e814bb10b353352802ebe70fd3d1b07.png) Sketch.java 使用简单的频率计数方法来计算文本文档的草图。在其最简单的形式中，它计算文本中每个*k*-gram（长度为*k*的子字符串）出现的次数。我们使用的草图是由这些频率定义的向量的方向。

+   *哈希。* 对于 ASCII 文本字符串，每个字符有 128 个不同的可能值，因此有 128^(*k*)个可能的*k*-gram。为了提高效率，Sketch.java 使用*哈希*。也就是说，我们不是计算每个*k*-gram 出现的次数，而是将每个*k*-gram 哈希到 0 到*d*-1 之间的整数，并计算每个哈希值出现的次数。

+   *比较草图。* Sketch.java 使用*余弦相似度度量*比较两个草图：

    > \( x \cdot y = x_0y_0 + x_1y_1 + \; \ldots \; + x_{d-1}y_{d-1} \)

    它是一个介于 0 和 1 之间的实数。

+   *比较所有对。* CompareDocuments.java 打印输入列表中所有文档对的余弦相似度度量。

    > ![文本文档](img/fd4da740f9535894bda439b8bda97674.png)

## 契约式设计。

我们简要讨论了两种 Java 语言机制，使您能够在程序运行时验证对程序的假设 - 异常和断言。

+   *异常。* *异常*是程序运行时发生的中断事件，通常用于表示错误。所采取的行动称为*抛出异常*。Java 包括一个预定义异常的复杂继承层次结构，我们之前遇到过其中的几个。

    > ![Java 异常](img/67eb76023dce2c3e9939a903fa9e1e91.png)

    当它们对用户有帮助时，使用异常是一个好的实践。例如，在 Vector.java 中，如果要相加的两个向量具有不同的维度，我们应该在`plus()`中抛出一个异常：

    ```
    if (this.length() != that.length())
        throw new IllegalArgumentException("Dimensions disagree.");

    ```

+   *断言.* 一个*断言*是一个布尔表达式，你在程序执行的某个时刻确认为真。如果表达式为假，程序将抛出一个`AssertionError`，通常会终止程序并报告一个错误消息。例如，在 Counter.java 中，我们可以通过在`increment()`的最后一条语句中添加以下断言来检查计数器永远不会为负：

    ```
    assert count >= 0 : "Negative count detected in increment()";

    ```

    默认情况下，断言是禁用的，但您可以通过在命令行中使用`-enableassertions`标志（简写为`-ea`）来启用它们。断言仅用于调试；您的程序不应依赖断言进行正常操作，因为它们可能被禁用。

    在*设计契约*编程模型中，设计者使用断言表达关于程序��为的条件。

    +   *前置条件.* 客户在调用方法时承诺满足的条件。

    +   *后置条件.* 实现在从方法返回时承诺实现的条件。

    +   *不变量.* 在方法执行时，实现承诺满足的条件。

#### 练习

1.  仅使用其他`Vector`方法（如`direction()`和`magnitude()`）为 Vector.java 提供`minus()`的实现。

    *解决方案*:

    ```
    public Vector minus(Vector that) {
        return this.plus(that.scale(-1.0));
    }

    ```

1.  为 Vector.java 添加一个`toString()`方法，返回以逗号分隔的向量分量，并用匹配的括号括起来。

#### 创意练习

1.  **统计.** 开发一个数据类型，用于维护一组实数的统计信息。提供一个添加数据点的方法和返回点数、均值、标准差和方差的方法。

    > $$ \begin{eqnarray*} \bar x &=& \frac{1}{n} \sum_i x_i \\ s² &=& \frac{\sum_i (x_i - \mu)²}{n-1} \;\; = \;\; \frac{n \sum_i x_i² - (\sum_i x_i)²}{n(n-1)} \end{eqnarray*} $$

    开发两种实现：OnePass.java，其实例值为点数和值的总和，以及值的平方和，TwoPass.java，它保留一个包含所有点数的数组。为简单起见，您可以在构造函数中取最大点数。您的第一个实现可能会更快，占用的空间也会大大减少，但也可能容易受到舍入误差的影响。

    *解决方案*: StableOnePass.java 是一个精心设计的替代方案，它在数值上是稳定的，不需要数组来存储元素。

    > $$ \begin{eqnarray*} m_0 &=& 0 \\ s_0 &=& 0 \\ m_n &=& m_{n-1} + \frac{1}{n} \; (x_n - m_{n-1}) \\ s_n &=& s_{n-1} + \frac{n-1}{n} \; (x_n - m_{n-1})² \\ \bar x &=& m_n \\ s² &=& \frac{1}{n-1} s_n \end{eqnarray*} $$

1.  **基因组.** 开发一个数据类型来存储生物体的基因组。生物学家经常将基因组抽象为核苷酸序列（A、C、G 或 T）。数据类型应支持方法`addNucleotide()`，`nucleotideAt()`，以及`isPotentialGene()`。开发三种实现。

    +   使用一个`String`类型的实例变量，使用字符串连接实现`addCodon()`。每次方法调用的时间与当前基因组的长度成正比。

    +   使用字符数组，每次填满时将数组长度加倍。

    +   使用布尔数组，使用两位来编码每个密码子，并在每次填满时将数组长度加倍。

    *解决方案*: StringGenome.java, Genome.java, 和 CompactGenome.java.

1.  **封装.** 以下类是否是不可变的？

    ```
    import java.util.Date

    public class Appointment {
        private Date date;
        private String contact;

        public Appointment(Date date) {
            this.date = date;
            this.contact = contact;
        }

        public Date getDate() {
            return date;
        }

    ```

    *解决方案*：不行，因为 Java 的 [java.util.Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html) 是可变的。要纠正，需要在构造函数中对日期进行防御性拷贝，并在返回给客户端之前对日期进行防御性拷贝。

1.  **日期。** 设计一个不可变的 Java [java.util.Date](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html) API 的实现，从而纠正上一个练习的缺陷。

    *部分解决方案*：Date.java。

#### 网络练习

1.  在 Genome.java 中添加方法来测试相等性并返回反向互补的基因组。

1.  在 Date.java 中添加方法来检查给定日期属于哪个季节（春季、夏季、秋季、冬季）或星座（双鱼座、天秤座，...）。要注意跨越十二月至一月的事件。

1.  在 Date.java 中添加一个`daysUntil()`方法，该方法以`Date`作为参数，并返回两个日期之间的天数。

1.  创建一个实现 Date2.java，它将日期表示为自 1970 年 1 月 1 日以来的天数。与 Date.java 进行比较。

1.  创建一个代表矩形的`Rectangle` ADT。通过两个点来表示一个矩形。包括一个构造函数，一个`toString`方法，一个计算面积的方法，以及一个使用我们的图形库绘制的方法。

1.  重复上一个练习，但这次将`Rectangle`表示为左下端点和宽度和高度。

1.  重复上一个练习，但这次将`Rectangle`表示为中心点、宽度和高度。

1.  **稀疏向量。** 创建一个稀疏向量的数据类型。通过非零索引数组和相应的非零值并行数组来表示稀疏向量。假设索引按升序排列。实现点积运算。

1.  **拷贝构造函数。** 只有在数据类型是可变的情况下才需要。否则，赋值语句可以按预期工作。

    ```
    public Counter(Counter x) {
        count = x.count;
    }

    Counter counter1 = new Counter();
    counter1.hit();
    counter1.hit();
    counter1.hit();
    Counter counter2 = new Counter(counter1);
    counter2.hit();
    counter2.hit();
    StdOut.println(counter1.get() + " " + counter2.get());    // 3 5

    ```

1.  为两次可微函数定义一个接口 DifferentiableFunction.java。编写一个实现函数 f(x) = c - x² 的类 Sqrt.java。

1.  编写一个程序 Newton.java，实现牛顿法来找到一个充分光滑函数的实根，假设你从一个足够接近根的地方开始。当方法收敛时，它会呈二次收敛。假设它以`DifferentiableFunction`作为参数。

1.  **生成随机数。** 从标准高斯分布中生成随机数的不同方法。在这里，封装使我们能够用更准确或更有效的方法替换一个版本。三角方法简单，但由于调用多个超越函数可能会很慢。更重要的是，当 x1 接近 0 时，它会遇到数值稳定性问题。更好的方法是 Box-Muller 方法的另一种形式。[参考链接](http://en.wikipedia.org/wiki/Box-Muller_transform)。这两种方法都需要两个来自均匀分布的值，并产生两个均值为 0，标准差为 1 的高斯分布值。可以通过记住第二个值以节省工作量。 （这就是在`java.util.Random`中实现的方式。）它们的实现是 Box-Muller 的极坐标方法，保存第二个随机数以供后续调用。（参见 Knuth，ACP，第 3.4.1 节算法 C。）

1.  **洛杉矶机场关闭。** 2004 年 9 月 14 日，洛杉矶机场由于空中交通管制员与飞行员通信的无线电系统软件故障而被关闭。该程序使用了一个 Windows API 函数调用`GetTickCount()`，它返回自系统上次启动以来的毫秒数。该值以 32 位整数返回，因此大约在 49.7 天后会"环绕"。软件开发人员意识到了这个错误，并实施了一个政策，即每个月技术人员会重新启动机器，以确保其运行时间不超过 31 天。糟糕。洛杉矶时报指责了技术人员，但更应该责备开发人员的糟糕设计。

1.  **点的极坐标表示。** 使用极坐标重新实现 Point.java 数据类型。

    *解决方案*：PointPolar.java。

1.  **球坐标系。** 使用笛卡尔坐标\((x, y, z)\)或球坐标\((r, \theta, \phi)\)表示三维空间中的点。要从一个坐标系转换到另一个坐标系，使用以下公式

    > $$ \begin{array}{lllllll} r &=& \sqrt{x² + y² + z²} &\hspace{.3in} & x &=& r \cos \theta \sin \phi \\ \theta &=& \tan^{-1}(y/x) & & y &=& r \sin \theta \sin \phi \\ \phi &=& \cos^{-1}(z/r) & & z &=& r \cos \phi \\ \end{array} $$

1.  **颜色。** 可以用 RGB、CMYK 或 HSV 格式表示。自然而然地会有相同接口的不同实现。

1.  **邮政编码。** 实现一个表示美国邮政服务 ZIP 码的 ADT。支持原始的 5 位数字格式和更新的（但可选的）ZIP+4 格式。
