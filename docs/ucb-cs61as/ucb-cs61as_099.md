# 双方练习

## 说明

本部分的前两个练习应由双方合作完成！只要双方完全理解练习和所涵盖的概念，就可以成对工作。 （仍然应只有一个解决方案，双方都同意。）剩余的练习将有诸如“A3”之类的数字，这对应于“合作伙伴 A 的练习 3”。

项目分为两个主要部分。 在双方都完成了第 1 部分的练习后，将您的工作合并在一起，并确保其中一个合作伙伴了解另一个人的工作。 由于项目的第 2 部分取决于第 1 部分的工作代码，请小心地组合您的`adv.scm`和`adv-world.scm`的代码。

## 问题 1

实例化一个新的 Person 对象来代表你自己。 把自己放在一个叫做`dormitory`（或者你住在哪里）的新地方，并将其连接到校园，以便可以到达。 创建一个叫做`kirin`的地方，位于`soda`的北面。 （实际上它在 Solano 大道上。）在那里放一个叫做`potstickers`的东西。 然后给出必要的命令，将您的角色移动到`kirin`，拿起`potstickers`，然后将自己移动到`Brian`所在的地方，放下`potstickers`，并让`Brian`拿走。 然后回到实验室，继续工作。 （有传言说你在现实生活中这样做会得到这门课的 A！）所有这些只是为了确保您知道如何讲冒险程序的语言。

**列出在此情节中发送的所有消息。** 在脑海中尝试解决这个问题是个好主意，至少对于一些发生的动作来说是这样，但是您也可以跟踪`ask`过程以获取完整的列表。 您不必提交此消息列表。 （**您必须提交一份不包含跟踪的情节转录。**）此练习的目的是使您熟悉不同对象在执行工作时如何互相发送消息的方式。

[提示：我们提供了一个`move-loop`过程，您可能会发现它作为调试工作的辅助工具。 您可以使用它来重复移动一个人。]

## 问题 2

很重要的是，您考虑并理解参与冒险游戏的对象的类型。 请回答以下问题：

**a)** 变量`Brian`的值是什么类型的东西？ **提示：**在以下情况下 STk 返回什么：

```
> Brian 
```

**b)** 列出地点了解的所有消息。 （您可能希望为自己的每种对象类型维护这样的列表，以帮助调试工作。）

**c)** 我们一直在定义一个变量来保存我们世界中的每个对象。 例如，我们说：

```
> (define bagel (instantiate thing 'bagel)) 
```

这只是为了方便起见。 并非每个对象都必须具有顶层定义。 每个对象都必须构建并连接到世界。 例如，假设我们这样做了：

```
> (can-go Telegraph-Ave 'east (instantiate place 'Peoples-Park))

;;; assume Brian is at Telegraph
> (ask Brian 'go 'east) 
```

以下表达式返回什么以及为什么？

```
> (ask Brian 'place)

> (let ((where (ask Brian 'place)))
       (ask where 'name))

> (ask Peoples-park 'appear bagel) 
```

**d)** 所有这一切的含义是对象可以有多个名称。一个名称是对象内部`name`变量的值。此外，我们可以在顶层定义一个变量来引用一个对象。此外，一个对象可以有另一个对象的私有名称。例如，`Brian`有一个变量`place`，它当前绑定到代表人民公园的对象。一些需要思考的例子：

```
> (eq? (ask Telegraph-Ave 'look-in 'east) (ask Brian 'place))

> (eq? (ask Brian 'place) 'Peoples-Park)

> (eq? (ask (ask Brian 'place) 'name) 'Peoples-Park) 
```

好的。假设我们在 STk 中输入以下内容：

```
> (define computer (instantiate thing 'Durer)) 
```

以下哪个是正确的？为什么？

```
(ask 61a-lab 'appear computer) 
```

或者

```
(ask 61a-lab 'appear Durer) 
```

或者

```
(ask 61a-lab 'appear 'Durer) 
```

`(computer 'name)`返回什么？为什么？

**e)** 我们提供了一个不使用手册中描述的面向对象编程语法的 Thing 类的定义。将其翻译成新的符号。

**f)** 有时候以交互方式调试一个对象是不方便的，因为它的方法返回对象，而我们想要看到对象的名称。你可以创建辅助程序供交互使用（与对象方法内部使用相对），以便以可打印形式提供所需信息。例如：

```
(define (name obj) (ask obj 'name))
(define (inventory obj)
    (if (person? obj)
        (map name (ask obj 'possessions))
        (map name (ask obj 'things)))) 
```

编写一个名为`whereis`的过程，它以一个人作为参数，并返回该人所在地的名称。编写一个名为`owner`的过程，它以一个物品作为参数，并返回拥有它的人的名称。（确保它适用于没有任何所有者的物品。）

类似这样的过程在调试项目的后期非常有帮助，所以请随意为自己编写更多。现在是时候对冒险游戏进行第一次修改了。这是你们分工的时候了。
