# 高级C++编程：3：类类型

![](img/d918ba9e763f55bad3f71ae57e77662b_1.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_3.png)

## 概述
在本节课中，我们将要学习C++中的类类型。我们将探讨作用域规则、对象的生命周期、类的定义与使用、构造函数与析构函数、常量成员函数、静态成员以及如何控制编译器自动生成的成员函数。理解这些概念对于掌握C++面向对象编程至关重要。

## 作用域

![](img/d918ba9e763f55bad3f71ae57e77662b_5.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_7.png)

上一节我们介绍了课程安排，本节中我们来看看作用域。

在C++中，当你声明一个变量或任何命名类型（如lambda、字符串对象或基本类型`int`）时，该变量的作用域通常从其定义点开始，直到下一个闭合花括号`}`结束。这个规则适用于函数、`if`语句、`while`语句、`for`语句以及匿名代码块。

![](img/d918ba9e763f55bad3f71ae57e77662b_9.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_11.png)

与C语言风格不同，我们鼓励你在首次使用变量的地方附近定义它，而不是在代码块顶部声明所有变量。这样做可以避免变量拥有超出其所需范围的作用域，使程序更紧凑。

![](img/d918ba9e763f55bad3f71ae57e77662b_13.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_15.png)

以下是关于作用域的几个关键点：
*   变量名在其作用域内有效。
*   相同的变量名可以在不同的作用域中重复使用。
*   每次遇到一个开括号`{`，通常意味着一个新作用域的开始，该作用域在对应的闭括号`}`处结束。

![](img/d918ba9e763f55bad3f71ae57e77662b_17.png)

## 对象与生命周期

上一节我们介绍了作用域，本节中我们来看看对象及其生命周期。

在C++中，几乎所有东西都可以被视为对象。从形式上讲，对象是一块具有特定类型的内存，该类型可以是`int`、`string`或`unordered_set`等。对象生命周期指的是对象从进入作用域（被创建）到离开作用域（被销毁）的整个过程。

![](img/d918ba9e763f55bad3f71ae57e77662b_19.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_20.png)

所有C++对象都有构造和析构的概念。构造函数在对象创建时被调用以进行初始化，析构函数在对象销毁时被调用以进行清理。即使是基本类型（如`int`），在某些上下文中也会被默认构造（例如设置为0）。

对象生命周期的价值在于资源管理。当对象离开其作用域时，其析构函数会被自动调用。对于管理资源的类（如动态分配内存的`vector`或打开文件的`ifstream`），析构函数可以确保资源被正确释放，从而避免内存泄漏或资源泄漏。这并非传统意义上的垃圾回收，而是通过对象的生命周期自动管理其拥有的资源。

![](img/d918ba9e763f55bad3f71ae57e77662b_22.png)

## 命名空间

![](img/d918ba9e763f55bad3f71ae57e77662b_24.png)

上一节我们讨论了对象生命周期，本节中我们简要了解一下命名空间。

![](img/d918ba9e763f55bad3f71ae57e77662b_26.png)

命名空间提供了一种将全局作用域细分为不同命名范围的方法，用于组织代码并避免名称冲突。`std`就是一个标准的命名空间。

你可以使用`namespace`关键字定义命名空间，并使用范围解析运算符`::`来访问其中的成员。

![](img/d918ba9e763f55bad3f71ae57e77662b_28.png)

关于`using`关键字：
*   `using namespace xxx;` 会将指定命名空间中的所有名称引入当前作用域，这可能导致名称污染和歧义，通常不推荐使用。
*   `using xxx::yyy;` 只引入特定名称，相对好一些，但在本课程中仍建议显式使用`xxx::yyy`的形式以保持清晰。

![](img/d918ba9e763f55bad3f71ae57e77662b_30.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_31.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_33.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_35.png)

## 类的基础

![](img/d918ba9e763f55bad3f71ae57e77662b_37.png)

上一节我们介绍了命名空间，本节中我们深入探讨C++类的核心概念。

![](img/d918ba9e763f55bad3f71ae57e77662b_39.png)

类允许我们抽象复杂的代码，并提供清晰的接口（如`std::vector`的`push_back`、`size`等方法），从而分离接口与实现。

![](img/d918ba9e763f55bad3f71ae57e77662b_41.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_42.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_44.png)

类是一种新的类型，使用关键字`class`或`struct`定义。类由**成员函数**（方法）和**数据成员**（字段）组成。类定义中必须包含至少一个`public:`、`protected:`或`private:`访问说明符区域。

![](img/d918ba9e763f55bad3f71ae57e77662b_46.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_48.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_50.png)

**类定义示例**：
```cpp
class MyClass {
 public:
  // 公有成员函数
  int get_val() const { return i_; }
  MyClass(int i) : i_{i} {} // 构造函数

 private:
  // 私有数据成员
  int i_;
};
```
**类使用示例**：
```cpp
auto mc = MyClass{1}; // 创建对象，调用构造函数
std::cout << mc.get_val(); // 调用公有成员函数
// mc.i_ = 5; // 错误：i_ 是私有成员
```
**类定义与实现分离**：
通常，类声明（包含成员函数原型）放在头文件（`.h`）中，而成员函数的定义则放在源文件（`.cpp`）中。在类外定义成员函数时，需要使用类名和作用域解析运算符`::`。
```cpp
// person.h
class Person {
 public:
  Person(const std::string& name, int age);
  const std::string& get_name() const;
  const int& get_age() const;
 private:
  std::string name_;
  int age_;
};

![](img/d918ba9e763f55bad3f71ae57e77662b_52.png)

// person.cpp
#include "person.h"
Person::Person(const std::string& name, int age) : name_{name}, age_{age} {}
const std::string& Person::get_name() const { return name_; }
const int& Person::get_age() const { return age_; }
```

![](img/d918ba9e763f55bad3f71ae57e77662b_54.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_56.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_58.png)

## 构造函数详解

![](img/d918ba9e763f55bad3f71ae57e77662b_60.png)

上一节我们介绍了类的基本结构，本节中我们详细学习构造函数。

![](img/d918ba9e763f55bad3f71ae57e77662b_62.png)

构造函数的职责是初始化对象。其执行流程如下：
1.  按类中声明的顺序，初始化初始化列表中的数据成员。
2.  对于未在初始化列表中出现的、非内置类型的数据成员，进行默认构造。
3.  执行构造函数体。

**初始化列表**：
使用初始化列表（构造函数参数后的`:`开始的部分）直接初始化成员变量，效率更高。它可以避免不必要的默认构造和随后的赋值操作。
```cpp
class MyClass {
 public:
  // 使用初始化列表
  MyClass(int i, int j) : i_{i}, j_{j} {}
  // 对比：在构造函数体内赋值（可能先默认构造，再赋值）
  // MyClass(int i, int j) { i_ = i; j_ = j; }
 private:
  int i_;
  int j_;
};
```
**合成的默认构造函数**：
如果你没有为类定义任何构造函数，编译器会为你合成一个默认构造函数（无参）。但是，一旦你定义了任何构造函数（即使是有参的），编译器就不会再自动生成默认构造函数。此时，如果你需要默认构造函数，必须显式定义它。

![](img/d918ba9e763f55bad3f71ae57e77662b_64.png)

**委托构造函数**：
一个构造函数可以在其初始化列表中调用同一个类的另一个构造函数。
```cpp
class B {
 public:
  B() : B{5} {} // 委托给 B(int) 构造函数
  explicit B(int val) : val_{val} {}
 private:
  int val_;
};
```
**`explicit` 构造函数**：
如果构造函数只有一个参数，编译器允许进行从参数类型到该类类型的隐式转换。使用`explicit`关键字可以禁止这种隐式转换，要求必须显式调用构造函数。
```cpp
class Age {
 public:
  explicit Age(int a) : age_{a} {} // 禁止隐式转换
 private:
  int age_;
};
// Age a1 = 20; // 错误：不能隐式转换
auto a2 = Age{20}; // 正确：显式构造
```

![](img/d918ba9e763f55bad3f71ae57e77662b_66.png)

## 常量成员函数

上一节我们学习了构造函数，本节中我们来看看常量成员函数。

![](img/d918ba9e763f55bad3f71ae57e77662b_68.png)

常量成员函数是指在函数参数列表后加上`const`关键字的成员函数。它们承诺不会修改对象的任何数据成员。

![](img/d918ba9e763f55bad3f71ae57e77662b_70.png)

**规则**：
*   **非常量对象**可以调用常量成员函数和非常量成员函数。
*   **常量对象**只能调用常量成员函数。

![](img/d918ba9e763f55bad3f71ae57e77662b_72.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_74.png)

因此，在设计类时，所有不修改对象状态的成员函数都应该声明为`const`，以确保常量对象也能使用它们。
```cpp
class Person {
 public:
  void set_name(const std::string& name) { name_ = name; } // 非常量函数
  const std::string& get_name() const { return name_; } // 常量函数
 private:
  std::string name_;
};

![](img/d918ba9e763f55bad3f71ae57e77662b_76.png)

int main() {
  auto p1 = Person{"Hayden"};
  p1.set_name("Chris"); // 正确：非常量对象调用非常量函数
  std::cout << p1.get_name(); // 正确：非常量对象调用常量函数

  const auto p2 = Person{"Hayden"};
  // p2.set_name("Chris"); // 错误：常量对象不能调用非常量函数
  std::cout << p2.get_name(); // 正确：常量对象调用常量函数
}
```

## 静态成员

![](img/d918ba9e763f55bad3f71ae57e77662b_78.png)

上一节我们介绍了常量成员函数，本节中我们来看看静态成员。

![](img/d918ba9e763f55bad3f71ae57e77662b_80.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_82.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_84.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_85.png)

静态成员（包括静态数据成员和静态成员函数）属于类本身，而不是类的某个特定对象。它们具有全局生命周期，在程序开始时创建，程序结束时销毁。

静态成员函数不依赖于任何对象的数据成员，因此可以通过类名直接调用，而无需创建对象。
```cpp
class User {
 public:
  static bool valid_name(const std::string& name) {
    // ... 验证逻辑，不访问非静态成员
    return true;
  }
};

// 调用静态成员函数
if (User::valid_name("Santa Claus")) {
  // ...
}
```
静态数据成员通常在类内声明，在类外定义和初始化（除非是`constexpr`）。

![](img/d918ba9e763f55bad3f71ae57e77662b_87.png)

![](img/d918ba9e763f55bad3f71ae57e77662b_89.png)

## 控制默认成员函数

上一节我们学习了静态成员，本节中我们来看看如何控制编译器自动生成的成员函数。

编译器会自动为类合成一些特殊的成员函数，如默认构造函数、拷贝构造函数等。你可以使用`= default`和`= delete`来显式控制这些行为。

![](img/d918ba9e763f55bad3f71ae57e77662b_91.png)

*   `= default`：显式请求编译器生成该函数的默认版本。
*   `= delete`：禁止编译器生成该函数，使得相应的操作（如拷贝）不可用。
```cpp
class MyVector {
 public:
  // 显式请求编译器生成默认构造函数
  MyVector() = default;
  // 禁止拷贝构造函数
  MyVector(const MyVector& other) = delete;

  explicit MyVector(std::vector<int>::size_type length)
      : data_(length, 0) {}

 private:
  std::vector<int> data_;
};

![](img/d918ba9e763f55bad3f71ae57e77662b_93.png)

MyVector v1; // 正确：使用默认构造函数
MyVector v2{v1}; // 错误：拷贝构造函数被删除
```

![](img/d918ba9e763f55bad3f71ae57e77662b_95.png)

## 总结
本节课中我们一起学习了C++类类型的核心知识。我们探讨了作用域规则和对象生命周期，理解了如何通过构造函数和析构函数管理资源。我们学习了如何定义和使用类，包括分离声明与实现、使用初始化列表高效初始化成员。我们还了解了常量成员函数的用途、静态成员的特性，以及如何使用`= default`和`= delete`来控制编译器自动生成的成员函数。掌握这些概念是进行有效C++面向对象编程的基础。