# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p76 01_01_01_为什么我们需要交互性和内存管理.zh_en -BV1Kp42117vh_p76-

![](img/2015da2c37eb6d6da9cce72633db2eab_0.png)

Welcome to Cose 4， your C programming skills are developing nicely。

 and it is time to finish out the specialization with a few more very important topics。

 The first thing we're going to talk about is interacting with the system and the user。

 you've printed output to the screen， but what if you want to read input from the user。

 What if you want to store data in a file instead of printing it to the screen。

 or read data in from a file。 How do programs that take command line arguments use them。😊。

We'll cover all of these topics as well as some background on the relationship between your program and the operating system。

 which is involved in these tasks。The second major topic in this course is dynamically allocating memory。

 What does this mean， It means allocating space to store data when your program runs。

 because you do not know how much space you need when you write it。If your program will read a file。

 you don't know how much data will be in that file， it might be 50 lines， or it might be 50 million。

 even if you made a 50 million element array to hold the data。

 you might find that your program needs to handle 500 million elements。Finally。

 we'll wrap up with a discussion of some important concepts to keep in mind as you move to writing larger programs。

 What you've written in this course is pretty small。

 Some programs have thousands or even millions of lines of code in them。

 We aren't going to work on anything that large。 but we'll talk about important principles and work through a moderately larger example。

 So let's dive right in。😊。

![](img/2015da2c37eb6d6da9cce72633db2eab_2.png)