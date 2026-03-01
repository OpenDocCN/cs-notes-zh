# Java编程和软件工程基础：2-5：使用封装重写凯撒密码 🛡️

![](img/f5f757a9803ae4844d5959e4f9866535_0.png)

在本节课中，我们将学习面向对象编程中的一个核心概念：**封装**。我们将通过重写一个已有的凯撒密码程序，来展示如何将代码组织得更具面向对象特性，使其更易于管理和理解。

## 课程概述

上一节我们介绍了面向对象编程的基本思想。本节中，我们来看看如何将一段过程式的代码，通过封装数据和方法，改造成一个更清晰、更易于复用的对象。

## 原有代码回顾

首先，回顾一下之前课程中编写的用于凯撒密码加密的代码。这段代码是一个方法，它接收两个参数：待加密的信息和加密密钥。

```java
public String encrypt(String input, int key) {
    // 基于密钥计算移位后的字母表
    String alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    String shiftedAlphabet = alphabet.substring(key) + alphabet.substring(0, key);
    // ... 其余加密逻辑
}
```

如你所见，该方法首先根据传入的密钥 `key` 来计算移位后的字母表 `shiftedAlphabet`。

## 面向对象方式的重写

现在，我们来看一种不同的、更具面向对象特性的凯撒密码类实现方式。它完成相同的功能，但更好地利用了Java的对象特性。

这个类包含两个**字段**。字段是一种特殊的变量，它存在于对象内部，而不是方法内部。

```java
public class CaesarCipher {
    // 字段：存在于对象内部
    private String alphabet;
    private String shiftedAlphabet;

    // ... 其他代码
}
```

在这里，两个字段分别是原始字母表 `alphabet` 和移位后的字母表 `shiftedAlphabet`。它们被移到了 `encrypt` 方法之外。注意，它们现在被声明在类内部，但在任何方法外部。这些数据现在被**封装**在你的对象中。当你创建一个 `CaesarCipher` 对象时，它将拥有这两个字段，类内部的任何代码都可以通过名称引用它们。

接下来，注意一段看起来像方法的代码，它没有写返回类型，并且名字与类名相同。

```java
public class CaesarCipher {
    private String alphabet;
    private String shiftedAlphabet;

    // 构造函数
    public CaesarCipher(int key) {
        alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
        shiftedAlphabet = alphabet.substring(key) + alphabet.substring(0, key);
    }

    // ... 其他代码
}
```

这段代码实际上是一个**构造函数**。构造函数是在使用 `new` 关键字创建对象时，用于初始化对象的代码。这个构造函数接收密钥 `key` 作为参数，并使用与你之前相同的方法来初始化 `alphabet` 和 `shiftedAlphabet` 字段。

如果你继续往下看这个凯撒密码的实现，`encrypt` 方法看起来和之前大部分相同，但它不再将密钥 `key` 作为参数，也不再计算移位字母表。

![](img/f5f757a9803ae4844d5959e4f9866535_2.png)

```java
public String encrypt(String input) {
    StringBuilder encrypted = new StringBuilder(input);
    for (int i = 0; i < encrypted.length(); i++) {
        char currChar = encrypted.charAt(i);
        // 使用对象内部的 alphabet 和 shiftedAlphabet 字段进行加密
        int idx = alphabet.indexOf(Character.toUpperCase(currChar));
        if (idx != -1) {
            char newChar = shiftedAlphabet.charAt(idx);
            // ... 大小写处理逻辑
            encrypted.setCharAt(i, newChar);
        }
    }
    return encrypted.toString();
}
```

![](img/f5f757a9803ae4844d5959e4f9866535_3.png)

方法的其余部分保持不变。实际上，这段代码使用了对象中的 `alphabet` 和 `shiftedAlphabet` 字段，尽管它们没有在方法内部声明。因为该方法位于对象内部，所以允许使用对象内的任何字段。

## 两种方式的对比图解

一个图示有助于理解这两种方法之间的区别。

![](img/f5f757a9803ae4844d5959e4f9866535_5.png)

在旧代码中，一个凯撒密码对象不持有任何数据。当你执行 `new CaesarCipher()` 时，你不传递任何参数，创建的是一个空对象。当你调用 `encrypt` 时，你需要传递信息和密钥，然后方法返回加密后的信息。

```
旧方式：
对象: [空]
调用: encrypt(信息, 密钥) -> 返回加密信息
```

在新方式中，每个凯撒密码对象内部都封装了一个密钥。现在，当你执行 `new CaesarCipher(密钥)` 时，你传入密钥，创建的对象会将这个密钥存储在其内部。当你在此类对象上调用 `encrypt` 时，你只需传入信息。密钥已经存在于对象中，它仍然会返回与之前相同的加密信息。

![](img/f5f757a9803ae4844d5959e4f9866535_7.png)

```
新方式：
对象: [存储了密钥]
调用: encrypt(信息) -> 返回加密信息
```

## 封装的优势

既然这两种实现方式产生相同的结果，那么面向对象方法有什么好处呢？

当你将密钥封装在密码对象内部时，你就得到了一个能够接收信息并对其进行加密的独立实体。这构成了一个思考“执行任务的事物”的良好逻辑单元。你不需要单独跟踪密钥并传递它。

对于你目前编写的小型程序来说，这可能看起来没什么大不了的。然而，当你解决代码更复杂的大型程序时，这种设计思想将对你大有裨益。

## 本节总结

![](img/f5f757a9803ae4844d5959e4f9866535_9.png)

本节课中，我们一起学习了如何通过**封装**来改进代码结构。我们通过将凯撒密码的密钥和移位字母表作为对象的**字段**，并使用**构造函数**进行初始化，使得加密逻辑更清晰，对象职责更单一。这种设计使得代码模块化程度更高，更易于维护和扩展，是面向对象编程的核心优势之一。