CSE 331 软件设计与实现

# Java 风格指南

目录：

+   概述

+   描述性名称

+   一致的缩进和间距

+   局部变量

+   类型

    +   泛型

    +   类型转换

+   信息性注释

+   Javadoc 注释

+   TODO 注释

+   注释掉的代码

+   文档化代码

    +   规范级别注释

    +   实现级别注释

## 概述

编码风格是良好软件工程实践的重要组成部分。目标是编写清晰易懂的代码，减少未来扩展或修改所需的工作量。

在 CSE 331 中，我们不指定必须遵循的详细编码风格。但是，我们期望你的代码清晰易懂。本手册提供了总体指导，你应该在其中发展自己的有效编码风格。

还有许多其他风格指南可供参考。例如，你可以查看 Oracle 的[Java 编程语言的代码约定](http://www.oracle.com/technetwork/java/codeconv-138413.html)或 Michael Ernst 关于[编码约定](http://homes.cs.washington.edu/~mernst/advice/coding-style.html)的文档，这些文档与本文档相辅相成。我们不要求你盲目遵循这些指南——它们只是编写代码的一种可理解的方式——但在开发自己的风格时，你可能会考虑它们。比编码风格指南更有价值的是关于设计和编写代码的良好方法的描述。对于 Java 程序员，Josh Bloch 的书*Effective Java*是一个很好的选择。

## 描述性名称

包、类型、变量和分支标签的名称应记录它们的含义和/或用途。这并不意味着名称需要很长。例如，在短循环中，像*i*和*j*这样的名称对于索引是可以的，因为程序员通过约定了解这些变量的含义和用途。

你应该遵循标准的 Java 约定，即将类名大写，但将方法、字段、变量和包名以小写字母开头。常量使用全大写字母命名。Java 语言规范提供了一些常见的[Naming Conventions](http://docs.oracle.com/javase/specs/jls/se7/html/jls-6.html#jls-6.1-120)，在为类、方法等命名时可能会用到。还请参阅*Effective Java*第 56 条。

## 一致的缩进和间距

一致缩进代码使得很容易看出`if`语句和`while`循环的结束等。你应该选择一致的策略；例如，一致地将开放的大括号放在与*if*相同行或下一行，或者你的 try-catch-finally 块是什么样子的。查看由工作人员提供的代码，以及书中打印的代码，了解示例样式；如果让你更舒适，可以自由发展自己的风格。

在 Eclipse 中，`Ctrl-F`将根据其内置缩进规则缩进您的代码（您可能会或不会喜欢）。

一致（且充分）的水平间距也有助于读者。没有理由试图通过消除空格来节省一两列。在分隔方法参数的逗号后应留有一个空格。在`for`、`if`或`while`与后面的开括号之间应留有一个空格；否则，该语句看起来太像一个方法调用，这会令人困惑。一般来说，每行只应放置一个语句。请记住，阅读您的代码的人可能有不同宽度的显示器，或者可能选择打印您的代码进行代码审查（助教可能会这样做！）。80 列是行业中普遍接受的宽度，我们要求这样做是为了方便助教在标记您的打印输出时。偶尔出现较长的行是可以接受的，但不应作为一般规则。当您换行时，请在逻辑位置而非任意位置进行。

代码文件中不应包含制表符。它们在不同的 IDE 中格式化方式不同，在打印时也不同。一个体面的 IDE 不应在代码文件中插入制表符，或者至少应该有一个设置来使用空格代替。在 Eclipse 中，执行以下操作：

1.  转到窗口 > 首选项 > Java > 代码风格 > 格式化程序

1.  创建一个新配置文件（如果您以前没有 —— 您无法更改默认的 Eclipse 配置文件，并且它们使用制表符）

1.  将“制表符策略”设置为仅使用空格

1.  Ctrl+Shift+F 将按照这些设置重新格式化当前文件

1.  您可以临时启用`常规 > 编辑器 > 文本编辑器 > 显示空格`来验证它是否将制表符转换为空格。

## 局部变量

局部变量应具有尽可能小的作用域。不要在方法开头声明它，然后在其声明和第一次使用之间有很多不相关的代码。另一个例子是，如果您有一个在每次循环迭代中使用的变量，请在循环内部声明它，以便向读者明确表明没有循环依赖。

另请参阅*Effective Java*第 45 条。

## 类型

### 泛型

每当使用泛型类型时必须提供类型参数。永远不要使用所谓的“原始”类型，如`List`，而应使用`List<Integer>`或类似的类型。

所有代码必须使用`javac -g -Xlint`编译而无警告，不得使用`@SuppressWarnings`，除非下面允许。

### 类型转换

一般规则是，您不应该在您编写的代码中使用类型转换（尤其是 CSE 331 的代码）。类型转换是一种隐藏信息并阻止编译器标记代码中真正错误的解决方法。

*然而*，在 Java 库中存在一些过于宽泛的遗留接口，需要使用类型转换。这些接口通常是在 Java 拥有今天强大类型系统之前编写的 —— 其中一些接口被广泛使用。实现这些“过于宽泛”的接口是使用类型转换的一个可以接受的理由。

以下是 Java API 中需要进行类型转换的接口的相当完整列表。除非你正在实现其中之一，否则你的代码中可能不需要类型转换：

> 所有的实现：
> 
> +   [Object.equals()](http://docs.oracle.com/javase/7/docs/api/java/lang/Object.html#equals(java.lang.Object))
> +   
> 一些（不是全部）实现：
> 
> +   [Object.clone()](http://docs.oracle.com/javase/7/docs/api/java/lang/Object.html#clone())
> +   
> +   [Collection.contains()](http://docs.oracle.com/javase/7/docs/api/java/util/Collection.html#contains(java.lang.Object))（以及 Collection 的子类，如[List](http://docs.oracle.com/javase/7/docs/api/java/util/List.html)和[Set](http://docs.oracle.com/javase/7/docs/api/java/util/Set.html)）
> +   
> +   [Collection.remove()](http://docs.oracle.com/javase/7/docs/api/java/util/Collection.html#remove(java.lang.Object))（以及子类）
> +   
> +   [Map.containsKey()](http://docs.oracle.com/javase/7/docs/api/java/util/Map.html#containsKey(java.lang.Object))
> +   
> +   [Map.containsValue()](http://docs.oracle.com/javase/7/docs/api/java/util/Map.html#containsValue(java.lang.Object))
> +   
> +   [Map.get()](http://docs.oracle.com/javase/7/docs/api/java/util/Map.html#get(java.lang.Object))
> +   
> +   [Map.remove()](http://docs.oracle.com/javase/7/docs/api/java/util/Map.html#remove(java.lang.Object))
> +   
> +   [JComponent.paintComponent](http://download.oracle.com/javase/7/docs/api/javax/swing/JComponent.html#paintComponent(java.awt.Graphics))（在官方 Oracle 教程中鼓励对`Graphics`对象进行类型转换）
> +   
> 这些可能需要*未经检查的*类型转换（更糟糕！）：
> 
> +   [SortedMap.containsKey()](http://docs.oracle.com/javase/7/docs/api/java/util/SortedMap.html)
> +   
> +   [SortedMap.containsValue()](http://docs.oracle.com/javase/7/docs/api/java/util/SortedMap.html)
> +   
> +   [SortedMap.get()](http://docs.oracle.com/javase/7/docs/api/java/util/SortedMap.html)
> +   
> +   [SortedMap.remove()](http://docs.oracle.com/javase/7/docs/api/java/util/SortedMap.html)
> +   
> +   [SortedSet.contains()](http://docs.oracle.com/javase/7/docs/api/java/util/SortedSet.html)
> +   
> +   [SortedSet.remove()](http://docs.oracle.com/javase/7/docs/api/java/util/SortedSet.html)

CSE 331 要求你的代码在使用`-Xlint`标志运行`javac`时能够干净编译。你可以使用`@SuppressWarnings("unchecked")`注解来抑制关于上述方法列表中未经检查的类型转换的警告。此外，如果官方的 Oracle Java 教程告诉你要使用类型转换，那是可以的。除此之外，你不得在代码中使用`@SuppressWarnings`。而且，每当你使用一个时，都要记录你的理由。

## 信息性注释

不要犯在任何地方都写注释的错误 —— 一个糟糕或无用的注释比没有注释更糟糕。如果信息从代码中显而易见，添加注释只会给读者增加额外的工作。例如，这是一个无用的注释，只会帮助那些不懂编程语言的人：

```
i++;    // increment

```

良好的注释以简洁明了的方式为代码添加信息。例如，如果注释具有信息性，那么它们应该：

+   *使读者避免阅读一些代码。* 以下注释节省了读者研究一些复杂公式的工作量，并说明了程序员的意图，以便稍后检查这些公式。

    ```
        // Compute the standard deviation of list elements that are
        // less than the cutoff value.
        for (int i=0; i<n; i++) {
            ...
        }

    ```

    这种类型的注释的一个重要应用是记录方法的参数和返回值，这样客户端就不需要阅读实现来理解如何使用该方法。

+   *解释一个晦涩的步骤或算法。* 当某个步骤的效果在代码本身中不明显时，这一点尤为重要。你应该解释棘手的算法、具有副作用的操作、代码中的魔数等。

    ```
        // Signal that a new transfer request is complete and ready
        // to process.  The manager thread will begin the disk transfer
        // the next time it wakes up and notices that this variable has changed.
        buffer_manager.active_requests ++;

    ```

+   *记录假设。* 代码在什么假设下才能正常工作？

    ```
        // The buffer contains at least one character.
        // (If the buffer is empty, the interrupt handler returns without
        // invoking this function.)
        c = buffer.get_next_character();

    ```

+   *记录限制和不完整的代码。* 经常情况下，代码的第一个版本是不完整的；记录哪些代码已知是不正确的是很重要的。如果你在作业时间内完成一个程序，但它不能正确处理所有输入，我们会期望你的代码表明你理解它的局限性。

    ```
        if (n > 0) {
            average = sum / n;
        } else {
            // XXX Need to use decayed average from previous iteration.
            // For now, just use an arbitrary value.
            average = 15;
        }

    ```

提示：

+   不要先编写代码，然后再加注释 — 边写代码边加注释。在思考代码时加注释会更容易记住细节，而且你不太可能回头再加注释。事实上，最好在编写代码*之前*加注释 — 这样做可能会暴露你的想法中的弱点，并节省你在实现上的时间。

+   我们不要求你在每个程序片段上写注释。然而，你的分数在很大程度上取决于你的代码清晰度，对你来说似乎清晰的程序片段可能对读者来说并不清晰。因此，我们*强烈*建议你为所有类、字段和方法添加解释性注释，特别是公共的 — 这对你可能有利。

## Javadoc 注释

每个类、每个接口、每个公共方法和字段，以及每个非平凡的非公共方法和字段，都应该有一个解释性的 Javadoc 注释。（即使在非公共成员上也很有用，有两个原因。首先，Javadoc 有一个特殊选项，使其输出所有成员的文档，包括私有成员。你永远不会向客户提供这个，但对于开发团队来说，这确实很有帮助。其次，像 Eclipse 这样的 IDE 在你悬停在使用处时显示成员的 Javadoc，这对私有和公共成员都很有用。）

注释应该是符合语法的英语。如果超过几个词，注释应该由以大写字母开头并以句点结尾的完整句子组成。

HW3 中的`HelloWorld`有几个 Javadoc 注释：在文件顶部，在类声明之前，在`greeting`字段之前，以及在每个方法之前。你可以通过这些 Javadoc 注释的位置和以**`/**`**开头而不是**`/*`**来判断它们是 Javadoc 注释。

使用这种语法来记录你的代码是很重要的，这样你的注释就会出现在 Javadoc 工具生成的 HTML 文档中（这是[Oracle API](http://docs.oracle.com/javase/7/docs/api/)文档是如何生成的）。在生成 HTML 文档时，有一些[Javadoc 标签](http://docs.oracle.com/javase/7/docs/technotes/tools/windows/javadoc.html#javadoctags)会以特殊的方式格式化。你可以识别这些标签，因为它们以 **@** 符号开头，例如 **@param** 和 **@return**。

对于 CSE 331，我们使用了一些 Oracle Javadoc 工具不识别的额外 Javadoc 标签，例如 **@requires**、**@modifies** 和 **@effects**。因此，我们需要使用一个特殊的 331 版本的 Javadoc，其他地方有描述。

当其他人（如你的 TA）试图理解你的 Java 代码时，他或她通常会首先查看生成的 Javadoc 来弄清楚它的作用。因此，重要的是你自己检查生成的 HTML，以确保它清楚准确地传达了你代码的合约。

## TODO 注释

如果你想给自己留个关于需要修复的代码片段的注释，请在注释前面加上 TODO。你会注意到 TODO 会以粗体显示，如果你执行 Window > Show View > Tasks，那么一个“Tasks”窗口将弹出，其中包含你留给自己的所有 TODO 事项。你可以通过在“Tasks”窗口中双击快速跳转到这些代码点。

## 注释掉代码

有时，你想要临时或永久注释掉一些代码。

Java 有两种写注释的方式：`/*`...`*/` 注释掉注释分隔符之间的所有内容，而 `//` 开始的注释直到行尾结束。你应该使用 `//` 来注释掉代码。保留 `/*`...`*/` 注释用于 Javadoc 注释，在这种情况下，开头标签应该有一个额外的星号：`/**`。

在 Eclipse 中，你可以通过高亮显示区域并按下 **Ctrl+/** 来注释掉一段代码块。在 Eclipse 中使用 **Ctrl+\** 来取消注释代码。

本节的其余部分解释了为什么应该使用行注释，例如 `//` 而不是块注释，例如 `/*`...`*/`：因为块注释不支持嵌套。例如，如果你已经这样做了：

```
String a = "The HUB "; String b = "bites";
/* String b = "brings me happiness"; */
String c = "closes? Nope. Never.";
String d = "doesn't have anywhere to sleep comfortably.";

```

但如果你想要使用块注释注释掉变量 `b` 和 `c` 的创建，你会有：

```
String a = "The HUB ";
/* String b = "bites"; /* String b = "brings me happiness"; */
String c = "closes? Nope. Never.";
*/
String d = "doesn't have anywhere to sleep comfortably.";

```

（已添加的两个块注释字符为红色，新块注释注释掉的代码被下划线划掉。）请注意，这未能注释掉创建 `c` 的语句。而且，由于在 `c` 的定义之后有一个 **`*/`** 悬挂着，所以这段代码将不再编译。现在可能很容易修复，但如果你注释了一大块代码，找到导致编译错误的嵌套块注释可能会很麻烦。你完全可以通过使用 `//` 注释来避免这种混乱：

```
String a = "The HUB ";
// String b = "bites";
// // String b = "brings me happiness";
// String c = "closes? Nope.  Never.";
String d = "doesn't have anywhere to sleep comfortably.";

```

这也使得取消较小的已注释区域更容易。

## 文档化代码

### 规范级别的注释

**抽象数据类型。** 每个抽象数据类型（类或接口）都应具有：

1.  一个**概述**部分，简要解释该类型对象代表什么以及它们是否可变。

1.  一个**规范字段列表**。可能只有一个；例如，一个集合可能有表示元素集的字段*elems*。每个字段应具有名称、类型和简短解释。您可能会发现定义额外的**派生字段**会更容易编写方法的规范；对于这些字段中的每一个，您应指出它是派生的，并说明它是如何从其他字段中获得的。可能会有**规范不变量**来约束规范字段的可能值；如果有的话，您应该指定它们。

**方法规范。** 所有类的公共方法都应有规范；复杂的私有方法也应该被指定。 方法规范应遵循课程资料中描述的*requires, modifies, throws, effects, returns*结构。请注意，在 CSE 331 中，除非另有规定，否则可以假定参数为非空。

### 实现级别的注释

**实现注意事项。** 类注释应包括以下元素：

1.  一个将每个规范字段定义为表示字段的**抽象函数**。抽象函数仅对抽象数据类型的类是必需的，对于异常或某些 GUI 小部件等类则不是必需的。

1.  一个**表示不变量**。对于任何具有表示的类（例如，不是大多数异常），都需要 RI。我们强烈建议您在可能的情况下在`checkRep()`方法中测试不变量。请注意，在您的不变量中包含关于什么可以和不能为 null 的假设。

1.  对于具有复杂表示的类，解释**表示选择**（也称为**表示原理**）的说明：做出了什么权衡，考虑了什么替代方案并拒绝了（以及为什么）。

**运行时断言。** 应该谨慎使用，如讲座中所解释的。有关运行时断言如何提高代码质量的更长讨论，请参阅 Steve Maguire 的《编写可靠代码》，Microsoft Press，1995 年。
