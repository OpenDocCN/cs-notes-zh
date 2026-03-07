# 多伦多大学【中英⚡编程入门：编写高质量代码｜Learn to Program： Crafting Quality Code】 p27 P27 05_处理异常情况 -BV1QuJVzpEKE_p27-

![](img/6a6401b7237c31f750a969e1e59d9643_0.png)

So far in this course， we've been assuming that input to functions is valid。In this lecture。

 we're going to show you what to do when input is invalid。 That is when preconditions are not met。



![](img/6a6401b7237c31f750a969e1e59d9643_2.png)

We have all encountered errors。 Here's one where we divide by 0。



![](img/6a6401b7237c31f750a969e1e59d9643_4.png)

The trace back tells us the list of functions and methods on the call stack here。

 only the shell session is on the call stack。The next line shows the Python statement in which the problem occurred。

The last line shows the kind of error and a message containing a description of the issue。



![](img/6a6401b7237c31f750a969e1e59d9643_6.png)

Here's another example。 We'll try to find the index of Q in ABC。Here we get a value ever。

There are other ways to get value errors。 They happen when we tried to turn string Uga into an integer。



![](img/6a6401b7237c31f750a969e1e59d9643_8.png)

The exception type is the same， but the two value ever messages are quite different and describe what the problem was。

The writing is quite terse， but you'll get used to it if you put some effort into reading it carefully。



![](img/6a6401b7237c31f750a969e1e59d9643_10.png)

![](img/6a6401b7237c31f750a969e1e59d9643_11.png)

Here's what function help has to say about class value ever。

It means that there was an inappropriate argument value In both of the examples。

 That's exactly what happened。 We called the function or method and asked it to do something that it couldn't do。



![](img/6a6401b7237c31f750a969e1e59d9643_13.png)

That is why it is an exceptional situation。 It isn't part of the normal execution of the call。



![](img/6a6401b7237c31f750a969e1e59d9643_15.png)

The method resolution order lists the classes in the inheritance hierarchy。

 Class value ever is a subclass of class exception， which itself is a subclass of base exception。

 Class base exception is a subclass of class object。



![](img/6a6401b7237c31f750a969e1e59d9643_17.png)

0 division errors provide the same pieces of information。

 They occur because we asked Python to do division or modo by 0。



![](img/6a6401b7237c31f750a969e1e59d9643_19.png)

Note that class zero division ever is a subclass of class， arithmetic error。



![](img/6a6401b7237c31f750a969e1e59d9643_21.png)

Python provides an exception handling statement。 We can try to execute a block of code。

 and Python will contentedly execute it， except when there is a problem。In the except clause。

 we can do whatever we like， as with any other block of code。When an exception is raised。

 any following code in the same block is not executed。 For example。

 if we add a pen statement after we divide by 0， we see that it is not executed。In the except clause。

 we can specify which exception types we are interested in。 If we specify 0 division error。

 we still catch it。If we change this to value ever， the accept clause ignores the exception。

We can use both， much like Python handles ifs and dephs。 It tries each accept clauses in order。

It executes the block of the first matching exception type， and skips the rest。

This means that we can hide later except clauses by using a super class。

 because every0 division error is also an exception。 The first clause matches。

 So Python does not reach the0 division error clause。Every exception is an object。

 and Python allows us to give them a name Here， we assign the0 division ever to a variable Z D E。

We can use this variable as we would any other variable。

We can cause exceptions to happen using the Ray statement。Let's go try all this out in a program。

Function raise an exception， raises a value error。

![](img/6a6401b7237c31f750a969e1e59d9643_23.png)

Function main calls raise an exception with argument 3。The main program calls function Ma。



![](img/6a6401b7237c31f750a969e1e59d9643_25.png)

When we run this， there will be three frames on the call stack。

 The main program function main and raise an exception。



![](img/6a6401b7237c31f750a969e1e59d9643_27.png)

This information shows up in the traceback。Notice that the most recent call is last。

That means that the function in which the exception occurred is on the bottom of this trace。

The second line in the Ray's statement is shown。Inneath that。

 Python displays the exception type and the message。



![](img/6a6401b7237c31f750a969e1e59d9643_29.png)

The other two frames are also included in the trace back。 We see that Na appears right in the middle。



![](img/6a6401b7237c31f750a969e1e59d9643_31.png)

And that it called raise an exception。Main was called from the main program in the module。



![](img/6a6401b7237c31f750a969e1e59d9643_33.png)

Here is a try statement that tries calling function main and catches any exceptions that are raised or at least any value ever。

When we run this function main is called。 the value error is raised。

 and we catch it in our accept block， printing whatever the exception is。

It's quite common to want to assert that a variable has a particular value or range of values。

Python provides an assert statement that does just this Here。 we assert that x is equal to 3。

Notice that this assertion was true， and there was no output as a result。

If we assert that x is equal to 4， however。An assertion ever is raised。



![](img/6a6401b7237c31f750a969e1e59d9643_35.png)

We can use the assert statement to check preconditions。



![](img/6a6401b7237c31f750a969e1e59d9643_37.png)

Many programmers use assert statements to confirm that preconditions are met。

When we run this module and call function every n with valid arguments。

 the return value is what we expect。 However， if we violate the precondition。We get an assertion。

 ever。We get the same result， if n is too large。We can provide a message to go with the assertion error。

This message is included in what gets printed when an exception reaches the shell。

That was a whirlwind tour of exceptions in Python。A proper treatment would take up an entire week's worth of lectures。

 but we wanted to give you an overview so that you can read exception code and understand how it works。

Well end with a couple of tips to keep in the back of your mind as you explore exceptions further on your own。

 First， exceptions are for exceptional situations， situations in which the programme couldn't do what it was supposed to。

Second， only catch exceptions that you know how to handle。

This is frequently in the user interface code where we're asking users for values of various kinds。

If the user provides a value that isn't valid and it causes an exception。

 we can ask them to enter another value。Related to that as a saying， throw low。 catch high。Typically。

 ever are encountered deep in the bowels of a programme。 and often。

 the programmer at that point has no idea how to recover from the ever。

 So they'll raise an exception saying， sorry， I have no idea what to do with this data。

A raised exception will propagate up the call stack until an accept clause catches it。

It's generally a bad idea to just let a program crash。

 And that means that code very high up very early on in the program should have a general try。

 except that catches errors and at least provides an informative message for the user。Last。

 many programmers feel that it's sensible to assert that preconditions are met。



![](img/6a6401b7237c31f750a969e1e59d9643_39.png)