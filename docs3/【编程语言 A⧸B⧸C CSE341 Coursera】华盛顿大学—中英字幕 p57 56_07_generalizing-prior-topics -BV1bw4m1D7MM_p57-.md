# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p57 56_07_generalizing-prior-topics -BV1bw4m1D7MM_p57-

We've now seen a number of examples of first class functions， including my favorites map and filter。

 but all of our examples so far have been similar enough that I want to emphasize now just how general first class functions are So so far our examples n times map filter and probably a couple others have all just had one function that took one other function as an argument and then recursively process numbers and lists So I just want to remind you that we can use functions wherever we can use any kind of expression this is actually a useful thing to do So a couple of things I won't show you examples of in this segment are passing multiple functions as arguments to a function the same way we pass in one function that I've been calling F to abstract over some sort of computation if you had two different computations you wanted to abstract over it would make perfect sense to pass in have callers pass two different functions。

 So that's the first。We can do with first class functions we haven't seen so far。

 Another one is we can put functions in data structures in topples or lists or records。

 and I'll show you an idiom that uses that later in this section of the course。

 but we're not going to do it quite now because we want to have some other features and study some other things first but two things I am going to do in this segment are have functions return other functions as results just a silly example to show you how that works。

 and then we're gonna to write a higher order function over a data structure that is not a list that's actually one of our own data type bindings so let's do the returning functions first and how about I just show you the code to start with So here is a function that actually takes a function and also returns a function So it takes in an argument F and it calls f with7 that's how I know it's an argument So in fact。

 for this part to type check I can tell you that this function overall has to take in an inarrowbo that that needs to be the type of F right。



![](img/ff82586d67b9029a9545be821e858c34_1.png)

But then if you look at the then branch in the else branch， in each case。

 it returns a function that turns out an anonymous function。

 although you could have any expression there that evaluated to a function and in both cases。

 since we know then and else always have to have the same type， we have functions of the same type。

 and in fact， this function always returns in in arrow int。

 So the function binding for double or triple defines a function that takes in an int arrowbu and returns an int arrow int。

 sorry about that。So let me show a couple uses of this here's I'm going to write down an expression that's going to end up returning the first function that given x returns two times x。

 so I'll bind this to the variable double if all I have to do is call double or triple with some argument that will cause f of 7 to evaluate to true。

 so there's any number of them， but how about x minus3 equals4。Okay， if I call that。

 I'm gonna end up getting the double function back。 Notice that double is not a number。

 It's a function because double or triple returns a function。 We could take that and then call it。

 But or we could take another call to double or triple， maybe something that returns false。

 like fun X X equals 42， that will not return true and applied to 7。

 that we could just take that entire expression， which will end up being the function that takes its argument and multiplies it by3。

 And if I call that with three wound up with three times 3， which is 9。Okay。

 so how about we trial that out real quick。 use generalizing dot SmL。 And sure enough。

 double or triple is just about the type I told you。 We'll get back to that in just a second。

 Dole is indeed an into arrow in。 And to make sure it's the function we think it is。 Yes， indeed。

 double of4 return 8。 And this last expression I wrote down did indeed evaluate to 9。

Alright so now the only remaining thing I want to talk about here is how I said the type of double or triple was this。

 take an inbu return in int arrow int and the repple said this type it just left off the parentheses around the result type It always does that。

 The repple never prints parentheses that does not have to and it turns out that those parentheses are optional。

 So to see that let me show you the general rule which I have down here at the bottom of this slide。

 when you see a type like with multiple arrows like this like T1 arrow T2 arrow T3 arrow T4。

 the implicit parentheses are always on the right So this for example would be a function that takes a T1 and returns another function that takes a T2 that itself returns another function that takes a T3 and then returns a T4。

 So when you're first seeing functions that return functions you really wish the repple would put in those parentheses。



![](img/ff82586d67b9029a9545be821e858c34_3.png)

For you， it's not going to， so you have to put them in yourself and your head and you get used to this fairly quickly。

 and then you end up liking， in fact， the conciseness of leaving off the unnecessary parentheses。

Right， so that was functions returning other functions。

 Now let me remind you that higher order functions are not just good for numbers and lists。

 They're a great way to process any sort of recursive data structure where you might want to do the same sort of recursive traveral with many different possible computations。

 So for an example of that， let me go back over here and scroll down， I have our old friend。

 this data type binding for arithmetic expressions and suppose I gave you a homework problem like given an X one of these things is every constant in it and even number you could write that recursive function。

 but suppose I had another homework question that said is every constant in it less than 10。😊。



![](img/ff82586d67b9029a9545be821e858c34_5.png)

And you could write that as well。 but it would be very， very similar。

 And if you had a bunch of these traversals that where all of the form is something true of every constant。

 it would be a great idea to abstract that kind of traversal。

 that kind of processing of the data into a higher order function。

 So let me show you how many we might do that。 I might write a function true of all constants。

 And it's going to take in a function in an E。 and it's going to say does F return true for every constant。

 So it's a lot like a filter in the sense that we're going to call F on every constant in here。

 but it's not a filter。 It's going the whole thing is going to return true or false。

 So if our entire expression is a constant， then I just want to call F on that constant。

 and all the other cases are just recursively calling true of all constants on the sub expressionpresss so that we can find all the constants。

 And this is the sort of thing that's fine to write out once。

 but it would be a pain to write it out over and over。😊，again。

 for all the different questions we might have about the constants and expressions。

 so it's great that we're abstracting it into a higher order function that then we'll be able to use multiple types。

 And I think that's right。 And then it's such a pain to write this out。

 I'm even going to copy and paste just a little bit and write multiply there。😊，And now。

 if I wrote this once and I wanted to write the function that I started with all even。

 take an expression are all the constants in it even， then I would just say true of all constants。

And pass in a little function that asks if the argument is even。And call that with E。

Let's see if I got all that right。

![](img/ff82586d67b9029a9545be821e858c34_7.png)

And I at least got the types right， all even is indeed a function that takes in an X and returns a bo。

 yes or no， are all the constants even。True of all constants is one of those higher order functions that has a nice type that really kind of explains a little bit what's going on。

 although not completely， you still need documentation for the function。

 it takes in an X and an int arrow bo because we know that we take that function argument。

 we apply it to constants and then the entire thing， the result type is bo， yes or no。

 the and also is combined to return true or false based on whether all the constants are true。

 according to this int arrow bo argument。So when you have these functions that have return type bull like this that process some data。

 I like to call them prediccateates， it's a nice mathematical world。

 a predicate is something that returns true or false for something。

 and this is an example of a higher order predicate， it takes in。

 it abstracts over that computation it says give me any inarrow bull and I'll give you a predicate that uses that inarrow bull。



![](img/ff82586d67b9029a9545be821e858c34_9.png)