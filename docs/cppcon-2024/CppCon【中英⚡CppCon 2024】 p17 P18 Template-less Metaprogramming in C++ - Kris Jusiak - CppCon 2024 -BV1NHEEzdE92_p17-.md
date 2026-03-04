# CppCon【中英⚡CppCon 2024】 p17 P18 Template-less Metaprogramming in C++ - Kris Jusiak - CppCon 2024 -BV1NHEEzdE92_p17-

The C++ is such a tight knit community and it's awesome to have events like this where everybody can kind of immerse themselves in。

 mingle and then get to know each other on a social basis and on a professional basis。

 while having some really good content that you can learn from as well。



![](img/2c15dbda218a7ee7a9894dfbcf794fd6_1.png)

![](img/2c15dbda218a7ee7a9894dfbcf794fd6_2.png)

![](img/2c15dbda218a7ee7a9894dfbcf794fd6_3.png)

Thank you for coming。 I'm Chris， and I believe that meta programming is a superpower。

 and today I will try to share a bit of that with you。😊。



![](img/2c15dbda218a7ee7a9894dfbcf794fd6_5.png)

Not is I didn't say template meta program。But well get to that。But before we'll start。

 let's just make it clear what we'll be talking about。

So template meta programming the ability to generate code at compound time。

 There are many in many different ways to do it。One of them has been chosen by Cpl++。

That's why we had templates from the very good。Beginning， and that's the first T。

 Sis here on this slide。But that's not what is actually。Difficult or wrong with C plus plus。

S T D vector of T， you know， specialization templates。 that's totally fine。 Nothing wrong with that。

 That's the designer we have。 However， what we'll be talking about today。

And this talk is about these tears as ellipses and these meta functions。

 this ability to manipulate things， ability to change。These types get something out of them。

And there's a lot of power in that， which I'll try to show。 And then。Improve upon。

 So hopefully that sounds exciting。 But before we'll dig。As a is。Raise your hand。

 if you think that template meta programming in C+ plus is either too hard。Or could be easier。Okay。

 well， that notice that these slides pre compile compile them as well。 So I have the answer。

So I totally agree it's hard。 But on the other hand， why are we dealing with all of that。

 why we do all of these hacks。Before who is thinking that template mono is actually powerful。

Thank you。We are on the same camp before， I believe， well。I believe that。

Comply metal programming could be easier， you know， powerful。Still get nice error messages。

 compiled fast。 Who would like that。Everyone。Sorry， out of like it's C plus plus， but。

We'll see how far we can get of that。😊，So， before。We'll show examples I just wanted to point out。

Sean Baxter give a keynote at C plus plus now 2022 about meta programming in C。

 She's the author of this compiler， saying better meta programming features make better libraries。

 And I think that's a very， very important point about meta programming。

 It's not about your production code and stuff that It's about making the libraries better。 C plus。

 it's great。😊，If it comes to making libraries， but making actually the subtle things and better interfaces。

 more perform things requires meta programming because we have templates。

And without great facilities to do it。That's kind of difficult。So， without further。Let's begin。

 So this is， I'll show a few examples of where the template Meogram is being used and how it's being used。

So we don't have to dig far。 Let's look at the FL。 So that Li C plus plus。

I just taken it from the it。 It's a variant implementation。 It has this fine index。

Where we have the T and we have this TSS ellipses， and we want to get the index。😊，Of the TSs。

 which match the T。You know。Very simple， in principle， kind of difficult in meta programming world。

 There's a lot of solutions to that， which I'm not going to show。

 but you have to be kind of clever to make it happen。So that's one of the examples。

 and standard template library is full of that。Another thing。Who likes tus using tus。

I believe your compilation times are exploding。So SDD2po is an example of that。 So before C+ part 26。

 when we get Pg indexing， that usually implemented with template recursive instantiation。

 which is the worst kind of way of doing template meta programming。😊。

That's example of lip standard T++。我。Sorry about that。Another example from Microsoft S T LRA。

 Even RA has temporary meta programminggram in it。You have to enforce the types to be the same and there's tons of other examples。

 which I'm not going to dig into that， but you get the g that STL is full of template meta programming。

 is full of that and why because it's a library and meta programming empowers libraries。

But there an observation。 Standard templateulator barrier doesn't have。

A standard template meta programming library。I don't know whether you have noticed that before。

 but that's true。 All these all implementers of standard S T L， very powerful implementations。

 but very tricky to make it right。😊，And they lose a lot of magic to happen， to do it。By the way。

 there has been proposal to to add that to the language that' by Peter Diov， the author of Bot MP 11。

 Greg Library， by the way。Didn't get through because of C plus plus trying to get into different directions。

 which we will actually discuss。 But very interesting point。

 I think in an observation that S T L on its own auto has tons of template metagrammian。

Doesn't have facilities to actually do it Therefore。

 implementers have to deal with intrinsictri and hacks to make it happen。Another thing。

 which is really close to my heart， is performance。And meta programming empowers performance。So。

In that case， let's just look at the simple example of unpacked tract。

 Sho what kind of size that would be， what， what would be the size of。12， That's right。

ForFor those of you who don't get it， you can read it in the standard。 But the point is that。

It's not optimal。 And， you know， if you follow data driven development or something like that。

The data rate design， you may be surprised。Wouldn't be nice if you have。A meta function， for example。

 pack， which will pack it for us。 like it will do the unpacking of distract tract and pack it back。

 That's powered by template meta program。And if you have reflection。

 we can even get the same names out of it。Before the reflection， we could get the tuple out of it。

 which is packed。 But with the reflection， we can get the names as well。 So that's very powerful。

 That gives us you know， better cash utilization and stuff like that。😊，So。Performance is important。

Before， Ill have one other slide about it because I care so much about it。😊，So， I claim that。

Way more things when it's assumed by default and by most projects is not at compile them。

And that hasn't been leveraged as much。I believe because of the facilities which we have so far。So。

 for example， let's look at these protocols。 We would like to add run time。

Look up which string view is matchinging to the you know Pro and returnino。Very simple thing。

But if you get into the implementations and overhead。

 you' will see that it's a lot of code to make that happen。

 But what I'm trying to point it out here that if you have policy design from Anda Alex Sanresco designed by introspection。

 you can make choices， based on what you care about。 You care about performance。

 You care about the size。 You care about the memory。 You can make that choice yourself。

And just to scare a bit， I will show a bit of assembly。

Because I think it's extremely powerful that this magic lu， which is the magic look at table。

 If you interested how this work， you can poke me afterwards。 I will show you。😊。

But notice that the first implementation on the top doesn't have even the lookup。And you know， it。

 it doesn't have a table。 All of that is in register。 So it's the smallest hash table you can get。

There's no lookout， no comparisons， nothing like that。 it just。A few instructions to get。

That might in from this protocols to the。 And the other one， it requires additional lookup table。

 So you will have cash Mes， potentially and salvada。So I think that's powerful。 And finally。

 as an example of meta programming to get you excited about。😊。

I only to point out about state machines。 I love state machines。 I think they're very powerful。😊。

But it's kind of hard to implement them very efficiently。

 If you go to the switchcase and order solutions variant， you will get this overhead。

 but let's imagine that we have this state here， which do not have actually values。😊，Out would lie。

