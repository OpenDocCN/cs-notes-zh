# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p25 P25 01_将函数作为参数传递 -BV1QuJVzpEKE_p25-

![](img/d01c0fd7458fa0ee36885560026c4d37_0.png)

Like everything else in Python functions are objects。Because functions are objects。

 we can supply them as arguments in a function call。



![](img/d01c0fd7458fa0ee36885560026c4d37_2.png)

Here is a function called function runner。 It has one parameter。 F。 F's type is function。

Function runner calls F， and as you can see in the body， that's exactly what it does。



![](img/d01c0fd7458fa0ee36885560026c4d37_4.png)

Here we define a function that we're going to pass the function runner in just a little bit。

Because this is just a demonstration， all we'll do inside here is print that the function was called。

Let's add one more function just like this one。Here we call function runner supplying function 1 as the argument。

Now will trace execution of this program。When the program starts running。

 we get a frame for the module。Every function definition creates a variable with the name of the function that contains the memory address of a function object that contains all the details of what it means to run that function when it's called。



![](img/d01c0fd7458fa0ee36885560026c4d37_6.png)

Thing happens when we define function one。Send function 2。

Then we reach the name equals mainiff statement， and inside that is a call and function runner。

To execute the function call， we evaluate the argument。

 That's just the memory address of the function object。

 then Python creates a frame for the function Perameter F is inside that frame。

 It is assigned to the memory address of the function that was passed as an argument。



![](img/d01c0fd7458fa0ee36885560026c4d37_8.png)

To execute function runner。We just execute the statement in its body， which is a call on function F。

We draw a frame for that function。We're going to write F slash function 1 here。

 although it turns out that the name of the function is taken from the function definition。

In the body of function 1， we have a call on function print。That's the end of function 1。

 So we exit it。 That brings us back to function run。 We just completed the call on function F。

 That's the end of function run。 So we exit it。 That brings us back to the main program。

 We're at the end of it。 So we exit the program。When we traced this。

 we reached one call one function print。 When we run it， we get the output that we expect。

When we change function 1 to function 2， we see that we end up at this call on function print。



![](img/d01c0fd7458fa0ee36885560026c4d37_10.png)