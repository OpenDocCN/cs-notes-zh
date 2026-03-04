# 164：添加操作或变体

在本节课中，我们将学习如何在函数式编程和面向对象编程中扩展一个表达式语言。我们将探讨添加新操作（如“移除负常数”）和添加新数据类型变体（如“乘法”）的难易程度，并理解不同编程范式对软件可扩展性的影响。

## 概述

上一节我们分别使用面向对象和函数式编程实现了一个表达式语言。本节中，我们将考虑如何扩展这个软件，添加新的功能。具体来说，我们将看到在函数式编程中添加新操作很容易，而添加新数据类型变体则较困难；在面向对象编程中，情况则恰恰相反。

## 函数式编程中的扩展

在函数式编程中，程序通常围绕数据类型进行分解，并为该类型定义各种操作函数。

### 添加新操作

以下是添加一个名为 `noNegConstants` 的新操作的步骤。该操作的目标是预处理表达式，将所有负常数替换为对正数取负的形式。

```ml
fun noNegConstants (e : exp) : exp =
    case e of
        Int i => if i < 0 then Negate(Int(~i)) else e
      | Negate e1 => Negate(noNegConstants e1)
      | Add(e1, e2) => Add(noNegConstants e1, noNegConstants e2)
```

![](img/6d2a0f1dc6c335abff095dfae18d3649_1.png)

添加这个新函数非常简单。它不会影响任何现有的函数（如 `eval`、`toString`、`hasZero`），因为这些函数完全独立。新函数只是对现有数据类型的一个新操作。

### 添加新变体

现在，考虑添加一个新的数据类型变体，例如 `Mult`（乘法）。

![](img/6d2a0f1dc6c335abff095dfae18d3649_3.png)

```ml
datatype exp = Int of int
             | Negate of exp
             | Add of exp * exp
             | Mult of exp * exp (* 新增变体 *)
```

添加这个新变体后，所有处理 `exp` 类型的现有函数（如 `eval`、`toString`、`hasZero`，以及我们刚添加的 `noNegConstants`）都会因为模式匹配不再完备而出现编译错误。在静态类型语言中，类型检查器会明确指出哪些函数需要处理新的 `Mult` 情况。

因此，我们必须返回并修改每一个现有函数，为 `Mult` 添加相应的处理分支。这使得在函数式编程中添加新变体变得相对困难。

## 面向对象编程中的扩展

![](img/6d2a0f1dc6c335abff095dfae18d3649_5.png)

在面向对象编程中，程序通常围绕操作进行分解，每个操作作为一个方法分布在各个类中。

### 添加新变体

以下是添加一个名为 `Mult` 的新变体（新类）的步骤。

```ruby
class Mult
  attr_reader :e1, :e2
  def initialize(e1, e2)
    @e1 = e1
    @e2 = e2
  end
  def eval
    e1.eval * e2.eval
  end
  def toString
    "(#{e1.toString} * #{e2.toString})"
  end
  def hasZero
    e1.hasZero or e2.hasZero
  end
end
```

![](img/6d2a0f1dc6c335abff095dfae18d3649_7.png)

添加这个新类非常容易。由于动态分派机制，现有代码（如 `Add` 类的 `eval` 方法调用其子表达式的 `eval`）可以无缝地与新类 `Mult` 的实例协同工作，无需任何修改。

### 添加新操作

现在，考虑添加一个新的操作，例如 `noNegConstants`。我们需要在现有的所有类（`Int`、`Negate`、`Add`，以及新加的 `Mult`）中都添加这个方法。

```ruby
class Int
  def noNegConstants
    if @i < 0
      Negate.new(Int.new(-@i))
    else
      self
    end
  end
end

class Add
  def noNegConstants
    Add.new(@e1.noNegConstants, @e2.noNegConstants)
  end
end

class Negate
  def noNegConstants
    Negate.new(@e.noNegConstants)
  end
end

# 同样需要在 Mult 类中添加此方法
```

在像Java这样的静态类型面向对象语言中，如果我们在超类中声明了 `noNegConstants` 方法，那么类型检查器会强制所有子类实现它，这为我们提供了与函数式编程中类似的“待办事项”列表。

## 核心对比与总结

本节课中我们一起学习了在两种编程范式下扩展软件的不同特点。

*   **函数式编程**：天然支持**添加新操作**（新函数），但**添加新变体**（修改数据类型）较为困难。
*   **面向对象编程**：天然支持**添加新变体**（新子类），但**添加新操作**（新方法）较为困难。

这个区别源于两者最根本的分解方式：函数式编程按数据类型（列）分解，面向对象编程按操作（行）分解。

## 扩展思考

预测未来的扩展需求非常困难。如果你预期会频繁添加新操作，函数式分解是更自然的选择；如果预期会频繁添加新数据类型，面向对象分解则更合适。

值得注意的是，过度的可扩展性设计可能会增加代码的理解和维护难度。因此，许多编程语言都提供了限制扩展的机制（如ML的模块隐藏、Java的`final`关键字），以便在需要时提供更强的封装和推理保证。

![](img/6d2a0f1dc6c335abff095dfae18d3649_9.png)

最后，存在一些设计模式（如函数式编程中的“其他”用例、面向对象编程中的**访问者模式**）可以预先规划以支持另一种类型的扩展，但这通常会使初始设计更加复杂。