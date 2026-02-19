# 使用 Junit 进行测试

我们之前已经讨论过对函数进行增量测试。现在我们将为我们的对象和方法创建更系统化的测试。

要使用 JUnit，您必须按照安装说明中所述安装它。

[JUnit](http://junit.org) 是一个允许我们编写测试套件的 Java 库。测试套件是一个包含任意数量测试的类，检查我们代码的正确性。

#### 一个简单的测试套件

让我们从一个简单的例子开始（[test1.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/60-junit/test1.kt)）：

```
import org.junit.Assert.*
import org.junit.Test

public class AdditionTest {

  @Test
  fun onePlusOne() {
    assertEquals("1 + 1 must be 2", 2, 1 + 1)
    assertNotEquals("1 + 1 must not be 3", 3, 1 + 1)
  }
} 

```

我们编译这个类：

```
$ ktc test1.kt

```

如果您现在检查 classes 目录的内容，您会在那里找到一个新文件 AdditionTest.class。我们可以按以下方式运行测试套件：

```
$ kttest AdditionTest
JUnit version 4.12
.
Time: 0.004

OK (1 test)

```

输出结果显示一切都顺利进行，所有测试都通过了。

为了演示测试失败的情况，我将更改测试中的第二个断言如下：

```
  assertNotEquals("1 + 1 must not be 2", 2, 1 + 1)

```

再次编译并运行测试：

```
$ ktc test1.kt 
$ kttest AdditionTest
JUnit version 4.12
.E
Time: 0.005
There was 1 failure:
1) onePlusOne(AdditionTest)
java.lang.AssertionError: 1 + 1 must not be 2\. Actual: 2
	at org.junit.Assert.fail(Assert.java:88)

```

#### 检查异常是否被抛出

要检查我们的代码是否正确处理需要抛出异常的输入，我们需要编写一些测试，指示实际上期望抛出异常。这是通过在测试上进行注解完成的（[test2.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/60-junit/test2.kt)）：

```
import org.junit.Assert.*
import org.junit.Test

public class ArithmeticTest {

  @Test
  fun onePlusOne() {
    assertEquals("1 + 1 must be 2", 2, 1 + 1)
    assertNotEquals("1 + 1 must not be 3", 3, 1 + 1)
  }

  @Test(expected = ArithmeticException::class)
  fun divisionByZero() {
    @Suppress("UNUSED_VARIABLE")
    val result = 1 / 0
  }
}

```

这是输出结果：

```
$ ktc test2.kt 
test2.kt:14:18: warning: division by zero
$ kttest ArithmeticTest
JUnit version 4.12
..
Time: 0.004

OK (2 tests)

```

如果我们将 1/0 更改为 1/1，以便不会抛出异常，测试套件将正确检测到错误。

```
$ kttest ArithmeticTest
JUnit version 4.12
..E
Time: 0.006
There was 1 failure:
1) divisionByZero(ArithmeticTest)
java.lang.AssertionError: Expected exception: java.lang.ArithmeticException
	at org.junit.internal.runners.statements.ExpectException.evaluate(ExpectException.java:32)

```

#### 测试我们自己的类

对于多项式计算器项目，我已经编写了一个在[polynomial.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/60-junit/polynomial.kt)中实现的类 Polynomial。

现在我们将为 Polynomial 类编写一个测试套件。这比进行交互式测试要好得多，因为当测试失败时，您可以修改代码并重新运行所有测试。如果您需要向您的类添加功能或以任何方式更改它们，拥有您以前使用的所有测试非常有用：您可以再次运行它们以确保您没有破坏任何内容。

创建测试套件以对所有有趣的类进行测试是一个好习惯。您可以使用测试套件来确保您实现的类是正确的。更重要的是，它让您相信，当您进行更改时，您不会意外地破坏类的某些部分。

这是 Polynomial 类的一个测试套件。请注意，它仅使用 Polynomial 类进行测试（[polytest.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/60-junit/polytest.kt)）：

```
import org.junit.Assert.*
import org.junit.Test

public class PolynomialTest {

  @Test
  fun creatingPolynomials() {
    val p1 = Polynomial(3)
    assertEquals(p1.degree(), 0)
    assertEquals(p1.toString(), "3")
    val p2 = Polynomial(-1, 3, -4, 0, -6)
    assertEquals(p2.degree(), 4)
    assertEquals(p2.toString(), "-6 * X⁴ - 4 * X² + 3 * X - 1")
    val p3 = Polynomial(0, 0, 1)
    assertEquals(p3.degree(), 2)
    assertEquals(p3.toString(), "X²")
    val p0 = Polynomial(0)
    assertEquals(p0.degree(), -1)
  }

  @Test
  fun additionAndSubtraction() {
    val p1 = Polynomial(3)
    val p2 = Polynomial(-1, 3, -4, 0, -6)
    val p3 = Polynomial(5, 0, 4, 0, -6)

    val q1 = p1 + p2
    val q2 = p2 - p3
    assertEquals(q1.toString(), "-6 * X⁴ - 4 * X² + 3 * X + 2")
    assertEquals(q2.degree(), 2)
    assertEquals(q2.toString(), "-8 * X² + 3 * X - 6")
  }

  @Test
  fun multiplication() {
    val p1 = Polynomial(3)
    val p2 = Polynomial(-1, 3, -4, 0, -6)
    val p3 = Polynomial(0, 0, 5)
    val p4 = Polynomial(2, -4, 6, 8)

    val q1 = p1 * p2
    val q4 = p2 * p3
    val q5 = p2 * p4
    assertEquals(q1.toString(), "-18 * X⁴ - 12 * X² + 9 * X - 3")
    assertEquals(q4.degree(), 6)
    assertEquals(q4.toString(), "-30 * X⁶ - 20 * X⁴ + 15 * X³ - 5 * X²")
    assertEquals(q5.toString(), "-48 * X⁷ - 36 * X⁶ - 8 * X⁵ - 12 * X⁴ + 26 * X³ - 26 * X² + 10 * X - 2")
  }

  @Test
  fun power() {
    val p1 = Polynomial(3)
    val p3 = Polynomial(0, 0, 5)

    val q2 = p1 pow 5
    val q3 = p3 pow 5
    assertEquals(q2.degree(), 0)
    assertEquals(q2.coeff(0), 3*3*3*3*3)
    assertEquals(q3.degree(), 10)
    assertEquals(q3.toString(), "3125 * X¹⁰")
  }

@Test
  fun creatingPolynomialsUsingX() {
    assertEquals(X.toString(), "X")
    val p4 = -1 * (X pow 5) + 3 * (X pow 3) - (X pow 2) + 5
    assertEquals(p4.toString(), "-X⁵ + 3 * X³ - X² + 5")
    val p5 = (X - 1) * (X - 3) * (X + 5) pow 2
    assertEquals(p5.toString(), "X⁶ + 2 * X⁵ - 33 * X⁴ - 4 * X³ + 319 * X² - 510 * X + 225")
  }

  @Test
  fun evaluation() {
    val p1 = Polynomial(3)
    val p2 = Polynomial(-1, 3, -4, 0, -6)
    val p3 = Polynomial(0, 0, 1)
    val p4 = -1 * (X pow 5) + 3 * (X pow 3) - (X pow 2) + 5
    val p5 = (X - 1) * (X - 3) * (X + 5) pow 2

    val eps = 1.0e-9 // floating point precision

    assertEquals(3.0, p1(5.0), eps)
    assertEquals(-1.0, p2(0.0), eps)
    assertEquals(4.0, p3(2.0), eps)
    assertEquals(2.0, p4(-1.0), eps)    
    assertEquals(0.0, p5(-5.0), eps)
  }

  @Test
  fun derivatives() {
    @Suppress("UNUSED_VARIABLE")
    val p1 = (X - 1) * (X - 3) * ((X + 5) pow 2)
    /*
    val q1 = p1.derivative()
    assertEquals(q1.degree(), 3)
    assertEquals(q1.toString(), "4 * X³ + 18 * X² - 24 * X - 70")
    val q2 = q1.derivative()
    assertEquals(q2.degree(), 2)
    assertEquals(q2.toString(), "12 * X² + 36 * X - 24")
    */
  }
}

```

要运行测试套件，我们当然首先必须编译 Polynomial 类，然后编译 PolynomialTest 类，最后我们可以运行测试套件：

```
$ ktc polynomial.kt
$ ktc polytest.kt
$ kttest PolynomialTest
JUnit version 4.12
.......
Time: 0.03

OK (7 tests)

```

当你对多项式类进行更改时，你可以在每次更改后运行测试套件，以确保一切仍然正常。

#### 从测试套件开始

我们可以再进一步。我们可以将测试套件视为我们要创建的类的正确行为的可执行规范。因此，我们不是先编写代码，然后使用测试套件进行测试，而是首先列出我们的代码必须满足的测试列表以确保正确。然后我们逐个实现对象的方法。每次更改后，几个测试将正确通过。当所有测试都通过时，我们就完成了实现。

让我们回到我们的多项式对象，并假设它还没有给出：我们应该从头开始实现它。

这次我们从测试套件 [polytest.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/60-junit/polytest.kt) 开始。在这里，我们立即遇到一个问题：由于 PolynomialTest 使用 Polynomial 对象，因此在没有 Polynomial 类的情况下无法编译 polytest.kt。

因此，我们将创建一个空的 Polynomial 类框架，显示所有方法及其类型。使用这个框架，我们不仅可以编译测试套件，而且现在还有了我们计划实现的方法的完整文档。

因此，我的多项式类的第一个版本看起来像这样 ([polynomial1.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/60-junit/polynomial1.kt))：

```
@Suppress("UNUSED_PARAMETER")
class Polynomial(coeffs: Array<Int>) {

  constructor(vararg coeffs: Int) : this(coeffs.toTypedArray()) { }

  fun degree(): Int = TODO()

  fun coeff(i: Int): Int = TODO()

  override fun toString(): String = TODO()

  operator fun plus (rhs: Polynomial): Polynomial = TODO()

  operator fun plus(rhs: Int) = this + Polynomial(rhs)

  operator fun minus (rhs: Polynomial): Polynomial = TODO()

  operator fun minus(rhs: Int) = this - Polynomial(rhs)

  operator fun times (rhs: Polynomial): Polynomial = TODO()

  infix fun pow (ex: Int): Polynomial = TODO()

  operator fun invoke(x: Double): Double = TODO()
}

operator fun Int.times(rhs: Polynomial) = Polynomial(this) * rhs

val X = Polynomial(0, 1)

```

我已经定义了我计划实现的类的所有公共方法，包括参数类型和结果类型。每个方法都定义为返回 TODO()。这段代码已经可以编译：

```
$ ktc polynomial1.kt

```

现在我们可以编译测试套件而不会出现任何错误：

```
$ ktc polytest.kt

```

我们运行我们的测试套件：

```
$ kttest PolynomialTest
JUnit version 4.12
.E.E.E.E.E.E.E
Time: 0.026
There were 7 failures:
1) creatingPolynomials(PolynomialTest)
kotlin.NotImplementedError: An operation is not implemented.
	at Polynomial.degree(polynomial1.kt:31)
2) power(PolynomialTest)
kotlin.NotImplementedError: An operation is not implemented.
	at Polynomial.pow(polynomial1.kt:31)
3) additionAndSubtraction(PolynomialTest)
kotlin.NotImplementedError: An operation is not implemented.
	at Polynomial.plus(polynomial1.kt:31)
4) multiplication(PolynomialTest)
kotlin.NotImplementedError: An operation is not implemented.
	at Polynomial.times(polynomial1.kt:31)
5) evaluation(PolynomialTest)
kotlin.NotImplementedError: An operation is not implemented.
	at Polynomial.pow(polynomial1.kt:31)
6) creatingPolynomialsUsingX(PolynomialTest)
kotlin.NotImplementedError: An operation is not implemented.
	at Polynomial.toString(polynomial1.kt:31)
7) derivatives(PolynomialTest)
kotlin.NotImplementedError: An operation is not implemented.
	at Polynomial.minus(polynomial1.kt:31)

FAILURES!!!
Tests run: 7,  Failures: 7

```

当然，所有测试都失败，因为我们的类还没有做任何事情。特别是，如果尝试调用函数 TODO，它会引发 NotImplementedError。（TODO 是一个具有结果类型 Nothing 的特殊函数。由于 Nothing 是每种 Kotlin 类型的子类型，因此可以写成 TODO() 而不是任何类型。但是，没有 Nothing 类型的对象，因此该函数必须引发异常。）

现在我们已经准备好构建我们的多项式类。我首先添加一个构造函数，实现 degree 和 coeff，并编写一个 toString 方法 ([polynomial2.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/60-junit/polynomial2.kt))：

```
@Suppress("UNUSED_PARAMETER")
class Polynomial(coeffs: Array<Int>) {

  constructor(vararg coeffs: Int) : this(coeffs.toTypedArray()) { }

  private val c = createCoeffs(coeffs)

  private fun createCoeffs(a: Array<Int>): List<Int> {
    var s = a.lastIndex
    while (s >= 0 && a[s] == 0)
      s -= 1
    return a.take(s+1)
  }

  fun degree(): Int = c.lastIndex

  fun coeff(i: Int): Int = if (i < c.size) c[i] else 0

  override fun toString(): String {
    var s = StringBuilder()
    var plus = ""
    var minus = "-"
    for (i in degree() downTo 0) {
      if (c[i] != 0) {
	var e = c[i]
	s.append(if (e > 0) plus else minus)
	plus = " + "; minus = " - "
	e = Math.abs(e)
	if (i == 0)
	  s.append(e)
	else {
	  if (e != 1) {
	    s.append(e)
	    s.append(" * ")
	  }
	  if (i > 1) {
	    s.append("X^")
	    s.append(i)
	  } else 
	    s.append("X")
	}
      }
    }
    return s.toString()
  }

  operator fun plus (rhs: Polynomial): Polynomial = TODO()

  operator fun plus(rhs: Int) = this + Polynomial(rhs)

  operator fun minus (rhs: Polynomial): Polynomial = TODO()

  operator fun minus(rhs: Int) = this - Polynomial(rhs)

  operator fun times (rhs: Polynomial): Polynomial = TODO()

  infix fun pow (ex: Int): Polynomial = TODO()

  operator fun invoke(x: Double): Double = TODO()
}

operator fun Int.times(rhs: Polynomial) = Polynomial(this) * rhs

val X = Polynomial(0, 1)

```

我们编译新的 Polynomial 类并再次运行测试套件：

```
$ ktc polynomial2.kt 
$ kttest PolynomialTestJUnit version 4.12
..E.E.E.E.E.E
Time: 0.031
There were 6 failures:
1) power(PolynomialTest)
kotlin.NotImplementedError: An operation is not implemented.
	at Polynomial.pow(polynomial2.kt:66)
...

```

第一个测试现在已经通过：我们可以正确构造多项式对象。只剩下六个失败的测试。我可以继续实现缺失的方法，在每次更新代码后运行测试套件。逐步构建一个正确且完全实现的类。

请注意，我们不需要再次编译测试套件：只需在开始时使用空的 Polynomial 框架进行编译即可！（当然，您可能会发现后来���要添加一些更多的测试，如果修改了 polytest.kt，则当然必须再次编译。）
