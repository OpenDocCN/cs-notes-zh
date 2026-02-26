# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P18：-18-COMP6771 21T2 - 8.2 - Advanced Types - Part 1.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Hi hi everyone， I'm glad that was muted because my chair collapsed and。😊，Got got really mad。

 Nice to see you。 Good to still see some people here after like。😊，You know。The time， like given， I。

 like， just this time of term， everyone kind of gets tired and they all start to disappear。

 It's definitely time for a new chair， old， old Betsy。I've， I've moved this chair。

I've moved since I bought this chair， I think I've moved house 14 different times。

Move like where I lived。 So it's been， I， it's， it's an old chair。The very first。Very first move。

 it did， I think， was I wheeled it from Maroobu to Kensington along the footpath to to move houses。

 So I'm very， very very sad to see it go。 Now， just before we jump into today。

 two things I just want to preface today with quickly first。

 one is just about some of the comments people made last night。

 So I had to look through the feedback last night。 And there was quite a lot of people who said that。

They didn't feel like we went through the content last night in enough detail。

 and I totally get where you're coming from。 I think I just wanted to give some context to that。

 So with everything in this course， we can always go through things in a substantially more detail than than we do sometimes we could probably talk about custom iterators for two or three weeks if we wanted to generally speaking our attitude as to try and go as deep into things as we feel that you need for。

Accessible content， which is basically the assignments or the exam。

Where week8 and9 differ from the rest of the weeks is that we don't ask you to do it。Sorry。

 we don't ask you to do a ton with this stuff。 So unlike custom iterators and templates where we like really dig into everything。

 the advanced template stuff we did last night is very much like a it really doesn't It's not going have a massive impact on the rest of your time in this course。

 the way it manifests in your assessments is substantially less than the other stuff。

 So therefore we'd rather cover a broader array of topics in a little in a little less depth。

 So that's on last night' stuff。 I know some people are still not like that。

 but I hope that gives context。 that's not us just deciding not to go through it。

's it's just a choice about how much we go through certain content。的。Yeah， exactly。 And the second。

 the second point is that today today's topic， which is called advanced types。

 which I'll pull up now。This particular lecture is probably the most mish mashy of lectures in the course It's probably the first one I would look at changing We're going to cover a bunch of things by a bunch I mean a few first one is decal type which is a way of converting values to types in a sense we're going to cover type transformations which is a lot like type traits last night。

 all the same kind of principle just different usage we're going to cover binding which is an extremely confusing but relevant topic which we touched on in the Tuute7 for anyone who's watched the Tuute7 recording and I actually talked about this a bit then and then we're going to talk about forwarding which is really interesting application of binding。



![](img/e82bc31b31dc2045370c217ef829b1b7_1.png)

These aren't my strong suit topics， though So I think I just want to preface that in advance。

 there'll be a few times today that the answer will be I don't know because these are getting really theoretical。

 not theoretical。 these are just getting like a bit more obscure and kind of academic and I use that word a couple times yesterday。

 and I think just to contextualize when I said to people that these topics are academic what what that means is not like。

There for the smart students， what it means is that like， you know。

 if you think about like research versus like practice。

 it's like the practice stuff is what you go and do every day with and some of the academic stuff is more。

Most people don't come across this I have to think about this much in their day to day， whatever。

 you know， so like a lot of things in this course as we get deeper into the course like around this time。

You'll find that if you were to go do some work with C plus plus in a research context or industry or this or that。

 like not that it doesn't matter。 But for the majority of standard use cases。

 you won't have to think a ton about things like type traits and type transformations。

 And if you do often， it's just to make your code cleaner and better and all of that。

 So the point I was trying to get at yesterday was just that。

The way I kind of view a lot of the week8 topics maybe with the exception of binding because I think binding is pretty important a lot of it like if you just never watch these lectures。

 you'd probably be okay right like you would never be like damn it I really don't understand something whereas like if you miss stuff on templates or you miss stuff on smart pointers like all these things you definitely feel a very real obvious whole in your knowledge so when I say it's academic I just mean you know you'd be fine and a lot of the fun of doing this is to think about the language and a bit more of a。

Theoretical broadway rather than just being like if， if I'm not using it every day。

 I don't care about it。 Like that's a non academic view of this。Any hoot？That was a bit of a bubble。

Today， so the one of the first things we're going to talk about is decoal type。 now this。

This concept is easy to understand at a high level。

 a bit harder to understand at a lower level mainly because we've started stripping parts of this topic out over time and in some ways that's made it easier but some ways it's made it harder。

 for instance previous offerings of the course we used to go into more detail about L values and our values and some of the subtypes they have。

 but in essence。Deult type is a built in function into C plus plus that。Essentially allows。

 maybe we could start with an example。 It essentially allows you to take a variable or a named。Item。

 whether it's you know an R value or an L value or whatever。

And to get the type of that So instead of writing something here like int or auto or double you can actually say know the type that I would want to put here is actually the declared type which what decoal type stands for of this particular of this particular value so in a program like this for instance。

 if you want to say int X but instead of it being an int you actually want to say I just want x to be the same data type as whatever I is。

You can just say。You can just say decal type I。Of X。

 So it's really a way to replace typings by using name values。 You can do it broader than that。

 but that's that's the use case of it over the next few slides， we'll talk more about。

Where you can use it， and。Kind of how this topic can be brought in， but at the highest level。

 it's similar to a type of function for C plus plus。 Now。

 if you've used a language like C C is is type of in C。maybe anyway， like Python has a type。

I can't remember which language has a type of。I'm not sure if it's JavaScriptscript and I'm getting confused。

 but it's like in other languages like Python， you have this。

 you have this ability to do something like I was writing some Python this morning for someone and you can say like you know。

 if type of a equals int， then do something now。

![](img/e82bc31b31dc2045370c217ef829b1b7_3.png)

Where I want to point out the difference between where you may have seen something like this is what。

This is saying is this is like， I wantna take a named item like a。Pie of data。

And I want to find the type of it。As a value。So you can actually do value operations with this like equals where decal type differs is that decal type is like a type。

 So if you imagine in a language you have types and values right and when you say int a equals5。

 you're essentially saying this is one way of thinking about it。

 you're essentially saying type value equals value right A is a value R's a value， L value R value。

 whatever int is not an L value R an R value is's just a type。

It like int double whatever T generic types。 So when we're dealing with types and values in a lot of other languages。

 when you have it like a type or a type of depending on the language。

 like if you're using something that's loosely typed like Python type will actually return you a value that you can interact with。

 you can put it inside of if statements whereas in C plus plus it's more like you know C and type of where it's actually getting you a type So in C plus plus if you did something like say。

If you said n I equals 5， it makes no sense to say if decal type of I equals int。That's not。

Valid code， right， Like that's just not how the the language works。 You don't， you don't do。

Binary comparisons and equality don't take in types， they take in value， so this here is a type。

 not a value， which is os。

![](img/e82bc31b31dc2045370c217ef829b1b7_5.png)

![](img/e82bc31b31dc2045370c217ef829b1b7_6.png)

Which I guess is kind of one obvious and key difference。嗯。The real question though。

 is when you pass something in， like if you pass a variable in like an integer variable in。

 decoal type will give you an int。The real question is， what type does it give you？

So if you look at these slides here， you actually see there's four different outcomes here。

 which is that。😊，You have type T T reference， T R value reference。

 I'll call this T L value reference T R value reference or type T here as well。 Now。

 I think in the past， I've tried to go through these rules in a bit of detail， but。嗯。

It can get very confusing very quickly。 But the point is that if you have something like。



![](img/e82bc31b31dc2045370c217ef829b1b7_8.png)

嗯。You know， if you have something like an int。Ent equals1。

 and then you say in J or in reference to J equals I， or then you say int you know。

 K equals standard move I and all these kinds of things。U。But it's still going to give you an in。

 but it's like these these are all kind of different instances of in。

 So it's like if you take I J or K and you decoaltype it， you'll get an in。Right， they're all ins。

 They're all different types of in。 So you'll get an in。 That part's the easy part， right。

 that part's quite straightforward。 The harder part about decal type is are you going to get just a standard T value Are you going to get a T reference。

 which we call an L value reference or are you going to get a T R value reference， right。

 And that depends on the type of thing that you。

![](img/e82bc31b31dc2045370c217ef829b1b7_10.png)

You enter so void's already asked does decal type happen at compile time and the answer is yes right so with languages like C plus plus types are essentially all about compilation So anytime something has to do with types you're pretty much always dealing with compilation。

 that's not always true， but it is very broad general pretty much all kinds of types and checkings and stuff happen at comp time。

3。

![](img/e82bc31b31dc2045370c217ef829b1b7_12.png)

Here's the thing so these are kind of a summary of the rules。

 it's like if an expression E is any of a variable like a standard variable a static member。

 a function parameter， then the resulting type is t so if you just say n I equals1。Then， you know。

 it's of type T。 And then you get into some weirder rules where like。

If the type you're decal typing is say a reference。



![](img/e82bc31b31dc2045370c217ef829b1b7_14.png)

You know like what we had in in G added here， which was J。

 then that's going to be the actual decal type will be a T reference right so that reference will carry over。

Then it gets more complicated once we get into like X values and R values。 And again。

 I'm intentionally not going to start explaining this because it's not accessible， right。

 It's not accessible and。We could talk about it for a while， two things I've done though。

If you want to read more on it， which I some of you will， is that firstly。

 to understand the decoal type rules， we have to understand that in C plus plus the types of values we have are more complicated than L values and R values。

 it gets a little。

![](img/e82bc31b31dc2045370c217ef829b1b7_16.png)

A little bit more thorough than that。 I have， I have linked to really。



![](img/e82bc31b31dc2045370c217ef829b1b7_18.png)

Something I look back on if I ever want to refresh my memory。Which is。

Essentially how they describe R values， L values， X values， G L values and PR values。

 And there's a certain amount of inheritance relating to these in terms of like， you know。

 they're not all five totally disjoint types。 Some of them are kind of subsetstish of each other or they have some kind of complementary value。

 but this is like， you know。嗯。These are kind of some descriptions。

 This is kind of one of the more simple ways I like to understand it。 Some of them are quite funny。

 like， you know a PR value is an r value that's not an x value。

 And then you think well what's an R value， an R value is an x value。

 a temporary object or a value that is not associated with an object。

 Now we've kind of explained R values before without the x value stuff right。

 we've said R value essentially something without an address was how we simplified it。

 You know' it's a temporary object that has no address like like a literal or a value not associated with an object like a literal a lot of the time or something that's standard mood。

 something that's kind of floating through the error and isn't really tied to a specific thing。

 So then to understand what a PR value is， they say well it's an R value that's not an x value。

And you think， okay。Sure， what's the next value and then it gets kind of complicated how to separate all these out？

嗯。So Nathantaniel in the chat said， a better description to split a PR value is just information on how to construct an object and isn't an object yet。

An X value is an R value that is actually an object and has an address。Et cea。

I'm sure there's more coming， but or maybe not， but。

pointin is the distinctions here are more valid than kind of the simpler ways we talk about in the course。

 though in the course we just kind of deal with you have L values and R values and L values have addresses R values don't which is actually a really easy way to understand things because a lot of compiler errors will give you information in terms of like know trying to assign R values so it's a great starting point but if you want to learn more。

That's where you can look or you can do some more Googling。

But then also the actual decal type rules what I have on this slide here is just a summary of the C plus plus decal type specifier anyway。

 so decal type can take in some stuff and here is a full explanation of how it's all kind of derived in terms of like what we have on the slides is what's here if it's an x value then it's that if it's an L value then it's that if it's a blah bh then it's that though generally speaking generally speaking the main things to take away are that。

And this will cover you for the majority of cases， usually you're going to mainly be interested in。😊。

One and two， which is kind of like。If you have an int of some sort。

 decal type of that value will give you an int。Deal type of that name， I should say。

 will give you an end。But if it's a reference， then you're going to get an L value reference。

 that're kind of the two main things。 So then if we look at some examples here。

 this is kind of what I started writing up in G edit。



![](img/e82bc31b31dc2045370c217ef829b1b7_20.png)

And again they can get pretty complicated pretty quickly if we have an int I and then we have an int j which has a reference to I。

 it's like， okay， well the decal type of I is an int because I is just a variable。

 I is just a standard boring old variable decal type of J though because J is a reference。😊。

Which is an L value， in this case， the decal type of J is actually an int。

Reference an L value reference。 And then again， it can get more complicated pretty quickly in terms of like5 here is a PR value。

 And， and Nathaniel said this on the chat too， which is like one is a one is a PR value。

 There's no object behind it， right？ So it's like。And this is。

Like PR values are type of r value in the sense that we've kind of said this before as it's like this isn't really like an addressable thing。

 You can't really say like where is this object， It's just kind of floating。 And yeah。

 there's a very tiny typo， which I'll fix up before later Again， I just want to preface like。This is。

 this is getting this is a topic in the course that we've kind of floated about whether we should keep going into much depth on it。

 And we're kind of phasing it out slowly。 So don't like stress about it if you don't understand it In a lot of ways。

 this is mainly useful because you'll see deccal type in a lot of code。

 which we'll kind of get to some examples of more importantly。

 like rather than talking about this again too academically。

 I just want to kind of give you a sense of what the hell is the point of this。

 Like why would I need it， I know my thing's an in。

 why can't I just write in or why would I not just write auto， you know like what's what's。

What's even the value of any of that？Here's a really， really simple example。

 So let's say you're writing a generic find function。

 and that find function takes in an iterator begin an iterator and in an index you're looking for like a needle you're looking for as you loop through this linear representation of some container。

 Now， the logic you write might be quite straightforward。 You say for auto I equals begin。 Y。

 you also set an integer to be 0 to start。 Yep， that sounds good。

 And then you say we're going to loop while the beginning is not end。 And then each time we loop。

 we're going to increment both the iterator and the I。 So we're basically。😊。

you know we're basically looping through looking for a sorry I did say something wrong before。

 we're looping through looking for a particular index earlier， I said this was a needle。

 that's not true。 Sorry about that。 So you know if we have a list of like 10 items or something and we're trying to go through every item to look for like the third index or the fifth index this is how we can do it now obviously we have STL algorithms like standard advance and standard next。

 I think one of them is in place and one of them is not in place。 Oh my god， this chair I'd love it。

 but it hurts my soul。

![](img/e82bc31b31dc2045370c217ef829b1b7_22.png)

Yeah， we have like standard advance which helps us move along with Standard Next。

 So there are STL algorithms for this kind of thing， but in this case。

 let's say we're implementing our own for some reason。



![](img/e82bc31b31dc2045370c217ef829b1b7_24.png)

![](img/e82bc31b31dc2045370c217ef829b1b7_25.png)

The problem with this kind of function is what is the return type？

Particularly part like if what you're taking in is an iterator that can be generalized across a series of types。

You know， like what happens if you're， you're passing in some iterator that can be the alias or。

 you know， forward iterator that you could pass in a。iterated to a vector and iter it to a string。

 How do you know what the return type is？Right， so in this case， we can't。You know。

We can't really just write in order。Good oh yes， but it's like the main problem is that we could find the return type using decal type because what do you know about iterators。

 Well， if you dereence begin。RightBecause beginner is an iterator to the beginning。

 if you dereence it， you get the value at the beginning， and if you get the decal type of that value。

 you'll actually get the type。So decal type here could actually help us get some key information as to the return type。

But， and if this kind of gets into some really kind of more obscure things about dealing with this。

 So ideally， we'd love to use decoal type here to actually specify the type。 We'd be like， yep。

 that's the actual type I want to use。That's a bit clearer to the compiler Now。

 We're not dealing with any kind of， you know。I don't know how to put it because this example doesn't even work。

 but it's like the one of the most one of the more interesting things about this example is that based on the actual language rules of C++。

😊，This isn't even valid code because the decal type of the dereencer begin。

 remember that when when this code is actually compiled it does so in like a linear fashion right。

 it sweeps through it and the problem is at this point in your code here。

 star begin doesn't mean anything this name is not valid yet because this name only becomes valid once it's actually passing the function parameters and one of the good things about。

The introduction of so in C plus+ 11 was where they introduced trailing return types。

 this actually solved the problem， which is really interesting again， I guess。

Example of language design。Debscurities， whereby this first one here doesn't work。

 The second one here does work。 And you'll all kind of see it as familiar as， you know， the the。

 the modern way of doing。Function return values， because at this point here。

 when we've used decalite begin。This has actually already been this is now a valid name so the compiler is like yeah actually at this point now I know what that is because the way the compiler processes the users like you know。

 that first value， then the function， then the next value etc。U。And yeah。

 this is I think this is another reason why I mean I think there's a few reasons why the auto always use auto and the auto at the start of a function and the trailing return types are kind of starting to be encouraged。

 I think two big things one thats come to my mind is like well， firstly。

 there are some circumstances where the old way of making the old way of specifying return types doesn't work。

 But I'm pretty sure in basically every instance， the new way always work。

 So at least there's some consistency there Also it kind of aligns more with you know。

Most of your lines starting with auto so that you're always looking you're always looking you know to the right hand side or over that side for return types and stuff。

 but I mean again we don't really care what you do in that course this is just an interesting example of decal type again。

 decal typers mainly got lip service in this course is like you're going to see this around you just need to know what it does。

Are there any kind of questions before we move on to type transformations？Cool。Excellent。嗯。So。

If you liked type traits yesterday， you're going to love。Oop， sorry， Someone got it。 Sush says。

 can we do decoal type auto in the loop， yes。Our deco type order。

I don't know even about a decal type auto。 I don't think you can do decal type of auto like auto is not a concrete type。

 or autos autos in instruction to the compiler to derive the type。It's not a type。I mean。You know。

don't do it， I'm sure there's some weird things about it。But yeah。

I don't I don't know what I think like all these questions right。

 I get lured into this thing where a student's like。

 can we do this and it's like why would you want to do it's the first question？

Or like what motivated that kind of question， like using doing a decal type of auto？

What is that going to help solve？Deal type of decal type。 Can you do a decal type of a decal type。

 I'm not sure。 I mean， I don't think you can even do a decoal type of a type。



![](img/e82bc31b31dc2045370c217ef829b1b7_27.png)

I mean again， this is one of those things where you can go and try these things out really quick。

 I mean the benefit of G++ and GCC and any kind of implementation of C++ is that。



![](img/e82bc31b31dc2045370c217ef829b1b7_29.png)

They're really quite like easy things to play around with。 So like， you know。

 if I were to just make a file here， I don't even know what folder I'm in。嗯。I go inside 6771。

 I'll just call it bla。cppP， right？And we just。Bla。cppP。And we say， you know， well。

 I want to make in equals zero， and then I'll say decal type of。I J equals 0。 You know。

 is this valid code。 Yeah， that's valid code。 What happens if I do decal type of int。K equals 0。

 does this work， right， you can just play around with these things。

They didn't like that right so that's why again if you go back to the decoal type docs you can see here it's looking for some kind of I mean here they're referring to as an entity。

 but it's essentially an expression in in language terms。

 expressions are I can't remember what the difference the expression or statement is。

 but it's certainly not a type。Similarly， you wouldn't be able to do this for the same reason。

You know， decoal type itself as a type。So it's basically like。

 I have no idea this is not an expression to me， so it's expecting some kind of expression。



![](img/e82bc31b31dc2045370c217ef829b1b7_31.png)

Now。A little bit of an expansion on yesterday's stuff。Is that。

Yesterday we did type trades and we talked about the the background around that and how it's basically you're using thesestructs to pass you're using。

Explicit specialization on these trucks to give you some really cool compile time。Like。

How to put it to give you some really cool compile time abilities to kind of inject like conditionality throughout your code。

 The reason yesterdays stuff was called type traits is because we were looking for traits of type such as is it a void。

 is it a pointer we looked at partial specialization for his pointer and we looked at like explicit specialization for his void type transformations though are more focused on taking a type and transforming it to a different kind of type so。

😊，Some examples here are that and we're not going to go into the mechanics of how these work。

 a lot of this is mainly again just touching very lightly on these different kinds of things that exist。

So firstly， we actually have a tight trade here， which is。Well， I mean， the type。

 this is just a function we wrote， but there's a type trait called is same。

 And what is same is as it's， as you'd expect， it's basically like you give it two types。

 So it's a templated。It's a templated Strto class that is。

Temp it across two type names and all that one is， is that simply like as we saw yesterday。

 I mean again， I could just really quickly explain it to you。



![](img/e82bc31b31dc2045370c217ef829b1b7_33.png)

If it's not concrete enough。

![](img/e82bc31b31dc2045370c217ef829b1b7_35.png)

Which is like， you know， if you had something like you said， struck is name， which you'd say。

 you know。Think about how you'd implement one of these template type name T， type name U。

And all you'd have say under the model we did yesterday is or is it static？I can't remember。

Static constant in。Val equals。False。I think it was。

 I'm actually not sure how this one would be implemented，cause yesterday。

 the ones we were looking at were。Kind of explicit， which is really interesting。

 I've never actually thought about how this one's implemented becauseuse we've never bothered to go into it。

 The ones we went through yesterday were a little bit easier。

 I guess to wrap your head or wrap my head around， I should be more explicitca we were just dealing with。



![](img/e82bc31b31dc2045370c217ef829b1b7_37.png)

![](img/e82bc31b31dc2045370c217ef829b1b7_38.png)

Where' as an example， yeah， like here we were just dealing with essentially like whether or not the types concrete or not。



![](img/e82bc31b31dc2045370c217ef829b1b7_40.png)

嗯。So Nathaniel says that the answer to this one is partial specialization。

 so what if you remember about partial specialization is that partial specialization is where you still have the templates you still have the type names。

 but you're actually in some way partially specializing it here。

I'm not really sure what the syntax for this would be I'm not sure if Nathaniel is but the example we had a partial specialization yesterday was is pointer so remember how we defined our like catch all case our true general generic then we defined our partial specialization which was still tempered across the same type name that we gave it a more explicit condition and that it had to be a pointer of that type and that's how we dealt with partial specialization yesterday。



![](img/e82bc31b31dc2045370c217ef829b1b7_42.png)

And the point is that all these different type traits and type transformations do the exact same thing。

 They just go into a little bit more。

![](img/e82bc31b31dc2045370c217ef829b1b7_44.png)

Like variability with it。Right。嗯。So this is a trait where essentially if you have T 1 and T2 as the same type。

 this returns true， otherwise it returns false， something that you might be wondering or asking is like。

 okay， sure， but。Yesterday， when we were doing it， we didn't use a pattern like this， right。

 We used a pattern。 like， so this is what the slides have。 But yesterday， we did something like this。



![](img/e82bc31b31dc2045370c217ef829b1b7_46.png)

We were like Valel， and you can see this here too when these things were used。



![](img/e82bc31b31dc2045370c217ef829b1b7_48.png)

嗯。Now， I don't I think I can't remember which change it was。It was one of C plus pluses。

 And I don't think I put it in the notes anywhere。 but I don't know if it was C plus plus 17 or。



![](img/e82bc31b31dc2045370c217ef829b1b7_50.png)

One of the。There was a particular point where they made a little advancement on it such that to access the actual value here。

 you could just use like a call operator or something else other than like a static。



![](img/e82bc31b31dc2045370c217ef829b1b7_52.png)

Member field， right， so rather than having to do whatever valids， like this is totally valid。

 though I don't think it's valid。For all versions of C++， and again。

 we could try this out really quickly。

![](img/e82bc31b31dc2045370c217ef829b1b7_54.png)

Just by， I mean， let's even try and just run this piece of code here。Probably okay。

 so this one works fine。Ay it out。Yeah， so I mean， again， I could do this in V S code。

 I'm just kind of doing it really quick， so。You can kind of step through this now。

 standard bull alpha。What even is that line， This is something that we usually discourage。Right。U。

Again these these have a particular actually funnily enough in the older version of the course。

 some of the first examples had these particular。😊。

I don't know if they call theyre like terminal specifiers or something。 What。

 what this first line here actually is is it's kind of like changing your terminal settings。

 If any of you have done that thing where you。You put special commands in your shell scripts or whatever that give your terminal different colors and stuff like that。

 it's not the same as that but。It's basically like a command because like you think standard C and you're like okay printing stuff。

 but you're not really printing stuff here。 you're actually sending like a signal to standard C that's like。

 oh from now on， I want you to print like ones and zeros as true and false。

 and you can do a similar thing to like set the number of decimal places。

 It's kind of like it's kind of like sending a setting to standard out that changes how it prints。

 Yeah yeah P sense as I think decimal places has something similar。

 Yeah so generally speaking this particular thing is something we discourage the use of in the course。

 though here it's mainly just done for example。 So you can see whether it's true or false。

 But yeah you can see here that we call print is same It's just a templated function with in in and we get true。

 We call print is same witht and int reference or L value reference。 we get false。

 we get the same thing where we compare an in to an R value reference。Yops， compile。And so forth。

 and this is a type trade up here。Right these three things we're seeing down here though are what are the start of what are type transformations and type transformations are where you essentially have a astruct just like type traits。

 this case is called a remove reference， you give it the type you're starting with aE your type and when you access a type element here。

You actually get the transformed type。So in this case。

 it's like standard removed reference of int type。 Well int never had a reference。

 so this will be true right So the removed reference of int will be true。

 but then in the cases here where we have L value references and R value references。

These are also true once you remove the reference because you take an L value reference here。

 you remove it， you take an R value reference， you remove it and you remove the reference part and you just get left with the raw type。

 So it's like if you try and check if int is the same type as the type transformed L value reference。

Type Trans， remove reference of the L value reference， then those two things are the same。

And you can see the same thing here if you compare a constant with a constant R value reference。

 so these remove references are essentially these type transformations are a way of taking in a type as a template argument and then extracting the type as a property here right so this is a you know a type property essentially。

Now。呃。There are so。I'm wondering what this is compiling with。 So let me， let me try。Okay。

 that still didn't mind doing that。Compilr， generally， I mean。

 Nathaniel's again given some more information on this， so。The transition， as I understand， it。

 is something roughly along the lines of。That used to be how you would access it， access the info。嗯。

And I think Nathaniels saying that it went to this in C++ 14 and I wasn't sure of the particular version and then it's gone to this in C++ 17 and I'm pretty sure it's all revert backwards compatible to so they all work but essentially it was just like a you know can we reduce the vibosity of this so that we're not。

ToHaving all this know scope to vowel static， whatever。So yeah。

 you'll probably see a few different ways of doing this depending on the particular version that's being dealt with because of some improvements that have been made on that front。

Pyn says， would we ever need to know the implementations of type transformation functions， I mean。

 no， you don't really need to know the implementations of type trait functions。

Most of the reason we actually talk about type traits is just as a。As a way to understand。

How explicit and partial specialization work。Um， you know， that's kind of the aim of that stuff。

So no， again， this's what I mean about。嗯。It's all very academic。So it's just， you know。This stuff。

 again， if， if you， if you， if you fell asleep through all of this， I'd9 up， you you're。

 you're not gonna like wake up tomorrow and， and be missing a huge amount in your。

 your day to day life。 It's more just fun to explore the language and and think about it。

 So there's a whole bunch of type transformations。 though it's not just removing a reference。

 You know， we have the ability add our value reference。



![](img/e82bc31b31dc2045370c217ef829b1b7_56.png)

Which in a way， iss kind of like this is kind of like standard move to me。

 at least in terms of standard move， the difference is it's taking a value and converting that value to another value with a different type。

In this case here we're actually dealing with types though。

 so you know the using keyword as a way of saying I'd like to give this name a particular type。

And again， if you think about the differences between types and values or types and you know。

 names that denote types and names that denote values， it helps you really separate these out of it。

 otherwise it gets really confusing really quickly。It like you can't print a， you can't print this。

This is not a value you can print。 This is a type。That you can。

Use when creating a name to a value and so forth。So we have add value reference。Same thing here。

 Just another example here。 Oh， that's where it is。 I， I knew。

 I knew we put it in the slide somewhere as like。Kind of previously speaking。

 I always hate that Ica I always， I like cutting things out of courses when I think they don't achieve a purpose。

 So I I cut a lot out of courses as I goca they don't just like keeping in for no reason。 And then。

I keep thinking I cut things out。 And then I'm like， oh my God， I cut that out。

 What was that random detail。 And then it was sitting right there and I didn't actually cut it out。

 But yeah， so this is like the old school way of dealing with type trades it's you know the actual struct itself and here's the the this specialization。

 You know this is just the template。 Maybe this uses maybe you're doing the catch all case。

 Maybe you've got the partial specialization or the explicit。

 you know this one here is obviously going to be。😊，Probably some kind of part， I mean。

 these are all probably partial。 I can't imagine that the compiler has。

I can't imagine that library writers have manually written explicit specializations for every single possible type so that doesn't make sense。

 but the point is that from C+ plus 14 onwards you don't need this colon colon type thing so you'll see like a lot of C++ code this is okay I'm not exactly sure in the implementation details。

Of how this works for C++ 14。 I mean， obviously this one makes sense because we saw it yesterday。

 This is a class or astruct that has a particular static member。 how this one works。

 I'm not too sure。um。But I'm sure there's some really simple solution I just haven't ever thought about and I'd be like。

 oh， that makes sense。G。So。I mean， yeah， down here down here is still the old school way。Like。

 so you can see here in this， in this case， in C plus plus 14 and stuff。

 you wouldn't need this value down here。 These are just older things when the method of。

 of defining those particular strikes or classes was。Using those static members。

 but again the whole point of just mentioning type transformations is just whether it's type transformations or type traits。

 are all just ways these are all ways that you can use these particular libraries to get more out of your code。

 for instance， if you need to type that。Needs a reference or doesn't need a reference or you need to remove cons or add cons。

 etc ce， you can do all of that and it's good to kind of get a sense of how they work because of all these different specializations we have with templates。

Now， one of the most fun topics I use find in double quotes here is。Finding。Because。And again。

 I'm not sure how many of you actually watch the tu recordings or watch the tu recordings I do。

 but and I'm not sure what the other tutors did。It was linked in the ch as like you might want to refer to this。

嗯。And I haven't checked。 So perhaps， perhaps， you know。This wasn't coveredVID at all。

 perhaps it was talked about a lot though。Bding is a topic around， you know。

 you've got these different things like you've got。

Youve got values and you've got values and you've got L value references。

 which we just call references， you've got R value references， you've got contel value references。

 con star value references。And when it comes to passing them into functions。



![](img/e82bc31b31dc2045370c217ef829b1b7_58.png)

What can accept them is kind of like the question and you already have a very semi intuitive understanding of this topic because you all kind of know roughly that if you have a function called min that takes in or you know。

 int print that takes in an eye that you can pass in I as an int。



![](img/e82bc31b31dc2045370c217ef829b1b7_60.png)

You can pass in what's， I think it， you can pass in eyes in it。

 But if you have another function called print。Double J， for instance。You can pass in J as an int。

 you can pass in J as a double。Et cetera M。While this isn't the same thing。

 you already kind of have this understanding that。The types that you give a function。

Don't need to be perfect。 They just need to be。compatible for lack of a better word they need to be they need to make enough sense in their compatibility to be what you might call binded。

 So like you know if you have a variable that you pass into this function like I come down here and I say you know in K equals 0 and then I say print K。

Li。When the compiler tries to figure out which function you're trying to call K' is an int。

 but print takes in a double but it's like they're compatible type。

 so it's kind of happy to you know for lack of a better word， like bind that K。😊。

To that double parameter。 It's like， yeah， okay， I can make this argument work。 it， it fits my model。

 And the topic of binding is really all on the same track， which is that on the left here。

 you have all the parameters that functions might take in such as， you know。

 and forget the top one for a sec，cause we'll come back to that。 You know， it might have。



![](img/e82bc31b31dc2045370c217ef829b1b7_62.png)

An L value reference， basically a noncons reference。

 it might a contll value reference which is just a const reference as you know it。

 and you might have an R value reference which you probably haven't seen a ton。

 but you have seen it for things like copy， sorry move assignments and move constructors。

And the idea is that if these are your parameters， if you have functions with these parameters。

What arguments will bind to those things。You know which which of these arguments will work like will an L value bind to a function that's expecting an L value reference would would a constant value reference bind whenever I say L value or L value reference。

 they are the same thing just to be clear So when I say you know。

 would an L value bind to an L value reference， you could also phrase that as like would an L value reference bind to an L value reference now obviously。

This is an L value。 this is a constanttel value。 This is an R value。

 So an L value will bind to itself。 a contel value will bind to itself。

 and R value will bind to itself。 That's all pretty self explanatory。 The question is。

What are the other cases where those things will bind together now。Here。

 an L value will also bind to a constant L value。 That makes sense because if you have a reference to something。

You can pass it into a function that's expecting a con reference， you've probably done that before。

The other way is not true， though， you can't have a con reference to something and pass it into a function that expects a reference。

 again， you have an intuitive understanding of this。 like you see this with const。

 If you have a non-cons variable， you can pass it into a function that expects a con variable of a compatible type but not the other way round because if you if you have a constant variable and you pass it into a function that has a noncon parameter。

 that just wouldn't make sense according to the language rules because it would say that that function has now permission to modify that because in the function。

 everything's in a bubble and it's like okay the function is like well。

 I have a noncon parameter I guess I can edit it， but you can't so。That doesn't make sense。

 and probably the only other interesting thing is that you can pass a an R value into a constant value reference parameter because。

You can't modify and you can't actually modify an R value or a PR value or whatever。

 just like you can't modify literal。 And again， just to really spell this out。 And I mean。

 I'm not sure if Nathaniel you're still around， but if you are it be be good if you could share a difference because I think I got asked this the other day is's like what's a good example of the difference between know R value and a constant R value if that even makes any sense But like let's just define ourselves a function here。



![](img/e82bc31b31dc2045370c217ef829b1b7_64.png)

Called print， void print。 and it's just going to take in a。In reference to A。

RightAnd all it has to do is standard C out A。Like this。Or just include IStream。

And we'll just have int main and inside int main we'll say int j equals1。嗯。

And then we'll say print J， now will this code compile？Yeah， and when we run it， does it work， Yeah。

 why， Because what is J in this case， Well， I mean。

 J in this sense gets treated as a as an L value reference right。

 it's a noncon thing that we can reference It's a noncon L value。 It's a thing with an address。

What happens if I make this a or if I， you know， just if I maybe make this even clearer to you。

 it's like we have。A reference to K like this and you know we say past K and and we're like， okay。

 that works， that makes sense。 What if we make this a constant， a reference to a constant？

Will this work？No， because binding reference see， like we're seeing all the words come together。

 the binding the reference。Of the non constant reference。Hia。To a constant discards its qualifies。

 it's basically saying when as you're like in my attempt to bind this K to this particular parameter。

 it just discards the cons qualification。 it's saying like do you not care about the fact that this is con。

 that's not okay。 So it throws an error。Now， what happens if this is now a cons？Reference function。

That works。Here's another question for you。 What happens if I just try and print 6。 Now。

 remember that 6 is not a variable。6 is an R value in this context。It's not an L value。

 It's an R value because it kind of you know has no memory。

 has no like addressable memory or anything。 And when I try and do that， we get the exact same thing。

 right And again， the error messages are relatively straightforward。

Cannot bind non constant L value reference here。Of type int reference。

 That's what this is to an R value of type int。 So it's saying6 is an R value of type int。

 And I can't bind that to an L value。

![](img/e82bc31b31dc2045370c217ef829b1b7_66.png)

It's all in this table here， right an you can't bind an R value to an L value reference。



![](img/e82bc31b31dc2045370c217ef829b1b7_68.png)

However， what happens if this is a cons？

![](img/e82bc31b31dc2045370c217ef829b1b7_70.png)

L value reference。That works。R values can be binded at constant L value references and why is that the case？



![](img/e82bc31b31dc2045370c217ef829b1b7_72.png)

Again， it makes sense because even though an R value is not an L value。

 what do you know about contel values， you can't modify them， They're like read only。嗯。So therefore。

 like as far as the compiler and the rules are concerned， it's like， well， you know what？

The only problem with R values is that you can't modify them。

 You can't modify an in literal or a string literal。So if it's constant they can't modify it。

 why not just have it treat let's just have it treated like a constant value reference。

 that'll make it easy， that'll make the code more robust because your functions can work on more kinds of things you know you can just define it once and it can work on a range of circumstances and then finally we could take in in an R value reference to an end here。

I believe。Yeah， so this will also work because6 is an R value。

But what happens if you try and pass in K。

![](img/e82bc31b31dc2045370c217ef829b1b7_74.png)

Another one。 What happened here。 We tried to pass in a L value to an R value reference parameter。

 an L value argument to an R value reference parameter。

 And we got cannot bind R value reference of type int ampersan ampersan to L value of type constant。

 It won't work for J as well。 same error， but it just won't be a constant。 It'll just be an int。



![](img/e82bc31b31dc2045370c217ef829b1b7_76.png)

So the rules make sense， right， like if you step through it， it's actually very well prescribed。嗯。

Phi S says， how do you do a const value？I don't know。 That's what I mean。

 That's what I was saying before about like， this is a carryover from。



![](img/e82bc31b31dc2045370c217ef829b1b7_78.png)

Slides time memorial that。Trying to think， I used to， I have this memory。

That's why I asked Nathaniel because I'm just like， I don't really remember what that is。嗯。

And I guess， again， for more context here， I wonder if I even have them。Just a really quick。

 What's the time，57， let's finish off this topic， and then I'll。

 I'll give you a little sneak peek in relation to that。 How many we got。 Yeah， okay。

 a couple things so。

![](img/e82bc31b31dc2045370c217ef829b1b7_80.png)

In terms of binding， this can actually be， Oh yeah。 So if you look at the left example here。

 we can actually use this to understand our code a bit more in terms of。

This top function here is our print function， and it is a constant L value reference function。

 It takes in a constantele value reference。Okay， so that'll take in our values， con values。

 not all values， though。Like is in non constants values。 Now you can see here in our code。

 we're creating a few things。 We're creating an L value here because J is an address。

 We're creating a。Or maybe this is a con star value。Is it， What is K there， Why is it an L value。

 Becauseuse it's a string。I thought we talked， oh， right， it's an address。Sure， got it。

That makes sense。 I was thinking of something else。 Yeah。

 this is a constantst L value because auto will make it a cont cha star。 And generally speaking。

 the compiler is happy for you to assign a string literal to a variable as long as you declare it as cont because string literals have to be const because they're not they're not mutable So that's all valid。

 And then when you say print C plus plus you're passing in an R value an R value will bind to a constant L value reference。

 Then you say print go。 Now go here returns a string literal。

 So that string literal is also an R value。 So therefore， when you do this。

 you're basically taking a result of this， which is an R value and you're trying to pass it into this and that does work because you can bind an R value to an L value reference We try and print j which is an L value。

That works because you can pass a noncon L value。To a constant L that like combine noncon things to constantt things。

 we've known about that since nearly week one。 and then K here， which is another constant L value。

 also works。 So those three things in this case work fine。

 And that's why you can see the constant T reference binds every argument binds to it。

 It's like great。

![](img/e82bc31b31dc2045370c217ef829b1b7_82.png)

Sounds good。 The other relevant example， though， which is a bit weird。



![](img/e82bc31b31dc2045370c217ef829b1b7_84.png)

Is that the other type of parameter that everything binds to is a templated。R value reference。

 So it's an R value reference of a templated type。 I don't have a great explanation for you as to why this is。

 because I I don't know the answer to every single y of y of y in the universe with C plus+。

 But essentially here， the point this example is trying to demonstrate is that。

These things are the same in the sense that a templated R value reference。

 everything will bind to it as well。 So in this case here。

 we'll be able to bind these R values and these L values and these cons L values they'll all bind totally fine。

嗯。So yeah。And then we kind of get onto forwarding， which is probably my。

The one pilot of the course that confuses me the most。We'll get on to that in a sec。

 But before we do， does， do anyone have any questions about。Bing。

 I should probably mention reference collapsing。 actually。

 I think I have that somewhere in the notes。Yeah， I mentioned reference collapsing before the break。

 but does anyone have any questions about that so far？



![](img/e82bc31b31dc2045370c217ef829b1b7_86.png)

Cool， found it。Alright， okay， so the last thing is just on reference collapsing。



![](img/e82bc31b31dc2045370c217ef829b1b7_88.png)

![](img/e82bc31b31dc2045370c217ef829b1b7_89.png)

So I I don't have this in the slides。But you can Google reference collapsing。Sorry， I was like。

 get really worried about everything， every Google I do now。嗯。

I don't know that I don't really have a， a true source of。Knledge on it。

 there's some really simple rules that you can find floating around。嗯。It's， it's not like。

 it's not like pivotal， but it's， it's actually area。 that'll do。 So basically。

 if you're ever looking for reference collapsing information。

 look for something that looks vaguely like this and you'll be like， oh， that's the correct thing。

 So the reason reference collapsing is really tricky is because。



![](img/e82bc31b31dc2045370c217ef829b1b7_91.png)

The example we looked at where a templated R value reference。

 also everything binds to right so if you're dealing with templates you use a template R value reference。

 the tricky thing is， how do you tell what the type of a is here？Right， like。



![](img/e82bc31b31dc2045370c217ef829b1b7_93.png)

And how do you tell the type of any of these things， Because like if you think about it。

 an R value might be like， you know， like。

![](img/e82bc31b31dc2045370c217ef829b1b7_95.png)

If you say print 5，5 is technically an int ampersand ampersand。

 So if you have a function that takes in an int constantpersand， it's like。

 what even is the actual type of that a And the idea behind reference collapsing is that。



![](img/e82bc31b31dc2045370c217ef829b1b7_97.png)

I'll just copy these into to G edit I that these are the four rules around what happens when you essentially start stacking ampersans on top of each other。

 So the point here is that if you try and create an L value reference of an L value。

 you get an L value。 If you try and create an R value reference of an L value， you get an L value。

 if you try and create an L value reference of an R value， you get an L value。

 and if you try and create an R value reference of an R value reference， you get an R value。

 Now this will become more relevant with standard forward and stuff。 Sorry my eyes hurt。



![](img/e82bc31b31dc2045370c217ef829b1b7_99.png)

But。These are kind of some useful rules that can help you understand what happens if。

 say you go back to our type transformations where we were， did we add an R value reference。 Yeah。

 so it's like， take something like this。

![](img/e82bc31b31dc2045370c217ef829b1b7_101.png)

![](img/e82bc31b31dc2045370c217ef829b1b7_102.png)

![](img/e82bc31b31dc2045370c217ef829b1b7_103.png)

Where we have these lines of code here。If you take something like an int that's just an int and you add an R value reference to it。

 you're going to end up with an int R value reference。 What happens though。

 if you add an R value reference to int ampersand because this is already an L value So like when we say R value reference。

 all we really mean is like do double am percentand of that。Right。

 but you can't have just like random series of ampersans。 like it has to stop somewhere。

 So you can look at the reference collapsing rules which say that， okay， well。

 if you take an R value reference of an L value， you end up with an L value。Okay， cool。

 And if you take an R value reference of an R value， you end up with an R value reference。

 And I don't even know what an R value reference of a pointer is。 I think it's just that。

It's kind of an ugly thing。So yeah， these reference collapsing rules can be helpful if you come across a situation like this and you're like。

 wait， wait， wait， wait Wait， if I， if I had an R value reference to an L value。

 what even is it anymore。 And it's like the answer is an L value。

 because the reference collapsing rules tell you。You take an L value。

 add an odd value reference to it。 it becomes an L value。So that that's like a little handy。

 nuggetative knowledge。Cool， just before the break， I wanted to very quickly give you some。

 some fun insight into would everyone like some quick fun insight into four minute history of Adv C plus plus at UNSW。

😊，Well it's not we're going gonna extend the lecture time。 Well， I guess it will。

 but we're not gonna run over。 But or you just want to have your break and tell me to shut up。

 You tell me， I don't mind I have no ego。Sure。嗯。

![](img/e82bc31b31dc2045370c217ef829b1b7_105.png)

Sure， so really quick。😊，Basically， you have up until 2016。You have a。

So what happened with this course was up until 2016， this course was。

 I don't remember the exact name， but I think it was called object oriented programming。Right。

Re simple stuff。 it was I did the course in 2013 very long time ago when it was kind of different。

 most of this time the course was taught by a jingling Jingling is a pretty senior academic in the school of CSC really crazy brain like good brain like good crazy brain very smart does a lot of research and compilers and programming languages。

 So you know this is kind of where the course came from。

 he stopped getting involved with it somewhere around here and then a couple other people started to help take over it。

 a guy called Bradford Heap in 2016， Brad ran the course and I did a few random lectures on some topics just to fill in the gaps。

 I didn't have any involvement with running the course。

 but like I just helped with a couple of pieces of content in 2017。

 they couldn't find anyone to run the course。 So the course was kind of。

Of courseour was kind of render the same way by， I think it was a new academic and then someone else and and you know that kind of happened there and it really kind of slumped and then in 2018 it didn't run at all and then in 2019。

呃。They wanted to run the course again， so I started running the course as well as two other people。

 which was a guy at Google called。Matt Star and then another guy who's now at Google called Christta Bella or Christo Tpher deella。

 who have much bigger brains than me， particularly in this。Field or in this language。

 And we kind of rewrote this course， and we took， we kind of took a good half out of it。

 A half we liked。And then we made another half up， but it still followed the same general structure。

And then that's kind of carried on ever since and we've made some alterations every year。

 but just for like an example。 So I still have my lecture slides from 2013。

 I dug them up while I was talking before and what's really interesting about the course is that it's actually like you'll actually see how weirdly similar and different at the same time it is so one thing for instance is at the course contained very similar concepts but like the ordering of things was very different So for instance there was a lot of emphasis on different kind of raw types on the computers and the different sizes of those types I think some of the earliest examples were around numeric limits but it's funny because you'll see this and you'll be like oh that actually looks like a lot of the stuff looks really familiar like type conversions how do we convert types in C+ all right well we have different types of cast but you know maybe there's more cast than we've talked about orcast so a lot of kind of a lot of the things that we've done for better off。

Or worse， it's a different kind of course。 It's， it's jinglings。

 This course was a lot more focused on compilation and some of the more fundamentals of the language。

 whereas Chris and Matt brought a lot of。Kind of they， they， you know。

 their time working with C plus plus， Claaririssa says it looks like。3，1，4，1。

 I figure what this course is， software design and implementation。 Now， totaltle looks cute。You know。

 declarations and definitions。 So here's an example， right。

 is that declarations and definitions came like， remember those slides we did in week 1。

 It's like all of this is from this original slide deck。 It's different。嗯。It's quite different。

 but it's like fundamentally like that's there。 Topics on scopes and function scope and like local scope and name spaces like。

 so it's， it's really interesting because in a lot of ways。

 it's like there's a lot that has evolved and things that have been cut out too。 Remember。

 I said earlier that we cut out a whole bunch of。tererminal manipulations， you know。

 things like this， for instance， where you could set the precision of decimal points and and random other things。

 But again， a lot of very similar topics， you know， such as。Argument， dependent lookup。

 our value references， stand a move。 I'll shut up in a sec。 We'll have a break in a sec。

All the stuff about OO。I did pretty bad at this course as a student， so。嗯。Templates。

Same kind of things。 You know， it's like， it's a little bit more involved。 Some of these examples。

 like sometimes as' en tiling you chunks of the cost that we've made up。 Other times。

 you'll actually see that some examples are。Extremely similar to some of the earlier stuff。Which was。

You know， like you， you remember this from yesterday's member template stuff。

 So some stuff's kind of port it across。 and， you know， we keep good things。

 We get rid of things that we think are slightly off， off topic。You know。

 I'm just trying to find even one last one， I'm just dragging in random ones that I don't remember copy semantics。

 right like here's all your rule of five stuff。Big5， by the way， this was 2013。

 So like C plus plus 11 was actually pretty new at the time。

 So a big emphasis on this course was kind of like， oh。

 what's all the cool things you can do with C plus plus 11， You know。

 and how do you copy a stuff and。Really random， but I think the general just as you can see that it was when when I talk earlier about like it being academic。

 it was a lot more academic in the sense that the course wasn't really focused on you building lots of things with C+ plus the course was focused on you。

😊，Understanding things about C plus plus like what like how is it， how does the language work。

 how does it work with the compiler， you know， why certain things certain ways and stuff， but。🤢，Yeah。

 that's all。Yeah， so last question before the break， PS says。

 so next year the course will be a lot more prepared for C++ 20。Yeah， so as I said。

 we delved a lot into C++ 20 last year， though it caused a lot of confusion mainly due to the lack of both teaching staff and online resources who were familiar with the topics。

There are a lot of kind of new things that we didn't feel we could support at the moment。

I think what you'll see is just a a slow， like you'll see like a slow creep of。

C plus plus 20 things come into this course。 Like， there's really a few things like， you know， the。

 the function return type notation and stuff， I think， is one example。Maybe that's not2 C++ 20， but。

You'll see you'll see the kind of old school custom iters go naturally like when we if we do an assignment two style thing they'll be more about or less about you know all those different kinds of operators and there'll be more on like the spaceship operator and stuff though there's definitely some quite fancy new stuff about C++ 20 like filters which。

Fuil to C++ 20。嗯。Which I don't know what to Google to get what I want。

 But these were the things that very much confuse students。Like this， for instance。

 like this piece of code。 It's like， okay。This is how you do a full loop， which。

Takes all the even numbers from a list and。For I， I don't know what this is for I from 0 to 6。

 filter it and only get the even numbers and then transform it to get the squares of all those numbers and then print them all out。

So it's like we just felt at the time that。Given the early uphill battle of this course。

 it's not the hardest course in the world， but you know it's not an easy course that trying to teach everything we have to teach and then to try and teach this on top is just like a bit。

 so yeah there's plans to move towards these things as they become more widely adopted and then there's also plans for a second course that touches on these things a bit more because the reality is like while this course is called advance C plus plus it's more really。

Intermediate level C plus plus or something equivalent to that， right， Like you wouldn't。

It it's hard， but it's not like， I mean， you know， you can't really have an advanced course that has no prerequisite knowledge。

 I guess。嗯。Yeah， anyway， that's all。 So let's take a， let's take a 5，10 minute break。

 Take a little break till 720。 We'll talk about standard forward for a little bit。

 It's not really going to be a massive part of your exam or any other assignment。

 So we won't go into too much depth of it。 And then we'll just I'll have a little quick run through the assignment。

 We can do a little bit of a Q And A until 8 o'clock。 so。Yeah， sounds good。



![](img/e82bc31b31dc2045370c217ef829b1b7_107.png)