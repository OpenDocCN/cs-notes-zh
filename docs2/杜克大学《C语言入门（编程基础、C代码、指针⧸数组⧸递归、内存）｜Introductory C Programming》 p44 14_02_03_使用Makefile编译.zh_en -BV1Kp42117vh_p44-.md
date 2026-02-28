# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p44 14_02_03_使用Makefile编译.zh_en -BV1Kp42117vh_p44-

![](img/39c54fe37c04837cc996b54a00d5e004_0.png)

Okay， you've been compiling programs， we've been talking about make and how it's useful for building larger programs and tracking your dependencies and changes and so forth。

 and I'm going to show you a little bit of compiling with a make file and so forth。

So at the moment I have here。A handful of files and a handful of header files， a handful of C files。

 a handful of header files， and a make file。This isn't a super big project。

 but we want a small example。 So right now， if I type make。We'll dove into the makefin in a second。

 It's going to compile all of these things and create my program。

 which doesn't really do anything super interesting。 Just compute math。

Now if I were to open up file 1。c。And make a change in here。

 let's say that I realize that this really should be plus one from some testing and debugging that I've been doing or something like that。

And then I go to compile again and I do make， you'll notice that this time it only recompiled file 1。

c to an object file and then relinked to the program。

 This is really nice because it didn't recompile all these things these are all pretty small files so they compiled quickly。

 but in a real big project it might take a while。Okay， and in fact。

 now that we're dealing with things in Es。We may as well not even go back to the command line。

 we can just compile on E so if I hit C C control V。

 you'll see at the bottom it says compile command and it says makeK so when I hit enter it actually runs make dashK just says keep going if you run into errors try and make as many things as you can so you can see as many errors at once。

 you don't have to use it it's a default。It finished with no problems。

 if I were to have a syntax error， let's say leave off that semicolon。And I compile。

 it's going to display my errors in EmX。And in fact。

 let's make it so that we have a couple errors in here。Now。Now if I go to these errors， it will。

Jump to wherever in the code。That error is coming from。 So this is on that line。

 This error message is coming from the makegphius is telling me it failed to make that thing。

 This is on that line of code。 So this works really nicely。 We can just stay in emax。

 move around and see our errors。In your readings you'll learn about the details of how to make the make file。

 starting with a very simple make file and building up to sort of a nice feature full make file that's flexible and lets you add more and more files。

 but this is how we can use those in this environment we just create a file called make file with whatever we need in there and then we go from there。



![](img/39c54fe37c04837cc996b54a00d5e004_2.png)