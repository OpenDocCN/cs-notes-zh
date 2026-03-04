# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p37 36_09_type-synonyms -BV1bw4m1D7MM_p37-

In this segment， I want to introduce type synonyms。

 which are a separate thing from what we've seen before and a bit of a digression from data type bindings and case expressions。

 but nonetheless helpful for the next homework and in nice contrast with data type bindings。

So data type bindings introduce a new type name， and that new type is different from every other type。

 the only way to make things of that type is with the constructors that are part of the data type binding。

A type synonym is a new construct I'm showing you now for the first time。

 and all you do is you write type， so that's a new keyword， not data type。

 just type the name for the type， then equals and then another type。

And what I want to emphasize is that the English word synonym is perfect here。

 It just creates another name for the same type that was already there and so now we can use that name wherever we were using T and we can use T wherever we might use that name they're interchangeable in every way and I even want you to not worry about which one the Reple prints the two things。

 the type T and the name a name really can be used interchangeably so let's go over to some ML code so I can show you how this works so first I have two data type bindings that we've seen before for suit and rank and those behaved just like they did before。

 but now I also have a type synonym where I kind of remind myself and allow myself to use in the program that wherever I have a suit paired with a rank I can think of that as a type named card so the type card is a new type name that will now be in my environment。



![](img/485b0ccb23744ad3cc30c4158b2166c1_1.png)

And it means the pair of suit and rank， so I could write suitstar rank or card。

 and that would be fine。Another common idiom by the way that I'm not going to use in the rest of the file but I wanted to show you is to give a name to your record types。

 it's a huge pain to write down this record type anywhere or to remember or even give a name for it。

 so instead of just having a comment that says this record is for describing the names of people in my class along with their student numbers I can go ahead in my program。

 give a name to that type and then use that type name wherever I want。Okay。

 so now let me really emphasize this interchangeability aspect。

 So here's a short function I wrote called I Queen of spades。 It takes in a C of type card。

 So notice I can use that type name that I introduced up here。

And it does the appropriate computation of seeing if， indeed。

 the suit is spades and the rank is queen。Okay， so now here are three variable binding， C1， C2。

 and C3。C3 is how we've been writing most of our variable bindings where I just create a pair of a spade in an ace。

 and when you see that you might be asking， well， what's the type of that， is it suit star rank？

Or is it card。 And the answer is it's both because those types are the same。 So， in fact， C1 and C2。

Are both perfectly reasonable very declarations， variable bindings。

 It turns out you can write the type of a variable if you want with a colon and then then the type。

 and the type checker will make sure that that's correct。

 that the expression over here really does have that type。

 And what we'll see here when we go over to the reple is that all three of these C1 and C2 and C 3 will type check just fine。

 So let's just。😊，Make sure that's right。And they are。 We see all the bindings here。

 You'll see the Reple printed are data type bindings are type synonyms。

 Then this function is queen of spades of type card arrow bull。

 And then it happened to say that C1 has type card C2 is type suit star rank and C3 is type suit star rank。

 But I promise you that。This works fine。 That type checks and runs。

 this type checks and runs and this type checks and runs because anywhere you have card。

 it's the same thing as suitstar rank。 So I emphasize this because on your next homework we'll tell you to write functions of certain types like for example。

 card arrowbo。 And if you write a function and it seems to work correctly。

 but it prints out a different type like maybe suitstar rank arrowbo。

 I want you to recognize that that's the same type and it's okay and the reason why that's going to come up if I switch back to the code file here。

 is a little thing I haven't shown you yet， which is soon we're going to write functions like is queen of spades differently。

 We're going to use case expressions for that sort of code2 even though suitstar rank is actually a pair and not a data type it contains data types And once we write is queen of spades with case expressions rather than in hash1 and hash2 then we won't have to write types on our arguments anymore we won't have to。



![](img/485b0ccb23744ad3cc30c4158b2166c1_3.png)

Wr C colon card We'll be able to just write C。 The only disadvantage of that is then the repple won't know whether we want to see card or suit star rank。

 So it'll just pick whichever one it happens to based on its own internal procedures in internal algorithms。

 But nonetheless， I find this style of coding much more pleasant。

 just not writing down the types and letting the type checker figure them out for me for function parameters the same way we've been doing it for variable bindings。

 So that's why this notion of type synonyms in this interchangeability would be so important。

 It does raise an interesting question， though， which is why have this in your language。I mean。

 if it's really just a convenience， well， let's be honest。

 sometimes convenient things for programmers are worth putting in the language。

 If you want to write C RD rather than suit star rank， it's nice to have a facility for doing that。

 And the only confusion is that if you wanted a function of type cardarrow bull。

 And the Reel says suit star rankarrow bull。 you have to realize that that's an equivalent type and it's okay。

 And it's the same thing。 So it doesn't really let us do anything new yet。

 But in a couple weeks later in the course， we will build on top of these type synonyms when we study Ml's module system and there we'll be able to do something pretty special and we'll need these type synonyms in order to do it。

😊。

![](img/485b0ccb23744ad3cc30c4158b2166c1_5.png)