# 带有方法的类

对象是面向对象编程的基础。在 Scala 中，每个数据都是一个对象。对象的类型决定了你可以对对象做什么。类可以包含数据（对象的状态）和方法（你可以对对象做什么）。你可以把类看作是对象的蓝图。一旦你定义了一个类，你就可以使用关键字 new 从蓝图创建对象。

将对象视为一个原子单位。客户端（这是指使用对象的程序代码）不关心对象的实现，它们只使用公开的方法和字段。这里的“公开”意味着它们由类提供给客户端使用。

#### 一致性

日期由三个属性组成：年、月和日，它们都是整数。因此，我们可以将日期存储为一个三元组 Triple<Int, Int, Int>，但是如果它们表示年-月-日，或者日-月-年，我们可能会感到困惑。最好创建一个具有三个属性的数据类：

```
data class Date(val year: Int, val month: Int, val day: Int)

```

然而，这两种方法都不能保证我们的日期对象是一致的。一致性意味着属性只取合法的、有意义的值，并且每个属性的值与其他属性的值一致。例如，一个日期值为 31 是与一个月值为 3 一致的，但与一个月值为 4 的不一致。一个日期值为 29 和一个月值为 2 只有在年值表示闰年时才一致。使用上面定义的数据类，我们没有任何限制，可以犯这样的错误：

```
>>> data class Date(val year: Int, val month: Int, val day: Int)
>>> val d = Date(2017, 13, -5)
>>> d
Date(year=2017, month=13, day=-5)

```

为了确保我们的日期对象始终保持一致，我们可以在对象的构造函数中添加四个 require 语句。它由关键字 init 指示，后跟在每次创建此类型的对象时执行的语句（[days1.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/50-objects/days1.kt)）：

```
val monthLength = intArrayOf(31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31)

data class Date(val year: Int, val month: Int, val day: Int) {
  init {
    require(1901 <= year && year <= 2099)
    require(1 <= month && month <= 12)
    require(1 <= day && day <= monthLength[month - 1])
    require(month != 2 || day <= 28 || (year % 4) == 0)
  }
}

```

如果值正常，什么都不会发生。否则，require 会抛出一个异常，我们立即就知道出了什么问题。由于日期对象是不可变的，因此在对象构造时保证的一致状态永远不会被破坏和变得不一致。

如果对象保证它们的状态是一致的，那将会很有帮助。这样可以使得与对象一起工作的函数能够进行无错误检查的操作，并简化调试，因为当出现问题时我们会很快注意到。

要使用我的新的日期对象，我必须编译定义，然后可以交互式地测试它：

```
>>> val d1 = Date(2017, 3, 17)
>>> d1
Date(year=2017, month=3, day=17)
>>> d1.year
2017
>>> d1.day
17
>>> var d2 = Date(2017, 2, 29)
java.lang.IllegalArgumentException: Failed requirement
	at Date.<init>(days1.kt:24)

```

#### 方法

在过去，我们有函数接受特定类型的参数，比如一个函数 date2num ，它将一个日期表示为年、月和日，转换为从 1901 年 1 月 1 日开始的日期索引。

在面向对象编程中，我们更喜欢将适用于特定类型的函数定义为该类型的方法。其中一个优点是它清晰地记录了给定类型可用的函数（例如，要找出可以对字符串执行的操作，您可以查看 String 类的方法列表）。然而，主要优点将是隐藏或保护对象内部信息的可能性，正如我们稍后将看到的那样。

暂时，让我们添加方法来将 Date 对象转换为日期索引，并返回日期的星期几 ([days3.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/50-objects/days3.kt))：

```
val monthLength = intArrayOf(31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31)
val weekday = arrayOf("Monday", "Tuesday", "Wednesday", "Thursday",
		      "Friday", "Saturday", "Sunday")

data class Date(val year: Int, val month: Int, val day: Int) {
  init {
    require(1901 <= year && year <= 2099)
    require(1 <= month && month <= 12)
    require(1 <= day && day <= monthLength[month - 1])
    require(month != 2 || day <= 28 || (year % 4) == 0)
  }

  // returns the number of days since 1901/01/01 (day 0)
  fun dayIndex(): Int {
    val fourY = (365 + 365 + 365 + 366)
    val yearn = year - 1901
    var total = 0
    total += fourY * (yearn / 4)
    total += 365 * (yearn % 4)
    for (m in 0 until month - 1)
      total += monthLength[m]
    total += day - 1
    if (year%4 != 0 && month > 2)
      total -= 1
    return total
  }

  fun dayOfWeek(): String = weekday[(dayIndex() + 1) % 7]
}

```

方法看起来像函数定义，但放置在类的主体内。方法的主体可以引用对象的字段名称：注意在方法 `dayIndex` 中使用了年、月和日字段。

只有当我们有可用于引用该类型对象的引用时，才能调用方法，因此每当执行方法时，总会有一个“当前”对象。字段名称指的是此“当前”对象的字段：

```
$ ktc days3.kt 
$ ktc
Welcome to Kotlin version 1.0.1-2 (JRE 1.8.0_74-b02)
Type :help for help, :quit for quit
>>> var d1 = Date(2017, 4, 16)
>>> var d2 = Date(2000, 1, 1)
>>> d1.year
2017
>>> d2.month
1
>>> d1.dayIndex()
42474
>>> d2.dayIndex()
36159
>>> d1.dayOfWeek()
Sunday
>>> d2.dayOfWeek()
Saturday

```

#### 打印漂亮的日期

Kotlin 或 Java 中的每个对象都可以转换为字符串，这就是在交互模式或使用 `println` 时发生的情况：首先使用其 `toString` 方法将对象转换为字符串：

```
>>> d1
Date(year=2017, month=4, day=16)
>>> d1.toString()
Date(year=2017, month=4, day=16)
>>> println(d1)
Date(year=2017, month=4, day=16)

```

由于我们将 Date 定义为数据类，编译器提供了一个合理的 `toString` 方法，显示类名和每个字段的值。

在生产质量的代码中，我们可能希望有一个漂亮的日期表示。我们可以通过重写 `toString` 方法的默认定义来实现这一点，就像这样 ([days4.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/50-objects/days4.kt))：

```
override fun toString(): String = 
  "%s, %s %d, %d".format(dayOfWeek(), monthname[month-1], day, year)

```

注意关键字 `override`。这是必需的，因为每个对象已经有一个 `toString` 方法。因此，我们不是添加一个新方法，而是重写了之前的定义。

有了这个方法，我们的对象看起来更漂亮了：

```
$ ktc days4.kt 
$ ktc
Welcome to Kotlin version 1.0.1-2 (JRE 1.8.0_74-b02)
Type :help for help, :quit for quit
>>> val d1 = Date(2017, 4, 16)
>>> d1
Sunday, April 16, 2017
>>> d1.toString()
Sunday, April 16, 2017
>>> println(d1)
Sunday, April 16, 2017

```

#### 运算符就是方法

让我们添加一个方法来计算两个日期之间的天数。由于我们已经有了 `dayIndex()`，这个实现非常容易 ([days5.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/50-objects/days5.kt))：

```
  fun diff(rhs: Date): Int = dayIndex() - rhs.dayIndex()

```

它表现良好：

```
$ ktc days5.kt 
$ ktc
Welcome to Kotlin version 1.0.1-2 (JRE 1.8.0_74-b02)
Type :help for help, :quit for quit
>>> var d1 = Date(1993, 7, 9)
>>> var d2 = Date(2017, 4, 9)
>>> d2.diff(d1)
8675

```

但如果我们能够写 `d2 - d1` 来表示两个日期之间的差异，而不是不那么美观的 `d2.diff(d1)`，那不是很好吗？

在 Kotlin 中，与 Java 不同，这是可能的。事实上，在 Kotlin 中，像 `+` 这样的运算符和像 `take` 这样的方法之间根本没有区别——它们都被实现为方法。

要定义减法运算符 `-`，我们只需将我们的 `diff` 方法重命名为 `minus`，并添加关键字 `operator` ([days6.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/50-objects/days6.kt))：

```
  operator fun minus(rhs: Date): Int = dayIndex() - rhs.dayIndex()

```

我们现在可以计算日期了：

```
$ ktc days6.kt 
$ ktc
Welcome to Kotlin version 1.0.1-2 (JRE 1.8.0_74-b02)
Type :help for help, :quit for quit
>>> val birth = Date(1993, 7, 9)
>>> val today = Date(2017, 4, 17)
>>> today - birth
8683

```

定义自己的运算符可能很有趣，但不要过分——只有在代码更易读时才有用！

#### 重载

Scala，像 Java 和 C++一样，但与 C 不同，允许方法名的重载：允许有不同的方法具有相同的名称，只是在它们接受的参数类型上有所不同。这里是一个简单的例子（[overloading.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/05-basic/overloading.kts)）：

```

fun f(n: Int) {
  println("Int " + n)
}

fun f(s: String) {
  println("String " + s)
}

f(17)
f("CS109")

```

编译器正确确定 f(17)是对第一个函数的调用，而 f("CS109")是对第二个函数的调用。

我们可以利用重载来为我们的 Date 类添加更多运算符。我们将允许将一定数量的天数加或减到日期上以获得一个新日期（[days7.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/50-objects/days7.kt)）:

```
val monthLength = intArrayOf(31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31)
val weekday = arrayOf("Monday", "Tuesday", "Wednesday", "Thursday",
		      "Friday", "Saturday", "Sunday")
val monthname = arrayOf("January", "February", "March",
		        "April", "May", "June",
		        "July", "August", "September",
		        "October", "November", "December")

data class Date(val year: Int, val month: Int, val day: Int) {
  init {
    require(1901 <= year && year <= 2099)
    require(1 <= month && month <= 12)
    require(1 <= day && day <= monthLength[month - 1])
    require(month != 2 || day <= 28 || (year % 4) == 0)
  }

  // returns the number of days since 1901/01/01 (day 0)
  fun dayIndex(): Int {
    val fourY = (365 + 365 + 365 + 366)
    val yearn = year - 1901
    var total = 0
    total += fourY * (yearn / 4)
    total += 365 * (yearn % 4)
    for (m in 0 until month - 1)
      total += monthLength[m]
    total += day - 1
    if (year%4 != 0 && month > 2)
      total -= 1
    return total
  }

  fun num2date(n: Int): Date {
    val fourY = (365 + 365 + 365 + 366)
    var year = 1901 + (n / fourY) * 4
    var day = n % fourY 
    if (day >= 365 + 365 + 365 + 59) {
      year += 3
      day -= 365 + 365 + 365
    } else {
      year += (day / 365)
      day = day % 365
      if (day >= 59)
	day += 1
    }
    var month = 1
    while (day >= monthLength[month-1]) {
      day -= monthLength[month-1]
      month += 1
    }
    return Date(year, month, day+1)
  }

  fun dayOfWeek(): String = weekday[(dayIndex() + 1) % 7]

  override fun toString(): String = 
    "%s, %s %d, %d".format(dayOfWeek(), monthname[month-1],
			   day, year)

  operator fun minus(rhs: Date): Int = dayIndex() - rhs.dayIndex()

  operator fun plus(n: Int): Date = num2date(dayIndex() + n)
  operator fun minus(n: Int): Date = num2date(dayIndex() - n)

}

```

请注意，Date 类定义了两个减号运算符。编译器根据右侧的类型选择我们需要的那一个：

```
$ ktc days7.kt 
$ ktc
Welcome to Kotlin version 1.0.1-2 (JRE 1.8.0_74-b02)
Type :help for help, :quit for quit
>>> val birth = Date(1992, 8, 21)
>>> val baekil = birth + 100
>>> baekil
Sunday, November 29, 1992
>>> val today = Date(2017, 4, 19)
>>> today - birth
9007
>>> today - 9007
Friday, August 21, 1992
>>> birth + 9007
Wednesday, April 19, 2017

```

#### 一个真正的程序

既然我们现在有了一个不错的日期类，让我们写一个程序来使用它（[days.kt](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/50-objects/days.kt)）：

```
val digits = "0123456789"

// if s is not a legal date, or is not in range, 
// then throws IllegalArgumentException
fun getDate(s: String): Date {
  if (s.length != 10 || s[4] != '/' || s[7] != '/')
    throw IllegalArgumentException()
  for ((i, ch) in s.withIndex()) {
    if (i != 4 && i != 7 && ch !in digits)
      throw IllegalArgumentException()
  }
  val year = s.substring(0, 4).toInt()
  val month = s.substring(5, 7).toInt()
  val day = s.substring(8).toInt()
  return Date(year, month, day)
}

fun main(args: Array<String>) {
  try {
    if (args.size == 1) {
      val d = getDate(args[0])
      println("$d is a ${d.dayOfWeek()}")
    } else if (args.size == 2) {
      val d1 = getDate(args[0])
      val d2 = getDate(args[1])
      println("There are ${d2 - d1} days between $d1 and $d2")
    } else if (args.size == 3) {
      val d1 = getDate(args[0])
      val sign = if (args[1] == "-") -1 else +1
      val dist = args[2].toInt()
      val d2 = d1 + sign * dist
      println("$d1 ${args[1]} $dist days = $d2")
    } else {
      System.err.println("Must have one, two, or three arguments")
    }
  }
  catch (e: NumberFormatException) {
    System.err.println("Illegal number")
  }
  catch (e: IllegalArgumentException) {
    System.err.println("Illegal date")
  }
}

```

如在前一节中所解释的，程序通过主函数启动，该函数以参数 args 的形式接收命令行参数。

我们编译程序：

```
$ ktc days.kt 

```

编译器为包含主函数的源文件生成一个类 DaysKt，因此这是我们需要调用来运行程序的类：

```
$ kt DaysKt 2015/a3/04
Illegal date
$ kt DaysKt 2016/04/26
Tuesday, April 26, 2016 is a Tuesday
$ kt DaysKt 2016/04/26 2017/01/01
There are 250 days between Tuesday, April 26, 2016 and Sunday, January 1, 2017
$ kt DaysKt 2016/04/26 + 250
Tuesday, April 26, 2016 + 250 days = Sunday, January 1, 2017
$ kt DaysKt 2016/04/26 - 100
Tuesday, April 26, 2016 - 100 days = Sunday, January 17, 2016

```
