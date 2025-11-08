# 第 5 讲

> 原文：[`cs50.harvard.edu/python/notes/5/`](https://cs50.harvard.edu/python/notes/5/)

+   单元测试

+   `assert`

+   `pytest`

+   测试字符串

+   将测试组织到文件夹中

+   总结

## 单元测试

+   到目前为止，你很可能一直在使用 `print` 语句测试自己的代码。

+   或者，你可能一直依赖 CS50 来为你测试代码！

+   在工业界，编写代码来测试自己的程序是最常见的。

+   在你的控制台窗口中，输入 `code calculator.py`。注意，你可能在前面的讲座中已经编写了这个文件。在文本编辑器中，确保你的代码如下所示：

    ```
    def main():
        x = int(input("What's x? "))
        print("x squared is", square(x))

    def square(n):
        return n * n

    if __name__ == "__main__":
        main() 
    ```

    注意，你可以使用一些明显的数字，例如 `2`，在你的机器上合理地测试上述代码。然而，考虑一下你为什么想要创建一个确保上述代码适当运行的测试。

+   按照惯例，让我们通过输入 `code test_calculator.py` 创建一个新的测试程序，并在文本编辑器中修改你的代码如下：

    ```
    from calculator import square

    def main():
        test_square()

    def test_square():
        if square(2) != 4:
            print("2 squared was not 4")
        if square(3) != 9:
            print("3 squared was not 9")

    if __name__ == "__main__":
        main() 
    ```

    注意，我们在代码的第一行导入了 `square` 函数，来自 `calculator.py`。

+   在控制台窗口中，输入 `python test_calculator.py`。你会注意到没有任何输出。这可能意味着一切运行正常！或者，这也可能意味着我们的测试函数没有发现可能导致错误的“边缘情况”之一。

+   目前，我们的代码测试了两个条件。如果我们想要测试更多的条件，我们的测试代码可能会很容易变得臃肿。我们如何在不扩展测试代码的情况下扩展我们的测试能力？

## `assert`

+   Python 的 `assert` 命令允许我们告诉解释器某个断言是真的。我们可以将此应用于我们的测试代码，如下所示：

    ```
    from calculator import square

    def main():
        test_square()

    def test_square():
        assert square(2) == 4
        assert square(3) == 9

    if __name__ == "__main__":
        main() 
    ```

    注意，我们明确断言 `square(2)` 和 `square(3)` 应该等于什么。我们的代码从四行测试减少到两行。

+   我们可以通过以下方式故意破坏计算器代码：

    ```
    def main():
        x = int(input("What's x? "))
        print("x squared is", square(x))

    def square(n):
        return n + n

    if __name__ == "__main__":
        main() 
    ```

    注意，我们在平方函数中将 `*` 运算符改为了 `+`。

+   现在，在控制台窗口中运行 `python test_calculator.py`，你会注意到解释器抛出了一个 `AssertionError`。本质上，这是解释器告诉我们我们的某个条件没有满足。

+   我们现在面临的一个挑战是，如果我们想要向用户提供更多描述性的错误输出，我们的代码可能会变得更加繁重。可能地，我们可以这样编写代码：

    ```
    from calculator import square

    def main():
        test_square()

    def test_square():
        try:
            assert square(2) == 4
        except AssertionError:
            print("2 squared is not 4")
        try:
            assert square(3) == 9
        except AssertionError:
            print("3 squared is not 9")
        try:
            assert square(-2) == 4
        except AssertionError:
            print("-2 squared is not 4")
        try:
            assert square(-3) == 9
        except AssertionError:
            print("-3 squared is not 9")
        try:
            assert square(0) == 0
        except AssertionError:
            print("0 squared is not 0")

    if __name__ == "__main__":
        main() 
    ```

    注意，运行此代码将产生多个错误。然而，它并没有产生上述所有错误。这是一个很好的说明，说明测试多个情况是有价值的，这样你可能会捕捉到存在编码错误的情况。

+   上述代码说明了主要挑战：我们如何在不使用像上述那样数十行代码的情况下使测试代码更容易？

你可以在 Python 的文档中了解更多关于 `assert` 的信息：[assert](https://docs.python.org/3/reference/simple_stmts.html#assert)。

## `pytest`

+   `pytest` 是一个第三方库，允许你对程序进行单元测试。也就是说，你可以在程序中测试你的函数。

+   要使用 `pytest`，请在控制台窗口中输入 `pip install pytest`。

+   在将 `pytest` 应用于我们自己的程序之前，按照以下方式修改你的 `test_square` 函数：

    ```
    from calculator import square

    def main():
        test_square()

    def test_square():
        assert square(2) == 4
        assert square(3) == 9
        assert square(-2) == 4
        assert square(-3) == 9
        assert square(0) == 0 
    ```

    注意上述代码断言了我们想要测试的所有条件。

+   `pytest` 允许我们直接通过它运行程序，这样我们可以更容易地查看测试条件的输出结果。

+   在终端窗口中，输入 `pytest test_calculator.py`。你会立即注意到会提供输出。注意输出顶部附近的红色 `F`，表示你的代码中存在问题。此外，红色 `E` 提供了一些关于 `calculator.py` 程序中错误的信息。根据输出，你可以想象一个场景，其中 `3 * 3` 输出了 `6` 而不是 `9`。根据这个测试的结果，我们可以按照以下方式更正 `calculator.py` 代码：

    ```
    def main():
        x = int(input("What's x? "))
        print("x squared is", square(x))

    def square(n):
        return n * n

    if __name__ == "__main__":
        main() 
    ```

    注意我们在平方函数中将 `+` 运算符更改为 `*`，使其恢复到工作状态。

+   再次运行 `pytest test_calculator.py`，注意没有错误产生。恭喜你！

+   目前，`pytest` 在第一次测试失败后停止运行并不理想。再次，让我们将我们的 `calculator.py` 代码恢复到损坏状态：

    ```
    def main():
        x = int(input("What's x? "))
        print("x squared is", square(x))

    def square(n):
        return n + n

    if __name__ == "__main__":
        main() 
    ```

    注意我们在平方函数中将 `*` 运算符更改为 `+`，使其恢复到损坏状态。

+   为了改进我们的测试代码，让我们将 `test_calculator.py` 中的代码分成不同的测试组：

    ```
    from calculator import square

    def test_positive():
        assert square(2) == 4
        assert square(3) == 9

    def test_negative():
        assert square(-2) == 4
        assert square(-3) == 9

    def test_zero():
        assert square(0) == 0 
    ```

    注意我们将相同的五个测试分成了三个不同的函数。像 `pytest` 这样的测试框架会运行每个函数，即使其中一个失败了。再次运行 `pytest test_calculator.py`，你会发现显示了许多更多的错误。更多的错误输出允许你进一步探索代码中可能产生问题的原因。

+   在改进了测试代码后，将你的 `calculator.py` 代码恢复到完全工作状态：

    ```
    def main():
        x = int(input("What's x? "))
        print("x squared is", square(x))

    def square(n):
        return n * n

    if __name__ == "__main__":
        main() 
    ```

    注意我们在平方函数中将 `+` 运算符更改为 `*`，使其恢复到工作状态。

+   再次运行 `pytest test_calculator.py`，你会发现没有错误发生。

+   最后，我们可以测试我们的程序是否能够处理异常。让我们修改 `test_calculator.py` 来实现这一点。

```
 import pytest

  from calculator import square

  def test_positive():
      assert square(2) == 4
      assert square(3) == 9

  def test_negative():
      assert square(-2) == 4
      assert square(-3) == 9

  def test_zero():
      assert square(0) == 0

  def test_str():
      with pytest.raises(TypeError):
          square("cat") 
```

注意我们不再使用 `assert`，而是利用 `pytest` 库中的一个函数 `raises`，它允许你表达你期望抛出一个错误。我们需要将 `import pytest` 添加到程序顶部，然后使用 `pytest.raises` 并指定我们期望的错误类型。

+   再次运行 `pytest test_calculator.py`，你会发现没有错误发生。

+   总结来说，作为程序员，定义多少测试条件取决于你自己的判断！

你可以在 Pytest 的[pytest](https://docs.pytest.org/en/7.1.x/getting-started.html)文档中了解更多信息。

## 测试字符串

+   回到过去，考虑以下`hello.py`的代码：

    ```
    def main():
        name = input("What's your name? ")
        hello(name)

    def hello(to="world"):
        print("hello,", to)

    if __name__ == "__main__":
        main() 
    ```

    注意，我们可能希望测试`hello`函数的结果。

+   考虑以下`test_hello.py`的代码：

    ```
    from hello import hello

    def test_hello():
        assert hello("David") == "hello, David"
        assert hello() == "hello, world" 
    ```

    看到这段代码，你认为这种测试方法会有效吗？为什么这个测试可能不起作用？注意`hello.py`中的`hello`函数打印了一些内容：也就是说，它没有返回一个值！

+   我们可以在`hello.py`中更改我们的`hello`函数，如下所示：

    ```
    def main():
        name = input("What's your name? ")
        print(hello(name))

    def hello(to="world"):
        return f"hello, {to}"

    if __name__ == "__main__":
        main() 
    ```

    注意，我们将`hello`函数更改为返回一个字符串。这意味着我们现在可以使用`pytest`来测试`hello`函数。

+   运行`pytest test_hello.py`，我们的代码将通过所有测试！

+   就像本课之前的测试案例一样，我们可以将测试分开进行：

    ```
    from hello import hello

    def test_default():
        assert hello() == "hello, world"

    def test_argument():
        assert hello("David") == "hello, David" 
    ```

    注意，上述代码将我们的测试分成多个函数，这样即使产生错误，它们也会全部运行。

## 将测试组织到文件夹中

+   使用多个测试进行单元测试是如此常见，以至于你可以使用单个命令运行整个测试文件夹。

+   首先，在终端窗口中，执行`mkdir test`以创建一个名为`test`的文件夹。

+   然后，在终端窗口中输入`code test/test_hello.py`以在该文件夹内创建一个测试。注意`test/`指示终端在名为`test`的文件夹中创建`test_hello.py`。

+   在文本编辑窗口中，修改文件以包含以下代码：

    ```
    from hello import hello

    def test_default():
        assert hello() == "hello, world"

    def test_argument():
        assert hello("David") == "hello, David" 
    ```

    注意，我们正在创建一个测试，就像之前做的那样。

+   `pytest`不会允许我们仅使用这个文件（或一组文件）作为文件夹来运行测试，而不需要一个特殊的`__init__`文件。在你的终端窗口中，通过输入`code test/__init__.py`创建这个文件。注意，就像之前一样，`test/`以及`init`两边的双下划线。即使这个`__init__.py`文件为空，`pytest`也会知道包含`__init__.py`的整个文件夹包含可以运行的测试。

+   现在，在终端中输入`pytest test`，你可以运行整个`test`文件夹中的代码。

你可以在 Pytest 的[导入机制](https://docs.pytest.org/en/7.1.x/explanation/pythonpath.html?highlight=folder#pytest-import-mechanisms-and-sys-path-pythonpath)文档中了解更多信息。

## 总结

测试你的代码是编程过程中的一个自然部分。单元测试允许你测试代码的特定方面。你可以创建自己的程序来测试你的代码。或者，你可以利用像`pytest`这样的框架来自动运行你的单元测试。在本讲中，你学习了关于……

+   单元测试

+   `assert`

+   `pytest`
