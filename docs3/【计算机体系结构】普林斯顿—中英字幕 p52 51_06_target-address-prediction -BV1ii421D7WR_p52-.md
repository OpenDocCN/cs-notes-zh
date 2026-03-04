# 【计算机体系结构】普林斯顿—中英字幕 p52 51_06_target-address-prediction -BV1ii421D7WR_p52-

![](img/2aff4a8349fafdd1f966b3308758eaf9_0.png)

Okay， so that gets us out of。The outcome part of today's lecture。

 Let's start talking about how to figure out where we're going。

So this brings us back to this picture。 And I took some stuff off this picture now。

But now what we need to do is we need to know the targets。The relative targets。And as I said。

 we don't know the target for a branch， a jump and a jump and link。

Until we actually do PCE plus the offset calculation， sort of somewhere in the decode stage。

 until we at least get the instruction。For jump registers and jumping link registers。

 we don't know that until later。But this is baking out。 This is not looking at the。The outcome。

 this is just looking at， when do we know the value。 But this is important。

 because even though we have the prediction of where we're whether it's taken or not taken and can do that。

 let's say， with 99% accuracy， this is the harder one。

 We're trying to pick from 2 to the 32 possible numbers。Can we actually do a good job here。嗯。

So something not in the slides， but something I wanted to talk about very briefly here。

Is we can use a static algorithm。Similar to what we had seen with the other predictors to do this calculation。

Through the compiler， if you will。 So there's been a few architectures。One example， actually。

 is the Hitachi or or now Renaissance S H 5 architecture， which is sort of a。Me processor。

 willll say。And they actually have。An instruction。Which loads the target of a future branch。

So they decouple the branch into two instructions， the actual branch and a preparer branch。

Which has they have to execute earlier in their instruction sequence， and says。

I'm playing to do a branch， and it's to address something。It's actually called prepare target。

 Is the name of their that this instruction or PT T A on their architecture。And because of this。

 they don't have this problem。They， all they need to do is actually do the branch。

 So they know the target of a branch。In the fetch stage。

 they can actually just go because they have this instruction which says load up this special register with a my target of the branch。

 and then well decouple the actual taking of the branch sometime in the future。

So this is an interesting idea。 I thought I'm pretty sure there was actually one of the CDC machines that controlled daycor machines did this a long time ago。

 also， but I couldn't find the reference in time for today's lecture。

 But I know the S Hhi S H5 definitely has this instruction。

 So all I'm trying to get at here is that there are static software ways to go about doing this。

 In addition， Now let's talk about some dynamic ways。Okay， so。The most。

Common way to go do this is to implement something called a branch target buffer。

And the branch target buffer， you actually do in parallel。With。

Both the branch prediction outcome or the branch outcome prediction and the PC plus 4。 So you。

 you put into it。The current PC。And it's going to tell you， somehow。One out of。

2 to the 32 possible targets。How does it do this？Well。

 what it does is it actually just keeps a table of where that branch has gone in the past。

So the first time it executes， it just gets it wrong。But then the second time it， But。

 but given that first time it executes， it's actually going to load a table。With。A predicted target。

So we're gonna to load the predicted target。Based on where this branch went in the past。

We're gonna index into this table based on our current program counter。And then， we're gonna a check。

To see that we actually match。 So we're gonna take a whole PC， We're gonna do a tag check。

Very similar to our cache。 This is effectively a cache。And if。

A we hit in this small cache here of targets。We have。The new program counter。If we predicted taking。

If we predicted not taken。We also， we just want to use PC plus 4。So in effect here， we can actually。

Predict the target of the branch based on where this branch has gone in the past。What。

 made this a lot easier。I thought it was gonna be really hard。 Well， it's actually not that bad。

One thing I should say is the size of this table kind of matters。

If you allys too many places into here， you may end up just pulling out wrong， wrong data。

 or you end up having a miss quite often。 So you want to size this table appropriately。

But you don't want to make it too big because you're。

 you're carrying the entire program counter in here。And that can get big。

 So the data in here is quite， quite large。So one way to solve this actually。

 is typically people try to make these things set associative。So you'll actually have multiple。

PCs and predicted targets， because that actually a little bit better performance。

If you can check multiple and parallel versus making it larger， I mean， you can just make it larger。

 But typically having a little bit of sociivity helps with this。

But you're really executing this in parallel with the PC plus 4 logic。

One thing that also makes this a little bit better here is the branch target buffer does not hold every instruction。

If it's not a branch or a jump， don't put it in this table。So you really only put in。

Instructions that are branches into this table， which helps save a lot of space。嗯。Okay。

 so we have a question here。How do we achieve this effect。Without decoding the instruction。

 So we have a branch target buffer。We don't want to code the instruction。

Can we just look in the branch， branch target buffer I this， is this good enough is。

 is all the information we need in that table。Cause we're executing it in parallel with the PC plus 4。

 We haven't fetched the current instruction。Is， is that good enough or are we missing something。Yeah。

 this is kind of what I was trying to get at is that because we check the。

 the program counter here into do a full bit with match， this is good enough。

 We don't actually need to look at anything else。嗯。One thing I this this， this。

 this comment was here to make a point about something called a line predictor。

Sometimes you want to get rid of this valid bit。And this PC from before。

And then you just have coming out of here。 instead of predicting the program counter。

 you don't really need to know the program counter。

 You just need to know where to go get it from your cache。

Sort of which entry in the cache to go fetch。 And this is called a line predictor。So， a。

Full branch target buffer will give you an actual PC。At some point。

 you actually do need to know the PC， but you can wait to actually know the PC until later on the pipe。

What we all we really need to know is which line in the cache we want to go fetch。The next cycle。

And we can do that actually， by just sort of removing this check。And just ad hoc。

 just having it fetch whatever it gets pointed to from here， which might be wrong。

We have to check that。So anyway， this is a， this is a trick question。

 We can achieve this with a full B TB。A full branch target buffer。If we don't have。This check。

 it turns into something called line predictor。 So we're predicting which line in the instruction memory or which line in the instruction cache to go fetch from。

Oops。Okay， so this brings us to jump jump register。So， don't register。This one gets harder to train。

 We can try to train it the same way。 We can try to use the B，TB。

So let's look at these different cases。 So what does a jump register use for？

 It's used for switch statements。It's used for C plus plus virtual function pointers or dynamic function calls。

 So if you're doing a jump through a function pointer。And it's used for returns from。Subrines。

So how well does a BTB work in these different cases。So for switch statements。

If you use the same switch statement and the same case gets lit up。This works pretty well。

 It's kind of like training any other predictor。If， if。

The probability that you're actually choosing something out of that switch statement is data dependent。

Or highly data dependent。 You're probably not gonna predict it very well。

 And you're not gonna do very。 There's probably no great solution to this。

There's some people who do sort of data prediction and try to look at the register values to try to do this a little bit better。

 but it gets very hard。Dynamic function calls， well。This works very well。 So if you。

 you' ever in a C plus plus function。In C plus plus， they have function pointers all over the place。

 And this is to implement polymorphism。And this is how when you in C plus plus。

 you sort of do a method access on some sort of function。

 You're actually indexing through a jump table。Inside the data structure。And it just so happens that。

This is basically always， always correct。 unless you actually reassign that object to something else or if that object actually changes to a different type。

嗯。So example of that is that you have。Class animals。 And you have， you know， dogs and cats。

 which subclass from animals。And you have a pointer to a animal， and you have a cat and a dog。

And let's say you assign。A cat to this function or excuse me， this object pointer。

 which is an animal。 And you call some method on it， like run。Well。

 that's going to train up very well。 But all of a sudden， if you change that cat to a dog。

The virtual function pointer because what you actually execute on a cat。 when you run。

 when you run the function， run on a cat versus rain the function， run on a dog。

 They do different things。 Catts like to sleep a lot and dogs like to run around a lot and bark。 So。

 you know， the， the code in the middle of the， the the run function of the cat and the dog are different。

 so。We， we no longer jump to the same location。 So our B T B will be wrong。

 but it' will train up pretty fast because you're probably not changing the object pointer very often。

So that that''s decent。Okay， so subroutine return calls。Jump Pres are used there a lot。

So you call into a function。 You do it with a jump in link。To come back out。

 you come out with a jump register。Well。BTBs are okay。If the place that you are returning。

 or excuse me， the place that you call from。You calling from that location a lot。

But if you're calling a function from different locations， quite often。Effectively。

 what's going to happen here is the。嗯。One function is we call from lots of different locations。

 and you're not gonna to predict the return location very accurately。

So if one leaf function gets called from lots of different locations， that's not。

 that's not particularly。Very good for BTB。1。One interesting thing about。This subroutine return。Case。

Is that。The jump register at the end of， of a leaf function。

The program counter for that jump register is not cor to the function which called into it。

So effectively， when you go to index the B， T B， you're using the address of the jump register。

And it might point to some fun other function that had called it in the past。

And that may have no correlation to someone calls in the future。

 And that's why this is really hard to do。So can we， can we do better for jump registers。Yes。

 so there's an idea of a subrtoutine return call stack。Or subine return stack。

 And the idea here is you have a small predictor。Specifically。

 just for jump register subroutine returns。And what you do is you track。Function calls。

And you push the return address onto a stack。And then when you do a return， you use that prediction。

So let's say we have these three functions here。 We have function A， which calls function B。

 function B， which calls function C， function C， calls function D。As denoted here。

We have some stack that we're gonna push entries onto when we do jump in links。So we。

 we know that there's something to go to load this predictor with。

So when the function call gets executed or the jumping link gets executed， we're gonna push。

The address。Of what is after。Effectively， the function call site。

So I'll deote here about the address of F B。 So that's for when we call when F A calls into F B。

 In reality， it's probably like， well， the instruction right after that is where we're gonna return to。

Likewise。When FB then calls F C， we're gonna push the return location after F。And。When F C calls FD。

 we're gonna push that。And these come off in the return， in the。Inverse order， because it's a stack。

 So when we try to。Pull off this。 We're actually going to pop return addresses。like that。

 So we're going pop off the。FD， F C and F， B， or the address after F FD， F C and F B。

 And we're actually gonna predict the return for this function or the leaf function correctly every single time。

Where it gets a little hard is if we have our call depth。Be deeper or recursion depth， if you will。

 be deeper than how many entries we have in a return stack predictor Then we're going gonna start predicting wrong。

But otherwise， we can do pretty well with this。In fact。

 some architectures make this a little bit easier on the hardware。

 and they'll actually have a special instruction。For the jump in link or the call instruction。So。

 for instance， in X 86， they have the call instruction。 and that。Tlls。The code， basically， or。

 excuse me， tells the hardware to load this predictor。Because otherwise， a jump in link。

 there's too many other uses for a jump in link。 It does。 It's not always a function call。

 It's almost always a function call， it's not always a function call。

 But for a call instruction on X A 6， that's basically always a call。 So you know to load this。

 And then on X  A 6， there's a return instruction， which is always a return from a function。

 you know， thats。The semantics of it are tied very well。Okay。

 so there's actually one other topic I wanted to talk about。Today， that's not the notes。嗯。

This correlates to line prediction。 We talked about line prediction。

 The one other thing I wanted to talk about was weight prediction。We haven't talked about this yet。

 but if you have a。Let's say， two way instruction cache。We talked about where to go look。

Of which line do go look at in the instruction cache。

But one of the things that's just as hard is if you have two way instruction cache and you're trying to fetch the next instruction。

Which way do you go and shove into the decode stage or your pipe。Way 0 or way 1。It's tough。

 You don't know。 So this is one of the reasons a lot of times people will build direct map instruction caches because it's very hard to know which way。

Is the correct way。But our predictors， just like our branch predictors， helps with this。

We can build a way predictor。So we can have the same prediction architecture we've talked about today in today's lecture。

 dynamic。Multi level predictors， sometimes even bait into the， the branch predictor。

And then that can be used to predict whether we choose from let's say way 0 or way 1 or。

 or if we have a four ways set associative cache wave 0，1，2 or 3。Anyway。

 that's what I wanted to talk about today。 And let's wrap up for here for today。



![](img/2aff4a8349fafdd1f966b3308758eaf9_2.png)

![](img/2aff4a8349fafdd1f966b3308758eaf9_3.png)