# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p43 42_15_nested-patterns -BV1bw4m1D7MM_p43-

In this segment， I want to start talking about nested patterns。

 This is going to generalize everything we've been learning about pattern matching by do a very simple thing。

 which is letting us put patterns inside of other patterns and then extending our definition of pattern matching to account for that。

So it turns out that we can nest patterns as deep as we want everywhere we have been putting variables and patterns。

 we can actually put other patterns。 This corresponds to the idea that when we're making expressions。

 we can always put nested expressions in a way we want we don't have to write x plus Y we can write expressions in those positions we're going to be able to do the same thing with patterns and what this will let us do is avoid hard to read case expressions that have other case expressions inside of them and instead let us write some very elegant and easy to read programs So it turns out the full meeting of pattern matching is going to be a recursive definition that's going to take the idea of a pattern that can contain other patterns and a value that can contain other values and see if the value has the same shape described by the pattern and if so bind variables to the right parts but I think it'll be easier to see several examples over the next couple segments before we get to that precise。

Again， recursive definition。

![](img/29b20e98d134a1ec54c0b83da4d72572_1.png)

So what I want to do in this segment is show one nice example which relates to zipping and unzippping so to explain what zipping and unzippping is。

 I have written a function zipip3 and it's reverse。

 it's inverse unzip3 that work like the following if I call zipip3 with a triple of lists so three arguments each of which was a list say a list of integers although it turns out this function is polymorphic what I get back is one list containing triples so it went from three lists to one list of triples and what it did is it put corresponding pieces together。

 so in the arguments the first elements here are14 and 7 and in the result the first element is a triple of14 and7 similarly we then see25 and8 and then3。

6 and9。And unzip does the reverse。 It takes a list of triples and returns three lists where each list contains first all the first positions from the tuples then all the second positions from the tuples and then all the third positions from the tuples。

 So by the way， the reason why this is called zip and unzip is that it acts a little bit like a zipper like on your shirt or you know on a bag or something。

 because zip takes these separate things and puts them next to each other。

 and unzip takes something that was all together and separates it out。

 I wouldn't look at your zipper two closely， though。

 because when you actually zip the teeth do not end up next to each other。

 they end up adjacent but the intuition is right。 Okay so that's what I want these functions to do。

 Let's see how we might implement them。 And to give you some contrast here。

 let me start by showing you how we would do it if we didn't have pattern matching。

 So here is one way to zip together three lists。😊，It's a function using our old features。 Old zip3。

 It takes in three arguments， L， L and L。 And if they are all empty。L1 is null。 L2 is null。

 L3 is null。 Then let's return the empty list。Else， if any of them are empty， aha。

 our lists don't have the same length， and I'm gonna to call that an error。

 and I'll raise a runtime exception。 I'll show you in a few segments how to raise exceptions。

 but this is how you do it。 I've declared an exception up here and I'll raise it。 Otherwise。

 I have three nonempty lists。 If I have three non-empty lists。

 let's create a topple out of the head of L1， head of L2 and head of L3。

 and cons that onto the result of zipping tail of L1， Ta of L2 and tail of L3。 Okay。

 so that's zipping。 I prefer pattern matching。 This is pretty easy to get wrong。

 you could easily miss some cases， you're getting no help from the type checker。

 But if you go to use pattern matching。 the way we've been using it so far。 It's frankly。

 a bit of a mess。So here is a version that uses pattern matching。And let's see。

 So let's first deal with the case that all three lists are empty。 Well。

 I'd have to pattern match on L1。 and then if it's empty， CFL2 is empty， and then if it's empty。

 CFL3 is emptyha if I get here then all three lists are empty and so I should return the empty list otherwise L3 is not empty but L1 and L2 are so I should raise an exception。

 otherwise L1 is empty but L2 is not and I need to raise an exception Otherwise L1 is not empty。

 So let's pattern match head1 and tail 1 and then if L2 is empty， then raise an exception。

 and you see where this is going。 I'm exploring all possibilities of empty and non-emp rather than the convenience up above of and also an or else。

So it turns out the fix for this is not to abandon pattern matching。

 but to use the fact that patterns can appear inside of other patterns。

 so now let's look at how I like to write zip3。Here is a nice concise function， Z 3。

 It takes one argument just like every function in ML。

 let's call it list triple and call it anything you like。

 and let's pattern match on this triple of lists， and let's consider three patterns。

The first pattern is this one。 This is a pattern where I have a pattern for a topple with three patterns for lists inside of it。

And what this is going to match is any value that is a triple of three empty lists。

 So if list triple is all empty， then this pattern will match and I'll return the empty list。

Now let's look at the next pattern。This pattern also matches triples， here's before the first comma。

 before the second comma， here's after the second comma。

Each thing in it has to be a non-empty list why， because this is a nested pattern that matches against non-empty lists just like this one is。

 and this one is so the overall pattern will only match list triple if list triple is something that is a triple containing three non-empty lists and if it matches I'll bind six variables Head1。

 tail 1， head2， tail2 head3 and tail3 Head1， head2 and head3 will be bound to the beginning elements of the three lists and tail  one。

 tail2， tail3 to the tails of the three lists and what I want to do over here is the very elegant call cons with the triple made from head one。

 head2 and head3 recursively called zip3 with tail one。

 tail2 and tail3 so here is my pattern if it matches here is my expression and it actually looks like I'm zipping it up。

 create a tuple。Out of head1， head 2 and head 3， recursively zip 3 with tail 1， Ta 2 and tail 3。Now。

 that does not cover all the cases。 I've covered the cases where everything is empty and where the three elements are non empty。

 Here's a new kind of pattern。 underscore， underscore matches everything and doesn't find any variables。

 And it turns out for zipping and all the other cases， I just want to raise an exception。

 So if the first pattern doesn't match。 And the second pattern doesn't match。

 Then I want this third case。 The type checker will warn me that I want this case because my first two patterns don't cover all the possibilities。

 So I really like writing programs like this。 zipping is one great example。

 There are other examples that work as well。 And for this segment。

 let's finish up with unzippping and then I'll show you some other examples in the next one。

 So in unzipping， I want to take an argument， which is already a list of triples。😊。

And I want to return three lists。So now my pattern matching is going to be a little bit simpler if this argument list is empty。

Then I want to return three empty lists。 That is how you unzip the empty list。

 You return three lists， all of which are empty。Otherwise。

 I want to pattern match against the non emptyty list。

 Now we used to just do this as something like head colon tail or X colon x's，😡。

But what you can do is you can nest these patterns as well。 You can say， sure。

 I want to pattern match。The rest of the list against this Tl variable has nothing to do with the tail function。

 I'm just shadowing it with a Tl variable， but I want to match the head of the list against this each of pattern against this tuple pattern。

 So if this pattern matches， then a will be the first component of the head of the list。

 B will be the second component of the head of the list。

 then C will be the third component of the head of the list and tail will be bound to the rest of the list。

 These are the only two possibilities I have to account for because any list of triples will either match this pattern or will match this pattern。

 and the type of unzip3 is going to require list to be a list of triples so once I bound these four variables。

 let's look at this expression。 let us recursively call unzip3 on the tail。

 that's going to give me back three lists。 Let's use ordinary each of pattern matching to bind those three list to L1。

2 and L3。 And now I'm basically done because I have the three lists for unziping the tail。 I have A。

 B and C for the three components of the head of the list。

 And now I just want to return the triple expression that's a cons on to L1， B cons on to L2。

 C cons on to L3。 And now using the idea of nested pattern matching I in what less than 10 lines of code written elegant and concise。

 easy to read，ping zipping and unziping for three lists。

 This is a bit of an advanced example for nested pattern matching。

 but it uses all the features that I want to show you。

 then the next segment I'll show you a couple other common situations。

 Common idioms were nested patterns are extremely useful。😊。



![](img/29b20e98d134a1ec54c0b83da4d72572_3.png)