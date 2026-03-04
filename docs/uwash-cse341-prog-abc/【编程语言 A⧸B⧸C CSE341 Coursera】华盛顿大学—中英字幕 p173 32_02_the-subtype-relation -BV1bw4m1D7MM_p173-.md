# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p173 32_02_the-subtype-relation -BV1bw4m1D7MM_p173-

In this segment， we're going to give a very precise definition to subtyping and do it in a way that we can add a lot more flexibility to our type system without having to change any of the typing rules we already had in our programming language or have learned earlier in the course。



![](img/949318d97faa22917079f2c3b4d2d01a_1.png)

So this is important because a programming language already has a lot of typing rules and they're complicated and sophisticated。

 And if we had to make complicated changes to all of them just to support passing a record with three fields where we only needed two of those fields that would be annoying。

 We have great typing rules， for example， when you pass an argument to a function the type of that argument should equal the type of the function parameter。

 It's a nice rule it's easy to explain， we can implement it in our language。

 but that rule in and of itself is what in the previous segment did not let us pass something that we wanted to pass and that would do no harm。

 So the way we're going to fix this now is by adding just two things to our language。

The first thing we're going to add is a notion of subtyping separate from everything else。

So on the slides， I'm going to write T1 less than colon T2 to mean t1 is a subtype of T2。

 This does not have to be syntax in your language。 This is just a binary relation on two types。

 given two types T1 and T2 maybe one is a subtype of the other and maybe they're not and what we're going to have to do is come up with a definition of that relation just like the less than relation on integers is a binary relation takes two integers and either the left one is less than the right one or it's not we're going to define a relation on two types。

Now， once we have that relation， which we call the subtyping relation。

 now all we do to our programming language is we add exactly one rule。

 and it's the rule you see in blue here， it says if some expression has type T1。

And if T1 is a subtype of T2， then E also has type T2。 and that's the only rule we have to add。

 and everything will just work out。 For example， if x colon real Y colon real color colon string is a subtype of x colon real Y colon real。

 then anything of the type with three fields also has the type with two fields。

 and since it also has that type willll be able to pass it to a function that expects the supertype。

So we've really separated things out very， very nicely here。



![](img/949318d97faa22917079f2c3b4d2d01a_3.png)

Now we do want to do this carefully， There's a common misconception by people who don't actually work on programming languages that if you're making up a new language。

 you can do whatever you want because it's your language right and as we've learned repeatedly in the course。

 yes you have a lot of flexibility in language design， but if you do it wrong。

 your language doesn't work the way you expect， for example。

 dynamic scoping foreclosures is a terrible idea for lots of reasons。

The same thing is true with typing and subtyping rules that you can't just use whatever rules you want。

 at least not if you want your type system to actually accomplish something right back when we learned about static typing。

 we learned that the purpose of a type system is to prevent certain operations in the language we're studying for subtyping。

 the purpose is to make it impossible to ever have a program that type checks， but when you run it。

 you try to access a field of a record that is not in that record。

So it turns out that with just our typing rules from the previous segment， we have that property。

 we are sound for preventing bad record field aes。Now when we add subtyping。

 we want to make sure we stay sound if we define the subtyping relationship in a way that ruins the soundness of our type system。

 I would say we've done the wrong thing and there's a little saying about this in programming languages which is that subtyping is not a matter of opinion right either your subtyping rules break your soundness or they don't it's important to us that they not break the soundness。

So the key thing you have to reason about for not breaking it。Is this idea of substitutability？

So if T1 is a subtype of T2， then what we want is that any value of type T1 can be used in every way a value of T2 can be。

 So this is going to be true for our example with a record with more fields in the super type where we just have x colon real Y colon real。

 The only thing you can really do with that record， besides pass it around is get the x field。

 get the y field， set the X field， set the y field。

And you can do all of those things with something of type X colon real。

 Y colon real color colon string。 So the substitutability principle holds。 All right。

 So that's why this works。 and that's why that's a legitimate thing to add to our subtyping relation。



![](img/949318d97faa22917079f2c3b4d2d01a_5.png)

So without further ado， how about I add， I now define at least a preliminary subtyping relation。

 these are all things that I'm going to use to say that one type T1 can be less than another type T2。

😡，So the first thing is what we've been talking about。

 this has a name it's called width subtyping that you can take a wider record and make it a subtype of a slimmer record provided that the slimmer record has all field names and types that are in the wider record so that's the rule we have been talking about and you can do that Basically you can take your wider record and drop some of the fields。

5。😡，Here's another rule that maybe you didn't even occur to you。 We might need。

 How about I have two records that have the same fields and the same types。

 but they're not written down in the same order。Well。

 the order doesn't matter right you know when I'm writing down a record type。

 it doesn't matter if I say x colon real， y colon real， or if I say y colon real， x colon real。

 so we should let one record type be a subtype of another record type that just permes the order of the fields。

 doesn't change the types of the fields doesn't change what fields are there。

 but write them out in a different order。 and that's a very nice rule。

 It seems to clearly pass our substitutability test because you know we'll still be able to get and set all the same fields。

 my point is if you don't write this down as part of your subtyping relation。

 all sorts of programs don't type check that you really want to type check So it's a great rule to put in your subtyping relation。

And then we have two that kind of come along for free that every subtyping relation should have。

 but we should be explicit about them。 The first one is transitivity that if T1 is a subtype of T2 and T2 is a subtype of T3。

 then T1 is a subtype of T3 this should follow directly from substitutability if a value of T1 can be used a value of T2 and a value of T2 can be used as a value of T3。

 then a value of T1 should be usable as a value of T3 this is a nice rule to have because that way our other rules are rules that actually do something more interesting don't have to say everything all at once that if we want to think of subtyping as dropping a field and then reordering fields width and then permutation we can use transitivity to get it to work that way And finally one you might think is really weird it's called reflexivity it's a word from discrete mathematics or logic every type is a subtype of itself so T is a subtype of T for any type T and we don't really。

Need that so far， but when we see some other subtyping rules in particular。

 the subtyping rules for functions， which we'll get to shortly。

 it will be nice to have this rule because it helps simplify other rules in ways that we'll see。So。😊。

Summary， we have one new typing rule if T1 is a subtype of T2 and E has type T1。

 then E also has type T2， and then we have to define the notion of two subtypes being two types being subtypes of each other and this slide is where we made our preliminary definition these rules are all fine and an upcoming segments we'll try to add additional rules and see if we can do that in a sound way。



![](img/949318d97faa22917079f2c3b4d2d01a_7.png)