Java全栈开发：06：向上转型与向下转型详解 🚗

![](img/f5b4790d7014fadb9f8115d4a10da7e2_0.png)

在本节课中，我们将通过实际代码演示，学习Java中向上转型与向下转型的概念、区别与具体实现。理解这两个概念对于掌握继承和多态至关重要。

---

![](img/f5b4790d7014fadb9f8115d4a10da7e2_2.png)

上一节我们介绍了继承的基本概念，本节中我们来看看类型转换在继承关系中的具体应用。

考虑以下场景：我们有一个`Vehicle`（车辆）基类和一个继承自它的`Car`（汽车）子类。

```java
class Vehicle {
    void drive() {
        System.out.println("Driving the vehicle.");
    }
}

class Car extends Vehicle {
    @Override
    void drive() {
        System.out.println("Driving a car.");
    }

    void speedUp() {
        System.out.println("Speeding up a car.");
    }
}
```

---

### 向上转型详解

向上转型是将子类引用转换为父类引用的过程。这个过程是安全的，并且可以由Java编译器隐式完成。

以下是向上转型的步骤：
1.  创建子类对象。
2.  将其引用赋值给父类类型的变量。
3.  通过父类引用调用方法，实际执行的是子类重写的方法。

```java
public class Main {
    public static void main(String[] args) {
        // 向上转型：Car对象被赋值给Vehicle引用
        Vehicle vehicle = new Car();
        vehicle.drive(); // 输出: Driving a car.
    }
}
```
在这个例子中，`vehicle`引用是`Vehicle`类型，但它指向一个`Car`对象。调用`drive()`方法时，执行的是`Car`类中重写的版本。这就是多态的体现。

---

### 向下转型详解

向下转型是将父类引用显式转换回子类引用的过程。这个过程不是类型安全的，必须由程序员显式进行，并且可能在运行时引发`ClassCastException`异常。

以下是向下转型的必要条件和步骤：
1.  前提是父类引用实际指向的是一个子类对象。
2.  使用强制类型转换语法 `(子类名)` 进行转换。
3.  转换成功后，可以访问子类特有的成员。

```java
public class Main {
    public static void main(String[] args) {
        // 首先进行向上转型
        Vehicle vehicle = new Car();

        // 向下转型：将Vehicle引用显式转换回Car引用
        Car car = (Car) vehicle;
        car.drive();    // 输出: Driving a car.
        car.speedUp();  // 输出: Speeding up a car.
    }
}
```
**注意**：如果`vehicle`引用最初指向的不是`Car`对象（例如指向另一个`Vehicle`子类或`Vehicle`本身），那么向下转型将会失败。

---

### 核心区别与总结

本节课中我们一起学习了向上转型与向下转型。

*   **向上转型**：子类 -> 父类。安全，可隐式进行。用于实现多态，让代码更通用。
*   **向下转型**：父类 -> 子类。不安全，必须显式进行。用于访问子类特有功能，使用前需确保类型正确。

![](img/f5b4790d7014fadb9f8115d4a10da7e2_4.png)

简单来说，**向上转型是“看作更通用的类型”，而向下转型是“还原回具体的类型”**。理解并正确运用这两种转型，是灵活使用Java面向对象特性的关键。