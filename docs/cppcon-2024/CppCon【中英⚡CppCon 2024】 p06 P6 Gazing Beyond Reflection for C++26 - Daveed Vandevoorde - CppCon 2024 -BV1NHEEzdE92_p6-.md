# CppCon【中英⚡CppCon 2024】 p06 P6 Gazing Beyond Reflection for C++26 - Daveed Vandevoorde - CppCon 2024 -BV1NHEEzdE92_p6-

![](img/f3214a456322ca7d793f691cd0333c7a_0.png)

I've got a sad announcement to make。Andrea A Sandresco offered me free beer for not showing you guys a cool example about transforming enumerator values into strengths。

😊。

![](img/f3214a456322ca7d793f691cd0333c7a_2.png)

So I'm really sorry about put yourself in my shoes。We're talking free beer， guys。So sorry。Originally。

 I was going to talk about the use for S for reflection and try to， to give you reasons for things。

 but it doesn't fit in an hour and a half。 So we're going to jump right into。Technicalities。

 for those who are not familiar， the C plus Committee， the scienceization Committee talks in papers。

 right， We exchange papers。 We propose ideas with papers， rebut ideas with papers。

 So I'll be talking about a number of papers。 And I'd like to talk about the papers that are aimed beyond the fundamental paper for reflection。

 So you probably have heard that we're going to try to land P 29，9，6。

 which is this paper with written by these awesome folks。In C 26， chances are good that will succeed。

 It's not a dumb deal， but were we're on schedule， but I want to build on top of that。

 but I hesitate to do that without going first through the basics。

 So I'll go through that paper first in about half an hour。

 And then I'll talk about another paper that have start standardization It going to open up a whole new world。

 but that is still that is not at all clear that I can make an N C+ 26， but we'll work on it。Okay。

 I think， oh， one more thing。 Peter 96。Landed about a year ago。

 but it's really the result of many years of work before that。 And in particular， to this paper。

 P 1240 that had it had more features。 It had more stuff in it。 And so what we did。

 we distilled it to a sort of minimum set of features that still achieve all the goals we want。

 and hopefully， hopefully they'll work out。 I might occasionally refer to this P 12，40 paper。

 All these papers are available on the Internet。 If you， if you look for them。 So reflection。

Is the ability to treat your program as data， right to。

 to look at your program to the program to look at itself。 we're going to do that compile time。

 right， But we so we need， we need a way to transform your source code into values。 So for that。

 P296， right， our proposal is introducing an operator to transform the source domain into a value domain with an operator。

 a prefix operator that we call the reflection operator So we are now spelling it a double carrot。

It used to be single carrot， but that conflicts with an extension in the clang compiler。

 And so we didn't want to break clang or make it so that that clang cannot implement reflection。

 So thats that's， that's the operator， which you can apply to a type like vector in or point to function returning in or a variable like C out or template like vector or namespace like stood or the global namespace or a few other things like a data member。

What you get out of it is a black box style called info。 stood matter info。Why a black box type， you。

 you might think， well， why don't you come up with a bunch of types to describe all the different kinds of reflections that we could have like a variable reflection。

 a functional reflection。 And we actually started that way。

 But or or we've quickly concluded that if you do that。

 you put a st jacket on the language for those who are familiar with the evolution of C plus plus。

 you might have noticed that once a type is in the standard。

 there's not much you can do about that anymore。Right，30 years ago。

 we made a mistake with stood vector of bull。 We decided to make an explicit specialization with a different API than the rest of vector。

 and we cannot change it because too much code depends on it。 So by making our type。

 a black box type for everything， we allow compilers and the language to evolve without having to worry too much about what reflection says。

Anyway， that type comes from a new header， we call meta。 And along with the tie come。

 dozens of functions that allow you to take apart your program。

 Ex it and maybe even synthesize a few things。 right。

 So say you have a class template V and you take its reflection。

It's going to deduce third meta info out of this。But all the functions。

 So third meta info is a type that's associated with st meta。 So when you make a call。

 an unqualified call。With an argument that it has type info。

 it will automatically also look in st matter， so。It makes the the built in functions feel a little more。

 a little more special。 So there's simple predicates like， are you template。

 but there's also functions that can ask where are you from， What's your enclosing namespace。

 What's your enclos class。 There's all kinds of other functions。 Some are a little more synthetic。

 right， So there's a function called substitute， It you give it a template reflection and a range of reflections of template arguments。

 it will， it will give you back the reflection of the corresponding specialization。

 So this would give you back a reflection of V of int。😊，And the reflection system can。

 can represent any template arguments， right， values， templates， types and so on。

Now that you have Vecoin， you have a class， you have an natural class。

 You can ask for its members if necessary， that will trigger the iniation of Vcovent。

 But now you're going to have a vector of infos。 And you can look at them。

 all the members will be in there。 nest types， nest alias， nest inums of member templates， anything。

 And you can write your own constant valve functions to do things with it。 right。😊。

One of the things that we've done to make this possible is that before this paper landed in C plus 20 and C plus 23。

 weve worked on adding capabilities to constant evaluation。

 So some of you might be aware that right now， you can use a vector during constant evaluation。

 You can use a string during constant evaluation。 You have things like constant Al functions。

 which used to not exist All that stuff was done by the same team that's bringing your reflection in anticipation of reflection。

 Those things are also useful in other ways， but the the motivating feature was all this work。

Alright， so now you have you have all this data。 You want to turn it back into into source code。

 P 296 have has relatively few mechanism for that。 In fact， there's one dominating mechanism。

 which is called splicing。 So it's these funny little new tokens， square brackets。

 And it's it's the inverse operation of reflection。 So reflection turns source code into a value。

 And now you can， you can turn the value back into a source code construct。

 So this is exactly the same as saying in。Sometimes you have to。

 you have to help the parsor out and put type name in front of it as if you。

 as you would doing in in a template， It's in fact the same rules。

 So in the place where you might need a， a type name in a template。

 you will also need it in with reflection with the splicers。 Occa。

 you might need to say that it's a template。 although I've never run into this。

 So we put this in a specification。 but we have no use case for it so far。

You can use it as a name qualifier。 In that case， you don't have to say it a type or namespace or anything。

 It will figure it out by looking at the colons。 like it looks ahead the colon and figures out what needs to happen。

 And， of course， you can， you can splic expressions and variables and functions， all sorts of things。

 So that's that's a paper in one slide except that there's all dozen of functions that you will have to look up in a paper。

 I think P 296 is pretty readable up to the point where it talks about how the standard gets modified。

 So if you're interested in reflection， I actually recommend reading the paper。

 it has a number of examples that I hope are are motivating and compelling。Just to be sure。

 let's look at a very simple example that has no use other than to demonstrate the feature。

I'm creating a little type with three members。 I chose some bit fields because a lot of reflection approaches cannot represent bit fields because they try to work with point to data members。

 which can't point to bit fields or reference members。 We have no problem with that。

 And so now I'm going to take apart that type。 So I take。

A reflection of entry right into a context per variable。 In principle。

 you're not allowed to leak info to runtime。Comper should give you an error on that。

 although the current implantations don't necessarily do that。

You can ask for its name so that identifier was declared with。 So this would output entry。

There is a a U8 identifier off， but to Y is not prepared for U 8 string views yet。

 So identifier off returns a string view。 U 8 identifier off returns a U8 string view。

 But more interestingly， you can ask for the members， the non static data members of this entry。

 So non static data members off。 is's going to return a vector with an info for every non static data member。

 We have three here。 So we're gonna have 0，1 and 2。I select 2。 since it's a vector。

 you can use all the algorithms that you have available for vector， right。

 most of the ones that are in the standard library， anyone that you write is contableval。

 you can do that anyway， after this line， I have now an info that represents value 0，1，2。

 and I used 2。And I can print out this name。But I can also programmatically now select a member out of E。

Right，So E dot D M with value， this is almost exactly as saying E dot value。

 except there is no lookup happening。

![](img/f3214a456322ca7d793f691cd0333c7a_4.png)