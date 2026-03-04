# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p29 28_01_building-compound-types -BV1bw4m1D7MM_p29-

Okay， what I want to do in this segment is give a general way to think about how to build new types。

 in fact， this is going to be more general than even an ML。

 but we're going to be able to use this idea， these concepts to better understand what it is we've been doing in ML and what we're going to continue to be doing in the upcoming segments。



![](img/13bac50a4ff10365069a0e5e5cefffbe_1.png)

So the way I want you to think about all the types out there is that there are base types and compound types。

 so base types are things like ant bull unit cha realel that describe sort of the basic values in your language and then compound types are ways that you build new types with other types inside of them So tus are compound types because we can take any T1 and T2 and make a pair of a T1 and T2 lists and options are also compound types because we have a T list for some type T or an option type for some type T and in the upcoming segments we're going to learn new ways to make our own compound types。

 we're going to learn records and we're going to learn data types which are even more interesting。

But before we get there， I want to take this step back and basically tell you that in any programming language。

 there are really three fundamental ways to build compound types out of other types that are part of the pieces。

 And although these are not the standard names， I'm going to call them each of one of and selfreference。

 So when you build in each of type the entire idea to build a new type T where values of type T have each of some other collection of types。

 So if it were a triple with a T1 a T2 and a T3 that would be in each of type because values of that compound type have a T1 and they have a T2 and they have a T3。

Conversely， a one of type is a type where a value of the new type has either a tau1 or a tau a T2 or a T3 for some collection of types。

 I'll sometimes say tau， the Greek letter that's closest to T for types。

 It's all the same And the third way you can build a new type is with some notion of recursion。

 So if you just add each of in one of you can't describe things like lists or trees because values of a list type include other lists that are smaller。

 And so you need some way to say an int list is either the empty list or it's an ant and another int list。

 So you need that self-reference。 And what's remarkable is once your programming language。

 support some way to do each of some way to do one of and one way to do selfreference。

 you have an amazing way to describe a lot of interesting data in terms of types。

 And that's why pretty much every programming language has some way to build these kinds of compound types。



![](img/13bac50a4ff10365069a0e5e5cefffbe_3.png)

so in terms of examples we've seen， as I mentioned。

 two bowls pretty directly capture the idea of each of if you have instar bull that contains an ant and a bull。

Options really are a one of type， but they're a bit of a strange example because you either have something or you don't。

 So there's always this or involved。 So an int option either contains an int or it does not contain an int。

 That's an or。 There's no each of or and involved。And then when we create a list。

 it turns out it uses all three building blocks。 So an int list， if you just say it out loud。

 has all three concepts， An int list either contains an int and another int list so that's each of and self-reference or it contains no data and that's the one of idea and of course these things can nest arbitrarily to let us describe interesting shapes of data So there's an example here on the bottom of the slide where either we have some data or we don't。

 and that data is described by two things either a pair of ints or nothing and a list of a list of ints。

 which itself can be described in terms of each of one of and self-reference。



![](img/13bac50a4ff10365069a0e5e5cefffbe_5.png)

So where we're going with this is I'm about to show you another way to build each of types in ML。

 and that's going to be records， records are a lot like tus except they have named fields instead of a first position。

 a second position and a third position， and we're going to see there're so much like tuples that we can describe tus in terms of records using this important idea called syntactic sugar。

After that， we're going to see a way to build our own one of types。

 So if you look at that previous slide， we can build our own each of types withinstarbo。

 but for one of types so far， we only have options and lists。

 Ml has a great way to define our own types that maybe say either you have an int or you have a string。

 We don't have a way to do that yet。 And once we have such types we need a way to access the pieces and we're going to use what will probably seem very unusual to you。

 if you've only programmed in Java or C or Python before。

 and that's this thing called pattern matching， it's incredibly powerful and we'll get comfortable using it。

 even though it's not like anything you've seen before。

 and then much later in the course we'll get around objectoriented programming because you might be thinking wait a minute。

 I know how to program in Java or C plus plus I've never seen one of types。

 It turns out you have seen one of types。 but OOP objectoriented programming does them in a very different way using subclasses and subtypes。

 It's a very elegant way。 In fact， it's the exact。

![](img/13bac50a4ff10365069a0e5e5cefffbe_7.png)

![](img/13bac50a4ff10365069a0e5e5cefffbe_8.png)

opposite way that languages like M do it。 And once we've seen both。

 we'll be able to make that contrast。 And it's one of the most fun and general takeaway lessons from the course。

😊。

![](img/13bac50a4ff10365069a0e5e5cefffbe_10.png)