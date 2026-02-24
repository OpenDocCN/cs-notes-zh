# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P37：36_纯函数.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

A good coder will try to keep code clean， make it easier to debug and ensure it's extendable The great thing is that pure functions can help you do all that。

😊，In this video， you'll learn what pure functions are and how you can use them in functional programming。

😊，It's important to understand that there is a clear difference between traditional and pure functions。

A pure function is a function that does not change or have any effect on a variable data， list。

 or sets beyond its own scope。😡，For example， if you have a list of the global scope。

 a pure function cannot add something to that list or alter it in any way。😊。

Let's explore an example function and then determine if it is a pure function or not。😊。

This code includes a list on the global scale and a function called add to a single parameter called It。

The value of item is then set to4。😊，The output is one， two， three， four。

 What do you think is this a pure function？No。It's not a pure function as it changes the global list by appending the item which is passed as an argument。

In order to change it to a pure function， you need to think how to extend the function to accept a list as an argument。

Add the item to the list without modifying the original list。

And how to return a new list with a newly added item。

 the solution is to create a new list and copy or clone the data from the original list。

Let's revisit the code to make some changes。This time you make a copy of the original list。

The new item is added to the new list。Then the new list is returned to the caller。

Now that you have a better idea of what a pure function is。

 let's review a few benefits of pure functions。😊，Firstly， with pure functions。

 you always know what the outcome will be。Pure functions are consistent snippets of code that do exactly what they are intended to do。

Thirdly， pure functions include the ability to cache since you know the return is always going to be the same。

Lastly， pure functions lend themselves well to a multi threaded program。In multi threaded programs。

 more than one process could run concurrently， which creates many threads of data。

Pure functions will help prevent changes on the global scope， ensuring data stays reliable。

Now I think it's time to offer you a step by step demonstration in VS code of how to alter a normal function to a pure function。



![](img/05b97bf1678e8d9c02abd0f53d33cf09_1.png)

Pure functions are especially useful because they are easier to read。

 better to debug and more consistent。I'll now take you through a simple example to demonstrate how to create a pure function。

I'll start by creating a function that does not behave like a pure function。

 and then I'll tweak it until it's a pure function。😊。

First I create a list called My list and inside it I add three numbers， one， two and three。

Then I add a simple function called add to list， which takes a single variable called item this function will return my list and append the new item that is being passed through。

Below that， I call the function add to list and assign the value of4 to the variable item。😊，Finally。

 I add a print statement of my list so that I can focus on the output in the console。

I click on the run button and the numbers one， two， three， and four are printed out。

This means that my list now contains the inserted number four as well because the function appended it to the existing list。

What do you think？Is this a pure function， no， it's not。

 because the data has been manipulated at the global scope from inside the scope of the function。

Let's try to turn it into a pure function。The first thing I'm going to change is how the function is being called I want to pass in a new argument。

😡，I type new list equals add to list， I keep the value of4。

 and I'll also print out the new list below the first print statement to compare the output。

Now let's make some modifications to the function itself。I add a simple append to my list。

 which is going to take in the item variable。😡，I type my list dot append and item in parentheses。

Then I want to return back the list。😡，I type return my list。

Now I click on run and the output in the console indicates that both my list and new list include the values of one to four。

It's clear that the function is still not a pure function， why。

 because even though it's returning a new variable， it still has a reference to the My list variable。

😊，Let's try something else to turn it into a pure function。

This time I'll accept a parameter called LST for the variable item。

 I type LST comma in front of item in the parentheses。I also change the append statement to LST。

 append item and I also changed the return action to return LST Finally。

 I change the call action by passing in my list comma inside the parentheses before the value of four。

Let's run that。And once again， both lists contain the values of one to four。

The reason for this is that the function is still using the list as an argument and it's still being updated from within the function。

😊，So ultimately， in order to create a pure function。

 the problem that I have to solve is how to create a new list。

 and then I need to solve how to get all the values from the list that's being passed through and then return the new list back to the call action。

Let's give it another try。This time I create a new list by creating a copy。In the function。

 I typed the name of the new list NL equals LsT。copy and a set of parentheses。Now。

 instead of putting the past valuesd into the LST， I'll put it into the copy。😊。

So I type Nl dot append， and then I also change the return action to return NL。

I clear the console screen so that I can focus on the output and click on run。And finally。

 I get two different results。 My list is printed with the values one， two and3。

But the second print statement for new list includes the values of one to4。

This function is now a pure function because it adds a value to a list。

 but it doesn't manipulate the original list outside the function。😊，In this demonstration。

 you've learned what a pure function is and what you need to do to change a function that's affecting a list on the global scope to a pure function that does not interfere with the original list。



![](img/05b97bf1678e8d9c02abd0f53d33cf09_3.png)

It's likely that you'll use pure functions regularly in your're programming career because pure functions will keep your code cleaner。

 easier to debug， and easier to extend。