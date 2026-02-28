# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p16 16_02_03_方法.zh_en -BV18U411U729_p16-

![](img/970eb8924852c21f3fc98b73205046fe_0.png)

In the previous video， we executed the declaration and initialization of points P1 in P2。

 And you learned about new and constructors。 Now， it is time for you to learn about method calls。

 Method calls work a lot like function calls， except that we have to pass the this parameter to let the method know which object it is working on。

 Let us resume where we left off。😊，This line is going to call P1 do distance P2 and then print its return value。

 We need to set up a frame for distance， which will take two parameters。 The implicit this parameter。

 which tells it which object it is acting on and the other point parameter。

 which is explicitly passed to it。this parameter has the same value as the variable before the dot。

In this case， we have P1 dot distance， so this has the same value as P1。

It is an arrow pointing at the same point object。 We have colored this arrow differently。

 but that does not have special meaning。 It is just to help you keep straight which arrow is which in this diagram。

For the other point parameter， we just copy the value that is passed in， in this case， P2。

So the value of other point is an arrow pointing at the same point object as P2。

Now we go into the distance method and begin executing code there。Executing the first line。

 we are declaring a variable D X and need to initialize it to x minus other point dot git x to evaluate that expression。

 we need to call other point dot git X。 So we need to set up a frame for that method call。 again。

 this method takes an implicit this parameter to tell it which object to do git x on Which object should this point at。

Well， we did other point do git x so we copy the value of other point。

 which is an arrow pointing at that point object。 Now we go inside of Git X and begin executing code there。

Here we have returnturn x， so we need to evaluate the expression x and return its value。

How do we get the value of x？We follow the this pointer to find the object we are working on and then look for the X field inside of that object。

 The value of that field is 6， so that is the value of the expression X here。

 which is what will return to the collar at call site 2。Returning to call site number two。

 we want to evaluate x minus6。How do we evaluate x here， We again look at the this pointer。

 which refers to this point object。And we get the x field inside of that point object。

 That value is 3， which is the value of x in this expression。

 so we will compute 3 minus6 and initialize dx to minus3。Now。

 we are going to declare and initialize Dy using a very similar process。 First， we make a box for Dy。

Then we call get y on other point， notice how this is a copy of the value of other point。

 an arrow pointing at our second point object。We get the value of the y field out of this object。

 which is8， and return it to call site 2， where we return the execution arrow to。

We evaluate Y by looking in this object and finding its y field， which is4。

Now we are ready to finish the initialization of dy to 4 minus8， which is negative 4。

 Our next line has a little bit of math。 Let's look at it in detail。

We are calling math dot square root of Dx squared plus dy squared。 First。

 we can compute the value of the parameter， which is 9 plus 16， which is 25。

 so we need to evaluate math dot square root of 25。 This looks like a method call。

 but where did the math object come from。It turns out that math is a class。

 not an object and is part of the Java library。 This is a static method call。

 The method is being called on the class in general， not on any particular object here。

 the math class is just a handy place to put a bunch of mathematical functions together since we don't have the code for math that square root。

 we have to know what effect it has。If we did not know。

 we would look it up in the Java documentation。 however， as you might have guessed。

 this method just computes the square root of its argument。

 so math that square root of 25 will return 5。0。Our distance function returns that value to its collar。

 so the value of the call to distance in main will be 5。0。

 We then return execution domain where we are ready to complete the print statement。

 which will print out 5。0。Now we are done with Maine so we will return from it。

 destroying its frame and exiting our program。

![](img/970eb8924852c21f3fc98b73205046fe_2.png)

![](img/970eb8924852c21f3fc98b73205046fe_3.png)