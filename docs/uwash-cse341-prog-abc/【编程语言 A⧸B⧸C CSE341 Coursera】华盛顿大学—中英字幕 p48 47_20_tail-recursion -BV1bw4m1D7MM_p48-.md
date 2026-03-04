# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p48 47_20_tail-recursion -BV1bw4m1D7MM_p48-

In this segment we're going to start our discussion of tail recursion。

 This is a new topic relevant to reasoning about how efficient your recursive functions are in ML and in other functional languages so at this point we've written a lot of recursive functions and so hopefully you're convinced that writing a recursive function is no more difficult than writing a loop in fact I've never shown you a loop I could even pretend that I don't even know what a loop is I would even argue that recursion while never harder than a loop is often easier than a loop whenever you're processing a tree like when we evaluate an arithmetic expression。

 you really want recursion examples like a pending to list together became much easier when we just thought recursively and basically these recursive functions avoid any need for mutation even of local variables if you have something like a four loop。

 you always end up incrementing that index I and we're really trying to stay away from mutable variables。



![](img/5bf2b2c5470fe31b11a1e11447e3585d_1.png)

But what we haven't talked about yet is whether recursion is efficient or in what situations does it lead to fast code a lot of times people think recursion is inefficient。

 that's not necessarily the case， and even when it is the case。

 it often doesn't matter but what we're going to do is see the importance of this idea called tail recursion and then in subsequent segments see how to use common idioms in order to get tail recursion using things like an accumulator so just to be clear I'm not showing you any new language features here。

 just new programming idioms and new ways to reason about the efficiency of code that we've already been writing。



![](img/5bf2b2c5470fe31b11a1e11447e3585d_3.png)

So to understand recursion and tail recursion， I have to tell you a little bit about how function calls are implemented and all you have to understand is the high level idea of a call stack。

 so when a program runs there is a call stack of all the functions that you have called and that aren't done yet。

Okay， so when you call a function F， what that does is it pushes onto the stack， some instance。

 something that is going to stay on that stack until the call to F finishes。

 and when the call to F finishes， we will pop it from the stack。 So at any given time。

 the stack contains all the calls that have started and not finished。

 and there can be lots of them because one function calls another one。

So what's in these stack things， which I'll call stack frames。 Well。

 they store information like what are the local variables bound to and they store information like what work is left for this function to do after any function that it called is done with its evaluation。

Now notice that if we have a recursive function where F calls F， which calls F， which calls F。

 we're going to have multiple stack frames on our stack that are all for the same piece of code。

 the function F， that makes perfect sense， and it's what recursion is really about。

So let's see an example， suppose I have a factorial function here so it just computes if you pass it n。

 it returns n times n minus1 times n minus2 down to1。

 it only works correctly for non-neative numbers and suppose I call fact with three。

 so I'll eventually get the answer six back three times 2 times1。

So my first call is here on this single element stack you see， I'm calling fact with three。

And then when I call fact with3， it ends up calling fact with2，3-1。

 And so I'm going to represent that by adding to my stack that there's now a call a fact2。

 And what fact 3 is remembering to do in its stack frame is when it gets its result back。

 it's going to multiply it by3。 and then that will be its answer。

 So three times whatever I get back from the call to fact2。Similarly。

 fact2 is going to call fact1 and I have a bigger stack where fact2 is waiting to get it the result of the call and multiplied it by two and even fact1 ends up calling fact0 so at this point I have a stack with four elements on it but then when I call fact with zero it evaluates the if expression and returns one so there's no additional call put on the stack so it ends up saying all right I'm going to return one and when you return you pop that off your call stack。

😡，So now we have a smaller stack and now fact1 has its recursive result。 It needs。

 It multiplies one by one， gets one， and now we pop it off， get two by one。

 We now pop off the recursive call of fact with argument 2。

 We have fact of3 and then fact of  three would eventually return6。 All right。

 so this is how call stacks work。 This is exactly what I would expect to happen when we evaluate fact。



![](img/5bf2b2c5470fe31b11a1e11447e3585d_5.png)

Now here is a second version of factorial that is more complicated。

I'm going to show you in a minute that it's actually more efficient， but we can't see that yet。

So let's first understand how this version of factorial works。

 What it does is all it does is it calls a helper function locally defined。

 although that's not important that I've called ox for auxiliary for helper function and this helper function takes in a number but also a。

 which is short for accumulator and what it does is it says if n equals0。

 then just return whatever is an accumulator otherwise call ox with n minus1 and go ahead and multiply the accumulator by n。

And I'm going to show you that this will actually compute factorial correctly。

 Instead of our simple recursive function。 What we're doing now is we're multiplying into this second argument accumulator as we go。

 So when n is0， we just end up returning accumulator。 So this is still recursive ox is recursive。

 it's more complicated， But when ox calls ox， the result of the recursive call。

 is the result for the caller， there' is no extra work to do。 When I got back here。

 when in the first version of factorial， after the recursive call， the caller had more work to do。

 It had to multiply by N here， there is no more work for the caller。

 the result of the recursive call is the result。 And that's going to be the key difference。

 But before I show that， let me show you how the call stackax would look given what I've shown you so far。

😊。

![](img/5bf2b2c5470fe31b11a1e11447e3585d_7.png)

![](img/5bf2b2c5470fe31b11a1e11447e3585d_8.png)

So I start with fact3。Fact3 is going to call a with three and one。

 because that's the initial value for the accumulator if you look back at the code。😡。

Then ox of 31 will end up calling ox with2 and3， so3 minus1 is 2 and three times the currentummator 1 is three。

 Now notice that these callers on my stack are just waiting to get their results back and immediately return them。

So then ox 23 we'll call ox 16， ox16 we'll call ox 06。

 so at this point I have a bigger stack than I actually had with my previous version。

 but now ox 06 will return6。Oux 16 will return that6， A 23 will return that6。

 ox 31 will return that6 and fact three will return that six this will just continue until I'm done with my program。

All right， so now we get to the key idea of an important optimization that you should understand functional languages do。



![](img/5bf2b2c5470fe31b11a1e11447e3585d_10.png)

It is simply unnecessary to keep around a stack frame if all it is going to do is take the result from the colleaee and immediately return it。

😡，So such a situation is called a tail call for reasons I've never fully understood。

 but that is what everyone calls them， and the compiler， the implementation of the language。

 recognizes these function calls and treats them differently。

What it does is it removes the caller's stack frame before it makes the call so that the call lead just reuses the same stack space that the caller was using。

And along with a couple other optimizations I'm not going to show you。

 this makes recursive functions that use tail calls absolutely as efficient as loops in other languages。

 and so it is reasonable to assume it is guaranteed by MLL the language that you can assume this kind of efficiency for tail calls so in fact。

 what I showed you before for this more complicated version of factorial is not what happens。



![](img/5bf2b2c5470fe31b11a1e11447e3585d_12.png)

We do start with our stack fact of3， but right here where I see this call for fact 3。

 this is a tail call， there's nothing more for fact to do when it calls aux of n and1 than return it。

 so we will reuse the stack space， we will replace the stack frame for fact 3 with the stack frame for ox 31。

😡，Now we're evaluating the aux function with3 and1， and when we get down here to the recursive call。

 there is no more work to do afterwards， so this is also a tail call so we will reuse this stack space for the recursive call of OX 2 and3。

The same thing will happen with the next recursive call and with the next recursive call。

 and so we never build up a stack and when as 0 comma 6 returns6， we immediately have our answer。

So that is why this more complicated version of factorial is in fact more efficient and if you were planning to use factorial on very large numbers where you cared about this sort of efficiency。

 this would be a better way to write it on the other hand。

 if you were just computing factorial of three， it's more complicated and I would probably prefer the simpler solution。

😡。

![](img/5bf2b2c5470fe31b11a1e11447e3585d_14.png)