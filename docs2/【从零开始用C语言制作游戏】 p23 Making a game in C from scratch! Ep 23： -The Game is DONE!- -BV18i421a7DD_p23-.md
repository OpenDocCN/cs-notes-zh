# 【从零开始用C语言制作游戏】 p23 Making a game in C from scratch! Ep 23： -The Game is DONE!- -BV18i421a7DD_p23-

Hello everybody， welcome to this new live stream in the series where we're creating the entire game In from scratch。

 you have seen everything from the game all the way to the starting from the first line of code all the way to where we are now and if you can see here on the screen。

 we are really close to releasing the game on steam。😊，And that's the main goal。

 hopefully today we're going to either finish it。Or be very cost efficient because I want to release it next week。

 so you guys here heard it here first。I want to release that on the 20th of September 2019。

 which is one pretty much one week from now， one week and one day， which is a Friday。

And hopefully we'll be able to get done， so I do have to send that to team。

 so I have to come a couple days before that to finish everything。But the plan is。

To get as much as possible today。There are just a couple things really have to fix the audio because we improved on that last time but that was really hushed and it kind of broke down in the end of the last stream so we're going to fix that today pretty quickly and have to do some small polishing passes。

 maybe a little bit of the difficulty。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_1.png)

And things like that。So if you want to follow along， you can download the game already on HIO。

As well as the source code， so if you go to dzd。h。o/ breakarakega。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_3.png)

And I could download now， you can download every episode source code from the very first one。

 which we had like just a window pop up and like a renderer or something。

And we could download last episode， which was episode 22， and you're welcome to give me a tip。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_5.png)

But if you want to you can just click no thanks and then download whichever day you want and you can watch whole the entire live streams。

 the whole development on YouTube， which is YouTubebe。com/danzadan。

And if you come here in the making game in C from scratch， although it is Team launchunch。

 right series， you can watch from the very first episode all the way to where we are now and yeah last episode was Zeel 22 so this episode 23。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_7.png)

If this was the last episode of coding， if we managed to finish the game。

We may only get the 24 episodes， which is okay， so if we have one more after this one of coding。

We're going to get to 25 because I want to do like a really easy live stream that was going to play the game on seeing things that can be pretty cool。

Okay so we're going to get started。And yeah， let's see。

 Maybe this would be the last stream of coding the game。 I don't know。

 I don't know what you guys thought about that。 Hey， man， nice to see you here as well。 Awesome。

 We were just about to get started。😊，So。Let's go。 Let's go to4 coder。And sorry， making the game。

 We have to fix the audio pretty quickly and hopefully we'll be able to polish that up to we did a lot of crazy stuff last time。

 Last time we made a。😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_9.png)

We made it on Fig file and we parsed that and that was pretty cool。

Maybe you can add stuff to the complete file as well to date。That could be pretty cool as well。

So if you go to the game， let's compile。Okay， everything's running nicely。And yeah。

 and we were about to review the audio system because I don't know if you guys will be able to let me just see what kind of what kind of。

I I can just load the project。We get the kind of build settings we're running。

I'm going to make that the debug just so we can see the crash because the audio is crashing a lot。

Don't I have the。future your studio project。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_11.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_12.png)

Oops， I supposed to be like。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_14.png)

O。Let's see。 I' gonna。Turn out your volume。Yes， see so。Well， were crash right off the bat now。Oh。

Well， I thought we were going to crash， but I wasn't sure we were going to crash that early。

My own C program of the Ar andau games is on the stage of collision with the ball with blocks。

 That's awesome， man， are you like。😊，Making videos about it somewhere， that could be pretty cool。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_16.png)

Oh， because we don't have debug seaables。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_18.png)

Yeah， I love to see it that'll be that'll be pretty awesome。😊，We've got 10 viewers already。Okay。

 so you guys are going to be able to see the game crash and burn， right？So yeah， oh。

 we're failing the load， probably。Let's see， let's see our pack file。 Yeah。

 we don't have a pack file。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_20.png)

Because the truth is。I copy the project settings to another directory and probably didn't copy the pack file which should if this was supposed to be yeah videos on YouTube drop the link man'。

 I love to see that later that would be pretty cool。If we were a more like on an over game。

 we should probably log or maybe put a message box or something if we can't find the assets。

But if you can't find the S we might as well just crash。

 at this point it's not that big of a problem， I think。And I'm just going to copy the data well。

Oh no， that's another problem， I have to set the run directory yeah。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_22.png)

Okay， so now we run， we're pretty slow because we are on a debug field。

But I'm not sure if I'm going to be able to make the game crash。But believe me。

 the audio is pretty bad at this point。And since we' not optimized， it's already pretty slow as well。

At least it's playable for me， it's not like a wick of broker。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_24.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_25.png)

🎼7。Yeah， the camera shakes pretty out of control。I yeah you guys could probably see that。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_27.png)

Let me show you guys how the game actually looks。If I actually make that。

Peaible for you guys to see what's going on。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_29.png)

来次。So this is the actual game and we were very close to releasing the game。Now we're talking， right？

And I'm pretty sure it're still going to crash。米要0。Those level transitions animation are really cool。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_31.png)

See， we had a small boat app。 there we go， We crash。 Hey， Marcus， man， it's awesome to see you here。

Really cool， because this may be the last coding stream before they release on steam。😊。

Because we are already up on the steamam start page， which is pretty cool。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_33.png)

For its such a small， I don't know， project， everything on livestream kind of project。

 it's awesome to probably be closed and I'm probably going to release that next week。

 so everyone can add the wish list to be notified， but it's be it's going to be free along with the source code。

 the source it's also going to be free on steam。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_35.png)

And yeah， it's pretty cool。 It's nice to see you here。 So the a system is pretty。

 pretty pretty bad at this point， crashing。 and it's really hard to。😊。

To see exactly what the problem is because it's a multi threaded problem。

 I mean this is optimized right， I think。But。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_37.png)

But the very idea of the way we are searching it' not working。

But it still take20 minutes GP your time， or we have optimized the menu， we have optimized that man。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_39.png)

Oh， it's pretty cool now， let me show you how much we're taking from it。So yeah， we are running here。

Can you see that？It's the W 32 platform。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_41.png)

Well， it's kind of a。Put this a little bit more to the side like this。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_43.png)

We are sleeping correctly。So if you were taking like 1% off the GPU。So yeah。

 1% and it's entirely GPU， so we're taking0% of the GPU or did I say GPU I meant CPU。

 we're taking 1% of the CPU time and zero of the GP because this game' is entirely software rendering。

whole thing。Because we hadt we optimize that pretty well， there was a one live stream。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_45.png)

There was a pretty cool live stream where we focused on optimizing。

And we managed that to run like five times faster。And is optimizing the game。

 so we build a profiler for the game， make that one five times faster。And at some point。

 I don't know which point。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_47.png)

We， we ended up。Making the locked frame rate， but I am going to add an option today to unlock it。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_49.png)

I don't know for some reason to not v syncync because we're not probably this syncync because we're not using OpenGL of C and PV32 yeah I means it's it's so much better and we didn't even optimize that a lot if we could have made that S which we would have gained at least for time speed I think。

And also multi threadreaded， which we at least like twice as fast。 So we could get。

 we could have got like 10 x above。Thats five x that we've got。Pretty easily。

 but that's not really necessary。 the game is running pretty well at this point。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_51.png)

🎼And。And I don't want to really spend much time。Yeah， so we're spending like 1。3% of the CPU， 35 mes。

Of memory and like0% of the GPU。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_53.png)

new things to do， maybe yeah， I don't know， I want to close this up because it's。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_55.png)

It's pretty's pretty， it's kind of long already。 I mean。

 I'm not sure if I can see how many hours or I can I can see how many hours I recorded here。😊，On my。

Let's see on my videos here and I' see how many hours we already did。What 74 hours？Is that correct？

What。😮，74 hours divided by 22 episodes， about three hours per， this looks correct。Wow， dude。

 this is a lot，74 hours in this game， but that was pretty cool。 We added a lot of cool stuff， man。

 a lot of cool stuff。 So I want to close that up。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_57.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_58.png)

Probably today， maybe maybe maybe black next stream， so for the honor system。

 I want to change a couple things。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_60.png)

First of all。Now to make this a little bit more。Not robust。

But it'll be a little bit easier to understand。Im going or not this。Yeah， this。No， this is wrong。

 this is the old one， yeah。I can just remove the old code from here。Okay。This thing here。Yeah。

 instead of just adding to the pointer like this， I'm going to just do that in two steps。

Because since we were dereencing a pointer， I think it's a little bit。

It's more clear to just do the addition here and then。Add to the reference pointer。

But that's not the problem， the problem is。We are running this on a separate thread。

 even if you watch that。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_62.png)

The multi threading episode can see。冇知啊。Red。What was that called？Paraallleel programming。

 making job system implementing。Yeah。😊，Well， in one of these episodes， I think it was this episode。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_64.png)

We made the audio run sink， so we have two threads kind of a fighting and that's the problem we have that's why we're crashing。

This， this play sound thing。This thing gets called on one thread。

whichch the thread that wants to change the sound that's playing however。

 it might as well be playing in the other thread so we kind of zero that out and we change we change like the active to true we change the sound we zero that before we do that and as far as we know this thread might be running。

😡，Like reading reading from the other thing。 so we can't zero that out like this。

 What I want to do is a very small lock。So that when the audio thread is processing the audio。

I'm not going to change the idea。😡，ok。So。That's it。 I'm going to add a volatile。わ volatile tile。不。

Like呃。Playing sound are blocked。Yeah， blocked by thread。Okay。

 and whenever we start playing this sound， if we can， right？I'm going to。Se the black by3 through2。

 but I can't set that if you remember our multi threadreading stream。What we did。

 we use the inter locked。Compareed exchange is yes， like this。That's what we need to do。

Because we need an atomic operation to try to change and read。

 because if you read and then change the other thread might as well slip inside these two operations and do something else。

 that's why we need this this atomic operation， this is one operation that's going to compare and exchange of values。

And what I'm going to do。Is going to I'm going to create。A。see。

I'm going to create a macro for that because if， well。

 if you ever port this game to another platform， this is compiler specific。So compiler specific。

Intrisic。行。I'mre going to define interlock。Exchange。Pretty noisy outside， it's pretty noisy。

 pretty hot as well， it's pretty hot in Brazil usually。😊，But today is especially hot。

 so it's going to take three values pretty， pretty easily。😊。

And then you can use the interlocked Comp exchange here。The macro。呃。Per locked。空。全国这一套的。Interlock。

Hereair。Exchange， okay， and this， this is what we need to do at this point。 We need like a volatile。

The same thing。Of all a T original。Volaile B 32 original。Can really even wrap that on its own blog。

If anyone has any questions， be should drop them on a chat。

 I'll try to answer that and it's going to be the sound blocked by thread。

And I'm going to create a volatile new value。And it's going to be true because I want to set that block。

 And then I'm going to do like inter lot。It calls interlect compare exchange。Okay。

 and then I'm going to set the pointer。And know what， I can also do this cast。Here。

 because they need to cast that to a volatile long because that's what it takes。

That's what it takes to paralyze。So， yeah， I'm going to。Soer。Block by thread。

And then I always forget the order of these guys internal lock。The new and the original。

 so the new value and the original okay？And。Let's say if we didn't manage to lock that we should always lock。

 to be honest。That should always turn out to be true。So we can probably assert that。

Because this is the only one that's going to change the value。

 the other one's going to read the value。It's going to read the value to make sure that it's not locked。

 so it's going to pretty much。We can do like a spin lock。At this point， at at the。

And they play audio thing。At this guy， just closing。The Discord channel that just popped up there。

So what I'm going to do in the play sound here， which is the only place that we change the playing sound。

 which is the problem， right？Does it mean is that your CPU has four cores。

 the maximum amount of threads is four or it's possible to do more？呃。Theoretically。

If I have four cores， I probably have eight hyper threads because that's the basic idea。

 right because。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_66.png)

The the actual CPU core。CPU core。Is what has， let's say， the LOU， right？

The arithmetic logic unit and there's like the floating point unit。There's all sorts of stuff here。

 the cash， right？This is inside a single core and if I have like four actual cores of my CPU。

 what the CPU manufacturer usually does is create。More hyper threads and hyperths just the state of the CPU。

So for each core， I can keep two states。For that part and the way the way they do this because if like this guy is stuck on the ALU。

 for instance， is it really AU just make。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_68.png)

石？

![](img/c990a1d1bc1607ec62b9419da49f4cdf_70.png)

I'm not sure it's ALU。It's like arithmetic， well， it doesn't even matter just。Yeah， A you， yeah。

So if like one thread is stuck on this guy and it needs that cleared。

 maybe the floating point unit is cleared。So what happens is。呃。

It's going to save the state of this hyperth。Or not even that。

 it's probably just going to get the command like the instruction set from another hyperthread。

So two instruction sets。To completely different pieces of code。

 right and then's going to execute this guy from this guy here and then this guy here。😊。

And this the CPU does automatically。So the first part of the question is if the CPU has four cores。

 I can probably have more hyperths， so if I go to my test manager and see my performance here。

This CPU has six cores。But 12 hyperths， so I can execute up to 12 separate pieces of code。

 but it's not 100% separately， you know， because if both of these instructions need the same unit。

It's not going to be 100% parallel。But in terms of course， these guys are 100% parallel。

The hyperthts aren't， so this is six core， 12 hyperths， okay， so that's the first part。However。

 if you look down here， there's threads。And there's like 3000 or something。

These threads are OS threads。And the operational system。Operating system， right。It kind of a， well。

 see， it's changing all the time here。The OS can keep a state for a specific thread。Of any program。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_72.png)

So when we do here in the Windows， when we do the create thread。Readed。

All we're doing is asking Windows for one of these guys。These guys， it's not one of these guys。

It's just it's just an OS notion of what a threat is and this notion is just a state so it's going going to save this state however the OS is the boss here if the OS says okay。

😡，Well， so I have like 200 processes running on this PC。 So right off the bat。

 I can't have control over the actual CPU core all the time， so。And in this process。

 are running like 3，000 threads。So the US is the one that manages， okay。

 so they want to run a thread like this or this process and stuff。

So it's up to the OS kind of a manage， right， manage is the right word， manage which process gets。

Well， which thread gets the actual core at what time。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_74.png)

Okay， and for all we know they can change that during during our execution right。

 so when the OS like changes what we're doing， it saves our state， our CPU state。

To maybe run someone else's process and then go back。 So the actual answer is。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_76.png)

It's possible to do whatever number you want of threads， of OS threads。

 because the OS is going to manage that anyway。😡，However。

 we don't actually want that over that overhead of the O。 So in the game， you want。

The number of threads exactly as the number of hyper threads the user has。

 which is the number of actual CPU。呃。Not states， but there shall CPU concurrent operations that they can do。

 which is the number of hyper threads。Okay， which is 12 in this PC because it has six core。

 12 hyper threadreads， so we can probably do like 12 most so the main thread plus 11 that's what we want to do。

Okay， its not clear。 thanks， no problem， man。 I hope， hope that was clear。

 And you can also watch the other stream where we go onto the actual programming because it's pretty clear。

😊，When we create the thread and stuff， but we can create like 1000 and actual Jonathan blow does we have 1010000 threads as the testing for his language。

 but that's。😊，That's OS threats because the O is going to manage which ones the 10000 is going is going to appear at what point You're going to take ABC。

And we're going to call the Interlock Comp exchange。Okay。😊，So at this point， we're going to lock。

 okay， and that's it。And at the play。Sound point。At this point， we can only， we can only。Do this。

If we're not locked， so we can probably like spin lock， we'm going to create like a volatile。

I always have a hard time spell volatile， volatile。😊，Blocked。Okay， which is the result？像呃。Yeah。

 blocked my thread。Okay， and while we are blocked。I could probably sleep here or something。

But I don't think we need to， we probably print also。But I'm just going to set the block again。

And what this volatile does here， and that's a pretty good point because the OS and the CPU knows。

That this may actually be concurrent， right， but a compiler doesn't。Because the memory is shared。

 right， the memory is shared because these guys connect as the sound just the same。

 so if it's not volatile。Like none of these guys that I said is volatile。

The compiler doesn't know that anyone can change that。Exactly。

 then Lu take answers that so the compiler would be like， okay， maybe this guy is created here。😊。

And then this gets set inside the loop， but nobody here is going to set the value。

 no one is going to change the value， so this product is going to be optimized away。😡。

Because the compiler doesn't know that in another thread， someone else might change the value。😡。

With this compared exchange。So what the volatile does。It state， okay。This， this。This variable。

May actually change that at any time and you can't optimize that because you don't know where it's going to change that。

That's why we need that in this case。Okay one more detail for example you have 12 hyperthreads。

 I have an iPhoneO with four hyperths， do we need our code so much to detect number of threads3 degrees。

If you don't want to detect， you can just like ask for like 50 threads。

 whatever and theOS will do the for you， but since games are very perform critical。

 usually games detect and that's a pretty easy call to MSDM， but I remember right off my head。

 which calls that。That returns the number of threads and what we want to do is when we create a J queue then we programd another stream。

When you create a thread here， create thread。We're creating the number of threads that we take as a variable。

We will actually detect the number of threads on the computer。

And then ask for that number of threats， this way， we're going to have minimal OS overhead。

But it's not necessary， but it's usually beneficial in performance systems。In case of games。So yeah。

 but it's very easy to ask for the executive number of that because we were already managing that。

We created the job queue and we are managing like when did you like do next？see。Next entry。系。Entry。

We are already managed here， see we do the barrier and then we add the job to queue since we are doing all that work。

 we might as well call for the right number of threads and not have DO doing this actual managing。

Because the O is pretty slow， I mean， in terms of talking to us。Okay， hopefully that was clear。

And well， we're going to have to test that we might have broken the entire thing。But hopefully not。

 because that was pretty simple， I mean， just to review what we did， what we did。

 whenever we start playing the sound， we're locking the sound， oh gradually， have to clear the lock。

We also have to clear the lot。So after we finish playing the sound， right？Which is。

 let's see this four is the actual ammbd at this point。We can。Yeah。

 so it was good that we revealed this， he was wrong。Your macro is invalid， I think。

 oh it was invalid， but I'm pretty sure I fixed that。So interlock to compare exchange takess ABC。

 then it calls interlect to Comp exchange。ABC casting the ball long。 Okay， yeah， it was wrong。 I， I。

 I I originally the types。This。😊，And then a complaint about not knowing what ABC was， thanks。

 nice catch， man。Yeah， I did a， pretty quick fix。Okay。So re that in the compare exchange。

 and then we unlock that when we finished。A copying the sound to the sound buffer， okay。

 and when we play the sound。If the sun that we managed to get is actually blocked。

We wait so we spinlock， this is going to run like a lot's going to burn the CPU here。

 but then this' pretty fast we're going to at most do like， I don't know， 500 samples。

It's going to be pretty fast it's not going to log for a long time if we were supposed to log for a long time here。

 we could probably have probably think about a better solution， but this will be good enough for now。

Okay so why it's blocked， we're not going to do anything， then it's going to un block it。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_78.png)

Okay and we could probably， first of all， we could probably test the game right then we can just put a breakpoint here to see at some point if we try actually getting a locked sound。

 that would be cool to see because that's probably what causes audio artifact effects in our system at least。

Okay， so let's pray， everything works properly。Why not using the O solutions for synchronization。

 we could， We are using a semaphore here。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_80.png)

They are telling about， yeah， you are correct， we could use this well， in know W 32。

 we do create a semaphore。Here， yeah， to help with the waiting。

So theOS will wake our thread when it's running， so we are using。

 but we could have made a mute text here， but you know what。

 these kinds of locks are so simple that I might as well just create them from scratch because see that pretty that was pretty easy that was not hardly a lot of code right？

It's also pretty uniform across OSs and stuff。So in this case I I usually liked to do that。

 but in our job system， we did create a semaphore， which was very useful for the weighting。system。

I think sympho and indext are pretty heady， yeah you do want to avoid that。啊。

I think critical sessions are okay。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_82.png)

嗯。You know what I'm going to have to read up on that。Rritical sessions。

 is that specific to a Windows？

![](img/c990a1d1bc1607ec62b9419da49f4cdf_84.png)

Critical session and objects， okay， yeah。Is see critical sessions， exact， yeah， new text objects。

So I am going to have to read up on that because I'm not very familiar with those。Usually。

 I just create the semapho for our queue。Because if we are supposed to sleep in our queue。

Then I let the Sema four wake us up。Because normally， if we have a lot of stuff to do。

 that means that if you are perform performant， critical， critical， Yeah， in this case。

 we're not even going to。We're not able to do anything with the semophore because this is only called if we are supposed to sleep。

And if you are supposed to sleep， we wait。And in amount time。For a new job， in this case。

 I think that was a pretty good solution。I suppose， in this case。But yeah。

 another another problem with those objects is that。

It really depends whether they' are performing critical or notte。

 so you say new taxes are performed are pretty heavy。

 but a lot of games is new taxes all over the place。So to avoid this kind of undguity。

 I just rather just created the lock ourselves in spin lock。

 which was very easy to do with that our while here。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_86.png)

Let's see， I'm kind of nervous to see if it's going to work or not， let's see。🎼Gues we do have audio。

And it sounds pretty correct。It be crazy。Okay， that was a pretty。What I think。We are backing normal。

 we are going to have to test that for a bit。Let's see that crash again。That may have been a success。

Yeah， I have tons of playing。And sounds perfect。It's pretty cool see the results。

 but yeah it's awesome。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_88.png)

It's awesome because the whole thing was a lime stream， by the way。

 what are the numbers in the main menu， the numbers the highest score？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_90.png)

Because we have a safe system。So my highest score on this level was 1，200。Whi's pretty good。

 actually。This lab is 42，000。Because this lab is crazy。🎼Just craziness。So yeah。

 those are the numbers， they're not centered， so see this looks pretty bad。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_92.png)

And that's another thing we can do today。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_94.png)

Let me just go back now that we think this， this was a major problem because it was crashing all over the place。

 looks like you were prone space paint， well to my defense。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_96.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_97.png)

There's tons of Arabs on this level。And it's also breakout spacecing invade。

 its not actually space engagementrs， right， because this game is like breakout all over the place。

So see， I can rack up points pretty easily。There have tons of paras。几得诶。All we got to 901D。Okay。

 so we did crash。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_99.png)

I have a problem staying motivated when I work with Subs， it's pretty hard， man。

 it's not easy when I worked on my big project， which was three and a half years of development。

I had， had let me show you that was， that was pretty， pretty tough。So this project。

 I worked the first year by myself。Then for two years， I had a team。And then for the last six months。

 I worked on myself again。And even this project。🎼Which is a huge project。

 Australia using on real web stuff。I have motivation problems。🎼Yeah， and。And the problem is。

I had thoughts about quitting the game， even like。Even like six months before release， man。

 after three years， I would still think about cleaning， I was like。Oh man。

 I can't work that's too hard， it sucks everyone who's gonna to hate it so it's really hard to stay motivated even on projects that apparently look pretty pretty nice and that project that have been worked for a long time but I suggest that you do also shingles test that' it's procrastinating right now。

And I also I also have like very big waves， like I have huge waves of demomotivation and huge waves of motivation。

And what what I have to do is kind of， I don't know。

 bend yourself against the wall to try to work right， but it's pretty hard。

 So the way I like to do it that's not like very hard on me and also it's pretty pretty good。

Is that I try， when I'm not very motivated， I try to make it like a game game or something。呃。

I did the， let's see， Dan take Dan， but I did the community game jam。

 which like was like a couple weeks ago， like three weeks ago。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_101.png)

And I did this game for the community game jam and that was pretty cool I did that from scratch and see。

And what I also did is， pretty cool。It's like a small RTS game。

 and the thing about game James is that you can go to like the forums and I created a threat。

 I'm not going to define the threat now。Because there's tons of threads after that。But。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_103.png)

I created a thread like share your progress here。And then I could like keep working and then like seeing everyone's progress and then keep working。

I managed to。I don't know to get a lot of motivation on that week。

 so I suggest small projects like game jam like to two day game jam or at most one week。

 one week still a lot， just still can get a lot of procrastination in one week。

 but two days you can't。You can't do anything else right Yeah I worked so much for like a month or two on Scottish but some something broke my momentum and that's it's a big struggle since。

And you are correct because motivations。Can only happen so far。This project。

 the big one that I worked on， this one。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_105.png)

Imagine for three and a half years， I had all sorts of like huge productive monthss and like super non productive months。

The important thing to do。🎼Is Su just keep on a project despite。Those problems。But the problem is。

sometimes you did actually get in Portuguese， there's a saying like too much sand for a truck， right？

That are you。Like try to eat too much right， I don't know if that's any important I wouldn remember on side project but drugs is already a sad project itself yeah。

Rather， there is kind of a。It's kind of a rule that you can only do side projects smaller than what you have already shipped。

Right， otherwise it's going to keep you making side projects， right， like you said。😊，But。Yeah。

 if it's like a small two day project， like a game jam。

 I think it can't pretty much do that as a side project。But yeah， a big side project。

 you said that you worked for a month or two pretty motivated。So I suggest tackling smaller projects。

Then you can finish them and this project itself， I've been doing this project。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_107.png)

I've been doing this for a little over two months now。And 7074 hours， right。

 it's pretty hard It doesn't motivation because I have to do that on live stream， so I have to like。

I get a couple hours free on my time because this is a hobby as well as the side project。

 it's not my work or anything。I have to get that hours free and then I can only work with the game on the live stream。

 so it's pretty hard。You can every time go deeper on side projects the number is unlimited Yeah exactly man that's how your keep aware Yeah。

 it's just going about smaller， smaller but I have no interest in easy small price I had the same problem you know this。

😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_109.png)

This project， I don't know if you guys can see， it's calledsosis。

 I'm going to drop that link in the chat。This game。At that time when I created。

 which I wasn't very too indieated that， I was like trip away huge prime stuff。

This is like the smallest product I was happy creating， right， What do you do for a living。

 I have a software company， So I programme for a living， but it's not games。

 It's a random enterprise。😊，RPpa kind of software。Ive done't a few projects where I have a functioning game after a day or two。

 but they just lie on。R around unfinished， and this is a big problem because making games。

It's not's not that hard， but shipping games is really。

 really hard and it's it's kind of interesting to think about it because like。

This game I created like in one week， the live stream game， whatever kind of closed， Yeah， this game。

It's a pretty big game， I mean he has like you have like an army of guys， sure you guys。Oh。

 it's going to be too small， right？We have like an arm enough and there's like combat and it's like procedural maps and you can type stuff on the map to see what you learned about there's like correct clues and there's like false clues。

 there's a huge game。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_111.png)

And I did that in one week alone from scratch， right？

But the problem is getting that to a robust shipable form is really hard if this game on live stream that we are creating now。

 if you watch the live streams in order。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_113.png)

By date。By day two， we had the basic gameplay， and by day three， we had like a solid gameplay。

And by day six。The entire game was functionally done。 I mean， we didn't make another level later on。

But basic idea was done by day six。We're just like， I don't know how many hours， like 15 hours。

 whatever。However， were still in up to like 23 and we haven't released the game yet。

So it's really hard， man， I guess the side project is on the 100th iteration we look like a。

Cite simple calculateulates some two numbers。😊，Yeah。Well， I don't know。 So it's kind of hard。 You do。

 you do want to tackle a game that's easy enough to ship， right。

 because you do want to ship because it's pretty hard， but it's pretty。Pretty worthwhile。

 to be honest， you know， to see the game on steam is pretty awesome。

So you do want to create a huge game in this case to shift it。

 but I have to fight that for so I don't know I also have that conflict man I really want to do like a bigger game like this again。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_115.png)

But it is going to take at least three years of my life。You have to be financially stable。

 emotionally stable。I don't know knowledge wise is stable right。

 you have to be confident I'm creating that with the tools that you want。So with that in mind。

 I'm confident of creating smaller project of this because I don't want to take on big project now。

 especially the side project。But yeah， the thing is find small things that interest you and then work on those like this game is pretty simple。

 but it was this cool idea to implement like smaller acade games inside the breakout game。

 So that was what what interested me。 So that's what I decided to focus on。😊。

And that was pretty cool。 And that's enough to motivate me。

 And one thing's gonna feed on another like when I have the page on the team Im like， okay。

 so now I do have to release the game， right so。Yeah。

 incremental steps it's better than big motivation boosts。

 so that's the main thing about motivation you do want to because making games are a process。

 not an event。 it's not like we're gonna make a game then you do make the game No so I'm going to orient my life into making this game So this is the big thing that's why a lot of people have post release depression。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_117.png)

And I I didn't have like a full of depression， but I was pretty empty for a couple weeks at the game released。

Because for for not to release this game and we didn't have any budget thing like that。

 it's like super indy。And in order to do that。I had to orient my life 100% in order to do this right so my life was this game and when I finished it。

 I was like， okay， now I don't have a life anymore because my life was making the game and the game's done。

 right？So even smaller projects， you do have to orient your lifestyle around that。呃。

To get it finished so and that really solves the procrastination thing because sometimes you have big motivation spikes to get started and those are great。

But in the end， the process of like iterating that of everyday day so。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_119.png)

We did we did crash again。Which probably means that we didn't we even we either didn't solve% of the problem。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_121.png)

Or something else， for some reason， I can't look at the sound。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_123.png)

Oh， I can probably pass Z Z for more information。Or I can just。G the debug build。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_125.png)

Because we do have to。Do have to take a look at that。

 you have to see if our lock works correctly because the idea is pretty solid what we did。

Maybe Ga is our in to rescue you to work on power。ああ。I don't know， man。

 maybe I could working on half like three for three lifetimes they'll be done。But like。呃。Like 2300。

ちして。Funny， I don't know if you find to work involved anymore。You know what， to be honest， man。

 I really like making game as a hobby。Because。Like I said， making games is awesome。

 releasing games is not awesome。So let you work。As a hobby。You pretty much on。

Creation mode most of the time， right？However， when you work for a company or if you are on a serious E project。

You do have to be on release mode a lot。And that's where it becomes really hard in terms of motivation。

I think it' would be great all with that mentality okay， I don't know。

 maybe I'm going to send my resume or whatever。Okay， so we have to see that crash man。And。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_127.png)

。We've got to have a lot better， to be honest。Oh we probably at a break point。No。

 I'm also going try a break point。On the audio， let's see。Line 56。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_129.png)

Just so just so we try to， yeah， so at this point， we tried to read a blocked audio。

Let's see if this makes sense， we are playing this position at this volume with a fading speed。

This band。This looks correct， to be honest。Now， the blocks should now。Not these blocks anymore。

See now is not blocked。Because it's probably finished playing for that iteration。

 so then we just zero that out。Eex's correct。To make sure you mention it。

 you're terrified of number three。And like Dota2， this is also what you want to mention on the R CVV。

😊，I don't know， man。I probably would learn a lot by working on a company like Valve。

But I don't know if if I like the idea of like， I don't know working on it。

As an employee for a big game studio， I don't know。Not at this point， at least。So if we crash now。

 the problem is empty， so we didn't crash。So we managed to survive a blocked pass。

 so the block system is working correctly。Like blocking and unblocking。

We have to see that crash in race。And why because we have like tons of asserts at this point and the asserts。

Make sure that if we change the value during that。We probably had like a volatile。

Keyword to the sound。And since we are changing the value， it's probably by another thread。

 but now we just lock that so we can't change that by another thread。To be honest。Oh。

 I would still rather work at Val on their big studio， you're probably correct。

Probably valves on the list stuff。Sio is kind of worth working on at least。

I think we may just have to keep on working on the game。And whenever we see the on debug mode， right。

 and whenever we see the crash， we stop。T to fix that。I think that will be the plan。

It's like you've created a fucking rope like archenoid， but is difficulty man， really？Nes that hard。

Tacts may be a little bit too hard， though。🎼Let me see if I can be ts。Well。🎼ち。Oh， man。Okay。

That was a waste of a life。Dude。🎼See， okay。And this is thebu so it's not running。🎼10%。

But we're still hitting the 16 yet yeah。But thing about the way we are seeking。

Since we are not asking for the open GL or something to sing for us。

We may actually be sliping through the virtual blank， the vertical blank。

So it's not the best way to synchronize。Anyways。🎼Okay。自己。Yeah， I don't know， man's kind of hard。

 oh yeah， I was supposed to change his bo， to be honest。Oh。Okay， let's keep going。One more life。

I think I'm going to add fewer blocks in the Texas as UVVN。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_131.png)

Yeah。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_133.png)

Let let's， let's see。I'm going to。Kind of a keep。I keep an eye on audio just to we finish the other things that we minutes to do。

Make the failing more evident， I't know man。It's kind of fuel stuff。

You could spend like ears working on these smalls， of making the place being tighter。

 get the mouse not to reappear。I don't know if you decide the player。

 I'm not so not a big fan of this。 This is this wrong thing。 I think we we may have。

We may have finished it like is。This wrong。Oh no， it's not wrong。So we may think。

 by the way it's an open source music from somewhere or， I created that myself。

I'm kind of learning that， how to make music。So that's pretty cool。 And because I made that myself。

 I could make like a。😊，一次。😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_135.png)

I can make like the menu， can hear that。There's the menu of music。And they gameplay。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_137.png)

It has like different nice features and stuff。 So yeah， the music in mine。

 I didn't want to fus with like。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_139.png)

Licenses and stuff because I want to distribute the game for free， right， nice， yeah， thanks。😊，Well。

It's kind of it's really helpful to learn how making a signal only to do like small one main projects like this。

But also because when are you thinking about music？

Things like timing and a game feel becomes really clear because music is like 30% about rhythm。

 right？So knowing that。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_141.png)

It really helps to make like good feeling animation。And synchronization as well。

 we didn't do a lot of sync。And maybe we didn't do anything z at all in this game。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_143.png)

But in the other game， then I have only childo that you can play and take a look。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_145.png)

YouSee。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_147.png)

I did do a small。This game。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_149.png)

I did do a small system where the music kind of changes every quarter note。

This one you have drum behind， yeah， I do have。I do have a。Yeah， like trying drums， it's pretty cool。

😊，Although I haven't used it for creative use for gamego yet， let's see。

 I only created like music electronic music， I just click around the do to create。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_151.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_152.png)

So yeah， so we consider that this is maybe wrong， let's just take a quick look。

On the other system that we can actually review so and this is this is probably also wrong。

We probably don't need to。T run this before。Yeah， this may be wrong instead of like precalalculating。

The sink sounds。We can probably just do it here。Like if you're supposed to play this sound。

 then we sync。I think we're going to do this。Thiss way we can eliminate this loop。

 and then we can only do this after the lock， okay。呃。I think。😊，The thing this will work。

 in order to be 100% synced， I have to make sure that the sink sound。It's actually after this guy？

Correct。Because if I start playing。呃。This sound。And then the same town and then this one， well。

 I don't know， I don't think it's going to matter。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_154.png)

Anyway， this sync is really for the menu。And in the other， the menu when the。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_156.png)

And the gameplay music is not 100% perfect if we're supposed to play like two tracks on top of one another。

 then we wouldn have a pretty sa system， let's see if it's pretty。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_158.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_159.png)

Now， we're broken。We broke that。We changed the position。And the speed multiplier。If you are sinked。

 if I remove this sink thing， we're not going to be synced at all， let's see。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_161.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_162.png)

But it still sounds sync。And the reason is sound sync， sync sound。Yeah。

 weve zero this out and then we come this out and the reason we will sound same。It's because we play。

 let's say， playing music。嗯。See。Play sound。Yeah， so we played the main music and the menu music。

Pretty much together。So if this gets run like。This is the amount delay we're going to have。

So we may actually not care about the same thing。To be honest。But why was that wrong？嗯。

You're setting the position。Embasssy。If I happen to do the other way around to play the。

Which one is synced？The menu is synced to the main。 So if I play the main， the main after this one。

Yeah， that correct。Because in this iteration of the loop， I'm going to see。

The position of a sync sound， which I haven't updated yet。Then update this guy。

 then update the same sound and then they should be the same。So I me just you if that makes sense。

 then we can put an assertion here。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_164.png)

So yeah， that was perfect。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_166.png)

Yeah， so we worked on that just by changing the order and then here we can pretty much assert。

There we're going to run through this sound first， so we're gonna to assert that sound is greater than sound I'm a sound sync so I'm just testing for the pointer position and actually this is the other way around So I first have to update myself and then the sound so let's see this to not assert perfect。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_168.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_169.png)

But if I do the way that I was doom。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_171.png)

I should probably search。Yeah， and I do a search。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_173.png)

So this is correct it's kind of a pretty bad limitation for the system。

So probably if you want to expand this game， I should probably review the way sync sounds work。C。呵。😊。

But。This will work pretty nicely， I think for now， we're going to get sync sounds and then we're not going to have and this may actually work because this loop was not locky。

And we were changing the sound here。So that crash that we had。This was probably。AThe culprit。

 the cprit。 Okay， so by just doing this guy and just running and doing the。

The lock here and the unlock here， we can make sure that we operate on the sound on this thread inside the locked。

想。And the other one， we just set the active as the this we can do with no problem。

 we one can do is set the sound。 So that would cause a crash。

 And we want to do this in the play sound。 So I think now this is a pretty solid system。

 we do have to re。😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_175.png)

I this wrong thing？Butら。I don't think we're going to crash the mark。And are。

 those are some strong words。But I don't know， I am willing to bat。

That this game will not crash because that opposite system。

And that's what we want because we want to release the game and we don't want to release the game crash right。

That's perfect。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_177.png)

It's pretty solid， collision is pretty solid， everything looks solid man I think we were getting pretty close to read。

 so let's see if is this wrong really？😊，So。This just getting the sample， what sample we want to run。

So the same is the sound position。A clamp between zero and。The sound。Sample count。Minus。

So this I'm not sure it's correct， the sample count minus this channel minus one。Oh， okay。

 because yeah。Yeah， I think unfortunately， it's about a night here in Europe York。

 So I'm going to bed bless you。 Yeah， and I'm going to see this later on YouTube。

 Good luck and go and see you。 It's awesome， man。 Thanks a lot for dropping by。

 It was awesome talking to you， man。 Have a great night。😊，It's pretty。

Ptty bright here in Brazil still it's around around 530。 Yeah。

 it's pretty pretty early we can do a lot of programming still。Okay， so I hope to see you later。

 maybe there's going to be the last stream， I don't know if you keep crashing。

We'm going to do one more clean upstream， but I'm pretty confident that was the problem。

 this other loop was the problem， okay？So I can probably document this。I clamp。That to the。Sound。就。

This。😊，Because。I add。I add more。Because they get。Samples， I get more samples。

Based on the sample count。Oh。嗯， the same。I won't say this。

 but I pray crashing for more crashing Yeah， okay， I don't know， man， even if this game's done。

 I can probably do more more games live I I'm not sure I'm gonna to do my entire game live anymore because that was pretty hard this may actually be the only entire game I did on a live stream but I do I do go on a live stream from time to time。

😊，Although I am going to have at least one more live stream for this game， which is the release one。

 I'm not sure I think this is going to be the less coding live stream， but we may have one more。

A crash is good this way even know that there is a problem。And I'm going to add to that。

 I'm going to say that question is good because this way you are sure that there's a problem because you probably know there's a problem because there's always a problem。

 right？Right now， we're not sure because we we did crash we knew there were a problem。

 but then we change this。 So now we don't know if there was a problem， right。

 So you are correct in this sense， it's kind of a。It's kind of a gloomy scenario， right。

 not very bright in the sense。😊，Okay， so another question is， should I， should I do like？

A floor or a clamp and the question is I don't think it matters most。

 so I don't think I'm going to remove that is this wrong comment？

And I'm going to say that this is wrong， so I am going to clamp to this guy。Instead of clamping。呃。

For every buffer， I clamp。Instead of claming ors probably， well。I could probably just loop again。

 but this for every sample。So I couldn assert。Probably， and this doesn't go through。But to be honest。

 one sample problem is not going to make。Sound that bad。At all。So。

But at least we think about where we double， we double think， we double。

 we double checked about this next value so we can remove this。

This this wrong make full screen watch prettier， I think you can remove that because I think it's pretty enough。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_179.png)

I tested that on stream， I can show you guys on stream。I'm going to open up steam。

And I can show you guys the game launching on steam。Let me just make sure。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_181.png)

And you guys can see the full screen。That's not the full screen。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_183.png)

Yeah， this is the full screen。来 see。See， first of all， there was super fast， a super fast startup。

 super fast。So that took have little longer。And we have like one frame of a white screen。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_185.png)

we could make it like a black screen that on a white screen， but who carefully， and that was so fast。

That the full screen startup is perfect， I think。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_187.png)

So I'm going to call that a day， so not a day， an item。Savor and quit。

 I don't think I'm going to need to saveor and quit because we are saving。

 let me see when you are saving， save。😡，Save game， save game。Let's see when we are at college game。

We call Sa game when we finish the level。That it。That's it and since we only care。Save is your only。

Change the state game。When we changed the level， so were receiving every time it was so the sound problem was yes。

 it was fixed， we can call that a big， so we had two problems， at least two problems。

The first problem was the lock thing and that solved。

 but we crashed again because we were looping here again， we had another loop like this。

That was testing for the sound sink， so this is what we had。After the we the lock。And this is。

Probably I'm going to say like 90% sure that this was the problem why we crashed because this was the same problem we were changing。

The sound here。And as far as we know， we could have gotten like the active sound here。

And then we were like， okay， it's active， however， then we would run this on the thread and then would clear the audio。

 and then we would try to access the sync sound。And like the sound position stuff。呃。From the cleared。

 so this was really problematic。So now we are assured that this thread。

Whenever it tries to work on the sound。It locks the sound。So。I'm going to call that fixed， however。

 I am going to keep an eye on the audio for this stream， see if we crash not。

 but I don't think we will hopefully not。Save and quick。

 don't need stay quick make the players return the out curor when before I say。

 oh I don't know what the thing is， when we try to play that let me make you guys full screen again。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_189.png)

When we try， is it normal to Brazil that someone's screaming outside at 5 a。 dude， it's 5 pm。

 Look at the sun， man'am Steve can show guys outside a window， I't know。

 I don't have enough camera for that。I don't know if you guys can see， but it's a bright day outside。

Well， I'm not okay， so it's normal for people to scream outside Brazil。😊。

At 5 PMm because it's really hot today， like really hot， I'm not even sure how hot it is， Let me see。

It's probably maybe you guys come from like a harderter place like。Temperature。Let's see。Well。

 it says it's 30。With 26 degrees， 26% of humidity， so 30 degrees Celsius。

 which is like 87 Fahrenheit。And the maximum today was 92， and somar is going to be 93。So。😊。

It's really hot， everyone just playfoot exactly， man。

 it's like kids playing outside because it's really hard hot and people want to enjoy the hotness。

And everyone single day is sick。And the only what an only onegu Dan is sea what？Yeah。

 and you know what， I probably got some more water。Because I'm sweating like a lot。

But I really like the heat， I mean， if I if I didn't like the heat。

 I'd probably bit miserable here because it's hot here。But yeah， I really like it。

 but it's pretty hot these days， maybe a little more than I yeah like。😊，93。34， 34 is really hot。

 Oh my god。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_191.png)

Okay， so testing the mouse position， so when we finish the game。

 the mouse goes back to the center of the screen。And we could probably save that。

And then return the mouths to deposit position， but to be honest， I don't think I care。

Because if kid is going to focus on playing the game， it's not going to remember where the mouse was。

So this would be like a more robust thing。I don't know。More robust thing later on。

Or maybe we could do that， I don't know。So I think I'm going to do the center test text thing。

 It's going to， pretty quick。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_193.png)

The problem we have just so you guys see that our text is centered like the space invaders。

 but our numbers are not。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_195.png)

And this looks pretty bad。 So in the menu， and I think I only care about that in the menu。

 I have drawn number。Yeah。😊，Let's see our withdrawal number。知aw number。Okay， we said the P。Okay。

 and it's pretty cool because our number are fixed size。

 which is four times the square size except for the number one， which is two times。

 so we have to can pretty much pre calculateculate that。Before。Yeah。

 I seems you don't have a lot of numbers anyways。We can probably。

We can probably just run through this twice。I think and calculate the P and then outside the P。

I think that'll be the best call。Yeah呀。Like centered。Text。Okay， and if it's centered。7。😊。

If can enter text。I'm going to run through this。对。It's going to be the same thing， right， however。

 I'm going to tell like if digit。Digit is。1。I'm going to add sorttract。This guy from X。Otherwise。

 we'm going to subtract this guy。嗯。Yeah， so。F。This is for debug only I think。False。Yeah。

 draw messages false。And this one is going to be true。This I me get really false。Pause。

And this one will be false as well。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_197.png)

I think that's it， that's it。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_199.png)

Well。Something was massively wrong。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_201.png)

What happened？What happened？Oh， have。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_203.png)

Okay， that's funny because since we are the audio is multi threaded。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_205.png)

It runs perfectly， but we can't get out the game， the game's not right。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_207.png)

So we probably probably make up。Really bad job at talking that code。Software rendering。W哦。Let's。847。

Appear。Yeah， we do have to change this guy。Have to update the digit。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_209.png)

Okay， thats probably the problem， I's see。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_211.png)

Okay， now we don't have any。Text。Yeah， because number。Yeah， so that now we're going to do like。

Number and I'm going to change number to n。Number  well。Not this guy， number of zeros。

And probably also a number of leading zeros。Totally unpredictable behavior。Yeah。

 I'm also going to have to save the zeros。Number。This way I don't alter the actual state digit， yeah。

 just the P。But I think I got to the wrong place， I should have added that， yeah。

 should have added that to Sany。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_213.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_214.png)

No， oh it's half that。So subtract。Subtract half。Of what I was supposed to do and this really pretty ugly code。

 but since we're pretty much shipping， we don't really care about that。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_216.png)

But this is super handy。Funny。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_218.png)

This is really bro。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_220.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_221.png)

So I'm pretty yeah， I'm starting from the left。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_223.png)

🎼Enjoying them to the right。So I have to move that right， I think yeah， I have to add that。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_225.png)

Okay， see， I was subtracting X。 So this is weird。 I'm drawing from the right to the left from the left to the right。

 Oh， of course it's easier to draw a number like this。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_227.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_228.png)

This looks better。I'mNot sure it's 100% though， so let's just make sure that in the menu when we call draw number。

We've better the same position and we probably don't。As the drug text。ラl nameピー。Yeah， see。No。

 this is correct， same x， which just subjecttract 14 and Y。If I just pass B here。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_230.png)

Oh， another thing I want to do， I just remembered I'm going。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_232.png)

A quick note before I forget。I could probably add another thing to the Con file since we did the Con file anyways。

So， add the。F sync option。这 they con speak。File， that was pretty cool。 We wrote that last stream。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_234.png)

I very five parser。So is this correct？This doesn't look correct。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_236.png)

If I don't send her that。Let me see if I get starting from the ending as they ending at this Ob probably have one character off Yeah。

 we do have one character off。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_238.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_239.png)

That coat is super hacky。Or half a catcher， to be honest。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_241.png)

That's super weird because we let me try to draw for guys to understand。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_243.png)

That a super bad drawing number of code well。Anyway， we know it's a bad number draw number code。

 but it's even worse than we thought， right？Let's see we're drawing like item 78。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_245.png)

We start at the center of the last character。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_247.png)

Okay， this is where we start。And we end well， and we are supposed to。To move this in this case。

 we just want to move half this character， so we can move the full width times two。

 which is one character that will make us center like this。Then move back this have guy。Right。

 the problem I don't know if it ends on one。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_249.png)

Partard two or another number， right？So what I can do。Which is pretty hacky， to be honest。

It's like last move。Right。And I'm going to set that to the last move。

You say that last move is a square。And this guy。Is a last move。

And then I'm going to say that p dot x plus equals the last move。

And then when I finish iterating through the number， I'm going to。Is see， I'm gonna to remove。

The last move。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_251.png)

If by2。So。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_253.png)

Yeah， no， just the last move， so we don't need to do the last move right school。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_255.png)

I don't know that was that was really hacky。Hey， man， nice to see you here。Awesome。Okay。

 so now we are standard。So yeah， no we are pretty center。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_257.png)

No， you know what？🎼那还先生了。This problem is just half。Like we originally thought。No， oh my God。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_259.png)

Twice。This is super hacky。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_261.png)

No， is the entire thing。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_263.png)

It's better than before。And they'm going to settle with good enough。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_265.png)

Looks pretty centered。And then I can go back to the old position。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_267.png)

And oops， let' me show what I did。How you doing， I'm doing great man。

 we are really close today Max actually need our last coding stream， to be honest。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_269.png)

And we our last coding stream because the game page is already up on team I can already play the game on team。

 this nice team account， and I can play the game on team， which is awesome， you know when I started。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_271.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_272.png)

I actually didn't think I could actually release the game on steam， that was pretty cool。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_274.png)

Because the game looked pretty cool and you can see the whole thing on the steam page。

And you can relist that and I post a couple of live streams that。You know。

 the new updates is and looks pretty cool， to be honest。Pretty， pretty nice。So yeah。

 I'm super excited， man to release the game。We we made a couple of it's going to be almost like 80 hours of entire development。

 which is good enough。I mean， if you see like hand heroes first 80 hours。呃。

He wasn't close to shipping， he's not been close to shipping still I see som going I'm going to say。

😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_276.png)

Their our mission was accomplished， the mission was to do like， I don't know， a simple vert。

This not looks standardndered at all。This looks pretty standarded。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_278.png)

Maybe the ones on 100%。Let me see how that looks full screen。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_280.png)

So I suppose the mission was accomplished and the mission was to make like a simple。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_282.png)

Handmade hero kind of stream， so we're going to code the entire game。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_284.png)

From scratch。In live streaming diet process。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_286.png)

And we are close to release， I think you're going to finish today。Yeah， it's not 100% centered。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_288.png)

Let us try and get the centered codehe center。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_290.png)

Because I don't know since we are doing this， we might as well， right？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_292.png)

If I don't do the last characterter offset。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_294.png)

It looks worse。But based on our。Oh， we do have to do the less act offset plus。The spacing， right。

 don't we have a spacing？I suppose this already has the spacing。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_296.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_297.png)

Yeah， so have to move half of that character over。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_299.png)

Which is this guy。Last half of the character of the last character。ok。😊。

Maybe we should add that yeah， I think。I had don't know没 I。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_301.png)

はい。This is superhey， I think I'm going to have to live with this。

Not perfect centering see pun looks perfect， oh， not perfect。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_303.png)

If we make that time two， it's going to be way too much， I suppose。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_305.png)

🎼Well。🎼Not really。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_307.png)

And you know what， I think now that looks correct。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_309.png)

And you know what？This can actually be not two， but actually be one plus the spacing， which might be。

Which might be one， so I'm gonna。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_311.png)

Let me see it's probably not going to change much， yeah。But this looks correct。

At least it's good enough this one's not 100% Let me see how that looks with a zero。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_313.png)

0 guys。 So I'm gonna。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_315.png)

Change our save。Yeah， so the zero looks pretty cool。Pretty well centered。

And one of the things that we should be considered？It's like the first。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_317.png)

Contact with a game。Right， if you just。Turn the lights on， starting to get dark here。

The first player contact with the game， so when the first player launch the game。

 this is what he sees， right？

![](img/c990a1d1bc1607ec62b9419da49f4cdf_319.png)

I think it's pretty clear。Late direction。🎼And like。Meanneractivity of it。

And like the YouTube channel and stuff。I think this is really clear in terms of goal， right。

 and it shows all the。Objected things stuff。So this is great， I mean， this animation right not map。

But I'm not 100% happy with。It's the windscreen， that's why I said that I needed maybe AMor。

Happy win kind of。You win kind of stuff。I might actually。Ma actually add the union。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_321.png)

Yeah， let me just analyze that If I go to like the levels。And I have the block block。爱奇。

I'm going to add， I don't know， just like。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_323.png)

我不。🎼W to make it very easy， too。 That was awesome。C？😊，This is not very the best I don't know。

You'll win cannabis of this。So what can we do？The good type you win。

And then we could pretty much immediately。ok。And fireworks after Winnie。He said we crashed。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_325.png)

Mision failed。Mi should say， oh oh， when we are in a release build。Oh crap。

And we are in the optimized build。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_327.png)

This sucks， let me see。So we are in the update game audio thread。And the main thread。

It's in the spawn particle。So he probably just ran， let's see。Probably。It's see sp particle。

Probably ran a sound as well yeah。So it either just played a sound。

Or it's about to play a sound because it's not 100% trustworthy， right？I don't know， maybe。

Because if just setting some random particle stuff。It's okay， but at this point called it， yeah。

 you were correct， man。So at this point。We are， we are about to add a couple salads。

 And the thing is， we added a lot of stuff like。I think it's the。

This one that's about to explode right that that wants to add product effects。

 but we have a strong block， so this is probably going to add like a to of sound effects。

 like a ton of them。Maybe that's the problem when we add a ton of sounds。

 and I'm going to make a re situation like this。It's going a pretty cool thing。

 but let's just analyze that that's the main threat。The audio thread。Is。I can't see the values。

For some reason because。How come the optimize sound out？Well， okay， so yeah。

 we do have a couple of eFfo。I is。好。Yeah。Playing sounds。So yeah， we don't see the value of sound。

 which is a hnge bufferer。Right。And。That's suppose access validation reading。

So I assume it's the sound sound sound sound DDOS。Yeah， I think that was a problem， man。

I think our song just got a DDF tag。Because。Reds strong blocks。

See in the bottom left corner and strong blocks means that instead of destroying the block。

The boat's going to redirect。But this is a comment， so it really doesn't want to redirect。

 it wants to go straight through， so this is going to play the sounds like a lot。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_329.png)

So okay， I am going to stop debugy， go back to the non optimizeized build so we can probably read that if it crashes again and try to reproduct to re that。

 so I'm just going to go back to the normal play。And。And test couple things。

 Now in the in the let's say。Either play sound。Because we call it the play sound variation。

 but it just call the play sound。This is the only place， right？That we have like a plain sound。

Let's see， yeah， it's going to place。So。If it's okay， first of all。

 we can try to get the first free sound。And if we do got a free sound。We just use it。

If we didn't get a free sound first。We assert。And the next place sound is greater than zero。And last。

 okay。And then we get。The next plain sound。Okay。And then。If。And then add that。

 and if we are greater to coator count。We said that to the immable sound count， which should be。

We should be。 Let's see。In the audio system， immutable。Oh this is a game， I suppose。Yeah。

 we said that to the next plain sound。When we finish adding the initial loop sounds。So the thing is。

 if I add like only like kernel。Oh， first of all， let me see how many in sounds we have game two。

 five， two， let's see。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_331.png)

Well， we don't have the game， right？Wow， that's a bummer。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_333.png)

What you like。What is it called。是唔你惊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_335.png)

他得定。Let's see when we update a game， okay， let's see how many immutable sounds we have。

We have 26 imidable sounds。That's a lot。Why do you have that many minimalable sounds？That's weird。

See in next。Sound， it was it called。Ex plain sound， Next plain sound， let's see。Okay， zero， perfect。

Okay， so we load the sounds， load good maps， Okay， so this where we'， we play the music。Both music。

 both musics。The movement sound。Perfect。Then we had a block。We have a sun for each block。

Over for each power block。ok。Yeah， which are 16， so yeah， that's not the best solution。by okay。

So I'll take 26。I'll take that。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_337.png)

ok。😊，So the truth is we only have a very limited number of sounds besides our constant 26 sounds。

If I make that 30， well， it would like 32， right？Can made the 28。I expect to see a crash more often。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_339.png)

Well， I didn't crash， which would， well， to be honest， I didn't expect see a crash。

 I mean I hope to see a crash。Because we are dealing with that correctly。

 were just going to overwride the sound。🎼So we don't hear all the sounds。 See。

 Did't hear all of them。Butら。Yeah， this is kind of what I expect to see just fewer sounds。

Let's see react if I get to caught。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_341.png)

It's perfect， to be honest。So let me try。In the end of they knit。I do like a huge for loop。

And then I play a bunch of sounds like play sound。Let's play it。It's good a comment。的眼。Well。

 I do have to finish writing the for loop， huge mean's okay。Okay， so this is the number。

That I was told to be huge。Okay。あ。But I mean we have 28 slots， 100 is going to go over 28。

 28 a lot of times。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_343.png)

Yeah， nice， ma'am， we did crash。😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_345.png)

Let me see。If 100 would cause the crash， so this is actually the actual answer to the question is 100 a huge number or not？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_347.png)

那'次。Oh and it didn't crash， dude， you are totally right， you know what？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_349.png)

Every time I need a huge， I may actually actually just like。😊。

I're going to add that to the utilities。Because。This is a huge number。

You are the only one who's happy when the game crashes No。

 I'm not the only one admin 2244 is also happy when the game crashes。😊，It's also， it's great， man。

 because when the game crashes， means that we。Can solve the crash he said that it's great because you're sure that there's a problem。

 right？Okay， so this is a huge number， so if we are greater than a huge number， we crash。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_351.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_352.png)

Awesome。😊，You know what， this time didn't crack， this time was assertion failure failed。

But it's okay， it's the same effect now。This sounds that we're trying to play。Oh。

 but this is another problem。Well， or is it？The problems that we don't have。A sound。

But we did have a time， Okay， so it's not the same problem， okay so。It is， it is active。

 it's not blocked。Why is it not blocked？Okay， so we found the problem。

 the problem is I blocked in our block system。Which sucks？Why is it not blocked？

You know that there exists。Yeah， we could make， we could make。It could make this number so huge。

 but it can't type it， you you could make like cut。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_354.png)

And this note， well if I I make that a long long。I can make that a huge number。

Now this is a fucking page number， but I don't think we need a fucking page number。

 just the page number， it's good enough。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_356.png)

In this case。Okay， so let's again see the problem。So we already asserted that a few times。

 so we can be sure。Then the process of like this。To this point。Something changed。And you know what。

 we were zero， someone zero us out， man。Someone zeroed us out。This is so weird。呃。

Let me see assert this guy and also assert。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_358.png)

Most athletic programming has some weird stuff。If you're not like 100% safe and do all sort of stuff。

 this is why we don't need to do a lot of stuff we don well， not that we don't need。

 but we shouldn't do a lot of stuff， except if we really do need。

Don't use it because your game will crash team and gave them with the later your tiny game。Okay。

I't know， they did reject the game though， because I didn't say the source code and it says on the page that I do have the source code。

If I am going to say the source code， do you， come on， they have to chill， I have to assert。

That the sound block by thread is true。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_360.png)

Let's see if。Okay， oh。It's not blocked by thread。We are probably wrong， man。In our interlock。

 compare exchange。This is so weird。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_362.png)

Do we timepo something like interlock compared to ABC？Interlock Compare Exchange ABC。

This looks correct。And in our interlocked compared change here。

 we passed a new entry in the original。And that's what we are passing here。はいがある。The new entry。

In the region， no age is true because I want it to be blocked。Just。As a。Test， I suppose。你翻呀。

If I don't do this， do I crash now that I have this assertion in place？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_364.png)

🎼I don't crash。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_366.png)

So when I do have a DDOS attack on my audio system。I crash。

But this doesn't make a lot of sense because play sound。It's going to try to get。Maybe this is wrong。

 that explains sound。嗯。You know what， I think I'm going to tag。I'm going to do， like。H know。

When I play the sound， I'm going to tag it。You I have like incrementing values so I know which sound。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_368.png)

Crash the game。爱奇。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_370.png)

So the sound that crashed was sound， what？Oh， is that because of it。No。

 I thought it was because of a。Buff for overflow， like energy overflow， how many。

 how much is our huge number anyways， we see， yeah， it is a pretty huge number。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_372.png)

It's 100 million。嗯。😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_374.png)

Okay， so we crashed。We crashed in sound 44 millionlia。It says it's not blocked。嗯。

This is really weird。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_376.png)

Because this， oh， wait a minute。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_378.png)

Wait a minute， I put a breakpoint here， but it crashed before it reached the break point。Oh。

 because this guy also has to do a compare exchange。Yes。I can't do。It compare like。This。😊，Yeah。

Because。Yeah。😊，Maybe it's not blocked。Then I entered this point。And then it's blocked。

So you know what？I may actually do instead of just like I blocked my thread。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_380.png)

I'm going to do a more robust thing。Of doing， like。Type de， I don't know sound。Access。

You're going to do like sound reading。Like sound。0 me。Sound。ItSo normal。Okay。😊。

And I'm going to do a volatile。Sound reading。I think this is going to be a little bit more robust。

 let's see， tile。Sound reading access going be this result。And well。

And we'm going to make this like also compare exchange， let's do compare exchange here。So。

This is the sound。Read the access， the original， the new value is going to be。The sound reading。Yeah。

规一定。Okay。Danger lock is going to be。啊。I we can access。O。And assert that the。

What does he called it again？I forgot， oh， it's called that reading， that's called an act。Access。

And I'm going to change that to a complex change in a moment， so I'm going to ignore that。Access。

This will be the axis。And assert that the。Access equals to soundwe。I can probably would you like。O。😊。

And I can probably do like。I going do like a macro for this。But。And this one the sound model。Okay。

And I'll at this point。Well， you know what？I want to change that。To the。Yeah。

 I have to change that way。Yeah， let that change that first。 So the thing is， if this guy。

If this guy original value， if this guy is not。好， if。For a while。Original is not。AI blocked。

A sound normal。安装啊。It's been like this guy as well。Anyway with the moment it is locked， well。

 you know what I can do the normal thing。I can do the while interlocked right into a block。Interloed。

 Yeah， this guy inside of the for loop， right。So， yeah， so for。Okay， so original。Access。

I going say if we're regional。Is not。The小 model。Continue。Okay， they had no value and then this。

 instead of a3， I'm going to do like and if the interlocked。If things are locked， it's equal。

Do like this。If it's equal to the original， please that we piano play all。O。😊。

I'm not going to do this down here， but I am going to assert this the case。O。Okay。

 so this is a more correct thing I suppose。I'm going to do the same thing here。

So while it's not normal， I'm going to spinlock， and I'm going to change that to sound。Zero。

 I probably call that writing。And I'm， I'm going to search soundsy。Let's see， I don't know。

 access is' not a number of loaded sound。This is result。Result。ComM。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_382.png)

Okay。What do you guys think will happen， you guys think is's going to solve the problem？

Cause a new problem or I don't know。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_384.png)

Okay， so it's still crashing。We are set to sound reading。I guess they crash， yeah， we did crash。

You are。We are setur reading so， we fix this problem。Which is good。Because。😊。

When we crashed this before， we weren't set to block and now we're set to read it。Oh。Oh but yeah。And。

The play sound。If it's not normal， we continue。We only should do this if it's normal well。

I'm going to be really stupid here and then assert it's normal。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_386.png)

Yeah see。Okay， so we survived for a bit， I could hear a little bit of the sound shifted it we are yeah。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_388.png)

I mean， we could ship that problem because it all happens when we pass a huge number， right？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_390.png)

But it is a crash。Cryts aren't fun。Sound was no。That that's so weird， man。

 sound was no right after we checked。If sounds not little， right after we insert that。I mean。

Literally， we test if the sounds are low。We test that。And it's funny because it's not no， oh。

 the samples are no， no， it's simple no no， okay， so now this is weird。

It's saying that sound sound was an no pointer。But it's not an no pointer。

What happens if I try to ignore this？'s probably notgon。You see， you go to this assembly。De。

 this is so weird。We are in the compare line， okay， so we are in the compare line。See。

 you your studio sucks。Because we are in the if sound， sound samples line。And it says here， oh， well。

 this is correct。O。So Vi doesn't suck。So it's so weird。We are on， we have zero on that registered。

We have zero that on。Yeah。But on the actual pointer。We don't have zero。

Then it'll be let you explaining how the first day patch actually。

Would it be so that you create an additional stream explaining how to the day。

The first day patch after the game release。You mean how to say that to steam？Well。

 we are going to do a release stream， so maybe we we can do like a release celebration and fix at the same time。

 I don't know。😊，Dude， this is what I don't understand。5愿50。Okay。Yeah， I don't know。

So we're moving this pointer。Should this registered？I me just， yeah。

Then we're just adding eight to that and then it becomes zero。This is so weird。I have no idea。

I have no idea what the problem could be， to be honest。Because right now we do have samples。

And it's trying to add eight， which is like to get the samples。Member of thatstruct right。

Where am I here that is the same？It's trying to get at8 to this no pointer guy。

 so that was the problem。Noow， you' de accuracy seeing a pointer and its results into zero。

Sound sound is0， but yes otherwise okay so。Okay， so this is a bit better I suppose， so you're saying。

That vig city is wrong。Which is not news， right？But we just move it again。Yes。I wasn't a very。Okay。

So you're saying you go back to the audio， so you're saying that sound this guy is actually yeah。

 the simply tells us so it says that it's zero right and we're trying to direct that we're trying to add this eight guy here。

And then to zero is the point。You are correct， so the pointer is zero for some reason， but look here。

When I first set that Richard， it's not zero， it's a valid pointer。See， this is a valid pointer。

 first of all， first I move that， which looks like a valid pointer。Right。To thisす。

Then I just add eight to that in somewhere along the way。It was zero。

So if I can't trust the visualual Studio the bugger。Oh， next place house is 27。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_392.png)

How much， much explain sound do we give？Also， we could probably add that to a huge number and that would probably solve the problem as well。

Oh，' 28。So we are on a very limit。On the plain sound。But 27 is still valid， yeah。

 you take your point or just sound from the stack。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_394.png)

呃。It's appointed pointer to the stack。呃。You take your point to sound from a stack。

Then you take sound， sound。And that results to zero student't learn assembly， yeah， you know what。

 I do have to learn my assembly to be honest。Yeah， you are 10% correct that I do have to learn but come on man。

 you are helping me out here。Sound is zero， correct， sound sound is zero， you're saying， right？

Sound sound0。For a sound， sound sample zero because I have just tested if sound wasn't zero here。

So if sound was zero， or are you saying that it changed along the way because there was。Oh。

 you know what， he may have changed， to be honest。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_396.png)

It may have changed， I think you are correct， that I can't do these tests。At all。Until I lock it。

Okay， this is a bit better。This is a bit better。香相的技术y。Okay， oh， this is zero。But if this is zero。

 we should have continued。And not tested sound samples， and that wasn't the case， right？

Looks like a good time to create sound sound， sound samples。But if sound sound was zero。

 we shouldn't be testing if sound sound samples are zero。

Because the problem is we tried to direct this pointer。Yes， exactly。

So you're saying that it changed along this way， which I suppose that's the problem。

 I think it's correct， this wasn't zero in this in this point and it was zero in this point。

 which means that it changed you that I have to lock。Before it we do。This is correct。

Now I do have to unlock。When I go through the loop。So instead of continuing。I'm just going to。

 let's say。Like if we are active。And。We have sound。And we have sound samples。I can do everything。

And if I don't， I am going to advance anyways。Okay。So now we shouldn't do this test。This test。

 which is the only that we did。Before Lockhe。So I hope that the value doesn't change from like。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_398.png)

This this whatever， right？

![](img/c990a1d1bc1607ec62b9419da49f4cdf_400.png)

来 see来 see。🎼O。Okay， so we survived a lot longer。And then we crashed。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_402.png)

Which is good， I suppose。Okay。So again， sound access assert c thats。So yeah。

 I should probably do an interlock exchange here。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_404.png)

Right。And not just this volatile thing， but the same idea， right。

 so when I get the original and the original， I'm going to assume it's the sound normal。So yes。

 it's the same thing we did before， but it's not the correct behavior split so this is the original。

This is the。Sound0ing。And interlocked。上次。Okay， this is the correct。

Insterlect exchange and we can do this more robust thing because we don't do this copying before just a ton operation one operation it's going to。

Make sure that it's normal there and change that to zero， so that's the actual in context change。

 right？So this is what we're going to do。We are going to same thing， ignore these guys。

And these guys and these guys， new value is going to be sound ready。The original has to be。

Sound normal。And SB sound reading。AtThis point。And something I'm going to assert that it's really。

But this shouldn't be problematic， to be honest。they're not going to change that to sound normal。

And the original has to be sound reading。And assert that。It's going to be sal。哦。Threading is hard。

 message ahead， but you are correct。So， it is hard。

 especially because these functions are a bit finicky。I mean， it shouldn't be like an easier call。

 I suppose， in terms of API， let me just go back to that kind of， but yeah。

 we're going to reill this before we try to run， assert that interlocked。

 let me just see interlocked。Is sound reading， yeah。And assert。

That we could probably loop through this to make sure that this should really not happen。This case。

 in the other case， we were doing an if because it can't fail。

 but in this case it shouldn't fail because this is the only thread that's changing it。香ry欧香。

But this is the yeah， this is the old one。This is the one。Okay。Normal。Okay， so what we are doing now。

It's the same thing that we wanted to do in the first place， but now we're doing the correct code。

I suppose。I entered lock。Which is when we play the sound。

 we're going to make sure that it's normal and we're going to set that to zero。

 so this is the correct code for doing this。Okay， they either like Com exchange。

 and if it's the old one。This is， this is wrong。They do not compare exchange。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_406.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_407.png)

Returns the。你有 value。I'm not mistaken。What？😮，Destk。耳机。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_409.png)

Is this。😊，How come it doesn't return to value， it doesn't make any sense and it needs four arguments。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_411.png)

Original value。Okay， so suppose that's a weird way of typing that it returns a original value。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_413.png)

So。This should actually be。你确是你毛。And this should be really。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_415.png)

It's your wrong MSM page。啊。Wow the have center。Yes， dude， how come they have。

 I'm not even them to ask。Okay， but it's the same thing， right。

 the same thing is going to return the original value of destination。

 so the original value has to be normal。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_417.png)

You know， for it to break。Thanks， man， dude， you are having me a lot。

 especially be the assembly thing。I am， I am going to have to learn。More because you really。

 you really helped me realize that it was being changed between those two lines that was that was key that was key man。

Yowki， thats awesome， really， okay。😊，Were on page， yeah exactly， ma'am。

 come on normal and this is the correct interlock I suppose。And again。

Then an assert that was really internal。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_419.png)

It know。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_421.png)

I don't know， so let's go back and just one more time review the code。Interlocked， okay。

So when we try to play the sound。We want to have a sound to zero。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_423.png)

Only if it's normal。And it's going to succeed， right？嗯。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_425.png)

You could probably play around with this a bit to see the results。Yeah， if it's not。This guy。

 which means that we failed， so we're going to try to set that again。Okay。

 so this is going to be our skin log and if it is normal。

 which means that we mentioned set that to zeroing。

 we're going to break and we're going to assert that it's zeroing okay。

 same thing when we are updating the game audio， we're going to make sure that it's normal。

 set that to reading。And if it's normal， which is the original value。

We said that's reading and dense， the last one we should be reading because no one can change if we are reading。

We going oh， we'll get oh， yeah so another problem。We set this to， yeah， we need the same thing。

We need to set that back， it's funny， I don't know what would happen。But when we finish， we probably。

 yeah， we're got to make sure that we are zero。And we're going to set that。To normal。Damn。

 girls outside want to play your game， fix the bugs， please。We are almost done。 We are almost done。

 man。We're almost done on sound。Will be resolved。I think this is fixed， and you know what？No。

 this is correct， so we changed a lot of stuff， but now we set that to normal。

 we set that to zero and then we zero that。Make sure we're still hearing that I think this is going to work I think this is going to work man girls outside and play the game。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_427.png)

Okay， so we crashed。At this point， sound was normal。Somebody changed inside here， dude。Dude。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_429.png)

Dude， let's just do something。Here am I'm not going to do anything。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_431.png)

And we still crash。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_433.png)

So our problem is the way we're losing the interlock exchange， so they can't， yeah， they can't yet。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_435.png)

But this is weird because we're not changing that another threat now that's for sure。

 and right here we're sure that it was zeroing。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_437.png)

Right， yeah。But right now it's not zero。It's not all because we zero that out， okay？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_439.png)

This way， they will define another developer。Okay。Okay， so this is wrong。I can't zero that。

So I'm going to make this a little bit more prone to error。

 but a little bit more robust and that's kind of a。But paradox。But that makes sense。

 so I'm changing the active。Because I can't zero the whole thing， I can't zero the axis。

Fox thinking we have to ship， we do and we are going to finish the today。

 I think we are we're very close to finishing this。We are active， we're not going to change the axis。

 we're going to change the sound。Inch is the position， the looping。The volume。The fading speed。

 the target volume。Oh the volume target volume the things from the pan， the speed multiplier。

And the source sex。Source x。The sinks free。See。Sound。And the next week。Okay， so this。

This has to be manually。那个。Every member。But。Access。ItMus be manually zeroed。颠对一下。Oh my god。

 please sound。Okay。我想。So we shouldn't just so we know， we did。Put a return here。

 but we shouldn't crash。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_441.png)

Mo shouldn't play out either。Okay， so we do crash again。It's not zerori， it's normal， oh。

 because we didn't change that code， dude， dude and super hushed。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_443.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_444.png)

Rushed， rushed， this suppose， okay， so we're not crashing。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_446.png)

Great， but we are infinite loop， though。 Oh， yeah， we are actually looping because we are running that。

😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_448.png)

100 million tanks。😡。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_450.png)

That's a huge number。Okay。So this code is now correct。😡，As far as we know。Which is not very far。

 to be honest of you。Now let's try to listen to some audio and this's funny because we should really hear a very weird audio。

In the beginning， because。We're going to spend a couple seconds playing that， never assume。

A third means assume I should change。The assert。To like assume， because I think it makes more sense。

 like assume this is correct。A certain means that， I suppose， so we are asserting。

That we're going to read。Only if we're normal， only if we're normal， we're not normal。

 I'm very not normal。Certainly and then I'm going to insert it Sweden here so we can't make a right。

 this is the more complicated thing， not complicated I mean。

Prone to error right this with the original problem， we were zeroing that during this two。

 so this is the correct thing。Okay， okay。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_452.png)

Compiling without error success， maybe you can ship and never actually play the game。

 So if we don't play and we don't see a crash， we can't say that we know that it was bo。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_454.png)

What do you guys think maybe can send that to team？Or maybe we can。Try to run the game。

What do you guys think？Your recall， I can really send that to steam， to be honest。

 the only problem I think is that you guys may be going to say oh， try it， okay， so' not to try it。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_456.png)

So I'm not going to send that to steam， I am going to try to see if the audio works， let's see。

You guys are going to hear some weird sounds and that's what we want for a couple seconds。

Then normal game。Oh， no。Oh no you crashed。啊，我的啊。Okay， okay， so。

The sound axis is normal and it's not normal。Good thing you have checked。Dude。Where do we assert。

 Because I'm going to have to go to the family。 You're going to have to help me out here， man， again。

 because。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_458.png)

Visual Studio， according to its debug info， and let me just make sure that we are outputting everything correctly。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_460.png)

Yeah we are。According to his debug information。Our interlock is ready。

 which means that we manage to change that correctly。 And we change that to normal。 So right here。

 everything's correct。 However， it said。That this line is not it's not correct。

 So it seems that the X is not on， but it says it is。 Now let's go to this assembly。 Let's see。

The actual problem。Okay， so that was a huge fan here， okay。I can try around that。Okay。

Let's go to disassembly。Okay， suppose that huge number will solving the problem。

Maybe that number is too huge。Okay， so。We call ct。U dude， you going to help。

 you are going to help me out here， man。Really， I mean。We call ct。Like。呃，This is。Fors plus 500 H。

 what does that mean？

![](img/c990a1d1bc1607ec62b9419da49f4cdf_462.png)

我s。L E A。LEA， let's see load effectiveive address， Okay， puts into the mesh， Okay， so。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_464.png)

Weload a couple stuff。And then we assert。It's funny， we are passing this lawsuit suit。

What's this dude， help me out， man。ADM 244 assembly is not my strong point， let's see。Our writersers。

 why are we ex boring， to be honest？Does assert X org see the value？That'd be weird。

 let's go to the red window， let's see。Thebu windows register。I see right， Str。Just move it here。

Okay， so we ask are in E where is that？E AX。Flas。Select all what。

It's checking if sound x is zero or not。It's calling a third。

Is this the test that if it's zero or not？Jump if it's equal to this， yes， this is correct， dude。

You are good at this。So yeah， test this guy。Yeah。😊，Can I see the value of these guys？Where are they。

 they're not。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_466.png)

Floating point。Shouldt shouldn't they be the CPU， thing？Oh， I think RAX， the same thing as。Test。

EAX and EAX。And jump。If this guy， which is our。Our value is equal to this guy， what is this guy？

Instead of memory we head， oh， is's near the address of the hard coded sound normal I suppose。

Which is zero， right， yeah？Rx is0。 sound X is 0。 but this what we're testing， man， are。

 we are asserting that it's 0。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_468.png)

And it says it's zero， see。This is exactly what we want。We want it to be zero。

And you just said that sound x is zero， RAX is zero。Everything is zero， to be honest。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_470.png)

Right。Yeah， movie， yeah， the test here jump is equal。Yeah。

 jump with this guys and apparently we didn't jump。Why didn't we jump？But to be honest？

If that's the problem with the assert。We may get away with this。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_472.png)

No， we don't get， oh， we have a ton of desserts。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_474.png)

Now this guy says that's not normal， but it does say that's normal。Well， you know what？

Let me just try removing the desserts。Unfortunately， the amount of beds， nots or bugs。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_476.png)

Dude， but I can't solve a bug like this。If Vi Studio tells me that it's a one value。

 we look at disassembly and it looks like it's the same value， it looks like it's zero， right？😡。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_478.png)

Maybe the assert is problematic because we didn't write a c。We could have could have done is right。

 you know what before。Before I try running with a search turn off。

I am going to try running with our search。So。O， so呃。Asert， so。Yeah， this library is a c。

I am not going to put this guy here。And。I'm not going to assert this library at all。S to be。Sir。Sign。

Un signign mismatch。 Oh my god。Okay， let's just come at all the asserts。That's really stupid。But。

These guys aren't here。As far as I know。De to your studio。

I see you broke inside of a third routine and not a place you've called it。

 change a third intuitive if statement break them exactly and that's what I'm going to do。

I'm going to see。Oh man， come on， changing these asserts broke everything。Okay， I can make。

 is this a sound in interaction？No， does this sound looked。And differs in life from playing sound。ok。

Because I was actually comparing the pointer。So啊。I can you rate pointer。How can I compare， Can I。

 can I just。And just cast the point to a size T on want to compare the pointer address。

Signed unsigned mismatch。Okay， so this is。Okay。Sign aside， so I don't know why。

 but our assert has problems with sign aside， but we're not even using that so we don't even matters just。

Oh， we probably did like this。Maybe that was the problem， yes， that was the problem。

 this assert was wrong， to be honest。Change a search intuitive statement and put a break on it I suppose you're saying。

In this audio thing and we are going to do this。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_480.png)

But that's just before， let's just see what happens if our search runs， okay， so we still fail。

So let's add a new statement。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_482.png)

50。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_484.png)

Let' see。Okay。Oh， actually， if it's not long， right。

 so we assert it it's normal so we should break if it's not long。C。😊，I don't know。

Quite is better than I said， well， it's supposed to give more information， right？But。

I really don't know， man。We should probably write a book about this， right？Because。If sound X X。

 oh it's not so weird。This is so weird。This is broad man。Seed says it's false。So normal。

This guy's so normal。If it's equal to some。Let's check assembly， Okay， okay， man， let's go， let's go。

 let's go。Okay so this is the if。Right。We moved this guy some normal。To AX ErX plus5， so yeah。

 this is sound。I'm learning， right， this is sound。Move on this restaurant and this we're adding four。

 which is the outside of axis。 So this is a value that we want。 Oh， it says it's one。Yue。Oh。

 but both of them are one。And jump if equal。Okay， what， yeah？Yeah， what indeed， man， I have no。

 no clue how this is so weird， I have no clue how above this。I mean。

 the watch window is certainly problematic。And this guy。

 this guy is crack like test its equal to one。啊。Right。Why， why both of them are one。

 I'm not sure because some are is supposed to be zero。

 even the literal thing because this guy's a literal。 So if I put the mouse over here。

 this guy it says zero。But apparently I'm testing， I'm testing one and one。

hich should be true anyway。So why it jump equal that， yeah， jump if it's equal， yeah。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_486.png)

If it's not equal my manager， okay this is correct。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_488.png)

Apparently it wasn't equal， so one and one wasn't equal。 I was expecting to be zero， zero。😡。

It is one， but it goes inside of this， it is one， but it goes inside of its iftick。

So I suppose this is correct， one and one， okay。But what's not correct is the jump eagle， right？

If you're testing one in one。Yeah， and this goes to leave， right， and it jump gets' equal。

 it's equal。We should jump。If you go to like the red， can I see， can I see the。EAX。This guy EX。

 it's RAX 1。And。You know what' it's testing the same register， it's testing like EX and EX。

That's why both them are one。Yeah， it's one here。呃。Jump if equal would be taken if E is zero， okay。

Okay。So jump equal checks zero flag。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_490.png)

So going I am going to make that a note because I am going to study more assembly so this is an important thing to know thanks man。

 so jump with who will be taken if EX is zero so it's not zero so eventually this test failed， right？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_492.png)

The test。It's funny because it didn't fail the first time， right？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_494.png)

If I put it like a break point， in both these places。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_496.png)

Yeah， we're going to hit this a lot before we hit this guy。

 so it's hard to know whether or not'm going to hit this guy beforehand。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_498.png)

But you know what I'm going to test。I am going to turn assertions off。Okay。

 I'm going to turn assertions off。And and this if as well， right， you this if。

Assembmbling andancy lessons at the same time。So visualual Studio tells you garbage。But come on， man。

 this doesn't make sense either。Because if interlock exchange， in lack of exchange returned。

The reading， which he did because this assert was succeeded， if this is the case。

 it should be normal， it should set it this guy， it doesn't make any sense whatsoever， man。

to have returned reading， which is the original one and not be normal。So。I really don't know。I think。

Certain。But this is good because like we certain the very last thing。

And I'm going to turn assertions off。And I think this is going to work。To be honest。

Because it has to be normal。It looks like something's changing the value between instructions。

 but this instruction you can't change。This instruction is。Oh。

 you're seeing between this and this instruction。Okay， yeah， okay， I see what from me。Okay。

This instruction is atomic， that's why we're using it for multi threading。

 this instruction makes sure is that we first test if it's reading。

Change that to normal in one instruction。So we can't change。

 we can do stuff between in a lot compact exchange， this is one thing when a test it's normal。

 if it's reading pardon me fantastic test if it's reading normal this is search just make sure that this is correct。

 but I suppose we can't。Make sure this's correct because it may change from this to this instruction。

And I suppose they were correct in this sense。So it may be changing between this and this。

 which doesn' is not a problem for us because this was the problem if you look at the old code from earlier today when we started the stream。

😡，We were doing these stuff， these tests。With several instructions。

 and then it could be done between instructions。And this could also be done between instructions。

 but we don't really care about this， this is just for our own sanity check， whatever。And you know。

 to be honest， this is probably also going to be problematic because。If this guy is bin luckying。

This guy。😊，This has been locking the atomic exchange， so as soon as this atomic exchange is done。

This one's going to be executed。 So it's going to change like this， Okay。

 so I suppose they're correct。 I suppose we can't。Assert this。

But we are going to have correct behavior。 That's what I hope。I'm going to turn assertions off。

But if it works， I'm going to remove these asserts because we can assert that because instructions can happen。

We're going to just have to trust in a lock exchange， which I suppose we have to write， come on。

We have to choose that at least those asserts are useless exactly it's useless in terms of like。

The correctness of the code because this should do this， right？

But this just make sure that this is doing this， right， but I suppose， yeah， it is they are useless。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_500.png)

Let's see we are supposed to hear weird noises for a long time， then go back to the game， let's see。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_502.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_503.png)

Okay， I think。I think it was a huge victory。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_505.png)

Again， again， weird noises for a long time。And here we finished， which is that explosion。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_507.png)

🎼And then we get on sound like a pro dude， that was really hard man to debug。

 I think that was the hardest thing I ever debug， to be honest。You know， memory hard to debug。

 which was the second heart of this thing I ever debug， which is like a realalc memory problem。

This might actually be the first， and I would not have done this important for you guys。

 to be honest。Especially you at ADM 244， thanks a lot， man。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_509.png)

I am going to learn more assembly。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_511.png)

And this was a typical motorth bug。And because you can't assume。

Even these asserts in a motor threatitis scenario。Right。So what you're going to do， this assert。

 we can' assume。But these guys， we can't。So we can't remove a lot of these。

Those are a lot repetitive。Yeah， this guy。This guy I'm pretty sure we can' assume because this would actually block that execution and this would release it so when released we can't check because someone else might be blocking same thing here。

 but I'm not sure this would happen， but this can't be done This can be done。

This search can be done because that would block the other exhibition。

I just joined and all you noticed see sharps of this lookingrk magic to me， yeah。

 you joined on the most crazy part of it because we are about to ship the game。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_513.png)

You know， this is the game that we are making。 It's already on steam， but。

We are polishing it for the release。Yeah， this is the game on this team page。Yeah。

 that was pretty cool， a pretty cool title idea， I programmed that title like we did like the blocks folding。

 I programmed that for trailer it was pretty fun。So yesterday was correct after for all， what is it？

😊，I mean， yeah， I suppose on that thread， it was， I don't know， I don't know， it's hard because。

What I expected to see from Visual Studio was that it was a wrong。

Value right because the decision failed。😡，But then I was like， okay。

 how could that be wrong and the answer was because the change between instructions， right。

 but I don't know if Vi studio。Was't really leave。If you're still correct， don't delete it。Oh man。

 I'm not going to delete it， okay， but I'm not going to say that it was correct also。Okay。

 so this the game， we are pretty close to shipping， it's going to release really soon I'm kid。

 it's going to be next week probably。😊，So today was a bug fixixie and Poing day。Yeah， we we can。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_515.png)

We can remove， we can remove the crazy test now， the huge number， let's remove that huge number test。

Huge number。You can move that and in the audio system we can now improve this because we're normally only playing 28 sounds and 26 of them are like permanent so you can make that I don't know。

 48 sounds， whatever。At the same time。Does learning。 that was awesome man。

 That was an awesome learning experience。 No， this trip was great。😊。

Because a polishing game is really hard and that's why a maiden me Maer was like， oh。

 I think this magic stuff because。Most of that is hard enough。

But when you're doing motor threadreading for the polish pass。

 which means that you don't care how it works as long as it works。

 you're doing all sorts of crazy stuff。Right， we didn't do。 Oh we started doing not。

 but now it's pretty robust。 I mean， the way we turn out through the auto system like this。

This is really cool I mean we always been luckying so it's not。😊，Probably not the。I'm not sure。

But yeah， the names are pretty bad。But but the idea is perfect， I mean。

 if you're supposed to if you are reading， we can't change it so we lock， if you're writing。

 we cant read it， we can't change it so we lock and in complex change was perfect in this case。Right。

Where are you from so proud？And know this this we can test this we can't be sure we could be sure。

 but we can in this case， it's not going to be changed but this。

Can't be sure because this is in our stack。Where are you from， I'm from Brazil？Bella Hte， Brazil。

Baldo design how do we stay it here？Pretty hot here。Very hot here。 Just replace sound with S And D。

 dude， I hate it。 I hate。 I hate it with like code so like。😊，S and D。S and D Z。SNDR SNDM。I mean。

 who's going to understand this doesn't make any sense， dude。And anyway。

 Autocompte does like have the job for you， we can just like tap sound。Tap， right。Yeah，明。

Cold clarity is really important and I really strive for that， let's just count the lens of code。

Break crowd。Cold。Because I think we are about them， to be honest。To be honest。

 we're going to have to check a little bit or maybe play tes a bit more。

Oh going I have to balance that。Do the software is so slow？So we wrote almost 10。

000 lines of code ourselves。And if you could the lines in comments， it's like。12，000 lines。

 and if you could the libraries that we used， oh no， this is wrong。This is the other way around。

 this are the libraries that we use， this Zar code。😊，So we managed to ride。54000 lines of code。And 5。

000 lines of code including blink comments， and that was in 70 hours。That was decent not 70 hours。

50 hours， I already forgot we saw how many about that。Okay， how do you auto complete In call。

 by the way， being using for a few weeks have not， Oh， just tab if you start。

 if you start typing something like playing in press tab。😊，It'll look for this the beginning stream。

Starting from where you are。All the way down to the buffer and then the other way around。 So if I。

 if I have like。If I have like playing this and do're like playing sound。

 this is going to be playing sound， but if I press tab again。

There's going to be this guy so I can just。Go through these guys that are appear in the file， right？

This is the other complete， but it's not 100% perfect I would wish there was when when when the beta releases for a four quarter。

 which should be by the end of this year， Im going to write a pretty big customization it already has like I have a ton of ideas of what I need。

In the customization layer just pull that up。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_517.png)

These are what I want and one of the things。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_519.png)

I know words where it's at， I mean。Basic thing is one of the thing I really like in like retail students stuff。

 but it makes it the way it implements pretty bad， but I like the idea is that when I do like set volume。

It's pretty volume It's pretty cool to know what the parameters are right it's pretty because we forget about that all the time However。

 the way they do it is like a toe tip a toe tip is terrible do don't ever put toe tips on the main thing that you're typing because they can obfuscate things they want to see right So the way I would implement that I will make something like up here。

Appear like the argument list， that's what I would do and I can do that for a code because it's pretty open。

 but I'm going to wait for the data because it's going to change a lot of stuff。The game looks fun。

 Why did you see over something like unity looks kind of hard I have done games in nuity。

 have done games in O Rio， have done games in gamemaker， Gooddo。

 I've done all sorts of games in those games in fact。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_521.png)

This game， this game， which is the pretty big game I released。

 I spent three and a half years making this game， this was in unreal。And and it's kind of a myth。

That engines make it easier to make games。I can tell you。

That engines making easier easier to start making games， I mean I at that time。

 certainly I wouldn't be able to do this game with no engines that's that's for sure。

 especially the way I did it， they're like a super limited team， right？However。

Three and a half years is a long time， and in three and a half years I would have learned programming for real。

And maybe I could have advanced enough to be able to do something like this， not like not this。

 but something like this， right？And there's another problem。This is a problem that we had today。

Today it was basically fixing the id problem， right？

Problemably like this happened in games all the time。

 especially for like three and a half years making this game like I was。You are going to have。

 you are going to find very weird problems like like the one had。

 this is normal for anybody this is normal， right？😡，The problem is， if you're using an engine。

You can't solve it like ADM helped me and you guide as well。

 right to go to the disassembly and see what exactly was the problem developing the red shirt index and C。

😡，I understand the problem if you are using an engine like unity， like I said， and this happens。

All you can do is search this same my game， please help。

 this is the only thing you can do you can't understand the problem for a real。😡。

And there's a lot of value in understanding the problem but why actually seeing these projects specifically because this project is a very small game。

And I could do that with no engines pretty easily and for a couple reasons。

 so we watched the very first stream on YouTube。Youtuube。com/daydan。

I talk about the goals for this product， I can say that in pretty much。

Success and pretty much all of them， right？Which were to learn a lot， which I did。

 and I think you guys did as well， right， which was great。 Have fun。😊，Whi we did。

 we also had some hard times fuing with visual students。

But it was a great project and see is a lot of fun and that's why I didn't chose like C++ because C++ is a mess。

 it's crazy。So C it's way way better than C++， so we did accomplish that as well。

 so yeah I've learned myself learned for you guys teach you guys right and learn so those are the goals and if I use something like unity。

I wouldn't learn programming， I would learn how to use unity。

And it's not fun to use an engine because of these problems I said。Like we were talking before。

You can pretty easily make a game。But shipping a game is really hard。

And unity in a real stuff helps you how make game， right So and to be honest。

 this game that I that I showed you guys that I released， I even developed that for the PS4。

 I have the whole process here on YouTube， right from the very first thing I've created like。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_523.png)

This the first time I created， this is unreal then I did like the character animation and the top down aiming。

 right？So at this point， I was like， I don't know， three months in the project by myself。

 this is what I'd be able to do。😡。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_525.png)

I would not have able to do this in three months， especially at that time。

 but today I can do that in three months like 3D with cash transformation stuff with no ranges right。

 but unreal real helped me get to this point this is the game I had the game three months into development however。

 the game took three and a half years to release。So really see the problem there。

That they help us get to this point， not the other point， the other point， the same thing。

 whether you're using an engine or not。To release the game， the same thing as this point， right？

And the other point in the other part， the three and a half years that this well let's say three years in two months right that I spent to release the game to make content and polish and things like that and you can see the whole thing here on YouTube。

This is really hard and engine doesn't help and in fact， engine makes it worse。Like I said。

 how we were supposed to debug this problem， of course we wouldn't have this problem in the nation right。

 but we would have similar problems a problem I had in this game， for instance， in the PS4。

 I was running out of memory using Ne mod。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_527.png)

How would I， first of all， know the problem and debug the problem and improve the problem？

What I did was like in the F model firms， like， oh my God， please help me。

 please help me have no idea what's going on Here the files the news what's going on and， you know。

 wait for updates。 It happens a lot。 Like wait for someone to fix someone who doesn't even know my game to fix my game。

 right。😊，This is not fun and this is not' is not a very learning process。

 so this why for this game I chose this。That's a pretty long explanation， I think you've got it。

 right？Okay。About assembly， can I paste the link to thetail absolutely man。

 I would love to see a link like this。I， I do know the intel026 Sky， but do you mean that。

The huge man。 Yeah， Okay， so let's see the link。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_529.png)

That。呃ADM。Okay， so yeah， this is the full manual。This is the actual manual that we should be able to know at least partially right。

 at least at least no better than I did， if you know it as well as you did。

 which was pretty well because you managed to you know see exactly how the jumps worked and the assertions we change that today if that was perfect。

呃。Yeah， but do you suggest， how do you suggest I read this。

 just start from like page one and read until I get bored to death？

Or is there like a more interesting like， yeah， brief history？Yeah， but it's pretty small， though。

 yeah。Baase execution of， okay， and maybe I should start at the beginning。Data types。Content。

I'm not sure。How do you recommend that I study this？I don't know。呃。

You have just denied the encapsulation principle of OOP。You are correct， I did。呃。

If your code is an open source， you have to make an obcation anyway。And I'll， oh。

 this is why I said the O thing。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_531.png)

で。Yeah， dude this like super， super open andvi we see the license for the game。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_533.png)

Let me you open the HIO， you can already download this， I'm going as soon as I'm done。

 I'm going to push that on HIO。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_535.png)

And the license is， do whatever you want with it，This is this is like。

Public domain and do whatever you want， like you can choose whichever license you prefer， right？

And so it is open， so it's pretty open source us in this sense， right？

I love the content things a lot。😊，That's awesome， man。 thanks。

 I really hope that more people are watching that as well， because。😊。

It has some pretty cool stuff to do overhead and planning。

This reminds me when my older brother told me， why make your own ranging when your audit are available。

 who help you make your own problems at the time I didn't say that best should have me。YeahExactly。

 ma'am。Exactly， it's awesome to solve your problems。

It's great what's not awesome is to solve other people's problems。

 especially since you don't have enough information and the problems that they have。

 it's way more complex the problem that you have because this problem was super simple。 I mean。

 once we learned that it was simple like people instruction like changing between instructions like because of motorread。

 okay。😊，But when you're talking about big problems that you can't really solve because you don't。

I mean， you're not going to debug on realan rights like 170 million lines of code， right so we wrote。

Like 4000 right for this game。 So that's why I don't use anity or for a game like this， right。

 because come on like bringing up Booka to kill a cockroach that that wasn't the same is， right。

About the display factor， you could just output them in place right after they appropriate yeah。

 this is also pretty。😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_537.png)

Pretty useful， but it's not 100% though， however， because imagine like I'm calling this function。

 like let's see an example。I'm calling like set volume， but I want to add another parameter here。

Like where would I add here？Because I'm like in the middle of either， I don't show this case。

Or I well。Or I kind of a， yeah。Either I offset this whole text or are putting it on top of this text。

 which is the problem on the toe tip。Or I can just like do as if I was typing。The suggestion。

 I could do this。U but I suppose that the most elegant solution is really to do this on a corner somewhere because it will work。

 on any case， not just the new function。I mean， maybe if you are changing a。

 maybe you already know the parameters so maybe you can ignore that case。

And only have the toe tip if you are doing no functions， I don't know。

 but I'm going to have to test that it may be a burden to like keep looking like this and like this a lot。

一屎。I just use it as a reference。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_539.png)

Yeah， okay， but I think I need a little bit more， I think I need like a more in depth introduction introduction to the statement because I do know the very。

 very， very， very basic。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_541.png)

But it's not like， okay， I need to know， yeah， we such about that Al， what instruction was that？

Kin of searched。yeah， good search about this instruction。Whatever。

It's going to be kind of hard search as post， memory operations， whatever。

But that's not really what I think I need， I think I need a more introduction。

 like strong introduction to assembly。I do know that they're basic though。

Do more projects about different stuff， in my opinion。Yeah， but this is what I intend to do。

But I know， it's just like the other friend told us in the stream before。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_543.png)

I really like big projects， man。I really want to tackle a project this big game。Like this big。

 this big， I reallyt want to do it， but I can't take my free time， right， So while I can't。

 I want to prepare myself in terms of knowledge to be able to tackle this project， so。

I want to incrementally do more complex things。And I understand that this doesn't make for very much interesting content。

Unless I can do like very contained things， that's what I'm trying to do。

 I'm going to try to build a more complicated thing over with a more contained kind of structure。

Yeah。But you'll see， I have a pretty cool idea， though。

 let's see show all parameters but highlight the parameters at the current position。Yeah。

 but where am I going to show up memories up here， then that's the idea。

 show upper memories here and then do like the bold thing。That's the like thing it's pretty cool。

 but I don't want to do it like in the middle of the text， though。I can just invert the colors。

 white backgrounds。On my font。Yes。Yeah， it'd bit fun though。

 when I get to right that customization layer， I could probably make that stream that could be cool。

 I do have to learn though because I have no idea how to do the customation far quarter。呃。

Don't highlight existing for coder。But highlights show opera renders behind。 Yeah， they do。

 they do now， they do now in the new renderry， but I'm not using this is old4coer。

 This is like for coder。0。28， I think it's like in 30 or 31， I'm not sure。

Because it changed some of the shortcuts， and I suppose that if I don't have the customization layer to change。

It's not worth changing。But I was about to， to do the because initially。

 when he released the video talking about the data launch， I was like， okay， I'm gonna wait for that。

 So yeah， but they now now in the new render system， they do。😊，They'll be clean okay。

 unless you change the time you think for the colors I just probably I never even heard for a codeer since 15 minutes ago。

 yeah， parkcode is pretty cool man， for a runner for a coldder。Forcode is great。

 It's this version is free that you can't customize。 It's really fascinating has。

 all cool features like if I type like I don't know， like if something like an open this thing。😊。

Kind of indent the whole thing automatically， pretty cool。I was bad as a man was learning。

 but for beginners， it's hard to take comp， okay， so thanks， yeah。

 so I'm going to keep this in mind for like reference。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_545.png)

But I am going to search for my introduction。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_547.png)

Material and stuff， I don't know the very basis， though I don't know， does a per。Vawson teaches that。

In bitwise。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_549.png)

I learned a lot a bit twice， though， although。Although he doesn't explain too much。

 his code does explain a lot so assembly。Dynaically， yeah， I'm not sure this is it though。

How to program a family language。Dude， this is it， this is what I need。

I know Per has something like this disclaimer。One be one out for the optimizing this is perfect。

 I'm going to link for everyone who wants to go a little bit more in depth in what we learned today on stream。

I think this is going to be perfect， to be honest。Yeah， awesome， awesome， nice find。I'm going to。

 and I'm going to know。This as well。To do later on。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_551.png)

Okay， let's。You know what， I think we center text add this and maybe we're going to call that。A game。

 not a day a game we're going to call that， but what idea what happened to per handss appeared I don't know。

 man。I don't know。 I kind of wished， I mean。HeHe did take a big project， right， like like Casey。

 but and it's really hard to go， I mean， this project， I've been doing this for like 23 live streams。

It's really hard men to keep motivated and to go back really hard。

Sometimes you want to program offstream， but you can't。

 a per does program offstream because helps that helps a little bit right。

 but the people can follow along， the people are not going to be that motivated to watch。

I don't know， it's kind of hard。I kind't understand that it doesn't I didn't have the motivation。

 but I would love to see more from him because that series was awesome I programmed a programming language after I watched the beginning of his series。

That was awesome。Thank God he did that and also has an introduction to assembly like a three part。

 let's see how long it is。 Yeah， like one and a half hours each。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_553.png)

So he's going to be a great introduction to assembly two hours。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_555.png)

It's going to be cool， I think。Hopefully。Okay， so let's just play for a bit and let's see if actually。

 let's just make sure。There we are， let's see， on the development， let's go to the optimized build。

 Let's play for a bit。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_557.png)

So cool now。Yes， finally， man，'s so good to be able to play the game。You know， in the other game。

 can you guys hear me pretty well or is it too loud？Just turn the volume a little bit down。You know。

 one of the greatest things to finish a game， it's okay， yeah。

Is to be able to play it in the end of development because in the end motivation really is problematic because you've done that for a long time。

 you can't even see the end， but it's close but there's so many problems。

 there's so many bugs so many things that could be better you could spend like so much time with there's like sometimes you think。

Oh man this suck I shouldn't stop doing right now and do something else。

 but then you stop and think okay this is awesome I should really spend like ears in this because this is so great it's getting really weird the way projects work big projects like this work Oh not like this。

But project this size also has the lead with least。

 but I'm talking about my three and a half year year project that was pretty evident back then。

 right？And the best thing you can do at this point is just sit down and play the game for a bit。

 I used to do this when I was pouring the game to the PS4。

It was and I was alone in the project in my home because at some point we did have like a smallest space。

You know， I had a cousin who had like a vacant。Room in his office。

 so we were able to don know for like two years。Uh beinging his a stuff。

 that was awesome and there were like no motivation problems from that part because everyone was there and everyone was like motivating one another。

But then when we run out of money。I kind of I was looking at the cool I was Mr。

 B and then when we run out of money， I kind of had to come back home。

And I was alone again into the project。And then I had huge motivationous problems， man， huge ones。

And what I would do to kind of a。And I had like a list of 200 bugs。That had to solve。Right。

That's off fun。And I was like， oh man， this is going to take so long stuff。

So I would do to get motivation back。Was just to play the game for a bit。

Right and I I was going to be reminded of how awesome it is， I mean。

 I was also going to be reminded of how buggy was。And I shipped that with some pretty bad bugs。

 unfortunately， but I couldn't prove that I did the best I could adapt and I didn't even know how put it for real that's another problem man the other guy that asked about unity and stuff。

It makes so easy to start making the game and I started making the game。

 I was program like visual programming against them， and I had no idea what I was doing right。

So by the end， I was almost under with the game。I didn't have like a solid understanding。

 I solid foundation， so it was really weird。Unfortunately， this seemss about coding or art。

Or so whenever never will be viewed as gameplay streams， but you learn you do a very important thing。

 especially for people who really want to learn， so thanks， do that's awesome。

Very kind of words man also for it， but I am getting a lot of you like 22。

I think I got like 22 like once before to be honest so people are't because the game is getting done right so it's awesome to see some visual stuff it's almost like a gameplay stream nows not oh my God it got slow okay。

Oh my god， that's good。Okay， but that was pretty hard， I got this low oh and then the mouse was back。

Maybe you can try to fix that。🎼I try to fix that， but I don't know if that will happen on full screen。

 the problem is when I move the mouse really fast and I get off the screen in know one frame。😊。

Don't forget to set the title bar icon， I will man， but the way I do this is with resource hacker。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_559.png)

So I had to load up the executable here and then load up the image here。

 and I only do this before I if I'm not mistaken the last one in the HIO was set。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_561.png)

To be honest， and on steam it' already set， so if I go to the steam page of the game。Well。

 it's not public yet， but I do have a build here， just fine steam here for a second。team。

Sam maps common， break our games out。Okay， so it's not， I didn't actually put the title here， yeah。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_563.png)

But what does it say in terms of text breakouts， I'm going to change that。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_565.png)

Yeah， the icon going to change later on but。I' change this to break。Arcade games out。Awesome。呃。

So audio， I think is perfect。 Let's add oh which also， oh， let's do the mouse thing。 So mouse。😊。

You get the mouse not to disappear after making the fast movement， so let's do this pretty quickly。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_567.png)

Okay， so the idea is when I do a really fast movement， I go off the screen。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_569.png)

And then the mouse appears， let's see if it happens when I go full screen。

It may not it may not happen if it doesn't happen， maybe I don't care about this。 Let's see。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_571.png)

So I'm not sure how would I solve this， to be honest。Yeah， when I do a really fast movement。

 the mouse doesn't appear on full screen mode， so since most players will be playing full screen。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_573.png)

I don't think we hear。The official influence kind of games is Atonoid， which is pretty fun。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_575.png)

Yeah， you mentioned that before， but to be honest， I hadn't heard about this arc annoyed。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_577.png)

Are it with a key？Okay， instead of breakout， yeah， breakout was the， okay， I know what you mean。

 yeah， breakout was the game。And I can the kind of game， right？You are correct。

You can appear to have two monitors though。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_579.png)

U， you are correct。That sucks pretty hard。I'm not sure how would I do this because the set cursor。

Let's see why we were saying this。When we resize the window。

 I set the cursor position and then if we're supposed to hide， I set the crsor to zero。

If we're supposed to hire when we activate the app at's zero。Then set the cursor。If we're not active。

Yeah， if you're not active， we're going to set the cursor bank， is this a problem？

I don't think we get that message if we run out of here。状介。I don't think that was the problem。

To be honest。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_581.png)

🎼Yes art come。 So yeah， okay， yeah， but I managed to find it。 Yeah， I know what you mean is the。

 yeah， so that's not the problem。 So it's the， it's the kind of gameplay game。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_583.png)

Yeah I like rogue， rightgue rogue was the game like breakout， but Dunngeon crawling， I suppose。

 I don't know， it's more than that Dunngeon Cred。Yeah， it's kind of hard these categories。

 so set cursor again if we're supposed to hide。😊，We said the cursor， this is in development mode。

 right？If you press that for one， yeah， this is the pause thing。Mouse input except cursor po。呃。

Let's try to do something， I'm not sure this is going to have an impact on performance。

Let's try to do like set， let's try to do this every frame。I'Not sure this is the best call。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_585.png)

Oh， that's the best thing if you're supposed to。 Yeah， I'm not sure， that's see。So。Yeah。

 this fixed it， so I managed to see that asking screen for one frame。But then I am back on screen。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_587.png)

So， but you know what I think？I think that wasn't a very good call because I think it pretty slowly than I was。

 so I'm going to turn on the profiler。And I'm going to stop sleeping。And let's see。Android number。

That。记啊。Yeah， who has a prototype withdrawal number？I don't know。Let's look for drone number。

Oh my God， so many draw numbers。Let's see someone has a prototype。Of this guy。

That has different app this guy profile it has different parameters。し。Okay， two a few argumentsna。

 oh my God。Oh， themic Oh， awesome。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_589.png)

Thanks， Pas me。It was like pretty good call。Okay， so this is the profiler。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_591.png)

You take a print screen with this， this is calling every frame。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_593.png)

And now let's make one that we're not calling every frame we could probably probably have a profiling just on that particular。

Call。嗯。一？But I don't know things's going to be that bad， though， I see。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_595.png)

Yeah， I don't think it changed at all。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_597.png)

一次一次。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_599.png)

I don't know if you guys can see， okay， you guys can。Okay， so we were about the same thing。

This is like with。Se pass。So the game was a bit longer， where are we supposed to measure that。

 let me just see？This should be， This should probably be。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_601.png)

In the input。 So let's see the input。Yeah。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_603.png)

It's like 0。01 milliseconds， so we're going to keep that everything。

 but now we have to make sure that if we all tab。We canWhen you move the bar very fast。

 it sounds like it sounds of a dove。Yeah， the idea would be to make like a a。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_605.png)

I didn't get 10 working， I like that in other the game better。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_607.png)

This game， see this game， I had the same thing because that was digital audio because it used the W and S。

 So it was a very smooth acceleration。 but in the mouse it's really chaotic。

 So the sign doesn't get a perfect wave， like perfect movement。

 So we have to like put a lot of delay。 It had a ton of problems with this， but。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_609.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_610.png)

But I think it ended up pretty cool it。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_612.png)

yeah， I think I'm going to keep that， but I just have to make sure。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_614.png)

I'll begin game here just going to make sure that if I all tap， I see the mouse， I do。

 if I all tap back， I don't。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_616.png)

So this is pretty cool， I think， I think we solved the problem 100%。Get the mouse to appear。

 let's add a V option to the con file。So instead of doing this in order like if。你啊。

I think I'm gonna add， like。Like limit frame rate or unlimitedlim。

 I'm not sure let's see how our configure。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_618.png)

Fig file loops。As of now。Like this。Let's do like locked。FB。Locketh guess。It goes false。

I think that's correct dude It's so so cool to have done this。😊，This kind of conflictg file。

 parsing and stuff。 That was pretty cool。 That was my stream。 So if we lock。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_620.png)

FPS。可能是一。Isn't there a solid way to prevent mouse from changing position when a game window is active？

To prevent mouse from changing position one again， Windows is active。We are doing this。

But we're doing this what of frame。Once a frame， we change that back if I。Hight mouth。 Let's see。

Securency。Well， high pressure。We said that to zero， I think we're not going to have。Yes。😊，嗯，好似。Yeah。

 let's see。 if you see what's going on， see its， it's pretty light。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_622.png)

But for one framework， I suppose we could add that to the mouse movement message。

And not the way we' were doing。That may be more robust。But the idea is the same。

 the idea is every so often often for as long as frequently as we can I suppose。

🎼I'm going to set that to the center again， see。I'm going to save the dip。But。

The user can really get off the window if he chooses right so I don't know if there's anything we can do。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_624.png)

As far as I know， I can't ask Windows not change them mouse at all， I do have to do that myself。😡。

Because I always have this problem in games when I'm moving off quickly and I。

 I click something else out the game window， yeah。But。

I suppose this is Windows not having a very solid way for games to control 100% of the desktop okay so I'm going to blame that on Windows and as far as I know this is the best solution we can do and I did talk to people on a handway network about this。

And they said that this solution is pretty common to just set that back to the center by hand and click that。

So in in。In the of our game， in order to do this， I suppose you have to move and click the same frame。

😡，Let me see if I can try to create that， let's make a very small window。

And let's try to just like picking。You have that off the screen。So we have a very small window。

 which is kind of cute。And if I， yes， see， I can't at all， oh， I can't。No， I can't。

I can't yeah because I just moved the way to the side。So yeah。Yeah， so that was pretty bad。

 but oh my God。そ。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_626.png)

So exactly， it's not 100% robust if you are on a window boat。

 I suppose you have two monitors right that's why you're asking。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_628.png)

I'm going to have to test this on on two monitors， but in this game you have to move and click the same frame。

 but it's kind of， I thought you could clip a mouse totangle though。You probably can。

 but if you clip and that was the problem we had originally， if you clip。

You're not really have the diff see you're going to have like this behavior like his moving and then he can't move anymore that's not what we want I mean。

I mean， I suppose you could clip， I suppose you were correct。Yeah。😊，Even note this like。Could。

Cllip correct。And yet that is every frame。So the problem with clicking is that you're going to limit the movements。

 right this the problem。However， if you do this， every frame though。

And we're going to limit to half a screen per frame， or it's kind of okay， I suppose。

Unless it's super sensitive， in this case， this is not going to be very good。

So'm not entirelydy shirt。But no， I'm going to add just like。

I don't even have like a one to do thing I'm going to add this at the end。Yeah。

 it's kind of hard it should be ways easier man to do things like this but every game every game needs it to be like old school at a cheat activating press right left。

 right left A B， which gives you a fucking huge number of times。Oh。

Were probably going to make our remainder really low if you try to make up fucking a huge number of points display on screen。

So I think we have to do open GL Maining for that。いえ。😊，So let's finish adding in the V sync thing。

Do you have a conflict with your confi parser？Let's do a string lock FDS equals。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_630.png)

Is that lock or locked， lock， lock， FDS？

![](img/c990a1d1bc1607ec62b9419da49f4cdf_632.png)

One， two， three， four， five， six， seven， eight。8ight。Digits on this guy。And if we find。

And we probably add like。A make for this， but we're not going to have that many commands block FPS string。

Maybe you clip a mouse if it's hidden only。But that wouldn't change it， though， I mean。

 even if it's hidden。It's there， right， but user can't see it。

We have to get the diff and put it back， even if it's hidden。

That's what we were doing in every or like。The mouse moved， so get how much you moved。

 move it back and tell the game how much you moved。If we limit that movement。

We can only see this movement per frame， which， as I said， I don't think it's a big problem。But。Yeah。

Okay， and。We're going to set。The lock F D， S。To the parse value。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_634.png)

Now， let's see if this is working。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_636.png)

You know what？

![](img/c990a1d1bc1607ec62b9419da49f4cdf_638.png)

I'm going to have the default to true to be， oh， I want the default to be true。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_640.png)

Oh， I could do it like this。Yeah， think want to do this。And in the window， I'm going to do， yeah。

 whatever this a word， I can also do these guys。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_642.png)

If I don't find it from fix file。Let次。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_644.png)

So we are locked。If I come here， set this false。We're not locked so people can unlock the Fbs should they want to。

 which is a probably a good idea in this game， to be honest， because we're not using open GL and。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_646.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_647.png)

We may have like a little bit of a lag and stuff that was that was that's super easy。To add。

 we did a good job with our API stuff。Okay， when you start to clip it。

But then your game doesn't have any menu when a mouse is visible exactly， exactly man， but again。

 even if I had， I don't know if I wanted to do the Windows mouse anyway。

I think I want to have my own mouse because it can change like sensitivity pretty easily and stuff like we did。

 which we added like a mouse sensitivity variable here if I on Fig file。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_649.png)

And so if I had a menu with visible mouse， I probably have the Windows mouse invisible。

 have my mouse visible。That's probably what I would do。

And that's what King and Con deliver did I was playing that on the free weekend last weekend and there was a bug where the mouse appeared when I was tap back to the game。

 that was a lot of small bug in very small bugs， but there were。But because it's a huge game。

 that was pretty cool， though very well done， awesome to be such a small studio so。

But I could see the Windows mouse and their mouse， they were at a different position and different sensitivities and stuff。

Because I was also playing at the lower resolution。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_651.png)

So yeah， I would also just do what I was doing at this point， anyways。KDC， yeah， keen income deliver。

 yeah。That was was pretty pretty well done， you know。

 that's the thing and I really want to strive to start making more and more complex games。

hopefully not as complex as they by myself and stuff because it's like impossible。

But to be able to understand more， right？Good game for performance that's the thing and when you build a game this complex on top of a commercial engine。

And you don't have like the engine developers inside the team。😡，You are in a bad shape。

 it's impossible， like really impossible。Even on a big studio like EA。

 they use its own frostby engine。When the bior team like did the mass effect， the problematic one。呃。

Byware didn't have the agent for frostbite。So they didn't know the engine that well and they couldn't improve that and they couldn't fix the bugs。

 same thing in this case， they was crying and they did have engine developers improving the engine and fixing bug stuff。

 but since it's not the engine developers， they're real ones。It's going to be possible。

To make that robust and bug free and good performance and stuff。

 that's the difference between pubub G and Fortnite in terms of performance， right？

Pub G did use the same engine right as Fortnite， but the difference is Fortnite was built by the guys who knew the engine for real because they developed it。

So they can get a lot better performance， more robustness， overall improvements and stuff。

 so that's why I think making our own engines really really。

 they couldn't manage the original trilogy as well。Yeah， well。

 but I suppose this last one was words come on。It became like a huge meme， man。Yeah。Oh my God。

 I can't even imagine how chaotic was， you know， that's why we were talking about， you know。

 working for companies and stuff。Youag being a developers spending years of your life in this game and having like this crazy。

Ship time because you had to ship anyways。And it was actually no one， no particularly people's fault。

Except maybe I don't know the very early producers that organized the whole thing and decided some very high level stuff。

 but that was really hard because they didn't have enough information as well。

And they probably are the best people to make a call。

 so it was probably impossible to make a better job out of this。

But I don't know it's not a very comfortable position to be at working on a surgery like this。

Work you four years， years， man， four years， five years， whatever。

To at the very end have these problems， that's why's that's why I my game， I three and a half years。

 like I pushed that back along a lot。A lot， that's what I meant。To be able to ship down a good state。

 and it was like a very good state either it was just like a decent state， good state。

 good enough state， I suppose。They had to build their own sequence full on top of some yeah。

They had to build their own sequence stuff on top of X 61 for some reason， sequence you mean like。

Like cinemainetics stuff。Yeah， you know I really want to do like a project it's gonna be a pretty small one。

 not like yeah yeah， that's what I mean I really want to do like a cinematics tool later on it's not gonna be as complex as they use。

 but I watched the talk about the Wi 31 It's really awesome。

And the way like the tool talks to the run time that's a very nice game engine challenge to do I really want to do this this will be a nice stream series one day I suppose maybe do like 2D for now with text and events and camera and lighting first。

I would probably do an offline too for that and not inside the engine。

They put their own for dialogues and it's bug limited， yeah， exactly。

It's kind of hard because it's such an important part of the game。

Like Kingdom comes like more than half of the gameplay is that system like dialogue system cutsing system。

 so has to be really， really good， but it's really。

 really hard as well because they don't have enough time because there's a lot of content so you have to automate the lip sync and it looks bad so it's kind of it's really hard。

You know what？You turn the mouse for， I don't think I'm going to care about this。

Note this as an improvement to the platform layer。Like。😊，Windowsdow improvement。Nick。

 the fail more evident， I don't think I'm going to work on this man， I don't know。

 it's kind of hard it's kind of fiky and I think it'll be good enough for now。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_653.png)

We have a cool animation， so we learned on stream how to do awesome level transitions。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_655.png)

So we can't do this， it's not like we can't。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_657.png)

Just like there's a lot of work。And I think it would justify because I want to shift this game and started working on new things as well。

They should have just used existing one， but they probably needed a lot more， that's the thing。

That looks really。 Yeah， man， I loved adding that。 It was the first time I programmed without an engine。

 a level transition like this。 and that's another thing， I mean。😊，h。

 to program this exactly the way we want it' pretty easy， but in my game that I was a real phrase。

 I had to be stuck at unrealos like synced。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_659.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_660.png)

Level transition thing， like sometimes it has like a couple of hitches。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_662.png)

So you can't have a very smooth， me just close the door here， for， there's a weird noise。

So you't have like you can't have smooth transition between levels in people like level streaming and things like that。

 that's what we used in the end。But it's kind of finicky when we build an engine and we understand the transitions。

 it's pretty easy to like。😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_664.png)

Control that。That was pretty cool and we did a lot of stuff。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_666.png)

Let me see what day was it？呃。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_668.png)

It was one of the later days， later days。Tranition。Yeah， it's around here。I don't know where it is。

 but it's here。I don' know。Better menu， optimizing gameplay。

ReMs robustness animated la transition here it is， that's what 20。coolSo what's next Well。

 I think you've going to end the stream。And call that the finish game I'm not a Pix game I do want to do dude I want I have so many cool ideas Anne。

 but no this is what I'm going to do。I am going to。Because I'm going to tell you。

I'm going to tell you first just because there are a lot of people streaming watching and you help me a lot so we kind of deserve what I have in line so I think this game will be will be it so we go decide yeah this I think we have to play test a little bit more maybe。

😊，I know。Maybe for when like 10 minutes or so can play especially fasters， yeah， maybe oh。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_670.png)

I don't know if we managed， if we did that， I kind of had in my mind that I needed to do Tes to make thats easier。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_672.png)

I don't know if I got to do this or I didn't on stream or is it in a data。

So I'm not sure if I did or not， so I can probably take a look at that at this so but the idea is after this stream is done。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_674.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_675.png)

I had a lot of cool ideas， like with just like making these games， Donkey Kong。

 a supermarket game a froger that would be pretty cool a froger as a breakout or what is it？

That a a giveus said。Arkeoid， Yeah， so I'm going to make the， I'm gonna to make like a。

These game modes as well and make like an addd on for the game， whatever。

 it's also cool because everyone saw the whole thing being built on stream。

It'll be cool to be able to play with a little surprise， right， so that's also important。 I think。

 so I am going to。😊，After the stream is done， I'm going to start working on this on these maps。

 not all of them， then we're going to pick like five or so。You work a little bit。

With these suggestions， that's what I'm going to do afterwards。

 but that's going to be pretty quick right because the game's pretty much tenants gone just going to be like more levels。

Then I want to start building a game agent。Because I want to do more complicated games and there's a lot of stuff like this。

 this whole Windows platform thing。We don't need to do that every time for every game。

RightSo the way I did， this game rose from scratch because I wanted to show the whole thing on stream。

 but the way I do with my other game that don't write on stream。I just start copying things right。

 obviously from the things I already wrote， however， since they're not shorter to be copied。

It's not very easy to copy and sometimes you have to copy from different projects and this one's pretty old the other system but it's pretty new the render system all crazy so I want to formalize this into our game engine it's going to be a 2D game engine。

Very simple to use。And in order to make the game engine I have to make games right so I'm gonna make a super simple game first and then a pixelixar game and then a 2D game with more scratch animations then maybe with Scul animations that'll be pretty cool so I want to make a lot of games improve the complexity and hopefully the game engine will be able to grow in a good manner I have a lot of ideas about how to structure game engines in terms of libraries and frameworks and engines。

So I have a lot of cool plans I had， but I I do want to finish this first because I think this game deserves more levels。

 right but I don't want to do this on stream。Because it's hard for me to get like a four hour or a three hour and stuff spanm to a stream。

 so it's kind of it's kind of better just towards like 10 minutes。

 15 minutes whenever I can since just just for my free time stuff。

So I'm not gonna stream these guys I've probably gonna stream parts of the game engine。

 but I don't think I'm gonna to stream the whole thing because I do want to do a lot quicker and streaming does decrease productivity So I w I want to stream when I have like since thatmic。

Looccalization， for instance， I'm gonna do the localization system for the game。

 Then I can stream that because it's gonna be a self contained system， which is pretty cool。 However。

 I do want to keep you guys up to date on my YouTube channel with， with a。😊，With the progress。

 like the engine and stuff。So if you subscribe to my YouTube channel。

 you'll be able to see the progress of the engine all the way from nothing。

 which I'm going to start in a couple in the next few weeks when I finish the game。

 when I launch the na stuff。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_677.png)

All the way to hopefully a good engine and if it's good enough。

 maybe I can make it available for you guys as well if you guys want to use even if it's good to use。

 then this make it really fun to make the game， right？

So make it easier like this crash that we found have to make it easier to reproduce the crash。

That the whole thing to be have to be really easy to。To make the games， both terms like Ty。

 So I'm going to use like hand heroes。Dynamic codeloading idea for the engine we' going to see if the input have input recording。

And then if the game crashes maybe， I can go back to the previous input try to reproduce as a crash。

That'll be pretty cool man I'm really excited about this agent so that's the plan and then I can do like more complicated games and I'm going to do like simple games。

And I also have other ideas， I'm also doing like this tutorial series， how to do a simple game SL+。

Which is pretty cool， I think I may do a tutorial series where I do a game in OpenGL。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_679.png)

Because people really like this。 So I think I'm going to do a tutorial maybe I'm going to do like a。

Like Galag us kind of game。A shooter， I really like shooters。

Top down shoes stuff or yeah so I think I'm going to do on a tutorial as I do the game engine I'm going to have a small project which is the tutorial and a big one is the game engine then I'm going to do more complicated games with the game engine hopefully 3D hopefully 3D because like I said man I do want to do games as complex as this game again and even more complex I have so many cool ideas for games。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_681.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_682.png)

诶。No that I have to keep going okay， so let's do just a little more play testing just so we can say that the game isn't officially and next stream will be the release stream next week。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_684.png)

Because now they is， man， so let me just。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_686.png)

I'm going to make a full screen for you guys so can test the whole thing。

 so I'm going to remove the debug options， we're going to remove the profiling。

 remove the development。Then I make you guys full screen。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_688.png)

And and then see。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_690.png)

I don't think I'm going to play full screen though because I can't see the chat if I played full screen。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_692.png)

I do want to play Texas tomorrow yeah， so I don't think I'm going to play full screen。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_694.png)

Yeah， I'm not going to Facebook screen because I can't see you guys。So we're going to have to live。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_696.png)

With the development Mo line， which is like assertions and。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_698.png)

To screen。Okay。So let's play T because this was the harder。Of their levels。

Pret cool animation that we added。Through raw animation with a sound。🎼我面。

I maybe actually give up one that guy， okay， oh， I talking' think about like oh cram， strong blocks。

 oh man， strong blocks， his level sucks。Because they don't have much time。几远远。

I think it's pretty manage now， it's hard。But it's not like impossible。Yeah。

 so now that this because we now have rotating blocks， so they rotate from time to time。

 we could be set a rotation。🎼At that point， maybe we gonna， Maybe we're gonna do this。

 reset the rotation。Whenever we start that mode。Awesome， now this is the crazy part。Yeah this。

 I think I have to reduce the number of guys who spawned this， I already did though during。这始。Yeah。

 this likes it for crazy。You just worked fun。You can read see the stereo thing。I think that'll be it。

 man I I think it seems a good difficulty and I think it's possible。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_700.png)

Awesome。😊，Not rotation， I don't think I didn't want to add some smooth rotation， we could。

 our remainder supports it。呃。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_702.png)

See， we， we do have。Well。Yeah， we could could make that smooth rotation。

 but since Tetriris doesn't have a smooth rotation。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_704.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_705.png)

I didn't think it made sense for the relationship to bemo。It's not like it's not very tious。

 like so rotate。See， so this is the thing I rotate every two seconds， the blocks。呃。有DT。Rotate I。

 So all I have to do。You you see whenever I spawned， the rotated blocks。

 which is if have a specific shape index， dude this is super hard coded。

So let's see shape index doing this is such a baptism。Okay， so。Do we have like？Progress。

We added the progress later on， I don't think it's fully featured should would give be an Nland yeah exactly a preview for for an next rotation maybe。

嗯。Maybe we could add a sound though。I think I'm going to add a sound。They thatll be good enough。

Let's see rotate see。If it's weird than。Then 2。We're going to add a rotation。

I'm going to sound or play sound， let let's see。We have the play sound。Old sound。

 this is the sound of lot what an old sound。I'm going to add the oat sound。Because right now。

 it looks incomplete or something。Yeah。But I think if I reset the rotation in the beginning。

That'll be a bit。Is your Ms are going to add like a couple of sound cus like0。3。La theode sound。

Whenever we rotate。And also， like。Halfway there， so if rotate it' greater2 or than one。

I'm going to say like if。Tris。Play rock。Rotation。Sound。7 falses。True， and then do the same thing。

Maybe you can add animated rotation， but it's a very fast one。That's a good idea， oh， but oh。

I think we didn't actually rotate the blocks。I think。Yeah。😊，We didn't actually rotate the blocks。

 we moved them。That would be cool though， to do a really fast rotation。

 let's see how easy it's going to be。Let's do like。没 mean。所。Lotation sound。

Again I'm going to set this guy to false。Yeah， but let me do the two things and I'm going to do it。

 first of all， I'm going to reset as the rotate T。Whenever I start that sequence。

 so I'm not sure when that sequencer， I spawn two shapes， correct？And then I wrote date。Let's see。

 close the question to2。Don't have， let's say， equal to。I don't remember how we do this。Progress。

's let's see again， everybody is okay， I think that's yes。Sge shapes。Shaps spawned。

Okay so this is the first time around。Right。Yeah。Respond one shape， respond to two shapes。

If we destroyed oil blocks。And it's one two shapes。Post levels pawwnships plus plus。

This is what I kind of expected。Post level， sp shapes or plus equals to 2。 This is the one。

maybe an rejection， that's a very fat yeah。诶 see please。Because see。Because I don't think。

We didn't actually make a collision system。Except rotation， just our render。

So it has to be fasts enough that the player won't care。If he hits the ball， but I don't know。

Tes level state。Rotate seal so this is going to be a little more robust rotate。Yes。

Because we're not going to rotate immediately， you're going to wait probably set that to minus like five or something。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_707.png)

Does that going to take a while to start rotating？Thatそ。Yeah， so。

This is the sound that rotation will make？But I have to test whether or not I have rot blocks。

Maybe okay case， more partners we can do， we can do a lot of partners。Yeah。

 I think that'll be good at that。These two differences。Yeah， motor particles was a good call。

Let's see if we have to make the sound also only appear here。Thatack kids。🎼No crap。Yeah。

It takes a while then。Nice。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_709.png)

So yeah， kind of liked， could you explain the way you typed that before your strokes？Oh。Like this。

This is C。In C， it's kind of weird， you can't do like stroke flu， whatever。And then do like。

I can't do this。So you have to make that as。Specific type。With and see， you have to do this type de。

 the name， right？C plus suppose you can do this， but see you have to do this type that thing so I I don't do this guy because you don't have to because you're already down here。

 however， if I have to if I include like a pointer itself inside here。

I do have to like predelar the sort to like script。Throughw something like this。あ。Yes。Well， yeah。

But then I have to do it the so that's like a namet or something。Well， for some reason。

Old school program。 Yeah， this is pretty old school。 Yeah， but I could that before the stroke word。😊。

You meanstruct， oh attack thatstruct， okay？Tack death，struct fruit like this。Yeah， it could work。

 I mean。就可以。Do you that。佢 says。Identifier or okay， it expected to the semester。Ignore type F ignored。

嗯。Type death ignored left of food when no variable was declared。So you have to do it like this。Okay。

 so you have to do the yeah， tap that search。I I don't like typing food twice。Yeah。I mean。

 and also I kind of obfuscate the fact that it's a foo because the fact that I'm typed athlete is really not important at all。

 right？So。So if I kind of a。So if I make， I don't know， I don't know， it's kind of a style。

 I don't really care to be honest， it's kind of a style choice， but I don't have like a preference。

It could be either way， type de， type name。Type is stressful， okay。y， ok。

So I suppose that's more consistent， I suppose， right？We the rest。Is this SDL， No， man。

 this is no libraries。This is our rendering thing。We have a draw rack Oh， see。

 this is our trans rotate rack， so if you want to rotate recangle of this is what we should use。

It takes an an angle， then we do the matrix。Then we multiply the matrix， then we run for every pixel。

 and then we optimize this thing here it's running pretty well。No libraries， everything we did。

 we did live and we did from scratch。It's awesome。😊，呃。

But every since they tried to avoid  api my stroke， yeah。

 I'm probably going to move to C++ when I do the engine project， like I said。Because for instance。

 when I try to implement the C。Obviously the this team library on this the CM SDK。

 CM SDK C plus and it's very C plus plus like with scripts and with type depths and。

Templates and classes and all sorts of crazy s close stuff。So I couldn't。If I'm in there and see。

I could probably do some hack。 I did implement the beginning of it。

 but since I since I can't put the overlay because it's not a。

Hardware I rendered I didn't even bother to put the game that's why I didn't do anything on stream I just did a test and it failed so I didn't actually implement a team SDA。

Yeah， but that's why I'm going to do C++ for the engine to be more compatible because mostly pre+ is interested in all that stuff。

 but I'm going to be pretty much like see pretty much what I'm doing here。Okay。

 let's add some particles， O N B。And the audio thing。

 so let's go back to the level of what the equal is two。So with your progression three。

 we should be able to add a sound。So， play sound。So let's see old sound。So this will only happen。If。

Ttris， progression。Progression is three。Not progressive。Its three。Then we can do this。

Same thing here。If Te。Progression。Cose three， so there'll be enough of visual feedback。And then。

Whenever I rotate the guys block relative。Oh man， I don't even have a strong rotation， Jane。

So you know， it's kind of hey。GitHub呃。I don't have a GitHub for the project。

 but you can download the whole source code。Individualally， in my HIO page。

 I me link you to the HIO page。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_711.png)

Here。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_713.png)

You can click download now and then you'll be able to access each of the episodes。

 sourceRS code and executable。You are welcome to give me a tip if you want。

 where if you just want to download， you just click no thanks and you have to download which day you want to download。

 this is the link。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_715.png)

I think it's C99 since it except in place variable equations。 Yeah， it's C99。来週にしま新ななに。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_717.png)

Yeah， exactly。呃。Progression。I mean。Progression is not a number of Texasas， level progression。

Because the thing is C++ do have a couple cool things。I really like default arguments。

I think really helps。 I even prefer default arguments then overloaded procedures。

 I think default arguments make it really easy to not worry about。

I the calling combination because so I am going to use a couple features。

 but it's going to be pretty light。So， I'm gonna add like a。Like a。Tattra is like rotate。

Does this get called before or after this is the simulate level？啊。Let me see the calling order。

 I simulate the level。This is the game， a simulate level， and then a simulate black level， okay？

So this is okay， I can， I can set this。Ex rotation。Roated this frame。Rotate the frame。It goes true。

 and then when I set this to false every training。rotate。This frame。Okay， now。Whenever I simulate。

Thelog for level， if I'm Tetriris。Okay， if I rotate this frame。

Just level state that detectors over dig the string， I'm going to add a particle explosion。Particles。

 let's see how it expand particle。We have spwn particle explosion。So。The explosion takes account。

Let's do another5。Yeah， a P， The P will be the block P。The DP scale。

I don't even know these parameters， let's see a particle experiment。Yeah， I have me copy this。

And let's see how that will look， that look a lot more finished。

 though I think you can make it a bit bigger， though。For my understanding。

 Strs does not like the seaway of type casting and thus there are overloaded functions and they click if I record correctly。

Yeah。😊，I mean。My problem is not what they did is more like how they did it。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_719.png)

It's it's very important to have like a runtime type information system nowadays for meta programming。

But the way they did this really ugly， that's why I'm looking forward to J Ji， JAI。

 Jonathan Blow's language。Because。呃。Because I think will be a nice mixture of like。C and C+， I mean。

 it's a lot more complicated than C。So I'm kind of a little bit skeptical because I even like simple things。

But I think it'll be good。Enough to justify like the complex features。

He's a good designer so it's gonna yeah J Hy and man。

 he's a great designer so he's going to design a language's going to be a great language that that's the way I think about it that's why I am on。

The JAI Hy train。Oh， that was almost an awesome movie。Oh my god。い。I should probably have a cheap。

 I think I added a cheap code at some point。In the stream that I was programming。

Somebody have suggested to have the cheat code than I did。

I think I'm going to add that back or maybe at least search for that because I don't remember。🎼Cat。

给し。Okay， I'm not resetseing the particles， oh it's good to see that our a render can take that many particles。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_721.png)

So tan was too much a couple problems， right， tan was there's all particles of us。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_723.png)

NotNot distant， this stem was good enough， like more particles。And actually do like。

Set this guy to false。It's weird， I thought I was setting that every frame to fall。Oh。

 only if it's really into。 so this thing why far codeder， I really like it， I think it's。Easy to use。

Has awesome features like having。Like。😊，I don't worry about indentation at all and in effect if I ever have to type tab again or space。

 I'm going to be really pissed because this is a great programming like this。

 you don't have to worry about indentation about organization。

 this is the biggest feature also because it's super open and at some point I'm going to make an awesome customization layer。

It's pretty fast， reliable where we like it。I think it's due to not having to deal with the header fire。

 how end is the you to avoid them？Okay， I forgot if you're doing。If you're doing what you're doing。

 the chances are you're doing a job， so I'm decided I don't understand the hyp for modules。呃。Yeah。

 do header files。Are one of the worst things ever to program because you know thats small。

remember that we had to do like for the profiler， we had to add the far decor have to change this four declaration that was inside the ifdF。

If prefer father。Imagine this for every function right Do this is so terrible。

 Why would you want a program like this， So I avoid them at all costs by by not by having a unit to build and how this different from themm。

 I haven't used Vm so I can't say exactly how is it different， but it's more like Iax。

 So it's based on Imax。So。It's more like a lot for code is a model text editor。

 it's not a sort also virtual spa exactly man， virtual white spacing is a new feature。

Virtized space is awesome， so that's why I really like it。😊。

So it's so intuitive because I can really， I can just move with the arrow key， whatever。

And type for the normal key。 so this is great， I think， for like easy to use the ability， whatever。

 better word。😊，And it's also super opened in C， so I am going to add a lot of more features and stuff。

 it's going to be super fast。I'm really excited， so I really like it because of these features。 Yeah。

 I don't I' I wouldn't be comfortable with waterworth。

 even though it may be faster and better for the things and stuff， I not sure。😊，Okay。

 so this was fixed， I suppose， I think that was the O N10， yeah。I was like minus1 that I added。

It was like rotation T， rotate T。us。5， I think you can just make that zero， to be honest。

Do you mean ISO standard and working compilers？I like the set， right with control A。

 what is the position you want， which you want。Control a。Yeah， I do this with control。Yeah。

 I think you're referring to this way of like。Of like setting the marker， whatever。

And then operating on that。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_725.png)

🎼I do that with control space and I also like that a lot I really got to use that's theX way I suppose right yeah I I used the next for a very short period of time。

But if that's the index way， I really liked。That way it took a bit of time to get used to it。But。

That was worth it yeah。Oh man， I really want to close the stream in a bit。Getting kind of laid here。

But。But I also want to get this 100% because this will be the last coding stream that's for realo。

 the last stream the next stream will be releasing stream。

Maybe you can do like a day one patch or something if we need， just keep it。Hopefully it'll be 100%。

One use smart codeder， Yeah， I mean。As long as theella keeps doing a great job。

And it doesn't get like demotivated for not having a lot of people use it。

 but I think it's a gradual process， I mean， it's kind of hard。Just sell tools for a friend。

Programs and stuff， especially。Like non mainstream and like。Visual code， like visual Studio code。

 really。Like， you know， yeah， that's awesome。はい。How weird does that look？Dude。

I that really bad or just is a bit bad？

![](img/c990a1d1bc1607ec62b9419da49f4cdf_727.png)

I said that incorrectly， I meant that okay， talking about modules and stuff。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_729.png)

So a couple things， man， I reached particles were behind。Blocks。

I'm not sure how this will affect the general look at the game Oh probably going to be pretty bad。So。

 but in this case， I can probably add the same color， I had to have like black color。Hopefully。

 I have。 I do have。So let's go back and see， now let's tweak the parameters。First of all， explosion。

I see the count， the count looked pretty cool， the P Dp scale is how fast it's going to scale。

I suppose， right， D scale。DP scale， let's see。No， it's just for the random thing， okay。

 so it doesn't matter the base size， I think it can make that a little bit bigger， oh。

 I add that to the wrong thing and I can make that a little bit faster as well。Maybe like 07。

So youre rotating a single block， I am not even rotating the blocks， man， oh。

 you wanted a particleco on the whole thing。し。This is pretty hacky， man， the way I'm doing this。

It's pretty， pretty hacky。I think I even drew the shapes I don't even。呃。Yeah。😊，Oh no。

 I didn't I have the base shapes here。And I rotate， I rotate them in code。

 like I see whatever position this guy is and whatever position should be for every block。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_731.png)

But I think it won't be that bad。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_733.png)

Let me see if I have a cheat code。Blolock destroyed， yeah。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_735.png)

Yeah， button right。行。Well， well that just sets， it doesn't actually destroy the blocks。Yeah。

 oh button down to right the blocks。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_737.png)

Dan， Dan， Menane， Dan。How are you doing， man？🎼You know， today is the last stream of coding。

We aren't almost over with the game。Yeah， down thetro blocks。Yeah， the small blocks。

 they are a single block， but the big blocks are like several different blocks。是。

It's so cool to pop the blog like this， so let's see。Okay， I like the color。But at the speed。

 it's not very fast， though。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_739.png)

Explosion， which is the speed。Just I just started relearning see。 dude see， it's really cool， man。

 it's， it's awesome to be like go it's like going like on a vacation to a like like a desert beach or something because there's almost nothing there。

 you really value what you have there and you can build awesome stuff with things that are there。😊。

That was a really， really weird comparison。Oh my god， let's go， We're almost done。Go。

Just finished this particles explosion， thanks hello。GP scale is also base size， base life color。

 spawn particles。Is the DPK used for the。D P， yes。So， I'm going to increase。呃。C this like a lot。

It's like a little。And maybe like yeah for seven school where is' going to be released。

 it's going to be released probably next week。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_741.png)

Pretty sure all all I have to do is like send it to steam and make sure it's approved。

And it's already on steam， so here's the team page for the game man'm going drop it for people to like wish this and stuff it's gonna to be free。

 but it's also cool to like be notified when the game's done and stuff。😊，So yeah。

 we have a steep page already， it's awesome when we started at the game？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_743.png)

When I started the game。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_745.png)

I had no idea that it'll be so cool to have like these kind of animations and stuff。

So I'm really happy。With the way he turned out， it's really happy。And yeah。

 today's the last stream where we're going to code。And next stream we are going to release the game。

 so it's going to be the release stream， we're going to play the game。这个。

Duck about whatever people want to talk about。I'm going to tell you how got to programming， whatever。

🎼M的还行。Okay， that was a little bit over the top。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_747.png)

Maybe just make the life shorter。Maybe twice as。Maybe half a long。

And then I think would be maybe a little bit smaller as well。12。Oh maybe you keep Beijing。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_749.png)

Yeah， I think this would be good。Lets goLet's go right of blocks。🎼や得し。How does that look？

Is that much finished？I think it looks kind of finished。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_751.png)

What do you guys think， does that look finished enough？嗯。If I can make that， too。Nope。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_753.png)

Come on man。I'm not going to add smooth rotation for the blocks， it's going to be a lot of hard work。

And。I don't think of just a five bunch of the life。Polish is stuff。

But the particles were good call in sound， particles in sound were a good call。A for DLC， hopefully。

Maybe maybe for DLC， we can add LC。I kind of like the way it did out。

 it's not like the most beautiful thing in the world。But I think it shows that something happened。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_755.png)

$5 person smooth rotations。Do that thought was serious。

I thought it was serious any as a way to improve the game later on。I could， well。

 maybe people could buy the small business for $5， in fact。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_757.png)

For HIO， you can buy the entire the entire game for free。 You can buy the game for free。

 that doesn't make sense。 You can download the game for free or you can。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_759.png)

Like for $5？So maybe you can add like 205 cents， right？



![](img/c990a1d1bc1607ec62b9419da49f4cdf_761.png)

And then you can download。The source code for the game implements smooth rotations。And then。

There'll be smoothizations and $20。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_763.png)

How about that， That's the best plan ever。Dude， I think we're done， I think we're done for games。

I think we are。I think we're not going to make these things。

Then sell it because it's public domain exactly， you're going to download， make the you can do this。

 you could do the smoothification and then sell it as a GLC for the game。😊，That would be pretty cool。

 a good business plan。Okay， so I think they'll be the end guys that will be the end for the development of the game the game is developed it is ready you know we've come a long way and I know I've been saying this for like the past 10 streams or so。

 but we we did you know we checked there were like 7070 hours， 75 hours， whatever。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_765.png)

Of。Programming live。Which is a huge challenge。 wast a huge challenge， but I learned a lot today。

 I learned a lot。 I learned a lot about debugging， debugging some really hard multi threaded code。

 That's really hard。😊，But it is really fun， really great。

 thanks for everybody who came along and watched the game。

 we're gonna to have a live stream so you can keep an eye on that。 That would be pretty cool。

 We're going talk all sorts of fun things。😊，So yeah。You can watch the entire development on YouTube。

From the very first line of code that we wrote。Everywhere from like do you have a date for that。

 I do。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_767.png)

Unless plans change and you can follow them me on Twitter， if plans change。

 we're going to post that on Twitter。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_769.png)

Twitter。com/ Daniellaydan。And I'm going to post that， but if plans don't change。

 which I don't think they will。I'm going to release the game。And do the live stream。Friday。

The 20th of September。What time is good for you guys， Give me a time。What time is good for you guys。

 we can do the live stream maybe we can do the same time we did today， which was like。

 I don't know five。5 PMm Brazilian time and B RRT， so five。P m。Resilient time。Which is like。

GMT minus3。So right now， yeah， so if you do like minus so if you do from five to nine。Four hours。

 maybe a bit too much。I not make it， but I hope it would be fun。Yeah。

 maybe we can do a little bit later， like。Like， I don't know，7。Oh， today's Wednesday， right。

 oh today's Thursday， so it's going to be Friday。Friday7， maybe。It's going to be around that time。

you can follow me on Twitter。Because I'm going to post that。

I I know exactly the time because it all depends if steam will approve and stuff。

 so it may actually be pushed back a week or something。

And I'm going to put all sorts of crazy stuff there。And now that the game's done， you can really。

 you have to subscribe to my YouTube channel because my new projects are probably not going to be all live streams。

So it's on my YouTube channel， which is Dan YouTube iconlash Dan Z Dan。

Where you can find the new videos， right， I'm gonna do all sorts of crazy stuff new games。

 new engine， It's gonna be pretty cool livestream tutorials。

 how program games in C++ and see when when Gi comes out， we're gonna do some Gi programming。 Oh man。

 it' gonna be so cool。 that That would be cool。 That would be cool。

 Maybe we can do like a game engine in Gi。 like getting bits of pieces like from Jonathan Bs engine from like He He engines from my engine。

😊。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_771.png)

Alsos of crazy stuff。 So they are crazy stuff I ahead。 So if you want to follow me。

 follow me on YouTube channel， which there's gonna post most of stuff。 You can。

 you can also release the game。 The game we've been developing because now it's now it's ready， man。

 I don't think I I can't believe it。😊，I kind of miss it already and I'm still live streaming at this moment。

So yeah。So that's it。That's it everyone， I hope you enjoyed this live stream and all other live streams I certainly have enjoyed programming the games for you guys next stream we're just a fun playing the game talking not really programming oh that there's a huge bug and have to fix that that could be interesting。

Hopefully not， we did do a lot of testing today， today was pretty cool。Okay， so if that's it。

 I will thank everybody for watching every live live stream and。😊。



![](img/c990a1d1bc1607ec62b9419da49f4cdf_773.png)

I hope to see you next time。拜拜。