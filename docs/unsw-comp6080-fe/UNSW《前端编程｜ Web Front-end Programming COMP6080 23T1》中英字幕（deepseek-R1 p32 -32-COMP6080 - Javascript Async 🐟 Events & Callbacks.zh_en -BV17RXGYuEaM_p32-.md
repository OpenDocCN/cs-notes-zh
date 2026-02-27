# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p32 -32-COMP6080 - Javascript Async 🐟 Events & Callbacks.zh_en -BV17RXGYuEaM_p32-

![](img/493156f21f16627d7c2bd500e0de90b2_0.png)

Okay， welcome back， everyone。We're going to be talking today about。Concurrency in Javascript。

So without any further ado。Let's get it going again。Where is the stuff those bit there it is。

I just need to grab my laser pointer yet again。Yeahay， this is a smaller one， hang。Des 10。

There we go， okay。😊，As soon as concurrency in Javascript。So last time。

We talked about the client server model and we gave a definition for what AjaX is this time we'll be talking about concurrency and then we'll be talking about concurrency specifically in JavaScript。

😊，Just a reminder that what we're trying to achieve is a nice。

 asynchronous way to have our client talk to many different servers。😊。

Over the lifetime of our web app and hopefully we can devise a system so that these servers don't or they don't only preoccupied with us with everyone。

😊，So Ax gives us the framework right， we know we need some asynchronous stuff for lazy loading。

 but how do we do this specifically in JavaScript？😊，In fact。

 what does asynchronous actually even mean， that's what we're going to explore first。

 and then we're going to see how this works done。😊。

So this will be a very brief prim for congruency becausecurency is a big， big topic。

 but hopefully we'll be able to convey enough information that you guys will at least have an intuitive understanding of how all this stuff works So let' before talking about asynchronous we probably should contrast it with what synchronous programming is synchronous programming is what you guys probably did in1511 or whatever the postgrad equivalent of that is where you write a program top down right you start at the top year go down。

😊，We're guaranteed so that's I mean asynous programs also have this idea left top down。

 but what's most。Significant about synchronous programming is that we're guaranteed that every previous instruction will fully complete and evaluate before the next one is executed。

 and that gives us some very nice properties， the main one， of course。

 being that sort of easy to reason about synchronous programming。😊。

Because it's like maths in that things are transitive if I have int a equals B and then。😊，B plus one。

 and then in C equals B， then I know that C will be a plus one， right， and it won't be。A。

 it won't be some other random number because something has happened in the meanwhile。

 we know that if I store B into a increment B and then store that into C。

 that C will get a plus one or B plus one because A and the sent。😊，Before diploma。

Asynchronous programming on the other hand。😊，Has a few interesting things the first one is is that there are multiple flows of control a flow of control is like an execution。

😊，RightLike you guys know what a flow of control is because if you have a regular program and then you're writing if condition。

 you know that you can branch to two possible flows of control。😊，Well， in an asynchronous program。

 it's possible that you might take both branches at the same time。

 depending on the state of each of those things that we call threads a thread is a flow of control。😊。

That's sort of what the name means and you can think of it like a string that's kind of where the the word thread comes from because it's like it's stringing through the program。

😊，嗯。Threads， there's like different flavors of threads they can either interleave so that will be where one happens at one time and then the next one happens and then it goes like this。

Or you can have them literally work at the same time， and this is the hardest one。😊，And naturally。

 if you think about it， that's a much harder to reason about right because now we don't have this nice transitivity property now things could happen。

 things could change from underneath our feet and we would have no idea。

 but let's say this in diagrammatic form。😊，So the synchronous side。

 let's say we have two threads or processes or I don't know， things。In the synchronous world。

 process A happens， it calls a function that starts process B's work。

Process A waits while process B does its thing and then when process B returns process A gets the return result。

 the value and then process A continues so it's very nice right and this is like if you guys remember function call like like the block diagram for what a function call looks like it's exactly this we're in process A we jump to process B's function execute the body jump back。

Keep going。We're in an asynchronous world， however。😊，We're in process A first。

 we then ask for process B to start doing its thing and then process A， just keep going。😊。

And then at some point in the future， when process B is done。

 we get back whatever information process B generated and there's multiple strategies for。

Knowing how to do the side to of the response back。

 but this is the general idea of what's happening here。😊，嗯。Yeah。

 I think I've covered most of these once right so you can see already asynronous stuff。😊。

We can get more done with Asynbriner's work。But it's a lot harder to orchestrate。And。

That leads us to like this is more jargon right， but that there's kind of like two primary models of concurrency。

The first model。Is preemptive and I'm not going to talk about preemptive too much because that's out of the scope of the scores The other one is cooperative and again best explained through a diagram preemptive is this where we have two processes literally working at the same time same moment。

😊，And they're on different CPUs and they're sharing information through some protocol， some strategy。

😊，And this is generally what happens when you're working on your operating system or you're working in see or you're working a lower level language。

😊，Cooperative mode， on the other hand， is where it's this interleaaving thing right。

 where process A executes for some amount of time and then it stops and then process B has its turn and then it stops and then process A keeps going。

😊，This is a simplified diagram， obviously there are more nuances to this， but for。😊，Our purposes。

 this is basically the mental model that we're working with here。😊。

So preemptive multitaskking is really good for when you're doing lots of computation。

 obviously because you're running two CPU， so while one CPU is crunch in numbers。

 the other one can crunch other numbers。😊，But cooperative mode is really good for what's known as like this IO intensive workload right IO intensive because。

😊，I mean， this is something I'm not sure I get talked about enough in CSE but。

CPUs are really really fast like really fast they're so fast in fact that one CPU cycle is about a thousand times faster than reading for RAM so。

😊，You can imagine right if reading from RAM if reading from RAM is 1000 times slower than working on the CPU reading from disk is like a million times slower or 10100000 times slower how many microseconds are there in a in a millisecond1 thousand0 rate somewhere it's many orders of magnitude more than reading on the CPU so。

😊，If you're doing a lot of IOre reading from disk， reading over a network， something like this。

 then most of the time to see if you's just waiting spinning and so we're wasting time and this is exactly the kind of work that we do when we're in the web right we're waiting for a user to do a thing use and humans can only like operate。

😊，In the in the like time range of seconds like it takes about a second for us to click a mouse button or something like this right in that time the CPU is done like a billion cycles so it's just waiting and doing nothing。

😊，All were waiting for some information to come over the network in that case。

 the CPU is still just waiting。😊，But this is perfect， right。

 because what it means is is that if we just。😊，Take all the different tasks the CP has to do for all the different things that is's trying to do at once。

 then we can whilst we're waiting for say process A to grow grab its thing。

 the process speak can do its thing and the process C can do its thing and the process C can do its thing and instead of waiting for IO to come in and then doing the next thing and then waiting again and waiting for the next and the sort of always waiting for IO to come in whilst we're waiting for IO。

😊，We can go and run the other processes and this is cooperative multitasking in a nutshell and so we are we also get some other benefits with cooperative multitasking one is is that each of these processes。

Opers like it synchronous so what that means is is that there's no one of the problems that happens with this kind of thing you can imagine right is that if these if process A and process B are both isolated as in they don't share and a memory。

😊，Then everything's all good they just work on their own memory。

 but the world is much more complex than just isolation so generally process B and process A will work at some point on the same data and that creates what's known as a data race because whoever gets there first will change it and then whoever gets their second will change it and confuse the first person who got there so we don't want that to happen。

😊，And that's a data race and data races whenever you whenever you hear people talk about like concurrency bugs and why it's so difficult to do concurrency。

 data races are probably the primary reason and dead logs， which again not important here， but。😊。

If you think about cooperative mode because process A runs and then hypothetically waits here while it's waiting for IO when process B is running。

 process A isn't running， so even if they're sharing memory。

 process B exclusively when it's running we see the memory and process A when it's running will also exclusively see the memory so we just avoid a whole class of like problems that can potentially happen。

😊，So this is good because we get the reason of synchronous programming because things won't just change。

 but we also get the benefit of asynchronous programming because now we can do many。

 many things at once that're just interleaved， right？😊。

And this is exactly cooperative mode is exactly what JavaScriptscript does。

 so for every event that needs to happen that's known for every task that needs to happen that's known as an event。

😊，And then JavaScript maintains a thing known as an event loop and every event that needs to happen gets put onto this event loop。

 then we register a event handlers to go and handle that event。😊。

And each event handler runs completely isolated for every other event handler。And that's awesome。So。

I think that's all I wanted to say about these concurrency models。

 we're about to dive into the JavaScriptscript event loop and how it happens。

 but let me just pause think if there's anything more I need to say about this， that's important。😊。

Yeah。是。There is not I will say that cooperative multitasking isn't a silver bullet naturally it's really good for IO intensive workloads。

 but if your workload isn't IO intensive， then you shouldn't use it。😊。

I suppose that's a lesson to say。But now we're going to talk about JavaScriptscripts Even loop and the JavaScript event loop。

😊，In essence， looks like this， so we have our event emitters and our event emitters can be network。😊。

Could be a keyboard event like you' typing something。

 could be a mouse event like you're clicking or you're like scrolling or you're just moving the mouse cursa around all of these generate events。

😊，And for every event that gets generated， it gets pushed onto this first in first out event queue right so let's say the mouse event comes first it's event one and then we have some network requests that just came in or network response that just came in it's going to be event two and then we click or type in something。

😊，I should say if you press a key， not click a key， then that can be then three。😊。

And the JavaScript runtime it has a loop that's running always always running and what it does is it will grab the most or I guess it would be what not the most recent the least the least recent event so whichever one is at the head of the queue and then it will check to see if it has an event handler for that and it will go and excuse that penhandr right to completion is the main thing it will like I said these event handlers always run in isolation into completion there's no。

😊，There's no stopping it once it starts， there's no preemption that's called so the event handler will go until it's done or until it decides it wants to stop。

Wwhich we'll see in the last of these lectures， last of these lectures what that actually means。

 but for the time being you can think in your mind that these event handlers always work until completion。

😊，And the event loop basically it just always spends in the loop waiting for events to come in if there are no events。

 then it will just。Keeps it until something comes in。And。

Once the like global when you write a script right and we'll see what that means everything that you write at the global level will happen first and then the event will keep going so once you once you're in the event loops like loop it will keep going forever until you close the tab or you type on your computer or something。

😊，Right。😊，So this all looks really good at a high level， but it's not magic， it's not magic， right？

So。We still need some way to countdown timers because timers actually time happens like independent of a program right so if this event handler is always spinning you would imagine if you wanted to countdown on timer you'd have to。

😊，Every unit， say every nanosecond or every millisecond， every microsecond。

 maybe you would have to add an event to like just count down the timer。

 This obviously generates a lot of like false positive events。

 So the browser will count down timers for the Javascript engine。 So it doesn't handle that。

 It also doesn't handle networking as in it doesn't handle。

The actual mechanics of sending bytes over wire， the wire or like receiving the bytes from a socket or things like this。

 the browser does that， the browser does that， the event loop handles the event that something was said and the event that something has come back。

 but it doesn't handle the actual mechanics of sending over the wire。

It also doesn't handle the actual pushing to the event queue。

 so when input comes in from say a mouse， it's the browser that does the pushing onto the event queue。

 not the JavaScript run time the JavaScript runtime sees the event queue。

ItSees are the event too has grown， but it doesn't physically do the pushing itself。Cool。

 so I'm going to break out of this。😊，I'm going to break out is this， there we go。

Presentation and let's go and look at an example， so here I have not the code。😊。

Here I have Web store。And we're going to do a small demo。

 so let me just increase the font size for you guys。😊，I have a very basic。

Application here eventually just prints through bar and B on the screen and what I want to have happen is I want first through to be printed as soon as we load the page but then I want bar to happen next after some time and then I want B to happen again after some more times pass so let's see how we can use the event loop to do that or let's see how we can use functions that we've used before but with the new knowledge of how the event loop operates to do this so this is the the HD novel that it's really simple。

And yes and do。In Gal script。So I wanted to quickly say a word about this like。

The step one of the event loop thing。Which is execute your ja top down registering any handlers that's this so when JavaScript executes it does it from the top down so it will see this function definition and sort of store the fact that there's a function definition。

😊，And then it does that for this function as well， and then it does after this function as well。

 and then it does it for this function as well。😊，And then it see this called the food。

 and this is at global scope， and you know， it's at global scope because。😊。

There's an engine in there， right？When we hit this line。

We know that this will be immediately executed， right？

So we hit this line and then Fs cold F does the thing。

 this is also a function call so that gets immediately executed and all this does is just creates a new text element。

 sticks it on the oh puts a create H1 element or or H3 with some text and then it just puts it in the body。

😊，So this will run to completion。Then we call Ba Ba will run to completion and then we call Baz and then BS will run to completion right so this is a very synchronous program we start down here and then we go here way for the result then we go here way for the result then we go here way for the result we are going to make this asynchronous and if you guys have。

😊，Done any events or anything like JavaScript with timers。

 then you know there's going to be a function called set timer。😊，What' set time out， sorry。

 let's set time on。 And what set time it does is it takes。 Let's just。Get in whisperper now。

If I look at the documentation， it takes。This callback， this handler and a timeout。

 which is a number。So naturally， what we're going to do is we're going to be to have our callback be bar。

And let's make this run， Ota。2500 seconds a milliseconds， so that will be two and a half seconds。

And then we will do the same thing for Bs。So bad， let's be somewhat sneaky， let's put zero here。Yeah。

😊，So zero means let's make this happen immediately。😊，Well that's what you would think。

 let's actually put this first and see what happens。

What I'm going to do to make this super obvious is I'm going to put a console log here。plug。Hello。

And then inside of bar and bar， so let's made it fast。Inside of Bz， I'm going to put another console。

And it will say。W。So now if I go back to my web page and I do a Arabic。O好。

I won't judge your Google firm for thinking things。If I just relay this now。

You can see this happened really fast， except for Bob， it comes here。😊。

Hello was printed and then buy was printed， which is interesting right because we would think naively that this timeout because we're not waiting at all just don't happen right there。

 but that's not how it works。😊，So hello with printed first。And then buy was printed right。

 so what's actually happening here is this， and this is important to know。😊，Remember。

The global scope happens first to completion always。😊，So we call through， which calls steps andject。

 which does it to completion set timeout will queue up。😊，This event， this handler to execute。

At least after this manycond， but it doesn't happen straight away right we are still in the process of executing everything that's happened that's happening at global scope。

So we don't just。Break out， we have to run everything in global scope to completion first。😡。

Which is why we set the time out， it returns immediately basically after sunqueuing。

 and then we consult the。 log and then we do the same thing from Bar where we queue up after two and a half seconds for this to run in the event queue。

😊，And then that will return and then we jump off the end of the function。

 we jump out of global scope， and then at that point the event loop is going to kick in。

 look at what events there are and it will see that there are two。😊，There's the set timeout one。

And for for bas， which can happen right now because we're not waiting at all。

 And then after two and a half seconds， it will see that there's the bar event and then it will go execute the bar event。

 So this is what's happening right， We always complete global scope to the end first and then。😊。

We will。Execute the event handlers again， for them as well， to completion。😊。

And go from there so you can see this is important to understand because sometimes it's rather unintuitive or hard grasp what's happening here。

 but for every event handle that we have it always runs to completion and then any asynchronous stuff asynchronous stuff that we do gets pushed onto the end of the event here and then we just be going like that。

😊，Yeah， so。That's how that works。If I just get rid to these console buds in there， why not？

So if I just change this to be one second， and I go back to my webage and do a reload。

Then Kafr and then ba and then bar this one makes more sense。

 right because after a second we handle bath as printing and then after two and a half seconds we handle ball printing。

😊，But hello and by are called in potentiallytu and unintuitive order。So that's that。

 let's go back to the presentation。嗯。Put me back there。So。😊。

I'm making an emphasis about the fact that we need that the event loop runs all of its event handlers to completion because there's a very important thing that you have to understand。

The event loop runs on a single CPU， essentially a single thread is what you'll hear people say。

 but you can think of it as a single CPU。😊，So what that means is that we have our event handler that gets called my point one there。

 we have the event handler， which is called and during the period until the handler ends。

 there's nothing else that can run， not even animations。

 nothing will stop in a event handler except itself or completing。😊。

So what that means is is that if your event handler is long running， everything will freeze。

 everything will freeze right so naturally the way to avoid this is that if you're doing networking。

😊，That is done asynchronously， which is the default， so that's good。😊。

But less obvious is that if you're doing a CPU intensive calculation like I don't know。

 multiplying to 5000 by 5000 matrices， I don't know why you would。

 but you know you could that you push this to an environment that's much more apt to doing these intense calculations and so your best friend。

 the backend server is the best place to do CPU intensive calculations。😊。

There are other technologies， but we won't be talking about them because they're honestly more the more of an a side than anything right I want to show you guys this。

In practice。So let's go back to West one and we'll close this because we know。We， look inside。

This and this， so again， we'll just increase this。AM is't too important。

 you guys will have all access to this code once we are。😊，Done， But if we just take a look。

 see what the app does。It will load this very basic thing。

 we have a counter which will start counting when we count。😊。

Every second count then we have our calculator which will which we are going to make a very long running calculation and we're going to see what happens so let's just refresh this so it stop and we will go and put in。

That calculation。So you guys should have covered events already。

 so I'm not going to explain what all this startup code down here does。 Instead。

 we're going to write a very long calculation。😊，So let's say a nice something thing you're super stupid。

Let's do maybe。1 million， one， two， three，And what we're going to do is we are going to count to1 million without CPUU because。

 I mean， decal CPUs are basically for， right？If you guys don' know what I'm doing。

 this is a very hacky way of counting， a， the wrong way。No， that's right。

 So it's going to start at 10000。 This is actually the purse decrement is greater than0。

 but if you are。😊，Super， I don't know， happyy like me， you can just do this。That should be fine。

 So this will be a quote unquote， long calculation。Oh， it's con I need to make it left。There we go。

Let us now go back to。Here， give rid a reload， so does that work？So I have。U， I am stupid。

 I haven't updated that yet。😊，What I want to do is。Change the text。

As far as I should actually do this properly， shouldn't enough instead of going backwards。😊。

What I'll do is four it let eye equal is one。And then Wel's I is less than to end。

Then what we're going to do is increase higher。And。We will do document dot get only by ID。

 but that I call anything， I called it means sadly， it does not means。I think I' called it。

Next content will be I。Cool， okay， so this will update the counter now instead of doing nothing。😊。

So figure go back to here。😔，If you go to reload and then start calculating this should count well it didn't do the intermediate values unfortunately。

 but it did count up， which is good。 let's now refresh this and I might add one more0 actually because that was kind of false。

😊，Lets stop County。1，2，3，4。 Okay， now let's stop calculating。A can of stopped。

It's stopped forever or has it。There we go， you can see whilst we're accounting to what's that 10 million the kind of stopped for like a good six7 seconds。

 right so？😊，You can imagine for animations right or for user input。

 you can't do anything while this is happening like I can't even click， it's just stuck。😊。

Because it's， it's calculating。Like the stupid thing that it is。Y， it's frozen。And if a really long。

 yeah， you can see， right？😊，The Ch me even tells me， oh， no。

 this thing is like a legit working because you've the， you've blocked the thing。

 It should be done unless it just suspended the event loop。Yeah， it's just straight up on。

 but that you understand right you don't want to be doing too much big calculation because you block the event loop and that's like the antithesis of what we're trying to do here。

😊，Cool， para is a appointment。Right， so this。Discussion is all about concurrency right and how we can do asynchronous or sort of laying the logical the mechanistic framework for how JavaScript can do asynchronous concurrency we now know that we have like an event loop right and events or task can get pushed on the event loop we register handlers in the form of callbacks or whatever event listeners but we still technically don't know what to do about。

😊，Networking right because thats that's our point， that's our goal we want to be able to do some networking and we're going to use this event loop knowledge that we've just gained。

😊，And we're going to see the first and three breaches of how to do this。So I will see you guys。

ok you。Next time where we talk about XmL HTTP request。

 which is the first of three ways to do network。Requests， response， life cycle stuff in JavaScript。

 so。我 them。

![](img/493156f21f16627d7c2bd500e0de90b2_2.png)