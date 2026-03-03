# C语言编程：05_02_01：在C语言中实现类似Python的面向对象模式

![](img/b0a68f6384e4e676185efc89df140a19_0.png)

在本节课中，我们将学习如何在C语言中模拟Python的面向对象编程模式。C语言本身并不直接支持面向对象，但我们可以通过结构体、函数指针等特性来构建类似的对象系统。我们将通过创建一个`Point`对象来理解其背后的原理。

上一节我们探讨了Python对象的基本概念，本节中我们来看看如何在C语言中实现类似的功能。

## 构建C语言中的对象

C语言没有内置的面向对象支持。因此，我们需要通过编写函数、使用结构体和指针等方式来模拟。这实际上是在回答一个问题：Python的面向对象层是如何在C语言结构之上构建的？我们可以想象自己处于Guido van Rossum在1991年构建Python时的位置，思考如何让面向对象的语法在底层的C语言中工作。

以下是Python中一个简单的`Point`类示例，我们将以此为目标在C中实现：
```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    def dump(self):
        print(f"Object Point at {self}, x={self.x}, y={self.y}")
    def origin(self):
        return (self.x**2 + self.y**2)**0.5
```

## 定义结构体

我们首先定义一个结构体来代表`Point`对象。这个结构体将包含实例变量（数据）和指向方法的函数指针。

![](img/b0a68f6384e4e676185efc89df140a19_2.png)

![](img/b0a68f6384e4e676185efc89df140a19_3.png)

以下是`Point`结构体的定义：
```c
struct Point {
    double x;
    double y;
    void (*del)(struct Point *self);
    void (*dump)(struct Point *self);
    double (*origin)(struct Point *self);
};
```
*   `double x;` 和 `double y;` 是实例变量，用于存储点的坐标。
*   `void (*del)(struct Point *self);` 是一个指向“析构”函数的指针，用于释放对象内存。
*   `void (*dump)(struct Point *self);` 是一个指向“打印”函数的指针。
*   `double (*origin)(struct Point *self);` 是一个指向“计算到原点距离”函数的指针。

这个结构体在内存中占据固定大小（例如，两个`double`和三个指针，在64位系统上通常是40字节）。C语言的结构体就是一块连续的内存，我们需要预先定义其所有成员。

![](img/b0a68f6384e4e676185efc89df140a19_5.png)

![](img/b0a68f6384e4e676185efc89df140a19_6.png)

## 实现方法函数

接下来，我们实现那些将被结构体中函数指针指向的具体函数。我们遵循一个命名约定，例如为`Point`类的方法加上`point_`前缀。

以下是`dump`方法的实现：
```c
void point_dump(struct Point *self) {
    printf("Object Point at %p, x=%.2f, y=%.2f\n", self, self->x, self->y);
}
```
*   函数名是`point_dump`。
*   第一个参数是`struct Point *self`，它是指向当前对象实例的指针，类似于Python方法中的`self`。
*   在函数内部，我们使用`self->x`和`self->y`来访问实例的变量。`->`操作符用于通过指针访问结构体成员。

以下是`del`方法的实现：
```c
void point_del(struct Point *self) {
    free(self);
}
```
*   这个函数很简单，就是调用`free()`来释放创建对象时分配的内存。

以下是`origin`方法的实现：
```c
double point_origin(struct Point *self) {
    return sqrt(self->x * self->x + self->y * self->y);
}
```
*   这个函数计算点到原点的距离并返回一个`double`值。公式是 **√(x² + y²)**。

## 实现构造函数

![](img/b0a68f6384e4e676185efc89df140a19_8.png)

![](img/b0a68f6384e4e676185efc89df140a19_9.png)

我们需要一个函数来创建并初始化`Point`对象，这相当于Python中的`__init__`方法。

![](img/b0a68f6384e4e676185efc89df140a19_11.png)

![](img/b0a68f6384e4e676185efc89df140a19_12.png)

以下是构造函数的实现：
```c
struct Point *point_new(double x, double y) {
    struct Point *p = malloc(sizeof(struct Point));
    p->x = x;
    p->y = y;
    p->dump = &point_dump;
    p->origin = &point_origin;
    p->del = &point_del;
    return p;
}
```
1.  **分配内存**：使用`malloc`分配一块足以容纳`struct Point`的内存。
2.  **设置数据**：将传入的`x`和`y`参数赋值给新对象的`x`和`y`成员。
3.  **绑定方法**：将对象的函数指针成员（`dump`, `origin`, `del`）指向我们之前定义的全局函数（`point_dump`, `point_origin`, `point_del`）。这里使用了`&`取地址操作符。
4.  **返回对象**：最后返回指向新创建对象的指针。

![](img/b0a68f6384e4e676185efc89df140a19_14.png)

![](img/b0a68f6384e4e676185efc89df140a19_15.png)

本质上，构造函数分配了一块内存，并用数据和函数地址填充它，从而“组装”出一个可用的对象。

![](img/b0a68f6384e4e676185efc89df140a19_17.png)

## 使用对象

在`main`函数中，我们可以像下面这样使用我们创建的`Point`对象：

![](img/b0a68f6384e4e676185efc89df140a19_19.png)

![](img/b0a68f6384e4e676185efc89df140a19_20.png)

```c
int main() {
    // 创建对象
    struct Point *pt = point_new(4.0, 5.0);

    // 调用方法
    pt->dump(pt); // 注意：需要将‘pt’作为参数传入
    double dist = pt->origin(pt);
    printf("Distance to origin: %.2f\n", dist);

    // 清理对象
    pt->del(pt);

    return 0;
}
```
*   `struct Point *pt = point_new(4.0, 5.0);`：这行代码看起来很像面向对象语言中的`new`操作，但实际上它只是调用了一个全局函数`point_new`。
*   `pt->dump(pt);`：这行代码做了两件事：
    1.  `pt->dump`通过指针`pt`找到结构体中的`dump`成员，该成员是一个函数指针。
    2.  `(pt)`则是调用该函数，并将`pt`（即`self`）作为参数传入。这是模拟面向对象调用的关键：**方法函数总是将对象实例作为第一个参数**。
*   `pt->del(pt);`：最后调用析构函数来释放内存。

## 总结与展望

本节课中我们一起学习了如何在C语言中模拟面向对象编程。我们通过以下步骤实现了一个简单的`Point`对象：
1.  定义一个包含数据和函数指针的结构体。
2.  实现一系列全局函数作为“方法”，这些函数的第一个参数都是指向对象实例的指针（`self`）。
3.  实现一个“构造函数”来分配内存并初始化结构体，将函数指针指向对应的全局函数。
4.  通过结构体指针和函数指针的配合来调用“方法”。

![](img/b0a68f6384e4e676185efc89df140a19_22.png)

从本质上讲，这里并没有真正的“对象”，只有结构体、指针和函数。我们利用函数指针和命名约定模仿了面向对象的行为。早期的Python和C++（最初作为C的预处理器）在底层很可能采用了类似的技术来实现其面向对象特性。

![](img/b0a68f6384e4e676185efc89df140a19_24.png)

![](img/b0a68f6384e4e676185efc89df140a19_26.png)

下一节，我们将尝试实现一个简化版的Python字符串类，进一步巩固这种在C语言中构建对象模型的思想。