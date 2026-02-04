# 继承

> 原文：[`courses.physics.illinois.edu/cs225/sp2019/notes/inheritance/`](https://courses.physics.illinois.edu/cs225/sp2019/notes/inheritance/)

返回笔记 by Nathan Walters

*已经了解了继承的基础？可以直接跳转到继承在 C++中的应用，C++中的多态，切片，`virtual`关键字，或者虚拟方法工作的高级描述。*

*## 继承的动机

*继承*，与*封装*、*抽象*和*多态*一样，是面向对象编程的支柱之一。继承让新的类可以从现有类中借用或*继承*功能。这让我们避免了在不同但相关的类之间共享功能时的功能重复。你还可以指定新的实现，同时保持现有类的相同接口。

## 术语

当我们使用继承时，我们说一些新的类应该继承现有类的成员。我们将现有类称为*基类*，而新类是*派生类*。你有时会听到派生类被称为*子类*，基类可以称为*父类*或*超类*。

继承指定了一个*is-a*关系。考虑水果：Honeycrisp *is-a* 苹果，苹果 *is-a* 水果。这样的关系是传递性的：Honeycrisp *is-a* 水果。

## C++中的继承

```c
#include <string> 
class Fruit {
  public:
    virtual std::string getName() = 0;
};

class Apple : public Fruit {
  public:
    std::string getName() {
      return "Apple";
    }
    virtual std::string getVariety() = 0;
};

class Honeycrisp : public Apple {
  public:
    std::string getVariety() {
      return "Honeycrisp";
    }
}; 
```

上面我们的水果例子看起来是这样的；让我们来分析一下。

#### `Fruit`类

这个类声明应该看起来与您习惯看到的不同一些，尤其是这一行：

```c
virtual std::string getVariety() = 0; 
```

这行代码意味着`getVariety()`是一个*纯虚函数*。也就是说，`Fruit`类没有提供`getVariety()`函数的实现；子类必须提供实现。如果一个类有一个纯虚函数，我们称这个类为*抽象类*。这意味着我们不能实例化这个类的实例。考虑以下代码：

```c
#include <iostream> 
// Class definitions would go here...

int main() {
  Fruit f;
  std::cout << f.getName() << std::endl;
} 
```

如果我们尝试编译这段代码，编译器会抱怨我们试图实例化一个抽象类：

```c
main.cpp:6:9: error: variable type 'Fruit' is an abstract class
  Fruit f;
        ^ 
```

#### `Apple`类

这里我们看到了继承的第一个例子！看看`Apple`类是如何声明的：

```c
class Apple : public Fruit {
  ...
} 
```

这是我们如何在 C++中声明一个类为另一个类的子类。`public`是一个访问修饰符，它指定了基类公共或受保护成员的访问规则。这里可以使用三种访问修饰符：

+   `public`：对于一个作为`public`基类派生的子类，基类中的任何`public`成员在派生类中将是`public`，基类中的任何`protected`成员在派生类中将是`protected`。

+   `protected`：对于一个作为`protected`基类派生的子类，基类中的任何`public`或`protected`成员在派生类中将是`protected`。

+   `private`: 对于从`private`基类派生的子类，基类中的任何`public`或`protected`成员在派生类中将是`private`的。

注意，子类永远不能访问其父类中的任何私有成员。

`Apple`类实现了从`Fruit`类继承的`getName()`函数。但我们仍然不能实例化一个`Apple`对象！`Apple`类还有一个纯虚函数：`getVariety()`。这意味着`Apple`也是一个抽象类。

#### `Honeycrisp`类

这是我们的例子中的最后一个类。它从`public Apple`派生，并实现了`getVariety()`。这意味着`Honeycrisp`**不是**一个抽象类。所以我们可以最终做一些有用的事情！

```c
Honeycrisp h;
std::cout << "My name is " << h.getName() << std::endl;
std::cout << "I am a " << h.getVariety() << std::endl; 
```

如果我们运行上面的代码，我们会看到以下输出：

```c
My name is Apple
I am a Honeycrisp 
```

## C++中的多态性

我们现在看到了一个如何在 C++中声明派生类的例子。但我们还没有真正能够对它们做任何有用的事情！为了展示继承的用途，我们需要引入另一个概念：*多态性*。多态性是使用单个接口来处理不同类型的对象。在我们的水果例子中，由`Fruit`确定的接口适用于`Apple`和`Honeycrisp`：两者也都有一个`getName()`方法。`Apple`接口也适用于`Honeycrisp`，因为它有一个`getVariety()`方法。

让我们添加另一个类来展示继承是如何对我们有用的。

```c
class RedDelicious : public Apple {
  public:
    std::string getVariety() {
      "Red Delicious (an objectively bad cultivar)";
    }
} 
```

现在，让我们定义一个函数来打印苹果的类型：

```c
void printType(Apple *apple) {
  std::cout << "This apple is a " << apple->getVariety() << std::endl;
} 
```

我们现在可以使用这个函数来打印我们可能拥有的任何`Apple`的类型！

```c
Honeycrisp h;
RedDelicious rd;
printType(&h);
printType(&rd); 
```

运行上面的代码会产生以下输出：

```c
This apple is a Honeycrisp
This apple is a Red Delicious (an objectively bad cultivar) 
```

注意我们是如何通过指针将`Apple`传递给`printType`的。这是很重要的！记住`Apple`是一个抽象类；如果我们尝试按值传递，我们需要创建一个新的`Apple`实例，但我们不能这样做！但是，拥有一个抽象类的指针类型，如`Fruit *`或`Apple *`，是完全可行的。

我们也可以将函数写成接受引用的形式：

```c
void printType(Apple &apple) {
  std::cout << "This apple is a " << apple.getVariety() << std::endl;
} 
```

我们的功能调用看起来大致相同，只是这次我们不需要取地址`h`或`rd`：

```c
Honeycrisp h;
RedDelicious rd;
printType(h);
printType(rd); 
```

## 切片

在上面的水果例子中，我们无法声明一个接受超类参数的函数，因为所有的超类都是抽象的。让我们考虑一个不同的例子，它可以展示使用继承类时的一个陷阱。

```c
#include <iostream> 
class A {
  public:
  void sayHello() {
    std::cout << "Hello from the base class!" << std::endl;
  }
};

class B : public A {
  public:
  void sayHello() {
    std::cout << "Hello from the derived class!" << std::endl;
  }
};

void printHelloMessage(A a) {
  a.sayHello();
}

int main() {
  A a;
  B b;
  printHelloMessage(a);
  printHelloMessage(b);
} 
```

我们可能期望上面的代码打印以下输出：

```c
Hello from the base class!
Hello from the derived class! 
```

但实际上打印出来的内容如下：

```c
Hello from the base class!
Hello from the base class! 
```

这可能有些令人惊讶！让我们看看发生了什么。

首先要注意的是，`printHelloMessage` 函数通过 *值* 接收一个 `A` 对象。记住，当一个对象通过值传递时，会创建原始对象的一个副本。因此，当我们将 `B` 类的实例传递给一个接收 `A` 类的值参数的函数时，我们实际上是将 `B` 类的实例复制到一个 `A` 类的实例中。但是，为该 `A` 类实例分配的内存没有任何空间来记住它最初是一个 `B` 类的实例。由于 `A` 类有自己的 `sayHello` 定义，所以最终使用的是这个定义。

我们称这为 *切片*，因为当我们将其复制到其超类的一个实例中时，关于它是子类实例的信息就丢失了。

我们如何避免这个问题？你已经在上一节中看到了答案！如果我们通过指针或引用传递对象，当函数被调用时就不需要复制对象。相反，在运行时查找指针指向的实际类型，以便调用正确的成员函数。

带着这个知识，让我们稍微修改一下我们的代码：

```c
void printHelloMessage(A &a) {
  a.sayHello();
}

int main() {
  A a;
  B b;
  printHelloMessage(a);
  printHelloMessage(b);
} 
```

让我们看看新代码会打印什么。

```c
Hello from the base class!
Hello from the base class! 
```

嗯。还不是我们想要的！结果发现我们还缺少一个部分。

## `virtual` 关键字

当我们有一个基类的指针时，编译器默认不知道它需要查看子类以获取基类函数的不同实现。在上面的 `A`/`B` 示例中，我们发现自己正处于这种情况下：`B` 提供了与 `A` 不同的 `sayHello()` 实现方式。为了告诉编译器子类可能会覆盖一个函数，我们可以使用 `virtual` 关键字。让我们再次修改我们的代码：

```c
#include <iostream> 
class A {
  public:
  virtual void sayHello() {
    std::cout << "Hello from the base class!" << std::endl;
  }
};

class B : public A {
  public:
  void sayHello() {
    std::cout << "Hello from the derived class!" << std::endl;
  }
};

void printHelloMessage(A &a) {
  a.sayHello();
}

int main() {
  A a;
  B b;
  printHelloMessage(a);
  printHelloMessage(b);
} 
```

我们这次唯一的改变是在 `A` 中 `sayHello()` 成员函数的定义前添加了 `virtual` 关键字。现在，如果我们运行我们的代码，我们会看到我们终于得到了我们一直在寻找的输出：

```c
Hello from the base class!
Hello from the derived class! 
```

哈哈！

如果你注意到了，你将记得你已经在讨论水果示例时看到了 `virtual` 关键字。我们声明 `Food` 具有一个纯虚的 `getName()` 函数：

```c
virtual std::string getName() = 0; 
```

`virtual` 关键字的含义在这里是相同的：它告诉编译器“嘿，当你尝试在某个 `Food` 对象的指针上调用这个函数时，确保你在子类中查找更具体的实现！”`= 0` 只是告诉编译器 `Food` 类肯定没有提供这个函数的实现。

注意，你只需要在“最基”类中添加 `virtual` 关键字——也就是说，在继承层次结构中函数首次出现的那一个类。在水果示例的上下文中，我们甚至可以在 `Honeycrisp` 类中提供一个 `getName()` 的实现，即使中间的 `Apple` 类没有重新声明 `virtual std::string getName()` 函数。

如果你好奇`virtual`关键字是如何工作的，请继续阅读！这是高级内容，所以考试中不会对此进行测试。尽管如此，这仍然很有趣（或者至少，我认为是这样）。

## 奖励内容：虚方法是如何工作的？

*以下部分是超出本课程范围的高级内容。然而，如果你对 C++在较低级别的工作原理感到好奇，这仍然很有趣。*

*首先，让我们简要介绍一下 C++中函数的实现方式（其中一些可能有点模糊不清；不要责怪我，ECE 专业的同学们！）。这假设你对计算机的工作原理有初步的了解（指令是什么，它们是如何执行的，以及内存是如何工作的）。

函数本质上是一系列操作某些数据的指令序列。记住，指令也是数据；这意味着它们在内存中也有自己的位置。这给了我们一些有趣的东西：我们可以有一个指向函数的指针！这在这里得到了说明：

```c
#include <iostream> 
void sayHello() {
  std::cout << "Hello, world!" << std::endl;
}

int main() {
  // Declare a variable "funcPointer" that can hold a poitner
  // to a function that takes zero arguments and returns nothing
  void (*funcPointer)();
  // Assign sayHello to funcPointer
  funcPointer = sayHello;
  // Tell the runtime to interpret "funcPointer" as a void*, which we can then
  // print to see the address of the function
  std::cout << reinterpret_cast<void*>(funcPointer) << std::endl;
  // We can even "call" a function pointer!
  funcPointer();
} 
```

当运行此代码时，将打印以下输出。请注意，`funcPointer`的地址（`0x400830`）可能取决于你正在使用的机器。

```c
0x400830
Hello, world! 
```

当一个方法被声明为`virtual`时，编译器会为该类添加一个指向该函数的指针到所谓的*虚方法表*。这些函数对于该类的所有实例都是相同的，因此相同的表将用于所有实例。

接下来，当你实例化一个具有虚方法的对象时，会为该对象添加一个指向虚方法表的指针作为隐藏成员。这个指针被称为*虚表指针*、*vpointer*，或者简称为*VPTR*。现在，当你尝试在具有虚方法的对象上调用函数时，编译器将使用 VPTR 来查找在运行时实际要调用的实现！

让我们通过上面的`A`/`B`代码的具体例子来分析一下。为了方便起见，这里再次列出：

```c
#include <iostream> 
class A {
  public:
  virtual void sayHello() {
    std::cout << "Hello from the base class!" << std::endl;
  }
};

class B : public A {
  public:
  void sayHello() {
    std::cout << "Hello from the derived class!" << std::endl;
  }
};

void printHelloMessage(A &a) {
  a.sayHello();
}

int main() {
  A a;
  B b;
  printHelloMessage(a);
  printHelloMessage(b);
} 
```

当编译器为对象`b`创建空间时，它将包括指向`B`类虚方法表的指针，该表包括打印“Hello from the derived class!”的`sayHello()`实现。当我们调用`printHelloMessage()`时，将使用虚表指针来确定要调用的函数的正确版本。

许多人问为什么 C++中的方法默认不是虚拟的，就像 Java 或其他语言中那样。一个原因是 C++非常注重效率和速度。如果一个方法永远不会被子类覆盖，编译器可以跳过生成在运行时查找正确函数的代码。这意味着生成的代码将运行得更快！所以，除非你明确选择使用`virtual`关键字来启用此行为，否则 C++默认会做快速、高效的事情。

这只是一个关于其工作原理的概述；[维基百科](https://en.wikipedia.org/wiki/Virtual_method_table)提供了对虚方法的更全面了解。如果你对此感兴趣，不妨查看一下！**
