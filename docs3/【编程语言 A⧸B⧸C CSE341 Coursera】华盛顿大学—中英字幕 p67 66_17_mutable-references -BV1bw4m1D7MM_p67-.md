# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p67 66_17_mutable-references -BV1bw4m1D7MM_p67-

In this segment， we're going to take a brief break from closures to for the first time in the course。

 actually show you something mutable， show you an assignment statement。

 So I have certainly emphasized throughout this course that you do not need mutable data structures that they cause lots of problems。

 there are benefits to avoiding them that immutability is a great default。

 but I don't believe that there's always a need to avoid mutation。

 there are situations where what you are programming。

 the model of the thing that your computation is about has certain inherent updates to it。

 there are some state in the world， and that state needs to be updated for everyone who has access to that state to see when that's the natural way to think about your problem。

 then using mutation makes sense。

![](img/dd30551f5df29ea6a9191a5c3e15e2b6_1.png)

The problem with most programming languages is that they make everything mutable。

 So you have to worry that things should be changed。

 even when in your model of what the computation should be doing。

 there's no reason it should ever change。So ML does a nice job of supporting mutation。

 but not for variables， not for tuples， not for lists， for things you want mutable。

 you have to use a separate language construct called a reference。

And only the contents of references can be updated。

So I'm showing this to you now because the next closure idiom I want to show you。

 I'm going to use this in my example， so that's the reason for the ordering。

 you still do not get to use mutation on your homework。

 It's an important thing you need plenty of practice this mutation-fr programming and none of the things we are asking you to program。

 benefit from mutation or any easier to do if you're allowed to use references so you're not。😡。



![](img/dd30551f5df29ea6a9191a5c3e15e2b6_3.png)

Okay， so here is everything you need to know about these mutable references。

 There's a new kind of type T ref where T is any type。

 the same way T list is a type for any type T T ref is。

 So the type of a reference whose contents is a T。 So an int ref would have contents that are its。

We have three new primitives in the language functions we can use to use references。

 We make a new reference with the Ref function。 So this is on the left of an expression。

 It's a little confusing we reuse the same thing we used in the type。

 But the way this works is you evaluate E to evaluate。

 and then you create a new reference and the result is a pointer to that reference， if you will。

 It's a thing that refers to that reference。 So you know。

 have this thing whose contents are initially whatever eevalu to。Now。

 those contents can change because this is mutation。

We change the contents of a reference with the colon equal operator。

 This is our assignment statement， colon equal。 What we do is we evaluate E1 to a reference。

E2 to some value。And then we update the contents of the reference to that value。

 So the thing E refers to as its contents changed to be the result of E。In terms of type checking。

 perhaps not surprisingly， E1 has to be a T ref for some type T and E2 has to be a T。

 We don't allow the contents of a reference is type to change。 The type can't change。

 We have to replace one ant with another ant or one string with another string。Finally。

 if you want to read the contents of a reference as opposed to writing them or updating them。

 this is what we use exclamation point for， so many languages use exclamation point for negation。

 ML uses it for retrieving the contents of a reference， so we evaluate E to a value。

 it better be some T ref， and then bangang of that exclamation point of that。

 retrieves the T retrieves the value in the reference。



![](img/dd30551f5df29ea6a9191a5c3e15e2b6_5.png)

So let's see an example。 It's a silly example， but it emphasizes what is different about these things。

 So on the first line here， you see v x equals ref 42 that is going to go and create some new location whose contents can change。

 initialize those contents with 42 and return a reference an arrow in the picture over on the left to that thing。

 I didn't write the 42 in the box， but you should imagine that at this point we've return x is bound to this arrow that refers to this box that holds a 42。

The next line， v y equals F 42 that will make a new box。Initialize its contents to 42。

 The result of F 42 is that arrow pointing to it。 and then the variable Y now refers to that thing。

When we say v z equals x， while we evaluate x， we look up x in our dynamic environment。

 we get the arrow that it points to。 and so Z and x now refer to the same reference。

 they are aliases。 they both refer to that。 So when you see here， x colon equal 43。

 which is the next thing this file does。 this v underscore is just an idiom for do it。

 and I don't care about the result。Because the result here is not going to be bound any variable。

 So we say x colon equal 43。 Now this left box， o， pardon me， holds 43。All right。

 so on this last line， when we say bangang Y， we retrieve the contents over here， we get a 42。

 we retrieve the contents over here， we get 43， 42 plus 43 is 85。Notice that X。

 Y and Z all have type int ref。 They refer to a mutable location holding an int。

 You cannot apply addition to an int ref that doesn't make any sense。

 The only operations you can do in a ref are assignment with code equal and dere with exclamation point。

 So you can't write x plus1。 You have to write exclamation point。 X plus1。 that's keeping separate。

 the notion of a mutable location from the notion of an integer。 and that's a good thing。In fact。

 as I want to emphasize here， x is immutable。😡，The variable X， the variable Y， the variable Z。

 those always refer to the same reference they did when they were created。

X holds is bound to this arrow and will always be this arrow。😡。

It's the contents of the thing the arrow is pointing to that can change。😡。

So once you're using mutation， just like in any other programming language。

 you have to deal with potential aliasing， that is why when we assign to X。

 the result we get henceforth for exclamation point Z changes。Presumably， if you're using mutation。

 you want to think about stuff like that。 And if you don't want to think about stuff like that。

 don't use mutation。😡，Alright， so you should really think of these references as first class values。

 You can pass them around。 you can pass a ref to a function。 You can return a ref from a function。

 And for those of you more used to programming in other languages， Java C C plus plus whatever。

 you could think of a reference as a little mutable object， it just has one field。

 So since it only has one field。 Col equal updates that field。 exclamation point reads that field。

 We don't need to give a name to the field because references only have one。

 If you wanted multiple fields， you could have your reference， hold a tuple。

 And then you could update it to point to a different tuple。😊，It's not the topple that's mutable。

 it's always just the reference contents。😡，And those are mutable references。

 as I mentioned we will not use them very much in the course。

 but we need them a little bit for the next segment。

 so I thought I would show them to you a bit more generally。



![](img/dd30551f5df29ea6a9191a5c3e15e2b6_7.png)