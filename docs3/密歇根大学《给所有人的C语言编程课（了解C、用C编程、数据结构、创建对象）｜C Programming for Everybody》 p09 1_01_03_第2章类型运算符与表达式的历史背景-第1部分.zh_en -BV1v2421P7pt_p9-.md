# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p09 1_01_03_第2章类型运算符与表达式的历史背景-第1部分.zh_en -BV1v2421P7pt_p9-

![](img/45ff0e5f73ec9b10f4264fdb0794f430_0.png)

Welcome to Cha 2， typess， operators and Expresss。So again， I'm not going to tell you everything。

 the book， I want you to read the book， the book does a great job。

 I'm just going to call your attention to some things that that might seem a little bit weird if you're coming from a language like Python or JavaScript or even PhP where。

Things are objects and you don't even notice it， you've been using objects your whole career and you didn't even realize it。

So we're going to talk about data types and storage allocation。

 One of the things that you just got a part of what I love about teaching this historical view on C is that we have to talk about storage allocation Flo and double worked out pretty well partly because in the early days of C they did them all in software。

 so they just made them easy and they made them work well they weren't expected expected to be fast to things that they wanted to be super fast were like the integer and Bte byte data character data type conversion and and then there's a story that connects integer division in Python2 and all that pain of Python 3 and how division changed and why it was the way it was and how that worked and again。

 it has to do with performance and simple decisions that got made sadly。Bitwise logical operations。

 We'll talk about them。 You're probably not going to use them。

 but it's really important in a historical context to understand why they were so thorough。

 and it really had to do with the fact that，Because of word oriented computers switching to character oriented computers。

 all of us programmers were thinking in words and if we didn't see shifting and masking and bitwise stuff。

 we'd be like I can't program in this thing because a lot of our work in those word oriented computers was masking and shifting and so it's like we had to have it we didn't use it as much as we could have thought。

So let's start with division。唉。In the good old days。

We were not worried too much about doing division。And if you were doing division and you cared about the division。

 you were probably doing it in floating point because you were doing scientific computing and you did that on supercomputers。

 You didn't do that on general purpose computers。 Uniixer was really designed for general purpose computers。

 And in general purpose computers， you sort of thought to yourself in a wise division that important。

 And I'm sure they made some decision somewhere。 I do not know why。

 It probably had to do with one of the computers they were working with。

 had truncating division in hardware and non truncating division in software。

 I don't know or rounding division or whatever。A lot of those computers didn't even have fast floating point。

 So some of the computers they were working on did all the floating point in software。

 and maybe they even did integer division in software with loops and stuff。 but we don't know。

 I don't exactly know， but they made this decision to do。Integer division truncating。



![](img/45ff0e5f73ec9b10f4264fdb0794f430_2.png)

And this was one of the biggest things of going from Python 2 to Python 3 that was the most painful。

So Python 2。like over 25 years old， and it wasn't that long after C that Python 2 was written。

 Python 2 was written in C。And。Python 2 to Python 3 transition was a big deal， it took a long time。

 it took 12 years to get there。But Python 2 was like the greatest thing ever except for a few things。

Because Python 2 was so related to C， the strings in Python 2 natively were ASI， not UniIcode。

 which meant it couldn't even do like Spanish characters， let alone Asian characters。

Pri was part of the language and the programmers got a lot of help。

 like they got automated code converter and syntax checkers and they did all kinds of things where they would take certain libraries like the print function and they would put it in Python 3。

 then we backport it to Python 2 so you could like switch from using the print statement to the print function and there were lots of things that made this transition as easy as possible the one thing that they really。



![](img/45ff0e5f73ec9b10f4264fdb0794f430_4.png)

Never could crack。 And we just had to bite the bullet and get used to it was Python 2 returns integer。



![](img/45ff0e5f73ec9b10f4264fdb0794f430_6.png)

And the division is truncated。 so if you do3 divided by4 is0 in Python 2。

 and in Python 3 is integer 3 divided by integer 4 becomes floating 。0。75 because。

That's what calculators do。And the Python 2 division truncated because it didn't seem like it mattered much back in the 80s and C integer division truncated。

🤧咳。So three quarters in C was zero and three quarters integer three quarters was zero in C。

 and so it was in Python and 20 plus years later， that was the one thing we couldn't autocont and Python3。

Does it the way Python does。It's less of a problem in C because C is actually a strongly typed language。

 which means if I wanted to say three over four I knew whether it was integers or floats and I could force that and so but in Python you just。



![](img/45ff0e5f73ec9b10f4264fdb0794f430_8.png)

What's the variable and so it imputees the variable type from the result of that expression？

🎼Where C has got to declare X as a float or a double or an int。

 so when a C programmer writes a division， they need to know they know already that they have to cast the values or use float constants to trigger type conversion and expressions so as you're looking through the chapter seeing these type conversions and casting that's the kind of problem that was solved but then Python simplified it and then made it really kind of kind of kind of yucky and then they had to fix it it's better in Python3 and most of you have just learned Python 3 so consider yourself lucky。



![](img/45ff0e5f73ec9b10f4264fdb0794f430_10.png)

![](img/45ff0e5f73ec9b10f4264fdb0794f430_11.png)

🎼Yeah。

![](img/45ff0e5f73ec9b10f4264fdb0794f430_13.png)

🎼Yeah。

![](img/45ff0e5f73ec9b10f4264fdb0794f430_15.png)