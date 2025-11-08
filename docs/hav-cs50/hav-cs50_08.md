# 第六讲

> 原文：[`cs50.harvard.edu/x/notes/6/`](https://cs50.harvard.edu/x/notes/6/)

+   欢迎！

+   嗨，Python！

+   Speller

+   过滤器

+   函数

+   库、模块和包

+   字符串

+   位置参数和命名参数

+   变量

+   类型

+   计算器

+   条件语句

+   面向对象编程

+   循环

+   抽象

+   截断和浮点数不精确

+   异常

+   马里奥

+   列表

+   搜索和字典

+   命令行参数

+   退出状态

+   CSV 文件

+   第三方库

+   总结

## 欢迎光临！

+   在之前的几周里，你被介绍了编程的基本构建块。

+   你已经学习了一种名为 C 的低级编程语言中的编程。

+   今天，我们将使用一种名为 *Python* 的高级编程语言。

+   随着你学习这门新语言，你会发现你将更有能力自学新的编程语言。

## 嗨，Python！

+   几十年来，人类已经看到在之前的编程语言中做出的设计决策如何得到改进。

+   Python 是一种编程语言，它建立在你在 C 语言中学到的知识之上。

+   Python 还可以访问大量的用户创建的库。

+   与 C 语言不同，C 是一种 *编译语言*，Python 是一种 *解释语言*，你不需要单独编译你的程序。相反，你在 *Python 解释器* 中运行你的程序。

+   到目前为止，代码看起来是这样的：

    ```
    // A program that says hello to the world

    #include <stdio.h>  
    int main(void)
    {
        printf("hello, world\n");
    } 
    ```

+   今天，你会发现编写和编译代码的过程已经简化了。

+   例如，上面的代码在 Python 中将被渲染为：

    ```
    # A program that says hello to the world 
    print("hello, world") 
    ```

    注意，分号已经消失，并且不需要任何库。你可以通过在终端中键入 `python hello.py` 来运行这个程序。

+   Python 可以相对简单地实现 C 语言中相当复杂的功能。

## Speller

+   为了说明这种简单性，让我们在终端窗口中键入‘code dictionary.py’并编写如下代码：

    ```
    # Words in dictionary words = set()

    def check(word):
        """Return true if word is in dictionary else false"""
        return word.lower() in words

    def load(dictionary):
        """Load dictionary into memory, returning true if successful else false"""
        with open(dictionary) as file:
            words.update(file.read().splitlines())
        return True

    def size():
        """Returns number of words in dictionary if loaded else 0 if not yet loaded"""
        return len(words)

    def unload():
        """Unloads dictionary from memory, returning true if successful else false"""
        return True 
    ```

    注意，上面有四个函数。在 `check` 函数中，如果 `word` 在 `words` 中，它返回 `True`。这比 C 语言中的实现简单得多！同样，在 `load` 函数中，字典文件被打开。对于该文件中的每一行，我们将该行添加到 `words` 中。使用 `rstrip`，从添加的单词中移除尾随的新行。`size` 仅返回 `words` 的 `len` 或长度。`unload` 只需要返回 `True`，因为 Python 自己处理内存管理。

+   上述代码说明了为什么存在高级语言：为了简化并允许你更容易地编写代码。

+   然而，速度是一个权衡。因为 C 允许程序员做出关于内存管理的决策，它可能比 Python 运行得更快——这取决于你的代码。当调用 Python 的内置函数时，C 只运行你的代码行，而 Python 运行所有在引擎盖下运行的代码。

+   你可以在[Python 文档](https://docs.python.org/3/library/functions.html)中了解更多关于函数的信息。

## 过滤器

+   为了进一步说明这种简单性，请在你的终端窗口中键入`code blur.py`来创建一个新文件，并编写如下代码：

    ```
    # Blurs an image 
    from PIL import Image, ImageFilter

    # Blur image before = Image.open("bridge.bmp")
    after = before.filter(ImageFilter.BoxBlur(1))
    after.save("out.bmp") 
    ```

    注意，此程序从名为`PIL`的库中导入模块`Image`和`ImageFilter`。它接受一个输入文件并创建一个输出文件。

+   此外，你可以创建一个名为`edges.py`的新文件，如下所示：

    ```
    # Finds edges in an image 
    from PIL import Image, ImageFilter

    # Find edges before = Image.open("bridge.bmp")
    after = before.filter(ImageFilter.FIND_EDGES)
    after.save("out.bmp") 
    ```

    注意，此代码是对你的`blur`代码的微小调整，但产生了截然不同的结果。

+   Python 允许你将 C 和其他*低级*编程语言中更为复杂的编程抽象出来。

## 函数

+   在 C 中，你可能见过如下函数：

    ```
    printf("hello, world\n"); 
    ```

+   在 Python 中，你会看到如下函数：

    ```
    print("hello, world") 
    ```

## 库、模块和包

+   与 C 一样，CS50 库可以在 Python 中使用。

+   以下函数将特别有用：

    ```
     get_float
      get_int
      get_string 
    ```

+   你可以如下导入 cs50 库：

    ```
    import cs50 
    ```

+   你也可以选择仅导入 CS50 库中的特定函数，如下所示：

    ```
    from cs50 import get_float, get_int, get_string 
    ```

## 字符串

+   在 C 中，你可能记得如下代码：

    ```
    // get_string and printf with %s

    #include <cs50.h> #include <stdio.h>  
    int main(void)
    {
        string answer = get_string("What's your name? ");
        printf("hello, %s\n", answer);
    } 
    ```

+   在 Python 中，此代码将转换为：

    ```
    # get_string and print, with concatenation 
    from cs50 import get_string

    answer = get_string("What's your name? ")
    print("hello, " + answer) 
    ```

    你可以通过在终端窗口中执行`code hello.py`来编写此代码。然后，你可以通过运行`python hello.py`来执行此代码。注意`+`符号如何连接`"hello, "`和`answer`。

+   同样，这也可以在不连接的情况下完成：

    ```
    # get_string and print, without concatenation 
    from cs50 import get_string

    answer = get_string("What's your name? ")
    print("hello,", answer) 
    ```

    注意，打印语句自动在`hello`语句和`answer`之间创建一个空格。

+   同样，你可以将上述代码实现为：

    ```
    # get_string and print, with format strings 
    from cs50 import get_string

    answer  = get_string("What's your name? ")
    print(f"hello, {answer}") 
    ```

    注意大括号如何允许`print`函数将`answer`进行插值，使得`answer`出现在其中。`f`是必须的，以便正确地格式化包含`answer`。

## 位置参数和命名参数

+   C 语言中的函数，如`fread`、`fwrite`和`printf`使用位置参数，其中你通过逗号分隔符提供参数。作为程序员，你必须记住哪个参数在哪个位置。这些被称为*位置参数*。

+   在 Python 中，*命名参数*允许你提供参数而不考虑位置性。

+   你可以在[文档](https://docs.python.org/3/library/functions.html#print)中了解更多关于`print`函数的参数。

+   访问该文档，你可能看到如下内容：

    ```
    print(*objects, sep='  ', end='\n', file=None, flush=False) 
    ```

    注意可以提供各种对象来打印。当提供多个对象给 `print` 时，会显示一个空格分隔符。同样，在 `print` 语句的末尾提供一个新行。

## 变量

+   变量声明也得到了简化。在 C 语言中，你可能会有 `int counter = 0;` 这样的代码。在 Python 中，同样的行会写成 `counter = 0`。你不需要声明变量的类型。

+   Python 更倾向于使用 `counter += 1` 来实现加一，失去了 C 语言中 `counter++` 的能力。

## 类型

+   Python 中的数据类型不需要显式声明。例如，你上面看到 `answer` 是一个字符串，但我们不必告诉解释器这一点：它自己就知道。

+   在 Python 中，常用的类型包括：

    ```
     bool
      float
      int
      str 
    ```

    注意到 `long` 和 `double` 类型不见了。Python 会处理更大或更小的数字应该使用哪种数据类型。

+   Python 中还有一些其他的数据类型：

    ```
    range   sequence of numbers
    list    sequence of mutable values
    tuple   sequence of immutable values
    dict    collection of key-value pairs
    set     collection of unique values 
    ```

+   这些数据类型在 C 语言中都可以实现，但在 Python 中可以更简单地实现。

## 计算器

+   你可能还记得课程早期提到的 `calculator.c`：

    ```
    // Addition with int

    #include <cs50.h> #include <stdio.h>  
    int main(void)
    {
        // Prompt user for x
        int x = get_int("x: ");

        // Prompt user for y
        int y = get_int("y: ");

        // Perform addition
        printf("%i\n", x + y);
    } 
    ```

+   我们可以像在 C 语言中一样实现一个简单的计算器。在终端窗口中输入 `code calculator.py` 并编写以下代码：

    ```
    # Addition with int [using get_int] 
    from cs50 import get_int

    # Prompt user for x x = get_int("x: ")

    # Prompt user for y y = get_int("y: ")

    # Perform addition print(x + y) 
    ```

    注意 CS50 库是如何导入的。然后，`x` 和 `y` 从用户那里收集。最后，打印出结果。注意，在 C 程序中通常会看到的 `main` 函数在这里完全消失了！虽然可以使用 `main` 函数，但不是必需的。

+   有可能移除 CS50 库的训练轮。按照以下方式修改你的代码：

    ```
    # Addition with int [using input] 
    # Prompt user for x x = input("x: ")

    # Prompt user for y y = input("y: ")

    # Perform addition print(x + y) 
    ```

    注意执行上述代码会导致程序出现奇怪的行为。这可能是为什么？

+   你可能已经猜到解释器将 `x` 和 `y` 理解为字符串。你可以通过以下方式使用 `int` 函数来修复你的代码：

    ```
    # Addition with int [using input] 
    # Prompt user for x x = int(input("x: "))

    # Prompt user for y y = int(input("y: "))

    # Perform addition print(x + y) 
    ```

    注意 `x` 和 `y` 的输入是如何传递给 `int` 函数的，该函数将其转换为整数。如果不将 `x` 和 `y` 转换为整数，字符将进行连接。

## 条件语句

+   在 C 语言中，你可能记得这样的程序：

    ```
    // Conditionals, Boolean expressions, relational operators

    #include <cs50.h> #include <stdio.h>  
    int main(void)
    {
        // Prompt user for integers
        int x = get_int("What's x? ");
        int y = get_int("What's y? ");

        // Compare integers
        if (x < y)
        {
            printf("x is less than y\n");
        }
        else if (x > y)
        {
            printf("x is greater than y\n");
        }
        else
        {
            printf("x is equal to y\n");
        }
    } 
    ```

+   在 Python 中，它将如下所示：

    ```
    # Conditionals, Boolean expressions, relational operators 
    from cs50 import get_int

    # Prompt user for integers x = get_int("What's x? ")
    y = get_int("What's y? ")

    # Compare integers if x < y:
        print("x is less than y")
    elif x > y:
        print("x is greater than y")
    else:
        print("x is equal to y") 
    ```

    注意到没有更多的花括号。相反，使用缩进来表示。其次，在 `if` 语句中使用冒号。此外，`elif` 替换了 `else if`。在 `if` 和 `elif` 语句中也不再需要括号。

+   进一步查看比较，考虑以下 C 语言的代码：

    ```
    // Logical operators

    #include <cs50.h> #include <stdio.h>  
    int main(void)
    {
        // Prompt user to agree
        char c = get_char("Do you agree? ");

        // Check whether agreed
        if (c == 'Y' || c == 'y')
        {
            printf("Agreed.\n");
        }
        else if (c == 'N' || c == 'n')
        {
            printf("Not agreed.\n");
        }
    } 
    ```

+   这可以按照以下方式实现：

    ```
    # Logical operators 
    from cs50 import get_string

    # Prompt user to agree s = get_string("Do you agree? ")

    # Check whether agreed if s == "Y" or s == "y":
        print("Agreed.")
    elif s == "N" or s == "n":
        print("Not agreed.") 
    ```

    注意到 C 语言中使用的两个竖线被 `or` 替换了。确实，人们通常喜欢 Python，因为它对人类来说更易读。此外，注意 Python 中不存在 `char` 类型。相反，使用 `str` 类型。

+   对这段代码的另一种实现方式可以是使用 *列表*：

    ```
    # Logical operators, using lists 
    from cs50 import get_string

    # Prompt user to agree s = get_string("Do you agree? ")

    # Check whether agreed if s in ["y", "yes"]:
        print("Agreed.")
    elif s in ["n", "no"]:
        print("Not agreed.") 
    ```

    注意我们能够在一个 `list` 中表达多个关键字，如 `y` 和 `yes`。

## 面向对象编程

+   有可能某些类型的值不仅具有属性或属性，还具有函数。在 Python 中，这些值被称为*对象*。

+   在 C 语言中，我们可以创建一个`struct`，在其中可以关联多个变量，形成一个单独的自定义数据类型。在 Python 中，我们也可以这样做，并且还可以在自定义数据类型中包含函数。当一个函数属于特定的*对象*时，它被称为*方法*。

+   例如，Python 中的`strs`有内置的*方法*。因此，你可以按照以下方式修改你的代码：

    ```
    # Logical operators, using lists 
    # Prompt user to agree s = input("Do you agree? ").lower()

    # Check whether agreed if s in ["y", "yes"]:
        print("Agreed.")
    elif s in ["n", "no"]:
        print("Not agreed.") 
    ```

    注意旧的`s`值被`strs`的内置方法`s.lower()`的结果覆盖。

+   同样，你可能还记得我们在 C 语言中是如何复制字符串的：

    ```
    // Capitalizes a copy of a string without memory errors

    #include <cs50.h> #include <ctype.h> #include <stdio.h> #include <stdlib.h> #include <string.h>  
    int main(void)
    {
        // Get a string
        char *s = get_string("s: ");
        if (s == NULL)
        {
            return 1;
        }

        // Allocate memory for another string
        char *t = malloc(strlen(s) + 1);
        if (t == NULL)
        {
            return 1;
        }

        // Copy string into memory
        strcpy(t, s);

        // Capitalize copy
        if (strlen(t) > 0)
        {
            t[0] = toupper(t[0]);
        }

        // Print strings
        printf("s: %s\n", s);
        printf("t: %s\n", t);

        // Free memory
        free(t);
        return 0;
    } 
    ```

    注意代码的行数。

+   我们可以将上述内容用 Python 实现如下：

    ```
    # Capitalizes a copy of a string 
    # Get a string s = input("s: ")

    # Capitalize copy of string t = s.capitalize()

    # Print strings print(f"s: {s}")
    print(f"t: {t}") 
    ```

    注意这个程序与 C 语言中的对应程序相比要短得多。

+   在这个课程中，我们将只触及 Python 的皮毛。因此，随着你继续学习，[Python 文档](https://docs.python.org)将特别重要。

+   你可以在[Python 文档](https://docs.python.org/3/library/stdtypes.html#string-methods)中了解更多关于字符串方法的信息。

## 循环

+   Python 中的循环与 C 语言非常相似。你可能还记得以下 C 语言的代码：

    ```
    // Demonstrates for loop

    #include <stdio.h>  
    int main(void)
    {
        for (int i = 0; i < 3; i++)
        {
            printf("meow\n");
        }
    } 
    ```

+   `for`循环在 Python 中可以这样实现：

    ```
    # Better design 
    for i in range(3):
        print("meow") 
    ```

    注意，`i`从未被明确使用。然而，Python 会自动增加`i`的值。

+   此外，`while`循环可以这样实现：

    ```
    # Demonstrates while loop 
    i = 0
    while i < 3:
        print("meow")
        i += 1 
    ```

+   为了进一步加深我们对 Python 中循环和迭代的理解，让我们创建一个新的文件，命名为`uppercase.py`，如下所示：

    ```
    # Uppercases string one character at a time 
    before = input("Before: ")
    print("After: ", end="")
    for c in before:
        print(c.upper(), end="")
    print() 
    ```

    注意`end=`是如何用于传递参数给`print`函数，以继续行而不添加换行符。此代码一次传递一个字符串。

+   阅读文档后，我们发现 Python 有一些方法可以应用于整个字符串，如下所示：

    ```
    # Uppercases string all at once 
    before = input("Before: ")
    after = before.upper()
    print(f"After: {after}") 
    ```

    注意`.upper`是如何应用于整个字符串的。

## 抽象

+   正如我们今天早些时候暗示的，你可以通过使用函数和将各种代码抽象到函数中来进一步改进我们的代码。修改你之前创建的`meow.py`代码如下：

    ```
    # Abstraction 
    def main():
        for i in range(3):
            meow()

    # Meow once def meow():
        print("meow")

    main() 
    ```

    注意，`meow`函数抽象掉了`print`语句。此外，注意`main`函数位于文件顶部。在文件底部，调用`main`函数。按照惯例，在 Python 中，你期望创建一个`main`函数。

+   的确，我们可以在函数之间传递变量，如下所示：

    ```
    # Abstraction with parameterization 
    def main():
        meow(3)

    # Meow some number of times def meow(n):
        for i in range(n):
            print("meow")

    main() 
    ```

    注意`meow`现在接受一个变量`n`。在`main`函数中，你可以调用`meow`并向它传递一个值，比如`3`。然后，`meow`在`for`循环中使用`n`的值。

+   阅读上述代码，注意作为 C 程序员，你如何能够相当容易地理解上述代码。虽然某些约定不同，但你之前学到的构建块在这个新的编程语言中非常明显。

## 截断和浮点数不精确

+   回想一下，在 C 语言中，我们遇到了截断，其中一个整数除以另一个整数可能会得到一个不精确的结果。

+   你可以通过修改 `calculator.py` 代码来看到 Python 如何处理这种除法：

    ```
    # Division with integers, demonstration lack of truncation 
    # Prompt user for x x = int(input("x: "))

    # Prompt user for y y = int(input("y: "))

    # Divide x by y z = x / y
    print(z) 
    ```

    注意，执行此代码会产生一个值，但如果你在 `.333333` 后看到更多数字，你会看到我们面临的是 *浮点数不精确性*。不会发生截断。

+   我们可以通过稍微修改我们的代码来揭示这种不精确性：

    ```
    # Floating-point imprecision 
    # Prompt user for x x = int(input("x: "))

    # Prompt user for y y = int(input("y: "))

    # Divide x by y z = x / y
    print(f"{z:.50f}") 
    ```

    注意，这段代码揭示了不精确性。Python 仍然面临这个问题，就像 C 语言一样。

## 异常

+   让我们探索在运行 Python 代码时可能发生的更多异常。

+   按照以下方式修改 `calculator.py`：

    ```
    # Doesn't handle exception 
    # Prompt user for an integer n = int(input("Input: "))
    print("Integer") 
    ```

    注意，输入错误的数据可能会导致错误。

+   我们可以通过修改以下代码来尝试处理和捕获潜在的异常：

    ```
    # Handles exception 
    # Prompt user for an integer try:
        n = int(input("Input: "))
        print("Integer.")
    except ValueError:
        print("Not integer.") 
    ```

    注意，上述代码会反复尝试获取正确的数据类型，并在需要时提供额外的提示。

## 马里奥

+   回想一下几周前我们的挑战，即在马里奥游戏中堆叠三个砖块。

    ![三个垂直砖块](img/537bbb1a37714e6775bba1e32a625cd9.png "马里奥砖块")

+   在 Python 中，我们可以按照以下方式实现类似的功能：

    ```
    # Prints a column of 3 bricks with a loop 
    for i in range(3):
        print("#") 
    ```

    这会打印出一列三个砖块。

+   在 C 语言中，我们有一个 `do-while` 循环的优势。然而，在 Python 中，传统上使用 `while` 循环，因为 Python 没有内置的 `do-while` 循环。你可以在名为 `mario.py` 的文件中按照以下方式编写代码：

    ```
    # Prints a column of n bricks with a loop 
    from cs50 import get_int

    while True:
        n = get_int("Height: ")
        if n > 0:
            break

    for i in range(n):
        print("#") 
    ```

    注意，while 循环是如何用来获取高度的。一旦输入的高度大于零，循环就会中断。

+   考虑以下图像：

    ![四个水平问号砖块](img/4ad7c871af4e8b00a757f25c0d3d9051.png "马里奥砖块")

+   在 Python 中，我们可以通过修改以下代码来实现：

    ```
    # Prints a row of 4 question marks with a loop 
    for i in range(4):
        print("?", end="")
    print() 
    ```

    注意，你可以覆盖 `print` 函数的行为，使其保持在上一行打印的位置。

+   与之前的迭代类似，我们可以进一步简化这个程序：

    ```
    # Prints a row of 4 question marks without a loop 
    print("?" * 4) 
    ```

    注意，我们可以使用 `*` 来重复打印语句，使其重复 `4` 次。

+   那么一大块砖块怎么办？

    ![三乘三的马里奥砖块](img/fea3fbedfa6adcaaef02163ac93e5e41.png "马里奥砖块")

+   要实现上述功能，你可以按照以下方式修改你的代码：

    ```
    # Prints a 3-by-3 grid of bricks with loops 
    for i in range(3):
        for j in range(3):
            print("#", end="")
        print() 
    ```

    注意一个 `for` 循环是如何嵌套在另一个 `for` 循环中的。`print` 语句在每个砖块行的末尾添加一个新行。

+   你可以在 [Python 文档](https://docs.python.org/3/library/functions.html#print) 中了解更多关于 `print` 函数的信息。

## 列表

+   `list` 是 Python 中的一个数据结构。

+   `list` 中有内置的方法或函数。

+   例如，考虑以下代码：

    ```
    # Averages three numbers using a list 
    # Scores scores = [72, 73, 33]

    # Print average average = sum(scores) / len(scores)
    print(f"Average: {average}") 
    ```

    注意，你可以使用内置的 `sum` 方法来计算平均值。

+   你甚至可以利用以下语法从用户那里获取值：

    ```
    # Averages three numbers using a list and a loop 
    from cs50 import get_int

    # Get scores scores = []
    for i in range(3):
        score = get_int("Score: ")
        scores.append(score)

    # Print average average = sum(scores) / len(scores)
    print(f"Average: {average}") 
    ```

    注意，这段代码使用了内置的 `append` 方法来处理列表。

+   你可以在 [Python 文档](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range) 中了解更多关于列表的信息。

+   你也可以在 [Python 文档](https://docs.python.org/3/library/functions.html#len) 中了解更多关于 `len` 的信息。

## 搜索和字典

+   我们还可以在数据结构内进行搜索。

+   考虑一个名为 `phonebook.py` 的程序如下：

    ```
    # Implements linear search for names using loop 
    # A list of names names = ["Yuliia", "David", "John"]

    # Ask for name name = input("Name: ")

    # Search for name for n in names:
        if name == n:
            print("Found")
            break
    else:
        print("Not found") 
    ```

    注意这是如何为每个名字实现线性搜索的。

+   然而，我们不需要遍历列表。在 Python 中，我们可以如下执行线性搜索：

    ```
    # Implements linear search for names using `in` 
    # A list of names names = ["Yuliia", "David", "John"]

    # Ask for name name = input("Name: ")

    # Search for name if name in names:
        print("Found")
    else:
        print("Not found") 
    ```

    注意 `in` 如何用于实现线性搜索。

+   然而，此代码仍有改进空间。

+   回想一下，*字典* 或 `dict` 是键值对的集合。

+   你可以在 Python 中如下实现字典：

    ```
    # Implements a phone book as a list of dictionaries, without a variable 
    from cs50 import get_string

    people = [
        {"name": "Yuliia", "number": "+1-617-495-1000"},
        {"name": "David", "number": "+1-617-495-1000"},
        {"name": "John", "number": "+1-949-468-2750"},
    ]

    # Search for name name = get_string("Name: ")
    for person in people:
        if person["name"] == name:
            print(f"Found {person['number']}")
            break
    else:
        print("Not found") 
    ```

    注意，每个条目都实现了 `name` 和 `number` 的字典。

+   更好的是，严格来说，我们不需要同时使用 `name` 和 `number`。我们可以将此代码简化如下：

    ```
    # Implements a phone book using a dictionary 
    from cs50 import get_string

    people = {
        "Yuliia": "+1-617-495-1000",
        "David": "+1-617-495-1000",
        "John": "+1-949-468-2750",
    }

    # Search for name name = get_string("Name: ")
    if name in people:
        print(f"Number: {people[name]}")
    else:
        print("Not found") 
    ```

    注意，字典是用花括号实现的。然后，`if name in people` 这个语句会搜索 `name` 是否在 `people` 字典中。此外，注意在 `print` 语句中，我们可以使用 `name` 的值来索引 `people` 字典。非常实用！

+   Python 尽力使用其内置搜索实现 *常数时间*。

+   你可以在 [Python 文档](https://docs.python.org/3/library/stdtypes.html#dict) 中了解更多关于字典的信息。

## 命令行参数

+   与 C 语言一样，你还可以利用命令行参数。考虑以下代码：

    ```
    # Prints a command-line argument 
    from sys import argv

    if len(argv) == 2:
        print(f"hello, {argv[1]}")
    else:
        print("hello, world") 
    ```

    注意 `argv[1]` 是使用 *格式化字符串* 打印的，`print` 语句中的 `f` 表示格式化字符串。

+   你可以在 [Python 文档](https://docs.python.org/3/library/sys.html) 中了解更多关于 `sys` 库的信息。

## 退出状态

+   `sys` 库也有内置的方法。我们可以使用 `sys.exit(i)` 来使用特定的退出码退出程序：

    ```
    # Exits with explicit value, importing sys 
    import sys

    if len(sys.argv) != 2:
        print("Missing command-line argument")
        sys.exit(1)

    print(f"hello, {sys.argv[1]}")
    sys.exit(0) 
    ```

    注意使用了点符号来利用 `sys` 的内置函数。

## CSV 文件

+   Python 也内置了对 CSV 文件的支持。

+   按照以下方式修改你的 `phonebook.py` 代码：

    ```
    import csv

    file = open("phonebook.csv", "a")

    name = input("Name: ")
    number = input("Number: ")

    writer = csv.writer(file)
    writer.writerow([name,number])

    file.close() 
    ```

    注意 `writerow` 会为我们添加 CSV 文件中的逗号。

+   虽然 `file.close` 和 `file = open` 是 Python 中常用且可用的语法，但此代码可以如下改进：

    ```
    import csv

    name = input("Name: ")
    number = input("Number: ")

    with open("phonebook.csv", "a") as file:

        writer = csv.writer(file)
        writer.writerow([name,number]) 
    ```

    注意，代码在 `with` 语句下缩进。这会在完成后自动关闭文件。

+   类似地，我们可以在 CSV 文件中如下写入字典：

    ```
    import csv

    name = input("Name: ")
    number = input("Number: ")

    with open("phonebook.csv", "a") as file:

        writer = csv.DictWriter(file, fieldnames=["name", "number"])
        writer.writerow({"name": name, "number": number}) 
    ```

    注意此代码与之前的迭代相当相似，但使用了 `csv.DictWriter`。

## 第三方库

+   Python 的一个优点是其庞大的用户基础和同样庞大的第三方库数量。

+   如果你已经安装了 [Python](https://python.org)，你可以通过输入 `pip install cs50` 在你的电脑上安装 CS50 库。

+   考虑其他库，David 展示了 `cowsay` 和 `qrcode` 的使用。

## 总结

在本节课中，你学习了如何将之前课程中编程的基本构建块在 Python 中实现。此外，你还了解了 Python 如何使代码更加简化。同时，你学习了如何利用各种 Python 库。最后，你了解到作为一名程序员，你的技能并不仅限于单一编程语言。你已经看到，通过这门课程，你正在发现一种新的学习方法，这可以在任何编程语言中为你服务——也许在几乎任何学习领域中都能！具体来说，我们讨论了……

+   Python

+   变量

+   条件语句

+   循环

+   数据类型

+   面向对象编程

+   截断和浮点数不精确

+   异常

+   字典

+   命令行参数

+   第三方库

次次见！
