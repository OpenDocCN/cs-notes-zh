# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p43 13_02_01_构建工具Make.zh_en -BV1Kp42117vh_p43-

![](img/14bb5189a544b6da0c55d2747933e1da_0.png)

Now you have the basics of compiling using GCC， Of course you want to give it some flags so that it will work hard to identify potential problems in your code。

But what if you have a really large program， like one with hundreds of source files and many of thousands of lines of code。

You could just tell Gcc that you want to compile star。c， all the C files in the current directory。

 but that would mean you recompile every file， even if you just make one small change somewhere。

 that would take a lot of time and really harm your productivity， speaking of which XKCD。

 which is one of my favorite web comics， has a great comic about time wasted compiling。

You could instead try to manually pick out which files to recompile。

 This would be tedious and error prone。 if you miss one。

 you'll end up with strange errors in your program。

So what should you do you should use a tool for building large programs such as make。

 which is great not only for building large programs， but for building pretty much anything。

 For example， all of programming， my textbook， which this course is based on was built with make。

The input to make is a make file， which specifies the targets of your build that is what things should make build for you。

It also specifies the dependencies， which you can think of as the inputs to build a target。

 If one of the dependencies changes， then the target needs to be rebuilt。

 One target might be a dependency of another target， in which case。

 rebuilding the first means that you have to rebuild the second。

 The make file also specifies the recipes to build a target from the files that it depends on。

 These are the commands to run to make the target from the files it depends on。

To understand dependencies a little better， let's suppose you want to build my program to build my program。

 you link three object files shown here。 This means that my program depends on these three files。

 If any of them get recompild， we need to relink my program。If ABC。0 is compiled from ABC。c。

 then there a dependson relationship between these two files too Likewise if ABC。C includes ABC。h。

 then whenever we change the header file， we would want to recompile the ABC。0 object file。Likewise。

 xYz。0 might depend on a C file and some header files。

 we may end up including one header file in many C files as we develop a large project。And finally。

 main do0 depends on main do C and one of our header files。 Now， if we change X Yz do C。

 we need to recompile Xyz。 O， since X， Yz。 O depends on Xyz do C。

 We don't need to recompile any of our other object files。 We do， however。

 need to relink our program since my program depends on X， Yz do O。If we change the xyz。

hge header file， we would need to recompile two object files and then relink the program。Fortunately。

 once we tell make about these dependencies。And what commands are needed to build a target。

 It will figure out which targets need to be rebuilt and run the corresponding commands for us。



![](img/14bb5189a544b6da0c55d2747933e1da_2.png)