# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p18 18_02_05_for-each循环.zh_en -BV18U411U729_p18-

![](img/ea4de499b0a80a9c0263bab58d9191fb_0.png)

Hi， now we're going learn how if for each loop works。

 This piece of code looks similar to the hello around the world example that you started with earlier to make this work。

 we need to add an import statement to the top to tell Java where to find the file resource class。

 F resource is in a package that we provide to you to let you manipulate data and files before you learn the more advanced techniques and concepts that would let you do this in Java directly without the classes we've created。

 According， this is found in the Eduu do Duke package。 If you want to run this code in blueja。

 you could do so by creating a hello world object and then invoking its run hellello method we could also add a main method。

 which does the same thing if we want to be able to run the code directly but outside of Bluej in another environment。

😊。

![](img/ea4de499b0a80a9c0263bab58d9191fb_2.png)

![](img/ea4de499b0a80a9c0263bab58d9191fb_3.png)

Let's start executing the code by hand。 We start in Maine with a frame that contains args。

 We're not going to use this arg's argument， So we're not going to worry about its value。

 The first line declares H W and initializes it using new。You learned about new in a previous lesson。

 but there's a slight difference here。 The hellello world class does not have a constructor。

 So what do you do。In this case， Java provides a default constructor。

 one with no arguments that does nothing。 So we execute this line， as you're used to。

 but we don't call a constructor。 We make an object Class hellello world has no fields。

 So the object itself doesn't have any state or anything else we can see in it。

 Then we finish the assignment statement。Next， we call run Hello passing in H W as the implicit this argument In of Run Hello。

 our first statement declares the variable F。The next statement initializes F to a new file resource object。

 This raises two questions。 First， what does a file resource object look like。

 meaning what fields are there in the file resource object。

It turns out we don't actually need to know this precisely。

 The details of how a file resource object works can remain hidden from us as long as we know what it does。

 This is an instance of the important programming principle known as abstraction。Second。

 what does the constructor for a file resource object do to find the answer to this question。

 we would consult the documentation for file resource。 Consulting documentation for libraries。

 sometimes called APIs that you use in programming is an important task Since file resource comes from the Duke learn to program libraries。

 we would look at the documentation website， and we would read about the constructors for a file resource class。

 There are three constructors， and the one we want is the one in the middle。

 since we're passing a string literal in the string file do TxT this documentation says the constructor will find that file with that name on our computer。



![](img/ea4de499b0a80a9c0263bab58d9191fb_5.png)

![](img/ea4de499b0a80a9c0263bab58d9191fb_6.png)

Given this information， we're just going to represent the file resource object is knowing what file we asked for the file whose name is file dot T X T we don't know precisely what fields are stored in this object。

 but that's okay。 We'll represent it as precisely as we can because we know what the object does。

 We finish the as statement。 So now F references this file resource object we just created by calling the constructor。

 The next line is new to us。 It's a for loop。 In particular。

 this for loop is often called a for each loop。 because it does something for each value in an iterable。

What's an iterable， The short and simple answer is that it's an object which gives you a sequence of values。

 Let's dig a little more closely into the details of this loop。 The first part declares a variable。

 The type is string， and the name of the variable is line。

 This declaration will behave like any other will create a box for line。 Next is a colon。

This is the syntax of a for each loop。 We don't use an equal or assignment operator since we are assigning one value to line。

 Instead， we're going to use each value in the iterable sequence。

 Many people read the colon as in when they read the code out louder to themselves for string line in F dot lines。

 Next， we have an expression， which evaluates to the iterable。

 whose values we want variable line to refer to one after the other。 In this case。

 that expression is a call to F dot lines to understand what this does will need to understand what F dot line returns。

 So again， need to consult our documentation。 from this API documentation。

 we see that F dot lines gives us an iterable whose values are each line in the file in the order that they appear。



![](img/ea4de499b0a80a9c0263bab58d9191fb_8.png)

This week means that we'll need to look at the file whose name is file。

txt to see what its contents are in order to understand and simulate the code behavior。



![](img/ea4de499b0a80a9c0263bab58d9191fb_10.png)

On my computer， I've made file do T X T and put these two lines in it。

 Hello on one line and world on the next line。 It isn't a very exciting file。

 but we want this example to be relatively short。

![](img/ea4de499b0a80a9c0263bab58d9191fb_12.png)

Returning to our code， we now create this sequence of strings。 Hello and world。

 We'll create the box for line， and we'll make it refer to the first element of this iterable sequence。

 Now we go into the body of the for loop and begin executing statements there。

 The next line is a print statement。 So we print out the value of line， which is hello。

Now our execution arrow is just before the closed curly brace of the for each loop。

 we've reached its end。When you reach the end of a for loop。

 you move the execution arrow back to the start of the loop to do the next iteration the next time through the loop with a new value for the loop variable。

 In this case， our loop variable is the string line。

 So we need to update it to have the next value in the iterable。

 We update lines' arrow to point at the next value in this sequence。 and again。

 go into the body of the loop。 We encounter our print statement。

 But this time line has a different value。 So we print world。Now。

 we've once again reached the end of the body of the for loop。 So we go back to the beginning。

 the start of the loop。 We need to update line to refer to the next value in the iterable sequence。

 However， if we try to do that， we'll find that there are no more elements in the iterable sequence。

 We already use the last one。 So instead， we exit the loop。

 we move the execution arrow past the body of this for each loop and begin executing code there。

 when we do this， the loop variable in this case， the string line goes out of scope。

 That means it no longer exists。 So we remove its box。 Now。

 we're ready to return from the method run hello， destroying its frame。

Since the call to that method run Hello was the last line in Maine。

 we also returned from Maine exiting the program。

![](img/ea4de499b0a80a9c0263bab58d9191fb_14.png)