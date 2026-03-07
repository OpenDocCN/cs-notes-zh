# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p15 P16 -BV1qBqPBYEy1_p15-

Igue Thomaseringger， sitting amongst you is an new student who's just joined the course。

 he's actually。

![](img/bef0e2f429e2f84948f0dcf8a8be4e8a_1.png)

The lead implementer and inventor of all of the trouble stuff you saw last week。

And so what we can do this week is， well firstly we have a constraint that a quarter to five。

 we have the survey person coming。Ask you things and just say yes all the questions。Yes。

 and tan what scoring system。嗯。Between now and then。

 I have some material on doing implementing objects and methods in truffle， which we'll look at。

I have the beginnings of the stuff on concurrency in VMs。

 Thomas has some stuff on truffle and the project to Oracle and kind of what we're doing with it and all the various directions。

And we can also do kind of you know a clinic on your truffle code if you need that。

 so sort trying to get the sense of the room， how's it been going this last week and a half with your truffle implementation？

Which how people have got working。Program。Excellent。

 because I kind of threw you in at the deep end last time， you know， to be honest。

You're kind of got them just maybe just enough to actually make progress， maybe not even that。嗯。

Anyone want help？Got questions stuck。No， you need to explain the materialized right so explain the materialized different。

 Yeah， sure。 and I've got just， just to kind of。Be sure that this was doable， I did it myself。

 took a couple of days to get a working implementation。

 so I have that we can look at it's not very fast， it's not optimized in any way but it works or at least it works on a program over now。

So we can use that as a so the materialized frame stuff else。Let's look at that。We're don't have to。

Neurravisscus。Look at that screaming。I'm not going do it。嗯。我先等什么意思啊。Yes。这s错了。昨样去。Not super fast。

 but there's no caching of any kind。🎼啊。哎。啊。清走了呀。事实。为什么不是这样？

So the way I did the scope stuff is I have。A materialized frame which represents the top level environment。

I make that a compilation final。Because if there's only one of them， it's never going to change。啊。

And then I have a stack of a frame des that represent that nested frame。

 I think really I figure out probably。One， maybe two methods。

 the function of the method is a probably two right。

That's a of statements they have their own you know the stack is a nice general solution。

 so I just use a Java u Tinggi to build a stack of frame descriptors。And then when I compile。啊。

Variable。Show that。Yeah， so every node， I have a truleized method， which generates the truphy I ST。

And all I do here is。I look up on the top level frame descripture if it's there。

 I should really go down a stack， but I cheese it so this looks at it's been the top level if it's not declared in the sorry in the in the innermost level if it's not there it goes to the top level。

Which I think works fine for function because you can't nest function right yeah。So and then。

Generates one of two node kinds， depending on where it finds the frame lot。

 So the French lot is then stored in the in the node。 And when I generate。I execute a local。

So here I have specializations for int and object。There I take the frame that was passed in。

 and I do the lookup in that frame if I'm reading in a global。

I just go straight to the top level frame and do the look of that and I ignore the frame that was passed out。

And that works fine。's very direct。あ。What else is the same well we're looking。

 maybe looks bit more after I talked about the。Oject and methods。Okay。

 so the parts that are missing in your implementations， you know。

 you don't have objects and you don't have methods unless you've sort of figured out out for yourself。

And then all the performance enhancements that make those things fast。

 so I wanted to talk a little bit about the object model。

And how you implement objects so truffle that's one of the most recent additions to truffle supports objects dynamic objects with varying shapes because that's the common。

Where things are done in scripting languages like Ruby and JavaScript， you get some。

 you can add and removelo on the fly and that's actually done in real programs and like classB languages or himself where also programming operations are not expected to be happening at runtime。

So you get this abstract class called dynamic object。

And dynamic objects is implemented in such a way that it can track the shape of the。

Actual runtime object and by shape I mean the number and names of the properties and their types。

And if the shapes change as they do in most systems relatively infrequently， you know。

 say not every line changing them and changing them in a few ways。

 you know each path through the program has its own set of assignments。

 then you can it'll record the shapes and it can transition between them and cache them to get fast reading rights as if you'd implemented them sort of in a class-based language so I'll show you some pictures to explain that。

Underlying each object was a thing called storage object。

And a storage object looks a bit like you know a regular object except it has a shared reference now in the object head of this because it's a Java object there's a Java a class that it points to。

 but the way to think of this is the shared reference is a bit like the map in。

 it points to something that is the metadata for head stuff is laid out in here and how to look things up。

And then because this system is implemented in Java and you have to statically distinguish between primitives and objects。

 these things are divided up into sort of a little resource memory resource for where you can put primitives and another one where you can put objects。

 object references， so the GC knows to only look in here for references to objects。

 it won it won't look at this at all you can put floats and loanss and other stuff in there。

And then the shape tells you everything you need to know so what if you need to make one that you know gets really big as you add properties because that can happen at runtime you can be adding variables you know adding item。

Well， these things are fixed in size because they're Java objects。

 but you can use the object storage area to contain references to extension arrays and the extension arrays can hold more primitives and more object reference。

So there's a little bit of a space and performance cost in this relative to a direct implementation as you would do it。

 you know in a VM custom for your language， but this is sort of the best you can do in Java in a generic way because as I said last week your last time。

 know you've got a statically type language at the bottom and you're implementing dynamically tax done。

On top of it and there are going to be places where those things run against each other badly and this is one example where you have some space and speed penalty in the event that you make a really big object now there's enough space in these typically that for most objects you shouldn't be the extensions。

So how do you deal with the shapes and the ship transitions， well。

 as you add or remove properties from an object？A new shape gets generated， is it？

or looked up if it already exists and then the object transitions from one chip to another。

 so assume we're in JavaScript we make an object that's empty。

What that's going to look like in the underlying implementation is a header and a reference to an intership。

And the storage area isn't going to contain anything。Then as we write to a slot。

The new ship will be confusing that says， okay， this ship describes an object that has an X field that's an end sort of stored in the primitive area and it's the zero width。

Index into that area。 So so in this case where the floor is part and that's that's where the。Now。

 obviously when you want to look up an X， you have all the information you need in the share to find which slot in that underlying storage you can find it。

If add another slot。A new shape is generated。You should generate it。

That contains the extra description。And the object is modified when the appropriate awareness now suppose we change the X field to be a string and not。

premiseよ。And what's going to happen is we we generate a new shape。

 which contains X as being stored and as a string in the reference area and the。

This references this d pistoloid there。Iま。O。That clear。Further straightforward。

The ships themselves are immutable。The sort of never change the ships themselves。

 You change only of the underlying objects and they canonicalalize。 So once you。

Want to look up a shape if there's an existing shape that describes the structure you want。

 you find that， so there's no duplication of it。And so that means that the identity of them can serve for equality if you want to compare to shapes for being the same。

 if they're different identities， they have to be different。

And then a transition map is used to connect them together so that when you have a share and you have a request for a property addition or a type change or a property deletion。

 you could find the next one if that transition has already taken place really quickly。

There's not much computation involved first time you have to do some computation and maybe creation of a shape。

 but otherwise no so this is the kind of the full picture you have the storage object over on the left references the shape and then the shape。

References。Through its transitions all the new shapes that it already knows have to get to。

And then often here there are properties， so let's look at each， so each ship has a predecessor。

 which is how you got here。啊，They form a train。And then here's the references to the transitions which take you to all the successes of the descendants in the trade。

And then for each of the fields， which are called properties in this model。

 you have a property object。And the propcy object gives you the key。

 which is you whatever you use to look the thing up the name of the thing， a location。

 which is the place in here that it's stored， and you can have some attributes associated with it too。

For things like， you know， some properties can be hidden。

 they can be implementation only that the application doesn't get to see， you know。

 like in JavaScript Europe， you've got prototype fields and stuff like that。

There's a bunch of variations。And then the alloc there is a separate object here which is used to track the space used in the underlying storage and reshape that as it's needed。

 generate the extensions， if fields have to be generated， reclaim them if they're not needed anymore。

And all of these can be implemented or reimplemented by subclassing。

But this is the generic based model。And then。One of the attributes that's allowed in a property is a shared attribute。

 and in that case the property stored directly in the share and not in the。

Underlying objects so if you have an immutable user level thing which can be shared across all the instances that can go in the shape rather than a copy of it being into each。

It's then that shape transitions themselves。For a tree， the root is always the empty shared。

And as you insert or remove fields， you've traversed down this tree。

And the tables that are attached to each shape are used to look up the next shape if if you've already seen one。

 so here's an example of what the tree would look like。

Having executed a piece of JavaScript or the first three lines that we had earlier and then a couple more lines that make a couple of other objects with other ships and we have one here with x and Y strings and another one with x。

 there's a string and Y that's an int。Then you end up with a shared tree like this so that when you make an object。

It would be this shape and then when you get an assignment to a new property。

 if it's one that you've already seen， you just。Tverse you way down to the tree。

Comping the new the new shape and and。是 were restore attention。

So if you want to actually try and programming this up for yourself。It's fairly straightforward。

You have a thing called object type that your underlying object type should inherit from actually in the implementation item I just use object type。

You make a layout object。Then that can be used to create empty shares。

 so here's how you make an empty one。And then to make an instance of an empty shape。

 you just send new instance to the layout。And then here is the code for。

For doing the updates to add a property with Ne men and Val V。You grab the share you。

The shape as it currently is， you compute the shape as it would be after you value the slot within biggest values from that you can then get the location of where you're going to write the new value in them and then you set。

你八要嘢啊。The slot having got its location， if it's already existing。

 then then's there's a quick way of doing that and then to read a field。You get the shape。

 you get the property， you look up there。The location in the。

In the object and the shapes can be cached， so one enhancement for the fe implementation would be to compute a shape for an object and then cache it with an object node。

So that when you make an object， you just。You already have the shares constant。Okay。

 so once you've got this then。To make it fast， you want to do inline caching。

And Tffle provides a way of automatically building inline caches for you to speed up。

Dispatch and it automatically will generalize your online cash to polymorphic in cash if needed。

In the interpreting you do stuff type tests and specializations and for object property to use sharedgars so if you write a simple class with specializations。

Then。The system， when it dispatches the operation here， that's being implemented。

 it will automatically add in。The， the dispatching appropriate to make online cashching。

So for example， for property accesses。When you write the code。

 it will initially use an uninitialized cache and as you add。呃。More types in。

These gods will get added。Associated direct getss of the properties。 And if you've go megamorphic。

 then it'll fall back to。And the truffle DSL implementation。

involves writing specializations where you put in a cache that says， okay。

 I'm only executing this case when I'm my up brand match it out or cash up brand。

 you can give a limit to how many different variants it will hold。

And then you do the generic version， which it falls back on if the guard。

What do you mean bymorphism I'm sorry， what do you mean by megamorphism is so when you've gotten too many types？

So in this case， if you've got more than three different types。

 it would fall back to the generic case。And then you can do a similar thing using time tests。

To do cash lockup。Okay。Any questions。So in the implementation。

 when you have a guy like up and done good class， yes， is that pattern like specially reckon？No。

 these are just pieces of code that get plugged in at the appropriate places。

 the fact that there is a guard means that the template for a guard test will be generated and in the body of the guard test。

 this code will get pied in for you to say， okay， we execute this test and that user that's how we dispatch between the cache and the uncash case。

Like to implement a full do get class thing。Its like And， all right。

 you look up the enterer word and you look。A class subjects。Is trouble smart enough too。

A get class of。Oh， I see。So the underlying VM。Willll be doing optimizations within that。

Because you just running on top of a j game。It should probably in this case optimization because it's the last year。

我加好啦， o。So when it's compiled， Gar recognizes whatever construct you use， you know。

 in terms of just doing Java optimization of play its。

 it's just seeing sort of this big chunk of Java code that got generated from the。

From the code you wrote with the annotations， and it just does whatever it normally doesn't。Thomas。

 do you want the one Yes， next， I'm ready， I'm ready。Any productivity like that。嗯。反这。

I just put tested five minutes ago，Must work。Oh谢谁。I might need to sit。 Can chair。

ialAnd I might need that。这。should wear this。That什。Members security。Just don't worry。系呀。そださ。我。就把这两。

Thanks。그 you。かして。啊，开始。😊，Like why are all areas now？Yeah。

 you kind of need PowerPoint is encountered in problem。But we don' sense， but you also don't do。

 we don't need to powerpoint for now。嗯。Alright， so。There is one thing about truffle。

 there is a nice little wall。啊。Repository and Gi。Where you can get a thing that's called simple language。

It's on Githubcom， Gviium， simple language。You can and to be really simple to。Test truffle。

Sos some issues so here I just did it on my machine， clean check out， get clone。

And then you download binries for Chium by the Linux or Mac。

And you will unpack these binries to a certain location。And。啊。我白吧。I'm sure it works the the way out。

去吗？Yeahs。All right。😊，大です。Maybe just don know it is。

Yeah belongs on the right on the other side of put on the。I'mBcing where the heads。うっかりした？

嗯Ping right啊。Yeah， and downloaded this thing， I built it and this is my director here。

 which is my simple language directory。And the nice thing about this sample language checkout is that it also comes with some command lines that should easily run you some of the programs。

And the simple language is our example language to demonstrate thoughtful features。

I can show you here like example， loop dos L， it looks a little bit like JavaScript。

So it's just less complex。And I got here a loop that I'm testing。

 I got iteration number of iterations， I'm using the test function here， which is a loop。

 but the test that are smaller than。1 million。And what I can do is I can just hit dots slash run。

 and then let's say here example loop。DotSL。And what we're going to say is that while we get the number of iterations。

 we got the first two iterations， which are kind of slow because we're running an interpreter with 96 milliseconds。

And then we get the line that tells us that there was a traffic optimization done。

And it tells us here like EST size besides a number of EST nodes in the method。

It tells us then how much the long the compilation took here， a couple of hundred0 milliseconds。

And it tells us that the resultinging code size was 4 at nine machine instructions。

And after this one gets done， like the third situation is a little slower because we also need to compile。

 but afterwards。They get a huge speed up for the same program。And。Yeah。

 so this is this is one of these example programs here。

We can look at this program here now in different ways one thing is to look at let's just let's just skip the middle there and let's just go to the bottom layer let's just see what comes out of this optimization and what you can do for this is you can see run underscore core assembly。

And this would run the same stuff。 it's just that it will output the assembly code that was generated by trial4 when it optimized that method。

And so now you can see that this thing is real like actually。And。

You need to know a little bit about hotspot assembly to pass this correctly。

 but I will explain that here in a minute。So this first headers here is just some hotspot headers that make virtual dispatches and hotspot faster under all normal circumstances you would enter the program at the very entry point。

And you see here one first thing here， anybody knows what this does。Yeah， Mari knows that。

 except for Mari。This looks really strange。 we just entered the method and now we are like what and a quick question。

The syntax is it？The sometimes it' destination and this is like its destination or it's destination source so this is that doesn't help we're seeing it your from。

まける。So that's it's moving to。 sorry， yes， yes。's right。 So is yeah， this is， this is what you。

 this is a destination of this of operation。 And this is the source of this operation。 So we are。

 we are loading from this address。 and we're starting to R interesting enough。Yes。No。

 I don't think that's true。 Me is subtracting from the strike pointer。Yeah。

 exactly that you're right， It's actually the other to be wrong restoring them， restoring them right。

 Thank you。Yeahre this so we'reoring our reaction into this thing。

 so what is theian R at this point in the function？是是。I mean。

 it may just be storing because it doesn't know if it's used or not so。Yeah， exactly。

 but why is it just soaring and disappear？Excuse me。

 bias storing the disasters because so it can restore it after it comes back right after it returns whatever。

 whoever is using RA else stinks as RAs。Well， it's Amazon College Bank of stack limit。Yes。

 it's like a stack camera so that you don't push beyond a particular good point。 Yes， correct， A。

 Yes， so what what we're do here is this so calledled stack pattern。 We are。

 we are testing a couple of pages down the stack。 So we are sure that we have enough stack。

Because in Java， if we don't have enough stack lefts， we shouldn't just crash。

 but we need to throw a stack over exception and the code for throwing a stack over exception itself needs some stack。

And therefore， yeah， you better test where you got up， right， so that's the stack bang。Anyway。

 so there's no mapped page or that location so you got a traffic Yeah exactly you would get a signal。

 you would get a signal， you got like usually yellow pages。

 red pages like you got these pages are protected and you got a signal and in the signal handle you then make sure that you will scroll exactly so this move fail you have like a type offlow type offlow。

Like if this move， if this move fails， there's going to be a signal handle track， right。

 and the signal handle is for the action。And for throwing this exception。

 you're not executing Java code， but you're executing native code， C++code。

 but this code still needs the correct amount of stuff。So is this a safe problem， it's a step？

I'm very interested in this， the most straightforward way of implementing this。

Its to do a compare against the end of S。Andside to rely upon the signal。

How much faster does it go to each district？嗯。嗯。You doing products， right？little one another one。

In particular on modern In systems， Intel systems not a lot right the thing is just you we would need an actual test and an actual conditional jump which could take up space in the branch predictor in particular if the branch predictor in Intel sometimes has a coarse graity so if you this branch this predictive branch could like basically collide with another branch that is nearby。

And yeah， so there is corneral cases where it can make a difference。I wouldn't。

I wouldn't mind puttinging as a comparison， but on the other hand。

 this way you can have my nices questions to students。Yeah， anyway， so。

Yeah this is source destination source destination because we're moving your zero to the register zero to the registrar and on and so forth。

 but now we need to find that loop， let me find that loop this is usually a little awkward here but we need to find the back jump well this is the back jump。

Because here we jump from B3 EC to B。To 6，3 C 0， right， and C 0 is here。

So this is our innermost loop， this is the loop which corresponds to this。But I think she's get。嗯。

This is the loop which corresponds to this loop here。Simple language this is the loop。

 which is this division known as this one Yeah， this is the loop that this is the loop which just sums up I it sums up the sum and it sums up I always does I was form and it does the comparison against So this is the loop So now we look at the machine instruction that the interpro is going to perform for this loop and the first instruction again looks like oh awkward right。

It does a test of E X。And some other place。What is that吧。What does the test instruction？

The test instruction is comparing this， but actually we're not using the result of the compare。

 which is comparison。What to say。So it seems again are you out of instruction space， for example？

But yes， still， it's still like kind everyluing。ItNeed to make sure you don't are。

The optimization and what do you need to the look， All right。Well。

 like it's like we a managed system。 So we like， let's say we don't know whether this loop will spend forever or not。

 We need some way to。We need some boy to potentially stop the threat。

Because you don't want this thread to just run forever。Then you can just change RB exit jump code。

Yeah， but I mean。Right， but it needs to traps back to the BM so yeah。

 it needs to trap to the and so the way you do is you have in it it looks like you have an interrupt by I guess whatever that memory location you become make it invalid and so it'll trap exactly。

So it's a similar strips with the save point， which this Paul at the beginning of the method。

 it's just here that this is a called a safe point and it's a point where you can stop this thread if you want to make a chiicy。

Because I need to be able to make G quickly in particularly if I have a low latencycc so I need to be able to stop this right。

And I would stop this thread by protecting this memory address here。And then。

There will be a trap and there's a trap bring me to the signal handle and it will stop to swear。

 but they can come back。So this is the so-called safe point instruction to being able to loop。

 so that's just a useless type of stuff， but it doesn't actually work right。

 but it's not easy it's in the sense that it allows us to keep the system like snappy。

Because when I request that you see， when one spread request that you see。

 the other spread needs to be as fast as possible。So buying test versus like a mode or like just a load I would like test is here the smallest number of machine code instructions that you can get。

And in particular， test A X， because like Intel sometimes produce is low registers， R X。

 R P X and on force has some encoding is smaller。 So the only， the only reason here。

 you just don't the smallest number of machine code instructions that will。

So about why don't you use tests。For the stock overflow。I guess you could use time。That's actually。

 I don't know。Iの。嗯。I move would be here。 I also find that。I think it does the same thing。

Because you are not interested in there， I'm doing a few steps here， but is this also how。

Tougher assumptions are implemented。嗯。No， but if you are going to embody it an assumption。

You also need to stop these threat。So at the point in time and then the slide would be stopped here。

And then potentially from here， this red boot either continue here。

Or if then the assumption would invalidate these piece of machine code。

 then you would from here time to later time。So yes， I mean， the answer is kind of， yes。

 This is how assumptions are。So one possibility is that the interruptop flap will actually be different in this case here it's going to cause a read。

 so only things that protect breed there you can actually only trap if you' tried to write in this read only。

So you actually call a different interrupt flag when this happens。

So you could have an inter handler completely change on the internet flag rather than on the address。

Yes。Yeah， so all right， so then we got registration number let's ignore for a moment。

 so then we got here this addition of one register to another register and after this edition we have to jump and overflow because in Intel every subscription and automaticrithmetic instruction would set the class and so we can hit jump and overflow to the the optimization handle。

And this it's the sum variable level because here we have another add add one。RCX。

 and this is the I variable， which always has what on， and he will also have to jump on overflow。

 which is again going to the D10。Well， if this is the case， why not just use the loop。

 if you' were really concerned about code size， you should be using the loop X86 instruction。

There's a loop X 86 instruction with both berements， RCX and。

So why aren't you using that instead if you're really concerned about code size？Yes。Yes。

 which instruction so you're having to jump back and you're using RCX in order to decrement。

To increment or to increment， you can use this same mechanism using XA86 instruction。

I do not see that any of the optimizing compilers haveve seen use this type of look instruction。

Hello。maybe be smaller， but I think it's。so what is wrong in this code， which could be improved。

 which I give you is Al cents。 first of all， they're using here add1 and RCX and a little bit small will be ink。

So because you use your in ink potential。And the other thing is that in this case。

 this ju on overflow is not technically necessary because you could prove at this point that this cannot overflow because of these check。

But that's just。Is this prologue the same for？たの？Which problem。There no just this piece of code that。

And mean the thing at the of the method generator code generator code so one thing he didn't say was the allflow checks are here because in this language。

 you have arbitrary precision。And new increments if you all blow vote。

The machine size you go into a big。 Yeah doesn。不不为什么你比。

And then we I jump an over here and yeah register Locator there might be some improvement here possible。

 but you do not see because for us it looks like this mo all useless。

 because the de optimization needs the state from the loop panel。

We sometimes need to keep an old value alive。That is used by the destinations of these chas。

This is why this looks a little bit very awkward and from a reference's point of view。

 but yeah there could be improvements further on this slope， but this loop is already fairly tight。

For what they would usually produce for dynamic language type of。Code。

And this is the comparison then against the constant， which is 10，000 or 100，000。

Something like that and then we jump out of the hip。嗯。

So this is just to give you a little bit of a view on this on this very low level。

 and now we'll give for you a few on how we get from this high level to this low level。

 and we can do this by running。Dumb， and he has a crawfish Elir called idea crfish Elir。

That will give us。They compile a pipeline there。Yeah。哦呀，在在好吧。可ですか。嗯。So。Alright， let's just get a a。

And that's just remove state for now because it's just nice to function of it。ItSll， all right。

 so what we see here first is this is all muscles that would inlines road during the partial evaluation。

So as I call argumentss called proxy， ex generic， ex void and orange of force。

Here it's a historically local variable going through the methods here's。

As a less than node and so on and so forth， but is this is just the whole like in learninging through every method you would step through if you would step through this method。

And， and this is。This is then going here。And at this point in time。

 you've got sort of theed after in linening， which means you got tons of so-called fixed guard nodes。

 so this is the compiler graph of C， you get tons of fixed guard nodes。

 which is always something like， and know this is true and if it slows the optimize。Yeah。

 there's optimize type check and so on into force， yeah。

AndBut what then happens is that the first thing that's done here is an escape analysis。

So we have one object in there， which is the frame object in alpha， right？

And this actually isororing the local variables。And we do not want that object to action exist。

Because if that object actually exists， then every store to a local variable becomes a store to memory。

 I we don't want that， and we don't have that because in the loop。

 if you remember that the registers like the local variables were just in registers。

You were never actually on an object that is always was getting on the heat。

So this is why the first thing we're doing here is an escape analysis that will get rid of this object and just simulate and just simulating the object and just knows。

If I'm deopimizing here， the value for object on these registers。Or in these stack stocks， right？

AndAnd。One interesting thing on this conize is that it allows you to give a diff。

And this shows you the amount of code that is。justから。This shows the amount of code that is deleted。

By the escape analysis。And to give you here just a few， like， about this is a little bit too small。嗯。

Let's z a little bit out just to give you an impression of how much is this。

Like every red node here on this graph is deleted by the initial escape analysis。

 and only the white and green nodes are the ones that survive。

This is one of the reasons like for actually for performance reasons we are currently considering doing this CA analysis during。

During partial evolution， because that might give us for this upper part like probably it2 s。

 you know。Yeah， so basically out of we can also see this in the graph size。

 like after I do all the inlineing note count is 301 and afterwards and all count is 58。Its here。

It's58， this is 301。Because you have just every single store and reach to that frame has been virtualized and connected。

So after that， the graph already looks very same。In the sense that， oh， I mean。

 this is how I suppose scrap should look like， we got to loop。We got here an integer Alex Act。

With one coming in， which is my8 plus one。I got my inteship at ExAC。With this other variable like I。

Because I'm summing up，And。Yeah I got some proxy nodes here that just make sure I know which values are going out of the loop。

 this is very useful for some loop optimizations to know that but they don't do anything I got here of fine nodes which just capture like I got a value which is flowing in from before the loop which is zero and I got the value which is flowing in from the loop which comes from the back。

Yeah， and I got here comparison， I got the loop structure， like the loop begin loop end here。

 and I got here loop exit。And then I returned the value。

 which I returned and in boxed for my box internship because my return value is always boxed。喂嗯。Yeah。

 so so this will already looks very， very much like you can only imagine how from this you would get done to the machine code when you just check right and if I now have a compiler construct and I do like a range of analysis on。

 for example， this this variable here， then I can somehow see that this if is comparing this variable against。

1 million， so I will know that at this point this variable is either a0 or it's below 1 million。

 and then I could， for example， swap this integer at exact theres a normal integer head。

 and then I get a better code。That will give me like 5%。They actually have a version。

 like because the version which is now label here for problem doesn't do that。え不なった。嗯。

This is just and then， I mean， in this particular example， it's not very。

 very useful because most of our compile optimization don't do anything but。Yeah， like。

But in general， like these are the compiler phases that you're running through， yeah。

We know all sorts of conempalization， this lock elimination that is no lock in that graph right。

 we making needs floating below the bar and so on and so forth。

 but this is the tons of optimization that is running through this。And I正。That a little bit bigger。

Which is here， so that the loop looks not fairly similar to what we have。

 it's just that some of the control flow is more explicit。For example， here。

 this vintageage Ed Act is an actual control for instruction， but it has a。True and a false sponge。

 meaning like I was not overflowing。 I was overflowing。And the other thing that's changed here。

 for example， is that the boxing of the integer is lowered。So the boxing of the integer。

 which could potentially really allocate an integer， that whole code is in that graph。

And the allocation here would do pretty allocate to make sure that we。

We get a little bit more performance by telling the processor that this。Sd local buffer is important。

Then we potentially write here the object headers and on and so and we got something else here which is here a slow pass call into the DMm because allocation is even more complex because at the beginning we need to see whether our spread local allocation is actually going to succeed。

 which means whether we are at the end of our spread local allocation buffer and if you have at the end of our spread local allocation buffer then we actually need to evacuate that spread local。

That's spread local allocation buffer and this is standard for。But in this graph。

 you have now a lot more detail than in the original graph。

 and this is where the compile graph gets from less detailed to more detailed because then we can do more。

And this from this， then the register loator， like this is then up probe into non SE form。

 and the register locator is run on that， and then we create the machine company。

What you're showing us here， this is the girl。This is different。Hotspot has two compilers。

 client compilers over a compiler， as is the ground compiler。That's the best compiler in the bill。

 so the golf completely7。Can rideyme totally without hotspot。It can run with subium。

 which is not a project in the lab， but usually it would run on top of it。Uual that's a top。

That's really job。Which parts possible。No， we are only using like the garbage collector from Ha。

 the runtime system from H， and they're only replacing the compiler component。

So does Gro while also do like loop optimization like software pipeing。

I don't know what soft pattern is， it does loop optimization， it does loop peeling。

 it does loop inversion， but you have a check in the loop that you can get out the loop by duplicating the loop。

 it does moving guards out of loops。It will do some loop unrolling。

 It does full unrolling at the moment。 if a loop is only if if it's bound constant。啊。Yeah。

 if we do some loop optimizations， we also do vectorization。

 so if you get a loop that you can somehow vectorize， we recognize the vector。喂。

Yeah and Chd is also an open source project it's written in Java you can download and build it this is the thing that we just hear for the simple language we have prebuilt binaries so you don't need to also build draw。

 but you could theoretical also build Ch and then you could even build crowd optimization for your economic language here because you could plug again。

嗯。Yeah， all right。 So that's some。That's for for this type of stuff here， but let's go back now。

 this was like just showing you kind of the layers that I run after the troff layers。

And I want to share something else now， which is。I get an example program， which is example division。

 but S L。So this example program， it's just running this here ands similar to the previous volume here just in a parameter here。

 which is called divide by。But you to give a bond as a prominent here。Yeah， just for the sake of it。

 but let's say， there's some parts of the program we be one， I'll just give something else。And。

What I can do is I can run this。Ron and then I'm saying here example on this court vision。And。Yeah。

 that's that's just， okay， that's good we get from $99 milliseconds to about1 millisecond here right and now we look at the assembly again。

But now we're seeing this relief somewhere， if if I help me find the loops。

 this is the marker for the allocation code for the bar。And yeah， here's the same point Paul。

 which is a good indicator of probably the start of the loop。And some to jump back。

 which is probably is it discount。He guy。I this is not here。 No， it has to be。 this is7 years。

Imja from overflow and jump， yeah，嗯。But it goes to 818， which it means it goes to one。About。Yeah。

Because we are actually。Interesting。Yeah， I think they're actually comparing。 Yeah。

 we're comparing here actually the value against it。1， so you go what you expecting。

 or maybe I did a， maybe I did a mistake here because maybe I was not。Building this again。

Just try this again。Yeah， exactly sorry was I had to rebuild。

 I was testing this so he got 11 milliseconds now that was this point after our。

But but we got 1111 little seconds now， and if we now look at them Sandra。We should， at some point。

 see here。An ID instruction， actually that's the one I want to see here。

And so we got an ID instruction， interesting enough that IDDF instruction is actually。

 I believe that yeah it actually has all this met data associated with it because an IDF instruction can of course track。

Because you could have。Division by Sira Vi forna signal not Bar ritual。

And allows to continue here that's how we need all of these things like hoop map and values and so on and so forth for display place because we need everything to be able to the optimize。

Okay but now it's still a little bit of truful fun here。

 so the first thing I can do here is I will show you something that's called compiler directives and Pro fun compiler directives and the first one I want to show you is you can do like compiler direct。

The。发 something。Let's see if。Thank you。Canive us this。By directs。Yeah， exactly sir。

 This is probably too small to see。 I it place okay。嗯。And right， okay。

 so I was doing compiler directive study in interpreter here。

 so I can in draft or I can check in my code whether I'm running in a draft interpreter or in draft compile code。

And so I can just say you're like， all right。In texture。开起。I can compile this。

Buildil here because for some reason my trip doesn't。啊，Thank Ger。And I can run this again。

And then I will be Indian temperature。Too slow in your temperature。Yeah， it was my second it。啊。Right。

 but then after I am。After I'm done with that。It seems to be my print buffer it's a little bit。

A little bit delayed， but anyway， after I'm done with that once I'm entering the compiled code。

 I'm no longer printing that so I can I can distinguish code that should run on an interpreter from code that you run like。

As a business， I can also see like compiled vector in compiled code。

Which will do the actual opposite， which is going to be。It going be very slow。 all right。

 the is slow。Oh yeah， yeah。 now we are like， you know， now we have to the compile code。

But this is just for you to be able to distinguish stuff I only want to do at the beginning。

 or I only want to do in the science。Anyway， so you're going all this， but let's just。

 we have this intesure left divided by right and we want to do an optimization here we want to speculate that we know the value of the right。

Partly and the way we do this is we introduce here an integer which is going to be add compiler。

 The first thing is you see here like this is compilation final because I want the compiler to take the constant value of this field when it compiles as the compilation panel I say long and this right value here。

And what I willll do is that。Well， if my right equals my right value， which is like I'm actually。

My speculation was okay， then I will return left divided by right value。So that and otherwise。

 I will hear say， all right， I will do here compiler directive。And I will go here。

 transfer to interpreter。So， I will。I will transfer to interpreter and I will here assign my value to my right value profile。

So this would be the usual code， have some I have some speculation。

 my speculation on my profile here is the right value。

And I will test whether speculation holds if that holds。

 I know that I can do that divided the right one。And if it does not hold。

 then it yeah I will assign the new speculation。So this is will be the usual code and if we run this now on my example division file or I need to build again。

Let's build that and to run the example division Yeah。

 suddenly and a lot faster because suddenly I can speculate that my division was one then the whole division falls and and in the code is only the comparison but my my speculation yes this is the code we saw just before I will show it to you again we can run assembly example division and we will hear somewhere have。

Have here is。Yeah， this speculation that I'm value bond so this speculation and this jump here to the interpretter is actually corresponding exactly to this code I'm executing right equals equals one equal one is our speculation and then I'm going here transfer to interpreter。

All right。What is wrong Mr this good。The right value you change too。

Right good excellent excellent well， I that a thing here if the right budget changes too frequently。

 we're always going to the opt and I want to show this by just having a little bit of a slide modification of that program。

 which is also here。Example division of polymorph。Where I'm just giving out of12。

12 always is the right value to that function。And if I'm now running this thing。

Then I will be very disappointed， because。😔，Yeah。And it's actually， all right。

 I'm not slow and I'm optimizing and then if I'm hitting my optimized case。

 I'm fast like one millisecond。😊，But if I'm not hitting the case， I was optimizing for I'm slow。

 I' I can handle this。诶。But。I did hear something， which is。I did transferred to interpreter。

 which means I'm just transferred to the interpreter I'm not actually invalidating my profile。

So you would do this when you say， I assume like there should be one coming if there's something else coming。

 you going to the slope， but I still want to keep speculating that bond should come。

And I can quickly change that usually I would actually the correct thing to do here usually if the code would be correct。

 would be to say transfer to interpret and embo it。So this means I'm going Sw to interpreter。

 and' at the same time telling that the discomplied code looks fishy when should be thrown out。

What is going to happen now is that the。And I can run this。So now like I'm hitting my optimized case。

 maybe bones here， but then I'm hitting the unopimized case I'm trying to interpreting valid and later trules things again this is hot and I'm entering a recomplied loop。

Okay， so this is bad。So what I want is， I want to gracefully degrade to a non optimize solution if I got such changing values。

I have a so if you bring up the code again。嗯。Before you hand invalid invalid。

You still have that line that says right value is equal to write。

Ians you're overwriting your cash value。So， then。In it to work properly。

 wouldn't you have to redirect the code？As it's already been line。

I mean in this previous this version I had only trans interpret so in this previous version I only had trans interpret which changes then the value of right value like the optimize code is never actually reading right value as a field。

 it has already decided right value is more。So just because you changed that environment here。

 doesn't mean。This will give a different result because at the point in time when you do the compilation final。

 it means that at the point of compilation， you disasociate the access to the value because at this point you just say。

 oh， I'm very accepting the value， I think this is one。And I'm just replacing it as home。

And so any further stores by give us no update。嗯。We did have this annotation comp in the final case but you still had right is equal to equal to right value。

 would the generated code actually load right value from the memory and comparison。

But then you wouldn't get any optimization because then it was still just load divide pressure because the optimization is done because C is able to replace the load to the right level of this constant one and then C see like。

 oh， I got like left divided by one， I can optimize that。

Or left divided by8 can also be optimize because it can shift。呃。Yeah， so， but yeah。

 were not that's transparent temperature better anybody it。Now we need to fix our code。

So we need to make this slightly more complex。So what we do here is we say。嗯。If well， actually。

 if right equals0， it means the right value was never。They say that if right equi Syria。

 it means that right value you was never。O。Never never initialized。 And so what we do here is we say。

呃If。Rightright。It take for0。So now we are the uninitialized case and we want to hear transparent chapters and validate it because it means we were never ever executing the same。

And we are now assigning just by the input right， so that's the unized case that's good right so else and now what we need actually is we need sort of a case which tells me like and the generic case。

And I will put the generic case as just like。Private static， final， long， generic。はい。

Equals I don't know。 I will take， I need， I need to take some long value， which I will。

I could actually have an additional bullying here if I wanted。

 but just for the sake of keeping this simple， I take one long but if it just say a generic value。

And so else， if。If right value is not the generic value。Okay。

 so when the right query is not just generically， then I want to profile on that right query。

 then I want this type of code， I want to say it right。It equal equals right value。

Then I want to my trick here， right？嗯。And else， what I want to do is I want to transfer to interpret and validate it。

 but I'm not capturing now the new right value， but instead I'm now saying right value equals generic。

喂。And down there you will keep just in any normal case。

Here I will just keep your return left you by right。As my Miss。So I mean。

 we can make this even clearer by saying like uninitialized， uninitized。Un initialized equal 0。

And here I say equals financialized。And。Yeah， one thing we might still have to do here。

 which is here we have a one corner case， which is like if right equals equals unized， then。

Then like right value should be action I mean that doesn't really matter because exhibition by zero so so it's anyway quantitative but what I could still do is like if right equals equals uninialized because I I don't want to keep it being in the unitialized statement so I could say you're like right value equals also generic。

So in these cases， I all go to the generic。Should comp。So yeah， so， so this is just on。

On small things though， but here I'm right equal uninitialized。

 I can do that here my uninitialized case I transferred to interpreting body that was never executing this one I will capture the value from the first execution and then if I'm done the in the not generic case I will try to keep speculating but my calculation fails I will go to。

But you can imagine you could do now certain tricks here to say like。

 well I'm just actually this is something I never tried it。

 but what you could do is like I will do is something like I will get the milliseconds where I last that chronic is last occurred and if the milliseconds between now and then is small enough I will go to9 case but if it's too large then I will try to keep track。

So you could do a lot of， because here you get a choice， either go back to generic or don't。

So this is still your choice and you could still do hear transfer to interpret and not invalid invalid and only invalid validate when you are sure you won't。

So once you invalid it once。In this case， it's so you have a really long streak。

 and then you break that streak and try another really long streak。It's slow for everyone。

You could still， I mean， what you could do is and that's not a question， I mean in the in this case。

 you could still do some sampling or something or try like after some time think like， well。

 maybe a try again， right？But this is still a general problem， of course。

 that we're degenerating here， it's a oneway street。Is there like a library for？把申级。Yes。点30度。

Actually， that's something I can show next， but let's just see whether I did here correct and run here the polymorphic example。

No， I don' sorry， yes。嗯。I don't know have to run the pointmorph example。

 or right pointmorph example is slower， but it's still not you know out of pounds and I can run the monomorph example。

Which just give you the best information， so this is what we want to have。

There is a library for this， yes， let's just throw out all of the code。And。Let's see if's icon。啊。

At that one。Pro， it's kind of surprising that the divide is 12 times slower than。

Not the writing at all。Yeah， in Dai， is is a very big chunk of that loop。

 The other stuff was very new。The other stuff is very like here you can create a branch profile。

 but they don't want the branch profile， I want the value profile。Yeah。

 we can create value profile I want to hear a primitive value profile。Aside is to new。Not variable。

 actually， I want to file scientific to field。嗯。So I will assign this to a new little convert variable here。

 which will be final。I have a profile now。I can delete all of that stuff。

And here I can see something like。Long R equals profile that。か。The right value。

Then here just the that part。Allright。Let's see the。But let should build。

 Ill let say the code of this kind is to on the implementation。

You can run the example division as fast。 We can run the example division polymorphic。

It's a those lower。 It still works。So this is this is this is doing exactly that one。

 if you go into value profile the profile， this is。哦，我在这搜是可。我家了你下。嗯。Premitive money profile。

While you。给我发 the Javava。Alright。You can me some version of the same。It's a reason one。Yeah。

 this is approximately implementing the same thing。

 it's just more generic because it's actually working for all of the primitive values here。

But it has this genetic case。嗯。And it has this crisis。And。It has these different profile versions。

 it's cash misses and so on。And the Kashmist goes into the NHS statement。

So this is just the more complex of this， you can find the latest version of this also as part of the Pro source code。

 which is part of the PR Open GDPDK repositor。But it's just using the same primitives。

 I just wanted to give you a feeling for the underlying primitives that this are of fancy stuff like。

Cashs and on on built on because you can build other things with this。

 which would be actually more exciting。Like one of the things you can， I mean， just like this sense。

 like let's say I think one would like to see something which which is test measuring the time between the current exceptional case and the last exceptional case and only you optimize when this time is。

speak。嗯。So there's a couple of things that could be interesting to。Instead of this current。

 very primitive form of like unusualized estate。optimly generally。

This is still the most simple thing here。嗯。The vision is like 12 times slower。

Do you ever know what to do。I've never seen this optimization before。Wow， mean in Ya。

 we can't do that optimization because it doesn't tell me so much I mean。

 it's always good if you have the constant of a division level level。But you can don't。

The device by one。Yeah， division by one is the other thing。 Yeah， but， but actually。

 even if it's division by two， division by part8 right， any part Yeah， or even even like sometimes。

 I mean， compilers to even optimizations like division by 10 and you kind of have just some shifts in the loss。

When division is an expensive operation。Okay。嗯。But yeah。

 I think there's other things that need to be considered。

 I mean this is a tight loop and in performance and tight loops is sometimes very unpredictable。

 like the loop gets a little bit faster larger。Without actual so much additional growth and suddenly it breaks down。

I think what actually happens is that thetel Intel has some units to optimize loops and probably the compiler when it sees a division and the loop fails out。

So what you're saying sometimes with loops in Intel it's very nonpredic because they are running their own compile。

不错。So we are I did a lot of work at some point to try to get one more register move out of a tight loop and give like  zero%。

But on the other hand， the cookie loop one register to move is suddenly give you a 20% because you're falling below some threshold or some also like the thresholds are based on the complexity of the loop in terms of control structure。

So that can also。啊，就是。Yeah， and I mean， on startup hotspot。

 we can do such optimization so much because because it's harder to adhere to the traffic present additional profile。

Whereice here。 It's like super easy。呃。Yeah and this just shows one of these partss of providing。

 Yeah I get one more small stop if you time you want to take a break and then after the break take a break。

这个你不是。还有。Just just five more minutes and then a break， I will then。Because guys not take long。

 I just want to show you why our simple language is better than Java。And so going to better than。

I just get here I should put the generics slide this as you know the pregnancy expressed here in an Oracle so yeah。

 I spent the time writing the Java program which would do the semantic equivalent of our simple language program。

 which is it will try to。But people try to have big integer operations because this is the semantic of our language。

But at the same time， it would try to speculate on。On the value，15 long。嗯。So and so this is them。

 I mean， first of all， it's very awkward to write in Java。

 very awkward to write in the statistically type language code because yeah。

 but still it's kind of doing the thing， right？And。

I got this travel thing here compiled and I run this with one of the latest versions here。

 which is2 and I'm running this and this is my iteration times。Which is。

 but when I'm in the speculation zone here， I'm getting fairly okay numbers with maybe yeah。

 nine millise second。Yeah12 milliseconds， something like that。

 and then I'm running into the zone but I'm still I'm overrunning to pick and tissue and then I'm in this 40 milliseconds。

And I can compare this now with what I got for our simple language。

 which is now I'm now comparing this again the example loop。

 which is the exact same code and simple just one here。And I'm running this here。And。Yeah。

 this is actually the case where I'm not below flow to English I。Yeah， exactly。

 this is the case I'm not overflowing to integer。 So in if I'm hitting the case。

 I'm not overflowing to integer and get down to0 milliseconds here， whereas Java。

 even for the cases where it's not overflowing yet。

But that's not get overped in sure I'm in the three millisecond。But then。If I am。

If I am now running the overallval collaboration。I'm still getting into the same range as Java here if I'm overflowlying。

So yeah， actually a little bit below but the numbers are fairly up and down because the big engine is a lot of our locations。

 so it's like to see time， but yeah I'm here like in the same range of shower here I if I do then kind of degrade。

And that's in general what's the result of this code and what the result should be of this code it's like if my speculation works。

 I can get sometimes even tremendous speedups of 10x or more， but if the optimization doesn't work。

 I'm at least not slower。All right， does that remain break？Thanks for attention。But things。

we were a little bit so I'm going to talk a little bit about concurrency because most of what we've covered so far is language implementations that single thread。

 single threaded techniques， single thread VM， single threaded languages。

Concurrency is a big field and this is an introductory course so there's no way I can be exhaustive in the time that we've got。

 but I wanted to give you some sense of some of the work that's been done and maybe some of the opportunities that are available if you know if you're looking for a research topic。

嗯。Too fast。So。You know it kind of seems inevitable。

 given especially if you're in the hardware world that you have to go down the current path but it is worth pointing out that a lot of projects have survived just fine doing single threading stuff right because you can do federation if you don't have to do a lot of communication between the different threads if you don't have like a big common shared memory pool。

And they're all fairly evenly balanced， running a bunch of Vs in parallel on a node it works just fine and a a lot of implementations have gone that way so you don't have to go down and building a current current system。

嗯。No the word。So you run independent VMs to solve your bigger problem。

So have you're running sale web service。Right and you do you want one honking grip big VM that serves all the incoming requests or do you want a whole bunch of different ones running in parallel。

 you know as independent processes， maybe on independent machines to service the requests that are coming in so it's kind of your federate all of these VMs to give you a big system。

嗯。You know so there are a number of reasons why you might want to do that anyway。

 hardware is really big these days I don't know of any the and it really scales to a maximum node you know that could do efficient。

Ler pause GC on you know terabytes and memory and hundreds of co that's sort of still in around research to do that well and they certainly don't scale the cross nodes so if you've got a cluster。

 you're not going to run one VM anywhere， you've got to run one perform but no one solved that problem。

So you to you need replication anywhere to deal with faults because UV VM crashes and you on they very warm。

Not going to be a very good service。But on the other hand。

 if you really want efficiency and you mean you've fast communication。

Then multi threadreading on a common share pool remembering， you know。

 there's kind of nothing that beat that。嗯。So that said。

 it's a big field and you have a lot of choices and you have to look at the semantics of the language you're trying to implement as well as the semantics of the underlying hardware and try and find a match for the kind of the crossproduct of all that you've got。

 you know you've got attheomyistic requirements from the language attheistic。

Guarantees from the hardware， locking memory model does your language have explicit concurrency in it and you're implementing some of model that you've already been given like actors or monitors or are you trying to introduce concurrency or trying to do both implement an explicit thing and introduce concurrency all of these things are complicated you know and there's many ways of introducing the concurrency and exploiting as well so there's a lot of choices here。

Which is why it's a big field and a lot of these things。

Well these combinations are still not well explored。We saying a little bit about scheduling。

 it's very easy to supply relatively easy to supply a concurrent model for programming because there are programming approaches that are easier for solving certain problems where you write stuff that looks concurrent。

 but it's not necessarily running in parallel。And that was the way， for example。

 a self VM provides that and the small talk of VMs provided that because back then everything was a unit processor。

 there were no multiprocesors。So you wanted a concurrent abstraction。

 but you didn't have parallel hardware。And so in those systems。

 what you route was a single thread at VM that multipleed the single thread resource across the multiple user level threads and that's actually fairly straightforward。

 it's not a big change。To a VM to support that， all the Bhawkk ones did it and the self ones did it。

It's just no， you know。The fact that there's only one real actual thread running at any one moment makes things much simpler。

Of course， when you get into real parallel hardware。

 then you have to deal with a real scheduling issue and this approach of cooperative scheduling。

Kind of， you know， the the experiences is that。You can't really that。

 there have been a number of attempts where people have tried to build cooperatively schedule systems on top of parallel hardware。

But the problem is the underlying hardware and the O。

Tends to be designed around preemption and not cooperation。

 And so there's always some mismatch and stuff fails。

 It would be really nice someone's doing hardware research， Our system low level system research to。

To， to support some mechanisms for cooperative scheduling in the hardware and or OS S， for example。

Years ago， I proposed a mechanism for。Very lightweight safe point where maybe you could basically sell a bit in a register that said。

 okay， trap at the next safe point and every backward branch would look at the bit。

So it's very cheap to do that in hard work， it'sed it's all the patents going to expire soon。

That's how long ago that was done。嗯。So if you， you know。

 if any of you guys are working like on riskk five artrcies actually we going to support high performance of Vs。

 those are a whole bunch of things that have been tried in this field， some of them。

Actually implemented， that technique was actually implemented by a Zooul。So it just work。嗯。

What about concurrency and interpretation Well interpreters are slow so it's not really you're not trying to parallelize the interpreters to make it fast the idea is that know you're spending your time in the compile code you're not in the interpretive code so it's not really a goal to try and make you interpret it go faster through the use of concurrent hardware however what you don't want is for to go a lot slower。

And there are a number of techniques which we've already done and use。

 which you can't really use in a concurrent environment efficiently because they have safety problems。

So bike code are rewriting right you don't want to lock around every bikecode you execute to check whether it's the bikecode that was there before。

 All of these things that involve rewriting the instruction stream at the bike code level are problematic because the rewrites are not typically atomic you know multi byte instruction span we boundaries there's no asistic guarantees usually from the hardware at that level。

 So so all this stuff where you take a bike code sequencing you you know look at it and put a new one in unless it's a one by ride。

How to do that in the concurrent environment。Even the troublele stuff， right。

 the ASTs are per thread because we're doing notdary rides。And those things are not threat it。

 so we run in the systems in the lab where we have parallelism。We were on separate copies of the AHT。

An area for research here is how there's not a heck of a lot known about how threads interact with profile feedback。

 so you've got two threads running stuff， each of them is generating its own profile。

 how do you combine those profiles。To generate code or should you not combine them。

 should you just generate independent code for the independent threads because they might be doing different things that you might have different optimization decisions。

 I might't think of a single paper let's explore that issue。Yeah。

 it seems like an important issue to me。Completely open fail。

What has been explored and hence I can provide lots of slide on is objects synchronization。

 particularly the monitor form monitors have been around since its 70s。

And they hit the big time with Java， which put them in。

As the ob synchronization technique associated with objects and then suddenly you know there was big money in making them go fast。

 so you need to if you're implementing monitors or a monitor like system。

You need to deal with object blocks and fast locking。 So in Java。

 if a thread owns the lock on an object can it can call any other synchronized method and that happens a lot。

And the locks released when the last such method is executed。

 so you know first guy in onto the object。can do what you like and when you exit。

You release it and the next guy can come in。 So you have to count how many nested monitor enters you've got a match up with a monitor exits。

 And I mentioned in the。The early section on Java bikecodes that because those are implemented via separate bikecodes。

 they can be unpaaired in the bikecode string。There's no way you can generate unpaired monitor and exits from Java code。

 but of course if you get whitetecode that's generated some other way。

 they can be unpaired and the implementation has to detect that and throw an error if it gets an exit without matching enter。

嗯。So the simple way to implement this and how it was done in the very first job of VM is to just have a separate lock table。

Which is you typically has into this lock table， using the object ID inside there。

 there's an OS level mutex。And。And that all works， but it's really slow because the hashing has to be done every time you enter dual a monitor enter the OS level mutex is you know I not so fast either and then you' got the recursive things you've got to deal with the fact that you take the walk multiple times and release it multiple times which the O stuff usually doesn't account for so that's easy but it's slow so you want a fast technique and there's been a lot of work on this over the years the papers kind of peter out about。

The late 2000s， but there were a whole bunch of paperss from the late 90s through the early 2000s。

 it seems like we've kind of settled on a solution now。

Which is why I'll describe there are a few variants and if you look through the literature you'll see little tweaks here and there。

 but this is the。the overall solution now the best kind of locking of course is no locking。

 which is the benefit of doing a scale analysis where you inline a bunch of synchronized methods and you know when you came in。

 you grab the lock。So if you can in line a synchronized method， well。

 you already know you hold the lock so you want have to do anything you can just delay the monitor and monitor rights when you do that and that's a big advantage of。

Of escape analysis and Java。But if you need to lock。嗯。

Most techniques rely on observed properties of existing programs。 So in most programs。

 most locks are uncontended。They're acquired only by one thread and released by one thread once a thread is acquired a lot。

 it frequently reacquires it by calling a nested synchronized method on it so you have to deal with。

You want to make uncontended locking fast and you want to deal with a case where you reacquire the lock with nested monurants and monuratorss has。

The contented case。Is not so common。Of once you've made all this fast。

 then the contented case becomes important and you have to deal with that。

 whether there's less in the way of literature around that。So how's it done in hotspot？

I'm going to base on this paper from 2006 there are probably a few tweaks since then and I' time to go a look at the sources to see whether there's much more。

 but this should give you the basic idea。So the tag bits in an object's header word encode its lock stare。

 there are a couple of bits in the header word that are used for various purposes。

 GC purposes and other things so one of these combinations is reserved for GC。

But the other three represent an unlocked object。A thing called a light white lock and then the heavy weight lock is the thing that uses mute accesses condition variables and all of that stuff and has the slow path are contend。

Locks， so what you want to do is go from unlocked to lightweight and make the lightweight locks optimize the uncontended acquisition and the nested acquisitions really quickly。

 And there was a pretty clever scheme devised by Lars for the very first hotpot。

Which is that when you execute the first monitor enter on an unlocked object。

You do you copy the header word into a reserve slot in a stack frame。

 so because you know you're in a synchronized method， you can reserve a slot。

Copy the head word into that slot and it has a pointer to that header word into the existing header word。

And that has the lower order bit set to indicate there's a lightweight lock taken so if you do that CAs and it's successful。

 that means you've acquired a lock and the original header word now is in your stack frame。

If you do subsequent monitor answerss by the same thread。

 you compare to see whether that pointer points into your current stack because you know where your stack begins and ends。

 if it points into like your stack it means you want it。And in that case。

 you don't have to do anything with a lot record， but you do have to do the comparison。

And then if you want to know the number of lock records in the stack， well。

 that's the number indicates the lock in depth in the。

You could release them accordingly as you return from the frames and there's routine and the routine stuff and exempt handling code that does that that looks at the stamp frame knows whether you in the synchronized method。

And does the appropriate thing knows whether it's going to drop to zero， checks the lab record？Sorry。

 it doesn't know it has to check and then copies the frame。

 the header word back in and if someone needs the head of word they can follow a pointer to find out so you check the tag bitts if it's locked and the head of word is that the target and anyone can do that because it's just in memory。

So a further improvement came along。Was to。We to use bias locking and the idea of a biased lock is that the locks kind of biased towards a single thread。

 that thread has a cheaper sequence for locking it and relocking it。Than other threats。

 and so there's an extra be added for the biasable be。Which is down in the Lord a words。

And open these other bits when it's biasable there's a thread ID。Sttooid in there。

 which indicates which thread is bias towards。So in a biased implementation。

 if the CAS were successful， you try casing in the biased version and then if it was successful。

 your thread ID is there and it's biased towards you。And if it's been biased。

 then you don't have to do anything about the lock and and lock operations。But an。

 you don't signal that。But if you tried locking it in a biased form and you failed。

 that means somebody else tried locking it in a biased form and succeeded。

 and that's bad because you don't want to bias an contended lock。So what it does in that case is。

It uses a safe point mechanism to bring everybody to a stop。

 the other guy has you know gone off running with an old lock but biased and you want to undo that。

So you bring those guys to， you bring that guy to us well you have to bring everyone to a stop because you don't know who it was。

 although I guess you could use the threat idea。Just okay anyway。

Implementation brings threats to a stop。And uses the。

compileilr generated debubgging information to walk up the stack and sort of fill in the lock records as if it were lightweight blocks and sets the。

The state to be a lightweight white look。嗯。是 that。So it turns off the bining in the case that it was used。

Incorrly， and that process is of course， expensive。 So if that happens a lot。

 then bulk re biasing is done， which is。All the biasable instances of a certain type are reset。

Because what they found in the paper was empirically， certain types have。

The biasing works great and for other types， the biasing doesn't work really well and so they turn it off selectively by type。

 this is Java object type。If it still is you're getting these bias revocations for a particular type。

 then it does a bulk revocation， it sort of stops everything。

 scans through the heat fixes all the head ofward of all the biasable instances。And then says， okay。

 normal biasing for that type， we turn that off and just go back to the old blocking the slower sequence and this technique。

 yeah why would you do this rather than a transactional memory？

Because transactional memory didn't exist at the time。

 or do you mean software transactional memory no hardwareal。

 no this was this 2006 there was no transactional memory。

There have been a bunch of studies using transactional memory for Java locking。

 it works really well bias now Yeah， I think。I think the results were all very positive and I don't know whether they've actually put it into hotspot for the hardware platforms that support it。

 but。T0 I'm sure it's you know high up on the west I'd have to go look at the sources to see whether there's any any。

Yeah I think that the bias， as it is right now， I don't think if they even part of protection memory will be the same。

Really， at the moment it's really well transactional memory based on the fact that you're probably the one that's people using it Yeah。

 it's the same speculation in effect assumption so it should work really well but transaction what's the memory sta like on the Intel and looks at the internal implementation to see what what you need to keep because because this is just a few bits。

And it might be hard to compete on the memory demand right but then the cost of you don't have to do this re is you don't have a problem right so this they're going into a lot of effort to avoid the case where revocations start happening a lot and you can avoid that。

But whether the fast path is fast fast enough。No， it's always about the same then。 Yeah。

 that's the same thing。 okay same， but。Failure mode is much easier。Yeah， okay。

There were a bunch of studies done at some when there was a transactional memory implementation that was going into an earlier SpRC processor。

But I got cancelled， so。I wasn't very helpful in terms of first five had plans put it in， really？

This would be a good study to sort of look at this again and have a simulation in both directions and see which ones important。

 but it certainly would simplify things。是我。A couple of other noteworthy tricks， so as I mentioned。

 the monitor renters and monitor exits might not be paired。

And rather than trying to detect that in compile the code。

 the approach taken in hotspot is it attempts to prove that they are paired。

 if it successfully proves they are paired， then it generates compiled code。

 but if it can't prove they're paired， it says， this is going to be interpreted。

So anyone who writes funky monitor enter monitor exit stuff where the compiler can't do the analysis and figure out the caring。

 it's going to run slowly anyway， it's just going to be interpreted。Okay， last couple of things。

So code management。And patching in a concurrent environment is sort of notoriously tricky。

And this is mainly。Because they。You know， we do it a lot in VMs and and hardware designers and US designers never assumed anyone would do this alone。

 And so the mechanisms are not very well changed。 you know， in VM。

 you need it in all sorts of places in like caches。

If you're resolving classes in patching code or you're linking to new code or your flushing code code。

 all of that involves code modifications。Even on a unit processor。

 you have to be careful because on a unit processor。

 you unless you go back and use really old unit processor。

 there's a pipeline and the pipeline behind you can have stuff that's already been fetched。

From the locations， you're modifying， so you still need a pipeline for after you've done a code modification before you try executing。

嗯。Stuff behind you。 And that's， that's the horrible subtle book which I've seen before。嗯。

When you're on a multipro of you also have to flush invalid code out of the eyeCs。

 and it's easy enough to flush your own eyecash， but what about flushing somebody else's eyeCache？

If it's coherent and you don't have to do that， that's great。

 but mechanisms for doing this on most architectures that don't have our coherent eye cachees are really painful。

And you might also get the memory model reordering doing weird reorderings on your rights the code。

 so you have to have a code patching sequence。Which is saved no matter what reorderings that happen。

 so you know my recollection isn't the spark manual you have to do this weird patch where you write though。

The instructionsions backwards。In such a way that there's always some kind of a valid sequence with you a skip at the front or something。

 it's really contorted。And in general this is really tricky you have to spend a lot of time reading and understanding the process manual for exactly what's legal most Ioc is。

 as I said assume this is rare and they don't make any guarantees about timeliness so if for patch stuff here the visibility of the patch on some other core it's like well eventually is more what most architectures will say yes。

Is it not use like a mechanism where they just map？Let see。Well， so what you do is。No， no。

 I don't think so。 I don't think I've seen that。 Yeah， usually what you do is you make。

 you compile and generate code in some area of， you know， new area。

 and then you have to patch in branches to that from various places。

 So like if you have a new method and you have inline caches that will pointing to the old method。

 the inline cash has to be invalidd in the branch that's the inline cash has to be patched so。

I guess you could write the whole new code and switch it in， but that's。That's pretty heavyway。

That's a pretty heavy kind of operation。嗯。Usually you just do to modify the rights and you try and put the barriers in to make sure the rights propagate right in the correct manner。

放。一嗯。A potential benefit in a concurrent environment is you've got abundant threads you' can compiles in parallel。

The most high performance VMs now maintain a queue for compilation on the mutassia threads。

A runningunning through， you know， tripping counters and。

Invalidating in line caches and stuff and that generates requests in the compiler they get put in a queue in a separate thread or maybe several threads during the queue run the compiler in generate the code and then you know atically。

Install the code。mIn into the codeVD cache and the lockup system。So the trick there is。

Making sure that the atomic patching is done right but you have to do that anyway for other mechanisms and you also want to make sure that the compiler which is now running potentially somewhat delayed from when it was invoked。

 you know the world hasn't changed so much。Between when you put the thing in the queue and when the compiler actually runs that it gets confused。

 so it has to check its assumptions when it runs。All right。

 are you aware of anyone who does iterative copillation where you run low optimization？Iop this way。

In a queue， usually the lowest optimization stuff is done immediately。 the tier1， tier 0。

 as it's sometimes called， is usually。Literally just in time or just two do they like those those are cud。

 Yeah， Hosp is a conilation care。And it does at increasingly level levels of optimization it has yeah several。

ook several levels。Okay。You're going to probably have some foreign code you need to deal with。

 a precomplied library， say either stuff that you've got elsewhere or stuff that's linked into the VM that's not written in the application language and that might not have save points。

 use its own calling convention if it's foreign code， etc。啊。

If you're calling into that stuff from a concurrent VM。

 because it doesn't have safe points and you can't。You can't do anything really than supen resume it。

嗯。Then what you typically do is you have a barrier that you cross as you exit the VM into the foreign code and a barrier when it comes back in and if you need to suspend it for some purpose。

 you suspend it when it heats the barrier， otherwise there's kind of no point in suspending it usually when it's in native code to let it do what it was going to do it's presumably manipulating its own memory etc。

 you might have a similar barrier if it tries to invoke operations that mute objects in the heap。

 so for example， if you're running your GC。You will close the barrier。

Everything that's running foreign will carry on doing its own thing。

 but if it tries touching the heat， then it'll be suspended until the GC。

GC completes and so you need this locking system on the barrier that make sure you either stay in or you stay out but you don't cross when you're not supposed to。

嗯。That's all I have for this week， next week。I'll look at。

Memory management in a concurrent environment， including a little bit on concurrent G。

We're going to have Michael Vananderba to come in to talk about tooling。

NVMs and we'll do the competition stuff。As well， for the remaining half hour， we can。目嘅。

Code we've got more slides from Thomas。If anyone has questions about the truffle exercise or doing it more truffle stuff or if you're planning to。

Win the competition with your truffle submission。When you need hints， we can help you with that。

I'll release people submit benchmarks by tonight。So you guys don't get flat side of by。其实好边可能去。

然后我们待会。there may be one more reading thing which haven't decided on yet， but that will be we send。

Yeah， because I'm going to try and get to everyone by tonight。Let's say。Right。7左。有了。

Go for your remaining slide。Benjamin response。W to do something where you wind。Performance。Yeah， so。

You don't really have time to do that in this。What I think I'm going to do is gather all implementations of all your exercises。

And。If I can do this without massive amounts of human intervention。

Ourll run each one camp align the curve can measure the performance and report back。

You knowA graph of how things vary for each exercise， but that will be later。

After I've recovered and after， you know I've gathered everything from Patrickrick。

 soll I'll post the results， you know， on the Piazza I see the Piazza website of course will exist more than。

It many years， so I'll post stuff back。系埋呢个 wifi 。And if we find something really interesting。

 we'll write an educational paper everyone once name。Yeah。

I've always wanted you to discern 500 or people。嗯。Pro just做了。All， yeah。

 I have some more high level slides about thequ and Pro projects。I'd like to quickly show you。

This is just an overview of the type of stack that covering with chronicling thoughtful research at orac collapse。

And this includes here some high level language runtime type of research if you're doing with Al。

 Ruby， JavaScript implementation， some craft analytics。Then you can go to lower level on time。

Type of work， which includes partial lib stuff， academic object model research we did。

That also Mari presented some of it today， and then we have some high level compiler construction sink。

These are going into the crowd layer。But high level。This includes escape analysis。

 locking elimination， SSA form，m doing some vectorization。

 getting these key optimization checks optimized。Sort of on this level。

 and then we also have some really lower level compiler construction type of work where it's about getting the register loator better。

Trying to do a better trace allocator， for example。

 for gra and trying to use the spark hardware as good as possible。

But the nice thing about a research lab， like Oracle lab here is that we have experts for this whole stack and we have a project that has span this whole stack with 30。

40 people on。Regarding C and T， these are the main parts that we are developing at ourco year and these are the main languages we are developing。

There's a JavaScriptsco engine， there's a rubby engine， an R engine。And they' are also doing C。

So we are also interpreting C on top of the tro system and then dynamically compiling C。

This allows us to have a safety， for example， the spa checks。

This allows us in general to combine C programs with the rest。

Because we find out that see itself is not enough， he also wants to those pho forran rust。

 whatever we decided to do。LDM bit called Fend， and this is what is currently being workedked on with students in L and Manchester。

And this will allow us to run all of LLVM languages on top of G as well in addition to the E land。

And you can integrate those two。啊。All right， so that's just a high picture。

I was talking a little bit about the Java compiler， the Java compiler。

 this is the U for Open ChK for the Open ChK project。

 you can download build Chrow right imported into clips。And。Yeah。

 it's open source on the GPRV2 license then the main goals for C。

 like the main theme of C is first it has aggressive optimizations as a first task concept。

 so it's really designed for graphs that have a lot of optimizations in them。

And some of our dynamic languages， including JavaScriptscript， we have more。

Guards and actual operations。And this is why it's very important to have the guards of the。

Another focus of grow is it has like the best escape analysis that's available right now。

 has some partial escape analysis that allows you to push the object allocation as far out into uncommon paths as possible。

There's a TC cell from Luckatlo that available as well。

And finally C itself is very modelized a modelular Java application。

 where there's 50 different models， and you can very easily hook in your own optimization phase if you like InterC。

Well， the cover framework， this one is blah on GiHub。

 and this is the URL to the simple language on Github， which I was demonstrating today。

It includes also all the scripts that I was running today。And you can， I mean。

 for the idea of graphfish bus， you will need to check out of G。

Like you can get the ideal graphicualizer and you can print simple manuscripts and also for your own classical language。

 it is maybe a bit bad just thought to download this thing and just swap about the language implementation because you can reuse the scripts。

 which have the commentss in them to print the assembly the commentss to print to the ideal graphicraphual lessons。

For Druffle， the main idea behind it is it's a single definition of librariesmatics ant。

 so if you look at Google V8， if you look at spideridmonkey。

 they all have multiple layers of chit compilers and it's very hard to innovate in these languages。

And this is also at the current point in time via the most complete JavaScriptscript engine that supports most of the ECive 2015 tests。

Yes， so was that graphic on the right accurate if you do all that truuffle It's accurate if you can do all that。

😀は。😊，We have a brain for implementation yes。my laptop，I can tell you it runs really fast。Yeah。

 we love you're doing Hasco， but Hascal would actually be interesting。We have a cultural prototype。

 but it's not poverty yet you also have like some very unusual language in there like actor Yeah。

 I have to admit this is a marketing type of I say of because it would be I would be Wins be I find it unusual if you get any real performance gains on those particular languages。

Hi guys， there's very little dynamics。A agree， I mean， you can get performance gains on C++。

 for example， because even in C programs， more complex C programs would use function pointers。

And when you have functional supporters， you can have a link。

Or this division by constant for example， is also something you could profile in C so even if the language itself is a static language。

 you would think you can get performance gains also we say like the inlanding is not designed to be in any way related to the hot parts of the program。

So you can gain there right but there's some languages out there which are so weird that it seems at the moment hard to see how we could optimize them you would have to change to like garbage blocker for some of these languages because they rely on the fact that they're single right ones so you can get rid of immediately。

And when I take this a good feedback， I will modify that cloud to only the languages that Dfle supports on it because by now we have enough languages and Del that it will make a nice cloud is the this is from the early slides that we didn't have the epi so we were just putting out something。

So I understand that the LM B code implementation is still something that's being developed。

What opportunities for optimization do you see there， Because you're kind of。

 you're down at that level， I don't know you know， if you Yeah， so。

 so this is still developed and but you'll push this open source under the name Su long。

In a couple of weeks， actually。On Gi， so you will see the other。But he starts of it。啊，For LLDM。

 we don't have so much interest in speeding up the actual LDM program。There is two main interests。

 one is we want to be able to execute these LLVM programs in a sandbox without performance。

And there is speed up opportunities because the C compiler。

 if you would put all the bounce checks in， doesn't do a very good job in optimizing that。

 but our compiler can do that。So we will be able to execute the LLVN in the sample。

So no buffer overflow problems and so on and so forth and this can very interesting because like for example。

 the heartbleed bug or something like that that's actually one of our milestones。

 we want to be able to run the code that was causing the heartbeat。

Bg in travel LVN and show whether that this bug would not have been possible。

Because we think we can execute this with a very minor overheadha maybe 10% something in this range。

 because you need some more checks but you can do a lot of optimizations to move the checkzes out of loops to get them out of the way。

 so this is the first interest we have in this the second interest in this is we want this LLVM based approach to help us integrate LLVM based languages and tropical languages。

So here it's about， I want to be able to call from Ruby to a Ruby C extension method without having a call boundary and in particular also the other of around。

We have some really nice feed up through rubby there because， right。

 it's one thing to rewrite all of your inner loops to see。

But then this inner loop sometimes need to access Ruby data structures because you accessing Ruby or already accessing Ruby object。

 and then this access back from C to Ruby is not optimal。

 it's not the best way to access it because the runtime system is really able to generate better waste。

So here it's more about speeding up the integration between those two。

There are some opportunities where you might be able to outperform a C static half of time compiler because of the dynamic。

Like better inlining of the hot parts getting function point crossings， for example， in G I。

 G I is an interface between the GVM and a native code。

 but it's always function pointers like like it's always a co boundary when I'm getting a method ID for a method is chain I always crossing a function boundary。

 it's always an indirect core。But these are function pointer calls that can be with inland caches can actually be combined。

So I believe there is not zero opportunity there， but realistically speaking。

 I don't expect anything。I expect that we'll be able to run this in a sig mode if necessary。

 and we also expect this to bring us these languages together。

We have this structure that have also this nicecing of language interpreterabilityability where it can have one language pass the data structure to another language。

And there we also want to have CN single+ participation。So make a JavaScript object， a pass to C。

 and this C code would then access it。And all of these tricks are only possible if we also bring the C code via LVM into our compile infrastructure。

Right， you have a JavaScript engine， this one is at the moment not open source。

 but we're working on that。嗯。Yeah， but it it's actually one of the most like it is the most anosphertic compli engine right now because for us it's just so much easier to add in these features because it's just an interpreter it's about easier less manpower intensive to add this than I mean I think yeah the most crazy thing I do it's like the engine that's in Safari which is four tiers it's four different compilers like one interpreter is three compilers。

And of course， if you want that to change the semantics of free language。That's four places to look。

嗯。So。Ator， like if you's enough manpower and money like Appleing。

There's ways to overcome that problem， but in general it's still you're from Oracle and you're complaining about Apple。

But you know there arent many bigger answers is we complain by ourselves take our opportunities as we can the general theme right' conservative garbage collection。

 just a， small。 we're only 30 billionre。Yeah。😊，So， yeah。Yeah we got Ruby runtime。

 Ruby is on Gitthub and open source as well， so they are very active there。It's one of。Yeah。

 it's it's。There we are using actually parts of Robus。

 which is an arubi open source project to rewrite parts of this standard lab movie because one issue we having with Ruubbin R all the time is like compatibility problems with the lab。

You can get to a completeness with the language， but you also need the libraries to work。

And that's harder here in Ruby， we decided to rewrite as much as possible of the core library in Ruby。

That's the river runtime we got an our runtime， our is a statistical language for rec。

 it's our most challenging language that we're implementing。

So it's really stressing the limits of the system。In terms of a body can do。

 But it's so looks very good right now。 why it's so hard。 Yeah， absolutely， as though。

Like the way it， like it has。Like， every single。the only data structure knows it is factors。

That's the first thing， so is there is not the concept of a single value， every value is a vector。

 every operation is a vector operation， at least conceptually。

Then it has things like every assignment to a local variable of these vectors， which I raise。

 is a copy。Logical。So yeah and then it has things like every argument is a promise so it's not actually evaluated at the time when it is given as an argument to the function but at the time when the function first excesses parameter so it's lazy lazy not properly not properly it's not at the additional thing is like that the interpreter has sometimes some weirdness that we need to be backcomp but in general this in and itself is a problem it's lazy evaluation of arguments then it is you can overwrite any operator including the parent operator left parenthes then what else。

啊，我不在。Yeah， and yeah， it's like there's there's a lot more such thing。 so that it's like crazy。

 but basically if you look at a piece of sauce unless you assume nothing in the language sematictics has been modified by the surrounding code。

Then you understand what it is， but until you've looked at everything else and eliminated all possible redefins yeah and like every everybody really don't know what it does yeah every disoverator can be redefined in any of your outer environments and the out environments are very complex。

Yeah， and like basically it's just。And like if you yeah， about one more thing。

 I just the common case programmers are not doing this because it increases complexity for them too。

They're really weird stuff， yeah you don't see， but of course you have to deal with it if you and there are certain weird things which you wouldn't want to deal with like you can revert an expression back to its source。

 modify and reevaluate it。And here's one more thing which is that every value is immutable。

 so if you're assigning actually to a single array element， you assign to a single array element。

 then logically the whole array is copy。But actually you don't even know that because this assignment like the assignment operator is an operator that calls a function。

 which is， yeah， I mean。But yeah， there is。In short。

 you have to inline incredibly deep before you find out what's actually going on and you need a lot of assumptions about your surroundings before you can say。

 yes， this is an array access here and I don't need to copy in your ring。

But the good news is like theres speed of possible a factor 100 or more if you do it properly。

Does or do any of those optimizations or does it just do super negative now just but I mean。

 it's doing all the copies also the same it has a long bit reference can if it's only referred to from one place。

 it doesn't copy Yeah there's a reference count but it's internal general interpret temperature。

 which is very slow forqui values， but if you have very large vectors。

 the temperature overhead is amortized。But it's not completely amortized。

 even if you have very large vector operations because we confuse loops with scroll and the whole stack。

 we are able to get like speed ups like 2x react or more with the vector stuff。

 all the intermediate vectors and material lines。That's the big problem。

 so if you look at some R programs that manipulate you know only。Say 100 megabytes of data。

 some of them are run out of memory in a  four gigabyte heapers they're generating so many intermediate copies of that。

Of the。Yeah the whole language has dynamic typing and that's the other thing and then the array access operator is kind of touring completele in the sense that。

Like。You can use almost any value as a potential index inter rate。Including a boolean vector。

 including an integer vector。This integer vector can have positive values to select elements。

 it can have zero values to select nothing， it can have NA not available to select not available。

 it can have minus values to select everything except for these columns I get the。

I want a high level though you can look at the piece of code， which is the orange temperature here。

Oh the other thing this no language definition is just augment and it does a negative interface。

 which is not documented and yeah anyway， it's our problem，诶。Yeah。

 this is the Fend I was always talking about that， but now the oldest started that will go public with that soon。

 which is element Picode interpreter to try out the Amist languages。Yeah。

 that is part of the team and now being kind of the advertisement pitch。This is。

Some acknowledgeknowgments of some guys working on this。

A a lot of people in Oracle labs that worked on this project， we have a lot of interns。

 this is definitely an incomplete list， but I just can't fit more on the slide and youve got a couple of collaborations right now which is probably also an incomplete list。

But yeah， shouldn this is a big project there's a lot of people involved。And。Yeah。

 this is our working environment to come to us as an inter。啊。Well， yeah。

 we are looking for interns both in America， but also in Turkeyic， this is in Turkey。嗯。Baby。

 we have an operation。In Europe and yeah， we're looking for interns who are interested in anything in the stack from upper level to the lower levels。

 I should it is four levels。 We usually would。Select one of them for a internship。And yeah。

 I think we have a very great team and if you're interested， please ship me an email。

We definitely want to further increase investment in that setting because it looks very promising right now。

Yeah we hope that this will empower a large stack of compiler technology in the future。Alright。

I think if you have projects you want to pursue if you're interested in using any of our staff banner。

会带这啲。We have plenty of project on。All right，'s okay。

 so we got 15 minutes before the survey guys come in and stick around for about say nice thingses all right。

 so we got more time that's good。Right， I never realized Im into something。Even before。The time关仔。

I don't know why they schedule it for this week。Nograd classes ended this week right。

 I don't know this process。I was just told to late 15 minutes at the end。 Yeah。

 I can try one more demo。 you like， I have a question。 Yes。

 would you ever use like X 86 assembly and try to inline that directly rather than like try to interpret C or like。

Tsel down byco。Because you already have the assembly， I think it would be possible。

 but it will be more complex than the outcome。One of the things I worked on。

Before all of this stuff was the binary translation system。the hospital。就把那删出来。

And we built a prototypeton eventually using hospital server compiler as it's translateed with the jaw from and locked off。

That would ingest。X 86 code。And emit machine codes。 So basically simplified risk code。

So spot without。ranchesSo very been risk。And we got very good translation。不造成。

So I don't see any reason why without some effort。I'd be unwillingly to put us。

Quantity on the effort that we couldn't do the same thing。I mean。

 I'm sure it wouldn't be just rising truffle notes thats special simply how a wonderful binary translate bunch。

 you know， the general approach has been proven to work。Yeah， I think I it's holding more complex。

 but I think it could be。They starting us out bit code。

 maybe we have to go to P well because at the moment we assume that we have the source code available of the thing we are。

You'd lose a lot of information that you'd want for。You lose a certain amount。

 the hardest part is reconstructing the understanding of what the memory structures mean。

 so you can't do much in with that， but still can reconstruct a lot about the control and data flow。

Between registers， condition variables， you know functions， one of the nice things is that fun calls。

 you know it's just another's just another control flow so you can inline we had we were inlining。

 you thought our compilation unit size。For the stuff we were doing was on the order of 100。

000 instructions， so it's a pretty big compilation region and we were taking big chunks like the entire path of you know the inner loop of a TPCH query。

 out of the database using that as a translation unit。

should illuminating all the weird side branches that never。lots to all these techniques bullet quite。

跟 you跟来上来吧。Yeah， so IR has in my assembly， so do you just not handle it or at the moment to be not having that。

 but do you want to handle that because youCC playing with04 will generate in my assembly on regular。

 So I think we can handle in mind something I think it should be possible。 this is a certain amount。

Right。At the moment being on her。I was also interested the heartbleed analysis they hope can do。

Hows the plan doing that。So it's not a use app but free but， it's not traditional。

It's a book that there is a memory access into reason it's not about。

 so we would be it's allowed static me code because they use an internal allocateators。

 they allocate a big page， and they use internal free。

 they free that't actually free anything and then they did use that for free。So it wasn't Lib C free。

 but at the point when you're free， you mark the memory as like you never allowed to access it anymore so anybody who would have tried to access the memory that's free is going to but not so you have to modify the original program just it out。

But that doesn't call catch heart free， maybe that truth for you。

maybe they can do this use after free detection in particular。

 we because we have the garbage collector available。

 we can determine whether something is really free。

Because there is a lot of bur on safe with fat pointes or something。

 but useF to free is still a very big problem for them because if you use a fat point or like a point at a point to the table。

 you say at some point to delocate that table or that slot in the table。for this。

 you need a garbageva script to type policies。It seems like a lot of the heartache in implementing some of these languages are things that just。

小议。我已经讲年龄。Philosophically。う。Do you think that there's like a good feedback loop？

Referencing implementation。Yeah。好的。そじ。Yeah， don't do dumb stuff in your language design。

If more language designers understood the consequences of the designs。

Life would be a lot better in terms of making those things run quickly。But because we've had。

 you know20 more or less 20 years of scripting languages evolving to become very widespread that are all built on interpreters。

 you know， in the interpreter， it didn't cost anything to do some of these things。

 but very hard to generate code for some of them and so it would be。

It would be hoover language designers to understand more about。

What's hard to do and what's easy to do， And that's why， you know。

 stuff La was doing with Dar right that was all driven by an implementation team who knew how painful some things were and they tried to avoid those things。

 but it'd be good if there was more of that knowing on generally。Yeah。

 and I mean theres there is a feedback we tried to install the feedback loop a little bit for our。

 for example， we tried to add some flags where certain V features should products from errors and being actually supported。

But。Yeah， I mean， it's very hard to get language implementers who have the interpreter to adopt this because they are to certain an extent the competition and the more it the language is。

 the harder it is for。The competitive implementation uses a compiler。

Now you guys may not be the right people ask， but even so it Oracle doing。

 so you have various Jits and growl and these other things。

Has anyone ever thought to actually afford like a to actually do a radical of hardware that will speed up languages instead rather than doing a software？

In general， I can talk to you a lot about that in general。

 there's not a heck of a lot in ISA design that we do ISA design say FPG， for example。Oh。

 compiling to FPG is no not really， I'm not really， not really， not really。

 I'm very skeptical I swear about that。Yeah， I mean。

 there could be approaches that help us with some。Of the code， like， for example， I mean。

I mean Intel itself， for example， this is cha on overflow and things like that it's already very much intel also just vital terror。

There may be value in this。Well when it's partly checking an egg in that until there are widespread available FPGAs and common platforms。

 there sort of isn't much commercial interest in going down the path of using an FPGA' research lab。

 so you're supposed to be looking ahead。Yeah， I'm just skeptical that and FPGA is a good substrate for general purpose computing。

s Microsoft I think there might be some very limited uses where it benefits for general now and their servers or all FPKs and。

I'm still skeptical。呵。😊，Yeah， I mean the difficulty with FPG is it's kind of you know you have a sub in what you've already sort of discarded a factor of1 in you know area and performance and power and so you're immediately have the barrier of climbing and gain all back again before you even got par pretty people still GPUs for well I'm just as skeptical about GPUs to be honest GPUs you know designed for one。

Characteristic， which is graphics， you know， they don't have to be good。

So I think we have to leave's next Thomas again。Yeah， so so I have to get out of the room here。Oh。

