# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p39 38_11_polymorphic-datatypes -BV1bw4m1D7MM_p39-

OkayIn this section I want to talk about how you can define your own data types that are polymorphic。

 so the reason why I'm doing this is I've previously claimed that the options and lists in ML aren't particularly special。

 that they are themselves just data type bindings and the only thing that's different is that lists have slightly special syntax where we have the colon and colon as a constructor in the middle and bracket bracket for the empty list。

 but that's not exactly true compared to the data type bindings I've shown you so far。

 because lists and options are things that take type parameters， so list is not a type。

 it's int list that is a type or string list or even int list list which is lists whose elements are lists whose elements are ins so list and option are not types thatre type constructors they' are something that take type parameters to produce types and we've also seen functions that may or may not be polymorph。

So a function like some list has to take a list of integers and add them all up to produce an int。

 but a function like my favorite append is something that works for any type alpha。

 and it takes a type alpha list and another type alpha list and returns an alpha list。

 And I just say alpha instead of quote A because that's the traditional way to pronounce that。

So it would be good language design to not have built in things like lists and options that can be polymorphic in this way and then have data type bindings that you can define that don't have this facility So it turns out that ML did the right thing。

 It lets you define your own and this segment is going to show you how to do that Now this is optional in the sense of I wanted to show this to you for completeness。

 but the homework is not going to require you to do this。

 and I'm just doing this to finish the story of how lists and options are not particularly special。

Okay so here's the syntax I haven't shown you yet， and that is that you can have one or more type parameters between the word data type and the new type level binding you're introducing so this first line here on the slide is exactly how options are defined in ML before your program starts running and it just says that option is not a type it's something that given one type alpha or quote a produces a type So int option is a type string option is a type and so on and then once we have that quote a。

 then we can use it in the types of data that our constructors carry。

 so in particular we can have some of alpha some carries whatever type this particular kind of option carries as its parameter。

Similarly， if we wanted to define our own length list， ignoring the special syndax in ML。

 we have one type parameter alpha and the cons case carries two pieces of data and alpha and then another list but you can't just write my list here that's never a type we say that the rest has to be another alpha my list so you can even do things with multiple type parameters so this last example here shows that it defines a particular kind of tree where I have two constructors。

 internal nodes and leaves and the leaves always carry something of type quote B or beta。

 the second Greek letter and the internal nodes always carry something of type alpha and then two other alpha beta trees so this is going to be a binary tree where all of the internal nodes can carry data of one type and all the leaves can carry data of a possibly different type So two type parameters alpha and beta can。

Be the same， or they can be different。so that's how you do it。

 I have a bunch of code associated here that you can mostly look at on your own。

 So I started by showing you some list and append over Ml's builtin list。

 So some list here is going to have type in list arrow int and the type checker will be able to figure that out because it sees that right here you're taking an element of the list X and you're adding it to something else。

 and so the elements must have type in。 The result type must have type in both because we have an addition here and because we have a zero here in this other branch and zero has type in。



![](img/5bc40e7587f50d59db0c6e49f3a4fc9f_1.png)

Aend， on the other hand。The type techcker can see that we don't need our list arguments。

 X's and Y's to have any particular type。 They have to have the same type because if you take an element of one and cons it on to something that has to have the same type because we return something that is wise。

 These two is better have the same type because you can't mix and match elements of different types。

 and so the type ends up being alpha list are alpha listarrow alpha list which says that calls can use aend with lists of any type。

 but the two types， the two arguments， X's and y's have to be lists with the same element type All right then I have the data type bindings I just showed you here on the slide。

 and then down here using our own polymorphic data type。

 this alpha beta tree I showed you or the leaves have one type。

 The internal nodes have data of a possibly different type。 I wrote three different functions。

 This first one， some tree runs over the entire tree adding up everything at every position。

So if you have a leaf， we pattern match on that here and we just return the data there。

 this I if you have an internal node， we add I to the result of recursively summing the left child and recursively summing the right child。

 these left and right fields of the data， and so everything has to have type int and so the type checker will indeed figure out if you run this code that the argument has to be an int comma int tree that only trees where both alpha and beta are int can be legal to pass through the sum tree function and get a reasonable answer。

This is a much more interesting function from the type perspective。

 although it's probably less useful， what it does is it also takes a tree。

 but it only adds up all of the integers at the leaves。 So if you look in the node case here。😊。

What the right hand side does is it just calls some leaves on left and some leaves of right。

 It doesn't actually use the data at that node。And so indeed。

 the type checker will notice that the legal types of trees you can pass to some leaves are anything where the beta is in。

And the alpha can be anything。 so some leaves can be polymorphic。

 It works for any kind of tree where beta is int， and then it returns an int。And finally。

 if you did it something even more general， like just count how many leaves a tree has。

 So now we're not using any of the internal data。 We're not using this eye and we're not using this eye。

 We just count by in the base case， we're turning one and in the internal node case。

Summing the number of leaves in the left and the number of leaves in the right。 Now。

 any kind of tree is a legal argument， and indeed the type of numb leaves will be alpha beta tree arrow in。

Okay so that's fairly fancy type system as I mentioned we're not going to get into our own polymorphic data types in homework2。

 but it's interesting to notice that the way we used the constructors and case expressions was exactly as usual。

 Nothing about the code we wrote was any different。

 Nothing about the evaluation rules were any different。

 the only difference is in the type checking where now the type checker has a much more interesting job of making sure the types are used consistently so even though a list or a tree may be polymorphic。

 you still have to you can't mix element types in a particular data structure and then how polymorphic your functions are。

 how many of those quote A's and quote B's appear in the type depend on how the data is used and that's why we see things like summing the elements of a list requiring a list of ints but something like a pen working for lists of any type。



![](img/5bc40e7587f50d59db0c6e49f3a4fc9f_3.png)

![](img/5bc40e7587f50d59db0c6e49f3a4fc9f_4.png)