# 入门指南

## 入门指南

在这个实验任务中，我们将探索两个关键想法：

+   对象由一组状态变量来表征的世界的模拟

+   使用**消息传递**作为一种编程技术，用于模块化对象相互作用的世界。

面向对象编程正变得越来越受欢迎，这是一种适用于涉及计算实体相互作用的任何应用程序的方法论。

一些示例包括：

+   操作系统（进程作为对象）

+   Windows 系统（窗口作为对象）

+   游戏（如小行星、太空船、大猩猩作为对象）

+   绘图程序（形状作为对象）

## 项目文件

要开始，将项目所需的文件复制到您的目录中：

```
cp -r ~cs61as/lib/adventure/ . 
```

| 文件名 | 目的 |
| --- | --- |
| 1.`obj.scm` | 我们面向对象系统的代码。 |
| 2.`adv.scm` | 冒险游戏程序。它包含了对象类的定义。 |
| 3.`tables.scm` | 您将在问题 A5 和 B4 中需要的 ADT。 |
| 4.`adv-world.scm` | 冒险游戏中对象（即人、地点和物品）的具体实例。 |
| 5.`small-world.scm` | 一个更小、更简化的世界，您可以用于调试。 |

要在此项目上工作，您必须按照上表中的确切顺序将这些文件加载到 STk 中。只加载`adv-world.scm`或`small-world.scm`之一，但不是两者都加载。您被要求完成的工作是指`adv-world.scm`；提供`small-world.scm`是为了让您更愿意在较小的世界中调试一些可能更不复杂、也更快速加载的过程。

要加载一个 Scheme 文件，例如，`obj.scm`，请输入

```
(load "obj.scm") 
```

到解释器中。

将冒险游戏分为`adv.scm`和`adv-world.scm`的原因是，当您对`adv.scm`中的类定义进行任何更改时，您可能需要重新加载整个世界，以使您更改后的版本生效。拥有两个文件意味着您不必再重新加载第一批过程。

## 程序简介

在此程序中有三个主要类别：人、地点和物品。

以下是从`adv-world.scm`中选取的一些示例：

```
;;; construct the places in the world
(define Soda (instantiate place 'Soda))
(define BH-Office (instantiate place 'BH-Office))
(define art-gallery (instantiate place 'art-gallery))
(define Pimentel (instantiate place 'Pimentel))
(define 61A-Lab (instantiate place '61A-Lab))
(define Sproul-Plaza (instantiate place 'Sproul-Plaza))
(define Telegraph-Ave (instantiate place 'Telegraph-Ave))
(define Noahs (instantiate place 'Noahs))
(define Intermezzo (instantiate place 'Intermezzo))
(define s-h (instantiate place 'sproul-hall))

;;; make some things and put them at places
(define bagel (instantiate thing 'bagel))
(ask Noahs 'appear bagel)

(define coffee (instantiate thing 'coffee))
(ask Intermezzo 'appear coffee)

;;; make some people
(define Brian (instantiate person 'Brian BH-Office))
(define hacker (instantiate person 'hacker Pimentel))

;;; connect places in the world
(can-go Soda 'up art-gallery)
(can-go art-gallery 'west BH-Office)
(can-go Soda 'south Pimentel) 
```

构建了这个世界之后，我们现在可以通过向物体发送消息来与之交互。以下是一个简短的示例：

```
; We start with the hacker in Pimentel.

> (ask Pimentel 'exits)
(NORTH SOUTH)
> (ask hacker 'go 'north)
HACKER moved from PIMENTEL to SODA 
```

我们可以把物体放在不同的地方，然后人们可以拿走这些物体：

```
> (define Jolt (instantiate thing 'Jolt))
JOLT
> (ask Soda 'appear Jolt)
APPEARED
> (ask hacker 'take Jolt)
HACKER took JOLT
TAKEN 
```

你可以从其他人那里拿走物体，但是管理者不对后果负责...（很遗憾，这是一个幻想游戏，在苏打楼里并没有真的自动售货机存放 Jolt。）
