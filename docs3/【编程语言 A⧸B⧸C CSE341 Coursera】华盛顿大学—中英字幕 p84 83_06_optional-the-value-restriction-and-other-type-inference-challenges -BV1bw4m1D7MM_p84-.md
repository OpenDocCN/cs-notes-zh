# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p84 83_06_optional-the-value-restriction-and-other-type-inference-challenges -BV1bw4m1D7MM_p84-

I want to finish up our discussion of type inference with a few more topics that are necessary to finish the story。

 The first issue is that type inference for M， as I have shown it to you so far， is too lenient。

 it would actually let some things type check that we really should not type check。

 I want to show you that and it's related to the value restriction that came up once before when we were studying partial application。

 and then I just want to briefly point out that M is really in a sweet spot。

 the type inference works very well in M。 but if you tried to make the type system either more permissive or less permissive。

 type inference would become more difficult to reason about。 Now， in my view。

 these are important for finishing up the story。 but the topics are a bit more advanced than a bit less elegant。

 So I'm willing to say we will not ask exam questions about these topics。

 And since there are no more homeworks on M that means it's fine to treat this segment as optional。

Ok。So as presented so far， the ML type system is unsound。 What do I mean by that。

 The type system is supposed to prevent certain things。

 like never trying to add an int with a string。And as I've shown the type system and type in friends so far。

 you would be able to do that， and so it's unsound。

 it has an error in it as I've shown it to you so far。

 so I'm going to show you the problem and then how ML fixes that problem。

So it turns out it's a combination of polymorphism， those type variables， and mutation。

 and here's the shortest example I can think of that shows the problem。If on the first line here。

 we say v R equals ref none。Then using the type system as I've shown it to you so far。

 you would give R the type alpha option ref， it's clearly a ref， it clearly holds an option。

 and there are no additional constraints， you could hold an option of anything because none doesn't have enough data in it to say what kind of option should be in that RE。

But now once we give our the type alpha option ref， we're in big trouble。😡，Because colon equal。

 the assignment operator is essentially just a function that takes an alpha ref and an alpha and returns unit for any alpha。

So if I just use R here as though it's a string option ref。

Then I can assign into it a string option like sum of high。And then on the next line。

 I could use the dereference operator， the exclamation point， which has type alphapha ref。

arrow alphapha， and say， oh， I want that to now treat R as an int option ref。So I dereference it。

 I actually get back a string option because that's what's in there when I call Valive。

 I'll get a string， but the type system thought it was an int。

 and now I'm trying to add an int in a string。So that is the problem。

 and somehow if we want ML to have a sound type system， we need to fix this。😡。

So to restore soundness， we need a stricter type system that rejects at least one of these three lines if all three lines type check。

 we know that when we run it， we're going to have something happen that should never happen。Now。

 one's natural reaction is that you should make up some special rules for reference types and maybe not let references hold polymorphic things that they would have to have a type like intoption Ref。

 but not alphapha option ref。Now when we study the module system。

 which is one of the major topics coming up， we'll learn that this is actually impossible for the type checker to do because there will be ways to hide references and make them seem like there are other types。

 so I have some code here where I actually end up creating a function F that would have type Al arrow alpha F and will F's not ref right but it turns out there's a types syn inm here right above it。

 but in general it could be somewhere in the program that the type checker cannot see because of the module system and in fact when you make an alpha fo。

 you're actually making an alpha ref so if I called F with none。

 I would be in the same problem that I had above with the function ref。

So it turns out because of the module system， it doesn't work to make special rules for references。

 so instead we're going to restrict everybody just because references might be a problem and so this solution is called the value restriction and here's how it works。

When you have a vow binding， if you want to give the variable that you are introducing into the environment。

 a polymorphic type， then the expression you use for that variable has to be a value or a variable。

 it can't be something that computes a result。Now that might seem like a weird restriction。

 but doesn't come up too much， and it happens to solve the problem。

 even though it's not at all obvious that it would solve the problem。

You can see that it will make this first line not have the type we expect。😡。

So this is a function call。 Ref is treated as a function by the type checker。 None is an argument。

 Fun calls are not variables or values。 So we cannot give R a polymorphic type。 Instead。

 standard of M of New Jersey will give a warning about this and say。

 I can't give it a polymorphic type。 I don't know what type to give it。

 So I'm going to give it question mark dot x1 option ref。

 This is just some dummy type in here under the option ref。

 it's going to make R essentially unusable， and these next two lines are definitely not going to type check because you can't assign a string option into one of these and you can't read out one of these and pretend that it's an in。

 So that does actually take care of the problem。 So the general rule is if you want to give something a polymorphic type。

 It cannot be something that looks like a function call。

 It has to be something that looks like a value or a variable。Okay， so this has a downside。

 We've seen this before that if you have something else that would work absolutely fine。

 but it fails the value restriction rule， then you can't give over a polymorphic type。

 So the example I showed you before was a call to list dot map with a function here that does not constrain the type of X。

 So the type you would like to give to this expression and therefore to pair with one is alpha list arrow alphapha star int list。

 But that would violate the value restriction。 So you get an error a warning message。

 and these quote A's would be replaced with that same dummy type question mark dot x1。

And we've seen workarounds for this before， one of the simplest in this case is to go ahead and do a function wrapping。

 what I would normally call unnecessary function wrapping。

 but here it actually gets the thing to type check and get the type that we want。



![](img/b7b6b9661a6f2b0a8eb24b66144a00c8_1.png)

So I do have all the code over here， it's exactly the code I showed you。

 and so we have three times that the value restriction would refuse to give something a polymorphic type。

 dysfunction function body is fine， value bends are generally fine that just that these three do violate the value restriction and sure enough if I compile this as I already have up here at the top you will see three warnings referring to the line numbers where we have those issues and in all three cases we get these dummy types which make the results significantly less useful。



![](img/b7b6b9661a6f2b0a8eb24b66144a00c8_3.png)

Okay so that is our study of the value restriction and hopefully the last time we have to discuss it because I'm not a huge fan of it。

 although there really isn't a better solution， so it's one we've learned to put up with now I just want to talk about a couple other things with ML type inference that is that despite the value restriction that basic idea is quite elegant and fairly easy to understand it really only took us a couple video segments to get the hang of it。

What if ML did not have polymorphism？Then how would type inference work？

It turns out we would have a simpler type system， a more restrictive type system。

 and yet it would be harder to do type inference because when we wrote a function like list length。

 what type would you give it？You'd have to kind of pick one， and then it wouldn't be as useful。

 and it's not clear to the type inferencer what kind of list element you wanted to have for your list length function。

So you can do type inference without polymorphism， but in some sense it can be clumsier。

 it can be less obvious what to do。Let's think of a second example。 Now。

 we haven't studied subtyping in the course yet， but you may have seen it in another language。

 and we will study it later in the course。 but suppose certain expressions could have multiple types。

 So for example， suppose a triple like int star int star int could also have the type of a pair int star int。

 you could just forget that there was a third field。 that would be a form of subtyping。

 if we had that， that would be a more permissive type system， more things would type check。 And yet。

 just like when we had fewer things type check and type inference got harder now that more things type check。

 type inference also gets harder。 The reason is different， though。

 it's because when you have patterns like Val Y comma Z equal X。

We used to be able to look at that and say， aha x must be a pair， some T1 star T2。

But now we have to account for the fact that it has to be some tuple that has at least two fields。

 and it might have more。Now this can be handled， and depending on the details。

 you can have a language with this sort of polymorphism and still do type inference。

 but the types are often more difficult to infer， and it's。

 even harder to understand what's going on when you go to do type inference and you get a type error message back。

So that finishes our discussion of type inference， we've used ML as a great example of a language that does inference。

 ML is not the only language with inference， the details always differ by language。

 but it's pretty neat that you can have a statically typed language。

 even if you don't have to write down any of the types in your program。



![](img/b7b6b9661a6f2b0a8eb24b66144a00c8_5.png)