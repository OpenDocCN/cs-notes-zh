# 32：C语言中的多态性

![](img/904f985effe11bd10bc61ac6da1cf1b0_0.png)

在本节课中，我们将继续学习面向对象编程，重点是**多态性**。与上一节在C++中探讨不同，本节我们将学习如何在符合标准的、可移植的C语言中手动实现多态性。这将巩固你对C++虚函数的理解，并揭示虚函数表（VTable）实现的一些额外细节。本节还将提供在嵌入式软件中使用面向对象编程的一些通用原则和指南。

## 概述

![](img/904f985effe11bd10bc61ac6da1cf1b0_2.png)

上一节我们学习了多态性的概念，即子类可以为从基类继承的同一操作提供不同的方法实现。我们了解到，在C++中，这是通过**虚函数**和**虚函数表**机制实现的，它允许在运行时根据对象的实际类型（而非指针的类型）来解析调用，这被称为**后期绑定**。

![](img/904f985effe11bd10bc61ac6da1cf1b0_4.png)

本节中，我们将一步步在C语言中模拟这一机制，包括如何声明虚函数表、设置虚函数指针（VPTR）以及实现后期绑定的调用。我们还将讨论何时应该以及何时不应该使用多态性。

## C语言中实现多态性的步骤

以下是实现C语言多态性的核心步骤，我们将以`Shape`基类和`Rectangle`子类为例进行说明。

### 1. 在基类结构中添加虚函数指针（VPTR）

首先，我们需要在基类（如`Shape`）的属性结构体中显式添加一个指向虚函数表的指针作为第一个成员。

```c
/* shape.h */
typedef struct ShapeVTable ShapeVTable; // 前向声明

typedef struct {
    ShapeVTable const *vptr; /* 虚函数表指针，指向常量区 */
    int16_t x;
    int16_t y;
} Shape;
```

这里我们使用了`ShapeVTable`结构体的前向声明，因为编译器此时只需要知道`vptr`是一个指针的大小。

### 2. 定义虚函数表（VTable）结构

虚函数表本质上是一个结构体，其成员是指向该类所有虚函数的函数指针。

```c
/* shape.h */
struct ShapeVTable {
    void (*draw)(Shape const * const me);
    uint32_t (*area)(Shape const * const me);
};
```

声明函数指针时，需要写出完整的函数签名，并用括号将指针名（如`*draw`）括起来，以确保正确的运算符优先级。

### 3. 实现虚函数调用机制（后期绑定）

为了让用户能够调用虚函数，我们需要提供调用函数。有三种方式可以实现，推荐使用内联函数以降低开销。

**方式一：普通成员函数（有调用开销）**
```c
/* shape.c */
void Shape_draw_vcall(Shape const * const me) {
    (*me->vptr->draw)(me);
}
uint32_t Shape_area_vcall(Shape const * const me) {
    return (*me->vptr->area)(me);
}
```

**方式二：内联函数（C99标准，推荐）**
将函数定义移到头文件中，并添加`static inline`关键字，编译器会尝试内联展开，消除函数调用开销。
```c
/* shape.h */
static inline void Shape_draw_vcall(Shape const * const me) {
    (*me->vptr->draw)(me);
}
static inline uint32_t Shape_area_vcall(Shape const * const me) {
    return (*me->vptr->area)(me);
}
```
使用此方式需确保编译器支持C99模式。

**方式三：宏（兼容C89）**
对于不支持内联的老式编译器，可以使用宏，但类型安全性较差。
```c
#define Shape_draw_vcall(me_) ((*(me_)->vptr->draw)((me_)))
```

无论哪种方式，其核心逻辑都是：通过对象的`me`指针找到其`vptr`，再通过`vptr`找到正确的函数指针并进行调用。`me`指针被使用了两次，确保了调用是针对具体对象而非指针类型的。

### 4. 初始化基类的虚函数表并设置VPTR

虚函数表应作为常量存储在ROM中，并在基类的构造函数中初始化。

```c
/* shape.c */
#include “shape.h”

![](img/904f985effe11bd10bc61ac6da1cf1b0_6.png)

/* 1. 声明虚函数（仅在本模块使用） */
static void Shape_draw(Shape const * const me);
static uint32_t Shape_area(Shape const * const me);

![](img/904f985effe11bd10bc61ac6da1cf1b0_8.png)

/* 2. 定义并初始化常量虚函数表 */
static ShapeVTable const shape_vtable = {
    &Shape_draw,  /* 显式使用取地址运算符 */
    &Shape_area
};

/* 3. 基类构造函数 */
void Shape_ctor(Shape * const me, int16_t x, int16_t y) {
    me->vptr = &shape_vtable; /* 设置VPTR指向Shape的VTable */
    me->x = x;
    me->y = y;
}

/* 4. 基类虚函数实现（可能是空的或默认行为） */
static void Shape_draw(Shape const * const me) {
    (void)me; /* 避免未使用参数警告 */
    /* Shape太抽象，无法绘制 */
}
static uint32_t Shape_area(Shape const * const me) {
    (void)me;
    return 0U;
}
```

### 5. 在子类中重写虚函数表

每个子类都需要提供自己的虚函数表，并在其构造函数中重写从基类继承来的VPTR。

```c
/* rectangle.c */
#include “rectangle.h”
#include “shape.h” /* 为了使用ShapeVTable类型 */

/* 1. 定义并初始化子类常量虚函数表 */
static ShapeVTable const rectangle_vtable = {
    (void (*)(Shape const * const))&Rectangle_draw,   /* 需要强制类型转换 */
    (uint32_t (*)(Shape const * const))&Rectangle_area
};

![](img/904f985effe11bd10bc61ac6da1cf1b0_10.png)

/* 2. 子类构造函数 */
void Rectangle_ctor(Rectangle * const me,
                    int16_t x, int16_t y,
                    uint16_t width, uint16_t height)
{
    /* 首先调用基类构造函数 */
    Shape_ctor(&me->super, x, y);
    /* 然后重写VPTR，指向Rectangle自己的VTable */
    me->super.vptr = &rectangle_vtable;

    /* 初始化子类特有属性 */
    me->width = width;
    me->height = height;
}

/* 3. 子类虚函数的具体实现 */
void Rectangle_draw(Rectangle const * const me) {
    /* 绘制矩形的具体代码 */
}
uint32_t Rectangle_area(Rectangle const * const me) {
    return (uint32_t)me->width * (uint32_t)me->height;
}
```
关键点在于，子类的函数指针签名（接收`Rectangle*`）需要强制转换为基类VTable期望的签名（接收`Shape*`）。并且，必须在调用基类构造函数*之后*再重写`vptr`，因为基类构造函数会将其设置为自己的VTable。

### 6. 使用多态性

现在，我们可以像在C++中一样，使用基类指针来调用子类特有的方法了。

```c
/* main.c */
#include “shape.h”
#include “rectangle.h”

void drawGraph(Shape const *graph[]) {
    uint32_t i;
    for (i = 0U; graph[i] != NULL; ++i) {
        Shape_draw_vcall(graph[i]); /* 多态调用！ */
    }
}

![](img/904f985effe11bd10bc61ac6da1cf1b0_12.png)

int main() {
    Shape s1;
    Rectangle r1;
    Shape *graph[4];

    Shape_ctor(&s1, 10, 20);
    Rectangle_ctor(&r1, 5, 5, 30, 40);

    graph[0] = &s1;        /* 基类对象 */
    graph[1] = (Shape*)&r1; /* 子类对象，需要向上转型 */
    graph[2] = NULL;

    drawGraph(graph); /* 将调用Shape_draw和Rectangle_draw */
    return 0;
}
```

![](img/904f985effe11bd10bc61ac6da1cf1b0_14.png)

## 多态性的替代实现与选择

![](img/904f985effe11bd10bc61ac6da1cf1b0_16.png)

我们上面实现的VPTR/VTable模式是仿照C++的经典方式。在文献和网络中，还存在其他技术。

一种常见的替代方案是**将整个VTable嵌入每个对象**，而不是通过指针间接引用。这样做的好处是虚函数调用语法更简洁（如`me->vtable.draw(me)`），类似于C++的`obj.draw()`。但缺点是显著增加了RAM使用量，因为每个对象都包含一份VTable副本，且VTable位于RAM而非ROM中。当对象数量很多时，内存开销会很大。

在Bruce Powell Douglas所著的《Design Patterns for Embedded Systems in C》一书中，就详细介绍了这种实现方法。

## 何时使用与避免使用多态性

了解多态性的实现后，更重要的是知道何时应用它。

**何时使用多态性：**
当你发现代码中充斥着基于对象类型的`switch`或`if-else`判断时，就应该考虑使用多态性。例如，一个传统的`draw`函数可能如下所示：
```c
void draw_shape(Shape const *s) {
    switch(s->kind) { // kind是一个枚举类型
        case RECTANGLE: draw_rectangle((Rectangle*)s); break;
        case CIRCLE: draw_circle((Circle*)s); break;
        // ... 每增加一种新形状，都要修改这里
    }
}
```
这种代码难以维护，添加或删除形状类型需要修改所有相关判断点。而使用虚函数，只需定义新的子类并实现其虚函数，所有通过基类指针进行的调用都会自动适配，无需修改现有代码，实现了“开闭原则”。

**何时避免使用多态性：**
当对象类型的选择**不需要在运行时决定**时，就不应使用多态性。一个典型的误用场景是管理一系列相似但略有不同的产品线（例如不同型号的医疗设备）。

如果每个产品最终只包含其专属的代码，那么根据产品类型进行的选择应该在**编译时/链接时**完成，而不是运行时。更好的方法是使用**清晰的抽象接口（如板级支持包BSP）**，然后为每个产品提供不同的实现。通过物理设计（代码的目录和文件组织），在链接时为特定产品组合不同的模块。John Lakos的著作《Large-Scale C++ Software Design》对物理设计有极佳的阐述。

滥用运行时多态性来处理本应在编译时解决的问题，会导致代码充满条件逻辑，变得难以管理和测试。

![](img/904f985effe11bd10bc61ac6da1cf1b0_18.png)

![](img/904f985effe11bd10bc61ac6da1cf1b0_19.png)

## 总结

本节课我们一起学习了如何在C语言中手动实现面向对象编程中的**多态性**。我们详细探讨了以下内容：
1.  通过添加**虚函数指针（VPTR）** 和定义**虚函数表（VTable）** 来模拟C++的机制。
2.  实现了**后期绑定**的虚函数调用，并比较了内联函数与宏等不同实现方式的优劣。
3.  在子类构造函数中重写VPTR以指向其自身的VTable，从而确保多态行为。
4.  通过一个通用的`drawGraph`函数演示了多态性的强大之处。
5.  分析了另一种将VTable嵌入对象的实现方案及其权衡。
6.  最后，我们讨论了多态性的适用场景，指出其应用于需要**运行时行为选择**的情况，并警告了在产品线管理等编译时即可确定类型的场景中误用的风险。

![](img/904f985effe11bd10bc61ac6da1cf1b0_21.png)

![](img/904f985effe11bd10bc61ac6da1cf1b0_23.png)

通过本课，你不仅加深了对多态性底层机制的理解，也获得了在嵌入式C项目中应用或判断是否应用这一重要特性的实用指南。下一节课，我们将回归现代嵌入式系统编程的主线，开始学习在20世纪80年代成为主流的另一个重要趋势：**事件驱动编程**。