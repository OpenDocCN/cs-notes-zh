# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p128 08_02_01_介绍_1.zh_en -BV18U411U729_p128-

![](img/d913fdc02f23a7640fbb25d23526a20e_0.png)

Another problem you might want to solve using your earthquake data。

 which is a quite common type of problem when your data has a lot of information in it。

 is to filter the data to take an array list of earthquakes and produce an array list with those quakes which match some specific criteria。

 For example， you might only be interested in those earthquakes which have at least a certain magnitude。

 or you might want to only examine the set of earthquakes that are within a certain distance of your or some other specific location。

 or any other number of criteria。

![](img/d913fdc02f23a7640fbb25d23526a20e_2.png)

If you were to solve this problem for any of these criteria。

 you would find that it does not require new algorithmic concepts。

 You should be able to apply the seven step method and translate your algorithm to code using things that you have already learned however。

 if you were to solve this problem for more than one criteria。

 writing a method that filters by magnitude and another that filters by distance。

 you would find that the algorithm and code are quite similar between the two criteria。

 if you had many criteria， you would find yourself solving basically the same problem over and over and writing code that looks quite similar when you are programming。

 you should avoid duplicating code， rewriting similar code over and over again。

 not only does it waste your time， but it also introduces more opportunities to make mistakes and makes your code harder to maintain in the future。

 a better approach would be to write one method to filter earthquakes， which takes a parameter。

 specifying what the criteria is writing this generic method requires a new concept which。

We're going to learn about now。