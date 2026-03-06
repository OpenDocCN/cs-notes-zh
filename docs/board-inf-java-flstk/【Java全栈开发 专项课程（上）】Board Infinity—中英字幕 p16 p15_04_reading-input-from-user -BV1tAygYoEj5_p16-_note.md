# Java全栈开发：P16：从用户读取输入 👨‍💻

![](img/a83fc63e660aa179cab8a840142746aa_0.png)

在本节课中，我们将学习如何在Java程序中读取用户的输入。这是任何程序不可或缺的一部分，因为只有用户能够根据自己的需求输入数据，程序才能满足其要求。Java提供了多种读取输入的方式，我们将重点介绍最常用的`Scanner`类。

## 为什么需要读取用户输入？🤔

读取用户输入是程序与用户交互的基础。它允许程序根据用户提供的数据执行不同的操作，从而使程序更加动态和实用。

## Java中读取输入的三种方式

![](img/a83fc63e660aa179cab8a840142746aa_2.png)

Java提供了三种主要方式来读取输入：
1.  **BufferReader类**
2.  **Scanner类**
3.  **Console类**

本节我们将详细探讨`Scanner`类，因为它是最简单、最广泛使用的方法。

![](img/a83fc63e660aa179cab8a840142746aa_4.png)

## 认识Scanner类 📖

![](img/a83fc63e660aa179cab8a840142746aa_5.png)

`Scanner`类位于`java.util`包中，它扩展了`Object`类。这个类为我们提供了许多便捷的方法，可以将用户输入的数据解析为特定的数据类型。

默认情况下，`Scanner`将输入视为字符串。如果你需要其他类型的数据，可以使用其特定的方法进行转换，无需手动从字符串解析。

## Scanner类的常用方法

以下是`Scanner`类中一些用于读取不同数据类型的方法：

*   **`next()`**: 读取下一个字符串（以空格为分隔符）。
*   **`nextLine()`**: 读取一整行字符串（包括空格）。
*   **`nextInt()`**: 读取一个整数。
*   **`nextDouble()`**: 读取一个双精度浮点数。
*   **`nextBoolean()`**: 读取一个布尔值。
*   **`next().charAt(0)`**: 读取一个字符（通常结合`next()`使用）。

正如你所见，对于每种基本数据类型，`Scanner`都有对应的方法，这使得输入处理变得非常简单。

## 动手实践：使用Scanner类

现在，让我们通过一个实际的例子来看看如何使用`Scanner`类。我们将创建一个程序，读取用户的名字、年龄、性别和联系方式。

首先，我们需要导入`Scanner`类并创建它的一个实例。

```java
import java.util.Scanner; // 导入Scanner类

public class UserInputDemo {
    public static void main(String[] args) {
        // 创建Scanner对象，System.in表示从标准输入（键盘）读取
        Scanner scanner = new Scanner(System.in);
    }
}
```

接下来，我们将提示用户输入信息，并使用`Scanner`的不同方法来读取这些数据。

```java
// 提示用户输入姓名
System.out.print("Enter your name: ");
String name = scanner.nextLine(); // 读取整行，包括空格

// 提示用户输入年龄
System.out.print("Enter your age: ");
int age = scanner.nextInt(); // 读取整数

// 提示用户输入性别（M/F）
System.out.print("Enter your gender (M/F): ");
char gender = scanner.next().charAt(0); // 读取第一个字符

// 提示用户输入联系方式
System.out.print("Enter your contact number: ");
double contactNumber = scanner.nextDouble(); // 读取双精度数

// 打印用户详情
System.out.println("\nUser Details:");
System.out.println("Name: " + name);
System.out.println("Age: " + age);
System.out.println("Gender: " + gender);
System.out.println("Contact Number: " + contactNumber);

scanner.close(); // 关闭scanner
```

运行这个程序，你将能够输入你的信息，并看到程序将它们打印出来。例如：
```
Enter your name: King Kocher
Enter your age: 23
Enter your gender (M/F): M
Enter your contact number: 1234567890

User Details:
Name: King Kocher
Age: 23
Gender: M
Contact Number: 1.23456789E9
```

## Scanner类的优势与总结 🎯

本节课我们一起学习了如何使用`Scanner`类从用户读取输入。`Scanner`类的主要优势在于：
*   **易于实现**：语法简单，易于学习和使用。
*   **类型安全**：提供了直接读取基本数据类型的方法，避免了手动转换的麻烦。
*   **功能强大**：它也支持使用正则表达式来解析更复杂的输入模式。

因此，`Scanner`类不仅是初学者的最佳选择，也因其便捷性常用于解决算法竞赛中的输入问题。它同样可以用于从数据文件中读取记录。

![](img/a83fc63e660aa179cab8a840142746aa_7.png)

![](img/a83fc63e660aa179cab8a840142746aa_8.png)

希望你现在对如何在Java中读取用户输入有了清晰的理解。记住，与用户交互是让程序变得有用的关键一步。