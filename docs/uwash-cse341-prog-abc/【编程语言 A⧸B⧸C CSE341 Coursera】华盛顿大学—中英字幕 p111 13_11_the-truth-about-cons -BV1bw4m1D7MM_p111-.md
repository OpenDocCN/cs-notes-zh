# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p111 13_11_the-truth-about-cons -BV1bw4m1D7MM_p111-

In this segment， I want to continue studying how rackcet is a dynamically typed language by telling the truth about this cons primitive that we have been using to build lists。

 and that truth is that we can also use cons to make a pair。 In fact。

 what cons really does is take two arguments and make a pair。

 and in racket as is common in dynamically typed languages。

 all a list is is some number of nested pairs that ends with the empty list that ends with null。



![](img/e61c5f10378cf31aa61a9087ccc87a66_1.png)

So it's probably easiest to see that by just writing some code or using some code that uses this feature。

 So on this first line here， where I'm defining this variable PR。

 this is just a pair with one in the first position and in the second position。

 another pair that holds true and high。 So this is not a list。 This is the sort of thing that in ML。

 we would have written as one comma true comma high。



![](img/e61c5f10378cf31aa61a9087ccc87a66_3.png)

Sppelling true correctly。 But in racket， we write it like this with cons because we use cons to build a pair instead of comma。

 And we can see how this will print in the repel by just writing PR。

 And you see that what it actually does is it looks just like a list except it puts this dot before the last element that says this is not a list。

 This was the value that you get from using cons with one。

 and then one more pair of cons with true and high。

But let's compare that to the variable in the next line list。 So there I also use cons。

 which builds a pair from one and then another cons。

 which builds a pair from true and then another cons。

 and then the last one is the string high and null and that does make a list because a list is just some number of cons is where where in the cutter of each one in the second position of each pair。

 you have another cons until you get down to null until you get to the empty list。

 So that is what I mean by lists are just a particular kind of nested pair。



![](img/e61c5f10378cf31aa61a9087ccc87a66_5.png)

So once we understand this， we see that cons just builds a pair in racket it's common to call them a cons cell。

 and the way you access the pieces of a con cell is with car and cutter。

 so it turns out that car is really like MLs hash1 and Kudter is like ML's hash2。

And that is all that is going on。 So given our pair value， which remembers just nested pairs。

 which print slightly funny， if I take the cutter of the cutter of the pair。

 that gets me the string high。 It's the second component of the second component。

 But if I had my list。😊。

![](img/e61c5f10378cf31aa61a9087ccc87a66_7.png)

And I said， cutter of cutter。 sorry of list。 Well， then I get a one element list back because the cutter of the cutter of list is this pair of high and no。

 If I wanted the actual high， I would have to take car of that because if you take car of a pair。

 you get a string high。

![](img/e61c5f10378cf31aa61a9087ccc87a66_9.png)

![](img/e61c5f10378cf31aa61a9087ccc87a66_10.png)

By the way， sometimes in racket we find ourselves writing car of Kter of Qter and for a long time in racket and before its scheme there's a bunch of built-in library functions that combine this so you can use caditer and that is how it's pronounced and all that it is is there's a built-in function kar that takes an X and returns car of Qter of Qter of X。

 we could have defined this ourself but it's predefined for us in the standard library。

So now we know the difference between lists and pairs。

 as you might imagine we have built in functions for asking do you have a list or a pair。

 so if we ask is PR a list， the answer is false， the only things that are lists are the empty list。

And cons is where you eventually get down to the empty list。On the other hand。PR is a pair。

 Anything built from cons is a pair。 And if we do ask about list。LST， that variable， that is a list。

 and it's also a pair。 So here I'm just using the and primitive where I can ask a bunch of questions。

 I'll get the result true if they're all true。So that is our introduction to pairs versus lists。

 I should warn you that there are a number of built-in functions like length。

 which works just fine on lists， if I pass it a list with three elements， I get three。

 but if you try to pass it something that's not a list， even if it's built from cons。

 you get an error message this error message is introducing a little bit of terminology。

 sometimes when we want to emphasize this distinction， we say that lists like LST are proper lists。

 whereas something like pair， which is built from cons， but doesn't end with null。

 we would call an improper list。Okay， so that is the code I wanted to show you。

 Let's go back quickly to the slides and ask， why do we allow this， Why does rackcet have this， Well。

 we know pairs are useful， They were useful in M。 And if you're in a dynamically typed language that isn't going to have a type checker that distinguishes lists from pairs then why have one kind of way to build a pair and another kind of way to build a list。

 let's just use the same thing in rack's case cons for building both。 So unlike in M。

 we don't need the comma for building a pair and the colon and colon for building a list。

 let's just use the same thing for both and programmers will just have to keep track of which things are proper lists and which things are not。



![](img/e61c5f10378cf31aa61a9087ccc87a66_12.png)

Now， as a matter of style。If you have a collection of unknown size。

 I don't know how many numbers I need to pass to a function or something like that。

 You really should use a proper lists。 That's the convention。 That's what we want。

 put null at the end of your lists but if you really just need a quick pair or a triple I just need to hold three things then a pair or a pair with another pair inside of it is perfectly fine we don't have triples built in racket。

 you really do have to say something like let me just go back here。

 cons of one onto cons of true onto high that would be a fine way to build something that is like a triple。

 although it's really a pair with one thing in the first position than in another。

 we could have just as well done it this way， although this is a different data structure and it will print differently。

 excuse me one too many parentheses there we go and this shows that we have an improper list we have a pair that's what this dot shows with high in the second position and the pair one and true in the in the first position and we could get the true out for example。



![](img/e61c5f10378cf31aa61a9087ccc87a66_14.png)

![](img/e61c5f10378cf31aa61a9087ccc87a66_15.png)

let's see， let me first define this to a variable， so it's easier for you to see what I'm doing。

And then just say how about the cutter of the car of x， and that will be that true。

So this is perfectly reasonable when you just need a small number of things。

 but as we'll see in the next section， racket has some support for defining our own each of types。

 and I would argue that's even better style than just using cons。

 which is hard to keep track of how you've organized things and where things are defined and as we saw in the repple as I was playing around with this the list question mark predicate built into the language。

 returns true for proper lists including the empty list， but not it returns false for improper lists。

 whereas the pair primitive returns true for anything made by cons。

 and so that includes all proper lists except the empty list and it also includes any sort of pair。



![](img/e61c5f10378cf31aa61a9087ccc87a66_17.png)