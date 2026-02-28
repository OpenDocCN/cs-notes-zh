# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P35：1_模块1 1 2 函数参数和返回值.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

![](img/620237aee587107ecabdef9df6d068aa_0.png)

Module1 functions an organization， topic 1。2 function parameters and return values。

So the examples that we showed the function examples that we showed for were really simple。

 but generally functions often need some sort of input data to operate on right so functions of sequences of instructions or sets of instructions。

 but they need some data to work on So it is very common for a function to have a set of what are called parameters which are a set of variables that are listed right after the function name and the declaration in the parentheses and these are variables that they'll become local variables that are used as inputs to the function。

 so the function actually operates on these variables internally Now an argument is the data that's applied for those parameters during the call so to give you an example。

We got this function up here called P and in parentheses after the word fo after the name。

 you see x and comm a y nt。 so in parenthees is a list of the parameters。

 so that means there are two parameters， x and y and they're both integers。

So it expects somebody when the function gets called。

 it expects the caller to pass two integers as arguments。And what it'll do is just print the product。

 right， Pri x con times y。 Now， then if we look in the main。

 the main actually calls P and it calls P and in parenthees， it says two comma 3 has two comma 3。

 So2 is going to be passed as x。 What3 is going to be bound to y。

Inside the function fo when it executes。 So when Fo executes2 will be x，3 will be y。

 and it'll print  two times 3， should print out6 when you run a program like this。

 So having parameters is a very common thing for a function because functions often need some kind of input data to operate on。

 So there are different ways you can pass parameters， just to give a couple examples。

 maybe you don't need parameters。 sometimes a function does not need parameters。

 Maybe it just does something static and doesn't need input， or it gets input from some of the place。

 maybe it gets input from the user typing an input directly， or maybe it gets it from a file。

 something like that。 So sometimes you don't need arguments。So if that's the case。

 then you still have to put the open print close print in the declaration after the name， so funk Fu。

 open print and close print， you still need that there。

 you just don't put anything in the parentheses and then the compiler knows that there are no parameters。

Also another sort of shorthand is when you have multiple arguments of the same type。

 you can list them， you can comma separate them， you don't have to write int int int over and over say。

 so in the case below where you got F， it has two arguments x and y and they're both ints。

 you could write x int comma y int or just write x comma y int it's just another way to write it。Now。

 in addition to having parameters which are inputs to the function， a function can have an output。



![](img/620237aee587107ecabdef9df6d068aa_2.png)

One or more outputs， return values。 So each return value has to have a type。 Okay。

 so the type of the return value has to be listed in the function declaration on the top right after the the arguments after the parameters are listed。

 So， you know， maybe you know you return to integer or you know your return a flow or something like that。

And the function call， once you define a function that has a return value。

 then the call to that function can be used on the right hand side of a signal signal a variable assignment sorry so just to give an it's easier if I just show you。

 so to give you an example， we got this function fo。

 it takes an argument x so you see x int in parenthees after the name fo。Then after that。

 you see the word int right before the open open curly brackets and closed curly bracket。

 you see int， that means that the return value， its type is going to be an integer。

And then inside the function inside the curly bracket， you see it says return x plus 1。

 So if this function has a return value like it does in this case。

 then you have to call return in the function at the end of the function。

 And whatever is after the word return is what's going to get returned。 So x。

 whatever the value of x is plus1， that's what's going to get returned by this function。

 So this function just a returns an incremented version of the variable。Now then down below。

 you see that assignment， y equal colon equal F1。Now。

 this is taken out of context that y colon equal P 1 would have to be in a function of its own。

 So mape let's assume that that statement is inside a main， right。

 I don't want to draw the home main， but let's assume it's in a main。

 So that's a function calls calling the fo function。 It's passing as the argument the number one。

 So one is going to get bound to x inside the function F when it gets executed。

So the function fo that called the F will return x plus one。 So it will return2。

 So that open pro one close pro。 that will be replaced in that that assignment statement with the value 2。

 So itll get evaluated， it will be replaced with a two。

 and then y will be assigned to the number two to the integer 2。 So in this way。

 this what happens whenever you have a return value， you've got to do an assignment， right。

 Y colon equals1。 if I didn't say I just called 1， right。

 then it would execute the function but the return value would would go nowhere。

 I have to have a signal assignment a variable assignment So that the return value or values get captured。

The last example I showed the function took one or had one return value。

 but you can have multiple return value。 So in this example， food 2， we've got two return values。

So if we look at the declaration， Fk Fu2 X int， that's in parentheses， so that's the argument。

 then after that you have parentheses again， another set of parentheses， ant comma ant。

 and that means that you have two return values。And they're both integers。

And then after that you have the code， the code just return x comma x plus1。

 so those two return values the first one will be x。

 the second one will be x plus1 so they're listed after return comma separated and then when when say in a function main and something like that when I call food2 see that a comma B colon equal food23 So what will happen is that a comma B a comma A and B will be assigned to the two return values of food2 So so a is going to be assigned like in this case F2 is going to return x and x comma x plus1 so that'll be3 and4 So a would be bound to3 B would be bound to four。

Thank you。