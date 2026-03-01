# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p47 17_03_09_代码审查.zh_en -BV1Kp42117vh_p47-

![](img/16e3ab0b1e791ae7a22a0847e66f0e0d_0.png)

Testing is great。 You're going to test your code like crazy and write lots of hard test cases so you can identify problems with your code。

But testing has its limitations。 For one thing， you can never write enough test cases to guarantee that your code is correct。

 even if you write a million test cases， which are all really clever and difficult。

 there might be that million in first test case that your code would fail。Also。

 testing will only tell you if your code has the right functional behavior if it produces the right output。

 it won't tell you if you wrote readable code， use good variable names。

 wrote appropriate documentation， or a variety of other stylistic concerns。

 these may not sound so important now as you focus on trying to get your code to work。

 but when you are working on large projects with many team members that last for months or years。

 these concerns become very important。So another way that you can help ensure high code quality is a code review。

Sit down with a colleague in a work environment。 This would be someone on your team。

Go through your code with them line by line。 Ex what each line does and why it does that。

 You might even draw a diagram of the execution of your code as you go to make sure you are both on exactly the same page about what is happening in your code。

 As you do this， your colleague asks you questions and identifies potential problems。

 They might point out cases that they think you didn't consider。 if you think you did consider them。

 you can have a discussion about how your code handles that case and how you can make that clearer to future readers of the code。

 they might also point out areas where your code could use better documentation or any of the other readability concerns they see。

 And of course， they might see other potential problems ranging from security vulnerabilities to poorly phrased messages printed to the user。

A code review can take a variety of forms， not just the one we talked about。

 It may be that the case that your colleague reviews your code without you there to explain it。

 In fact， in many companies， someone must peer review your code before it gets pushed to certain branches like master of the Git repository。

 This ensures that certain quality guidelines are met with all code that is integrated into the main branch of development。



![](img/16e3ab0b1e791ae7a22a0847e66f0e0d_2.png)

The review could even happen while the code is being written as happens in pair programming。

In pair programming， one partner drives meaning they write the code。

 while the other partner navigates， meaning they watch what the driver is doing。

 look for problems and think about the bigger picture of where the code is going。

We aren't going to go deeply into these topics， but we did want to mention them to you if you go on to take more classes on software engineering。

 you will almost certainly learn much more about code reviews。

