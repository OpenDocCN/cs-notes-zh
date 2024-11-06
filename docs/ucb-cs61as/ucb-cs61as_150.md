# 什么是逻辑编程

## 什么是逻辑编程？

在本课程开始时，我们强调计算机科学处理命令式（如何）知识，而数学处理声明式（是什么）知识。事实上，编程语言要求程序员以一种表明解决特定问题的逐步方法的形式表达知识。另一方面，高级语言作为语言实现的一部分，提供了大量的方法论知识，使用户不必担心指定计算将如何进行的许多细节。

大多数编程语言，包括 Lisp，在计算数学函数的值时都是有组织的。面向表达式的语言（如 Lisp，Fortran 和 Algol）利用了一个“双关语”，即描述函数值的表达式也可以被解释为计算该值的手段。因此，大多数编程语言都倾向于单向计算（具有明确定义的输入和输出）。然而，也有一些根本不同的编程语言放松了这种偏见。逻辑编程通过将关系式编程视觉与一种称为统一化的强大符号模式匹配相结合来扩展这一思想。

当这种方法奏效时，编写程序可以是一种非常强大的方式。部分原因在于一个“是什么”事实可以用来解决许多不同的问题，这些问题可能具有不同的“如何”组成部分。

## 一个示例数据库

在我们深入讨论逻辑编程的具体内容之前，我们需要一个数据库来进行操作。您可以使用以下命令加载此数据库：

```
> (load "~cs61as/lib/query.scm")
> (initialize-data-base microshaft-data-base)
> (query-driver-loop) 
```

Microshaft 的人员数据库包含有关公司人员的断言。以下是有关住宅计算机巫师 Ben Bitdiddle 的信息：

```
(address (Bitdiddle Ben) (Slumerville (Ridge Road) 10))
(job (Bitdiddle Ben) (computer wizard))
(salary (Bitdiddle Ben) 60000) 
```

每个断言都是一个列表（在本例中是一个三元组），其元素本身可以是列表。

作为公司的住宅巫师，Ben 负责公司的计算机部门，并监督两名程序员和一名技术员。以下是关于他们的信息：

```
(address (Hacker Alyssa P) (Cambridge (Mass Ave) 78))
(job (Hacker Alyssa P) (computer programmer))
(salary (Hacker Alyssa P) 40000)
(supervisor (Hacker Alyssa P) (Bitdiddle Ben))
(address (Fect Cy D) (Cambridge (Ames Street) 3))
(job (Fect Cy D) (computer programmer))
(salary (Fect Cy D) 35000)
(supervisor (Fect Cy D) (Bitdiddle Ben))
(address (Tweakit Lem E) (Boston (Bay State Road) 22))
(job (Tweakit Lem E) (computer technician))
(salary (Tweakit Lem E) 25000)
(supervisor (Tweakit Lem E) (Bitdiddle Ben)) 
```

还有一个受到 Alyssa 监督的程序员实习生：

```
(address (Reasoner Louis) (Slumerville (Pine Tree Road) 80))
(job (Reasoner Louis) (computer programmer trainee))
(salary (Reasoner Louis) 30000)
(supervisor (Reasoner Louis) (Hacker Alyssa P)) 
```

所有这些人都在计算机部门工作，其工作描述中的第一项为计算机。

Ben 是一名高级员工。他的主管是公司的大佬本人：

```
(supervisor (Bitdiddle Ben) (Warbucks Oliver))
(address (Warbucks Oliver) (Swellesley (Top Heap Road)))
(job (Warbucks Oliver) (administration big wheel))
(salary (Warbucks Oliver) 150000) 
```

除了由 Ben 监督的计算机部门外，公司还有一个会计部门，由一名首席会计师和他的助手组成：

```
(address (Scrooge Eben) (Weston (Shady Lane) 10))
(job (Scrooge Eben) (accounting chief accountant))
(salary (Scrooge Eben) 75000)
(supervisor (Scrooge Eben) (Warbucks Oliver))
(address (Cratchet Robert) (Allston (N Harvard Street) 16))
(job (Cratchet Robert) (accounting scrivener))
(salary (Cratchet Robert) 18000)
(supervisor (Cratchet Robert) (Scrooge Eben)) 
```

还有一个为大佬工作的秘书：

```
(address (Aull DeWitt) (Slumerville (Onion Square) 5))
(job (Aull DeWitt) (administration secretary))
(salary (Aull DeWitt) 25000)
(supervisor (Aull DeWitt) (Warbucks Oliver)) 
```

数据库还包含有关哪些工作可以由从事其他种类工作的人员完成的断言。例如，计算机巫师可以完成计算机程序员和计算机技术员的工作：

```
(can-do-job (computer wizard) (computer programmer))
(can-do-job (computer wizard) (computer technician)) 
```

一名计算机程序员可以代替一名实习生：

```
(can-do-job (computer programmer)
            (computer programmer trainee)) 
```

此外，众所周知，

```
(can-do-job (administration secretary)
            (administration big wheel)) 
```

## 简单查询

查询语言允许用户通过对系统提示的查询来从数据库中检索信息。例如，要找到所有计算机程序员，可以说

```
;;; Query input:
(job ?x (computer programmer)) 
```

系统将以以下项目回应：

```
;;; Query results:
(job (Hacker Alyssa P) (computer programmer))
(job (Fect Cy D) (computer programmer)) 
```

输入查询指定我们正在寻找与某种模式匹配的数据库条目。在这个例子中，模式指定由三个项目组成的条目，其中第一个是文字符号 job，第二个可以是任何东西，第三个是文字列表(computer programmer)。匹配列表中第二个项目的“任何东西”由模式变量`?x`指定。模式变量的一般形式是一个符号，被视为变量的名称，前面加上一个问号。我们将在下面看到为什么指定模式变量的名称比只是在模式中放入?来代表“任何东西”更有用。系统通过显示与指定模式匹配的数据库中的所有条目来响应简单查询。

一个模式可以有多个变量。例如，查询

```
(address ?x ?y) 
```

将列出所有员工的地址。

一个模式可以没有变量，这种情况下查询只是确定该模式是否是数据库中的一个条目。如果是，将会有一个匹配；如果不是，将没有匹配。

同一个模式变量可以在查询中出现多次，指定相同的“任何东西”必须出现在每个位置。这就是为什么变量有名称。例如，

```
(supervisor ?x ?x) 
```

找到所有自我监督的人（尽管在我们的示例数据库中没有这样的断言）。

查询

```
(job ?x (computer ?type)) 
```

匹配所有第三个项目是一个两元素列表且第一个项目是 computer 的工作条目：

```
(job (Bitdiddle Ben) (computer wizard))
(job (Hacker Alyssa P) (computer programmer))
(job (Fect Cy D) (computer programmer))
(job (Tweakit Lem E) (computer technician)) 
```

这个相同的模式不匹配

```
(job (Reasoner Louis) (computer programmer trainee)) 
```

因为条目中的第三个项目是一个包含三个元素的列表，而模式的第三个项目指定应该有两个元素。如果我们想要更改模式，使第三个项目可以是以 computer 开头的任何列表，我们可以指定

```
(job ?x (computer . ?type)) 
```

例如，

```
(computer . ?type) 
```

匹配数据

```
(computer programmer trainee) 
```

以`?type`为列表`(programmer trainee)`。它也匹配数据

```
(computer programmer) 
```

以`?type`为列表`(programmer)`，并匹配数据

```
(computer) 
```

以`?type`为空列表`()`。

我们可以描述查询语言对简单查询的处理如下：

+   系统找到查询模式中所有满足模式的变量赋值 -- 也就是说，所有变量的值集合，使得如果将模式变量实例化（替换为）这些值，结果就在数据库中。

+   系统通过列出满足它的变量赋值的查询模式的所有实例来响应查询。

请注意，如果模式没有变量，则查询将简化为确定该模式是否在数据库中。如果是，则空赋值，即不为变量分配任何值，将满足该数据基的模式。

**断言和查询：第 1 部分**

在数据库中添加一些关于你喜欢的事物的断言。这应该看起来非常类似于

```
(assert! (likes brian potstickers))
```

接下来，编写一个查询，返回所有你喜欢的事物。它应该返回你刚刚添加的所有断言。

**断言和查询：第 2 部分**

在数据库中再添加一些关于你的项目伙伴喜欢的事物的断言。编写另一个查询，返回他/她喜欢的所有事物。

**断言和查询：第 3 部分**

最后，编写一个查询，返回数据库中任何人喜欢的所有事物。

**简单查询**

给出从数据库中检索以下信息的简单查询：

1.  所有由 Ben Bitdiddle 监督的人;

1.  会计部门所有人的姓名和工作;

1.  住在 Slumerville 的所有人的姓名和地址。

记住，要加载示例数据库并运行查询系统，请在解释器中键入以下命令：

```
 (load "~cs61as/lib/query.scm")
(initialize-data-base microshaft-data-base)
(query-driver-loop)
```

## 复合查询

简单查询构成了查询语言的基本操作。为了形成复合操作，查询语言提供了组合的手段。使查询语言成为逻辑编程语言的一点是，组合手段反映了形成逻辑表达式时使用的组合手段：与、或和非。（这里的与、或和非不是 Lisp 的原语，而是内置于查询语言中的操作。）

我们可以如下使用与来找到所有计算机程序员的地址：

```
(and (job ?person (computer programmer))
     (address ?person ?where)) 
```

结果输出为

```
(and (job (Hacker Alyssa P) (computer programmer))
     (address (Hacker Alyssa P) (Cambridge (Mass Ave) 78)))
(and (job (Fect Cy D) (computer programmer))
     (address (Fect Cy D) (Cambridge (Ames Street) 3))) 
```

一般来说，

```
(and <query1> <query2> ... <queryn>) 
```

对于同时满足`<query1> <query2> ... <queryn>`的模式变量值集合都满足

至于简单查询，系统通过找到满足查询的所有模式变量赋值，然后显示具有这些值的实例化来处理复合查询。

另一种构建复合查询的方法是通过或。例如，

```
(or (supervisor ?x (Bitdiddle Ben))
    (supervisor ?x (Hacker Alyssa P))) 
```

将找到所有由 Ben Bitdiddle 或 Alyssa P. Hacker 监督的员工：

```
(or (supervisor (Hacker Alyssa P) (Bitdiddle Ben))
    (supervisor (Hacker Alyssa P) (Hacker Alyssa P)))

(or (supervisor (Fect Cy D) (Bitdiddle Ben)) 
    (supervisor (Fect Cy D) (Hacker Alyssa P)))

(or (supervisor (Tweakit Lem E) (Bitdiddle Ben))     
    (supervisor (Tweakit Lem E) (Hacker Alyssa P))) 

(or (supervisor (Reasoner Louis) (Bitdiddle Ben)) 
    (supervisor (Reasoner Louis) (Hacker Alyssa P))) 
```

一般来说，

```
(or <query1> <query2> ... <queryn> ) 
```

对于所有满足至少一个`<query1> <query2> ... <queryn>`的模式变量值集合都满足。

复合查询也可以用`not`形成。例如，

```
(and (supervisor ?x (Bitdiddle Ben))
     (not (job ?x (computer programmer)))) 
```

找到所有由 Ben Bitdiddle 监督的不是计算机程序员的人。一般来说，

```
(not <query1>) 
```

对于所有不满足`<query1>`的模式变量赋值都满足。

最终的组合形式称为`lisp-value`。当`lisp-value`是模式的第一个元素时，它指定下一个元素是一个应用于其余（实例化的）元素作为参数的 Lisp 谓词。一般来说，

```
(lisp-value <predicate> <arg1> ... <argn>) 
```

将满足模式变量的赋值，其中应用于实例化的`<arg1> ... <argn>`的`<predicate>`为真。例如，要找到所有薪水大于$30,000 的人，我们可以写

```
(and (salary ?person ?amount)
     (lisp-value > ?amount 30000)) 
```

## 规则

只要我们告诉系统孤立的事实，我们就无法得到非常有趣的回复。但我们也可以告诉它*规则*，让它从一个事实推断出另一个事实。例如，如果我们有很多事实，比如：

```
(mother Eve Cain) 
```

那么我们可以建立一个关于祖母关系的规则：

```
(assert! (rule (grandmother ?elder ?younger)
               (and (mother ?elder ?mom)
                    (mother ?mom ?younger) )))) 
```

规则说第一部分（结论）为真*如果*我们可以找到变量的值，使得第二部分（条件）为真。

再次，抵制尝试进行函数的组合的诱惑！

```
(assert! (rule (grandmother ?elder ?younger) ;; WRONG!!!!
               (mother ?elder (mother ?younger)) )) 
```

`Mother`不是一个函数，你不能像这个错误的例子尝试的那样询问某人的母亲。相反，就像上面的正确版本一样，你必须建立一个变量（`?mom`），它有一个满足我们需要的两个母亲关系的值。

在这种语言中，单词`assert！，rule，and，or`和`not`具有特殊含义。其他一切都只是可以成为断言或规则的词。

**分析家谱**

让我们尝试写一些规则！以下数据库（参见创世记 4）通过该数据库追溯了亚当的后裔的家谱，经由该迦音：

```
(son Adam Cain)
(son Cain Enoch)
(son Enoch Irad)
(son Irad Mehujael)
(son Mehujael Methushael)
(son Methushael Lamech)
(wife Lamech Ada)
(son Ada Jabal)
(son Ada Jubal)
```

制定规则，如“如果 S 是 F 的儿子，F 是 G 的儿子，那么 S 是 G 的孙子”和“如果 W 是 M 的妻子，S 是 W 的儿子，那么 S 是 M 的儿子”（在圣经时代比今天更真实）将使查询系统能够找到该因的孙子；拉麦的儿子；麦土沙的孙子。

## 更多规则

这是一个稍微复杂��规则：

```
(rule (lives-near ?person-1 ?person-2)
      (and (address ?person-1 (?town . ?rest-1))
           (address ?person-2 (?town . ?rest-2))
           (not (same ?person-1 ?person-2)))) 
```

它指定如果两个人住在同一个城镇，那么他们住在附近。最后的`not`子句防止规则说所有人都住在自己附近。`same`关系由非常简单的规则定义：

```
(rule (same ?x ?x)) 
```

**拼车时间**

通过给出查询

```
(lives-near ?person (Hacker Alyssa P))
```

艾莉莎·P·哈克能够找到住在她附近的人，与他们一起上班。另一方面，当她试图通过查询找到所有住在附近的人的配对时

```
(lives-near ?person-1 ?person-2)
```

她注意到每对住在附近的人都被列出两次；例如，

```
(lives-near (Hacker Alyssa P) (Fect Cy D))
(lives-near (Fect Cy D) (Hacker Alyssa P))
```

为什么会发生这种情况？有没有办法找到一个住在附近的人的列表，其中每对只出现一次？解释一下。（不要写代码！）

## 逻辑作为程序

我们可以将规则视为一种逻辑蕴涵：*如果*对模式变量的值的分配满足主体，*那么*它满足结论。因此，我们可以认为查询语言具有根据规则执行*逻辑推理*的能力。例如，考虑`append`操作。`Append`可以由以下两条规则表征：

+   对于任何列表`y`，空列表和`y`连接形成`y`。

+   对于任何`u`、`v`、`y`和`z`，如果`v`和`y`连接形成`z`，那么`(cons u v)`和`y`连接形成`(cons u z)`。

要在我们的查询语言中表达这一点，我们为一个关系定义了两条规则

```
(append x y z) 
```

我们可以解释为“x 和 y 连接形成 z”：

```
(assert! (rule (append () ?y ?y)))
(assert! (rule (append (?u . ?v) ?y (?u . ?z))
         (append ?v ?y ?z))) 
```

第一条规则没有主体，这意味着结论对于任何`?y`的值都成立。请注意第二条规则如何使用点尾符号来命名列表的 car 和 cdr。

遵循这两条规则，我们可以制定计算两个列表追加的查询：

```
;;; Query input:
(append (a b) (c d) ?what)
;;; Query results:
(append (a b) (c d) (a b c d)) 
```

更引人注目的是，我们可以使用相同的规则来询问“哪个列表，当追加到`(a b)`时，会产生`(a b c d)`？”这样做如下：

```
;;; Query input:
(append (a b) ?what (a b c d))
;;; Query results:
(append (a b) (c d) (a b c d)) 
```

逻辑编程中的新事物是我们可以反向运行一个“函数”！我们可以告诉它答案，然后得到问题。但真正的魔力是...

```
;;; Query input:
(append ?this ?that (a b c d))
;;; Query results:
(append () (a b c d) (a b c d))
(append (a) (b c d) (a b c d))
(append (a b) (c d) (a b c d))
(append (a b c) (d) (a b c d))
(append (a b c d) () (a b c d)) 
```

我们还可以询问所有追加形成`(a b c d)`的列表对！我们可以使用逻辑编程来计算相同问题的多个答案！不知何故，它找到了使我们的查询成立的所有可能值的组合。

追加程序是如何工作的？将其与 Scheme 的`append`进行比较：

```
(define (append a b)
    (if (null? a)
        b
        (cons (car a) (append (cdr a) b)) )) 
```

像 Scheme 程序一样，逻辑程序有两种情况：有一个基本情况，其中第一个参数为空。在这种情况下，组合列表与第二个追加列表相同。还有一个递归情况，在这种情况下，我们将第一个追加列表分为其 car 和 cdr。我们将给定的问题简化为关于将`(cdr a)`追加到`b`的问题。逻辑程序在形式上不同，但它表达的是同样的意思。

(就像在祖母的例子中，我们不得不给母亲一个名字而不是使用函数调用一样，在这里我们必须给`(car a)`一个名字--我们称之为`?u`。)

## 警告

查询系统似乎展示了相当多的智能，使用规则推断上述查询的答案。实际上，正如我们将在下一节中看到的那样，系统在解开规则时遵循一个明确定义的算法。不幸的是，尽管系统在追加案例中表现出色，但在更复杂的情况下，一般方法可能会失效。

在追加案例中使用的“向后工作”的魔法并不总是奏效。让我们看看下面的例子，它颠倒了一个列表。

```
(assert! (rule (reverse (?a . ?x) ?y)
               (and (reverse ?x ?z)
                    (append ?z (?a) ?y) )))

(assert! (reverse () ())) 
```

这对于`(reverse (a b c) ?what)`有效，但���过来不行；它会陷入无限循环。我们也可以编写一个仅向后工作的版本：

```
(assert! (rule (backward (?a . ?x) ?y)
               (and (append ?z (?a) ?y)
                    (backward ?x ?z) )))

(assert! (backward () ())) 
```

但编写一个双向工作的程序要困难得多。即使在我们说话的同时，逻辑编程爱好者也在尝试推动这个想法的极限，但现在，你仍然需要了解一些关于下面的算法才能确信你的逻辑程序不会循环。

**最后一对**

定义规则来实现[SICP 练习 2.17](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-15.html#%_thm_2.17)的`last-pair`操作，该操作返回包含非空列表的最后一个元素的列表。在类似`(last-pair (3) ?x)`、`(last-pair (1 2 3) ?x)`和`(last-pair (2 ?x) (3))`的查询上检查你的规则。你的规则在类似`(last-pair ?x (3))`的查询上是否正确？

## 要点

以下是这一小节的一些要点：

+   在逻辑编程中，我们断言事实并提出问题。

+   一个断言由一个列表表示。

+   我们使用查询语言从数据库中检索信息。

+   规则允许从一个事实推断出另一个事实。

+   我们可以使用逻辑编程编写诸如`append`之类的程序！

## 接下来是什么？

前往下一小节，了解查询系统的工作原理！
