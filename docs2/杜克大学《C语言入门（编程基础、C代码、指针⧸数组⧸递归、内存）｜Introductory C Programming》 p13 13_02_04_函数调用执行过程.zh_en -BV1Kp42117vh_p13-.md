# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p13 13_02_04_函数调用执行过程.zh_en -BV1Kp42117vh_p13-

![](img/7b636685a5ef4443ac0aa380eddea558_0.png)

Okay， now that you have the basic ideas of function called semantics， let us see them in action。

 We have three functions here。 My function， F and mean。As you have learned。

 we start execution of a program inside of main。 We've drawn a frame for main and are ready to begin executing its first statement。

 which declares the variable A。 so we create its box inside of the frame for main。Next。

 we're going to set a equal to the value of the function call， my function of 37。

 to evaluate this expression， we need to create a frame for the function that we are calling。

In this case， my function， this will hold the parameters and variables of my function。Next。

 we pass the parameters to my function， we create a box for each parameter。

With the names coming from the Funition Dec， X and Y。

 we initialize these by copying in the values of the expressions that were passed here，3 and 7。Next。

 we need to note where to return when we finish executing my function。

 This location in the code is named the call site。 The place where the function was called We'll note it with marker 1 in the code and put the same marker in the corner of the frame。

Finally， we move the execution arrow into my function and start executing code there。

Here we declare and initialize Z， evaluating the expression2 times x minus y。

 The values for x and y come from the frame for my function，3 and 7 respectively。

 so z will be negative 1。Now we have reached a return statement。

 Re statements tell us to leave the current function， returning to the call site noted in the frame。

 they also tell us the value to return to the caller。

The first thing we need to do is evaluate this expression to obtain the return value。

Here the expression is z times x， so we evaluate negative 1 times 3 and get negative 3。Next。

 find where we should return。 This is the call site we noted in the frame。

Then we copy the return value back to the call site。

 the function call evaluates to this return value。We move the execution arrow back to the call site and destroy the frame for the function we just returned from。

Now， we are back in Maine。 the call to my function evaluated to negative 3。

 So this line behaves like a gets negative 3。 When you finish that assignment。

 putting negative 3 in A's box。Our next line， again has a variable declaration and a function call。

 We make a box for B and go through the same process to call F。We make a frame for F。

 and pass parameters。This time， there is one parameter in whose value is a times a， which is 9。

 We note where to return and begin executing code inside of F。

 Our next statement is a return statement。 but the expression involves a function call。

 So we have to evaluate that call before anything else。 We start with a frame and pass parameters。

X gets the value of n， which is 9， and y gets the value of n plus 1， which is 10。

We note the call site we'll use two this time since we are already using one somewhere else and move the execution arrow to the start of my function and start executing code there。

We declare Z and initialize it to 8。 Now we are ready to return from my function。

 We evaluate z times x， which is 72。 Then we find the call site noted in the frame and copy the return value there。

Finally， we move the execution arrow back to the call site， destroying the frame for my function。

Now we pick up where we left off an F using 72 for the value of the call to my function。

We evaluate 3 plus 72 to get 75 since we are evaluating the return statement。

 this is the return value of F， so we find the call site and copy the return value there。

Then we return to that call site， destroying the frame for F。

 Now we can finish the initialization of B。 B gets 75。Lastly。

 we reached the return statement from Maine。When we return from Maine， the program exits。

 so we are done。

![](img/7b636685a5ef4443ac0aa380eddea558_2.png)