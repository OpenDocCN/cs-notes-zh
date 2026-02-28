# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p19 19_02_01_编程问题解决：七步法.zh_en -BV18U411U729_p19-

![](img/5e696d8aa1719fb8b5a0451919e8e340_0.png)

Today， you're going to learn how to solve programming problems using the seven step approach that we will use throughout the rest of this course。

 When you're solving a problem， youre going to start with a problem statement。

 You know that you want to end up with working code。

 but going straight from a problem statement to working code is a rather large leap。

 It can take some significant thought and work。😊。

![](img/5e696d8aa1719fb8b5a0451919e8e340_2.png)

![](img/5e696d8aa1719fb8b5a0451919e8e340_3.png)

This is why we break it down into seven steps for you。

 giving you a manageable approach where you know what to do next to solve the problem。



![](img/5e696d8aa1719fb8b5a0451919e8e340_5.png)

![](img/5e696d8aa1719fb8b5a0451919e8e340_6.png)

This is the seven set process that we recommend you use whenever you are solving programming problems that are difficult。



![](img/5e696d8aa1719fb8b5a0451919e8e340_8.png)

![](img/5e696d8aa1719fb8b5a0451919e8e340_9.png)

As your programming skills improve， many problems will become easy enough to just do them in your head。

 However， there will always be some problems that are harder and having a step by step approach will be helpful to you。



![](img/5e696d8aa1719fb8b5a0451919e8e340_11.png)

Let us look at each step in a bit more detail。The first step is to work an example of the problem yourself by hand。

This should be a small instance of the problem， something with about four or five pieces of data to manipulate。

 You don't want to try to process a million pieces of data yourself。 That would take forever。

If you have trouble doing the problem yourself， you cannot write a program to do it。

So what should you do if you get stuck here， Well， one of two things could be wrong。

Maybe the problem is just unclear。 The problem statement does not give you enough information about what you're supposed to do。

In a classroom setting you could consult your teacher or TA in a professional setting。

 you might work with your technical lead or customer to clarify the requirements。

 or you might just need to refine the problem statement yourself。



![](img/5e696d8aa1719fb8b5a0451919e8e340_13.png)

![](img/5e696d8aa1719fb8b5a0451919e8e340_14.png)

![](img/5e696d8aa1719fb8b5a0451919e8e340_15.png)

The other potential problem is that you lack domain knowledge。

 The knowledge of the field that the problem belongs to。

If you're trying to write a program to compute physical motion and you do not know the physics equations that you need。

 that would be a lack of domain knowledge。When you have this sort of problem。

 you need to find the relevant domain knowledge before you proceed。In step 2。

 you want to write down what you just did to solve this problem。 You want to be as exact as possible。

Do not leave anything out and write down how you solved it in a step by step fashion。



![](img/5e696d8aa1719fb8b5a0451919e8e340_17.png)

At this point in the process， you are just writing down the step by step approach for the one particular instance you solved。

 not the more general problem。

![](img/5e696d8aa1719fb8b5a0451919e8e340_19.png)

![](img/5e696d8aa1719fb8b5a0451919e8e340_20.png)

The tricky part in this step is that we often do things without thinking about them。

If you gloss over something or you're not precise about what you did。

 it will make the later steps harder。In step3， you want to move from the particular instance that you solved in step1 to an algorithm that works for any instance of the problem。

 that is you want to devise an algorithm which can solve the problem correctly for any input that you give it。



![](img/5e696d8aa1719fb8b5a0451919e8e340_22.png)

![](img/5e696d8aa1719fb8b5a0451919e8e340_23.png)

You'll do this by finding patterns in what you did and replacing specific behavior with more general behavior based on that pattern。

Some important tools for finding patterns which we will delve into more deeply soon are looking for repetitive behavior。

 finding behavior which you do sometimes but not always。

 and figuring out under what conditions you do it and figuring out how specific values you use relate to the parameters you picked。

So what should you do if you have trouble with a step， go back and try steps 1 and2 again。

 Use different inputs， which will give you another example to work from。

 You can see the steps for a different instance of the problem and have more information to help you find the patterns。



![](img/5e696d8aa1719fb8b5a0451919e8e340_25.png)

In step 4， you want to check your algorithm before you proceed to turn it into code。



![](img/5e696d8aa1719fb8b5a0451919e8e340_27.png)

If you found the patterns incorrectly or otherwise made a mistake in step 3。

 you would like to find that out now。The way you check your algorithm is to pick at least one different input。

 Again， it should be swollen。And follow the steps of your algorithm for it。

 If your algorithm gives you the right answer， then you are ready to move on。 If not。

 you should go back and fix it first。Now that you have devised an algorithm to solve the problem。

 you're ready to translate that algorithm into code。

This step is where the syntax of a specific programming language comes into play。

 You need to write down your steps in the syntax of that language。Once you've written your code。

 you want to be sure that it works correctly， so you run test cases on it。



![](img/5e696d8aa1719fb8b5a0451919e8e340_29.png)

Running a test case involves executing the code on a particular input and checking if it produced the right answer。



![](img/5e696d8aa1719fb8b5a0451919e8e340_31.png)

The more test cases your code passes。The more confident you could be that it is correct。 However。

 no amount of testing can guarantee that the code is right。



![](img/5e696d8aa1719fb8b5a0451919e8e340_33.png)

![](img/5e696d8aa1719fb8b5a0451919e8e340_34.png)

When your program fails a test case， you know something is wrong and when that happens。

 it's time to debug your program， you can watch a review video about debugging if you need more information。

 but at a high level you will apply this scientific method to understand what is wrong with your program and determine how to fix it。

Once you have identified the problem using this scientific method。

 you will need to revisit a previous step to fix it。 If the problem is in the algorithm you design。

 you will want to go back to step 3 and rethink your algorithm。 If your algorithm is correct。

 but you implemented it incorrectly in code， you will want to return to step 5 to fix your code。

Now you have learned the seven step approach to solving a programming problem。In the next video。

 we will work through an example of the process。 This process can guide you through programming problems you need to solve not only throughout the rest of this course。

 but whenever you need to solve a difficult problem。



![](img/5e696d8aa1719fb8b5a0451919e8e340_36.png)

![](img/5e696d8aa1719fb8b5a0451919e8e340_37.png)

Thank you。