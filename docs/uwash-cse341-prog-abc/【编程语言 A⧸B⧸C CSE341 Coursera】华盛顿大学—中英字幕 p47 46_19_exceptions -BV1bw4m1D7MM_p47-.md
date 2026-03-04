# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p47 46_19_exceptions -BV1bw4m1D7MM_p47-

In this segment we're going to talk about exceptions which are what you use when you have a runtime condition that should be an error。

 We'll talk about how to create exceptions， how to raise them。

 which is called throwing in many languages and how to handle them which is called catching in many languages and this is a reasonable place in the course to put this because the way M does exceptions is very similar to how it does data type bindings。

 although exceptions are a separate concept。 So let's explain most of this with the code and then will summarize what we see with a couple of slides。

 So first let me show you how the function head is actually implemented。 So remember what head does。

 it takes a list if the list is non- emptyty， it returns the first element。 if it is empty。

 it ends up raising an exception that happens to already be defined and called list do empty So here is exactly how I expect the code in M standard library to be implemented just has a case expression in the case of a non-empty list it returns X。

 but for the empty list it uses this raise。

![](img/3f6504acc2d9b5da72da370ee511f568_1.png)

Keyword followed by the exception， and indeed， if we had a call of head with the empty list。

 head would never return because what rays does is cause an exception to occur instead。Allright。

 so list that empty was just defined by whoever wrote M standard library。 Not surprisingly。

 we can define our own kinds of exceptions。 And what you do is use the exception keyword and then any name you want。

 It's traditional to capitalize them。 So here I've created an exception called my undesirable condition。

 you can see here a little bit lower that having introduced that new exception binding。

 I'll be able to raise my undesirable condition。 you can also create exceptions that carry values。

 the syntax is exactly like with constructors。 So here's another exception where my other exception is not an exception。

 It carrying a pair of ints would be。 So you'd be able to write something like raise my other exception of three comma4。

 and that's a way to pass data out to whoever might be handling your exception。

 All right so at this point， we've seen our first use of rays up here in head。

 We've defined our own exceptions。 Now here's a function called my。😊，That takes two integers。

 and if the denominator is zero instead of raising whatever normal exception ML raises in this situation。

 we raise my undesirable condition instead， so that's really all there is to it。Now。

 there is one other distinction I'd like to make。 There is a difference between making an exception value。

 which is just something of type EXN and raising it。

 So here is a function max list that takes in a list and an exception。And if the list is empty。

 it raises whatever exception was passed in。😡，Otherwise， if the list has one element。

 it just returns it， otherwise it returns the max of the first element and the max of the rest of the list。

 So it's another nested pattern matching example， but the interesting thing here is that the call to max list passes in the exception。

 So max list in fact has type int list star EXn， which is the type of all exceptions，arrow int。

 because if it does return， it will return an int it raises an exception who cares what the return type is。

 So here I have a call to max list where I pass in the list 3 comma 4 comma 5 and pass in this exception。

 Now this is not going to cause an exception to be raised， it's just an exception value。

 And since in this case， max list won't call use raised with the exception， no exception occurs。

 So if I run this code W will simply end up being bound to5。The maximum element in the list。Allright。

 so the last thing I want to show you with exceptions is how to handle them。

 This is what a lot of languages call catching an exception。

 So anywhere you have there's a new form of expression I just haven't shown you before。

 anywhere you have an expression E1， you can then write handle some exception name。

 it's actually a pattern， some exception thing， and then some E2。😊。

And what this is going to do is if E1 evaluates normally， then the rest is irrelevant。

 but if E1 raises the exception listed here， then we'll evaluate， we'll catch that exception。

 we'll evaluate E2 instead。 If this is not the same exception that E1 throws。

 then we are not handling it and it continues the result of the entire thing is that the same exception is raised。

 So here is a perfectly reasonable example of a handle expression。

 but since the thing before the handle does not raise an exception， this's just evaluates to5。

 the result of this entire thing is just going to be5。 All right on the other hand。

If we had this code here。Where we pass max list the empty list。

 then indeed max L is going to end up evaluating raising my undesirable condition。

 so we will handle that exception and the result Z will end up being bound to 42。

This final example which is commented out here， this if we evaluate it。

 will in fact raise the exception， so y we' never end up being bound anything and since we don't have a handle expression here。

 the evaluation of our program would stop and so that is why I have it commented out and so we can see all this quickly if we come over here and just use this file。



![](img/3f6504acc2d9b5da72da370ee511f568_3.png)

We will see that I'm right， that W and x are both bound to 5 and z is bound to 42 and no exceptions were raised because the only one that happened。

 which was up when we evaluated the expression for x。

 we handled and decided to evaluate the expression to 42 instead。Okay。

 so let's switch back to the slides and see what's going on in general。

 We have a new kind of binding I had not shown you before。 This is an exception binding。

 This is how you introduce a new kind of exception。😊，We have a new keyword I hadn't shown you before。

 raise， this is how you raise or throw an exception。

And we have another new expression form for handling or catching exceptions。

 where we evaluate the expression to the left of the keyword handle。

 if that does not raise an exception， then that's our answer。

 if it does raise an exception and that exception matches the one we have there， then we evaluate E2。

 otherwise we continue to raise the exception。So it turns out that exceptions are a lot like data type constructors that there is this built in type EXN over here in the code。

 you'll notice that Max list does have type inless star EXN arrow int。 Allright。

 So when you add a new kind of exception。 you're really just adding a new constructor of type EXN。

So EXN is just a normal type， which is why we can pass values of Ty EXN like we did into Max list。

 it's not too common to do this， but it's useful， it does let your caller choose what exception you raise。

 which seems like a potentially useful thing to do。

And it turns out that handle expressions are more general than I've been showing you here。

 you in fact， can use pattern matching as deep as you want on those things of Ty EXN。

 and you can even have multiple branches separated by the pipe character but nonetheless。

 I've shown you enough basics。 you'll use exceptions just a little bit on your homework to make sure you understand how they work and how they can be used and now you know how they work。

😊。

![](img/3f6504acc2d9b5da72da370ee511f568_5.png)