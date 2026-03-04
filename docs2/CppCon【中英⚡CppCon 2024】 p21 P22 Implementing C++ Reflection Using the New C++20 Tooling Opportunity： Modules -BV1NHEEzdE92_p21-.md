# CppCon【中英⚡CppCon 2024】 p21 P22 Implementing C++ Reflection Using the New C++20 Tooling Opportunity： Modules -BV1NHEEzdE92_p21-

![](img/e7b7c4716df938594611b2792b654a26_0.png)

🎼I chose to attend because there are other talks that I think just being that in person really helps you engage and connect with people who have some law interests and even different perceptions。

 So it's just nice to be here in person。😊。

![](img/e7b7c4716df938594611b2792b654a26_2.png)

![](img/e7b7c4716df938594611b2792b654a26_3.png)

Hello， everyone。 Welcome to my talk。 I hope you have had a great conference thus far。😊。



![](img/e7b7c4716df938594611b2792b654a26_5.png)

And today I'll be talking about implementing reflection。

 using the techniques that are available to us right now。But before we begin。

 I want to could I see a quick show of hands for everyone who knows what reflection is。Okay。

 that is most of the room。Oh， and of those people， do you already have some problem or something that you would like to implement using reflection？

Okay， okay， I's round half the room。 So it seems I will be preaching to the choir today。



![](img/e7b7c4716df938594611b2792b654a26_7.png)

But let's get started。So I am Michael Steven， I'm a tools and engine programmer and I work in the AA video games industry。

 so previously worked at K ofem， where actually joined Grilla。

And I would like to explain why I am here talking about reflection because for me。

 it's been a much longer obsession than that because even before I worked in the industry。

 I was you know when when I was making games at university and even before that。

 I already had this like this desire to be able to just eat right over my members， right。

 I just wanted to like have my object， get get each field and just like dump it to disk right at that point。

 I just wanted to make a quick quick and dirty， like save and load system。

 just dump my game stay to disk。And that was even before I knew the term reflection existed。

 I already knew I wanted something like this。 over time， of course。

 I knew I started to learn the actual definition of reflection。

 and I started exploring different techniques to actually implement something like this。 again。

 using the techniques that were available at that point with differing success。So。

Thats what I'm going to be talking to you about today。

 I'm going to talk about how you can implement the reflection right now。

Using all of the knowledge that I've gained in the process and kind of。

Going to a final conclusion of having。A module system that works of having a reflection system actually powered by modules。

 which you might not expect， which solves most of the downsides of all of the other techniques that are currently out there。

So the structure that this talk will have this first I'll give you a quick overview of what reflection is in the room maybe there will not be many people who need it。

 but in general I think it's a nice recap it will also kind of set up the way I'm going to be thinking about reflection In addition I will talk about some of the use cases that I have which I find really powerful to use reflection for to hopefully get you excited to try and use reflection yourself and finally well go into actually implementing reflection right now so that you at the end of this talk have the tools available to you so that you can start solving problems using reflection。

Okay， so quick recap of what reflection is。 So the simplest way I can explain it is that it's the metadata of the code that's arrived。

 So for example， here， we have a small entities script and reflection is essentially the ability to ask the question。

 what numbers do I have。 So if I ask that question right now to my reflection system。

 it will be to tell me that my entity class or my entity script has two data members。

 One of them is called health， which is of an integer type。

 the onone is called tagagon is a string type。 In addition。

 it will give me information about what functionality the class has。

 So it test the ability to eat a burger， and it can do that all on its own without any additional inputs。

So that is nice， right， We can iterate over stuff， but like why do we really care about the disability right to ask what members we have。

And it turns out to actually be really nice for writing systems that don't depend on a specific ordering or specific structure of data。

 but I just care that there is some data in some form or another。

 so a clear example of this is if you want to write a serialerization system so that's the ability to take your inventory representation of your objects and you want to flatten it down to a single either binary stream or JOBlo or something like that。

 so you can send it over a network， put it on disk， anything like that。

So here there's a half pseudo code example of how you can do this using reflection。

 so we get in any value right， we don't even know what type it is， yet we can still reason about it。

We can we can ask it about what fields it has， right。

 which which data members are in this in this object and per object。

 we can simply assign the value of each of those fields to a value in in a JSO envelope。

Corresponding to the name of。To the name of it。嗯。And maybe a bit of a more realistic example of how you would actually implement this yourself。

 We would structure this is that you would have some value to Json function right。

 like the actual core serialization logic that you would like to write。

 you would have some set of things that you know how to concretely serialize。

 So probably some built ins， right， your integers， your doubles， your strings， things like that。

 And then you're able to compose your classes out of those。

 So you're essentially able to serialize anything that you can by because you're able to recurse into kind of the compounds the classes that contain these smaller things that you do know how to serialize。

So I think that is quite nice。 but we can even go further than this。

 right we can embrace it as an extension to the type system。 When I came up with this phrase。

 I was really happy about it， and I didn't know there was gonna be five talks about compile time reflection this year。

 So it's not very original anymore， but it fits the slide very well because you can think of other systems that you could write with this right you could think about you write your application。

 normal S plus write some data structures。 And when the time comes that you want to write or implement Aui for this。

 instead of putting a lot of effort into binding it。

 you could use a simple declarative text format for example， that can directly bind to。😊。

To our data model by string， so similar to how WPF does it， for example。

It doesn't have to be UI or application related right， You could take your library。

 and maybe you want to expose your library as to other languages。

 like you want to make a Python binding。 The information that you need for this， typically。

 you would implement this manually with some glue layer right in between to explain what is going on between the two languages。

But all of this information， right the structure about your code。

 that is what the reflection gives us。 That's what it provides。

 So you're able to automatically generate these bindings to languages。

Not just to expose your library， but also to write plugin systems， right。

 if you want to have a small scripting language inside of your application。

 you want to expose some API and can do this automatically without cumbersome wireprint。嗯。

If we take a look more， in more detail to data models and how we can reason about how how our data is laid out。

 you can think about automatically generating a full Ui， right。

 This is often what editors do for in the games industry Here， for example。

 we have an object that has an in script。 This is just like some script， It's not even。嗯。

Nothing ever says what is inside of this component。 however。

 we already have the editor that fully understands it and we have the ability to both view the values and edit them directly。

嗯。So。In addition， you can usually replace systems that have traditionally been required a lot of manual work。

 So one of those examples is an induced stack right。

 So the ability to press our controls at and haven see the previous stage。Tpically。

 this was implemented using some base class。 So every commands。

 every operation that you were able to do in your application。

 you would manually need to write out what that is and then and then also implement the undo version of that command。

 So's a lot of manual work， but using reflection right we can actually do this fully automatically。

 we can take the state of our of our data。 We can take a snapshot of that。

 we can then just modify our values like normal。 And then after we're done。

 we can do a small di between the two states of all the objects。

 and then the differences between those， we automatically store it in a command to a fully automatic indo system。

 also meaning that your un systems。Relatively， it it， it's really consistent， right， It's。

 it's fully automatic。So。I hope you all agree that this is kind of a cool feature。

 right like having the ability to reason about your code in your own program。

 it allowss you to do a bunch of cool things。 So how do we actually get there。

I'm going to go over it in a few steps。 I'll first give you a quick overview of how I I view reflection in in a kind of mental model of sorts to explain how we're gonna implement it。

 I will mostly be focusing on in this talk about runtime reflection。

 This is not that you cannot use this technique for other compile time like constructs。

 It's just just that I want to focus this talk on something concrete。In addition。

 the type range techniques that runtimer。

![](img/e7b7c4716df938594611b2792b654a26_9.png)