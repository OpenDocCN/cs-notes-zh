# 枚举

枚举（enum）是一种具有有限值集合的类型，例如 "yes"、"no"、"maybe"，或者 "north"、"south"、"east"、"west"。

枚举的定义如下：

```
>>> enum class Answer { YES, NO, MAYBE }
>>> enum class Direction { NORTH, SOUTH, EAST, WEST }

```

Answer 和 Direction 是类型名称，类型的值写为 Answer.YES 或 Direction.SOUTH：

```
>>> var a: Answer = Answer.YES
>>> val b = Answer.NO
>>> val dir = Direction.EAST

```

枚举值具有很好的 toString 方法，也可以通过 name 属性获取它们的名称：

```
>>> a
YES
>>> a.name
YES
>>> b
NO
>>> dir
EAST

```

但是，在内部，枚举被表示为整数。您可以使用 ordinal 属性获得整数。枚举值可以进行比较（按照声明的顺序）：

```
>>> a.ordinal
0
>>> b.ordinal
1
>>> dir.ordinal
2
>>> a < Answer.MAYBE
true
>>> dir < Direction.SOUTH
false

```

使用枚举类的 valueOf 方法，可以将字符串转换为枚举值：

```
>>> Answer.valueOf("YES")
YES
>>> Direction.valueOf("WEST")
WEST
>>> Direction.valueOf("NOWHERE")
java.lang.IllegalArgumentException: No enum constant Line2.Direction.NOWHERE

```

也可以获取所有可能值的列表：

```
>>> for (e in Answer.values()) println(e)
YES
NO
MAYBE

```
