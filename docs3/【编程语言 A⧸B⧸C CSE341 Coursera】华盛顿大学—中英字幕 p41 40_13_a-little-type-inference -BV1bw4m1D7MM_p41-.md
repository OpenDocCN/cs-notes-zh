# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p41 40_13_a-little-type-inference -BV1bw4m1D7MM_p41-

In this segment， I want to talk a little bit about type inference and then we'll continue this discussion in the next segment about one type being more general than another we're going to study type inference a little later in the course and understand how ML actually does it。

 but I need to tell you a little bit about it now so that you're not concerned on your next homework if you're getting some types back from ML that might surprise you in certain ways。

So as I mentioned， once we learned how to pattern match on each of types in the second homework we don't want you to use the hash character。

 we don't want you to say hash2 or hash fo to get the fo field out of a record and conversely now in ML once we stop using the hash character we don't have to write down types on any of our function arguments anymore or on any of our variable bindings or anything else and it turns out these things are related that once you use pattern matching for getting the pieces of a tuple or a record the type checker can always figure out what the type of a function argument should be so let me show you how that works mostly by showing you code here are two functions we've seen before our old fe for summing a triple。

 take in a single triple x comma Y comma Z to pattern match against the three parts and sum them up or take in a record here with first middle and last fields bind to those fields x Y and Z and then concatenate them together。



![](img/7834e8c1865be0634db3c057bb7ceebc_1.png)

There' with some blank spaces in between。So if I just run this and load this up， we will see。

 as we've seen before， that the type checker can figure out that some triple1 needs to have type int star int star intarrow int you can tell it's a triple because it's x comma Y comma Z you can tell they have to be ints because x Y and z are added together Similarlyly。

 full name has to be a record with first last and middle fields and those contents have to be strings because in the body we can catnate them and then the result type of full name1 is of type string。

 So these patterns told the type checker， most of what it needed to know and then how the variables were used showed the rest。

So let me show you that if you use instead hash characters。

 the type checker does not have as much information。 Now， these versions。

 some triple2 and full name 2， which use hash characters。

 the old fashioned way will work and they will work just fine。

 So let me quickly go over here and just show you that that if I reuse them， they work just fine。

 we get the correct types for some triple2 and full name2。 But if I took out these types。

 And let me just do this for the first one here and try that again。

I now get a compilation error message。 Unresolved flex record need to know the names of all the fields。

 blah， blah， blah。 And the reason why the M type checker is complaining is it looks at this some triple。

 And it can tell the triple here needs to be a tuple with at least three fields where the contents are type in。

 But how does it know that there isn't a fourth position or a fifth position or a sixth position。

 It doesn't。 and every type system has certain limitations。

 and an M one of those limitations is you can't write a function that takes in both three tuples and four tuples。

 And so since the type checker can't figure out how wide the tuple is supposed to be。

 you get an error message。 And that's why this simply doesn't type check and why in homework1。

 we made you write those types down。Alright， so that's fine。 That's an advantage of not using hash。

 But now let me show you something that you may trip across in homework2。

 And so it's important that we tell you about it。 So here are a couple functions that don't use all the pieces that were pattern matching against So this function。

 partial sum adds together x and z and doesn't use y and similarly。

 this name function concatenates the first name in the last name but doesn't use the middle name。

right so if I told you on your homework， say to write a function of type int star int star int arrow int that indeed had the behavior of adding the first position in the third position you would probably write exactly this code and then you would save it and then you would come over here and you would run this and you would see that the type of partial sum is int star alphapha star int arrow int and you would say。

 oh， no， I want。An in star int star int arrow int。 And what I got was an int star alphapha star int arrow int。

 And what I want to tell you is that's okay。That sometimes the type checker is perhaps a little bit smarter than you are。

 And in looking at your functions， decides they are more general， more reusable than you expected。

 And indeed， if you look at this， it works just fine to call partial sum with three integers。

 It's a polymorphic function that works for a tuple where the middle position has any type。

 And indeed， we can call partial sum。With3 comma 4， comma 5 and get 8。

 But we could also call it with a string in there。 and that will also type check。

 It would not work to put that string in the last position。All right， that doesn't type check。

 and that's because if you look at the code， the last part does have to be an int because we add it。

So whenever this happens and it often happens when you're not using part of your argument。

 you'll end up with a more general type than you might expect。 and that is okay。 All right。

 I sometimes call this unexpected polymorphism。 All， if your function is correct。

 and you still need to test it and you still need to make sure that it does work for the types that it is required to work for。

 then if it also works for values of other types， well， that's just a useful thing。

 and we don't have to worry about the type that Ml gave us as long as it's more general than what we need it。



![](img/7834e8c1865be0634db3c057bb7ceebc_3.png)

Now hopefully this idea of more general is intriguing to you and you'd like to learn， hey。

 given two types， how can I tell if one is more general than another。

 and I can give you precise rules for doing that and I'll do it in the next segment。



![](img/7834e8c1865be0634db3c057bb7ceebc_5.png)