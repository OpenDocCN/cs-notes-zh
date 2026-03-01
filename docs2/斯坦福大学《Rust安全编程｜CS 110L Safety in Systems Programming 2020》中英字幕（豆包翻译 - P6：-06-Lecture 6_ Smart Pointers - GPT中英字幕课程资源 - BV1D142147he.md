# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P6：-06-Lecture 6_ Smart Pointers - GPT中英字幕课程资源 - BV1D142147he

Great， okay， so hey everybody。 welcomel to lecture today。

 I'm going to be wrapping up our discussion of traits and generics from last time。

 and then we're gonna to talk a little bit about smart pointers。 So let's just dive right into it。

 Are there any questions before we begin like about anything。😊，Exactly。

 the box pointer is an example of a smart pointer。 So you're 100% right。

 We've already seen smart pointers。 But today we're gonna talk about a couple of other kinds that are a little bit more flexible。

 But yeah， just hold on to that thought。 So here， this was the example we were starting with last time。

 and let's just zoom in on this matching pair thing。 Let's let's implement something more on it。

 Right， So in case you forgot this is astruct that has two fields first and second。

 And they're gonna have the same type T。 And suppose now we want to implement clone on matching pair。

 right， So I'm gonna dople T I guess， yeah， so Iple T。😊，Kung。For matching。Care to。

I see there's a question in the chat。 Can somebody， I guess yeah，'s， it's not a question。

 Its just me。 Okay， great。 Okay， sounds good。 So the way clone works is it takes it has one function called it's as a function called clone。

 and it takes an ampersand self an imutable reference to yourself。 And it returns a copy of yourself。

 right， So， you know， let's， let's try this out， right， So it should return， you know， a self type。😊。

And it's going to output。Something like this， right， let's， let's see if this compiles， right。

 Let's try it out。It's angry。 It says it expected a matching pair， but found matching pair of T。

 Okay， Okay， that's fine， that's fine， that's fine。 That's fine。 Oh， it's calm down。

 It's just gonna be。 So we actually have a new function defined， right？ So yeah。

 we just have to do matching pair Col and Col and new of self dot first and self dot second， right。

does that look good to everybody？Is everyone happy with this？Okay， well。

 let's see what the compiler says。It's still angry at us。 Okay， and what is it saying。

 it says cannot move out of selfdot first， which is behind a shared reference， right？

 So this is the issue of transferring ownership。 It think we're trying to steal something from our structure。

 things we're trying to rip it out of thestruct。 So what we really。

 so can somebody tell me how to fix this。Maybe with a trait bound， what do people think I need to do？

Any thoughts？So first of all， while I be able to do this for anything。

 can I clone a matching pair containing anything？Or if people want to take a step back can anybody explain like in your own words what the problem is here。

That's it yeah so it's almost as if we're trying to transfer ownership right。

 like when we construct a matching pair， if we look at the definition of of new。

 it takes in an actual T right， but what we've passed in is an ampersand T。

 that's what the self thought first and the self thought second is。That's the issue。

So how do we fix this？And then the reason it's an ampersand T I should mention is that we have an ampersand self reference。

 So I see some things in the chat。嗯We。See what's in the chat。We've got T needs S clone exactly right。

 So T needs S clone。 So the way we can do that is we can say clone。And then。

 you know that that should work， right， Let's try to run it， right？Same， okay， so actually， sorry。

 wait， it's my fault。 actually， I wrote the。Syntax wrong there T has to be here。Okay。Same issue。

 same issue。 So what do I still need to do， right。Becauseuse if we go back to the U32 implementation。

 actually， I guess we didn't have a U32 implementation， but like the issue here is that， yes。

 we see another something else in the chat。You actually need to clone it exactly， exactly right。

 does that make sense to everybody So we actually have to explicitly call clone if we implemented copy。

 then it would have automatically copied it。And then we wouldn't have had。

 but like now we actually have to call the clone function on first and second。

That makes sense to everybody， so let's try this。Great， and it's happy with that。

 And then now if we want to do something like， you know， let like。Pas like， you know。

 clone Ps in a pod， I don't know。 is equal to Ps in pod dot clone。 That should be fine。

 And then we could do something like print andb clone of peas。And then， we should see。

So hopefully I spelled everything correctly there and it won't yell at me。

But you see exactly what you expect right， so we originally had peas in a pod that looked like that and now it looks like that and this is fine because char implements clone so it's all good。

 so it all just makes sense。Are there any questions about that before we move further？

Any questions about traits in general？It won't work for data types that don't implement clone。

 So if I had something， I need something that doesn't implement clone like if I had my point from last time。

 let me see if I can actually get my point from last time。 then it the compiler will yell at me。

 So let me just yeah， me go to the。We just get points。

So our point didn't implement clone our point could have implemented clone。

 but we didn't make it implement or we can take out clone actually， so I'll define point here。

 Does everybody see that， I'm going take out copy and clone we're gonna underrive those and then I will and I should also have my imp here to just so I can easily define points So I'll just have that and then if I do something like let you know two points equal matching pair new。

So， points。New 0。0， comm 0。0。 I's gonna copy that。So if I do that。

And then if I do let two points clone equal to points。qu。

So's what's the compiler going to tell us here，s it's going to scream at us， right。

 It says no method named clone found forstruct matching PowerPoint and current scope。So yes。

 the falling trait bounds were not satisfied right。

 so the method clone exists but the following trait rounds were not satisfied matching PowerPoint。

 standard clone clone。So yeah， that's that's the kind of error you get。

 Does that answer your question？Okay， great。 So we can also the cool thing about generics is that we can also use them in functions。

 right， so I can have a function over generic。 So let's just zoom in on this piece of code here。

 It's a very simple function called the identity function。

 And what it does is it's generic over a type T。😊，And it takes in。

A variable that has this type T and it returns the same type T。

 and it's just returns the variable very， very kind of like bare bones。

 We don't even need any bounds on this variable。 So if I do like identity function of some you know。

110， it's just going to return kind of like the debugging version of that because I had this debugging formatting string here。

 Does that make sense to people。 So， so we can we can just this is sort of like the the fundamental syntax for how you incorporated generic into a function。

 But I can also have trait bounds over these generics， which is super cool， right。

 So if I want to print some something excited， right first off， it has to implement display。

 So I can print it。 But then I can put a bunch of exclamation points after it and a bunch of smiley faces。

 And now it looks like that。😊，Right and this works for anything that implements display。

 so if I implement a display for point， for instance， then I could print my point like this。

So you can sort of see， I think this like ties to like Julio's question from last lecture about like how does this enable reuse it enables reuse because you can do things like this so you don't have to write the same code over and over again Also another point Julio's last question from lecture about trait bounds I don't know if you saw in the announcements but I think it it was Warren and Mark they did some like Googling and they found out that negative trade bounds kind of exist but they're unstable and rest so you like the concept exists。

 I think they want to introduce it into the language but you can't write it in stable Ru right now so that's just not supported。

And there are also reasons why you might not want to do that because maybe you shouldn't be printing out anything if something doesn't support printing to begin with。

 so it's more of a design question， I think。And finally。

 this is kind of this is a new thing that we haven't seen yet right。

 we can have trait composition here so we can use this plus symbol to say that， you know。

 whatever we take in has to implement both display and partial or。

Right and then we're going to print the smaller of the two。 So if x is less than y。

 and the only reason this less than makes sense is because it implements partial ord。

 then we print the minimum is X。 Otherwise we print the minimum is y。

 and the only reason this printing works is because we guarantee that the type that we passed in implements display。

Does that make sense to everybody？Right， so if I， yeah。

 so and then it does the minimum is one right when we invoke it with one and 10。

 If I were to take out one of these， let's just see what the compiler would say。

 it's probably going to be very upset with me。 It's going to say binary operation less than cannot be applied to type T T might need a bound for a standard comp partial order So it's really nice because it tells you exactly how you're supposed to fix your code here and then it works。

Does that make sense to everybody？Exactly。Compamp standard comp partial or。

 So I think partial or doesn't need one here because it's able to infer it。

 If I take away this use statement。Let's see what happens。

Faiil to resolve use of undeclared type or module format， sorry if I take away this format。

 let's just see if it's able to figure it out。Oh， it's because it's still there。I just wonder if。

 if the format。Qualifier there is necessary， cannot find trait display in this scope， right。

 but if I if I did something like use standard format， Col and colon and display。Then it would work。

 I think for some reason， the standard comp or partial or just lives there and it's able to find it。

 But here's another thing you could have done。 Oh it's it's still angry here。Oh， interesting。

Binary operation cannot be applied partial to。Wait。

 that's weird because it didn't need the I think you added the you added the partial or to print excited instead of print in。

Oh， whoops， oh， thank you。 That's sounds a good point。 They both had display， partial or great point。

Great point。Right now it's happy now it's happy。 So yeah。

 so you for some reason like standard format like it's just not there by default。

 you can include standard format and then do like you know or I guess use standard format and then do format or FMT colon and colon and display or you can just use the entire thing because the only thing we need from standard format is the display So this is also acceptable Does that answer your question。

Yeah。Okay， any other questions before we move on so this right here is definitely new we didn't see it last time。

 totally okay if it doesn't make sense yet， but it's a very powerful idea。

 the idea that we can say not only do I want this to implement display I want it to implement partial or。

 I can sort of compose these traits， this right here is called composition。

And we didn't see it last time。Okay， so if there aren't any other questions about that。

 I want to show you an example in a real world system， which， which is exciting。

 Let me just see if I can find that right here。 Actually， before I show you that， I'm going to。😊。



![](img/ec55f5672d2955956bd033a9cf70e52d_1.png)

Talk a little bit about so I need to share something else。



![](img/ec55f5672d2955956bd033a9cf70e52d_3.png)

So。This idea that these are zero cost abstractions in some sense you might be wondering okay like in like not inheritance。

 but like you know this idea of like having traits and stuff like that and rust isn't that kind of expensive and like dealing with generics is there gonna to be some like crazy way the compiler is going have to manage this it turns out that the compiler because it's able to infer types you compile time it's not too expensive to manage this information right so like when you're dealing with generics what it's going do is every time you invoke that generic code for a particular type it's going like precompile a version of that code for that type and it can do this run it can do this at compile time because it can statically you know it is called like static dispatch it's able to determine the types at compile time。

And this is extremely powerful because if you think to like something like you know we've been comparing you know rust to like how do other you know object oriented languages deal with you know things that are like inheritance and and polymorphism and stuff like that And you know if you just compare this to see like think about how C if you had to use a generic link list and C it would be such a nightmare right likes actually had to like deal with this just last night I was dealing with like the generic linkless and C and it just felt so dumb because you had to like it's kind of broken like you have to like put the pointer like you have astruct that's defined as a node and you put like the linked list information inside of that struct and that's how it's generic or maybe your generic data structure needs to deal with void stars and those are disgusting right like you remember void stars we don't have to deal with void stars and rust。

 This is the beautiful thing about rust you never have to deal with a void star it knows what type you're dealing with and it's still fast like you can still write an operating system in rust as we're about to see So we're gonna see an example in a real world system。



![](img/ec55f5672d2955956bd033a9cf70e52d_5.png)

I'm going share this to a different window actually and so there's this embedded operating system named Talk that's used for low-powered IoT devices and it's written in R and you can actually see traits everywhere just a quick point on the last thing with zero cost abstractions when people talk about zero cost abstractions they're talking about cost being runtime cost by zero cost abstractions they're meaning that rest gives you a lot of features that don't cost you anything at runtime it doesn't actually slow down your program execution it does have a cost at compile time like Ru is doing a lot of complicated things at compile time to manage things and that's one of the reasons that rust has a slower compiler than a lot of other languages but it' zero cost in that it doesn't make your program any slower the way that Python makes your code slower or Java in some cases makes your code slower。



![](img/ec55f5672d2955956bd033a9cf70e52d_7.png)

Exactly， exactly， are there any questions about that？So here we're looking at talk。

 it's an operating system written in rust， right。You knowThe whole thing about like compile time versus runtime。

 of course we want to shift all of our as much work as we can to compile time because you only have to compile your code once you can run it as many times as you like So we're looking right here in this a capsule that just means it's like something inside of the kernel。

 This is something inside of the core part of the OS。

 we're not going delve too much into like what the code is doing because it's very complicated but I just want to show you that even in something as low level as an operating system kernel。

 you can use these higher level typing ideas and you can use traits and stuff like that。

 So we're looking at here as an analog sensor right this could be like a light sensor or something look wow we even use an enum here it's a light sensor type。

 There's only one thing inside of it I I guess I'm questioning a little bit like why there's only one thing inside of their enum but maybe they're going to extend this later so like that could make sense and here you have an example of using generics within the struct you have this capital a and this ADC thing is presumably。

Some sort of trait right so ADC stands for analog to digital converter in case you're wondering and what we have here is if we scroll down a little bit。

 we can see， you know Iple。Client for analog light sensor。

 right so there's this trait called client that has a function called sample ready。

 and we're implementing it for this particular type right here。 And then similarly。

 we have another trait called ambient light and we can do something called set client on it and we can do something like read light intensity。

 it makes sense that something that you know that's of this type that has this trait like ambient light。

 We'll have something about reading the light intensity。

 So even in something as low level as you an operating system you want to organize your code in this way。

 you want to make it generalizable in this way to sort of。😊。

You know just like describe what different things are doing right and then if we go to this other example kind of the other thing I just wanted to show you is so here they have like they define their system call interface for their userspace applications and the cool thing about this is that they do this through traits as well so like something as low levelvel grungy and systemsy as as a ciys call interface can be defined using traits and defined using the richness of rusts type system So you have these different functions that describe how you issue system calls you have this thing called subscribe and you have this thing called command and allow and this sort of like defineds how that works。

 And I think you can actually see this implemented on the previous files So if I do likeple actually I guess like drivers not in this particular file but I linked the Github in case you just want like see other examples of this in their code base but yeah you can likeple driver for something。

a particularstruct and now it's sort of it can like interface with like with their Ssca interface so like these ideas are really powerful。

 and if you'd imagine you know writing something similar like this and see you can't get the same level of richness and like descriptiveness with this so I just want to show that they real quick just to show you that it's actually used there if people are interested in like future lectures we could do like more code case studies and stuff like that but this was just a little taste of what that might look like it looks like there's a question in the chat yeah。

 it is really cool right thank you Mark yeaht for sure so I link this in the slides feel free to look at it on your own time just like gain appreciation of like even lowle things like embedded O kernels can be written in rust and they can be really fast and really efficient and the cool thing about talk is that it's actually being used by Google to do a couple of things so there's like a group of people like Google focused on rest focused on talk。

To get that running on like their lowpowered embedded devices and try to like distribute that through。

 So yeah just wanted to mention that so that's it for traits and generics。

 there's still other stuff in the realms of traits and generics that we haven't talked about I included some links in the notes but now you know like the core essentials of what you need to know in order to be productive rest programmers using that So that's super exciting Are there any questions before we move on to smart pointers。



![](img/ec55f5672d2955956bd033a9cf70e52d_9.png)

Okay， then let's let's everybody let's just take like a one minute break and like stand up。

 stretch out。Get moving。Get your blood flowing just。Okay， perfect， great。Alright。

Or I guess the 10 second， 20 second， whatever people are feeling as I try to share my other screen。

 yeah， so let's talk about smart pointers can people people see that。



![](img/ec55f5672d2955956bd033a9cf70e52d_11.png)

![](img/ec55f5672d2955956bd033a9cf70e52d_12.png)

Yes， okay， great。So， yeah。So exactly， so we're going to review box T which Trip already mentioned is a smart pointer right。

 we're going to introduce something called RCT which is a reference counted pointer。

 and then we're going to introduce something called the Refa。

Please again ask questions or alsoll just happily go through the slides feel free to unmute yourself or even like ask things in the chat here's another added incentive to ask questions Ryan said that at the end of the quarter it'll randomly select three people that participated 10 times and it'll make you a custom mug that sounds super awesome right like I might ask myself a question for a chance to win this week's stakes but exactly so please ask questions we really want you to ask questions this be very kind of like sad if I'm just talking to myself so let's's move on here great so box tea you've actually already seen this in the context of linked list which we saw in lecture last week and which you'll see again in the assignments this week as you make it generic。

😊，And the idea is I can have a unique pointer to a chunk of heatap memory。

 which is great right oftentimes I might only just need one thing point to a chunk of heat memory at a time。

 but can somebody mention a couple limitations of box tea？Yeah。Yes， can we use box tea for anything？

Great， so it's a unique pointer。 let's dig into that a little bit more。 is that a problem。

 I can I code like any data structure I wanted just using unique pointers。

I think are you trying to unme yourself？In。Okay。I mean， okay。

 so like sometimes you're allowed to do that like like we can like define iterators over you know data struck like something like our linked list that had boxes in it。

 except we might run into issues with like lifetimes like there are ways there are ways around that though that's like a little bit more of an advanced point but like at what point might I need like multiple pointers to you know he memory that might need to be checked at runtime。

Yeah， did someone， someone want to say some things。Exactly。

 exactlyly what if I wanted a graph like even more so like a dynamic graph where at runtime。

 Like I don't even know when these things are gonna go out of scope right and like or even something like a linked list。

 which you can think of like as a subset of that So this is really tricky because let's just zero on like the doub linked list。

 for instance， because that's a little bit more of like I think like a simpler example but like I don't know which things I'm gonna remove from this do linked list at runtime。

 So I don't know how long I'm gonna to have to keep them around for versus you know before I just had one thing pointing to it So。

 I guess like how do I resolve that， Like what are some ideas people have like should I implement a garbage collector like Ru know it's not supposed to be garbage collected。

 It's supposed to be super efficient So what are some things I can do。😊。

It's that there's only one owning reference to it。 So remember how Ru says that we have like there's like this ownership model right。

 so there's only one thing that can own that pointer to the heat memory。

That's what makes it unique because then once that owner goes out of scope。

 drop gets invoked and you can imagine in the drop implementation for box。

 it's gonna to do some unsafe things right， but it's gonna free the memory right So like this it kind of like goes into a little bit about like a whole like unsafe rust。

 which might talk a little bit about later， but the box interface itself is safe。

Because there's this unique owner and because once it goes out of scope。

 the memory will be freed for you。Does that answer your question or do you have another question？

Exactly right so that's the next thing we're going talk about is this RC thing。

 It's a reference counted pointer。 This is what I do if I want to have multiple pointers to the same chunk of heat memory and so let's remember our borrowing rules we can have multiple mutable references but one mutable reference So the RCT lets you have multiple mutable references to a chunk of heat memory right so you can't modify that chunk why do we need that。

Right， why can't we have one of these be immutable？Or be mutable。

Exactly right yeah so it's sort of this like you know iterator and validation type thing that we were talking about earlier where you know it was like like remember Ryan's analogy with the lawyers and the Google docs and the contracts we don't want a situation like that where you sign a contract but it changes right under your nose So this has to do with the borrow checking rules So okay so you have this RC thing and now you might be wondering okay RC sounds pretty lousy I can have keep allocated memory。

 but I'm not allowed to change it like what do I do with that we'll see in a second why this can be useful and when you combine it with other kinds of smart pointers。

 it can be even more useful and you can get sort of runtime borrow checks in a way but a word of caution you can get memory leaks if you create reference cycles if you need a reference cycle like something in a graph in a linked list then you would probably need you actually need some other kinds of smart pointer types that we won't be talking about explicitly in lecture but I can。

Some resources if you're interested oftentimes when people do really or I guess like sometimes it depends on your style I guess when people do really fancy sort of like pointy things like this。

 sometimes they might even use unsafe rust but this is really a matter of taste This is a matter of style it depends you know do you want rusts compiler to know check everything for you and make and like have these like preexisting prebuilt mechanisms like check everything for you or do you just want to like trust yourself right's it's sort of like a preference of style I think yeah any questions about that。

Does everyone understand why RC can create memory leaks？Like rest is supposed to be safe。

 why does rest allow you to create memory leaks？Why is a reference cycle a problem？Oh。

 what is a reference cycle Anyone want to take a stab at explaining it？Exactly。

 you have like one thing that refers to something else， which refers to the original thing。

And because from each of their individual perspectives。

 you look at the reference counter and you're like， oh， the reference counter is nonze。

 there is something pointing to this region of memory and then you look at the other thing and you're like oh the reference counter is non zero。

 there's something pointing to this region of memory。

 but actually you may have these two things that nothing else in your code base is using like nowhere in your code are you using these two pieces of memory but because they're pointing to each other。

 they never get freed。And it's memory leak because you're quote unquote， leaking memory。

 you're not freeing memory that should be freed。Yeah。

 your intuition is exactly right like you should be able to clean this up and you can。

 but you need a garbage collector like you need a higher level strategy。

 it's not good enough to look at each object in isolation you actually need to look at all of memory to see what is being used and the reason we don't have garbage collection and rust is because it's a very invasive strategy that causes a lot of delays in execution and so rust only has very very simple rules for freeing memory like when a thing goes out of scope then you free it or in this case with reference counted pointers when the reference count hits zero then you free it and you have to know as a programmer that you're working in dangerous territory when you're using RC because you can get reference cycles I mean like another thing I would say is like do you absolutely need reference cycles in the code that you're writing like I think if you're doing something like a graph you can use an adjacency list representation you can just use a map I don't know like Ryan what are your thoughts on this like maybe。

系。How often。Like yeah really crop up for sure and in fact。

 like if you're storing a graph an adjacency list representation may may be faster because you may be storing the graph nodes closer together and so it's more cache friendly because you can load like a huge chunk of the graph into cache。

As opposed to making a lot of heat allocations in a lot of different places and making the computer chase through all the pointers。

 so reference counter pointers are very helpful and very important in some cases。

 but if you can avoid them， you should try to。Right。

 and now we'll actually see an example with reference counted pointers and this is about sort of this idea called。

Persistent data structures。 So what if I told you we could make a linked list that every function on the linked list was immutable。

 It would take a shared reference。 It wouldn't actually modify the list like we had a whole immutable data structure right like that's that's kind of like a weird promise to see right like something like popping from the list or pushing to the list。

 those seem like they inherently have to have side effects。

 they inherently have to modify our list but we can write them in such a way that instead of modifying our list。

 they return kind of like a new version of the list right So if we look at this example here I to see if I can I don't know if I can I'm worried if I like try to annotate it won't。

😊，Actually， yeah， you can you can see my mouse， right？

Right okay great so if we look at I'm gonna minimize this real quick。

 So if we look at this example right here， what we're doing is we start with an empty list and then we push 10 to it right and then we push5 to it and now we sort of have like two different versions of I guess three different versions we have one pointer pointing to this part and we have another pointer pointing to kind of like this sublist。

 this 3510 list and a different pointer pointing to4510 So you can sort of see this is like multiple versions of the same length list and we never had to modify the initial length list right once once these variables go out of scope like when B goes out of scope then this will get delocated by the reference counted pointer because we're going to have a reference counted pointer on this particular piece of heat memory these by the way are always going to be on the heap because we need to dynamically you know manage this but we never have to like modify anything about it。

😊，呃。One way to think about this is sort of like version control like something like you know GiHub this is like an area where this paradigm is kind of useful because you can have like different versions of your code you can sort of see like the code like forks here maybe and this is like what they have in common in their history I also wrote sort of at the end of the slides a couple of applications of this this is also used I think to optimize react applications I like saw a link about that and also used for concurrency you can think about with concurrency this could solve some issues because the issue with concurrencies oftentimes a case that you're like trying to like modify the same thing and you overwrite one another well these kinds of persistent data structures can sort of solve those issues this is an idea that's really popular and functional program by the way so that's sort of like you can so I'm not too aware of like if it's used in like rust in particular for like many like systemsy applications but I think it's an idea that's like。

Important to be aware of。Are there any questions about this。Totally。

 I imagine there are many questions about this。 so please somebody ask a question about this。

Even if you understand it， ask a clarifying question about this， please。

 I this is a super weird idea when I first saw it and I didn't understand it when I first saw it。

 so please ask a question。So merging it， yeah， I guess sort of merging it has like kind of the connotation of like we're we're modifying it。

 I guess one way to think of this is this lets you look at different like histories or like potential realities with this data structure right。

 like every time I add three to it like if I'm adding three。

 it's like what if I added three to what already existed here， I still have access。

 I could still have a handle to what the data structure used to be。Right。

 but now I've handled the history of it in a way。 But this is sort of saying like。

 what if I added three to it， Is your question more about like the application of this data structure or how it works。

Okay， for sure， for sure。 I think this will start making more sense as we code it up。

 so let's actually start coding it up together and it could also be the case that we don't have the time to like do an example with ref cells today。

 but like that's that's fine I can like explain at a high level what they are but I want to spend a lot of time with this to make sure that everybody understands it So I'm going to open this up and then I'm going change what screen I'm sharing this should be enough time let's see is this wait。



![](img/ec55f5672d2955956bd033a9cf70e52d_14.png)

I wanna make sure， I want to make sure it's the right window。 Great。 It's the bigger one。 Okay。

 great。

![](img/ec55f5672d2955956bd033a9cf70e52d_16.png)

Yeah， so does everybody see that？Right， let me just open this up。 Great， so this is essentially。

 you know， this is exactly the same implementation we had， I think it was last week， right。

 except I changed all the boxes and I replace them with RCs That's all I've done so far I havenve't implemented push and pop yet push and pop are the interesting parts of this right so notice we have RC node just like box right we have like box on the type inside of it。

 recall that these are also generic data structures right So R node RC node。

 And then when I create a new node， I do I just theres the same exact thing as before。

 and in order to allocate something on the heap instead of doing box colon colon mut。

 I'm gonna to do RC colon colon mute that does that make sense to everybody so far。😊。

So let's take a look at how we would actually push something to the front。So， yeah。

So this is going to be the first function we're going to implement here。

 So the first thing I need to do is instead of so notice another thing to notice here is that these are all ampersand self。

 I'm not taking an ampersand mute self because I'm not modifying the data structure I made this promise that I'm not modifying the data structure and that's why we can use the RC as is because remember the RC can only deal with im mututable chunks of heap memory Does that make sense everybody so far Great。

 so let's go forward So I'm going to say let new node equals So how do I create a new node Well。

 it needs to be allocated on the heap so I'm going to use RC colon and colon and new。喂。

And what goes inside of it。 So can somebody help me out here what should go inside of my new node。

So we should actually use the constructor of the node， right？So yeah， so you're right。

 so it's going to be a value and then it's going to be some next， right？So we can do node， colon。

 colon new value。And then what do I put here？So need I need next， right？

Of the current head of the list。Yeah， so this is a good question， what I take？So。

 so people's ideas seem to be something like value and self head， right？

And let's just remind ourselves， what is head again， head is going to be an option RC node。

So if I do something like this。You know， what's going to happen， right， Self dot head。

 do I need to do take， right， So take， take worked when we were dealing with。You know。

 it worked so take with the reason we had to do take， if you recall。

 is that we had an ampersand mute and we needed to convert that into an owned option。

RightWe no longer have an ampersand mute。But we can't。

 so take only works if you have an Ampersand mute。And we have an ampersense。

 just the straight up ampersand。We have a shared reference， so we're not allowed to call take。

 but that's a good thought。I think sorry， Julia Huo， did you mention something else？You can clone it。

 Great。 Okay， so， yeah， so if I do not clone。Right so clone。

 yeah it's kind of funny because I didn't even mention clone when we were talking about RC。

 but that's how we get multiple references to the same heat memory if I have one RC that's pointing to a chunk of heat memory if I need a second reference to the same heat memory just like Julio said。

 I can call clone on it right but you should complain。

 you should complain because this is not an RC it's an option RC。Right。

But it turns out that this is also okay because option， if it contains something that's cloneable。

 we can implement clone for it， just like we were talking about earlier， right。

 remember how we implemented clone for matching pair that was like our first example we did today。

Because RC implements the clone trait， we can clone an option containing RC。So that was， yeah。

 it was kind of complicated what I just mentioned， are there any questions about that？

Or can somebody ask a clarifying question even if they understand it？

So recall that option is a generic type， option contains some like generic type T in these angle brackets and remember how I took away the clone from our point and we tried to clone a matching pair containing the point and that didn't work so we can't clone all options。

 you know notably if our option contains something that is not cloneable。

 we aren't allowed to clone it， the reason we're allowed to clone this option is because it contains RC and RC implements clone。

Gotcha， does that answer your question？Exactly exactly， that's exactly what it is。

 This is what we were just talking about in terms of trait bounds and and this is nice because this helps us with code reuse right So just going back to the point of code reuse。

 I don't have to implement clone for option RCT I can just implement clone for all option T such that T itself implements clone This idea is very important for your assignment this week。

 by the way， because we're gonna have you implement clone on the linked list and you need to think about what trait bounds you have to satisfy in order to do that right So if I have a linked list containing things that are not cloneable。

 I can't hope to clone it right。😊，Does that answer your question？Right， okay， great。 Yeah So， right。

 So this is us creating a new node。 And now what I want。 and let's look at the return type， right。

 So the return type is actually a full linked list。😊，So what do we do here？

So I have to construct a new linked list， how do I do that？Exactly。

 so let's use the constructor and news so it's gonna be linked list Actually。

 I'd never created a constructor for linked lists because well we would always only initialize an empty linked list。

 but we're no longer so that's a good thought like that we could use a constructor but but this is only for empty linked lists we could define a new constructor for like semi full linked lists I guess。

 but we could also just use this syntax right here to directly create thestruct like that。So。

 I'm just going to say。That。Right， except now what is the head？So new node。So new node is an RC。

 but notice that our head is of type option RC。Well。

 what's so note new node it was on the right track， it was on the right track。

 we have to turn it into something that looks like the second value right。

 so we have to convince ourselves that this is a new node that is not none， right？

So what that looks like is I can just wrap it in sub。It's some new note。

Does that make sense to everybody？Exactly， right。 So it's some new node。 and then what's the size。

Exactly， so self do size plus1。 Does that look good to everybody。

Exactly because you you 32s implement the copy trade right， and because of that， instead of moving。

 instead of like changing ownership， it's going to get cloned automatically。 Yeah。

 it's a great question。So here we're going to just test this out。

 I have this one test with pop front， so we're just going to take that out。

 but let's just run it and see what happens。So we got some warnings。 That's great。 but yeah， great。

 So this is exactly like the example we had in the slides if you recall that sorry I can't have it up at the same time。

 but we have version 1 is just with 10 version 2 has5 on top of it right so version 2 has 510 version 3 and version 4 both build off of version 2 So if version 2 looks like this。

 this is saying version3 is going to be version 2 with3 added to the front of it。

 and we have exactly that version 2 is 510 version 3 is 3510 and then here we're saying version 4 is going to be the same as version 2 except with4 pushed to the front of it。

 So instead of just 510 it's going to be 4510 and notice how the sizes line up perfectly as well。😊。

Does that make sense to everybody？And I don't know if I mentioned this。

 but like the magic of RC is that once once everything is dropped and once all the reference counts dropped to zero。

 then it knows that it's safe to delocate that heat memory because's longer there's no one looking at it anymore right there are no more pointers to it so then it can just delocate it。

Does that make sense to everybody？And this data structure is non cyclical， it's only linear。

 you can't have cycles here， so you can't have the issue that we were talking about earlier where the memory doesn't get freed。

 it always will get freed。Right， and then I guess now we have like three minutes left。

 So we could implement pop front， or I could talk really quickly about ref cells。 So I guess like。

 what would you all prefer， or I guess like， Ryan， what do you think I should do。

How are people feeling about this， thumbs up， thumbs down， either in the chat or with a webcam？

Exactly， you would have a reference cycle and you'd have orphaned memory。 And that would be bad。

 You can still pull off a doubly linked list using safe rust， if you're interested。

I can post a link to that maybe next week。 I don't want to post a link to it this week because it' it's also generic and it looks very similar to what you have to do for the exercise。

 and I don't want anyone to be like tempted to like copy things but next week I can post an example of a doub linked list in rest and you can sort of see how that works but you have to use other smart pointer types So I guess yeah in the last minute let's just quickly talk about this final smart pointer type called let me actually just share it again I have to share this one great so people see that the ref cell T So this is what this answers a question of like what if I want to have multiple pointers to a chunk of heatap memory but I want to be able to mutate that chunk of heat memory So even by rests borrow checking rules is fine as long as I have at most one mutable borrow at a time or multiple immutables So that's what ref cell T lets us do it kind of lets I'm gonna say like lie to the compiler by。

😊。

![](img/ec55f5672d2955956bd033a9cf70e52d_18.png)

![](img/ec55f5672d2955956bd033a9cf70e52d_19.png)

![](img/ec55f5672d2955956bd033a9cf70e52d_20.png)

Interior mutSo that means that the exteriorotype， it looks like a shared reference。

 It looks like an ampersand， but on the inside， it can change itself。And then yes。

 so can you can have shared references to the cell but you can mutate what's inside of it and its new function doesn't heat allocate。

 which is important to realize， but you can use ref cell T with RC to have heat allocated things that obey this paradigm。

 I provided a link to all the things in rust that do heat allocate just in case you were wondering that's what that is。

And to note this type is safe because it enforces the reference rules at runtime。

 but this is now at an additional cost right so before we're saying rest is so great because it takes all the annoying work and it shoves it to compile time and because of that your code。

 your executable itself is really fast。 but now we actually have to do runtime checks to make sure that we don't have multiple say mutable references to the same piece of heat memory So there are these functions called borrow and borrow mute there are also versions called tryB and tryB mute that will return to you options in case you wanted that style of dealing with it so like the way this works is if I try to take like an immutable borrow with borrow and im mutable borrow with borrow mute then if I try to do that the same time。

 then it will panic and then everything will the program will crash but if I do tryb and tryb mute then one of them like I guess the invalidating one is going to return none。

Does that make sense to people？I can also post some like code examples if people are interested at looking at it more I provided some links at the end of the slideshow。

 but the last thing I wanted to mention here is that a common pattern you'll see is having RC containing ref cells and the reason this is fine is because like I said the ref cells have interior mutability on the exterior they look immutable so that's why an RC is allowed to contain it but on the inside what I could do is I have this RC to this heat memory I can call something like borrow or borrow mute on it to deal with the reference cell and then that will let me have like say a mutable reference to this heat memory and this would be something that I would need say if I was implementing a doubly linked list So yeah you'll see this in fancier data structures that have multiple points to the same piece of data。

So when you're thinking about RefFll， you can think back to the first week where we said that Ru actually limits the space of programs that you can write so that it can guarantee at compile time that those programs are safe。

 but sometimes that space of programs that you write is too small。

 sometimes you need to write something that is out of that space and RefF cell is one of the tools that you can use to kind of break the compiler guarantees and move them to runtime instead。

 so you're not guaranteed at compile time that your program is doing safe memory access but it checks it at runtime and if it ends up being unsafe。

 then your program will panic it will crash。Yeah， and I guess with that we're done for today。

 but please stick around and ask questions if you have any these are super like tricky concepts and and don't worry we'll see the same concepts we'll see smart pointers again when we talk about concurrency in a couple of weeks and that'll be sort of like one of the coolest things about rest the fact that we can use something like smart pointers to obtain exclusive access to a piece of data so you don't have to worry about you know sort of like rolling your own concurrency and stuff like that。

But yeah， thanks so much for coming to lecture today and for asking great questions。than。



![](img/ec55f5672d2955956bd033a9cf70e52d_22.png)