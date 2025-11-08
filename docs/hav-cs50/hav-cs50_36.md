# 第 8 讲

> 原文：[`cs50.harvard.edu/python/notes/8/`](https://cs50.harvard.edu/python/notes/8/)

+   面向对象编程

+   类

+   抛出异常

+   装饰器

+   将课程中的先前工作联系起来

+   类方法

+   静态方法

+   继承

+   继承和异常

+   运算符重载

+   总结

## 面向对象编程

+   编程有不同的范式。当你学习其他语言时，你将开始识别这些模式。

+   到目前为止，你一直是按步骤进行过程式编程的。

+   面向对象编程（OOP）是解决编程相关问题的有力解决方案。

+   首先，在终端窗口中输入`code student.py`，然后按照以下方式编写代码：

    ```
    name = input("Name: ")
    house = input("House: ")
    print(f"{name} from {house}") 
    ```

    注意这个程序遵循的是一种过程式、按步骤的范式：就像你在课程的前几部分看到的那样。

+   借鉴前几周的工作，我们可以创建函数来抽象掉程序的一部分。

    ```
    def main():
        name = get_name()
        house = get_house()
        print(f"{name} from {house}")

    def get_name():
        return input("Name: ")

    def get_house():
        return input("House: ")

    if __name__ == "__main__":
        main() 
    ```

    注意`get_name`和`get_house`如何抽象掉`main`函数的一些需求。此外，注意代码的最后一行是如何告诉解释器运行`main`函数的。

+   我们可以通过将学生存储为`tuple`来进一步简化我们的程序。`tuple`是一系列值。与`list`不同，`tuple`不能被修改。在精神上，我们正在返回两个值。

    ```
    def main():
        name, house = get_student()
        print(f"{name} from {house}")

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return name, house

    if __name__ == "__main__":
        main() 
    ```

    注意`get_student`返回`name, house`。

+   将`tuple`打包，以便我们能够将两个项目返回到名为`student`的变量中，我们可以按如下方式修改我们的代码。

    ```
    def main():
        student = get_student()
        print(f"{student[0]} from {student[1]}")

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return (name, house)

    if __name__ == "__main__":
        main() 
    ```

    注意`(name, house)`明确地告诉阅读我们代码的人，我们在一个返回值中返回两个值。此外，注意我们如何使用`student[0]`或`student[1]`来索引`tuple`。

+   `tuple`是不可变的，这意味着我们无法更改这些值。不可变性是我们进行防御性编程的一种方式。

    ```
    def main():
        student = get_student()
        if student[0] == "Padma":
            student[1] = "Ravenclaw"
        print(f"{student[0]} from {student[1]}")

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return name, house

    if __name__ == "__main__":
        main() 
    ```

    注意，这段代码会产生错误。由于`tuple`是不可变的，我们无法重新分配`student[1]`的值。

+   如果我们想要给其他程序员提供灵活性，我们可以使用`list`如下。

    ```
    def main():
        student = get_student()
        if student[0] == "Padma":
            student[1] = "Ravenclaw"
        print(f"{student[0]} from {student[1]}")

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return [name, house]

    if __name__ == "__main__":
        main() 
    ```

    注意列表是可变的。也就是说，`house`和`name`的顺序可以被程序员切换。你可能会决定在某些需要提供更多灵活性但以代码安全性为代价的情况下使用它。毕竟，如果这些值的顺序可以更改，与你一起工作的程序员可能会在将来犯错误。

+   在这个实现中也可以使用字典。回想一下，字典提供键值对。

    ```
    def main():
        student = get_student()
        print(f"{student['name']} from {student['house']}")

    def get_student():
        student = {}
        student["name"] = input("Name: ")
        student["house"] = input("House: ")
        return student

    if __name__ == "__main__":
        main() 
    ```

    注意在这个例子中，返回了两个键值对。这种方法的优点是我们可以使用键来索引这个字典。

+   尽管如此，我们的代码还可以进一步改进。请注意，存在一个不必要的变量。我们可以移除 `student = {}`，因为我们不需要创建一个空字典。

    ```
    def main():
        student = get_student()
        print(f"{student['name']} from {student['house']}")

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return {"name": name, "house": house}

    if __name__ == "__main__":
        main() 
    ```

    注意我们可以在 `return` 语句中使用 `{}` 大括号来创建字典并在同一行返回它。

+   我们可以在我们的代码字典版本中为 Padma 提供一个特殊案例。

    ```
    def main():
        student = get_student()
        if student["name"] == "Padma":
            student["house"] = "Ravenclaw"
        print(f"{student['name']} from {student['house']}")

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return {"name": name, "house": house}

    if __name__ == "__main__":
        main() 
    ```

    注意，与之前代码的迭代类似，我们可以利用键名来索引我们的学生字典。

## 类

+   在面向对象编程中，类提供了一种创建我们自己的数据类型并为其命名的方法。

+   类就像是一种数据类型的模具——在那里我们可以发明我们自己的数据类型并为其命名。

+   我们可以按照以下方式修改我们的代码来实现我们自己的名为 `Student` 的类：

    ```
    class Student:
        ...

    def main():
        student = get_student()
        print(f"{student.name} from {student.house}")

    def get_student():
        student = Student()
        student.name = input("Name: ")
        student.house = input("House: ")
        return student

    if __name__ == "__main__":
        main() 
    ```

    注意按照惯例，`Student` 是大写的。进一步，注意 `...` 简单地意味着我们将在稍后返回并完成代码的这一部分。进一步，注意在 `get_student` 中，我们可以使用语法 `student = Student()` 创建一个 `Student` 类的 `student`。进一步，注意我们利用“点表示法”来访问这个 `student` 变量的属性。

+   任何时候你创建一个类并利用这个蓝图来创建东西，你就创建了一个“对象”或“实例”。在我们的代码中，`student` 是一个对象。

+   此外，我们可以为期望在类 `Student` 的对象内部拥有的属性打下一些基础。我们可以按照以下方式修改我们的代码：

    ```
    class Student:
        def __init__(self, name, house):
            self.name = name
            self.house = house

    def main():
        student = get_student()
        print(f"{student.name} from {student.house}")

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        student = Student(name, house)
        return student

    if __name__ == "__main__":
        main() 
    ```

    注意在 `Student` 中，我们标准化了这个类的属性。我们可以在 `class Student` 中创建一个函数，称为“方法”，它决定了类 `Student` 的对象的行为。在这个函数中，它接收传递给它的 `name` 和 `house` 并将这些变量分配给这个对象。进一步，注意构造函数 `student = Student(name, house)` 在 `Student` 类中调用这个函数并创建一个 `student`。`self` 指的是刚刚创建的当前对象。

+   我们可以将代码简化如下：

    ```
    class Student:
        def __init__(self, name, house):
            self.name = name
            self.house = house

    def main():
        student = get_student()
        print(f"{student.name} from {student.house}")

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return Student(name, house)

    if __name__ == "__main__":
        main() 
    ```

    注意 `return Student(name, house)` 如何简化了我们之前代码中的迭代，其中构造函数语句单独占一行。

+   你可以在 Python 的[类](https://docs.python.org/3/tutorial/classes.html)文档中了解更多信息。

## `raise`

+   面向对象编程鼓励你将类的所有功能封装在类定义中。如果出了问题怎么办？如果有人输入了随机的数据怎么办？如果有人试图创建一个没有名字的学生怎么办？请按照以下方式修改你的代码：

    ```
    class Student:
        def __init__(self, name, house):
            if not name:
                raise ValueError("Missing name")
            if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
                raise ValueError("Invalid house")
            self.name = name
            self.house = house

    def main():
        student = get_student()
        print(f"{student.name} from {student.house}")

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return Student(name, house)

    if __name__ == "__main__":
        main() 
    ```

    注意我们现在检查是否提供了名字并且指定了合适的宿舍。结果证明我们可以创建自己的异常，通过 `raise` 通知程序员用户可能创建的错误。在上面的例子中，我们使用特定的错误消息引发 `ValueError`。

+   碰巧的是，Python 允许你创建一个特定的函数，通过它可以打印对象的属性。按照以下方式修改你的代码：

    ```
    class Student:
        def __init__(self, name, house, patronus):
            if not name:
                raise ValueError("Missing name")
            if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
                raise ValueError("Invalid house")
            self.name = name
            self.house = house
            self.patronus = patronus

        def __str__(self):
            return f"{self.name} from {self.house}"

    def main():
        student = get_student()
        print(student)

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        patronus = input("Patronus: ")
        return Student(name, house, patronus)

    if __name__ == "__main__":
        main() 
    ```

    注意 `def __str__(self)` 提供了一种在调用时返回学生的方式。因此，现在作为程序员，你可以打印对象、其属性或与该对象相关的几乎所有内容。

+   `__str__` 是 Python 类自带的一个内置方法。碰巧的是，我们也可以为类创建自己的方法！按照以下方式修改你的代码：

    ```
    class Student:
        def __init__(self, name, house, patronus=None):
            if not name:
                raise ValueError("Missing name")
            if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
                raise ValueError("Invalid house")
            if patronus and patronus not in ["Stag", "Otter", "Jack Russell terrier"]:
                raise ValueError("Invalid patronus")
            self.name = name
            self.house = house
            self.patronus = patronus

        def __str__(self):
            return f"{self.name} from {self.house}"

        def charm(self):
            match self.patronus:
                case "Stag":
                    return "🐴"
                case "Otter":
                    return "🦦"
                case "Jack Russell terrier":
                    return "🐶"
                case  _:
                    return "🪄"

    def main():
        student = get_student()
        print("Expecto Patronum!")
        print(student.charm())

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        patronus = input("Patronus: ") or None
        return Student(name, house, patronus)

    if __name__ == "__main__":
        main() 
    ```

    注意我们定义了自己的方法 `charm`。与字典不同，类可以有内置的函数，称为方法。在这种情况下，我们定义了 `charm` 方法，其中特定的案例有特定的结果。此外，注意 Python 有能力在我们的代码中直接使用表情符号。

+   在继续前进之前，让我们移除我们的守护神代码。按照以下方式修改你的代码：

    ```
    class Student:
        def __init__(self, name, house):
            if not name:
                raise ValueError("Invalid name")
            if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
                raise ValueError("Invalid house")
            self.name = name
            self.house = house

        def __str__(self):
            return f"{self.name} from {self.house}"

    def main():
        student = get_student()
        student.house = "Number Four, Privet Drive"
        print(student)

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return Student(name, house)

    if __name__ == "__main__":
        main() 
    ```

    注意我们只有两个方法：`__init__` 和 `__str__`。

## 装饰器

+   属性可以被用来加固我们的代码。在 Python 中，我们使用以 `@` 开头的函数“装饰器”来定义属性。按照以下方式修改你的代码：

    ```
    class Student:
        def __init__(self, name, house):
            if not name:
                raise ValueError("Invalid name")
            self.name = name
            self.house = house

        def __str__(self):
            return f"{self.name} from {self.house}"

        # Getter for house
        @property
        def house(self):
            return self._house

        # Setter for house
        @house.setter
        def house(self, house):
            if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
                raise ValueError("Invalid house")
            self._house = house

    def main():
        student = get_student()
        print(student)

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return Student(name, house)

    if __name__ == "__main__":
        main() 
    ```

    注意我们是如何在名为 `house` 的函数上方写上 `@property` 的。这样做定义了 `house` 为我们类的一个属性。有了 `house` 属性，我们就能定义如何设置和检索我们类的一些属性，例如 `_house`。确实，我们现在可以通过 `@house.setter` 定义一个名为“setter”的函数，每当设置 house 属性时都会被调用——例如，使用 `student.house = "Gryffindor"`。在这里，我们让我们的 setter 为我们验证 `house` 的值。注意，如果 `house` 的值不是哈利·波特的任何一个学院，我们会抛出一个 `ValueError`，否则我们会使用 `house` 更新 `_house` 的值。为什么是 `_house` 而不是 `house`？`house` 是我们类的一个属性，用户通过它尝试设置我们的类属性。`_house` 是那个类属性本身。前导下划线 `_` 表示用户不需要（实际上也不应该！）直接修改这个值。`_house` 应该*仅*通过 `house` setter 来设置。注意 `house` 属性只是简单地返回 `_house` 的值，这是我们通过 `house` setter 可能已经验证过的类属性。当用户调用 `student.house` 时，他们通过我们的 `house` “getter” 获取 `_house` 的值。

+   除了房子的名字，我们还可以保护我们学生的名字。按照以下方式修改你的代码：

    ```
    class Student:
        def __init__(self, name, house):
            self.name = name
            self.house = house

        def __str__(self):
            return f"{self.name} from {self.house}"

        # Getter for name
        @property
        def name(self):
            return self._name

        # Setter for name
        @name.setter
        def name(self, name):
            if not name:
                raise ValueError("Invalid name")
            self._name = name

        @property
        def house(self):
            return self._house

        @house.setter
        def house(self, house):
            if house not in ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]:
                raise ValueError("Invalid house")
            self._house = house

    def main():
        student = get_student()
        print(student)

    def get_student():
        name = input("Name: ")
        house = input("House: ")
        return Student(name, house)

    if __name__ == "__main__":
        main() 
    ```

    注意，和之前的代码类似，我们为名称提供了 getter 和 setter。

+   你可以在 Python 的 [方法](https://docs.python.org/3/tutorial/classes.html) 文档中了解更多信息。

## 连接到本课程中的先前工作

+   尽管在课程的前几部分没有明确说明，但你一直在使用类和对象。

+   如果你深入研究`int`的文档，你会发现它是一个具有构造函数的类。它是创建`int`类型对象的蓝图。你可以在 Python 的`int`文档中了解更多信息，链接为[Python 的`int`文档](https://docs.python.org/3/library/functions.html#int)。

+   字符串也是一个类。如果你使用过`str.lower()`，你就是在使用`str`类中的方法。你可以在 Python 的`str`文档中了解更多信息，链接为[Python 的`str`文档](https://docs.python.org/3/library/stdtypes.html#str)。

+   `list`也是一个类。查看`list`的文档，你可以看到其中包含的方法，如`list.append()`。你可以在 Python 的`list`文档中了解更多信息，链接为[Python 的`list`文档](https://docs.python.org/3/library/stdtypes.html#list)。

+   `dict`也是 Python 中的一个类。你可以在 Python 的`dict`文档中了解更多信息，链接为[Python 的`dict`文档](https://docs.python.org/3/library/stdtypes.html#dict)。

+   要了解你一直是如何使用类的，请打开你的控制台，输入`code type.py`，然后按照以下方式编写代码：

    ```
    print(type(50)) 
    ```

    注意，通过执行这段代码，它将显示`50`的类是`int`。

+   我们也可以将此应用于`str`，如下所示：

    ```
    print(type("hello, world")) 
    ```

    注意，执行这段代码将表明这是`str`类。

+   我们也可以按照以下方式应用于`list`：

    ```
    print(type([])) 
    ```

    注意，执行这段代码将表明这是`list`类。

+   我们也可以使用 Python 内置的`list`类的名称来应用于`list`，如下所示：

    ```
    print(type(list())) 
    ```

    注意，执行这段代码将表明这是`list`类。

+   我们也可以将此应用于`dict`，如下所示：

    ```
    print(type({})) 
    ```

    注意，执行这段代码将表明这是`dict`类。

+   我们也可以使用 Python 内置的`dict`类的名称来应用于`dict`，如下所示：

    ```
    print(type(dict())) 
    ```

    注意，执行这段代码将表明这是`dict`类。

## 类方法

+   有时候，我们希望给类本身添加功能，而不是给该类的实例添加。

+   `@classmethod`是一个函数，我们可以用它来给整个类添加功能。

+   这里是一个**不**使用类方法的例子。在你的终端窗口中，输入`code hat.py`并按照以下方式编写代码：

    ```
    import random

    class Hat:
        def __init__(self):
            self.houses = ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]

        def sort(self, name):
            print(name, "is in", random.choice(self.houses))

    hat = Hat()
    hat.sort("Harry") 
    ```

    注意，当我们把学生的名字传递给排序帽子时，它会告诉我们学生被分配到了哪个学院。注意`hat = Hat()`实例化了`hat`。`sort`功能始终由类的*实例*处理。通过执行`hat.sort("Harry")`，我们向`Hat`的特定实例的`sort`方法传递了学生的名字，我们称之为`hat`。

+   然而，我们可能希望运行`sort`函数而不创建特定的排序帽子实例（毕竟只有一个）。我们可以修改我们的代码如下：

    ```
    import random

    class Hat:

        houses = ["Gryffindor", "Hufflepuff", "Ravenclaw", "Slytherin"]

        @classmethod
        def sort(cls, name):
            print(name, "is in", random.choice(cls.houses))

    Hat.sort("Harry") 
    ```

    注意到 `__init__` 方法被移除，因为我们不需要在我们的代码中的任何地方实例化一顶帽子。因此，`self` 就不再相关，并被移除。我们指定这个 `sort` 为一个 `@classmethod`，用 `cls` 替换 `self`。最后，注意在代码的末尾，根据惯例，`Hat` 被大写，因为这是我们的类名。

+   返回到 `students.py`，我们可以修改我们的代码如下，解决一些与 `@classmethod` 相关的遗漏机会：

    ```
    class Student:
        def __init__(self, name, house):
            self.name = name
            self.house = house

        def __str__(self):
            return f"{self.name} from {self.house}"

        @classmethod
        def get(cls):
            name = input("Name: ")
            house = input("House: ")
            return cls(name, house)

    def main():
        student = Student.get()
        print(student)

    if __name__ == "__main__":
        main() 
    ```

    注意到 `get_student` 被移除，并创建了一个名为 `get` 的 `@classmethod`。现在，可以调用此方法而无需首先创建一个学生。

## 静态方法

+   结果表明，除了与实例方法不同的 `@classmethod` 之外，还有其他类型的函数。

+   使用 `@staticmethod` 可能是你希望探索的事情。虽然本课程没有明确涵盖，但你欢迎去学习更多关于静态方法和它们与类方法的区别。

## 继承

+   继承可能是面向对象编程中最强大的特性。

+   恰好可以创建一个“继承”其他类的方法、变量和属性的类。

+   在终端中，执行 `code wizard.py`。编写如下代码：

    ```
    class Wizard:
        def __init__(self, name):
            if not name:
                raise ValueError("Missing name")
            self.name = name

        ...

    class Student(Wizard):
        def __init__(self, name, house):
            super().__init__(name)
            self.house = house

        ...

    class Professor(Wizard):
        def __init__(self, name, subject):
            super().__init__(name)
            self.subject = subject

        ...

    wizard = Wizard("Albus")
    student = Student("Harry", "Gryffindor")
    professor = Professor("Severus", "Defense Against the Dark Arts")
    ... 
    ```

    注意到有一个名为 `Wizard` 的类和一个名为 `Student` 的类。此外，还有一个名为 `Professor` 的类。学生和教授都有名字。学生和教授都是巫师。因此，`Student` 和 `Professor` 继承了 `Wizard` 的特性。在“子”类 `Student` 中，`Student` 可以从“父”或“超”类 `Wizard` 继承，如 `super().__init__(name)` 运行 `Wizard` 的 `init` 方法。最后，注意代码的最后几行创建了一个名为 Albus 的巫师，一个名为 Harry 的学生，等等。

## 继承和异常

+   虽然我们刚刚介绍了继承，但我们一直在使用异常时使用它。

+   恰好异常有一个层次结构，其中包含子类、父类和祖父母类。这些在下图中展示：

    ```
    BaseException
     +-- KeyboardInterrupt
     +-- Exception
          +-- ArithmeticError
          |    +-- ZeroDivisionError
          +-- AssertionError
          +-- AttributeError
          +-- EOFError
          +-- ImportError
          |    +-- ModuleNotFoundError
          +-- LookupError
          |    +-- KeyError
          +-- NameError
          +-- SyntaxError
          |    +-- IndentationError
          +-- ValueError
     ... 
    ```

+   你可以在 Python 的 [异常](https://docs.python.org/3/library/exceptions.html) 文档中了解更多信息。

## 运算符重载

+   一些运算符，如 `+` 和 `-`，可以被“重载”，以便它们可以拥有超出简单算术的更多能力。

+   在你的终端窗口中，输入 `code vault.py`。然后，编写如下代码：

    ```
    class Vault:
        def __init__(self, galleons=0, sickles=0, knuts=0):
            self.galleons = galleons
            self.sickles = sickles
            self.knuts = knuts

        def __str__(self):
            return f"{self.galleons} Galleons, {self.sickles} Sickles, {self.knuts} Knuts"

        def __add__(self, other):
            galleons = self.galleons + other.galleons
            sickles = self.sickles + other.sickles
            knuts = self.knuts + other.knuts
            return Vault(galleons, sickles, knuts)

    potter = Vault(100, 50, 25)
    print(potter)

    weasley = Vault(25, 50, 100)
    print(weasley)

    total = potter + weasley
    print(total) 
    ```

    注意到 `__str__` 方法返回一个格式化的字符串。此外，注意到 `__add__` 方法允许两个保险库值的相加。`self` 是 `+` 运算符左侧的内容。`other` 是 `+` 运算符右侧的内容。

+   你可以在 Python 的 [运算符重载](https://docs.python.org/3/reference/datamodel.html#special-method-names) 文档中了解更多信息。

## 总结

现在，你已经通过面向对象编程学习了一个全新的能力级别。

+   面向对象编程

+   类

+   `raise`

+   类方法

+   静态方法

+   继承

+   运算符重载
