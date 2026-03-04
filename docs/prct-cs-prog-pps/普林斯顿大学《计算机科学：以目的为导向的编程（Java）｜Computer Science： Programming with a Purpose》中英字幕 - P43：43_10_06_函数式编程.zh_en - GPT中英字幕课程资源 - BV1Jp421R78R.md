# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P43：43_10_06_函数式编程.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/afdb700c52f087fe5ff7008a8189d506_0.png)

We're going to finish up by talking about functional programming。

 which is a completely different programming style than what we've talked about so far so far。

So why can't we use functions as arguments in Java programs？ Well。

 the answer is that actually in the latest version of Java， we can。

 doing it is pretty cumbersome in earlier versions even though it's possible。

And so let's talk about the idea of having this ability more generally。

 so functional programming is a programming style where we just treat computation as just the evaluation of functions。

And there's lots of modern languages for which this is really the basic concept。

So in its purest form， it completely avoids side effects in programming。

 which makes it much easier to reason about the correctness of programs。

 it's got what's called an ondemand execution model， it's what I want to compute。

 not so much how I'm going to compute it and we'll try to give a couple examples that explain these points。

So the big advantage of functional programming that we can now take advantage of in Java eight programs and other examples functions are firstclass entities。

 they can be arguments or return values of other function or they can be stored as data this opens up really a different world of programming and we'll see very often we can get much more compact code than alternative styles and again reasoning about a correctness of code is easier with the functional style。

 another thing is that it supports concurrency that's programming on multiple processors and that's very important nowadays people write programs that are intended to work over huge numbers of processors with the functional style we're not quite saying how to do the computation step by step we' just specifying what the computation is and things are structured and simple enough that the system can。

out how to allocate the computation to different processors。

So just a familiar example of passing a function as an argument or return value back when we looked at Newton's method。

 we wanted to find the value where a function is equal to zero and use the derivative of that function that computation is best expressed as a functional program。

 you want to function that going to find the root or Newton。

 you want to give a function as argument and then all Newton's method does is evaluate that function to get to its answer。

Or for sorting， which is we'll look at in part two of the course。

 you want to pass a function as argument that tells how to compare to things to be put in order。

Those are just some examples。So let's look at some simple examples of functional programming just to get started。

Here's a Python program that prints a table of squares。 and clearly。

 this is going to extend to any kind of function。So how do we specify a function that computes the square of its argument in Python。

 you should say deaf， give the name， colon and return X star x。

 that's the full definition of a function that squares its argument。So that's good。

 But now what we can do is。We can write another function that takes a function as argument in a sequence。

 say。And we say for x in the sequence。Prntex。Print F of x。 So it took the function as argument。

 and now it's evaluating the function on some variable that is the index of its for loop。

So that's a function that takes a function and a range of arguments and prints a table of values to the function for every value in the range。

 Now， if we call that function with its first argument。

 our function square and its second argument range 10， remember range 10 is a sequence0 through9。

 then we get a table of the squares， and we can use that same function。

 we could define cube or any function at all， we can put any expression at all instead of x star x in that function that's a really compact expression of that computation。

That is a simple example of the utility of function programming。

But now you can have powerful operations， say。Functions that operate on functions。

 And here's two basic operations that are very important and very widely used。

So one is the map operation。So that takes a function and a list as arguments。

And what map of the function followed by this sequence。

 the result of that is replace every x in the sequence by F of x。

So here's just an illustration of map。 So there's our square function。Here's another function odd。

 so that's returned2 x plus1。So if we print map。Of odd， a range of 10， What do we get。

And then print map square of range of 10， then we'll get the odd numbers and we'll get the squares。

So so we have the numbers one through9 and then in the first print statement， our odd function。

 each one of those numbers gets replaced by twice the number plus1 number 0 through 9 so that gives us one through 19 and then squares we get 0 through 9 we get 0 through 81 so that's the map function you can think of it as a compact expression of the four loop。

But now if we combine that with the reduce operation。

 that one takes a function and a list of arguments。But what it does is in its classic form。

Is to if you it takes a function in a list， it's going to return the function of the first thing on the list。

 followed by reduce of F and the rest of the list， that's car is short for the first thing on the list and Qter is short for all but the first center in the list。

 and this is terminology that comes from McCarthy's list language in the 50s。

So that's be easier to understand in an example。 So let's say we have the function plus。

In our function odd， what happens if we say reduce plus map of odd range of 1。Well。

 it turns out to print out 100 so how does it get to that Well so we're going to just trace out what it's supposed to do now actually Python it does it for the last entry。

 so it's not quite what I put in the classic definition of reduce。

So what we do is we take out the 19 and our function is plus。

 so we're going to reduce plus of the first part of the list， not including the last one。

 and then do a plus of that in the last entry in the list， which is 19。And so we do it again。

 and we pull out the next one and so forth。 So this is equivalent to saying add all the numbers together in the sum of the。

First， N odd integers is n squared as we learn in some early lecture。

So that's map and reduce in combination and again， the code is extremely compact and it's a way of expressing what the computation is。

 not how to do it and you can imagine for a huge range it's how it might be possible for the system to figure out how to break the computation。

 say among parallel processors or something of the sort。

That's why functional programming of this sort is widely used on modern systems。

So let's go back to our reasons to learn a programming language， offers something new。

 absolutely functional programming， if you don't know it， it offers you something new。

Need to interface with coworkers if there's even functional programming jobs available on Wall Street nowadays。

Better than Java for the application at hand， definitely。

 if you're one of these situations where parallelism is important and the compact expression of the computation or the ability to prove it correct is important。

Intellectual challenge， absolutely developing computations from this point of view。

 developing programs， any new programming language but particularly functional programming， in fact。

 the intro CSS course at MIT for many years was taught in scheme。

 which was purely functional language。Opportunity to learn something about computation for sure。

 and it definitely introduces a new programming style。So again， there's lots of modern applications。

 and for example， the Google Ma reduced processor， which is a huge scaled computational engine based on functional programming。

And not only that there's a deep and direct connections to theoretical computer science and we discuss a little bit in the second part of the course。

 as with many other things， all different types of programming styles and environments are addicted to certain types of people and certainly get into functional programming you might find it so interesting that you never get out。

So let's go back to the Tower of Babel now， the idea that the proliferation of cultural differences in multiple languages is a basis of civilization。

I think that's a pretty apt to metaphor。 Would we be better off if we just had a single programming language that enables us to do anything that we imagine。

Is the proliferation of languages， isn't that really a basis for civilization and programming。

 and this is not a new idea， in fact I got the idea from Gene Sammon's book in 1969 on the cover of her book at that time already there were 120 languages。

The number of languages that have been defined now， certainly thousands or tens of thousands。

Definitely learning more languages is at the basis of learning more about computing。Well。

 that's the first part of our course and again， this is from one of our early slides and we hope with this course that you feel confident that you've checked off the program a computer line。



![](img/afdb700c52f087fe5ff7008a8189d506_2.png)

And we hope to see you in part two where we learn more about the implications of computing and answer questions like how does my program work my computer work。

 and what kinds of problems can I solve with my computer？



![](img/afdb700c52f087fe5ff7008a8189d506_4.png)