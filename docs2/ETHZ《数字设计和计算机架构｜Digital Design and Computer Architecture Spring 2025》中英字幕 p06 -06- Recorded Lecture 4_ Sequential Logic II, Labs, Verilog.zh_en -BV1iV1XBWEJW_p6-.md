# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p06 -06- Recorded Lecture 4_ Sequential Logic II, Labs, Verilog.zh_en -BV1iV1XBWEJW_p6-

![](img/ca60c4d5aa3eb8571a442a7d418d47d8_0.png)

Okay， let's get started。Is it all good， okay？不。Okay， we're going to continue well。

 there's still 30 seconds or so。Let's make sure this is working， it's working。Okay。

 we're going to continue the third week， we'll start the third week of this lecture。😊，Good。

And remember that we were designing sequential logic and finite shape machines today。

 we're going to finish sequential logic design。😊，So you should be able to do both combinational logic and sequential logic and then。

😊，We're going to talk about hardware description language and very log so this is what we covered in the last lecture green stuff all of the green stuff we've covered only the blue stuff is left oh thank you that's much better。

😊，So basically we're going to design finite aid machines today， we kind of designed them last time。

 but right now we're going to do it a little bit more rigorously fully。

 but recall the first 10 slides or so I'm going to jog your memory of what we covered we talked about sequential circuits sequential circuits essentially produce output that's determined by。

😊，Currenturt inputs as well as past values， these are circuits with memory and we' actually built a bunch of storage elements to make this thing work right and we had covered combinational circuits earlier and this was my analogy for a combination versus sequential and I think this really captures the memory aspect of a sequential circuit very well the lock over here the sequential lock on the right to your right has some memory and we built a state machine for that sequential lock for a particular combination and you can see the state machine and we said that this' is an asynchronous state machine because there's no clock in this case there's no synchronizer if you will。

😊，And you can verify the state machine yourself and we discussed what a state machine is。

 state machine is really a pictorial representation of a discrete time model of a stateful system essentially。

 and this has a finite number of states， finite number of inputs。

 finite number of outputs and an explicit specification of how you can go from one state to another state and an explicit specification of what determines each external output value and how it's produced and when it's produced does that make sense？

😊，So that's clear， hopefully and this particular finite state machine has all of those characteristics actually。

😡，And then we talked about how to build this， basically we need three elements。

 three circuit elements， one is the state register， we talked about that。

 this is how do you build the state register so that you can remember the current state that you're in。

And then next state logic， how do you go from one state to another state。

 next state logic determines that， and then output logic。

 how do you produce the output of the finite state machine given the inputs and the current state。😡。

And you can see that this is how you actually organize a finiteate machine。

 any finiteate machine can look like this， I don't know what's happening。Anybody。

There's some timeout that is present somewhere here。That could be a finite state machine。

 there you go。The finite state machine is kicking in every maybe some synchronous clock okay but basically at the beginning of the clock cycle next state is lashed into the state register and we actually spend some time to build the state register because what we start out with the Dlatch or gated dt was not enough right so we built the sequential circuits as well as the combinational circuit so we said remember that how do we implement the state register so that it has two properties when is the data gets lashed at the beginning of every clock cycle and the data inside the state register is available for the full clock cycle full duration of the clock cycle so that the combination logic for the next state logic as well as output logic and evaluate for the full clock cycle and they can settle and this is going to be very important for the timing lecture that we will start tomorrow。

😊，We now ignore the timing we want this desired behavior， how do we make it happen。

 we said that the latches that we design until that point in time are not good enough because they're transparent。

 what does transparency mean transparency means that whenever the input value changes while the clock is high the output value also changes so this violates what we want to do what we want to do is we clock we want the input signal to affect the output signal only at the clock edge right and available for be available for full cycle and then we develop the deep flipfl so hopefully you can see that state changes on a clock edge in here this is really annoying。

😡，Some clock had just happened， for example。Okay， well， maybe it'll keep you awake。

Or maybe I'll keep you away from computers once in a while。Okay。

 I see a lot of people paying attention so that's good so basically state changes on a clockage and the data is available for clock full cycle because what we did was we actually had let's say protector first latch behind earlier than the second latch and this ensures that whenever the clock changes when the clock is low for example。

 the first latch propagates the value of D to the output of here and whenever the clock changes from low to high this called the rising edge of the clock the value of D that was propagated here gets propagated to Q because of the way clock is wired as you can see to the right naval signal of the first latch and the right naval signal of the second latch clock is basically。

😊。

![](img/ca60c4d5aa3eb8571a442a7d418d47d8_2.png)

![](img/ca60c4d5aa3eb8571a442a7d418d47d8_3.png)

This is really annoying you cannot see it right， we need to fix this somehow。

So when the clock is low D goes here， when the clock is high when it transitions high that capture D goes over here okay so that's the D flip fl we actually covered this last time I covered a little bit more because it's important and we can actually use these D flip fl to implement the state register as many D flip flos in parallel as you need essentially and I'll show you that in a little bit but just to summarize this was the last slide we covered in the last lecture we say that flipfl samples the input D on the rising edge of the clock or positive edge of the clock you can easily design a negative edge triggered D flip fl also but this is a positive edge triggered D flip flop yeah and I think we said everything over here so this is an edge triggered state element because it captures the data on the clock edge as opposed to a latch which is a level triggered state element which captures data on a level for example when the clock is one or when the clock is zero depending on how you tie the right naval signal to the clock。

😊，The different levels of the clock can actually enable state transitions。

So we want these edge trigger state elements in our finite take machines for the reasons that we discussed earlier so how do you build basically a Dfpl based register is very similar to another register that you use we did build using latches except now we use D flip flos so this picture shows you four d flip flos so this is a four bit Dfpl based register and you can actually indicated this way this is one representation of it this register stores four bits and you can see that output is four bits also this line represents four wires that's what this four over here means with a slash on the wire。

😊，So you'll see this terminology a lot and this is from your other book Pat and Patel book that basically shows essentially the same thing。

 but it shows the internals of the flip plot and you can see how expensive this is right there as I said there。

😊，There are eight gates and there how many transistors we say over here。

 so one9 gate is four transistors， right？So what we have。How many transistors does anybody？

Want to venture？So for one of these deep flip flops， we have one， two， three， four N gates。

Each of them has four。transranistors that's 16 and then you have an inverter over here that is kind of hiding。

That's 17 and then you duplicate that that's 34 so each of them has 34 transistor that's a lot right and we compare this to DM that has only one transistor。

😊，Okay。If I made the match wrong。Please shout， it's okay。So nobody objects。Okay。Okay。

 so basically now let's actually build a finite state machine based on what we've learned。

 we're not going to go into the details of the flipflop anymore。

 but you will do this actually in your labs we're going to get back to it in the later part of the lecture when we talk about very log and hardware description languages we're going to figure out how to write this exact same thing in a hardware description language called very log it's going to be very easy actually。

😊，You don't need to worry about the internals， especially when you do the behavioral modeling if you do the gateit level modeling as we will see later on that's called structural modeling。

 you will need to know the structure， but if you do behavioral modeling we're going to abstract it away and you don't need to know the underlying implementation but now you know why it's important to know the underlying implementation right how many gates could it be implemented with。

😡，Okay， so finite state machines， we said that next state is determined by the current state and the inputs and there are actually two different types of finite state machines depending on what the outputs depend on in a more type of finite state machine the output depends only on the current state。

 so output is really solely a function of the current state。😡，And we will see this。

 and we will also see a meli type of finite take machine where the output depends on the current state as well as the inputs。

😊，Okay， so this is the way you design the machine actually state basically in the more type of machine。

 state directly indicates your output and the other type of machine。😡，Just by looking at the state。

 you don't know the output value， you have to know the transition from the state。

 you have to know the input that goes into the state as well。😡。

And this has trade offs so let's take a look at one finite aid machine example from your book。

 how many people have seen this？😊，Okay， that's good， you're reading the book， I guess。

Or maybe watch the lecture from the past， how many people are reading the book？😊，Okay。

 that's great yeah okay so basically this is a supposedly smart traffic light controller。

 which is actually not so smart as we will see， but it's trying to be smart at least different from the traffic light controller that we've seen earlier so in this particular case we have two avenues Avenue A let's say and then Avenue B or boulard B A and B let's say and the traffic light there are four traffic lights as you can see over here and there are two inputs and two outputs to each traffic light theyre traffic sensors on Avenue A and Avenue B and these traffic sensors are one bit inputs。

😊，And they respectively turn to when there's traffic on the corresponding avenue or corresponding road。

 let's say， and they're false， when there's no traffic on the corresponding road and their two outputs these are the lights basically LA and LB and LA and LB actually I said four lights but the lights on the academic Avenue are the same and lights on the Bravada are boulevard are the same over here and each of them have three states as we have discussed。

 these are Swiss traffic lights as opposed to Texan traffic lights， there are three states。

 red yellow green， if you were living in Texas it would be red and green。😡。

There would be no yellow you could make an argument as to which ones better but we're going to not talk about that state can change every five seconds that's our assumption。

 but there's one but over here except if you have traffic on an avenue and if the light is green state doesn't change you stay at green。

😊，So this is the smartness。Not so smart in one sense。

 because if you keep having traffic on one avenue， that avenue will stay green forever， right？😡。

So you will get denied service on the other avenue。

So this is actually an interesting design thing whenever you're scheduling you need to be careful about fairness and quality of service。

 so this traffic light doesn't satisfy fairness and quality of service requirements or definitions it just says if the light is green and there's traffic on this avenue。

 that avenue is prioritized over the other one， live with it。😡。

So the people on the other avenue can go crazy。Fine， that's the traffic light that your book has。

And this is basically a black box of the finite state machine that we have。

 you can see that all finite state machines out to have a reset state that basically tells you where you start the system when it's reset。

 like when you power it up for example。😊，So don't never forget the reset state。😡。

Because the system is completely undefined if you don't know where to start from。

 basically to begin with， right？😡，So if I don't know how to start this machine。

 what is the reset state， then this machine can give me all kinds of junk output in the end， right？😡。

So this is critical and there's a clock as we said because it's a synchronous finite state machine。

 and then there are two inputs， these are the traffic sensors and then there are two outputs。

 these are the lights on the two different roads。😊，Okay， I've already said all of these， I think。

Yeah now let's take a look at let's construct this finite state machine diagram relatively quickly。

 we're going to construct the more finite seat machine。

 but you could also easily construct a me one states are going to be circles， this is our state zero。

 the light on Avenue A is green， the light on boulevard B is red。😊。

It just happens that way and it happens that we're prioritizing that one in the beginning reset when whenever you reset you go to that state。

 transitions are basically arcs so reset clearly causes some transition basically you go into the state from an undefined point whenever you start。

😡，And then you're not seeing that， but now you're seeing it whenever there's traffic on Avenue A。😊。

And the light is green， you stay in state zero， as you can see， when there's no traffic on Avenue A。

 you go to state one and state one basically changes the light so that avenue B can take over at some point so you can see this is yellow and red now。

😡，And then going from state one to state two is unconditional， it doesn't matter what the lights are。

 you after at the next clock edge， you go to state two where the light on Avenue A becomes red and lighton Avenue B becomes green。

😡，And then the same thing happens basically if traffic is there at the clock edge at the next clock edge。

 you stay in state2， otherwise if traffic is there on avenue on boulevard B at the next clock edge you stay on state two。

 otherwise you transition to state three and then the transition from state3 to state zero is unconditional again because yeah because this is an intermediate state where light B is yellow as you can see。

 so this is a more type of finite state machine because。

States clearly indicate what the outputs are outputs are solely dependent on which state you're in so outputs don't actually happen when you go from one state to another state based on some input。

 so if you look at this and if the outputs are indicated inside the state circles over there。

 you can say that there's a morety of machine。😡，Okay。

Anything good so based on the specification you can design a finite machine and that's what we did basically you can say specification is not great。

 so I'm going to enhance the specification in some way。😊。

Canim we easily fix this problem because it's getting really annoying is it annoying for you guys？

Yeah， I think so。I't know how to easily fix it。诶。I guess one option could be I could present from here but。

Okay， while you're doing that。We need to go okay， okay。

 you need to to share the screen to share the screen， Okay， okay， let's do that。😊。

But can I quickly do that， I guess I don't know。Okay。

 maybe I'll take questions in the meantime any questions so what we're going to do is basically we're going to build essentially the output logic。

 next state logic as well as state register。😊，Any questions questions far？也是不是。系度。Other types of Y。

 other than more a immediately。I mean， there are other classifications like synchronous versus asynchronous。

 like you discussed got this time， right？It requires a clock。

Whereas the sequential lock finite state machine was an asynchronous finite state machine。

 so certainly yes there are other types of finite state machines， I would say。

 but in terms of how outputs are generated based on the dependence on the state versus state and inputs。

 it's just more and merelyy。😊，Any other thoughts？Okay， good， let's hope that this works， thanks。Okay。

 this thing is also working so I can see myself too。Okay。

 so now let's build any other questions now that we've started questions。😊，Okay， good。

So we've switched the finite state machine as you can see right。

 something that's controlling you can also do that right you can switch the finite state machine dynamically in a machine in a real machine。

 and we will see that later on。😊，Okay， let's build a state transition table so we have the state transition table now let's actually turn this into a truth table right we know how to do that basically this is we're going to decide the next state logic。

 next state logic as we said， is a function of the current state as well as the inputs。😡。

So based on what we built this pictorial structure。

 if the current state is s0 and if there's no traffic on a then the next state is S1 right so basically you can build this truth table relatively easily by just looking at things and again this is a butcher type of truth table it's a compressed type of truth table right I don't have ones and zeros I don't have a very possible input value but I'm going to expand to that in a little bit and I also don't care is as you can see right I don't care what the traffic sensor on Avenue B is in state zero because you can see that TBB is doesn't determine anything any transition from state zero。

😡，If the state current state is a state zero and there is traffic on Avenue A。

 it doesn't matter what traffic sensor on the avenue B is the next state is still s zero so you can basically keep doing this and then this is an unconditional transition as you can see if the current state is S one it doesn't matter what the inputs are the next state is always as two at the clock switch you change that next state now let's un these states we're going talk about encoding later on but you can choose one encoding this is one ending since we have four states we need two bits right that's the most compact encoding and I assume these two well your book assume these two values。

Now you can actually write states as input2 bit values， let's say。

 that are stored in the state register， and basically I just replaced S0 is 00 s1 with 01。

 s2 with 10 and S3 was 11 everywhere in the the table。😡。

Now we have a much nicer tooth table and now we can actually express this in terms of Boolean logic。

 right as one prime this bit of the next state。😡，Is one。

Now we're doing this sum of products form is one only for these input values。Meaning S1 prime is1。

For if S1 is0 and S0 is1 and this doesn't matter so you can actually write this you can see that these are the these are the implicants well I wouldn't call the implicants these are the values of the input variables that correspond to S1 prime being one right S1 prime is1 if this is true or if this is true S1 is1 S00 and TB is one and it doesn't matter what this is and this is sum of product form or somewhat reduce sum of product form because we have don't cares over here essentially this function S1 prime and you can do the same thing for a0 prime you can see that S0 prime is one only for these values of the truth table this compress truth table as you will and that corresponds to S1 S0 and T all being zeros and S1 being one S0 being0 and TB being zero and these are the。

Some of products form essentially， again， considering the don't cares。

So everything we learned in combination logic and logic simplification also applies here。

 you can simplify this and this becomes just one extra door as zero and the other one。

 unfortunately you cannot simplify it further。😡，So that's our next state logic basically does that make sense this is how you determine next state based on the current state and the inputs now let's take a look at the output table we're going to do the same thing essentially well something similar not exactly the same thing of course as we said output is the more type of machine so output is solely a function of the current state that's why you don't see the inputs to the finite state machine on the left hand side of this truth table again。

😡，And if the state current state is 00， s 10 as00， then the LA is green and LB is red so you can actually verify this。

😊，Now you need to encode the outputs， of course because green and red doesn't mean anything。

 you cannot simplify that， you need to encode green。

 yellow and red and again these are three there are three types of three outputs so you need two bits to represent them in binary。

😡，And then you basically do the same thing， you try you start simplifying LA1 is one。😡。

If S1 is one as you can see right so we quickly did that simplification over here based on the uniting theorem right you remember uniting theorem says if for the onset of a function in this case the output is LA1。

😊，If an input changes。😡，And it covers all of the possible changes in binary in this particular does。

 then you can eliminate it， so Sra can be eliminated， so LA1 is represented this one。😡。

And LA0 is one only in this case as zero as1。And this happens to be LB1 is one。When S1 is0。

 so it's s1 prime as you can see this again based on uniting theorem and then L be0 is expressed this way。

 so this is the output logic as you can see so each bit of the output is determined as a function of the bits of the state。

😊，Makes sense， right？Okay， so there's no magic as you can see right any finite state machine。

 you can reduce it to a truth table， once you have the pictorial state transition table and once that's correct and complete。

 you can reduce it to a truth table and then you actually optimize the you can actually express the next state logic and the output logic。

 which is what we did right now。😊，Okay let's take a look at the schematic right now so this was our finite state machine general our state register is going to look like this basically it's a twobit state register and this is the current state on the right clock reset and then this is the next state on the left next state bits coming in on the left and there will be a logic that determines the next state bits as we discussed and this is the logic that determines the next state bits based on what we did earlier right？

😊，For our traffic light， smart traffic light， I should say。😡，Okay。

So hopefully that's clear and this is the output logic basic output logic is solely a function of S1 as0 inputs doesn't matter over here for the next state logic you can see that inputs TA and TB mattered obviously but because it's a more type of machine。

 the next state logic or output logic is only dependent on the current state。😡，Okay， no questions。

 We can on。 So this is something I'm not going to cover in detail， but this is good to think about。

 This is a timing diagram based on some inputs we're going to cover more on the timing diagrams tomorrow。

 just this is just a job you're thinking a little bit。

 So you're in this current state and then inputs。😊。

Now something is happening over here you can see that the reset reset basically resets the current state right at some because reset is high you reset the current state and you go into the state and this happens to be actually a flipfl with an asynchronous reset because the reset takes effect almost immediately regardless of the clock edge。

😊，So we're going to talk about that when we talk about the very log lecture。

 so reset doesn't depend on the clock basically whenever you reset the machine doesn't depend on the clock。

 so this is not a completely synchronous system from that perspective。

 but we will talk about that when we talk about flip flops and hardware description languages。😡。

And then you can see that you're in state zero over here and it happens that T is one。

 so you still stay in state zero over here， and then T becomes zero right at the clock edge over here so you transition to state one over here and take some time so transitions actually take some time based on the combination of logic delay。

😡，Because remember there are two types of combination logic over here， the next state logic。

 what is the next state going to be and what is the output going to be output logic and because there are non zero delays that you have in these gates that for example the end gates earlier or end gates it takes some time to transition from state to state so it takes some time for the outputs and the state to change and that's what this delay is and we're going talk about that a lot when we talk about timing and verification。

😡，This is just to prepare you for that and you can see that transition from state one to state two is unconditional。

 it doesn't matter what the inputs are TBb is one for example。

 it doesn't matter you transition to S2。😡，And then you can see that is yeah。Yeah。

 next state stays in S2 because TB is1 while you're in S2 and then you transition to S3 when the TB becomes zero at the next clockage。

 it just happens to become zero over there。Okay， and then there are some transition delays so if you want to go through this in full you should look at H and H chapter 3。

4， it actually has this demonstration， but we will see in timing and verification。

 so this means that。😊，If you want to properly transition， if you want this to work correctly。

 your clock cycle should be long enough。😡，To accommodate the delay of the combination logic。😡。

And the latching that we have， right， this is really critical if your clock cycle is so short。😡。

That the combination of logic takes longer time。😡，To settle， to evaluate。

To evaluate its outputs from the time inputs change。

Then you will not get a properly working system that's the importance of timing your clock cycle should be long enough to accommodate the longest combination logic delay that you have in your system and we've actually seen that combination logic so let's go back。

😡，So this is the their true combination logic one is this your clock cycle should be long enough such that。

😡，诶。After TA and TB change， and S1 and S2 start propagating。

 this delay over the circuitry settles basically your clock cycle should accommodate the delay of the circuitry as well as this circuitry over here if your clock cycle is too short over here。

 you will get the wrong output in a given state。😡，Here， if your clock cycle is too short。

 you will change the state to a wrong state potentially or you may not change the state because you didn't give enough time for the circuit to actually。

😡，Finish evaluation and get its output latched in the state register。😡，Okay。

 now I introduced some timing into this right so far we've been very logical。

 but timing is really important in these。😡，Okay。Okay， so let's go over。

 we're going to see more of this。And we're going to see actually in timing and verification that it's really a sequential system that we're talking about。

 a sequential system beginning of the clock cycle， ending of the clock cycle there's some combinational logic and you have to accommodate the longest combinational logic delay if you cannot accommodate it divide the work into multiple different let's say clock cycles and we will see that when we talk about pipelining for example later on in the principles of design of micro architectureiture so I'm kind of getting ahead of myself but this all of this is actually will be building up to a micro architectureecture that processes instructions。

😊，And that instruction processing。Can be done in one single clock cycle， as we will see。

And we will see that that's very long clock cycle， so we're going to chop it into pieces such that your clock cycle can be shorter。

 but now you need to design a finite machine that processes instructions in appropriate manner in multiple clock cycles。

😡，So whatever we are going to see。And a few lectures is going to build directly on top of what we're seeing right now。

😡，Okay， so state encoding so we just assume some state encoding。

 how do you encode the states and then we just assume some output encoding。

 how do you encode the outputs。😡，So basically there are three common ways of encoding states with different tradeoffs。

 I will not go into a lot of tradeoffs over here since this is not a again logic synthesis or design optimization course but just to give you an idea there fully encoded it one0 encoded output encoded fully encode also means binary encoded so let's take a look at our Swiss traffic light again you can see that we have four states over here and this is a pictorial representation of it binary encoding full encoding means that use the minimum possible number of bits if you have four state in binary minimum possible number of bits is log two to the four and that's basically two right and then you can assign some encodings over here this minimize the number of flip flops that you have clearly but not necessarily the output logic or the next state logic so that's the tradeoff basically you minimize the state elements but now your combination logic may be bigger so there's a tradeoff over here which is interesting of course in the small circuit it may not matter that much but in large circuits this may actually matter。

Especially in large circuits with many， many， many states。If you think about a processor today。

 it has millions of states， maybe even much larger than millions that understatement， if you will。😡。

Okay， one hot encoding basically here each bit encodes a different state。

 you use the number of states a number of bits to represent the states so you have four bits basically in this particular case。

 and exactly one bit is hot or one for a given state。😡，So you can see that 0，0。

01 represents one state， 0，01，0， another state， 01，00， another state and 100，0 another state。😊。

So this is nice because this is very easily autoattable it's the simplest design process。

 you know exactly which bit is set for a given state unfortunately this maximizes the number of flip flos but as I said it minimizes it is actually very automattable as well it minimizes the next state logic so next state logic becomes much simpler right now。

😡，So theyre trade offs， as you can see。And the final ones output and quoting here outputs are directly accessible in the state end quoting。

 for example， if here we have three outputs right that's a light color we encode the state with three bits where each bit represents a color。

😊，So you can see001， bit 0 encodes the green and bit1 encodes yellow， this is010， that's yellow。

 and bit 2 encodes red， that's 100。And then there's another state that has both yellow and red。

 and that's endote as  one month0。😡，So in this case， outputs are directly accessible from the state。

 and this works nicely for more machines because more machines。😊，In more machines。

 outputs depend only on the state， not on the inputs。

 clearly if outputs depend on dependent on the input。

 you cannot do that right you cannot encode the outputs inside the state and quoting itself right。😡。

Okay， so this is also good to minimize the output logic， but as I said， it has some limitations。😡。

So next state logic is another issue over here， which we're not going to discuss so basically it's the job of the designer to carefully choose an encoding scheme to optimize design under given constraints again。

 automated synthesis tools do some of this， but if the circuit is very very large as we will see later on its designer actually is an important。

😊，Let's say participants in the process of optimization。Any questions？Okay。

 hopefully these are not too bad。So more versus mealli machines going back to more versus mealli let's design a couple of things again based on your book。

 this is just a reminder more output depends only on the current state and mealL output depends on the current state as well as the inputs。

😊，And your book as an example， how many people remember this example， the smiling snail。No one， Okay。

 some people， that's good。So basically you're designing， well。

 you're modeling in this particular of your case you're not designing the snail。

 you're modeling a snails brain， and the snail happens to be a somewhat intelligent snail。

 it's able to interpret the bits or digits that it crawls over and if it actually sees a sequence 1101。

😡，It basically smiles。😡，Magic， al right。Basically you're modeling the snail's brain。

 how do you do that， you could do it with a more FSM ormelia FSM。😡。

So basically if someone gives you this problem of modeling you design this is a state machine right the snail smiles only when it sees 1101 in a sequence and otherwise it doesn't smile so a smile is an output it's one only。

😡，In this particular state where you reach after seeing1101 right and then after that whatever you see brings you to the reset state so you have to have a reset state as you can see and here we have five states in the fifth state over here you know that you have seen one101 in sequence and then this state directly corresponds to the output smile and that's one every other state smile is zero meaning the snail doesn't smile and you can make sure that this works and it works。

😡，Mely FSM on the other hand looks like this， we didn't design this so far but I want to introduce you to this one also。

 but basically here you have four states only so it actually reduces the number of states as you can see。

 but reset is here， you have not seen anything assume that。😊，So if you've seen a one。

 the output is zero， the smile is zero so this is the input this is the output and you go to state one and state one basically says you have seen a one and you see another one。

 the output is still zero， you go to state two and you see a0。

 the output is still zero because you have seen the sequence of  one10 right now and that's what the state means and now if you see another one。

You go to this state？And。You output one so basically you can play tricks like this you can actually combine different states over here because your output is now independent well I independent or partially dependent on the state right partially depend on the previous state you were in and the input that was applied to the previous state so basically once you see one101 you're at this state and your output is one and then you can basically keep emulating what it does so I don't want to go through the details of this they still the state machine but you can see that there are some tradeoffs over here with merely Sms because the output is not solely a function of the state you can actually reduce the number of states but your output logic may become more complicated this way so again in big machines this may matter。

😡，Okay。So we may ask you to design finite state machines and actually you will do that in your labs。

 especially batunos maybe in the exam also this is not a difficult procedure as you've seen right with simple finite state machines it's not that hard you need to determine all possible states of the machine you need to develop a state transition diagram。

😊，And this is generally done from a description of what should happen。

 and clearly this should have everything inputs， outputs for each state as well as how to get from one state another and don't forget the reset reset is very important。

😡，And as I said over here。Yeah， I don't know if I want to go through all of these over here。

 but I will mention that this is building an FSM is kind of like programming， right？😡，Like。

 what do you done over here in modeling the brain of the snail is。😡。

Kind of if the input sequence is 1101， you output a1 right you can actually write a program that does this relatively easily except we're doing it as a sequence of states。

 not as a let's say program that you're used to。😡，So it is not programming basically。

 you're really designing a stateful system in the end。😡，And as I said。

 as I just mentioned gave you an example of it as a sequential control flow like a program with conditionals I go to。

 for example， if I'm in this state and if I've seen a digit one， I should go to this state。

 otherwise I should stay I should go to this other state for example right so basically you can actually express a finite state machine as a program。

😊，It's not that hard。Yeah， I thing I've said this if the else construct is controlled by one or more inputs and the outputs are controlled by the state or the inputs basically in hardware you typically have many such concurrent finite take machines and we're going to see that again next week。

 one of the finite state machines may decoding instructions another finite state machine may be controlling the execution of the instructions another finite state machine maybe be actually controlling what's happening in the accelerator over here another finite state machine may be controlling what's happening in the memoryme site another finite state machine may be controlling the SSD so you actually have a bunch of finite take machines that interact with each other and overall it's actually a huge finite take machine that you can model but。

You really normally build hierarchy of finite state machines when you build hardware because clearly designing a single finite state machine for everything that goes on concurrently is very difficult。

 right？😡，I mean， you can imagine again each of you as being finite state machines and you're interacting with each of you who are different finite state machines over here also right you could try to model everybody together in this room as a single finite state machine。

😊，You would be probably plucking your hair by the time you're in the middle of that or maybe five seconds into that。

 but it's a lot easier to actually describe each one of you as a different finite state machine that is interacting with others。

😊，Okay。Any questions？Okay so what is to come Basically we're gonna to see the finite state machine of this one I didn't show you over here but you can take a look this is going to be basically what we have done so far is build up the fundamental blocks starting from the transistor combination logic sequential logic we're going to see all of these basically you can see that there's some state element over here register file there's some memory over here input output there's a bunch of combination logic that we will see over here this is going to be a finite state machine we're going to design actually this LC3 processor that can process instructions from a small instruction set and you're going to do something like that in your labs as well and this is going to be the data path that we're going to see and build you can see some of the elements that we've seen so far multiplexs for example there's a decoder somewhere that's not shown over here but we're going to use everything that we have used so far you can actually see the tristate buffers over here and then there's a bus over here and these tri state buffers control what data value loaded gets loaded onto the bus。

Again， that's a teaser， we're not going to go into that right now。

But I think this schemes be a nice time to give you a 10 minute break。Does that sound good？

Let's take an early break right now and we'll be back in 10 minutes to start like Tier 5。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_5.png)

![](img/ca60c4d5aa3eb8571a442a7d418d47d8_6.png)

好了。啊，对对对。Okay。Okay， let's get us started again。这。那在家。Is everything going fine on Zoom， YouTube？Yeah。

We had some infrastructure issues， but things are。I guess under control， thanks to our great Ts。

Great。So I think this is also a kind of lecture that you guys have been waitingit for it。

I'm going to introduce you the labs and also provide some fjis。

I put Aberg's name actually here on purpose。Because he actually he's the main person for labs and he's leading labs。

 he's also attending this conference to present HBC conference， as I said， to present his paper。😊。

So yeah， but in general， if you have questions about das， you need to， I mean， you can， of course。

Come to me， but AtOre is the main person， essentially。Okay。

So we're going to say about logistics first。Our lab session。

 you know that is on site and we have four days， this information is already known for you so I'm not going to bore you。

And basically we have these times and also these rooms， just make sure that in Friday。

 the first session， we have different rooms。So， this should be。Easy for you to cover。

And the first session is going to be next week on Tuesday， so make sure you attend。

 I mean those people that are going to attend Tuesday session essentially。

And you know that you will work in groups of two， we had two options。

 which I think we are already aware of that， so things are already defined。

And every group we receive an F Fiji board to work with。

 so make sure that you attend the first week of the lab。

 I mean you should attend all the lab sessions， but first week is also important because you're going to get a FiG。

And please follow modules for details。De grading we have 10 labs and we have 30 points in total。

 so you know that 70 points is coming from your exam and 30 points is coming from your labs so with that we're going to have 100 points that is going to somehow scale to one to six。

So we will put the lab manuals online on our webage and this grading policy we have in class evaluation。

 like in lab sessions， evaluation which is 70% and mandatory lab reports， which is 30%。

And there are going to be one point penalty for late submission of the report。

 so you should finish the labs within one week after they are announced。

You can also use your grades for labs from past years， this， for example。

 the Moodle page for last year。We had actually， in the past， we had the students that， for example。

 in 2023， they wanted their lab grade from。2019， you know， so don't worry。

 we have database we can' fetch from， I don't know whenever you want。😊，Just let us know exactly。

 essentially。And for a question， you can email us using this basically mailing list。

 this will email send to all TAs essentially that we can and also we're going to have model for。

So what we will learn in these lab sessions， we're going to see about this transformation hierarchy and we're going to understand this software hardware interface。

 micro architectureitecture and logic specifically labs。So。

 and how to maketeros between performance and area complexity in your hardware implementation。

 there are hands on experience on hardware prototyping using FJs。

And debugging your hardware implementation， using hardware description language HDL。

 which specifically we're going to see very large how to use it and this hardware design flow as well as computer aidD design tools short as CA tools。

So what is an FGA， ages state stands for field programmable G array。😊，This is one example of Fiji。

 there are many， many different examples also in the market in the world。

 you can see if Fiji is a software reconfigurable hardware substrate that makes a Fiji so exciting because there is a chip。

😊，But that chip is not hard coded， essentially， so you can implement。

kindind of any circuit as long as your circuit can fit in that fJ because each fJ has limitation in the number of lookup tables。

 number of I don't know flipfls， multiplex， whatever， so each fJ has a limit。

 but within that limit it can implement everything that you want。😊。

So this has reconfigurable functions， reconfigurable interconnection of function， which is very。

 very important and we're going to see a bit why， but you have a lot of switch boxes。

 you have a lot of switches that they call switch box connection box and all these switches can be reconfigured in order to connect a logic block to another logic block。

Which is very important for FPG to implement your circuit。

And also we have reconfigurable input and outputs in a friji。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_8.png)

So you have already seen this slide from Professor Motu's lecture that essentially we have this flexibility from CPUs。

And this is quite programming ease， but as we go through this basically spectrum。

 you're going to see more efficiency， but at the same time you might have basically less programability。

 so if fidges is they are standing kind of in middle between completely see A6 and also something else after GPUs that they are accelerators。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_10.png)

So we have a fidges in today's system， these are some slides that I just want to motivate that a fiji that you're going to use。

 not exactly the fiji that you're going to use， but the concept。

Is very useful and many systems are actually using a Fiji modern Fiji。

 this is one example in that use for deep learning platform for a Fiji。😊。

And this also from another system that they use a Fiji to solve complex science， engineering。

 business problems that require high bandwidth， enhanced networking and very high compute capabilities。

There's also another fG use for DNA sequencing， which is important for genome analysis bioinformatics。

 you may know when you want to that can actually provide a lot of applications including。

Personalized medicine to also you know to。limimit I mean mitigate this outbreak of our disease。

 so all these are important in genome analysis and DNA sequence is also one of the very。

 very early step of that， so effiggs are very useful for that as well。And have also in our group。

 we have used FJs in many of our studies， these two papers， gatekeeper and sneaky snake。

 both of them are actually a FiJ based accelerators for bioinformatic applications。

And you can learn more about it by checking this paper。

 we also use basically f fidges for other applications， again this also basic colors is for genomics。

 we also use a Fiji for weather prediction， stencil applications。

 so these are different applications that essentially you can use a Fiji to accelerate them。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_12.png)

You don't need to know all details， of course about them。

 just these slides are here just to motivate you to say see that how a freeger can be useful to improve performance。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_14.png)

![](img/ca60c4d5aa3eb8571a442a7d418d47d8_15.png)

In our group we actually we have developed a system called in the past we were calling it SotC。

 but we actually extended much more and we improve it and now the name is actually Diham Bennder Atic is the leader for this project actually。

 so that's why he's also your HTA in this labs。So this is an open source F FiJ based infrastructure to experimental studies on DRAM。

 so you can actually do a lot of studies on D wherere using this D vendor， which is kind of。

 for example you can play with all timings of your D your commands that you can you're sending to D and that can help you to understand many of hidden stuff in your D and also design techniques in order to benefit from functionalities that they are actually already available in D but people may not be aware of that。

So for example， in one of our work， recent work we show that commodity of the shelf of DM chips。

 they are capable of doing computation， they are already capable of doing functionally complete Boolean logic so you know what is functionally complete right so you can implement N nor and or and not operations using commercially off the shelf DM chips so that's what we for example got from this Dm Bennder system。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_17.png)

So you can also if you're interested， you can check So DeC and Dam Bennder on our Github page is already completely released。

And this is also the paper if you want to learn more about it。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_19.png)

Its also one of a picture from this system you can check。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_21.png)

And thiss also this Rou hammer study that。The first paper that we publish in this area that we show that essentially by opening and closing or activating and deactivating a row in a D row multiple times。

Or let's say fast enough you can actually cause errors in adjacent or neighboring growth in Dran so that's a phenomena we called it I mean they called it as Rohammer it's called as Rouhammer that basically breaks one of the main importance like this isolation principle of Dran chips so you can actually by activating and deactivating one Dra row you can cause errors and later works they use this phenomena to actually design attacks security attacks so this is Rohammer that you probably know about it because from Professor Mulu's talk。

But basically， we use our system to have lot more deeper look in Ro hammerir and also uncover a lot of stuff about Ro hammerir。

As well as one of the techniques that's basically industry provided and they taught they actually claimed that this solved the problem。

 Rohir， but later on with this work and other works we showed that this is not the case。So yeah。

 essentially you can use this kind of Dam Bennder infrastructure surgery to do a lot of studies。

There's also another work that we published in 2023 that we show that actually that there is also another phenomenon called ropepress。

 we actually call it ropepress that if you keep one row in the D active for a long time。

That can actually cause errors in neighboring roles。

 so we call it row press and we also again use Dham blender。You can for example。

 generate random numbers inside your DRA and random numbers are important for many。

 many applications， so we get to this generation of random numbers in DM using this DR vendor infrastructure。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_23.png)

Okay， so I don't want to bore you more， but this kind of infrastructure also can be used for other memories。

 for example this one is for characterization of flash memories and it's actually from quite past in 2012 until 2018 or so that we had this kind of infrastructure that we studied flash memories and we uncover a lot of reliability issues as well as mediatigation techniques for all these reliability issues in the flash memories of that time essentially。

😊。

![](img/ca60c4d5aa3eb8571a442a7d418d47d8_25.png)

If you want to learn more also about flash memories like this error characterization of flash。

 I would recommend you check this paper， flash memories are really exciting。

Is actually one of the very， I would say。Nice， listen。For every researcher。

Because when people were working on flash memories in 1990 or so。

So flash memories are way behind of their performance back then。

 and many there were many people there me say that while you're working on this kind of technology。

 this is not going to work at all。And but now you can see that those people were completely wrong。

 so you had to actually work on these emerging memory technologies to make them possible that can actually change many people's life and now the main reason that for example we have a smartphones is flash memory otherwise you could not for example have a hard disk drive in your smartphone you know and then gets you that rotate in your pocket to have your memory essentially。

 so it's very interesting to see why we need to work on emerging memory technologies。😊，Okay。

You can also use FJs aot for prototyping， this one example that we design a prototype in order to use processing using DN。

 so we showed that for example， we can have the holistic end to an FPJ based framework for processing in DN that you use your Dm in order to do computation。

You may not know completely what does it mean exactly。

 but essentially you are using your Dm to do computation and this p you can actually implement them in a prototype。

 the whole system is closed， you can see you can implement the whole system essentially。😊，Okay。

And these are also for another work meta， and you can see that at work。Here， this guy。

 he got this paper of art at HighP for his work。Okay， so let's have an overview of our lab exercises。

 any questions， by David？

![](img/ca60c4d5aa3eb8571a442a7d418d47d8_27.png)

Good， so this is our FJ board basis three。😊，U。This is actually is not a badboard。

 I mean it's quite capable but of course it's not you know as capable as modern refugeGs that people use。

 but you can learn a lot of fundamental things about these FGs so there are many actually stuff going on these a you have USB connection。

 you have video out VGA， you have micro USB， you have power switch， you have seven segment displays。

 these are a lot of LED that you have you have switches that you can control use them as an input for example。

 you have push buttons。And this is your refugeeship。This shows that when you want to design a system。

 the brain actually usually is so small and there are many。

 many things going on around it to make interface and that's why actually interfaces are actually very expensive in the computer system。

😊。

![](img/ca60c4d5aa3eb8571a442a7d418d47d8_29.png)

Okay， so at the end of exercises， we will have built a 32 bit microprocessor running on the FiJV。

So it will be a small processor， but it will be able to execute pretty much any program。

 so I think this is very exciting that we will learn how to design a microprocessor and each week we will have a new exercise that in the end will guide you to that microprocessor essentially。

So you're also encouraged to experiment with the board on your own。

 we may have some extra boards for those who are interested， unlikely I would emphasize on that。

 but you can ask of first when we see。And it's not possible to destroy the board by programming。

 so don't worry。Okay。So in lab one， we're going to draw a basic circuit it's going to be about comparison。

So you just need to draw a schematic of that circuit and we don't have a FiJ programming involved in lab one。

But we encourage you to do it later when you have understanding of FVJs。

In La2 we want to map our first circuit to PG， we're going to start with Ed。

 which is very simple and we design a circuit that adds two one bit numbers which is going to be a full add and then we reuse this one bit full add in order to make four bit addition。

And essentially you need to implement design a Fiji board and use input switches that I showed in that picture there are some switches that you can use as the input to the Fiji and also the output of the Fiji goes to LEDs so you can see the output on those LEDs based on the lights that they are lighting。

In La3， you're going to use actually seven segments in order to show the result of La two essentially。

 so that's training you how to design a combination of circuits for refugees。In La four。

 we're going to finite thete machine that we design these blinking LEDs for a card term signals。

And this implement and basic implementation and use memories because kind of a sequential circuits。

And also， we should be able to change the blinking speed。

 so you're going to see in your lab material essentially。In La five。

 we're going to see how to implement an ALU。And that's actually the first kind of step in order to get to your processor。

 so you will design your railU that can do some arithmetic operations like addition， subtract。

 multiply comp， and some logical operations like and orN so on and so forth。

Then in La6 we're going to test our value basically whenever you design you need to verify it and that's the verification part that you need to design kind of test page to simulate your design and in La6 the focus is to teach you how to simulate and test the functionality essentially。

 so well learn how to debug your implementation and to resolve problems essentially。In La seven。

 we' are going to write an assembly code for the microprocessor that we are looking for。

 we will use the MIPS and that implement a program which you will later use to run on your processor。

Which it sounds quite exciting， at least to me。In lab 8。

 we will use we will basically make this full system integration will that this will be cover in two weeks。

 so essentially。We have 10 labs， but La8 is actually kind of two laps。So we have La 81 and La 82。

 essentially。And then we learn how a processor is built and we will complete your first design of a MIPS processor and we run a snake program on it。

 for example， like this。Okay。And in La9， we analyze the performance of the processor that we design and how we can improve the performance by adding some other instructions like multiplication。

 bit shifting and so on so forth。Okay。So that's all， but you can see the material for every lab。

 you will put it on website， you will check it， I encourage you to check it early enough and you attend a lab session by kind of you know prepare mind as much as possible。

😊，Okay， let we also provide a bit more detail about Es。

 so what is an FJ we already know that it stands for field programr G array。😊，And you know。

 this is stuff。So this is a high level overview of eigs that we need to configure logic blocks。

 so all these。Rectangle square， let's see。They are kind of logic blocks that you need to configure them in order to implement some functions。

 and then you need to configure also these switch boxes。Or switch blocks。

 essentially in order to make connection of these circuits。And then you have some oil blocks。

And basically that you can use them， you can again also configure them in order to see the output like when you check the data sheet of fig。

 you know that you're going to see that， for example， some of these。These are go paths。

They are connected to some of some outputs in your board。

 like some of them are connected to seven segments， some of them are connected to， for example， LED。

 some of them are to switches， so you can actually configure them nicely。

There are two main busy blocks in Effvis lookup tables and switches。And I guess， I mean。

 you already know about lookup tables， it's a memory that you can implement like when you have LUT of three input。

You can essentially implement any tree input function using data。So。

 and then also you have switches that you can configure them in order to make connections。

 essentially。So this is a three bit input Lity that you provide one output， one bit output。

 and it can implement any three input function， as you know。So this stuff I think。

 is already familiar for you from the lectures Professor Motulu。

And then essentially you can combine these LUTs in order to this is still tree input。

 but how to implement complex function we fi are composed of many LUTs and switches。So。

 in the end the。Yeah， this， for example， is a fiji chip and this a small dot is actually this for example。

 so you have a lot of these。😊，And then you need to basically combine all these LUTs to create bigger function。

 for example， if you have three input LUs。And your function is for input。

So you can think of how many three input Ed you need to use in order to make your four input。

Function。Think about it。But yeah， so modern and figer architecture。

 they typically use elus with six bit， so they are six elus and we have thousands of them。😊。

And we have megabytes of distributed on chip memory that all these on chip memory are essentially used to configure。

LUTs and also switch boxes so whenever for example you want to configure this switch box。

 for example here to connect this wire to this wire you need to somehow configure it and there are small memories that you can actually configure each of them using a bit stream and that makes that connection happen essentially。

So yeah， exactly this is。😊，For any memory but at the same time for better efficiency。

 f FiJ also has some hard coded special purpose hardware blocks for example multiplers are usually very expensive and if you want to implement multiplers with LUTs their performance it might not be good so there might be some as special special purpose hardware blocks for multiplplayers and whenever for example you have a multiplplayer in your design you just use that for example basically F fiji they might actually have they might have also processor so there might be some microprocessor on your fPJ chip or also decide your fji chip。

Yeah， exactly， even a general papers processor can be embedded within the fridgeji。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_31.png)

She。And this is an example of modern refger platforms zing as zc ultral skill+。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_33.png)

And again， this kind of advantage and disadvantage of fijis that you know essentially， as advantages。

 we can say that an algorithm can be implemented directly in hardware and we have high specialization。

 high performance and high energy efficiency。

![](img/ca60c4d5aa3eb8571a442a7d418d47d8_35.png)

We have low development cost， of course， compared to custom hardware design， which is AC for example。

 and we have short time to market。And usable and reable for many purposes。

 so that's why FJs are quite useful and widely accepted， but of course they also have disadvantages。

 so they are not as fast and power efficient as dedicated hardware customized for an algorithm。

And reconfigurability comes at a cost significant area and latency overhead as well as I would say reliability overhead us also so there are all these switch blocks and you are controlling all these with some memories so if something happened in that memory。

 for example，10 goes to one or the other way around then the whole circuit is just can be wrong right so there are a lot of reliability issues that also can happen in a fijis as well as other circuits but that's also one of very important things to know about the fis Yes。

 so the latency。Usually still faster to run。on general诶。I would say usually yes， yeah。

 that's usually the case specifically because on a general purpose person you have。😊。

This sequential program so there is this stuff that I mean even though you can also have some parallel programming but still there is a program that there are a lot of sequential instructions that you need to go over than 101 but if fidges are kind of they are assembling hardware which has a lot of concurrency so that's why in general their performance is much better but at the same time they comes at the cost of。

S that I mentioned and also their performance is not as good as AsIC and custom devices。

Very good question。Yes。😊，But if you already have some sort of， for example。老人。

Some some specific part of the' some Yes， it's anJ still because can kind of adapt algorithm No， no。

 probably no， yeah， usually so yeah， I mean， that setting actually。

 today's systems are actually heterogeneous。And they are using general purpose course。

 they are using GPUs in GPUs they also have tensor core that kind of customize for that application。

 so actually today's system are combining all these difference basically platforms so in a modern system we have CPUUs actually this is also as Professor Muso also mentioned this shows am Apple M1 chip which has actually has GPUs。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_37.png)

Has also general purpose course， a Fijis， maybe not a FiJ， but many other accel。

 so basically today's season we're combining all these。

And that's why because we need there are not many， not every application can be accelerated in either of them。

 so you need to benefit from the all these things together be， essentially， Yeah， any other question。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_39.png)

Okay， great。So to program an Eia we are using computer aid design or CAD tools。

 Es have many resources， LUT and switches， and they are hard to program manually， of course。

 so it's going to be very headache if you want to do that。

So how can we represent a high level functional description of our hardware record using the FJ resources？

And then we need to select the resources to map our circuit tool and then optimally configure the interconnect between the selected resources and generate the final configuration file to properly configure NFJ so if we don't have cat we need to do everything manually。

 but luckily we have cat tools that we have this program problem definition and then we use kind of hardware description language like very log and BHD which're going to see in a bit so that's your job or our job but after that we would use cat toolss so there is this logic synthesize that synthesize your very log programming essentially to logics。

And then there is this placement and routing to place your logics on all these FPJ configuration blocks and then how to route them by configuring all these switch blocks。

And then after placement and ro we will get to this BT stream generation that essentially that BT stream needs to flow to your refugee and configure every single AUTs and memory that you have on your refugee so after happening after these BT stream generation and that communication you're going to have your circuit on your refugee essentially。

 and that is automated luckily fortunately with different tools。

 but in this course we're going to use the links realal tools。😊。

So Vivada is a software tool that helps us throw out a Fiji design flow and this tools provides tools to simulate also our design to validate the correctness of the implementation。

 debugging and many other things also。Weva also provide drivers and graphical interface to easily program the feature using a USB cable。

And is this application already installed in computer rooms in our lab rooms essentially？

So you can also check basically tutorial of this rivado using this。Basically， video。

 I'm not going to play it now so you can play it at home。Apparently you。I'm supposed to play。

 but yeah。I would the。Okay， so keep in mind that you do not need to install water on your laptop。

 I mean you can do it if you want， but lab pieces already have it installed。

And please do not have Ph to grade your labs outside of lab hours。

And stopping your lab files in the correct format， so the format is already specified in your lab manuals。

And please double check your uploaded files and do not incorrectly submit， you know。

Because that can cause zero points for you。And double check your grades， essentially。

So when we want to find larger grid， we will send an email to remind you。

 but very important that we check your lab grades back by then and let us know if something is missing and then we can fix that problem in time。

 hopefully okay。😊，So that brings me to the end of this lecture。

 but I want to also talk a bit start at least very luck very quickly。

Just to give you some foot for thought and then we're going to continue very look next week。

 we have 12 minutes。😊。

![](img/ca60c4d5aa3eb8571a442a7d418d47d8_41.png)

Of course we cannot cover this lecture， but we're going to see a little bit about this。😊，So yeah。

 this is the agenda for not today much， but anyway， we will basically we're going to get to。

 we want to get to this processor next week and the weeks， I guess after how to design a processor。😊。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_43.png)

But now let's also quickly talk about Harvard description language and verylock first I want to use some pictures to motivate why we need that。

So， this is a。The chip in 2017 which was one of the strongest chip back then。And it had。1。

75 billion transistors。So people were kind kind of you know what we're going to do when we have billions of transistors and nowa is actually we are way away from that。

So in about 47 years， we have basically one million fold growth in transistor count performance。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_45.png)

This is also another chip in 2021， which has 16 billion transistors。

This chip is in Apple Mbon Ultra in 2022 that has 114 billion transit stores， which。

You can see that it's growing and growing so of course it's not easy to configure every single transistor you know by our own so that's why we need some you know tools for that this also surplus in 2019 that has 1。

2 trillion transistors and largest GP back then had 21。1 billion transistors。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_47.png)

And another version of Cbraus wave scale aging 2 has 2。6 triuter transistors。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_49.png)

And also we also checked what Iippedia says about it and as I expected。

 memories are actually having way more transistors， so like flash memory in 2022 has 5。

3 trillion transistors。Or for example。😊，Yeah， GPUs in 2022 has had 18 billion transor。

 so you can actually see that here is also very important。So the D includes about。12。Quarter。

Qudrillium yeah thousands of basically triion transistor and that's about 97% of the old transistors so that shows actually that most of our systems transistor are actually spending on memories so。

Make sure that you always meize that that basically memories are actually very。

 very expensive in terms of number of transistors。Okay。

 so how to deal with this complexity we are using hardware description languages and what we need for hardware design that provides ability to describe and specify complex designs and to simulate their behavior。

 functional timing and to synthesize using automatically design as we showed like Vialdo as a CA tool。

 basically。So hardware description languages enabled all the above。

 and they are designed for basically describe hardware and we have different version of it。

They called it as HDLs， but very like VHDL are the most common HDLs。

People actually both of them are useful。But in this course， we're going to learn about very luck。😊。

And of course， if you learn one， it's not hard to learn another one。Okay， so as I said。

 there are two went on HDS， very large。And we year here we provide some history about it that you can check if you're interested。

But that's not the most exciting thing that we can bring from this course。

Okay so why specialized languages for hardware so HDLs enable easy description of hardware structures so specifically you can also you can think of using why not using for example seek programming you know to specify hardware the reason is that I mean HDLs are customize for hardware and in hardwares we have some basically components。

Like we have wires， gates， registers， flipopps， clock， rising， falling edge。

 and all these basically components or specification that they are not necessarily provided in sequential programming like the C++ for example。

So that's one reason another reason also is to enable basically parallels so in hardware we have a lot of concurrency so every single actually all these transistors。

 all gates they are actually operating in parallel so there is no sequential thing happening in your design so that's why actually if you want to model your hardware using for example C program or using Python is going to be very headache because it's very hard to simulate that parallels and that's why actually why our simulators that people develop for example simulator for GPU using C++ these simulators are very hard to design and also they are really slow because so they need to actually simulate all these complexity and all these concurrency that we have in the hardware which is not the easy thing to do so HDDLs enable that and all hardware logics can operate concurrently in HDDLs。

😊，And both of the above is a specification， simulation and synthesis for your heart failure。So HDLs。

 basically we have some key design principle that we should consider。

 we have this hierarchical design that we always need to design a hierarchy of modules for our system。

So in a complex circuit， you actually。You can see that there are many blocks。

 but each block actually can be a city structure， but many， many gates。So we use some predefined。

 we call them primitive gates like an and or， these are actually some kind of leaves in your hierarchical design that you don't need to go below。

 yes。The three that。Yes， yeah。And simple modules are built by instantiating these gates。

 like components like multiplexer， so we're going to see more about it later。

So basically you need to make a hierarchy of your design so you can have a top down approach that we're going to see in a bit or bottom up approach to design your big system。

 so top down approach you have a top level module which for example your top level module is let's say microprocessor。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_51.png)

But then you're gonna say okay my microprocessor would have some submods and then you need to design each of these submods but each sub moduleule also can have some sub modules and then you're gonna to get to some leaves and these leaves are actually are primitives the one that you don't want to go below of that for example。

 in very low you can say that okay my gates are those leaves you may design you may combine some gates and make some bigger logics like for example add multiplayers and then you may consider add or multiplayers or these arithmetic units as your leaves essentially but anyway there should be they're gonna to be some instance that you don't want to go below of that and these kind of top level methodology that you might have you can also think of bottom up design methodology that you first identify the building blocks that are available to you or to us and then we build bigger modules using these building blocks and these modules are then used for higher level modules until we build the。

Top level module in the design。 So， so you can also grow the other variable。

And I should acknowledge that in our system， so as a designer， whenever you want to design system。

 you actually need to use combination of boths， so you need to have kind of top down approach。😊。

First， because you should be motivated to what you want to give。

 but then when you want to implement you usually use the bottom up approach so you design your I mean you make this hierarchy using top1 approach。

 but from the implementation wise usually go bottom up。😊。

So in order to define a module in very large。So module is the main building block in verylock that's a notation。

 we first need to define the name of that module and directions of its ports like input and output so this is an example module that we have and it has three inputs ABC and output y and then we want to describe the functionality of this module essentially。

So this is the example， very low quote for that。😊，You start with defined definition of the module。

 you say these are keys， essentially module， and then the name of module， which is example。

And then you have these port list， ABC and y these are ports and then basically you need to define which of them is input。

 which of them is output so here for example， ABC are inputs and why is your output。

And then basically this part， you need to specify the functionality of that module。

 and in the end you have this end module which close your block。

And also you can also have different style so these two definition both are correct so here you say that module for example test a B by and then you say input a input B output y you can also say module test input a input B and output y so both are correct and it depends on your style the way that you want to write。

So what if we have multi bit input and output， we can use define using this kind of range。

 so you put range end and arrange a start。And that shows the number of beats you have。

 so number of beats is actually range n mind the range is star plus one example。

 so for example here you have input 31 to 0 a that means that actually a is actually a value which is 32 beat。

And then you can specify every single bit of a using this notation， A31， A30， a0。

 and so on and so forth。You can also do， for example， this B one you don't need to put zero always。

 you can say that for example， output 15 to8 B1。And this basically B1 has 15 until B18， essentially。

This is also another example7 to zero， and you can see。And you can also have this input C。

 which is single bit signal。So here， when you say 31 to0， actually it represents a3 a 32 bit value。

 so we prefer actually to define it as is， but you can。All you can also define it as 0 to 31 a。

 but that's not very common to use when you want to design define a multi bit value。

 you usually use this kind of notation，0 to 31 when you want to resemble kind of array definition。

 so you have array and you want to define every bit of it。Okay。

 so and it's also good to be consistent with our representation multi bit signals always we can use this kind of notation and for whenever you want to design define an area you use this kind of notation okay I think it's a good place to stop we will continue very luck next week have a nice weekend。



![](img/ca60c4d5aa3eb8571a442a7d418d47d8_53.png)