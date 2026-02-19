CSE 331 软件设计与实现

# 表示不变性和抽象函数

内容：

+   介绍

+   表示不变性

    +   选择表示不变性

    +   运行时检查表示不变性

    +   不要在表示不变性中写什么

+   抽象函数

    +   R 和 A 在哪里定义？

    +   AF(r)

+   示例 1：卡片

+   示例 2：栈

    +   表示不变性

    +   抽象函数

+   子类

+   关于可读性的一般提示

* * *

## 介绍

本手册描述了如何记录一个类的实现。它依赖于您已经理解了类和方法规范。

作为示例，我们将使用与类和方法规范中相同的类`Line`。请注意，我们现在展示的是`Line`的实现，因为本手册涵盖了记录类的实现，而不是规范。

```

/**
 * This class represents the mathematical concept of a line segment.
 *
 * Specification fields:
 *  @specfield start-point : point  // The starting point of the line
 *  @specfield end-point   : point  // The ending point of the line
 *
 * Derived specification fields:
 *  @derivedfield length : real // length = sqrt((start-point.x - end-point.x)² + (start-point.y - end-point.y)²)
 *                              // The length of the line
 *
 * Abstract Invariant:
 *  A line's start-point must be different from its end-point.
 */
public class Line {

  /** The x-coordinate of the line's starting point */
  private int startX;

  /** The y-coordinate of the line's starting point */
  private int startY;

  /** The x-coordinate of the line's ending point */
  private int endX;

  /** The y-coordinate of the line's ending point */
  private int endY;

  // Representation Invariant:
  //  ! (startX == endX && startY == endY)
  //
  // Abstraction Function:
  //  AF(r) = a line, l, such that
  //   l.start-point = ?r.startX, r.startY?
  //   l.end-point = ?r.endX, r.endY?

 /**
  * @requires p != null && ! p.equals(start-point)
  * @modifies this
  * @effects Sets end-point to p
  */
  public void setEndPoint(Point p) {
    ...
  }

  ...

}

```

我们从本文讨论的概念的简要定义开始：

*具体表示*

类的抽象状态如何在 Java 对象中表示。例如，`line`使用了四个类型为`int`的字段。

*表示不变性*

必须在类的所有有效具体表示上为真的条件。表示不变性还定义了抽象函数的域。在这个特定的例子中，`Line`要求`r.startX == r.endX && r.startY == r.endY`永远不成立，这是规范中抽象不变性所施加的条件。然而，表示不变性不仅限于规范包含抽象不变性的情况。只要有必须满足的条件，使得表示形式是完整的或正确定义的，表示不变性就适用。

*抽象函数*

从对象的具体表示到其表示的抽象值的函数。`Line`的抽象函数是微不足道的：一个具体的`Line`实例`r`被映射到一条线`l`，其`l.start-point`等于`?r.xStart, r.yStart?`，`l.end-point`等于`?r.xEnd, r.yEnd?`。

表示不变性和抽象函数是类实现细节的内部文档。客户端不应该需要任何这些信息来正确使用类。这些信息记录下来是为了帮助实现、测试、调试、修改和扩展类。因此，抽象函数和表示不变性不应该出现在类的描述或规范（Javadoc）中。相反，这些信息应该出现在类体中的内部注释中（通常使用`//`）。

本文首先介绍了如何通过使用表示不变式和抽象函数将类的具体表示与抽象表示相关联。然后提供了这些概念的两个示例以及类和方法规范中介绍的概念。最后，以一些一般提示结束，以便撰写易于理解的文档。

## Rep 不变式

一个 rep 不变式 RI 将具体表示映射到布尔值（true 或 false）。形式上，

> RI：*R* ? *boolean*

其中 R 是 rep 值的集合。rep 不变式描述了一个 rep 值是否是该类型的一个良好实例。

描述 rep 不变式的注释可能明确强调 RI 的功能方面：

```
 // Rep invariant is
 //    RI(r) = r.name != null && r.balance ≥ 0
```

然而，更常见的是，我们只是放弃 RI(r) 的细节，简单地将 rep 不变式写成必须对 `this` 为真的谓词：

```
 // Rep invariant is
 //    name != null && balance ≥ 0
```

rep 不变式可能会混合具体的 Java 语法（rep 字段引用、方法调用、`instanceof`、`!=`、`==`）和抽象的数学语法（序列/集合/元组构造、对于所有、存在、求和、`=`）。当然，rep 不变式也可以是简单的英语，只要它是明确的。以下是一些例子：

```
 //    for all i, transactions[i] instanceof Trans

 //    suit in {Clubs,Diamonds,Hearts,Spades}

 //    string contains no duplicate characters

 //    size = number of non-null entries in array

```

如果 rep 使用其他 ADT，则可以通过其规范字段或操作来引用它们。例如，假设 `Trans` 类型具有可通过操作 `getAmount` 访问的规范字段 `amount`。那么对于使用 `Trans` 对象的 `Account` 的 rep 不变式可能如下所示：

```
(1)   //    balance == sum (for all i) of transactions[i].amount
```

或者这样：

```
(2)   //    balance == sum (for all i) of transactions[i].getAmount()
```

或者甚至是这样（因为 `transactions` 是具有 `get` 操作的 ADT 的一个实例）：

```
(3)   //    balance == sum (for all i) of transactions.get(i).getAmount()
```

所有这些都是等价的。但是，重要的是要记住，在上述（1）中，`amount` 指的是 `Trans` 中的*规格字段*，而不是具体字段。除非 `Account` 和 `Trans` 合作非常密切，否则让 `Account` 打破抽象屏障并直接引用 `Trans` 的 rep 字段是不合适的。相比之下，让 `Account` 的 rep 不变式直接引用 `Account` 的 rep 字段是完全正常的。

### 选择 Rep 不变式

写下 rep 不变式对于测试、调试和编写正确代码非常有用。对于维护者来说至关重要：以后回来修复或增强代码的程序员。rep 不变式最常见的问题是*不完整* ——漏掉了一些重要内容。（完全忽略 rep 不变式可能是这个问题最常见的例子！）所以以下是一些提示，将帮助您填写您的 rep 不变式。

**寻找抽象函数无意义的 rep 值。** 抽象函数通常是一个*部分*函数，意味着它对某些可能的表示 *R* 的值没有定义。rep 不变式必须排除任何这样的值。回顾上面的 `Card` 示例：

```
public class Card {
    private int index;

    // Abstraction function is
    //    suit = S(index div 13)   where S(0)=Clubs, S(1)=Diamonds, S(2)=Hearts, S(3)=Spades
    //    value = V(index mod 13)  where V(1)=Ace, V(2)=2, ..., V(10)=10, V(11)=Jack, V(12)=Queen,
    //                                   V(0)=King
    ...
}
```

在这种情况下，当花色编号`index div 13`不是 0、1、2 或 3 时，抽象函数未定义。因此，排除了小于 0 或大于 51 的`index`值：

```
    // Rep invariant is
    //    0 ≤ index ≤ 51

```

请确保不要限制表示不变量以至于抽象函数不再覆盖整个抽象值空间*A*！如果这样做，你将不再实现抽象类型，因为一些抽象值将无法表示。在这里，稍加思考就会使我们确信`index`仍然代表 52 张卡片，全部不同。

**寻找使你的方法产生错误抽象值的表示值。** 考虑一个表示使用可变字符串表示字符集的`CharSet`类：

```
/** CharSet represents a mutable set of characters. */
public class CharSet {
    private StringBuffer chars;

    // Abstraction function is
    //    { chars[i] | 0 ≤ i < chars.size }
    ...

    /** @modifies this
     *  @effects this_post = this - {c}
     */
    public void remove (char c) {
        int i = chars.indexOf(Character.toString (c));
        if (i != -1) chars.deleteCharAt (i);
    }
}
```

此`remove`方法的实现仅在字符串中没有重复字符时有效，因为它只删除找到的`c`的第一个出现。请注意，这里抽象函数在*R*上完全定义 - 它不关心是否有重复字符，因为集合构造语法隐式忽略它们。但是，我们需要表示不变量来确保`remove`始终产生正确的抽象值，即不包含`c`的集合。

**寻找数据结构或算法所需的约束条件。** 例如，数组必须排序才能使用二分查找，树不能有循环，两个树节点不能共享相同的子节点。

**寻找需要保持协调的字段。** 例如，在银行账户中，余额和交易金额之和应始终保持同步。在链表中，`size`字段始终需要准确反映列表中的节点数。

**寻找会导致代码抛出意外异常的表示值。** 每个表示不变量的传统部分都是一组不应为 null 的字段，这样在以后使用它们时就不会出现`NullPointerException`：

```
    //   name != null && transactions != null
```

但是，请确保你的构造函数和生成器确实建立了表示不变量。这意味着，如果这些字段中的任何一个是从参数初始化的，你必须在将它们放入表示之前检查是否为 null。

一些其他需要考虑的异常情况：

+   除零

+   索引超出范围

+   类型转换异常

**寻找应用领域（对抽象值）强加的约束。** 在银行账户中，余额应始终为非负数。（甚至更强：交易金额的部分和必须始终为非负数，以确保余额过去从未为负数。）在国际象棋中，两个相同颜色的主教不应位于相同颜色的方格上（除非兵卒到达棋盘的尽头并晋升为主教）。

假设它们仅涉及抽象值的属性（如规范字段），这些约束不仅适用于表示。实际上它们是*抽象不变量*。抽象不变量应该为数据类型的客户端记录，因此将它们放在类概述中。但是，当存在抽象不变量时，它们很常常暗示需要包含在表示不变性中的约束。如果从表示不变性中省略了这些内容，那么您的类型将表示不符合规范的抽象值。

### 在运行时检查表示不变性

许多表示不变性可以直接转换为代码。如果是这种情况，请这样做！拥有可执行的表示不变性，并在运行时使用它，不仅有助于快速发现代码中的错误；它还检查表示不变性中的错误。有时，您编写的表示不变性*过于*严格，做出了不合理和不必要的假设。实际上，针对运行代码测试不变量是一个很好的健全检查。

表示不变性检查器可以编码为一个没有参数的方法`checkRep`，如果违反了表示不变性，则抛出异常，最好附带指示哪个约束被破坏的消息。 （但是，规范从不提及表示不变性；从客户端的角度看，该方法从未产生任何效果。）以下是一个示例：

```
private void checkRep () {
    if (balance < 0)
        throw new RuntimeException ("balance should be ≥ 0");

    if (name == null)
        throw new RuntimeException ("name should be non-null");

    // for all j, sum (i=0..j) transactions[i].amount >= 0
    int sum = 0;
    for (Trans t : transactions) {
        sum += t.getAmount();
        if (sum < 0)
           throw new RuntimeException("balance went negative");
    }
    // balance = sum (for all i) transactions[i].amount
    if (balance != sum)
        throw new RuntimeException ("balance should equal sum of transactions[i].amount");
}
```

在类中放置`checkRep`的最佳位置就在字段之后。您可以将您的表示不变性写成一个单独的注释，或者将表示不变性的约束插入`checkRep`中作为异常消息（如上所做）。后一种方法可能更好，因为这样更有可能使注释与`checkRep`中的代码保持同步。无法编写为可执行代码的表示不变性的任何部分，只需留下注释。

断言提供了一种更干净的编写`checkRep`的方式，因为它们为您处理了测试和异常。以下是两种方法：

```
    // using Java assert syntax
    assert balance ≥ 0 : "balance should be ≥ 0";

    // using junit.framework.Assert (you don't have to be writing a unit test to use this class)
    Assert.assertTrue ("balance should be ≥ 0", balance ≥ 0);

```

对`checkRep`的调用应放置在每个公共方法的开头和结尾，以及每个构造函数的结尾。即使您认为观察者不会改变表示，也应在观察者的结尾调用`checkRep`（因为您可能是错误的）。通常私有方法不调用`checkRep`，因为私有方法可能被设计为在不满足表示不变性的中间状态下调用��

如果表示不变式的一部分非常昂贵，你可能希望在发布版本中关闭该部分。否则最好保留它。在这里要谨慎评估性能。新手往往过于担心性能改进，结果却微不足道。在放弃检查之前，你应该有一些证据表明它是昂贵的，比如使用分析工具显示该检查确实是一个热点，或者理论上的论证，例如该检查将一个常数时间操作变成一个线性时间操作。检查字段是否为 `null` 总是一个常数时间操作；除非在绝对关键的性能代码中，否则没有理由放弃这个检查。对账户中所有交易进行求和与交易数量成正比，你可能不希望在生产代码中的每个方法调用中都这样做。但即使昂贵的 `checkRep` 在测试和调试期间通常是合理的；它们将在减少调试时间方面超额回报，除非它们使执行在任何合理的时间内无法完成（例如，几天或几个世纪）。启用/禁用 `checkRep` 调用的简单方法是向类添加一个名为 `debug` 的静态布尔变量，并在 `checkRep` 中检查该变量，或编写类似 `if (debug) checkRep();` 的调用。然后，你可以通过更改变量的值来禁用所有调试检查。

`checkRep` 方法也可以设为公共的，这样单元测试在测试时可以调用它。`checkRep` 通常是私有的，因为表示不是规范的一部分；客户端不应该知道底层可能存在破损的表示。 （可怕！）但是如果将其设为公共的，它并不会暴露表示。如果你的类正常工作，那么从客户端的角度来看，`checkRep` 只是一个空操作：它不会改变任何东西，也不会抛出异常。如果将 `checkRep` 设为公共的，你可能应该这样指定，以便客户端不会在不必要的情况下调用它： "此操作除非存在错误，否则不执行任何操作，并且（有时）会抛出异常。" 不用说，不要将表示不变式本身放在 `checkRep` 的规范中。这是依赖于表示的。

### 不要在表示不变式中写什么

你的表示不变式不必提及在表示中不可能的事实。你可以依赖于具体字段中 ADT 的保证。例如，如果你的一个具体字段是一个 `int`，那么你的表示不变式不应该提及其值小于或等于 `Integer.MAX_VALUE` 或不为 `null`。同样，如果你的一个具体字段是一个集合，那么你的表示不变式不需要提及它不包含重复项。

这类似于方法前置条件不需要提及由形式参数的 ADT 保证的属性。

表示不变性应该可以表达为`checkRep`方法。不要在表示不变性中写任何不能通过仅检查具体表示来检查的内容。检查表示不变性不应该需要任何关于表示意义或创建表示所执行的操作的知识。

## 抽象函数

一个抽象函数 AF 将抽象数据类型的具体表示映射到 ADT 表示的抽象值。形式上，

> AF: *R* ? *A*

其中 R 是 rep（表示）值的集合，A 是抽象值的集合。你可以将*R*中的元素看作 Java 对象。另一方面，*A*只存在于我们的想象中，在计算机内部并不存在。例如，如果这是 ADT：

```
class Complex {
  private double real;
  private double imag;
  ...
}

```

然后，表示空间*R*是`Complex`对象的集合，抽象空间*A*是复数的集合。

### R 和 A 在哪里定义？

表示空间*R*是显而易见的：它由你在类中放置的字段定义。你不可能实现一个抽象数据类型而没有字段，所以你永远不会忘记这一点。然而，抽象值空间*A*在代码中没有表示。它应该在你的类概述中记录（参见抽象状态），因为客户端和实现者都想知道类代表什么抽象类型：

```
/**
 * Complex represents an immutable complex number.    ← this is A
 */
public class Complex {
  private double real;    ← these fields form R
  private double imag;
  ...
}

```

类型是可变的还是不可变的是一个关键属性，应该在类概述中提到。

### AF(r)

从技术上讲，抽象函数是一个*函数*。这就是为什么你可能会看到它使用函数符号 AF(r)写成这样的原因：

```
/**
 * Complex represents an immutable complex number.
 */
public class Complex {
  private double real;
  private double imag;

  // The abstraction function is
  //      AF(r) = r.real + i * r.imag
  ...
}
```

AF(r)中的*r*代表表示空间中的一个元素。换句话说，它是对`Complex`对象的引用。因此，我们可以在抽象函数的右侧引用对象*r*的字段。（顺便说一句，*r*代表*representation*。）

当抽象函数是递归的时，函数符号是必不可少的，因为我们需要一种方式在右侧引用它：

```
/**
 * Cons represents an immutable sequence of objects.
 */
public class Cons {
  private Object first;
  private Cons rest;

  // The abstraction function is
  //      AF(r) = [] if r = null
  //              [r.first] : AF(r.rest) if r != null
  ...
}
```

(方括号和冒号是序列构造语法。)

然而，通常抽象函数并不是递归定义的。这时，只需写右侧更易读。我们进一步假设表示对象*r*代表`this`，并采用在写抽象函数时省略对`this`的引用的约定：

```
/**
 * Complex represents an immutable complex number.
 */
public class Complex {
  private double real;
  private double imag;

  // The abstraction function is
  //      real + i * imag
  ...
}

```

这很简单明了，但请记住这只是 AF(r)的简写。

对于具有平凡表示的 ADT，规范字段可能与表示字段一一对应：

```
public class Line {
    private Point start;
    private Point end;

    // Abstraction function is
    //    AF(r) = line l such that
    //       l.start = r.start
    //       l.end = r.end
    ...
}

```

但这个抽象函数几乎不值得写下来。这里有一个相同 ADT 的更有趣的表示：

```
public class Line {
    private Point start;
    private double length;
    private double angle;

    // Abstraction function is
    //    AF(r) = line l such that
    //       l.start = r.start
    //       l.end.x = r.start.x + r.length * cos(r.angle)
    //       l.end.y = r.start.y + r.length * sin(r.angle)
    ...
}
```

注意`x`和`y`是`Point`类型的规范字段。方便起见，也可以根据其规范字段定义点`end`。

让我们用更多的简写来简化这个过程。我们将放弃 AF(r)，就像我们之前做的那样。我们假设 rep 值*r*和抽象值*l*都代表`this` — 只是`this`的不同方面 — 并采用省略引用`this`的约定。所有这些简写的效果只是一个方程列表，用具体字段定义每个规范字段：

```
    // Abstraction function is
    //       start = start
    //       end.x = start.x + length * cos(angle)
    //       end.y = start.y + length * sin(angle))

```

请记住，在左侧，`start`指的是规范字段；在右侧，`start`指的是具体字段。（在这里，`x`和`y`总是指规范字段，因为`Point`类型的表示对我们不可见。）两个`start`之间是否存在混淆的危险？实际上并没有。我们以很好的原因给规范字段和具体字段相同的名称 — 因为它们被抽象函数等同。我们真的需要在抽象函数中明确写出`start=start`吗？可能不需要。如果规范字段`start`和 rep 字段`start`不是由抽象函数等同的，那么我们应该给它们不同的名称。请记住，在这些规范中，您的目标不是与机器进行正式通信，而是与其他人进行清晰和明确的沟通（不仅仅是作者！）。名称很重要。有时缩写有帮助，有时没有。

这里有另一个例子。假设我们想要使用单个整数在一个`index`字段中表示扑克游戏中的`Card`数据类型。我们可能有两个规范字段，`suit`和`value`：

```
/**
 * Card represents an immutable playing card.
 * @specfield suit : {Clubs,Diamonds,Hearts,Spades} // card suit
 * @specfield value : {Ace,2,...,10,Jack,Queen,King} // card rank
 */

```

然后抽象函数描述如何将`index`字段分解为花色和值：

```
public class Card {
    private int index;

    // Abstraction function is
    //    suit = S(index div 13)   where S(0)=Clubs, S(1)=Diamonds, S(2)=Hearts, S(3)=Spades
    //    value = V(index mod 13)  where V(1)=Ace, V(2)=2, ..., V(10)=10,
    //                                   V(11)=Jack, V(12)=Queen, V(0)=King
    //    (div and mod refer to the integer division and remainder operations)
    //    for example, 3 ? Three of Clubs
    //                 14 ? Ace of Diamonds
    ...
}

```

这个抽象函数将每个表示对象映射到一个`(suit,value)`对，但我们没有将其写成一个单独的函数，而是分别为每个规范指定了两个函数。

（两个次要的观点：您可能会想知道为什么 Ace 是 V(1)而不是 V(0)。这是为了使抽象函数在编号卡上更直接，以便 V(*i*) = *i*对于 2 到 10。但这可能不是理想的；因为 King 是 V(0)，我们不能通过直接比较`index`字段来比较卡片。其次，这种对`Card`的表示与花色集和值集紧密耦合。如果我们预计这些类型在未来会发生变化，例如添加或删除花色，那么我们将不得不更改`Card`的表示。然而，对于某些应用程序，表示的紧凑性可能值得更大耦合的缺点。）

## 示例 1：卡片

这是一个具有抽象函数和 rep 不变性的简单类的完整示例，这样您可以看到您可能如何构造您的代码的一种方式。

```
/**
 * Card represents an immutable playing card.
 * @specfield suit : {Clubs,Diamonds,Hearts,Spades} // card suit
 * @specfield value : {Ace,2,...,10,Jack,Queen,King} // card rank
 */
public class Card {

    private int index;

    // Abstraction function is
    //    suit = S(index div 13)   where S(0)=Clubs, S(1)=Diamonds, S(2)=Hearts, S(3)=Spades
    //    value = V(index mod 13)  where V(1)=Ace, V(2)=2, ..., V(10)=10, V(11)=Jack, V(12)=Queen,
    //                                   V(0)=King

    // Rep invariant is
    //    0 <= index <= 51

    /**
     * Check the rep invariant.
     * @effects: nothing if this satisfies rep invariant;
     *           otherwise throws an exception
     */
    private void checkRep() {
        if (index < 0 || index > 51)
            throw new RuntimeException ("card index out of range");
    }

    /**
     * @effects makes a new playing card with given suit and value
     */
    public Card(CardSuit suit, CardValue value) {
        ... // initialize Card
        checkRep();
    }

    /**
     * @effects returns this.suit   ← "suit" refers to the spec field
     */
    public CardSuit getSuit() {
        checkRep();
        try {
            CardSuit s = ... // decode suit
            return s;
        } finally {
            checkRep();
        }
    }

    /**
     * @effects returns this.value  ← "value" is the spec field
     */
    public CardValue getValue() {
        checkRep();
        try {
            CardValue v = ... // decode value
            return v;
        } finally {
            checkRep();
        }
    }

    ...
}

```

在这种情况下，所有观察者中的`checkRep()`调用可能是不必要的，因为该类简单、不可变，并且明显没有暴露表示。它们仍然包含在内，以说明在更复杂的类中您可能想要做的事情。

## 示例 2：堆栈

假设我们想要使用数组实现一个堆栈 ADT。

### 表示不变

这里有一些可能的表示不变：

```
public class Stack {
    private int[] elements;

    // Abstraction function:
    //    The Nth element from the bottom of the stack = elements[N-1]
    //    where the 1st element is at the bottom

    // Rep Invariant:
    //    For any index i such that 0 <= i < size, elements[i] != null

    // OR

    // Rep Invariant:
    //    elements never contains a null value
}

```

如果 RI 是针对 SortedStack 的，则可以想象稍作修改：

```
public class SortedStack {
    private int[] elements;

    // Abstraction function:
    //    The value considered 'least' in the stack = elements[size-1]
    //    ...
    //    The value considered 'greatest' in the stack = elements[0]

    // Rep Invariant:
    //    For any index i such that 0 <= i < size: elements[i] != null 
    //    For any index j such that 1 <= j < size: elements[j] <= elements[j-1]
}

```

在这种情况下，我们的 RI 正是区分 ADT 内部状态限制的。

RI（Rep Invariant）的目的是定义此 ADT 对象的有效和无效内部状态（SortedStack 应始终排序且不包含空值）。`checkRep()` 方法应该与 RI 保持一致。

### 抽象函数

这里有一些示例 AF（Abstraction Functions）。

```
// For a naive implementation with poor run-time performance:
public class Stack {
    private int[] elements;
    private int size;

    // Abstraction function:
    //    The top element of the stack = elements[0]
    //    The second-from-the-top element of the stack = elements[1]
    //    ...
    //    The bottom element of the stack = elements[size-1]

    // OR

    // Abstraction function:
    //    The Nth element from the top of the stack = elements[N-1]
    //    where the 1st element is at the top
}

```

```
// For a tweaked implementation with great run-time performance:
public class Stack {
    private int[] elements;
    private int size;

    // Abstraction function:
    //    The top element of the stack = elements[size-1]
    //    The second-from-the-top element of the stack = elements[size-2]
    //    ...
    //    The bottom element of the stack = elements[0]

    // OR

    // Abstraction function:
    //    The Nth element from the bottom of the stack = elements[N-1]
    //    where the 1st element is at the bottom
}

```

注意两个示例的签名和字段是相同的，但是每个抽象函数都暗示了具有截然不同运行时性能的不同实现。（如果不清楚运行时性能为何不同，请考虑在推送和弹出堆栈时需要对每个实现的数组中的元素执行什么操作。）

## 子类

抽象函数和表示不变是特定于实现的。因此，从超类继承它们是没有意义的。当你编写子类时，应该从头开始定义其抽象函数和表示不变，并将其完整写出。

## 关于可读性的一般提示

记住，阅读你的规范、抽象函数和表示不变的人很可能是*人类*，而不是程序。可能是一位队友试图找到代码中的错误；一个负责在你离开公司后更新软件的维护人员；甚至是你自己，六个月（或者几天！）后，试图记住这个程序是如何工作的。

因此，正式的语法正确性实际上比简洁性和清晰性更不重要。这并不意味着你应该牺牲语义精确度，或者让事情变得模糊或未定义。但这确实意味着你应该三思而后再写像这样的东西：

```
    // Abstraction function is
    //    <[x,y],s^[for all 0<i≤chars.size(), chars[chars.size()-i]]> | x=front.rest,
    //     y=back.first, s=n.toString()>
```

编译器可能会喜欢阅读此内容（如果编译器实际上正在阅读您的抽象函数）。人类会盯着它看，然后诅咒。

这里有一些使你的抽象函数和表示不变更可读的提示：

+   在有用处的地方引入新名称：

    ```
        AF(r) = list l such that...

        AF(r) = c_0 + c_1*x + c_2*x² + ...

            where c_i = ...

    ```

+   使用规范字段：

    ```
        suit = ...
        value = ...
    ```

+   提供示例：

    ```
     for example, 3 ? Three of Clubs

    ```

+   在有用处的地方引入新函数：

    ```
     reverse(back)
    ```

+   在明确且比正式语法更清晰或更简洁的地方使用通俗语言：

    ```
        chars contains no duplicates

    ```

    与正式替代方案形成对比：

    ```
        for all 0≤i<j<chars.size, chars[i] != chars[j]

    ```
