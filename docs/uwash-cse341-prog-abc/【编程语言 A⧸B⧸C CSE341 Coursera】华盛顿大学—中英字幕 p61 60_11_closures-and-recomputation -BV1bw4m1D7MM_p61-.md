# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p61 60_11_closures-and-recomputation -BV1bw4m1D7MM_p61-

In this segment， I want to show how we can use our understanding of lexical scope to avoid unnecessary recomputation of things when we're using closures。

So here's what we know。We know a function body is not evaluated until the function is called。

 That's not even relevant to lexical scope。 That's the way functions and methods work in every language。

 You don't evaluate the body until you make the call。

We also know that the function body is reevaluated， if you will。

 every time the function is called using the arguments for that call。

But we also know that a variable binding evaluate its expression once when the binding is evaluated。

 not every time the variable is used。These are three things we've definitely seen， Def used。

 And if you take a minute to understand exactly what's being written here。

 you probably understand those three things as well。Now。

 I want to put those three things together to point out that with closures。

 we can use these things to avoid repeating any computation that you would naturally put in the function body。

 but is not actually using any of the functions arguments。 This can improve performance。

 It can make your code a little longer。 it can make it more or less readable depending on your preference。

 but it's a good example that helps emphasize the semantics of how functions and function closures work。

So let me show you the example I'm going to use to demonstrate this first I just have our old friend。

 the very famous high order function filter， no change there。

 and now I'm going to use filter with this function here， it takes in a list of strings。

 X's and a string S and it returns another string list， so this has type string list。

 our string arrow string list okay。

![](img/5499761b6a70aa93ab096d73efa35185_1.png)

And what it does is it filters out all the strings that are longer than。S。

So all we're going to do is call filter with X's for the list and with this perfectly reasonable anonymous function taken in X。

 that'll be an element of the list and ask， is its size less than the size of S。

 if it's strictly shorter then we'll have it in our output and if not， we'll filter it away。All。

There is nothing wrong with this。 This will produce the right answer。

 but it turns out that we are going to recompute the size of S。For every element of the list X's。

Because。Filter is going to call this function one time for every element of the list。

 And every time we call it， we compute the size of x， which we need to。

 X is changing every time and the size of S。 But that's an unnecessary recomputation。

 The size of S is not going to change。The way to fix that is， as we see in the second example。

 let's just create a local variable that holds the size of S。

 call it I and now in our anonymous function， just ask， is the size of x less than I。

This will produce exactly the same answer， there's nothing any caller can do to tell whether we use the first version and the second version。

 except to notice that if our list is very long and or if the length of s is very long。

 we could see a performance difference。So that's exactly what I wanted to show you and notice we need closures here。

 if we don't have lexical scope， if we don't store with this closure。

 the environment where the function was defined， we're not going to be able to use this variable I。

 so this is yet another example of where closures and lexicalco are a very natural thing。😊。

So I wanted to show you this that it actually works。

 but it's a little hard to do because you can't see the difference in all shorter than one and all shorter than2。

 So for the purpose of showing you the difference， how we put in some print statements。

 so we can see where things happen。 So I haven't done this with you before。

 but there is a function print in M。 it takes a string and print it out。

 there's also this semicolon operator， when you use it as an expression in general。

 and we put this in a comment here。 if you have E1 semicolon E2， it does E1 throws away the result。

 then does E2 and that's the result for the whole thing in functional programming。

 you don't need this sequencing very often because what's the point of performing a computation that wouldn't have assignments or side effects。

 if you're just going to throw away the result。 but printing is a good example where it does have a side effect and that's what we're actually trying to do here。

And similarly， let us put in a print before this call。

 So my idea here is to print one exclamation point before any time that we call string dot size of S。

 So， in fact， let me change this up here。 I like it a little better。 if I put it right here。

 So you can see it really is related to the size of the string S。 Okay。

 so now I have my two functions。 And now down here， I have some。Testing code。

 where I had the prints commented out。 So what it's going to do is it's going to print with all shorter than one。

 Then it's going to call all shorter than long on a length four list with this string and then all shorter than two on the same list and the same argument。

And if we just run this。So use closures and recomputation。

 It's going to end up doing those print statements before the other stuff from the Reel。

 as soon as I fix my parentheses here somewhere。Yes， one， too many there。呃Or。



![](img/5499761b6a70aa93ab096d73efa35185_3.png)

四。Try it that way， yep。Good， and we see that with with all shorter than one。

 which was the version that did not use the local variable。

 we got four exclamation points for our length four list。 But when we called all shorter than two。

 we only did this let binding a single time。Once when we computed the size of S。

 and even though we called this function four times， we looked up I four times。

 but looking up I just returned， I think，3， the length of that list。

 there's no recomputation when you look up a variable。

