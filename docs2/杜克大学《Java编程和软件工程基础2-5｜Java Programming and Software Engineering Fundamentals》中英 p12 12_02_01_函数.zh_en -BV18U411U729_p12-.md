# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p12 12_02_01_函数.zh_en -BV18U411U729_p12-

![](img/d7c8c980106c0a68962a94171ef9b7a3_0.png)

The next important idea to understand its function calls functions abstract a computation out。

 giving it a name and parameters。 You then can use the function to perform that computation without rewriting it。

 You can also think about what the function does。 and not how it does it。 technically speaking。

 Java doesn't have functions。 It has methods。 Since all code and Java is inside of objects。 However。

 before we learn the more complex behavior of objects and methods。

 We'll learn the basic principles of function calls。

 These concepts will then lay the foundation for understanding method calls。

 We have three functions here。 My function F and G。 Why are we starting at G。

 We'll assume for now that you chose to call G from the blue J interface。 Later。

 you'll learn about the main method， which is where programs start when you run them outside of blue J。

😊。

![](img/d7c8c980106c0a68962a94171ef9b7a3_2.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_3.png)

We start with a frame for G and with the execution right at the start of that function。

 The first line declares a。 So we create its box inside of the frame for G。 Next。

 we're going to set a equal to the value of the function call my function of 3。

7 to evaluate this expression。 we need to create a frame of the function that we're calling。

 In this case， my function。 This will hold the parameters and variables of my function。 Next。

 we pass the parameters to my function。 We create a box for each parameter with the names coming from the function declaration。

 X and Y。😊。

![](img/d7c8c980106c0a68962a94171ef9b7a3_5.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_6.png)

We initialize these by copying in the values of the expressions that were passed here。

 three and seven。Next， we need to note where to return when we finish executing my function。

 This location in the code is named the call site。 The place where the function was called will'll note it with the marker1 in the code and put the same marker in the corner of the frame。

 Finally， we move the execution arrow into my function and start executing code there。😊。

Here we declare and initialized Z， evaluating the expression two times x minus y。

 The values for x and y come from the frame for my functions 3 and 7， respectively。

 So z will be negative 1。 Now we have reached a return statement。

 Re statements tell us to leave the current function。 Re to the call site noted in the frame。

 They also tell us the value to return to the call。

 The first thing we need to do is evaluate this expression to obtain the return value。 Here。

 the expression is z times x。 So we evaluate negative1 times 3， and we get negative 3。 Next。

 find where we should return。 This is the call site we noted in the frame。

 Then we copy the return value back to the call site。

 The function call evaluates to this return value。 We move the execution arrow back to the call site and destroy the frame for the function we just returned from。

😊。

![](img/d7c8c980106c0a68962a94171ef9b7a3_8.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_9.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_10.png)

Now we're back in G。 The call to my function evaluated 2 negative 3。

 So this line behaves like a gets-3。 We'll finish that assignment， putting-3 in its box。

 Our next line again has a variable declaration and a function call。

 We make a box for B and go through the same process to call F。

 We make a frame for F and pass parameters。 This time there's one parameter n。

 whose value is a times a， which is9。 We note where to return and begin executing code inside of F。

 Our next statement is a return statement。 But the expression involves a function call。

 So we have to evaluate that call before anything else。 We start with a frame and pass parameters。

 x gets a value of n， which is 9。 and y gets a value of n plus1 which is 10 We note the call site will use2 this time。

 since we are already using one somewhere else。 and move the execution error to the start of my function and start executing code there。

😊。

![](img/d7c8c980106c0a68962a94171ef9b7a3_12.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_13.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_14.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_15.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_16.png)

We declare z and initialize it to a。 Now we are ready to return from my function。

 We evaluate z times x， which is 72。 Then we find the call site noted in the frame and copy the return value there。

 Finally， we move our execution arrow back to the call site， destroying the frame from my function。😊。



![](img/d7c8c980106c0a68962a94171ef9b7a3_18.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_19.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_20.png)

Now we pick up where we left off an F using 72 for the value of the call to my function。

 We evaluate 3 plus 72 to get 75。 since we are evaluating the return statement。

 This is the return value of F。 So we find the call site and copy the return value there。

 Then we return to that call site destroying the frame for F。

 Now we can finish the initialization of B。 B get 75。 Lastly， we reach the return statement for G。

 which is where we started。 When we return from the function where we started。 We are done。😊。



![](img/d7c8c980106c0a68962a94171ef9b7a3_22.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_23.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_24.png)

![](img/d7c8c980106c0a68962a94171ef9b7a3_25.png)