# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p16 15_05_functions-informally -BV1bw4m1D7MM_p16-

Okay， in this segment we're going to start studying functions。 These are a new kind of binding。

 so we're going to change our program definition of program to not just be a sequence of variable bindings。

 but to allow both variables and functions。 If you haven't heard of the term function。

 it's a lot like a method in an object orient language。

 this is something that's going to take arguments， compute some result and return that result。

That's all it does。 So it's in many ways simpler than a method。

 And we're always going to call these things functions。

 So why don't I just flip over to Emax here and show you a first example about it。

 I write a little function for exponentiation or raising something to the power of something else。

 So here is most of what I need to write。 Okay so I have the keyword fun。

 the name of the function I'm defining Pu。 The arguments it takes here， X and Y separated by commas。

 I've written their types with a colon and then the type name。 then in equals。

 and then I have my function body。

![](img/f157940044633ba984f570e2671906bf_1.png)

Okay， so that body can just be any expression I want。

 And what happens when you call the function is we are going to evaluate that expression。

 and then the result will be the result of the function。 So for exponentiation。

 what I want is something like a conditional expression that says if y is 0， then one otherwise。

 how about x times。This other expression， which is to call the p function with x and y minus1。

 and that will work as long as y is greater than or equal to0。

 and I'll make no attempt to be correct for negative y So this is just an example。

 So this is a program。 This can be included in my sequence of bindings。

 I could have a v binding before maybe afterwards I could have another function binding。

 How about something that takes its argument and cubes it。

 so I could define this as x times x times x or I could use any previous binding sincell be in my environment。

 and I could instead implement this as pu x3， So the body of this cube function is itself a function call that calls pu with x。

 which is the argument to cube and the constant 3。so I could use these functions。

 I could say v 64 that should just equal cube of4， don't actually need these parentheses。

 but it looks a little more like other languages if I put them in at least for now。

 or I could have something that uses more nested expressions like you can call a function with an expression in which case I'll evaluate this two plus 2 to4 and then pass four as the second argument to Pu here I could add another 16 and another 8 and another two。

You could even have nested calls if you wanted。 So。

 you could say power  to comm 2 in there and so on。 when you want to test something out。

 just like always， go over here to the repple。 We can say use functions。Dot Sml。

See all of our bindings there。 You'll notice that pal and cube print differently than variable bindings in terms of the value。

 they just say I'm a function。 We don't print out the body of the function or anything。

 the repel will always just say here is a function and here is its type。

 So you see with P that it has type int star int arrow int。

 So the way function types are written in M is we write down the types of the arguments separated by a star。

 So it takes two int arguments int star int。 and then a hyphen and angle bracket and arrow and then the result type。

 which is an int。 notice we didn't have to write down that result type M figured it out by looking at the function body that conditional that we had up here。

 and realizing that if x and y have type int， the conditional has the have type int and so the function when called with two int will return an int。

Similarly， cube is a function that takes one int and returns1 int，64 and 42 are as usual。 And we can。

 you know， try things out at the。Repple now， so we could cube 7， and we would get 343 and so on。

 So that's the informal idea of functions。 Let me make a few points here back with the slide。

 since this is a new thing we're learning。 The first thing is that the body of the P function itself can use P。

 So that's how we implement recursive algorithms， as we did here。

 So all this is showing is that inside a function body， you can call the function itself。



![](img/f157940044633ba984f570e2671906bf_3.png)

There's a few gotchas when you start writing things out。

 we have all new sources of potential error messages。

 especially if you leave that colon off between the name of the variable and the type。

 or if like in other languages you try to write int X instead of X colon int。

 all of these things are syntax errors and you're going to get error messages as a result。

I would also point out that when we wrote out those function types in the Reel。

 we saw that P had type int star andt arrow int， that star is different than the star for multiplication so it's just a reuse of the same character in expressions。

 star means multiply in types， at least as we've seen so far。

 it's just separating the types of multiple arguments。And finally， just like variable bindings。

 function bindings can use earlier bindings in the file。

 but they can't use later bindings in the file and that's again just ML's rule so any helper functions you want if you wanted to find one function like cube in terms of another function like PAO。

 then you have to put cube second Now this does raise an interesting question what if you had two or three functions that all wanted to call each other there would be no good order to put them in and I'll show you in some future segment some special support in ML for that case of mutual recursion。

If you're not yet comfortable with recursion， hopefully you've at least seen it before。

 you will be soon on your first homework assignment。

 pretty much every function you write will be recursive。

 and we're going to see a bunch more examples so don't panic if the algorithm for pal looked a little too magical。

 but there's really absolutely nothing magical to it。

 so let me flip back here and just show you this pal function The reason why we can define PA in terms of pal。

 there's nothing circular here。 what we did is we defined raising something to the wife power in terms of raising something to the y minus one power and that is a perfectly reasonable definition a recursive call is solving a simpler problem。



![](img/f157940044633ba984f570e2671906bf_5.png)

And if that simpler problem is that y is zero， then we don't use recursion at all。

 and we just return the answer1。 So we'll get very comfortable with this idea as we move forward。

 And in M， we're always going to use recursion for these sorts of things。

 If you're used to writing things like power with while loops or for loops。

 we're not going to use them。 they often obscure what are simpler， more elegant algorithms。

 and recursion is more powerful。 So often while loops and for loops are more convenient or the idiom and many programming languages in many programming languages they're more efficient but anything you can do with a loop。

 I promise you you can do with recursion and we're going to focus on that approach in M and really most of the programming we do in the class。



![](img/f157940044633ba984f570e2671906bf_7.png)

![](img/f157940044633ba984f570e2671906bf_8.png)