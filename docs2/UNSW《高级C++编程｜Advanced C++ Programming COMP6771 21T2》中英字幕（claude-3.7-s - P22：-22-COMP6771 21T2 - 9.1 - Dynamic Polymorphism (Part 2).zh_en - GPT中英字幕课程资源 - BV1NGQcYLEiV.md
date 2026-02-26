# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P22：-22-COMP6771 21T2 - 9.1 - Dynamic Polymorphism (Part 2).zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Hi， everyone。Nice to see you all again tonight。We're going to continue on with the second half of the lecture on。

Drumtime polymorphism， dynamic polymorphism， however you want to think about it。

 How is everyone tonight， We have 25 people here， which is a record low。

 I not sure if the content was so boring yesterday or if it's just probably just a busy end of term。

 Got tons of stuff to do Just refreshing the page in case the chat went funny not we're all quite nice to 24 people。

 So I hope we don't we only't spend a ton of time on stuff tonight。

 So I can get let you all get back to your assignmentymus and stuff。I've had a long day， too。

 Tuesdays I have。Yes， I have a very long Tuesday， Not that anyone can。But。I feel your pain。

 I think this is my， I do seven hours of teaching and three hours of meetings on Tuesdays。

 and I am exhausted by the end of it， so。嗯。There something wrong with the slides website。

Seems really slow。 So we're just gonna， we're just gonna pick up with where we left off yesterday。

 P people are biningge watching these。 I'm sorry that you've just wasted like  two minutes of。

You know， trying to click through， I don't know what's happening with the links。

 So I'm just gonna go straight to the P F for now。

![](img/4b7813cdcebb076c3b3883056527f58c_1.png)

嗯。guessss the sights down。Oh well。 So where do we got up to yesterday day was we went through all the virtual function stuff and we got to。

 I believe。Around here was regard to creating polymorphic objects。



![](img/4b7813cdcebb076c3b3883056527f58c_3.png)

Soll pick up there。嗯。Now， again， a lot of these examples are kind of a little bit theoretical。

 There'll be a couple of things we can poke around within in V S code， but。Yesterday。

 we talked a lot about how。We can't do things with。Classes is in C plus plus5。By value， right。

 we talked about the object slicing problem when we talked about。

 we either kind of got to pass things by reference or we got to pass things by pointer and。

A way that this really manifests itself the most is actually when you're storing lists of objects that may potentially be polymorphic。

Objects that you might yeah again， experience the slicing problem with。

What you would do in a language like Java is you would simply do something like this on the left。

 you would say， oh， I'm going to create a vector。And then I'm going to push three new classes back to it。

 So just to be clear at the end of line 7 here， I've got a standard vector of type base class and then I have three objects that I've created and pushed to the back of that particular vector the first one has a static and dynamic type of base class the next two have a static type of base class because they're in a vector of base classes and a dynamic type of subclass in these cases so typical polymorphic thing you've got a class and a subtype or something that has all a common parent and you want them to be stored in a vector of the same type。

The the problem with this， though， is that because everything in a vector is stored in line as in like by value。

 you're going to run into the object slicing problem here。

 The other problem is that you can't store references in vectors， right。

 you can't have a vector of references， I don't remember the detailed reason why that is。

 but C plus plus just doesn't go too well with it。 So because of that。

 it means that if we want to store。A a list or some kind of SL container of polymorphic objects。

 We can't use references ever， and we can't use values for polymorphic objects because of slicing problems。

 So we basically end up having to use pointers or， even better smart pointers。

 So if you are storing lists of polymorphic objects， This is how you're gonna end up doing it。

 You're going to end up doing the exact same thing here。

 except that the construction will be similar to what we've done with smart pointers where you'll be making a base class and a subclass by make unique instead of by reference or anything like that。

 So that's how we go about it in C plus plus。

![](img/4b7813cdcebb076c3b3883056527f58c_5.png)

Okay， this appears to be working now so I can。

![](img/4b7813cdcebb076c3b3883056527f58c_7.png)

Get onto it。This is just another example to chat through some ideas。

When we think a little bit more about inheritance and constructors。

 we did mention before that every subclass constructor must call a base class constructor。

 so if you have a class B like subclass that inherits class A like base class。

 then as part of the construction of that subclass you need to delegate or call or not delegate specifically。

You need to call the base class constructor。 We mentioned this yesterday because in a case like this。

There might be a private field like in member， which you don't know how that's actually how that actually works。

 And you can't construct it yourself because it's private because remember private things can't even be accessed by a subclass。

 So you need to call the base classes constructed because this classes itself has some assumptions about how it's built。

 So the constructor does need to be called there。 And you can see this happening in these two cases here where I have a subclass that。

I'm constructing with an int member and a unique pointer R value reference。

 which I'm going to put here， and you can see that I first call base class on member。

And then then I do uniform initialization on the pointer member here。If I just try and do this。

 it won't work because this is private。Number one， like number one。

 this won't work because it's private。 If this was protected。

 it would also still not work because I would need to be calling。

I'd need to be calling the constructor for the parent， and I'm not。

So just keep that in mind when you're creating subtasses as they always need to call。The， yeah。

 the parent class。In terms of destructors， there's a few great questions in the week10 shoot about destructor order and stuff like this。

 like which constructors are called which destructors are called so I'm not going to go through it in much detail in the lecture because that's a lot of fun to do in the shoot。

But it's just something to kind of keep in mind because when you， when you do something like， say。

 okay， I'm gonna create a new base class like this。Obviously the base class constructor gets called。

 so any code you have inside the body here will get invoked when you do something like do a make unique of a subclass it's important to remember that that constructor flow will not only execute the body of your subclass but because it calls the base class it also executes the body of the base class。

So that's why you'll see there's like a lot of chaining that happens here because remember again a subclass is just a base class plus more。

 it is the entire base class plus more， it is not a version of it。

 it is it plus more so and then the kind of last comment we're going to make on constructors and destructors before we move on to static and dynamic types is that。

You should always make your。Destructive virtual。When you expect it to potentially be inherited。

 that's what we talked about yesterday。That it will compile without that， though。

The way we've set up clang and stuff like G++ just compile that fine。

 but the clang warnings is there as we have expect that to be virtual it's good practice too because like a destructor is a really critical function that if you don't make your destructive virtual。

 then what happens is all of your subclasses have no capacity to actually manage their own objects。

 if they need to do any kind or reference count or anything。

 so if you don't make your destructive virtual then you're really inhibiting the extent to which your class can be effectively inherited。

The other thing that's important to remember， which I think is a relevant note here。

 is that when you declare a destructor， even if you just default it。

The second you do anything like this， whether it's a body or just a default。

 the move and assignment construct sorry the move constructor and assignments are no longer synthesized as well。

So you actually will have to explicitly default them。

 so the reason you have to be careful is because if you just have a class remember the compiler will generate move assignments。

 move constructors， copy assignments， copy constructors。If you。

Explicitly define or default your base class， Then these will no longer be synthesized unless you default them。

 so that can be another thing to just keep in your mind。

We talked about static and dynamic types at the end of yesterday's lectures and static and dynamic bindings and stuff。

And I gave you a few examples of that。 And this， this piece of code here is where we can dig a little bit deeper into those examples。

 So I mentioned yesterday that static type is the type that something's declared as。

 I refer to yesterdays。 you can just look at the left hand side。

 So the static type of a given name is just what's declared as。

 The dynamic type of a given name is the type of what object it references or points to basically。

 So remember， you kind of have these three different cases。

 You kind of have you kind of have cases where you're dealing with value directly。



![](img/4b7813cdcebb076c3b3883056527f58c_9.png)

![](img/4b7813cdcebb076c3b3883056527f58c_10.png)

You're dealing with cases where you're doing pointers or references。

 so these are the different ways you can deal with subclasses。With anything by value。

 you obviously have the object slicing problem which ruins pretty much polymorphism outright。

 but also static type is always the dynamic type and this is actually because of the object slicing problem like with values like if you know if you have a standard vector of base class right。

And then you actually go and push three things to it， because if you're copying them by value。

 they all get sliced， right， Every subclass or base class gets sliced down。

Everything in that vector is now a base class in reality。

 like its dynamic type ends up just being the static type because that's all that's there because any any subtype was just cut off and sliced off So for values for any kind of you know store polymorphic objects by value。

😊，The static type is always the dynamic type。Whereas when you store by reference and pointers。

 you don't have that problem and this is where you get that case where like sometimes the static type does not equal the dynamic type。

Right， so in some of these cases， that's true。

![](img/4b7813cdcebb076c3b3883056527f58c_12.png)

If we look at a piece of code like this， we create a base class here that is。Both static。

And dynamically type to be base class。Right auto auto pretty much ensures that the static and dynamic types the same because what does auto do。

 it makes the left hand side type be what the right hand side type object is。

And you can actually see this here as well when I say auto subclass equals subclass。

 the dynamic type of this is obviously subclass because that's what it is。

But the static type of subclass is also subclass。Because auto just looks at what the right hand side is。

 And it's the same thing here。 when we copy subclass， we get the exact same thing， the dynamic type。

Of what subcopy。Is a sign too。嗯。Is a subclass。And the static types is also a subclass。

 General speaking， all of this is really easy if， you know。

 the type you're defining something as and what it references。The are the same thing。So。

Then we get on some more interesting examples， such as I want to create a name， a new object。

 a base to base object。That is a reference。This is an interesting way to do it， but yeah。

 I want to create a base to base vert name that's a reference to a base class。

 and it references the actual base class object I created previously。 So in this case here。

 base to base aesthetic static type is base class because's what's on the left hand side and its dynamic type is also base class because that's what we assigned it to。

This case here， we have。A differing between static and dynamic types， because base to sub。

The static type which is on the left hand side or what we declared that name as is a base class。

 whereas what it's essentially assigned to is a subclass。

So that's where you start to get that difference here。嗯。

If you try and do things the other way around， like you try and say。

 I want to have a subclass reference。To a base class， that doesn't work。Naturally。

 because a subclass is a subtype of base class， so you can't have like a subtype point to its parent type。

And I hope that makes sense too， because you know if the static type of sub to base is called subclass。

 that tells the compiler that you can call any subclass function on this object。

 like that's kind of why polymorphism works because even in a case like this where you have a subclass object but it's being kind of referenced by a name that static type is a parent something smaller。

 it still works because it's like the only functions you can call on base to subvariable are the base class functions。

And the subclass has all the base class functions， plus more。

 So it's like you're guaranteed to always have a valid function。 But the other way around。

 not so much the case。 It's a bit like in the previous examples we had。Here， it's， I mean。

 there's no members here， but it's like。if you have a subclass that is statically typed as a base class。

 you can still call base class functions' because it inherits it。 but if you have。

 if you tried to make a base class that's statically typed as a subclass。

And either you then tried to call a subclass method on a base class object。

 it just wouldn't make any sense because it just doesn't exist。嗯。Yes， and。

Probably the only kind of interesting thing here。Is that if you look at this last example on line 14。

 the reason this one's interesting is because on line 9 we had a we created a new base to sub variableable。

 I'll just draw this out here。 We created a base to sub variable。



![](img/4b7813cdcebb076c3b3883056527f58c_14.png)

That had a static type of base class。And it pointed。To a sub class。Or reference， whatever。



![](img/4b7813cdcebb076c3b3883056527f58c_16.png)

So we did that here on line 9 and then on line 14 what we're saying is I'd like to create another variable。

😊，Here。With static type subclass。Sure。That reference is base to sub。

 And we know that base to sub here。

![](img/4b7813cdcebb076c3b3883056527f58c_18.png)

Is a subclass。 So in theory， this should work， right。

Like you think this would work because it's now just a subclass referring to itself。

 But the problem is that with C plus plus something like this will fail to compile because I'm pretty sure that。



![](img/4b7813cdcebb076c3b3883056527f58c_20.png)

When you actually like tell it to point to this， C plus plus we look at its。呃。Static type。

 So like it looks to base to sub。 And it's like what is base to sub static type。

 which here is going to be a base class。 So it kind of sees this line here as effectively the same as this line here。

 because in both of these cases， the argument that you're trying to refer to has the same static type。

 which is apparent， which is bad。Yeah。Addd。We talked a bit about this yesterday again。

 so just to kind of refresh， it's like when we when we're dealing with this polymorphic stuff。

 static binding refers to how we decide what function to call it compile time。



![](img/4b7813cdcebb076c3b3883056527f58c_22.png)

And that makes sense why we've been referring to it as a static type， because at compile time。

Like the compiler always needs to know what functions to call。



![](img/4b7813cdcebb076c3b3883056527f58c_24.png)

You know let me go back and find a previous example。Like at compile time。Your compiler。

 when it when you tell it， I need you to call get class name， it needs to know like what。

What type of object it's calling that on it like needs to look at base class and say， okay。

 that's a base class。 And it does all its checks， right that's why we have types。

 So it can do checks， and it can make sure that this is a valid name inside this type and that that's all gonna to run smoothly when the program works。

 So that's why static types matter because it doesn't really matter here whether you pass in a base class or a child of a base class or a child of a child of a base class。

You still。嗯。You're still like you're still checking it against a base class。

 That's why it's called a static type。 It's only then when the program runs。That。During runtime。

It V checks the V table of the object that's passed in。So static means compilation and dynamic means。

You know， during runtime， which is based on the dynamic type。

 which is determined by the V table and all that stuff we talked about yesterday and the advantage of C plus plus is that there is a lot more static typing than some other languages。

 So we do all this static binding for non virtualrt functions。

And we do dynamic binding only for virtual functions。 So， again。

 like we talk about performance and stuff all the time in a language like Java。

 all functions are dynamically binded in the case of inheritance。 Even if there's no virtualization。

 even if there's no like overriding and stuff。 they're all just dynamically binded。

 So that just shifts， again， a greater degree of workload to run time that we could avoid。

Two really important words when it comes to dealing with polymorphism and both the phrase upcasting and downcasting。

 you've seen them already in the example two slides up。

Upcasting refers to when we want to cast from a derived class to a base class， and it's always safe。

 it's what we've been doing most of this course already where we create a dog which is it inherits an animal because a dog's like a subtype of animal and then we say。

 yep， I'd like an animal reference to a dog or I'd like an animal pointer to the address of a dog You don't do value again because of the object slicing problem。

You know， both of these two things are fine。啊。Animal reference equals dog。

 An pointer equals a addressed dog。Sorry。Yes， as we mentioned before。

 one of the reasons that we also like to encourage you to use auto is because auto prevents implicit upcasting from happening。

 because if you use auto in these cases， the left hand side type will always just be what the right hand side type is and you won't do this。

 So that's why it's good to use auto unless you explicitly need to upcast like we've been doing in the previous examples。

 So upcasting is always totally okay。 works absolutely fine。Downcasting， on the other hand。

 is a bit of a different story。 Now， again， we referred to why downcasting doesn't really work before when I said you can't really just。

You know， randomly say that I would like to turn a base class into a subclass。Because if you， like。

 if you were to do something like this， like this is all fine here。 We've just established that。

 But if you then come down here and you say， I would like to make a dog reference。

That references an animal dog or an animal cat。 These don't compile again because when it tries to create these references。

 these the static types of these references are a apparent type。

 That's what you might call downcasting where you take an object and you end up in this case。

 you're trying to refer to something that is that is。More general， less specific。

 less broad than the object itself。 And that isn't good， because this would mean again。

 that if this worked， then if there was a function on dog reference on a dog type that was valid。

 it would imply that you can call it， even if the animal， which is the static type of this variable。

 doesn't have it。嗯。So downcasting is the thing we have to be very careful of。Generally speaking。

 some downcasting just makes no sense， right， Like if you had a。

 if you had an animal class and you tried to downcast it to a dog。To like a subtype。

 that just doesn't make sense。 Like you can't do that。 A dog has more information than an animal。

 You can't just subcast it like downcast it。 like up costing makes sense because you're just slicing stuff off。

But downcasting， you can't just magically make it appear， right。

 The problem is that there are some examples in C plus plus where we do want to downcast。

 And this is actually an example of one of them。That example is when I create a dog。

 say a dog and a cat。Let's just focus on the dog。 I create a dog。I create an animal dog reference。

 which has static type animal， dynamic type dog。 And then I try and have another dog reference。

 refer to that animal。But we know we know this because we've written a code。

 we know that this is an actual dog， it's just polymorphic and it's just got a static type of animal。

 but it's an actual dog， we could turn it into a dog。 It's a real dog。

 so to get around that we can use dynamic casts， so this is another type of cast on top of static cast。

As we just said， the compiler doesn't know if animal happens to be a dog。

 it doesn't like it sees this name here and it says，  look， my static typess an animal。

The compiler doesn't know whether it's a dog or an animal or a cat。

 It just knows that it's static types an animal。 So it's not going to let you by default。

 So you need to give it more information。 So in a case like this。

 if you had a dog and a cat variable and then you created two references to animal dog animal cat references。

 you could try and downcast these a bunch of different ways。 Firstly。

 you could try and create a dog reference。That references。

Animal dog static casted to a dog reference。嗯。If you know， for sure。

That the type you're dealing with is a dog。If it's 100% certain under all conditions。

 then you can use a static cast here。嗯。Because static cast or， they just do it for you。

 They don't do any checking。 The reason we call it static casting is because it happens at compile time。

 So therefore， like， if it's not a dog， it's not going to check it at run time。

 It literally just forces it to be， you can get some really bad errors。

 So that's what you do if you know that it's the right type。

 If you're not sure if it's the right type。 You can try and do a dynamic cast。

 And what a dynamic cast does。Is that when you try and take an animal like this。

 an animal dog and you dynamically cost it， you downcast it。At run time， it will actually check。

If it's the right dynamic type。It'll be。 it'll， It'll actually look at this object in its entirety。

 which it doesn't do it compile time， which you can't do at compile time， And it will say。

 is this animal dog appropriate here， Can I do this？ And for reference types， it will return you。

It'll throw an exception if it can't do it。Right， so something like this throws an exception because a cat's not a dog。

 So when you try to dynamically cast this animal here， which has a static type of animal。To a dog。

It has a dynamic type of cat， so this will throw an exception。

Whereas something like this here will work and something like this here is bad So again is the reason you don't use this one is because if you static cast something that isn't then it's undefined behavior so we don't want to do that because if you aren't 100% certain that that animal cut is actually a dog terms of its dynamic type then you can't do that on the flip side pointers are really similar but slightly different the same rules apply for pointers in terms of like static cast dynamic cast you can see the example on the right to contrast it the only difference with pointers。

Is that。With pointers， if you， if your dynamic cast fails。Then。嗯。It returns Noll， instead。

So returning nu is kind of a better thing than throwing exceptions， right， because like。

Checking for nulls really easy。 You just don't， you dynamically cast something。

 You check if the result was null。 That's easy enough。 there is no such thing as null for references。

 So that's why。That's why we needed dynamic cost。Any questions so far where we're nearing the end we've got。

3，3，3 columns to go。3 short columns， I think。Yep， any any any questions before we move on。

Pying with a rubber band。Oki doki。Well， there's a quick little thing to chat about。

 which is covariance and contravariance so。You can read more about this。Online if you'd like， I mean。

 there's tons of articles on it， you get lots of different things but。

Because you'll see the phrases covariance and contravariance come up a lot in the realm of computer science。

 and particularly with C++ and polymorphism。😊，Covariants are like what a covariant of a particular class or function is is the answer to the question。

 if a function overrides a base， what type can it return。

 So if I have a base class like class base here and it has a virtual。

 which means it can be overridden function called get favorite animal that returns a reference to a land animal。

When I override it。Like I have here here in here。The covariants are the types that it can return。

And the real question is， how do you know what it returns， Well， the return。

 the return type of a function。Can be either the exact type itself。Or derived type。Of land animal。

 So what we mean by that is like the hierarchy is pretty simple right you have an animal。嗯。Which is。

 you know， the highest abstraction。 And a land animal is a particular subtype of an animal。

And then a dog is a particular subtype of a land animal。

 So what that means is that if my get favourite animal returns a land animal。And in my override。

I try and have it。嗯。Return an animal instead， big animal is a parent type of land animal this will fail to compile because not all animals are land animals。

And this is bad， obviously again， because imagine you had a case where you have some code that says。

 you know， base B equals new。

![](img/4b7813cdcebb076c3b3883056527f58c_26.png)

Was it cold， derived。Like that。You could say be dot get land animal， right， and it's like。

The static type of B here。Is a base and the dynamic types are derived。

 so that means that anything that any derived type of that users get land animal returns needs to be something that could at least be a subtype。

Of like what base returns， Because then they're all going to be compatible， right。

 Like if base returns a land animal， then it means it can， it can deal with any kind of return。

 That's at least a subtype of that。 You already again know about this through things like exceptions。

 Like if you have a function that returns an exception。whichhich would be a weird thing to return。

 but still， if it did return an exception， it's like if you tried to inherit that function。

 it could return exception or any subtype of exception。



![](img/4b7813cdcebb076c3b3883056527f58c_28.png)

So in this case here， trying to return animal in our overridden function doesn't work fails to compile。

 trying to return animal land animal does because it's the same one and trying to return dog does because it is a。

It is just a subtype of land animal。So these bottom two work and that's like a covariant of those particular functions。

 Convariants are the same concept flipped upside down specific to parameters of a function。

So the question we ask ourselves for a covariant is if a function overrides a base， right。

 Like here we have this base in this used animal， and you can see that it's a void function。

 So don't worry about the return。 It takes any reference to a land animal。One a override it。

 what different types of parameters can it take in？

The way this one's different is that the rules of the other way round in terms of for a function。

 in terms of contravariance， the。The function parameters can be any type。

That is the same type or a parent type。 So it's the opposite for return types。

 So return types of that type or any subtype。The parameters are any that type or a apparent type。

And you can see in this case here if I try and override use animal。

And I give it an animal that works because it's a parent type of land animal。 That means it's safe。

 That means any particular values or properties of animal here are going to be compatible with that。

Land animal also works fine。But dog doesn't because dogs are subtype。

 So for dog to be a valid parameter here， it would imply。That I could call use animal function here。

 override this one。And。That it could do things that my virtual function can't。

 which would break all those kinds of rules and stuff。

 So they are two concepts to keep in mind when it comes to thinking about inheritance and polymorphism and how that works with both parameters and return values。

A quick note， this one is a super random thing， I always forget this because I don't really come across it much but。

Default arguments for a function for an inherited function， for a function of an inherited type。

 are determined a compile time for efficiency reasons。嗯。Therefore。

That means if they determine a compile time， that default arguments need to use the static type of a function。

This creates some really strange behavior which we'll look at in VS code。

 though basically the takeaway from this whole thing is going to be please avoid using default arguments when overriding virtual functions because you will get strange behaviors so if you're dealing with virtual functions whether you're making them virtual or overriding them don't use default arguments so I just pull this one up。



![](img/4b7813cdcebb076c3b3883056527f58c_30.png)

Default here。Yeah， great。 So you can see here we've got a。I hate the S code。I like the S code。 Sorry。

 I'm trying to offend anyone。 I just。It's too clunky for my liking。

 I know I'm on V lab and don't give me that either， but even just locally。

 it just feels a little bit。unkAnyway doesn't matter。 So we have a base class here。

 and you can see we've got our destructor and we have a print nu function。 It has a。

 has a default argument， prints out base in the number。

We have a derived function print out based on the number overrides the virtual function。

 really simple。 I create my derived。Object。So static type， I mean， I could do this another way。

 like auto derived equals derived。So static type derived， dynamic type derived， easy。

 I then create a base pointer， static type base， dynamic type derived because it's defined as a base。

 but it refers to a derived， and then I call print nu on derived and print nu on base。Now。

 here's the thing to note about this example is that。Both prints are being done on the same object。

Right， so both of these will call the derived printum because the dynamic type。

 which is what determines what's actually called， is in both cases the derived type。

 but pay attention to how the default。Pay attention to how the default arguments work here。Something。

 I did something wrong。We keep clicking the wrong thing。 oh my god。Sorry。Buildill target， heavens。

Is that default。Yep。Yep， so now when I run this。We get derive2 and derive one。

 This is really strange behavior。 So what this means is that at compile time。

Wrong file at compile time， even though these two things end up calling the same function at runtime。

 the compiler bakes in these arguments based on the static types。 So the compiler says， okay。

 derived is a derived class。 So I'm I'm gonna put two in here for you。

 There you go I'll put two in there like that。 Great done。 And then it looks at this one。

 It says base is a static type of base。 So it has a default argument a one。 and then it goes done。

 And then what happens is at runtime， it goes and looks at these two。

 And both of these when it goes through their V tables， they end up at the same function here。

 but they end up getting called。嗯。With different arguments in the end。

 So the point here is that for efficiency reasons， I didn't design the C plus plus compiler。

 So I couldn't tell you more than that。Default arguments are essentially compiler signals， right。

 They they tell the compiler how to prep the code for runtime。

 So that's why you get the strange behavior。 So don't use or avoid default arguments whenever possible when overriding virtual functions。



![](img/4b7813cdcebb076c3b3883056527f58c_32.png)

![](img/4b7813cdcebb076c3b3883056527f58c_33.png)

And then last thing today， last series of slides is。嗯。Construction of derived classes。

 So this is just a little bit of a fun activity。 And this is， again。

 what your ch 10 touches on a bit too， which is what I've said before that base classes are always constructed before derived classes。

 So the base class constructor gets called and then the next thing gets called。

 So if you have something like an animal here and then a land animal that inherits that and then a dog that inherits a land animal。

 When you actually look at the flow through the code。😊，We always call like what we end up doing。Is。

The dog constructor calls on the land animal constructor as the first thing。

 the land animal constructor calls on the animal constructor。

And then we actually construct an animal， and then we actually construct a land animal。

 and then we actually construct a dog。So thats this comes back to those rules you see about like the first thing that your constructor for a derived type must do is construct。

The parent type。It's like the first thing it must do。So。Yeah。

 that and this is the behaviour that ends up happening is that we fully construct an animal。

 then we fully construct a land animal， Then we fully construct a dog。 So just by doing dog D。

 we're going to be calling constructors of three different。3 different classes here。

 And the opposite， I'll get to that in a sec， sorry。嗯。I'll just come back to that。

 The opposite is true for destructors。 So when you do destruction of a derived class。It。

You can see here it actually executes the dog destructor body first。

 so it does all the destruction for dog and then as soon as it's done。

 it calls the land animals destructor that goes and does all of that。

 And then as soon as that's done， it goes and calls the animal destructor So it actually moves through in the opposite order which is really interesting。

 I mean makes sense right it's basic stack philosophy you're building you inside out and then you collapse outside in you destroy yourself outside in that's pretty straightforward。

 And a note here is that if a class is not fully constructed， we cannot perform dynamic binding。Yeah。

 so in this case here I've got my animal class， I havet land animal class that's constructor。

 all it does is called run。嗯。Which just calls this function here， land animal running。

 And then I have a dog dog class that it just calls run as well。

 And you can see here that I'm kind of missing some information like calling the constructor and stuff。

 So when the land animal constructor is called up here。

 the dog part of the object has not been constructed yet。This is a very confusing piece of code。

 So let's actually run this one because I think this might make more sense as we run it and we can look at it。



![](img/4b7813cdcebb076c3b3883056527f58c_35.png)

Yep， so I'm going to build that。I don't know。 This one wasn't meant to be compiled。

 I'm gonna run into a whole bunch of random problems。嗯。

Let's just really quickly try and fix those up。Y。Oh there。 maybe I'll， maybe。

 maybe just for simplicity， I will do this one with。G plus plus sometimes like some of the。

 some of the， some of the things we write for。What would you say， like lectures， they。

They don't work too great with like the Kang compilercause some of the。

 the original code for lectures we wrote doesn't。Just doesn't work basically。

 like with all the the extra stuff。Maybe this was the dumb idea。Silly idea。

 Don't impro you code sometimes。Expected class name before open B。🤢。

I still don't quite understand why that's a problem。Air use of deleted function dog。



![](img/4b7813cdcebb076c3b3883056527f58c_37.png)

Dog， dog， okay。Yep， this is gonna be futile， I think。I shouldn't done that。

 I should have just talked to this point so。

![](img/4b7813cdcebb076c3b3883056527f58c_39.png)

The， the point here is that。When you try and call run as part， like when you try and call。

It's very strange。 It's like if you try and call run as part of the constructor for its parent here。

 So it's like when dog gets。Constructed。The dog constructor calls the parent constructor， right？

The parent constructor up here calls land animal and run。

 but it doesn't really care about the fact that we're dealing with a dog or whatever it's like because at this point。

 the dog isn't fully constructed because you're still constructing stuff。 So it's like。

 how does it know to call this run down here。 That's not even possible yet because the dog isn't fully constructed。

 So the point is if a class isn't fully constructed yet。 none of that V table stuff matters。

 99% of the time， this isn't gonna to be a problem for you because this is very like niche。

 like this is weird things that happen if you do really weird stuff。

 The point here is that you should always fully constructed objects。

 And like you should not call virtual functions as part of your constructor ideally。

 that's the short story here because the strange things happen， strange things happen。

 And in this case， the strange things that we can't perform dynamic binding as we expect。

 and we end up just calling like whatever function is there you know in my own class。

 That's a really weird example。Kind of pondering even if that's worth mentioning next time bit。

Last point on this topic。As if a class is partially destructed。

 then we can't perform dynamic binding， and this is unrelated to whether the deor itself is virtual。

 So a similar thing here， if I created a dog or if I tried to create a dog that dog we get created。

Then， it will get destroyed。But what ends up happening is that as part of the dog's destruction。

You see a similar thing again here where as it because I'm calling a virtual function。

Inside a destructor。That means that while the destruct is being run。

 this object is partially destructed and therefore it doesn't look up any V tables or anything like that。

 it's just going to call the run function that it has available to it。You don't want to do that。

 Basically， if this wasn't virtual， if this wasn't partially destructed。

 then this run function would call this one here because， you know， the actual type of the object is。

Yer。TheThe dynamic type here in this case is an actual dog。

 but similar kind of thing don't get too caught up in the details of this。

 the main point is that if you're calling any virtual functions as part of your constructor or destructor。

 you're going to run into problems， so try and avoid doing that。Now。

 just before we wrap up the topic， because we are at the end of this。

 And I know there was people in the lecture last night， and I didn't put the feedback up last night。

 Are there any kinds of questions people have about。This whole topic dynamic polymorphism in general。

 anything that we've gone through that you want to cover in more detail。 Obviously。

 we have a revision lecture next week。 We'll only probably spend half an hour talking about the exam next Tuesday。

 so we'll have plenty of time to talk about this topic as well if people feel like they need more on it。

But yeah， is there anything else people want to chat through。Around dynamic polymorphism today。

Or would you like to get back to your assignments。Is this key for C++ developer？😊，Well。

 like its it's key for dealing with polymorphism and C plus plus because as you can see。

C plus+ tries really hard to avoid overheads when it comes to polymorphism because poly like runtime polymorphism。

 the stuff you're used to with Java has a lot of overheads to try and figure out what functions to call and all this dynamic binding and stuff。

 So C plus+ therefore tries to do as much as it can feasibly at compile time。

 because of that lack of simplicity， there's a lot of subtleties in what is and isn't possible。

 which is most of what the lecture is about， Like some stuff like this is very C plus plus specific stuff like this is C plus plus specific Again。

 like this is an example of an efficiency。You know。

 it doesn't want to check default arguments at run time。 So that has a weird effect。

 So like this is a relevant fact。 Covariance and stuff， that's more just more general O0。

 Like you could apply that to Java and other things。 Downcasting as， again。

 this is a very spec plus plus specific thing。This one you could apply to kind of you know O0 in general so it's a mix of like O0 and how do I think about O0 and a mix of like how to deal with O0 and C++ but the short answer is this key for a C++ developer depends what you're doing like some people do C++ without a lot of classwork you know like they'll use C++ for really low-lel systems that just kind of functions and like you wouldn't be dealing with classes at all。

 some people would write large scale you know web services that include classes and stuff like that so it would just depend on what you're doing。

Cool。Give it 10 more seconds and then we'll wrap it up。嗯。

I w to try and get your assignment  three marks out on Friday， your tutors Friday or Saturday。

 When I say Friday， I mean， it's on my two due list for Friday。

 which means I make sure I do it before Saturday lunch， long story， but。

I want to get them to you like， you know。Soonish， I mean， thankfully。

A lot of the mistakes people make come through an assignment1。

 so I wouldn't stress too heavily about it。But I think it'll be good for everyone。

 So we'll try and get those back to you Asap other than that， Thanks。

 And I hope you have a oh don't forget to fill out my experience， too。

 I won't tell everyone on that till after， you know。😊。

Whatever it is after assignment3s due because you're all grumpy on the weekend and you're like I hate this course so hot。

 but no fill it out whenever you get the chance I'll send you some reminders in the next week and thanks again to everyone and I hope you have a good night and I'll see you all next week and email you later this week。

 And if you need anything else just post on the forum。😊。



![](img/4b7813cdcebb076c3b3883056527f58c_41.png)