Java全栈开发：05：接口实战演示与对比

![](img/9836fb2e45dcaa97f6a291175c8dd585_0.png)

在本节课中，我们将通过实际编码来学习接口的实现，并比较接口与抽象类的异同。

![](img/9836fb2e45dcaa97f6a291175c8dd585_2.png)

---

### 概述

我们将创建一个银行账户的接口，并实现它。同时，我们会探讨接口如何支持多重继承，以及它与抽象类的关键区别。

---

### 创建接口与实现类

首先，我们创建一个名为 `IBankAccount` 的接口。在接口中，我们只声明方法的返回类型和名称，不写方法体。默认情况下，接口中的方法都是 `public abstract` 的。

```java
interface IBankAccount {
    void deposit();
    void withdraw();
    void balance();
}
```

接下来，我们创建一个具体的 `SavingAccount` 类来实现这个接口。实现接口时，必须重写接口中所有的抽象方法。

```java
class SavingAccount implements IBankAccount {
    @Override
    public void deposit() {
        System.out.println("Deposit in saving account.");
    }

    @Override
    public void withdraw() {
        System.out.println("Withdraw from saving account.");
    }

    @Override
    public void balance() {
        System.out.println("Balance in saving account.");
    }
}
```

现在，我们可以创建 `SavingAccount` 类的对象，并调用其方法。

```java
public class Main {
    public static void main(String[] args) {
        SavingAccount saving = new SavingAccount();
        saving.deposit();
        saving.withdraw();
        saving.balance();
    }
}
```

---

### 接口与多重继承

上一节我们介绍了如何实现一个简单的接口。本节中我们来看看接口如何实现多重继承。这是抽象类无法做到的。

我们创建另一个接口 `IABCBank`。

```java
interface IABCBank {
    void openAccount();
    void closeAccount();
}
```

现在，我们的 `SavingAccount` 类可以同时实现 `IBankAccount` 和 `IABCBank` 两个接口。

```java
class SavingAccount implements IBankAccount, IABCBank {
    // ... 之前重写的方法

    @Override
    public void openAccount() {
        System.out.println("Open account.");
    }

    @Override
    public void closeAccount() {
        System.out.println("Close account.");
    }
}
```

这种一个类实现多个接口的能力，被称为 **多重继承**。

---

### 接口与抽象类的关键区别

以下是接口与抽象类的一些核心区别：

1.  **实例化**：和抽象类一样，**不能直接创建接口的对象**。尝试 `new IBankAccount()` 会导致编译错误。
2.  **默认方法**：在接口中，如果尝试为一个方法直接提供实现体，编译器会报错。但自 Java 8 起，接口允许使用 `default` 关键字来定义具有默认实现的方法。
    ```java
    interface IABCBank {
        default void welcomeMessage() {
            System.out.println("Welcome to ABC Bank!");
        }
        void openAccount();
        void closeAccount();
    }
    ```
    实现类可以直接使用或重写这个默认方法。
    ```java
    saving.welcomeMessage(); // 输出：Welcome to ABC Bank!
    ```
3.  **设计目的**：抽象类用于建立一种严格的“是一个（is-a）”关系，而接口更侧重于定义一种“能做什么（can-do）”的契约。**接口的契约性比抽象类更强**。

---

### 总结

本节课中我们一起学习了接口的创建与实现。我们了解到：
*   接口使用 `interface` 关键字定义，方法默认是 `public abstract`。
*   类使用 `implements` 关键字来实现接口，并必须重写所有抽象方法。
*   一个类可以实现多个接口，从而实现多重继承。
*   接口不能直接实例化。
*   从 Java 8 开始，接口可以使用 `default` 方法提供默认实现。
*   接口主要用于定义行为契约，在大型应用（如三层架构中的数据访问层）中广泛使用，以实现松耦合设计。

![](img/9836fb2e45dcaa97f6a291175c8dd585_4.png)

希望这些概念对您有所帮助。我们下节课再见。