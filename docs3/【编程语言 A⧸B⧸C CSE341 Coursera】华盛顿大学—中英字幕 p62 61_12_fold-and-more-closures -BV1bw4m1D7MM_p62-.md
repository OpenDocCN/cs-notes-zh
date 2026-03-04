# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p62 61_12_fold-and-more-closures -BV1bw4m1D7MM_p62-

Now I want to show you another famous higher order function that recursively traverses over data structures and then use that to show you more examples using closures and emphasize what these sort of iterative higher order functions are really all about。

So it's called fold。 It is very similar， possibly even a synonym to similarly wellknown names like reduce or inject。

 and the idea is to traverse a recursive data structure like a list in order to produce a single answer。

So the way fold is going to work， We're going to define a function fold is we're going to pass in a function F。

An initial value， which I'll call a for accumulator and a list And what we're going to do。

 as you can kind of see here， is apply F to the accumulator and the first element of the list。

 take that result and pass it to F with the second element of the list。

 Take that result and pass it to F with the third element of the list and so on。

 So you can imagine if you imagine your list laid out from left to right。

 that you really are folding over it， you're going over it starting with the accumulator。

 applying F to the accumulator in the first element to get another value。

 applying F to that value in the second element， that value in the third element and so on until you reach the end of the list and that's your final result。

As common in language with higher functions and convenient syntax like ML。

 I can write that function in about three lines， take in F that initial commator and x's。

 if the list is empty， then the accumulator is itself the result we want。Otherwise。

Compute F of accumulator and X and pass that two fold with F and the rest of the list Here。

 I'm shadowing this x's here in my pattern。 So this is folding left over the list。

 If we write down our list elements left to right， we could write a different version of fold。

 that would go from right to left。 That version couldn't be tail recursive quite as well。

 And the order doesn't matter unless it matters for F。 So that's why in the standard library。

 they actually do distinguish left from right。And the type of fold tells you a lot about what it does。

 If we type this into the readtaval Pri loop， what we would get is that the function F。

Can take any two types， Al and beta， Maybe they're the same。 Maybe they're different。

 but it has to return something of type alpha because the old accumulator and the new accumulator have to be values of the same type。

That type alpha has to be the type of ACC， the accumulator。

 the list has the type of elements of type beta。 that other argument we pass to F。

 And then the result of the entire thing has the same type as the type of our accumulator。

 and that's alpha。 So you start with a beta list and an alpha， an initial answer。

 You use F to fold over the list producing a new answer at each position in the list。

 We get to the end of the list。 Your final answer is that last alpha。😊，So that is fold。

 Let me talk about why we're so excited about these things。

 so these iterator like functions are not built into the language。

 They're just a programming pattern。 we just wrote it on the slide it's three lines of ML。Now。

 many languages provide built in support for iterating over a data structure and computing a result like like we would do with fold。

 there's nothing wrong with built- in support。 These things are so common。

 Maybe that's a reasonable thing to do。 They also provide special features like usually you could stop halfway down the list。

 whereas fold is all the way going to always go all the way down the list。But。When we have fold。

 we can just write it in our language。 we have I functions， and it's really a concept。

 We wrote fold here over lists。 We had a different data structure like an array or a tree or a graph or a set we could write fold over that as well。

 And then of course we're going to use fold with lots of different clients passing in lots of different Fs。

 So what I love about this is that it's a separation of concerns。

 One group of people can worry about writing fold over some complicated data structure。

 lists are not complicated， but they're much more complicated things out there。

 and then someone else can worry about how to compute over a particular for a particular result。

 And then if you change and you start using a different data structure other than a list。

 you can reuse your function， you just need a new fold and conversely once you've written fold for list。

 lots of different people can use fold for list for different computations。

 So it really separates two things out simply by using。

A high order function and passing one function to another。Okay， enough hypothesizing and theorizing。

 let's get to the code and show you a bunch of example uses of fold since you may still be getting the hang of how it works。

 I've purposely given all of these functions non revealveing names so you can kind of play along so here is fold up here。

😊。

![](img/a46dcd942e39cb0a1dcbb039ca170200_1.png)

All， remember， it's going to apply F to the accumulator in the first I want the list。 Get a result。

 App that to with that in the second element the list and so on。

 So what we do here in this first call is we pass in some list X's。

Our initial accumulator is zero and what we do every time the first argument to this anonymous function is going to be the next is the accumulator。

 the current accumulator， and the second thing is the next element of the list。

 you can see that right here in fold So what we do here at each step is we take what was the accumulator and the next element of the list and we add them together。

😡，That will be our new acccubator。 Then we'll get to the next element list， and we'll add that。

 get the next element list and add that。 So when I describe it that way。

 it seems pretty clear that this is a one line solution given fold to summing the elements of a list。

😊，Let's do another one。Here I also have a list， My initial accumulator is true。

 so at each step I'm going to produce a Boolean， you can't change the type of your accumulator still in a language with a strong type system。

 and here is my anonymous function。Remember， X is going to be what the accumulator。

 fold is going to pass back into our closure。 whatever the next accumulator is。

 And y is the next element of the list。 So what we do is we take our accumulator。And。

Is y greater than or equal to0？So if y is negative， we're going to get false for this whole thing。

 if x is false， we're going to get false for this whole thing and x keeps updating with each element of the list。

So what this ends up doing is are all list elements。Positive。OrExcuse me。

 non negative if you want to be picky， right？诶。Okay， so both those examples did not use private data。

 right， These closures we passed in only used their arguments。

Now let's see the real power of closures， which is that you can use other things。

 so here is a call to fold。X's is my list。0 is my initial accumulator。

X is always the current accumulator。 Y is the next element of the list， and I am adding to it。

 So I'm summing something here。 But what I'm adding here is if y is greater than or equal to low。

 and y is less than equal to high than 1 else is 0。

 Okay so notice I am using private data here low and high。

 refer to these things that are only in scope here where I define the function， but that's great。

 closures are powerful that way。 And then I compute there1 or 0。😊。

So what this is actually doing is counting the number of elements between low and high inclusive。你。😡。

It's almost one line long， it got a little long for me。Okay， here's another one。

 This is similar to something we did in the previous segment。

 Now I'm going to take in a list of strings and a string， and I'm going to call fold。

 I'm going to produce a boolean here。 starting with the list X is。

 And my closure here says X and also something。 So I'm doing the same game as I was doing previously of computing is something true of every element of the list。

 If you fold over in this way。 you're going to do a for all， if you will。

 are all elements of the list such that their size is strictly less than I where I is this variable。

 I bound up here， computing once to avoid recomputation。 the size of the string S。

 So what this ends up doing is computing are all elements of the list。

 strings whose size are strictly less than the size of S。😊。

And I avoided recomputation like we saw in the previous segment。

One more example here of some different function， this one is more generic。😡，Okay， so F 5。

Takes in a function G， and a list x's。And it passes X is the fold。 initialial accumulator of true。

 But what it does is it says x and also G of y。 So now callers of F 5 will pass in a function that says。

 well， this is how you decide if this element of the list passes the test。

 And it's F 5's job to use fold to see if therefore， do they all pass the test。

 So this is really saying， do all elements of the list， produce true when past to G。And now。

 given that reusable function， I could redefine F4 without using full directly。

 I could just use F 5 as my helper function。 And all I have to do is call F 5 with this simple anonymous function and the list X' is。

 So this is just another way to use higher order functions。 F 5 is using closures here。

 Notice this G is defined where the function is defined。



![](img/a46dcd942e39cb0a1dcbb039ca170200_3.png)

Alright， so that was several examples。 And let me just remind you why I'm showing you this。

 which is that map filter and fold do become much more powerful thanks to closures in lexical scope。

 We can pass in any private data that our function F needs just by using scope and the iterator fold itself doesn't need to know what data is there or even what type it has。

 So our first couple examples。 F1 and F2， I believe， didn't use private data。 And that's fine。 F3。

 F4 and F5 did， and that's fine too。 fold works the same way。

 It just calls F Once for each element of the list。 And F can use whatever is in its environment。😊。

So now we've seen map filter and fold， probably the three most important higher order functions there are。

 Of course， there are many other useful ones。 In fact。

 the F5 we just defined is itself a very useful higher order function。

 It's easier to use simpler to use than fold， but we nonetheless defined it using fold。😊。

And that's the end of our study of fold。 Now we can continue to study other idioms。

 other important ways that we can use closures。

![](img/a46dcd942e39cb0a1dcbb039ca170200_5.png)