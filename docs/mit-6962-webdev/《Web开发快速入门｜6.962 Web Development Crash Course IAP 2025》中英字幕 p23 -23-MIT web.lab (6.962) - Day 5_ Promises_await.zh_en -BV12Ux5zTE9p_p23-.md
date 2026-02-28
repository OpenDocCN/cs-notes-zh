# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p23 -23-MIT web.lab (6.962) - Day 5_ Promises_await.zh_en -BV12Ux5zTE9p_p23-

Hello， everybody。 My name is David。My name is Lucas。

 And today we'll be talking about promises and a await。So before we start。

 we wanted to define a few terms that we'll be using throughout this lecture。And。For a first term。

 it's gonna be okay， is it better。Is it better。Okay， cool。 Okay， cool。

 So does it define our first term。 It's synchronous。

 So synchronous essentially is a process which happens consecutively where you have one thing happen after another。

 And to use an example， Basically， we have， for example， classes where we have 6，100 a and then 6，1。

0，1，6，6，100 a is a prere for 6，1，0，1。 So you have to take one before you take the other。 yeah。

And for asynchronous， asynchronous is different where it's an idea where multiple processes can run at the same time。

 So using that analogy earlier， you can have， for example， if you're taking hasas and then 6，1，0，1。

 they don't， if they don't have any conflicting preres， then you could take both at the same time。



![](img/cedf0c2a806f413d658e9ca7045eaa06_1.png)

So to start off， we're gonna use an analogy where we have Abby。

 an avid Cat lover who wants to buy cats from a catalog。So in order to do this in today's society。

 you basically would go to an online retailer， a massive online retailer place an order。

And then after you place the order after some time passeses， you can have one of three things happen。

The first thing that can happen is if everything goes well， you can have the package get delivered。

 Abby's happy。 Everyone's happy。You can have another scenario where you can have the delivery get delayed。

 So Abby's。Anxiously waiting for the package。And lastly， and I guess， disastrously。

 that something that happened to the package where it can get lost。 And as you can see。

 Abby is very sad。So in essence， this analogy also fares very well for promises as well。

cause after placing a delivery order or creating a promise， you can have one of three statuses。😊。

You can have fulfilled or resolved where the delivery is completely successful。

You can have pending where the delivery is just currently being in like this middle state between like being fulfilled。

 or you can have it be rejected or something happened， something wrong。



![](img/cedf0c2a806f413d658e9ca7045eaa06_3.png)

So applying this idea to dot then， this should be a bit of a review， but basically， we have。

 let's say we have a post request。 and this post request essentially using our analogy earlier represents a order that Abby would place where this is basically our initial order for the cats。



![](img/cedf0c2a806f413d658e9ca7045eaa06_5.png)

And。From this， from this order， if the promise is fulfilled。

 then we can use a dot then where this would represent our delivered cats。

 And let's say the cats are delivered。 We can do like， for example。

 a hug function where we hug the cats。If the promise is rejected。

 then we could do other things where， for example， we can use a dot catch method where if。

 if something went wrong， then we can， for example， log it， say， oh， no， something happened here。

And just to be very clear on the idea of what， like， for example， in this code segment here。

 what story objects means， this represents in the case where it's a fail。

 it represents the cats or whatever object we want to retrieve from the promise。



![](img/cedf0c2a806f413d658e9ca7045eaa06_7.png)

And just to reiterate， if we have an error occur， if we have the do catch method here。

 we can easily log that mistake or log that error that occurs and very easily tell that something went wrong。



![](img/cedf0c2a806f413d658e9ca7045eaa06_9.png)

So back to this idea of synchronous versus asynchronous。

 So let's imagine Abby is operating in a synchronous process where in essence。

 once she places the order， she can't do anything in the meantime where she just simply has to wait until the order finishes before she can do anything else。

So the delivery comes。 The order is placed。 Once again， she's can't do anything in the process。

 Deliry comes。But let's say she wants to do something else in the process。

 Let's say she wants to cook。Let's say she wants to lecture the lectures。

Let's say she wants to get gains。 She can't。 She can only do these things while， well。

 and also not do the orders。 Basically， she can only do one or the other。

And let's say she goes back to the like placing an order。 In that case， she can only。

Place the order and then wait for the delivery in the process。As you can see here， however。

 basically one of the big things here is that this wastes a lot of time。

And if we compare this to an asynchronous process， what Abby can do instead is place the orders。

 And while the orders are being delivered， you can， She can cook。 She can lecture to the lectures。

Can get small。And in the process， these deliveries are coming in the background。And in essence。

 this is the difference between synchronous and asynchronous， where in synchronous， basically。

 Abby can only do one order at a time。 while in asynchronous。

 you can do multiple orders at the same time。And just like promises stop Abby from wasting her time watching her orders。

 promises can let us run other code in the background。



![](img/cedf0c2a806f413d658e9ca7045eaa06_11.png)

So what does that look like in code， right？In terms of this， we have a use effect here， right。

 And this use effect， we call a asynchronous function， which is our cat orders。

 which Abby would place。 And in this case， we have a slow cat order。

 Then we have a dot then where once the orders fulfilled。

 then we do console do log of the cats being delivered。Now， basically， yeah， this idea of like。

 we have our slow cat order。 and then we have our callback function， which if the order is fulfilled。

 then we do this。

![](img/cedf0c2a806f413d658e9ca7045eaa06_13.png)

Now， let's say we have some code that's outside of that function where we have constant dialogue of once again。

 cooking some food， lecturing lectures and getting games。Now。

 I w to take a few seconds for you guys to just consider。Even though this code is run in order。

 if we were to like， if we were to run this code in a terminal or just run this program as a whole。

 what do you guys think will happen， Will the cats delivered be。Pinnt it out。

 or do you guys think that the， do you think， do you guys think that something else will happen where maybe the console logs later on will be printed out before the slow cat order is finished。

 I want you guys to take like5 seconds to consider that。呀。Yeah， exactly。 Basically in the next slide。

 this is the idea I'm showing where let's say we have like that blue region where。



![](img/cedf0c2a806f413d658e9ca7045eaa06_15.png)

The blue region represents the slow cat order， and then the red region represents a console logs in the background。

 As we see here in， in this output， even though the slow cat order is written first， we can still。

 we can have a case where the， the other console logs are printed first。

 and then the slow cat order is finished。Which represents this idea of asynchronous。

 where the slowoutt orders running in the background while the other con logs in the red region are being run。



![](img/cedf0c2a806f413d658e9ca7045eaa06_17.png)

Yeah pass off with this。Alright， so can you guys hear me in the back。 thumbs up。 Allright， cool。

 So now we're gonna be looking into using multiple promises。So we have this piece of code here。

 I'll give you guys like 10 seconds to parse it。Essentially， what we have is slow number。

 which is an nine synchronous a call which takes in an input number and returns it to our like front end after one second。

 So essentially what slow number returns whenever we run this code is first a promise。

And so A and B are promises。And at the end， we console log a plus B。Now。

 I want you guys to take around like 10 seconds to think about what the console log would actually print。

And put one finger up if you think it's 19，2 fingers up， if you think it's 9，10，3。

 if it airs out and4 of object promise， object promise。Come on， guys。Alright， see some threes。

 some four， a fours，3，4， Okay， cool， it actually prints out object promise， object promise。

 because jascript just interprets A and B as promises and then concatenate them together。

 you would expect that we'd actually want to add up the numbers that these promises return。

 And so in order to kind of。😊，Unsll the promise and get the value that we want inside。

 We need to wait for these promises to actually resolve。



![](img/cedf0c2a806f413d658e9ca7045eaa06_19.png)

And so you guys know how to do this。 You guys just use dot then。

 So dot then waits for for our promise to resolve and then runs some callback function with the data that we receive from our a synchronous function call。

 So here a dot then that waits for promise A。 and then it runs our callback function。

 which takes in a Val。 And then waits for promise B to resolve as well。

 And so then we just console log A Val plus B Val。And now that we're going into dealing with multiple promises。

 there are multiple ways to actually create behavior from multiple promises。 So we'll look into that。

 So assume that we have multiple promises。 We send a get request to our server for some comments with different parent Is。

 And so we have our five promises。

![](img/cedf0c2a806f413d658e9ca7045eaa06_21.png)

![](img/cedf0c2a806f413d658e9ca7045eaa06_22.png)

And we put them in an array。We can make a promise out of all of these promises。

 and so what Pro do all does here is it resolves if all of our promises in our array resolve and it rejects if at least one of the promises in our array rejects。

So you can imagine that maybe on our Capex server， we want all of our our comments to render。

 And if one comment is not retrieved correctly， then we don't render anything at all。 And we run our。

Our error callback function that is in dot catch。 So if all the promise is resolved。

 we run a functionality in dot then using all the information。Otherwise。

 we run the callback function and catch。Any questions。哎。Now let's look at Pro。t race。

Promise dot race essentially takes in our array of promises and then waits for the first promise to either resolve or reject and depending on whether that promise resolves or rejects。

 we run or rather the promise that we return resolves or rejects so if let's say promise one is the first to resolve。

 then we run the dot then callback function with the data that promise one retrieves。

But let's say in another case， Pro 4 actually rejects first。 So we get a result from Pro 4 first。

 Then we run our error function with the error that promise4 returns。Any questions。All right cool。

Then promise not any takes an iterable iterable of promises and rejects whenever all the promises reject and resolves if at least one promise resolves。

 So you can imagine that promise  one rejects， promise 2 rejects， promise 3 rejects。

 but then promise 4 resolves。 So we use the result from promise4 inside of our dot then callback function。

 and。Yeah， but if we have the case where all our promises reject。

 then we end up running the callback function in dot catch。Okay。



![](img/cedf0c2a806f413d658e9ca7045eaa06_24.png)

够。Now， let's talk about aync and a weight。

![](img/cedf0c2a806f413d658e9ca7045eaa06_26.png)

So in order to actually understand why we use promises。

 and this is just like reiterating the example that David showed us。

 let's talk about a synchronous program and an asynchronous program from the view of like actual code。

So imagine that our red block of code depends on our orange block of code。

 So our orange block produces some data that our red block must use。

And so our orange block must run before our red block。

And it's also supposed that our orange block is not dependent on our green block。 So if we wanted to。

 we can execute them in whatever order we wanted。And so in a synchronous program。

 we would have one piece of code ran after the other。 We can't run run them at the same time。

 So we would run our green piece of code， our orange piece of code and then our red piece of code。

And this word。This would end up taking six time minutes。However， in an asynchronous program。

 this is where。We take advantage of the fact that our green block and our orange block are not dependent on each other。

 So we can run our green block of code。 but while our green block of code is running。

 like maybe we send some API for some data that we know that our red block of code will need to run。

 Then that API call can be ran on some other computer other than our own and we can run our green block of code。

And so by the time that our API kind of finishes， it's going to return that information to our own local computer。

And once we finish our green block of code， we can simply transition into the red block of code。

 And in this case， instead of six time minutes， we actually just run our program and4。

And so now let's talk about a weight。So if you guys remember the example that I showed you guys earlier。

 we actually need to wait for our promises to resolve in order to use the data that our promises hold。

And so one way to do this is to， do to use the dot ends that I showed you。

 But you can also use a key word called a weight。And await just essentially。

 awaits for our promise to resolve。And so， here's。And I'll give you guys。

Some practice questions to consider how long a program will take using just like waiting for promises。



![](img/cedf0c2a806f413d658e9ca7045eaa06_28.png)

So， in this example。just。This example， we send a get request to some URL and then immediately await it。

 with send another get request， we immediately await it， and then we console dialogue。

 If a takes three seconds to wait and then B takes five seconds。

 how long do you guys think it will take before we print something through our console do。

And I'll give you guys。呃。15 seconds to think about it。Okay。

 now I want you guys to put up the number of fingers you think or how many。

 how many minutes or seconds you think it will take to actually execute this code or to actually print it out。

5，5。5s。3。I see an A。Okay， cool guys。 cool。 Okay。 And so this actually takes 8 seconds。😊。

And the reason behind this is we send our get request to random URL， and we immediately await it。

 So we send the request。 All the work is being done on some other computer。

 and we simply await the data to be returned。 So we're not doing any other work on our local computer。

And then that's in order for our get request to actually retrieve information。

 It's gonna take three seconds。 And then we move on to the next get request。

 And then we immediately await it。 And that's gonna take another 5 seconds。 So in total。

 it's gonna to be 8 seconds。Now， this is another example。

 So what if we actually do these get requests before we await them。

And I'll give you guys another 20 seconds to think about how long does it take if。

A takes three seconds to away。 B takes 5。嗯。Yeah。2。嗯。So， it's actually 5。

And I want you guys to turn around， talk to your neighbors。

 And if you guys have any like differing answers， like explain why do you think it's5。哎。

Let's bring it back now。So whenever we send our get request to random URL and other random URL。

You can imagine that we have two different computers that are doing separate work。

And so the moment that we send those get requests， the work that they have to do starts。

 And then we start awaiting promiseise 1。 And it will take whenever we await promise 1。

 We know that it's gonna take three seconds。And so we wait promise one， takes three seconds。

 and in those three seconds， Both of our get requests are being processed。 So our， our promise，2。

 has already done three seconds of work。So by the time that we get to a waitinging promise to。

 we only have to wait two more seconds for it to resolve。

And so that's gonna to end up taking5 seconds。Any questions。Alright， cool。

 And now I'm gonna to give you guys a final example。

 What if instead A takes5 seconds to wait and B takes three seconds to wait。😊，And so。

I want you guys to talk to your partner， probably like。

 go through the code and explain your thought process。Alright， cool， let's bring it back now。

 So this actually takes5 seconds as well。 And so similar to our previous example。

 were sending both get requests， we await promise  one， Pro one is gonna take5 seconds。

 And so we do five seconds of work for both of the requests。 And by the time we get to promise 2。

 Well， we've already done five seconds of work。 and we've only needed three seconds of work。

 So our promise2 has already been resolved。 And so we don't， we don't wait any extra time。

 And so by the time that we console log done5 seconds of past。 And that's it。😊。

And so the thing about using a weight as opposed to dot then。

 is that only asynchronous functions can use a weight。

 And so what does it mean for a function to be asynchronous。



![](img/cedf0c2a806f413d658e9ca7045eaa06_30.png)

Well， it just means that we use the async keyword whenever we define the function。

So we just use async。 and then inside of that async function， we can freely use away。



![](img/cedf0c2a806f413d658e9ca7045eaa06_32.png)

And so now let's put the await code and the dot then dot then code side by side。

 So imagine that somewhere up in the code， we do our like get requests for A and B。

And then we simply want to wait for， we want， simply want to wait those for of those promises。

And so for our function that uses a weight， it's as simple as just a weight， A plus a weight B。

And then for our dot then， it's a little bit uglier since we're nesting in like two dot ends。

 And whenever we're waitinging， awaiting multiple promises， it can get a little bit ugly。🤢。



![](img/cedf0c2a806f413d658e9ca7045eaa06_34.png)

And so this is just like one benefit of using a weight as opposed to thought then。



![](img/cedf0c2a806f413d658e9ca7045eaa06_36.png)

Another difference between using away and dot then is that for traditional promises， we use dot then。

 And so for our use effect， if we have a get request。

 we simply get the data from that get request and then run our callback function。But for。Use effects。

 we can't have asynchronous callback functions or inside of use effect。 And so。

In order to actually run our。Are weight function。 We have to define a get stories function inside of our use use effect callback function。

 So inside here and then actually call get stories。😊，Yeah， so that's just like a small difference。

 So you guys just have to take into account。

![](img/cedf0c2a806f413d658e9ca7045eaa06_38.png)

Questions。

![](img/cedf0c2a806f413d658e9ca7045eaa06_40.png)

And I don't know if I have enough time for this。 Ey， no， okay。

But if you guys have any questions or have ever wondered like how jascript actually handles ayn calls。

 please go to office hours。 like， maybe it's a little bit confusing that like we wait for promises and then we run a callback function。

 But when do we actually have the time to run that callback function。

 if we're like running other code。 So if you guys are interested in that。

 please come to office hours and I'll do the mini presentation there。😊。



![](img/cedf0c2a806f413d658e9ca7045eaa06_42.png)

2。And so when should we use asynchronous functions。

And so we use async functions or like API requests or rather promises。

 whenever we have background tasks that we don't know how long we don't know how long these background tasks will take。

 So， for example， it could be fetching data or downloading slash uploading data on YouTube。

And it's very important to like， realize， like。Why promises contribute to like user interactivity。

 Let's say we're on YouTube and we're waiting for everything on YouTube to render。

 So we're requesting videos， we're requesting comments。

But we can still exc through the YouTube app or YouTube website。

 even when some videos haven't rendered。And that's very important because like。

 if we used synchronous or if our website was synchronous。

 then we would have to request all of our data。 And then only when we have received all this data。

 we can scroll through our， our， our website。 And so， yeah。

 that's just why synchronous functions are important。



![](img/cedf0c2a806f413d658e9ca7045eaa06_44.png)

对呀。嗯。I really appreciate you guys give us feedback。

 It's really important for us to improve our lectures。 Thank you guys。😊。



![](img/cedf0c2a806f413d658e9ca7045eaa06_46.png)