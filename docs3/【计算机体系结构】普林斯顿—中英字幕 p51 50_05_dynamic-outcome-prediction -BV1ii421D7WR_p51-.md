# 【计算机体系结构】普林斯顿—中英字幕 p51 50_05_dynamic-outcome-prediction -BV1ii421D7WR_p51-

![](img/de12ddc8def43ffb569bbec5a1441a70_0.png)

Okay， so that was。One way to figure out the outcome。 Let's look at a little bit more dynamic way。

Okay， so we can try to build。Pieces of hardware which determine the outcome of a branch。Dynaically。

And this is by adding extra little pieces of hardware。Somewhere in the front of the pipe。

 So somewhere in our PC plus 4 calculation。There is going to be this multiplexer here in the PC plus 4 calculation。

And effectively， we're going to use some piece of hardware to feed into that。

 And this is our taking and not taking prediction values。And we'll talk about this in a second。

 But one of the questions here is what things feed into this PC plus 4 hardware。

one of them is gonna to be PC plus 4。One of them should be your branch target。Unfortunately。

 as we said， we don't know the branch target till here。

 so we can't have that come around in one cycle。So we need to hold off。 That's how we， that's。

 that's this target address question。But。First thing is。

 how do we swing this multiplexer here of our next PC。Okay。

 so some solutions to this that are dynamic in hardware that try to increase the prediction accuracy is we can think about having。

嗯。Something which exploits。The nature of programs。So what we're to try to exploit， first of all。

 is temporal correlation。Of a branch。Probably a branch outcome with previous outcomes of that same branch。

So if you're in a loop。And you fall into a loop， and you have a branch that's predicted， taken。

Or let's say have a branch that is taken。 You can use that in the future to predict the outcome of that same branch。

So here we're actually going to have a 1 B predictor， as denoted by this finite state machine。

And what's gonna to happen is， let's say we start in the not taken state。

If the outcome of a particular branch is not taken， we just stay here。 We continually predict。

 not taken。If we then take a branch， if we don't end up taking a branch。

 we transition over to this other。Pict predict taken state。 And we sit in there if we're not taken。

 And if we have alterating branches taken and not taken。

 we're basically gonna be predicting the wrong one or well。

 we might have been predicting the wrong one every single time。But we can implement this with1 B。

1 extra bit to our control logic。 It's not a lot of logic here。Soly one extra bit。It just says。

Which of these two states you're in？Let's take a look at the performance of this。 Does this。

 does this help。So let's say we have a loop here。That iterates four times。 So we're going to graph。

The iteration number。And then we're going to show the prediction that's coming out of the predictor。

 this one bit predictor。And then we're gonna to look at what actually happened。

 And we're gonna see if we predicted right or wrong。Okay， so in the first。Ittereration。

Let's say we train up the， the predictor。 It says not taken。 It starts off and now it's not taken。

 It's a start state。We're to predict not taken。 It was actually taken because were gonna to loop four times in this loop。

So we mis predicteddicted that wasn't great。But then it transitions from the not taken or predict not taken state the predict taken state。

 So the next few times well iterate the loop， we're gonna get it right。Now。

 this is a relatively short loop。 We only run it four times。

 But if you have a loop that executes 100 times。This might actually do okay。Okay。

 but then we look at the end here。And， well。嗯。The fall through case at the end of the loop。

We're going to predict take in but we actually fall through。 This is the last。

 last little bit of our loop。That's， that's not great。 So here， you know。

 if you look at prediction accuracy， this is 50%。This was， this was not， not very good。Let's。

 let's try to execute the loop again。 And I just kind of wanted to show here the reason that I show a second execution of the exact same loop。

Is to show why the start prediction was not taken。The second time we come back to the same loop。

We left this predictor trained up to be not taken。So now when we go to execute again。

 we come in not taken。And we mis predictdt the first time。Correctly predict the second time。

 correctly predict the third time and mis predictdt the fall through case。

So that's why you need to sort of execute this loop twice here to see what the common case is with sort of the loop back to back。

Otherwise， you know， if we were to change the start state。

You might end up thinking that this predictor does better than it actually does。So that's， that's。

 that's not a whole magic there。 It's simple。It does okay。Can we do better？Well。

 we're nowhere near 99%。So the answer is going to be yes。Okay， so what happens if we start to have。

More bits to do prediction。 So here， instead of having one extra flip flop added to our computer architecture our processor pipeline。

 we add 2 bit to our processor architecture。 We had a 2 bit saturating。Preddictor。

So what do I mean by saturate？Well， what this means is we start off， let's say， in the strong。

 not taken state。And then if you have a predict taken， it moves here。

If you have another predict taking of moves here， if you don't predict predict taking it moves here。

 So we slowly can sort of， we have a range here， if you will， of。Taken， so we've weak taken。

 strong taken， weak not taken， strong， not taken。 And we can sort of move across the spectrum as we reinforce。

The taken or not taking this of a branch。So still， still got quite rocket science。

There is some subtle these here。 Effectively， we're introducing hysteresis into the prediction。

That we're trying to do here are our prediction algorithm。And that that， that can help。 Let's。

 let's see how that helps。So let's execute the same loop here。 Another time here。

 let's start off with strong not taken。Strong not taken， predicts not taken。

And the first time we execute this loop， well， it was actually taken because loops like to be taken。

Lot of mispredict。But we transition from strong not taken over here into the。

We cannot not take in state。So something actually happens that that mispreict was not in vain。

The second iteration happens， and we still are predicting not taken because we' were in this weak。

 not taken state， and we did take it。 So we mispredict again。

But now we actually transition to the week。Take in state。This time。

 things get a little bit better here。 we're actually going to have prediction of taken。

 The actual thing is taken。 We predicted it correctly。 And then finally， for here。

Prediction of taking it was actually not taken。 Sorry， this is actually a mispredt here。 This is。

 this is incorrect。 So if you go， this should， this should be yes。诶。

But can see that this is actually。Doing worse or appears to be doing worse than our one bit predictor。

Well， does， does life get better。Well， we we trained this up a little bit at this point。So let's。

 let's take a look。 And now， let's execute the loop another time。

Given that we started off in this strong taken state。So now we're gonna execute again。

 And we see that we actually predict。Taken， taken， taken， it actually was taken， taken， taken。

And we just mispredict the last one。And what's nice about this is now we go to execute it again。

We're gonna start off because we mis predicteded the end state here。

 We're actually gonna start off in the week taken state。 Sorry， So this is。

 this probably should be week taken。 Is that we were gonna say， yeah， so。

This is another bug in the slide here。 I'll fix this in what I upload。This。

 this should actually say week， we take him， because that's where we left off at the end of this one here。

 But the， the prediction accuracy is the same。We're still going to predict take。

So you can see that this does not get tricked， if you will， does not get untrained。By this one。

Not taking case here at the end。 But what's nice about this is you can train up basically。

 and hysteresis will not get fold by one branch at the end of a loop， sort of falling through。That's。

 that's positive。 Even think about this as actually being helpful that the false through case might even signal you to do something。

People could actually have history。You can even use that to sort of trigger something in your finite state machine。

 If you see lots， lots of take ins， then one not taken on the exact same branch that might mean something to you。

And people， in fact， have done things like that。 So you start to get。Even with two bits。

 you can think about having different state machines。For the same thing。

 So here we have something which jumps directly。Too strong from weak。So。Instead， here， when we had。

Strong。Sorry。We not take in， and we have a take in here。 We actually jump to strong。

 So we train effectively very fast。 So still hysteresis， but sort a faster acting hysteresis。

So this looks pretty similar to what you had before。 But now this week。

 not taken state will'll jump straight to strong taken。If you have one。Mispro。Or something like that。

But this is only one example。 If you go look in actually the Shen La Pate book in the chapter that talks about this。

 they give like three other examples that look similar to this。

 and with are different heuristics to sort of try to get different。Chances or different， different。

Behaviors that are common with programs。But， you know， none of these are gonna to be super。

 super great。Because there are only 2 bits。I you actually start to think about having a table。Of。

These predictors。So you have local predictions。 So it's not predicted globally。But instead。

 we're predicting based on each different branch。And how we do this is we take bits out of the program counter。

 and we index that into this big table。 And then we can store， let's say，2 Bs in this table。

And then we can train each of these things separately。 Now。

 we're not gonna want to have an entry in this table equivalent in the number of branches in the program。

 because it would be huge。But you want to somehow have。Some number of bits， K bits， in fact。

 maybe some sort of maybe just take the low or the medium order bits of the of the program counter。

 we use the as a index， similar to how we use how we use indexes into caches。

You could also think about having multi way asciative versions of these。So instead of having this is。

 this is a direct mapped version。 But you have a multi way asciative version of this。And。If you。

 if you look at， let's say something which is a 4 kilo entry version of this。 That's pretty big。

 actually， but a 4 kilo entry branch history table with 2 Bs per entry。

Now we're starting to get somewhere， we can get sort of 80 to 90% prediction accuracy。So that's。

 that's starting to get us there。 But we had to build。I don't know，8 kb worth of storage。

 And we had to somehow pipe it into our next PC logic。

 which is kind of a sensitive path on our processor。Well， you know， that's。

This can be helpful in performance。So， let's。Actually， before I move off， I I make one。One point。

There are other ways to organize this。Table。So what we're really doing here is。

We're indexing into a table， and we're。Let's say running through some sort of finance state machine decoder here。

 which tells us taken or not taken。 And they were individually updating sub entriesries of this table for a particular branch。

You could think about having other things to index into this table。

 So either more complex hash functions。Or maybe some other history information。

Or maybe previous states， or just some other bits up here。So this is just a base case。

 We're gonna show some more example， more complicated examples for。Spatial correlating predictors。

 But you a lot of the ideas that we're going to talk about in spatial correlating predictors。

 You could apply that to these temporal correlating predictors。

But I just wanted to make that point that these things do what we're gonna talk about。

 we're going gonna show were much more sophisticated versions in our spatial correlation predictors。

 But the， you could apply lot of those ideas back to these temporal ones。Okay。

 so let's look at spatial correlation。 We talked about temporal correlations， so。In time。

11 branch and the direction that one branch goes has a high probability that it's going to influence or or it's going to predict。

 rather。The whether that branch in the future is going to be taken or not taken。 That's。

 that's what is a temporal prediction is， a spatial prediction。 What iss trying to get at this， this。

 this piece of code here is that if you have， let's say， one branch。Do something。 The future branch。

 that's let's say right below it， is going to somehow be correlated。So a good example case。

 And this is kind of the canonical example here， is。If you check this value。And it's less than 7。

It's also less than 5。And you get code like this relatively often。So these branches are correlated。

But they're not the same branch。 They are different branches。This branch and this branch。

So we're having some sort of spatial correlation here。And we wanted to try to exploit this somehow。

 And this was。Yale Pat and， and one of his students came up with this not that long ago。

 surprisingly， in the， in the 90s。And the idea here is that。I don't know。

 We're going to have an extra register。 We'll call a branch history register。Which will store。

Whether previous branches that we've executed were taken or not taken。

And then use that to index into some tables or use that somehow to predict what's going on。

So this is actually going to be a shift register where we're going to shift in。What the branch did。

So it's not based on just the address。Okay， so here's our picture of our branch。History register。

The branch outcome， either whether taken or not taken， goes into here。every time we take e branch。

 we're going to shift a new value in and let the old one sort of fall off the end。

So what can we do with this？Well， we can use it to index a table。

So if we have a pattern history table。What the pattern history table is， is we will be indexed。Bai。

Previous branches。And then， based on this pattern。We're going to look in this table and that'll output either some bits that go into our state machine or might just output 1 bit。

 which says take or not taken。But， you know， the general sense is's gonna output n bit， maybe 2 Bs。

 which will feed into a state machine which updates itself， like what we had before。

What's cool about this is， let's say you have a loop。Which。Always has four iterations。

 So we're gonna to have taken， taken， taken， not taken。Well。

 what's going to happen is we're going shift in these four。Take in， taken， taken。

 not taken into this register。And then。Let's say we execute the loop we execute that whole inner that whole loop multiple times。

 We can train up this。History table here。 And it'll detect if we've seen the loop， let's say。

Have taken， taken， taken。 what do we think the next thing is going to be。It's going to be not taken。

And this predictor can detect that。And that could do that actually with only1，1 B here，1， you know。

 just a1 B state machine。Because。If it sees taken， taken， taken， not or if it sees taken， taken。

 taken。That's gonna index into this table。 And the output of here is gonna be not taken。

So it's gonna to build able to predict sort of short runs。Loops， which have short runs。And if this。

 as this gets longer， this branch history register gets longer， you could actually predict loops。

 which have longer runs。 So if this is 100 bits long。Now。

 you're never gonna have 100 bit long because of a pattern history table of2 to the hundred0 is a very large number。

 But as this gets longer， let's say it's 10。 That's very reasonable。 You can predict。A loop。

 let's say that loops 10 times。And it'll get the fall through case correct。

 Itll get the start case correct。 and you will have 100% accuracy in that loop。

For your branch prediction。Wow， that's pretty cool。

 So this is where we're starting to actually get some， get some traction here。😊。

And this is where branch fiction really started taking off。

 This is where we started to get sort of above 80%。 We start to get to higher numbers。

If we want to go even fast Florida even have better prediction， we can start to think about having。

A branch。History register， which indexes into multiple tables。And then， chooses。

Based on some bits in the program counter between these different。呃。Pattern history tables。Now。

 why do we want to do this？Well。We want to know。Based on our PC here， which one to choose。

 So this is trying to sort of get the， the mixing here of temporal。And spatial correlation here。

Because。If a certain branch。Gets executed。You want to use that prediction for that particular branch。

 And here， you know， you use some hash of some bits in the program counter will choose between some number of these history tables。

So this is mixing our spatial correlation with our temporal correlation together here。

And this this is called two level branch prediction。Because we， we have multiple levelss here。

 We have the history register and nesting here in the， the program counter。

And this can do quite well。嗯。And if we want to have a sort of generalized。2 of all。Branch predictor。

And you want to make this even go better or even go faster。

You can start to add multiple branch history registers。And have them be per。Branch， effectively。Now。

 you're ever going to have it per branch。You're gonna have it be somehow alias into here。

 So you have multiple shift registers。And only when。

That branch is indexed is when you actually shift that shift register。So for for。Relatively small。

Numbers of M coming into this index into this branch。

 history register table and K indexing between different pattern history tables。

 you actually can get very high accuracy。 You can get like sort of 97% accuracy。 Now。

 we're still not 99。Now， you might say， why do I care，97 sounds pretty darn good。Not good enough。

 Unfortunately， you actually need to go higher if you have a 22 stage pipe and you actually want to have decent performance because 2022 cycle mis predictict or 20 cycle mis predictt is。

 is really quite bad。I is pretty damaging when you go sort of work through the iron law of math。

So before we go on， this is kind of one of the more complex slides that we're gonna see today。

 Does anyone have any questions about this of what's， what's happening in the mechanics。

So let's talk about training this。So， as you're executing。You're going to be shifting。

When only when a branch occurs， you're gonna to be shifting the old outcome into this register。

 one of these registers here based on the PC of that branch。And then you're also transitioning。

Based on the outcome， the prediction or the state machine， which is embodied in the prediction。

So this is actually a pretty complex machine here。And you don't probably want to be。Updating that。Oh。

 we'll say。Right in the fetch stage or right in the decocode stage。 So typically。

 how this works is you go to do this update later on the pipe， sort of。

At the end of the pipe somewhere， you go and you actually feed back the true outcome of all the branches。

 and that feeds back into the branch history register and the pattern history tables。And， and。

The downside to this is by wing to the end of the pipe。Is， well， I was first to go for the upsides。

 The upside is， you know that the branch was actually executed。 You know the actual outcome。

 You know that it wasn't squashed by something else。 If you were out of order pipeline。

 you know it was actually committed。Cause you don't really want to train your predictor on bogus data。

 So you don't want to like sort of predict train your data on。

Incorrectly predicted branches themselves。 So if you， let's say。

 have a mis predicted branch and in the shadow of the mis predicted branch。

 you have something else And that would to go and try to corrupt your prediction state。

 That's not good。 So usually you sort of waits the end of the pipe。

 The downside way to the end of the pipe is there's more feedback and it takes longer to train up。

 it doesn't necessarily take longer time。 But if you have a branch followed by branch that wants to use that prediction。

You can't actually use that， let's say， until it gets to the end of the pipe。

 So you're gonna be using sort of old style data for a little bit of time。

 Or as long as your pipe is。Not the ends of the world， but something to be aware of。Okay。

 so now we're gonna start talking about getting under our。Higher 90s， well， higher than 97%。

 We're gonna talk about store games are 99% accurate branch predictors。And this brings us to。

Tournament predictors。It's a great name。Came up first in the alphapha 21，2，64。

And what they did is they actually had predictors to predict which predictor to use。So。

 one of the interesting things going back to this too low branch predictor。Is sometimes。You want per。

Branch information or per branch history。And sometimes you want global branch history。

The perar branch history， you're only basically training this up based on that previous branch。

But in this example here， you're training training it upon other branches。

 So sort of going back here， this is a different branch in that branch。 So you might even want。

 you might actually want global history。But there are times， for instance， in a loop。

 you actually want local history。So tournament predictors， actually。

 they end up with things where you're using a predictor。

 We'll call it a choice predictor that predicts which predictor to use。I show two examples here。

 one which is choosing from a glow predictor and a local predictor。That's， that's。

 that's kind of the， the canonical usage of this。 Actually， than 21，2cc，4。

 They had something more complicated。 I think they had， I think anecdotally。

 I heard they have about 10 predictors in there。 and they're trying to choose between 101010 different predictors。

 and they train the choice predictor。Based on which predictor was correct。So， you can use。Basically。

 because you run loops and you run code a lot， you can train up。

The choice predictor to choose between other predictors based on the accuracy， the other predictors。

 So for a particular branch。One of the predictors is always wrong。 The choice pictureer can say。

 just don't use that one。 Just exit out。So this， this does， this does quite a bit well here and。

You know， you're starting to get into 90， I don't actually know the full numbers here。

 It's probably 98 to 99% accuracy for large individual predictors hooked up to this。You the book。

 Chn Lapasse that you have talks about sort of some other things you might want to try to stick into here。

But for right now， we'll， we'll， we'll leave it at this that we have sort of global predictors。

 local predictors， things that use a branch history register for both of these。

 And then something which predicts between the two。But rest stay one time， you tramp your predictor。

To determine which one to use。 And it has lots of training data。But this is all heuristics。

 If you go look in the book， actually， there's a， they even joke。 There's， it's actually not joke。

 someone actually has proposed。 They call the preceptron predictor。

 and they basically have like a neural net hooked into the predictor the prediction strategy。

 So these things can get pretty sophisticated。 I don't know if anyone has actually ever built the perceptron predictor for real。

 But at least has been proposed。

![](img/de12ddc8def43ffb569bbec5a1441a70_2.png)

![](img/de12ddc8def43ffb569bbec5a1441a70_3.png)