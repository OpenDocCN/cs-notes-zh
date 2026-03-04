# SAS【中英⚡SAS高级程序员 专项课程｜SAS Advanced Programmer Professional Certificate】 p44 P44 03_SQL内连接替代语法 -BV1Cfe3z3EoA_p44-

There's alternate syntax you can use to create an inner join in SQL。

 A comma replaces the inner join on the from clauses， and the on clause changes to a where clause。



![](img/7735246b084d785ffa78a08aa28bea23_1.png)

![](img/7735246b084d785ffa78a08aa28bea23_2.png)

Using the from clauses and specifying Jo columns on the where clauses provides the same functionality as listing tables with the inner join keyword and on clauses。

This code produces the same output as the previous code， but uses the wear construction。



![](img/7735246b084d785ffa78a08aa28bea23_4.png)

Be careful using the wear clauses to create a join because you might inadvertently create a Cartesian product and could drain your resources if the tables are large。

The inner join and on syntax helped to avoid that issue。



![](img/7735246b084d785ffa78a08aa28bea23_6.png)