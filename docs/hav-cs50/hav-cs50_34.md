# 第六讲

> 原文：[`cs50.harvard.edu/python/notes/6/`](https://cs50.harvard.edu/python/notes/6/)

+   文件输入/输出

+   `open`

+   `with`

+   CSV

+   二进制文件和 `PIL`

+   总结

## 文件输入/输出

+   到目前为止，我们编写的所有程序都是在内存中存储信息。也就是说，一旦程序结束，从用户那里收集的所有信息或程序生成的所有信息都会丢失。

+   文件输入/输出是程序将文件作为输入或创建文件作为输出的能力。

+   首先，在终端窗口中输入 `code names.py` 并编写以下代码：

    ```
    name = input("What's your name?" )
    print(f"hello, {name}") 
    ```

    注意，运行此代码会产生预期的输出。用户可以输入一个名字，输出结果符合预期。

+   然而，如果我们想允许输入多个名字呢？我们该如何实现？回想一下，`list` 是一种数据结构，允许我们将多个值存储到单个变量中。按照以下方式编写代码：

    ```
    names = []

    for _ in range(3):
        name = input("What's your name?" )
        names.append(name) 
    ```

    注意，用户将被提示三次输入。使用 `append` 方法将 `name` 添加到我们的 `names` 列表中。

+   这段代码可以简化为以下形式：

    ```
    names = []

    for _ in range(3):
        names.append(input("What's your name?" )) 
    ```

    注意，这与之前的代码块有相同的结果。

    +   现在，让我们启用打印名字列表为排序列表的功能。按照以下方式编写代码：

    ```
    names = []

    for _ in range(3):
        names.append(input("What's your name?" ))

    for name in sorted(names):
        print(f"hello, {name}") 
    ```

    注意，一旦程序执行完毕，所有信息都会丢失。文件输入/输出允许你的程序存储这些信息，以便以后使用。

+   你可以在 Python 的 [sorted](https://docs.python.org/3/library/functions.html#sorted) 文档中了解更多信息。

## `open`

+   `open` 是 Python 内置的一个功能，允许你打开一个文件并在你的程序中使用它。`open` 函数允许你以读取或写入的方式打开一个文件。

+   为了向你展示如何在程序中启用文件输入/输出，让我们回顾一下并编写以下代码：

    ```
    name = input("What's your name? ")

    file = open("names.txt", "w")
    file.write(name)
    file.close() 
    ```

    注意，`open` 函数以写入模式打开了一个名为 `names.txt` 的文件，这由 `w` 表示。上面的代码将打开的文件分配给一个名为 `file` 的变量。`file.write(name)` 这行代码将名字写入文本文件。之后的行关闭了文件。

+   通过在终端中输入 `python names.py` 测试你的代码，你可以输入一个名字，并将其保存到文本文件中。然而，如果你使用不同的名字多次运行程序，你会注意到这个程序每次都会完全重写 `names.txt` 文件。

+   理想情况下，我们希望能够将我们的每个名字追加到文件中。在终端窗口中输入 `rm names.txt` 来删除现有的文本文件。然后，按照以下方式修改你的代码：

    ```
    name = input("What's your name? ")

    file = open("names.txt", "a")
    file.write(name)
    file.close() 
    ```

    注意，我们代码中唯一的改变是将 `w` 改为 `a` 以实现“追加”。多次重新运行此程序，你会注意到名字将被添加到文件中。然而，你也会发现一个新的问题！

+   在运行程序多次后检查您的文本文件，您会注意到名字是连在一起的。名字之间没有任何间隔。您可以修复这个问题。再次，通过在终端窗口中键入 `rm names.txt` 来删除现有的文本文件。然后，按照以下方式修改您的代码：

    ```
    name = input("What's your name? ")

    file = open("names.txt", "a")
    file.write(f"{name}\n")
    file.close() 
    ```

    注意到带有 `file.write` 的行已经被修改，为每个名字添加了行尾换行符。

+   这段代码工作得相当好。然而，有方法可以改进这个程序。它很容易忘记关闭文件。

+   您可以在 Python 的 [open](https://docs.python.org/3/library/functions.html#open) 文档中了解更多信息。

## `with`

+   关键字 `with` 允许您自动化文件的关闭。

+   按照以下方式修改您的代码：

    ```
    name = input("What's your name? ")

    with open("names.txt", "a") as file:
        file.write(f"{name}\n") 
    ```

    注意到 `with` 下的行是缩进的。

+   到目前为止，我们一直是在向文件中写入。如果我们想从文件中读取呢？为了启用此功能，按照以下方式修改您的代码：

    ```
    with open("names.txt", "r") as file:
        lines = file.readlines()

    for line in lines:
        print("hello,", line) 
    ```

    注意到 `readlines` 具有读取文件中所有行并将它们存储在名为 `lines` 的列表中的特殊能力。运行您的程序，您会注意到输出相当难看。似乎在应该只有一个换行符的地方有多个换行符。

+   有许多方法可以解决这个问题。但是，这里有一个简单的方法可以修复我们代码中的这个错误：

    ```
    with open("names.txt", "r") as file:
        lines = file.readlines()

    for line in lines:
        print("hello,", line.rstrip()) 
    ```

    注意到 `rstrip` 具有移除每行末尾多余换行符的效果。

+   尽管如此，这段代码还可以进一步简化：

    ```
    with open("names.txt", "r") as file:
        for line in file:
            print("hello,", line.rstrip()) 
    ```

    注意到运行这段代码是正确的。然而，请注意我们没有对名字进行排序。

+   这段代码可以进一步改进，以允许对名字进行排序：

    ```
    names = []

    with open("names.txt") as file:
        for line in file:
            names.append(line.rstrip())

    for name in sorted(names):
        print(f"hello, {name}") 
    ```

    注意到 `names` 是一个空白列表，我们可以在这里收集名字。每个名字都会追加到内存中的 `names` 列表中。然后，内存中排序列表中的每个名字都会被打印出来。运行您的代码，您会看到名字现在已经被正确排序。

+   如果我们想要存储的不仅仅是学生的名字呢？如果我们想存储学生的名字和他们的宿舍呢？

## CSV

+   CSV 代表“逗号分隔值”。

+   在您的终端窗口中，键入 `code students.csv`。确保您的新 CSV 文件看起来如下：

    ```
    Hermione,Gryffindor
    Harry,Gryffindor
    Ron,Gryffindor
    Draco,Slytherin 
    ```

+   通过键入 `code students.py` 创建一个新的程序，并按照以下方式编写代码：

    ```
    with open("students.csv") as file:
        for line in file:
            row = line.rstrip().split(",")
            print(f"{row[0]} is in {row[1]}") 
    ```

    注意到 `rstrip` 移除了我们 CSV 文件中每行的末尾。`split` 告诉解释器在哪里找到我们 CSV 文件中每个值的末尾。`row[0]` 是我们 CSV 文件每行中的第一个元素。`row[1]` 是我们 CSV 文件每行中的第二个元素。

+   上述代码有效地将我们的 CSV 文件中的每一行或“记录”分开。然而，如果您不熟悉这种语法，看起来可能有点晦涩。Python 有内置的能力可以进一步简化这段代码。按照以下方式修改您的代码：

    ```
    with open("students.csv") as file:
        for line in file:
            name, house = line.rstrip().split(",")
            print(f"{name} is in {house}") 
    ```

    注意，`split` 函数实际上返回两个值：逗号之前的一个和逗号之后的一个。因此，我们可以依赖这个功能一次分配两个变量而不是一个！

+   假设我们再次希望提供这个列表作为排序后的输出？你可以按照以下方式修改你的代码：

    ```
    students = []

    with open("students.csv") as file:
        for line in file:
            name, house = line.rstrip().split(",")
            students.append(f"{name} is in {house}")

    for student in sorted(students):
        print(student) 
    ```

    注意，我们创建了一个名为 `students` 的 `list`。我们将每个字符串 `append` 到这个列表中。然后，我们输出列表的排序版本。

+   回想一下，Python 允许使用 `dictionaries`，其中键可以与值相关联。这段代码可以进一步改进

    ```
    students = []

    with open("students.csv") as file:
        for line in file:
            name, house = line.rstrip().split(",")
            student = {}
            student["name"] = name
            student["house"] = house
            students.append(student)

    for student in students:
        print(f"{student['name']} is in {student['house']}") 
    ```

    注意，我们创建了一个名为 `student` 的空字典。我们将每个学生的值添加到 `student` 字典中，包括他们的名字和学院。然后，我们将该学生添加到名为 `students` 的 `list` 中。

+   我们可以改进我们的代码来展示这一点，如下所示：

    ```
    students = []

    with open("students.csv") as file:
        for line in file:
            name, house = line.rstrip().split(",")
            student = {"name": name, "house": house}
            students.append(student)

    for student in students:
        print(f"{student['name']} is in {student['house']}") 
    ```

    注意，这样会产生期望的结果，但排除了学生的排序。

+   不幸的是，我们无法像以前那样对学生的列表进行排序，因为每个学生现在都是一个列表中的字典。如果 Python 能够按学生的名字对 `students` 列表中的 `student` 字典进行排序，那将很有帮助。

+   要在我们的代码中实现这一点，进行以下更改：

    ```
    students = []

    with open("students.csv") as file:
        for line in file:
            name, house = line.rstrip().split(",")
            students.append({"name": name, "house": house})

    def get_name(student):
        return student["name"]

    for student in sorted(students, key=get_name):
        print(f"{student['name']} is in {student['house']}") 
    ```

    注意，`sorted` 需要知道如何获取每个学生的键。Python 允许一个名为 `key` 的参数，我们可以定义学生列表将按什么“键”进行排序。因此，`get_name` 函数简单地返回 `student["name"]` 的键。运行这个程序，你现在会看到列表已按名字排序。

+   尽管如此，我们的代码还可以进一步改进。恰好如果你只打算使用像 `get_name` 这样的函数一次，你可以按照以下方式简化你的代码。按照以下方式修改你的代码：

    ```
    students = []

    with open("students.csv") as file:
        for line in file:
            name, house = line.rstrip().split(",")
            students.append({"name": name, "house": house})

    for student in sorted(students, key=lambda student: student["name"]):
        print(f"{student['name']} is in {student['house']}") 
    ```

    注意我们如何使用一个 `lambda` 函数，一个匿名函数，它说：“嘿 Python，这里有一个没有名字的函数：给定一个 `student`，访问他们的 `name` 并将其作为 `key` 返回。”

+   不幸的是，我们的代码有点脆弱。假设我们改变了我们的 CSV 文件，使得我们指明了每个学生的成长地。这对我们的程序会有什么影响？首先，按照以下方式修改你的 `students.csv` 文件：

```
Harry,"Number Four, Privet Drive"
Ron,The Burrow
Draco,Malfoy Manor 
```

注意，运行我们的程序会产生许多错误。

+   现在我们处理的是家园（homes）而不是学院（houses），按照以下方式修改你的代码：

    ```
    students = []

    with open("students.csv") as file:
        for line in file:
            name, home = line.rstrip().split(",")
            students.append({"name": name, "home": home})

    for student in sorted(students, key=lambda student: student["name"]):
        print(f"{student['name']} is in {student['home']}") 
    ```

    注意，运行我们的程序仍然不能正常工作。你能猜到为什么吗？

+   解释器产生的 `ValueError: too many values to unpack` 错误是由于我们之前创建这个程序时预期 CSV 文件是用逗号（`,`）分割的。我们可以花更多时间解决这个问题，但确实有人已经开发了一种“解析”（即读取）CSV 文件的方法！

+   Python 的内置 `csv` 库包含一个名为 `reader` 的对象。正如其名所示，我们可以使用 `reader` 来读取我们的 CSV 文件，即使“四号，紫杉巷”中有多余的逗号。`reader` 在 `for` 循环中工作，每次迭代时 `reader` 都会从我们的 CSV 文件中提供另一行。这一行本身是一个列表，其中列表中的每个值对应于该行中的一个元素。例如，`row[0]` 是给定行的第一个元素，而 `row[1]` 是第二个元素。

    ```
    import csv

    students = []

    with open("students.csv") as file:
        reader = csv.reader(file)
        for row in reader:
            students.append({"name": row[0], "home": row[1]})

    for student in sorted(students, key=lambda student: student["name"]):
        print(f"{student['name']} is from {student['home']}") 
    ```

    注意现在我们的程序按预期工作。

+   到目前为止，我们一直依赖于我们的程序来具体决定 CSV 文件中的哪些部分是名字，哪些部分是家庭地址。然而，更好的设计是将这些直接嵌入到我们的 CSV 文件中，如下所示进行编辑：

    ```
    name,home
    Harry,"Number Four, Privet Drive"
    Ron,The Burrow
    Draco,Malfoy Manor 
    ```

    注意我们在 CSV 文件中明确指出，任何读取它的人都应预期每行都有一个名字值和一个家庭值。

+   我们可以修改我们的代码，使用 `csv` 库中的一个名为 `DictReader` 的部分，以获得更大的灵活性来处理我们的 CSV 文件：

    ```
    import csv

    students = []

    with open("students.csv") as file:
        reader = csv.DictReader(file)
        for row in reader:
            students.append({"name": row["name"], "home": row["home"]})

    for student in sorted(students, key=lambda student: student["name"]):
        print(f"{student['name']} is in {student['home']}") 
    ```

    注意我们已经将 `reader` 替换为 `DictReader`，它每次返回一个字典。此外，注意解释器将直接访问 `row` 字典，获取每个学生的 `name` 和 `home`。这是一个编码防御的例子。只要设计 CSV 文件的人已经在第一行输入了正确的标题信息，我们就可以使用我们的程序访问这些信息。

+   到目前为止，我们一直在读取 CSV 文件。如果我们想写入 CSV 文件怎么办？

+   首先，让我们清理一下我们的文件。首先，在终端窗口中输入 `rm students.csv` 删除 `students.csv` 文件。此命令仅在你位于 `students.csv` 文件相同的文件夹中时有效。

+   然后，在 `students.py` 文件中，按照以下方式修改你的代码：

    ```
    import csv

    name = input("What's your name? ")
    home = input("Where's your home? ")

    with open("students.csv", "a") as file:
        writer = csv.DictWriter(file, fieldnames=["name", "home"])
        writer.writerow({"name": name, "home": home}) 
    ```

    注意我们如何利用 `DictWriter` 的内置功能，它接受两个参数：要写入的 `file` 和要写入的 `fieldnames`。此外，注意 `writerow` 函数接受一个字典作为其参数。实际上，我们是在告诉解释器写入一个包含两个字段名为 `name` 和 `home` 的行。

+   注意，你可以从和写入许多类型的文件。

+   你可以在 Python 的 [CSV](https://docs.python.org/3/library/csv.html) 文档中了解更多信息。

## 二进制文件和 `PIL`

+   我们今天还将讨论另一种类型的文件，即二进制文件。二进制文件简单来说就是由一串零和一组成的集合。这种类型的文件可以存储任何内容，包括音乐和图像数据。

+   有一个流行的 Python 库叫做 `PIL`，它与图像文件配合得很好。

+   动画 GIF 是一种流行的图像文件类型，其中包含多个图像文件，这些图像文件会按顺序反复播放，从而创建出简单的动画或视频效果。

+   想象一下，我们有一系列服装，如下所示。

+   这里是 `costume1.gif`。

![猫编号 1.](img/e2f07bf55ef30460a0974f8ebbcf973a.png "costume1.gif")

+   这还有一个叫做 `costume2.gif` 的例子。注意腿部位置略有不同。

![猫编号 2.](img/d78e3160c6a18f8c59410c0c1e97ed29.png "costume2.gif")

+   在继续之前，请确保您已从课程网站下载了源代码文件。如果没有上述两张图像，您将无法编写以下代码。

+   在终端窗口中输入 `code costumes.py` 并按照以下代码编写：

    ```
    import sys

    from PIL import Image

    images = []

    for arg in sys.argv[1:]:
        image = Image.open(arg)
        images.append(image)

    images[0].save(
        "costumes.gif", save_all=True, append_images=[images[1]], duration=200, loop=0
    ) 
    ```

    注意我们是从 `PIL` 中导入 `Image` 功能。注意第一个 `for` 循环只是简单地遍历提供的命令行参数中的图像，并将它们存储到名为 `images` 的列表中。`1:` 表示从 `argv` 的第二个元素开始切片。代码的最后几行保存了第一张图像，并将其与第二张图像一起附加，创建了一个动画 GIF。在终端中输入 `python costumes.py costume1.gif costume2.gif`。现在，在终端窗口中输入 `code costumes.gif`，你现在可以看到一个动画 GIF。

+   您可以在 Pillow 的 [PIL](https://pillow.readthedocs.io/) 文档中了解更多信息。

## 总结

现在，我们不仅看到了我们可以以文本方式编写和读取文件——我们还可以使用一和零来读写文件。我们迫不及待地想看看你将如何利用这些新能力取得成就。

+   文件输入/输出

+   `open`

+   `with`

+   CSV

+   `PIL`
