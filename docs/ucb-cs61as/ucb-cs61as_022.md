# 作业 0.3

## 模板

在终端中键入以下命令将作业模板文件复制到当前目录（注意末尾的句点）：

```
cp ~cs61as/autograder/templates/hw0-3.rkt . 
```

或者，你可以在此处下载模板[here](http://inst.eecs.berkeley.edu/~cs61as/templates/hw0-3.rkt)。

## 练习 1

从作业 0-2 中编写`describe-time`过程的新版本。你只需要考虑一天内的时间段。它不应返回一个小数，而应该像这样：

```
-> (describe-time 22222)
'(6 HOURS 10 MINUTES 22 SECONDS)

-> (describe-time 550441)
'(6 DAYS 8 HOURS 54 MINUTES 1 SECONDS) 
```

**提示：** 使用`quotient`！

看看你是否可以使程序足够智能，以知道何时使用复数；这不是必需的。

## 练习 2

这是过程`remove-once`应该如何工作的示例：

```
-> (remove-once 'morning '(good morning good morning))
'(good good morning) 
```

（如果`remove-once`删除了另一个"morning"，也没关系，只要它只删除一个。）

编写`remove-once`。

## 练习 3

编写过程`differences`，它以一组数字作为参数，并返回一个包含相邻元素之间差异的句子。（返回句子的长度比参数少一个。）

```
-> (differences '(4 23 9 87 6 12))
'(19 -14 78 -81 6) 
```

## 练习 4

编写一个名为`location`的过程，它接受两个参数，一个单词和一个句子。它应该返回一个数字，指示单词在句子中的位置。如果单词不在句子中，则返回`#f`。如果单词出现多次，则返回第一次出现的位置。

```
-> (location 'me '(you never give me your money))
4
-> (location 'i '(you never give me your money))
#f
-> (location 'the '(the fork and the spoon))
1 
```

## 练习 5

编写一个过程`initials`，它以一个句子作为参数，并返回句子中每个单词的首字母组成的句子。

```
-> (initials '(if i needed someone))
'(i i n s) 
```

## 练习 6

编写一个过程`copies`，它接受一个数字和一个单词作为参数，并返回一个包含给定单词副本的句子。

```
-> (copies 8 'spam)
'(spam spam spam spam spam spam spam spam) 
```

## 练习 7

编写一个`GPA`过程。它应该接受一个成绩句子作为参数，并返回相应的平均学分绩点。

**提示：** 编写一个名为`base-grade`的辅助过程，它以成绩作为参数并返回`0`、`1`、`2`、`3`或`4`，以及另一个名为`grade-modifier`的辅助过程，根据成绩是否有减号、加号或两者都没有，返回`−.33`、`0`或`.33`。

```
-> (gpa '(A A+ B+ B))
3.67 
```

## 练习 8

编写`repeat-words`，它以一个句子作为参数。它返回一个类似于参数的句子，但是如果参数中出现一个数字，则返回值包含该数字的后续单词的多个副本。

```
-> (repeat-words '(4 calling birds 3 french hens))
'(calling calling calling calling birds french french french hens)
-> (repeat-words '(the 7 samurai))
'(the samurai samurai samurai samurai samurai samurai samurai) 
```

**提示：** 你不必在一个过程中完成所有工作。使用一个辅助过程可能会有所帮助。

## 练习 9

编写一个谓词`same-shape?`，它接受两个句子作为参数。如果满足两个条件，则应返回`#t`：两个句子必须具有相同数量的单词，并且第一个句子中的每个单词必须与第二个句子中相应位置的单词具有相同数量的字母。

```
-> (same-shape? '(the fool on the hill) '(you like me too much))
#t
-> (same-shape? '(the fool on the hill) '(and your bird can sing))
#f 
```

**提示：** 原始过程`count`可能会有用。

## 提交你的作业！

有关说明，请参阅此指南。它涵盖了基本的终端命令和作业提交。

如果你在提交作业时遇到任何问题，请不要犹豫向助教求助！
