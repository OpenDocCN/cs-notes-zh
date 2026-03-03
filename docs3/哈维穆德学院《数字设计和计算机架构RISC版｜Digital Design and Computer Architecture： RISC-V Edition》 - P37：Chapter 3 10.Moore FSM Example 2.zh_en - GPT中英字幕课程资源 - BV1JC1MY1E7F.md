# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P37：Chapter 3 10.Moore FSM Example 2.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/cb9b627c3c74d1dbd7649e3aaa824eea_0.png)

So here's a more FSM or more finite state machine example。

 Let's suppose we want to build a traffic light controller。

 And we have two inputs or traffic sensors。 T A and T B， They're true when there's traffic。

 So T A is a sensor on academic Avenue。And。TB is a sensor on Bravada Boulevard。

 and they say whether there's traffic or not。And we also have two outputs。

 the lights on Academic Avenue and the lights on bravado Boulevard， LB。Yeah。

So if we were to look at our black box diagram， would have our inputs。

 we always have clock and reset。Remember for our FSMs。And we have our inputs， T， A and T， B。

And our output。Or outputs， L A and L B。And it turns out we're going to need to have multiple bits for each of those outputs。

 So L A will have to have multiple bits because we're driving。A non binary signal is just not。

 The light is not on or off。 It's red， green， yellow， It has three possible values。

So when we need multiple bits， that's the hash mark here for both L and LB。

So our FSM operates like this when the there's traffic on academic Avenue。 It's going stay in。

With a green on the academic Avenue light。 So we have our states， which are circles。Here's our state。

And we're gonna have some transitions， which are arcs or arrows。

 And our outputs are listed within each of the state。So in this case。

 our output in the S 0 state should be that Academic Avenue has a green light。 L A is green。

 and Bravada Boulevard has a red light。And as long as there is still traffic。In。On Academic Avenue。

So T sub a。 Remember， I could have written T sub a equals1。

 but I'm just going make it simple and write T of a。When T A is asserted， when T is one。

 then stay in the S0 state。 This S 0 is the name of the state。The state 0。

So as long as we have traffic on。Academic Avenue， we're going to stay in that state。 state 0。

 But as soon as there's no。More traffic on academic avenue。 So T A goes low。 or in other words。

 T A bar is true。Then we're going to go into another state， S1。

 and we'll start to transition the lights。 We'll turn L A to yellow。And LB will stay red。

On the next clock edge， we'll go to the。Next state， S2， where L A will be red。

 So the academicmic Avenue gets the red light and Grvada Boulevard gets the green light。

So now traffic can flow on Vervana Boulevard。 and as long as。

There's still traffic onda Bovada Boulevard。It stays in the S2 state。

As soon as there's no more traffic in Bravada Boulevard， then we go to the next state。The S 3 state。

 state 3。Where L A stays red。But。L B goes to yellow。So starts to。

Get ready to stop traffic on Provada Boulevard。And then on the next clock edge。

 So each transition occurs on the clock edge。Goes back to state 0。

Where Acade Avenue gets the green light and bravada Boulevard has the red light。

So now we can use our state transitions diagram to fill in our state transition table。

 also called the Next state table。SoState transition table is also called the next state table because we're using the current state and the inputs to determine what the next state should be。

And a note here that we're using S here to indicate our state。

Not to be confused with our state names， S 0， S1， S2 and S3。Okay， so we're from the S0 state。And。

T A is 0。 Does't matter what T B is。Then we're going to go to the S1 state。

 So the next state should be number S prime means next state should be S1。If we're in the S0 state。

 still。And T A is one。Then we should go stay in the SD8 states so the next state should be S is0。

If we're in the state S1 state。No matter what the inputs are。We should go to the S2 state。

 so the inputs are don't cares。For in the S1 state and the next state should be S2。

If we're in the S2 state。And there's no traffic on Bvada Boulevard or TB。Bar is true。 So TV is low。

Then we should go to the S3 state。But if we're in the S2 state， MTB is one。

And we should stay in the S2 state。If we're in the S3 state， we're just going state by state here。

 if we're in the S3 state and doesn't matter what the inputs are。

 there's no inputs on that transition arrow。For the S3 state， next day should be。S 0。

And so now we have our state transition table， our next state table， and it is not encoded。 right。

 We need to now encode。Orre picking codings for these states。And then。

And then write equations for our next day bits。And so these。State names are not the states。 So S1。

 S 0， S 2， S 3， those are the state names。So now we're going to encode these。

 we choose an encoding of， well， I'll write it over here。 S1 colon0 or S1。S1。S0。Let's choose Well。

 we need。 we need at least two bits because we have four states。 So these 2 bits，0，0，0，1，1，0，1，1。

 And you'll notice because we've chosen these state names S 0， the encoding for the bits is 0， S1。

 The encoding for the bits is1， S the name S 2， the encoding for the bits is 2。And S3。

 the encoding for the bits is 3。And so now we have our encodings and we can replace our names。

 our state names with these encodings。😊，So we have here， instead of a zero。

 we'll put our state bids in。S sub1， S sub 0， S sub1 is sub 1 is not equal to state 1。 right。

 These are two different things。So S of1 is state bit1， so S0 will replace with 0。

0 everywhere we see it， state 1 with 0，1 or S1 with 01， S2 with 10 and S3 with 11。

And same thing over here， S1 is。0ero1。S 0，0，0。1，0，1，1。1，0， and 0，0。

We're now just encoding our states and creating the encoded state transition table or encoded next state table。

And now we can write equations for our next date fits。 So we'll write an equation for S1 prime。

 We'll look at this column and find the ones。 So S1 prime。Is equal to well， S0 S1 bar。And S0。

And doesn't matter what the inputs are in that。Row。Or we're doing summer products here。Or S1。

And S0 bar。And。TV bar。 don't forget the inputs。Or the last one that we could get。We。😔，S1 and S 0 R。

And T。subTB。And so we can see， well， let's see this one。

 we can easily see that we can use combining on these two terms， S1 S0 bar。😊，T bar。

 T sub B bar or S1， S 0 bar and T sub B。 So we'd get。Equals。S1 bar S 0 or。S1。S is0 bar。

 These differ only in the TB B term。So we combine those terms to get S1 S0 bar。

And we'll notice that that's the X or function。 So this is equal to S1 X， or。S of 0。Okay。

 so now we use the same process to find the next state bit0。 So here's next state bit 0。

 We'll use some of our products again to find our equation。 So S sub 0 prime state bit 0。

The next state is zero。We're going to have our first one will be S1 bar and S 0 bar and T A bar。

 So S 1 bar。And S 0 bar and T， A bar。Or let's find our next one。S1。And S 0 bar。And。Tis a B bar。

And so now we have our two next state equations。😊，And we can implement that in our circuit。

 in our next state logic。And we do a similar process with our output table。

 Remember in our output table， the outputs in a more finite state machine are completely determined by the current state。

 So we only have our current state here on the left。😊，We do not have our inputs on the left。

In an output table， the outputs are completely determined by the current state for a more FSM。

And so we here we have our states on the left。S 0， S 1， S 2， S 3。Are different states here。

 And we just look at the outputs。 while in the S 0 state， L A should be green。and l b should be red。

In the S1 state。L A is yellow。 L B is red。In the S2 state。L A is red。 L B is green。

And in the S3 state。LA。Is red。And。L B is yellow。And so we have our unencoded。

FSM and now in addition to the encodings for our states， which we've already done。

We have outputs here that can be either green， yellow or red。 So we need to encode them。

 We could have chosen different encodings。 But here。

 the encoding we're going to use is to well with three different values， we need at least two bits。

Green is encoded as 0，0， yellow as 01， and red as 10。We could have chosen different encodings。

 for example， if each of the green， yellow and red had a wire that was tied to it。

 which would make sense， green， yellow and red， so this would be 10，0 with3 bits of encoding。

 this would be the 010 encoding and this would be a 001 encoding。😊，But again， for this example。

 this is a valid encoding too， we'll choose the encoding of green being 00。

 yellow beam 01 and red beam 10。😊，So now we encode our output table。

 We replace our state names as 0 with their state bits or state encodings。 So 0。

0 for that encoding state 1 is。0，1， state 2 is 1，0， and state 3 is 1，1。And green。

 we replaced with zero， zero。Red with 1，0， yellow，0，1。Red 1，0， red 1，0， green 0，0。And yellow， zero。

 one。And now we can write equations for our outputs。 So L。Sub1， L A bit1。Is。Well。This is。Equal to S1。

L A 0。Is S1 bar and S 0， S1 bar and S 0。o。B1。It's just S1。Bar， again。

 you put these in into a came out to to minimize wise it。 But L B1 equals S sub1 bar。And。I'll be 0。

Is S1。And S is 0。So now we have equations for our outputs as well。

 and we can use those to implement the output logic in our circuit。

So we're going to start with our state register， we have two state bits， S1 and S0。

And remember that the current state is on the right and the next state is on the left。

Now we're going to implement our next state logic。Using our next state equations。

That we derived in the previous slides。So we have S1 prime state bit next state bit1 is going to be S1。

We bring our current state around。S1。X or。Has 0。S0 prime is。S1。Bar and S 0 bar。 and T， A bar。

Or there an orate。S1 and S 0 bar。And TV bar。And now we're going to implement the output logic。

 which is determined in a more FSM completely by the current state。And we get our output。Logic。

 given the equations that we derived in in the prior slide。We have L A1 equals S 1。Here。

 L A 0 equals S1 bar and S 0。L B1 equals S1 bar。N L， B0 equals S1。And S 0。

And so you can see that we have our。Next state logic。

Next state logic determined by our current states and our inputs。And our output logic。

Our block of combinational logic that determines the outputs。

Is completely determined just by the current state or the state of the system， S sub 1 and S sub 0。

And we can do a timing diagram as well to see what our circuit does。And we can go through the。

Timing timing of our system and see that one the。We get our clock and our clock reset and inputs。

 and we see what the next state， current state and outputs do。 Well， if we're in the S0 state。Then。

 given our circuit。We would expect that we would go into at the next clock edge if as long as T is high。

 it stays in that state， but when TA goes low， it's going to transition to the next state S sub1 or the01 state。

And so forth。So let's talk a bit about state encodings。 So so far。

 we've used binary encodings where we use a minimum number of bits。 So if we had four states。

 like in the last example， we need log base 2 of 4， which is 2 Bs， log base 2。

Of the number of states， where N is the number of states。So， for example。

 log base 2 of 4 is equal to 2。Log base2。 and and we log base two of 5， for example。 Well。

 that doesn't turn out to be a nice number。 So we take the maximum of it so that。Largest integer。

You know， the next largest integer would be 3。 Anything up to 8 would need 3 bits， right。

 We can encode the easier possible way to think it about is how many bits do we need to。

To encode five values。Well， it can't do five values with 2 Bs because we can only encode four values。

 So we need another bit or 3 B。 So anything up to 8 states would need 3 Bs。Once we pop over to nine。

 now we're going to need four bits。Up to9 to 16 states will need four bits。And so forth。

 So binary encoding is going to use the number， the fewest number of bits in our state encoding。

 And we've used that up until now。One hot encoding is so this term hot means high。

 so we're going to have only one statement that is hot or high。In any state。So if we had four states。

 for example， we would have。4 state bits。So this would be the S 0 state， S1。State 2 and S 3。

 And so now we have four state bits， S 3 column 0。 This is S。The state and S 0 is a state name。

So with one hot en coating， there's one bit per state and only one state bit is high at once。

This requires more flipfls， more state registers right when you need four bit state register instead of the binary binary encoding situation。

 a two bits of state or two bit state register。But often the next day an output logic is simpler if we use one hot encoding。

So let's do one hot encoding for our last example where we had our traffic light controller。

So now our state encodings are going to be while we're going to use 4 Bs of state S 3 to 0。

 and we'll have S 0 being。Only state is 0 is high， S1。State at one is high S2。Step but2 is high。

And S 3。S of3 or state of 3。It's time。So now we have these encodings for our。For sta bits。

For our state， we're using one hot encoding。 So now instead of S 0， we'll have 0，0，0，1。

So that's the encoding we're using。 The unencoded state transition table looks exactly the same。

As the as no matter what encoding you use。So is S1。Its at is 0，0，1，0， S 2。0，1，0，0。S 2 again。

And S 3 is 1，0，0，0。And same thing on the right here。

We use our one hot encoding instead of the binary encoding that we used before。

And so now when we write equations for our next state。😊，We're still going to use some our products。

But let me show this is a common error。 So S 3 prime， state bit 3， prime。 So next state bit 3。

Is going to be。 Well， this is the the。Tempting thing to do。 Just straight summer products。

So S3 bar and S 2 and S1 bar and S 0 bar and T B bar。That would be S 3 prime。

 But we know because of the way we encoded it， we chose 1 hot en codingding that if S 2 is high。

 we already know by definition that these are low。That S3 is low。 S1 is low， and S sub 0。Is low。

 And so we don't need to include those in our equation， and we shouldn't。Right。

So our our equation for S3 prime is just S2。 Well， we don't。

 we don't need to include this information。 It's redundant。

 We already know because of the way we encoded it， that those are zeros。 if S2 is high。

 it's one hot enco。 so none of the other bits are high。So S 3 prime equals S 2 and TV bar。

And let's do the next bits。S sub two prime。Is equal to。Well， S1。S sub one。

Don't care as on the inputs。Or。啊笑。And TV。As the one prime。Equals S sub0 and T bar。And our last one。

S sub0 prime。Right over here， a 0 prime is equal to。S 0， N T A。Or。S 3。And don't care on the inputs。

And so again， the common errors include all those state bits in our equation。

But because of the way we encoded it， we only include the state bit。That is high。

So that's the common error there is to want to include all of those。State bids。

 S3 bar and S 2 and S 1 bar and S 0 bar。But that would be incorrect， right， it would work。

 but it's not efficient。uses too many a larger gate that we need。So really。

 we should write this as S 2 and T B bar。And same process with the next。The next next seat bits。

And you'll notice from the state transition diagram。 Well， this kind of， you know， makes sense。

 So S3 prime， so S。State bit3 prime。Right， we know that S sub 3。Or state bit 3， This is S 3 to S 3。

 S 2， S1， S 0 in state 3， S sub 3， state bit 3 is， is high。 So S 3 should be1。1， S 2 is 1。

In other words。You're in state 2。And。TV。Is low。So our next state equations。

 we can double check them because they're kind of an immediate translation of the state transition diagram。

 Let's look at another one。 S 2 prime。 So S2 is going to be。A next date， if。You're in state  one。

 in other words。State vote one is one is true， or you're in state 2。And T B is one。So stupid it 2。

Hiss one and。TB材。Same thing for S1 prime S1 is going to be the next state， if。

You're in state zero and TA is low。S 0 is going to be the next state if you're in state 0 and T A is high or。

You're in state three。The current state is state3。And so an easy way to double check to double check those equations。

I to look at the state transition diagram。And so now we can implement our finite state machine using our one hot state encodings。

Well we start with our equations。 Remember never to include all of the state bits in our equations because of our encoding。

And we're going to。Start with our state registers， the process is the same。

 just our equations are different。So， we start with our。State register， in this case。

 we're going to have four bits of state。S 3， S 2， S1 and S 0。

And we're going to bring those state bits around。We can use them to calculate our。Next date。

And we also have our inputs。T。And TB。TA and TB。And now we're going to calculate what our next state should be。

And so always connect our clock。And our reset。And so we have S3 prime， S2 prime， S1 prime， S0 prime。

So S3 prime is going to be。唉。Single Anne gate S2 and TB bar。Here we have an orgate。With S1。

And angate S2 and TBB。Here we have S 0。And T A bar。 And here we have an orgate。With。S 0， N T A， and。

Other value。 So now we connect them S3 prime is S2。 So sometimes again， I labeled these up here。

To helplp me remember， whether they're not inputs there。

 remember they're being fed out from the state register。But we have S2。And。TB bar。

Is our equation for S3 prime。S2 prime is S of1。And or or。S 2。And T B。And here we have for S1 prime。

 we have S0。N T。R。And for S，0 prime。Asome。A zero prime。We have S 0。And T， A。Or。S 3。

And we could also write outputs， output equations。So we could have， here's our。

 I'll go ahead and go to the straight encoded version S 3。To 0， There are states。And our output。L A。

1 column0， I'll be1 quo0。And remember green。Yellow。Red， green was encoded as 0，0，0，1。Red was 10。

And so here's our states， 0001-0010，0100 and 1000， this was S0 S1， S2 and S3。So in the S0 state。

 we want it to be green， red， so green。And red is 10。S 1， we want to be yellow。And red。Ss2。

 we want it to be red。And green。And that three should be red。And yellow。

And so we can have equations here。Let's see。 So， L A。Bit  one is equal to。Well。S of 3， S of 2。Yes。So。

2。Or。S of 3。L A 0 is equal to。S sub1。Stteep at one。I'll be one。Equal to S1。Or are S of 0 or S1。

 S of0 or S 1。And finally。L， B sub 0 is equal to。Just S of 3。And then we could， you know。

 get right the。implementm that in a circuit over here on the right。For our output logic， L and LB。

So we can now implement that here using our state bids。To output。L A。



![](img/cb9b627c3c74d1dbd7649e3aaa824eea_2.png)

And I'll be。Okay， so there's， there's an error in this。In this circuit。

And let's see what happens when reset goes high。 So if reset goes high， as is。

we're to implement these equations in there for our output logic。😊。

So let's see what happens if reset goes high， so reset when reset equals one。😊，So we get a。

 This is a resettable flip flop。 recycles one， our sta bits。Become all zeros。Gosh。

 that's not what we wanted。 right， And the reset state should go to S 0， but S 0 is encoded as right。

 state 0。We encoded that as 0，0，0，1， right， S 0。 We encoded it as。This， not all zeros。Well。

 we can still make this work。This is a common error here， but we need to make the bottom。Flip fl。

A setable flip flop。 and all the rest are resetable flip flops。 So when reset goes high。

 still tied to the set and reset inputs on those。 Instead of getting 0，0，0，0， we get 0，0，0，1。 And。

 in fact， it does。Reset to。To S 0 or the。诶。0ero01 state。

