# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p08 P8 01_使用-doctest-进行自动化测试 -BV1QuJVzpEKE_p8-

![](img/a37c1b81fa14384784903ec50252c7b9_0.png)

As part of the function design recipe， we include one or two example calls on the function in its dostr。

The last step of the function design recipe is executing those function calls。Up to now。

 we've been executing the function calls by copying and pastcing them to the Python shell and then comparing the value returned with the value that we expect。

In this lecture， you'll learn about Do Test， a Python module that allows us to run these tests in a more automated way。



![](img/a37c1b81fa14384784903ec50252c7b9_2.png)

On the right hand side of the screen， there's a module named vowels do Pi that contains two function definitions。

 collect vowels and count vowels。

![](img/a37c1b81fa14384784903ec50252c7b9_4.png)

Each of those functions has two example calls on it in its dock string。



![](img/a37c1b81fa14384784903ec50252c7b9_6.png)

To execute the example calls， we need to run the module and then copy and paste each function call to the Python shelf。

Once the function calls x unit， we compare the value returned with the value that we expected to make sure that they match。

Let's do this for the other three as well。Rather than calling each example one at a time。

 it would be nice to be able to run them all at once。

 and Python has a module named Docs that allows us to do just that。We begin by importing doc test。

 and then we call doc test function test mod。To run all of the tests for this module。



![](img/a37c1b81fa14384784903ec50252c7b9_8.png)

What we see here are the test results。 Four tests have been executed， and in this case。

 all of the tests have passed。

![](img/a37c1b81fa14384784903ec50252c7b9_10.png)

A nice feature of doc test is that it does the comparison of the value returned by the function call with a value that we expect automatically。

 This makes the testing much less prone to human error since we aren't doing the comparison of those two values ourselves。

Let's consider another example。

![](img/a37c1b81fa14384784903ec50252c7b9_12.png)

On the right hand side of the screen， there's now a module named divisors。

 which contains one function named to get divisors。 Get divisors has two parameters。

 a number and a list of possible divisors of that number。



![](img/a37c1b81fa14384784903ec50252c7b9_14.png)

The function returns all of the items from the list that the number can be divided evenly by。



![](img/a37c1b81fa14384784903ec50252c7b9_16.png)

For example， for the number 8 and a list of possible divisors，1，2， and 3。

 the function call would return a list of divisors，1 and 2。



![](img/a37c1b81fa14384784903ec50252c7b9_18.png)

Eight cannot be divided evenly by3， so three is not included in the list returned by the function call。

This function has another example in its do string as well。

 let's run both of these example calls by running the module and then running Doc test。

The message that we get back from do test this time is much longer than it was for the vowels example。



![](img/a37c1b81fa14384784903ec50252c7b9_20.png)

For the vowels example， all four test cases passed。In this case。

 the two example test cases were executed， and one of them failed。



![](img/a37c1b81fa14384784903ec50252c7b9_22.png)

A test that fails is one for which the actual value returned by the function call doesn't match the value expected。



![](img/a37c1b81fa14384784903ec50252c7b9_24.png)

In this case， it was the second example call that failed。



![](img/a37c1b81fa14384784903ec50252c7b9_26.png)

Forget divisors with the number four and possible divisors negative 2，0 and2。

 an error occurred when executing the function call。

The error was a0 division error somewhere in our function， we divided by 0。

 Let's look more closely at the code to see where this would have happened。



![](img/a37c1b81fa14384784903ec50252c7b9_28.png)

We can see from the error message that the zero division happened on line 15。

 which is this if statement header。

![](img/a37c1b81fa14384784903ec50252c7b9_30.png)

![](img/a37c1b81fa14384784903ec50252c7b9_31.png)

This bullolean expression takes the number and divides it by the possible divisor to see if it divides evenly。

At this point， we can look at our example。There's a zero in the list of possible divisors。

 so that means that on line 15， we're dividing the number by zero。Now that we found the problem。

 it's time to fix it。We need to ensure that number is only divided by non zero numbers。To do this。

 we'll add an additional Boolean expression to our if statement as long as the item is not equal to0。

And the number divides evenly by that item。 Will it be added to the list of divisors that's returned at the end of the function call。

Recall that Python evaluates the and operation using lazy evaluation。That is。

 if the first operaand is false。The and expression is false。

 and Python does not go on to evaluate the second operaran to the end。In other words。

 when item is equal to zero。The expression on the right hand side of the and won't be executed。

 so none won't be divided by zero。It's now time to rerun the tests。

We'll rerun the module so we get the latest definition of this function。

And then run test mod from Doc Test module。

![](img/a37c1b81fa14384784903ec50252c7b9_33.png)

Although we no longer get the zero division error， the test case still fails。



![](img/a37c1b81fa14384784903ec50252c7b9_35.png)

We expected to get a list with integer 2。And instead， we got a two item list with negative 2 and 2。

This time， there isn't a problem with the function definition。 There's a problem with the test case。



![](img/a37c1b81fa14384784903ec50252c7b9_37.png)

Negative 2 is the divisor of 4， and it should have been included in the list。 We'll add it now。



![](img/a37c1b81fa14384784903ec50252c7b9_39.png)

Next， we need to rerun the module and retest it。This time， both of the test cases pass。

Instead of importing doc test and running test mod in the shell。

 we can do it from within the divisor's module。Now， each time that the divisor's module is run。

 the test cases are also executed。If the test case is passed， there's no output in the shell。

 no news is good news。

![](img/a37c1b81fa14384784903ec50252c7b9_41.png)