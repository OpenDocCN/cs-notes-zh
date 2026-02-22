# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p05 -05- L4_ Sequential Logic II, Labs, Verilog (Spring 2025).zh_en -BV1iV1XBWEJW_p5-

This you should not violate quality of service， I mean if it's important。

 so in this case this is actually important， you it's important that you provide fairness and quality of service。



![](img/d14fb3afe8d5ec668fee5df1dca90851_1.png)

So once if you keep traffic in Avenue A and this is green。This is going to be always green。

And this avenue B is not going to be green at all， which you're going to make people here crazy essentially so that's cause unfairness and this is very important that when you design system you should make sure quality of service and fairnness in any kind of scheduling techniques that we're going to also see a lot in this course when we discuss about memory controller。

 memory and other kinds of controllers okay。But that's kind of the site here。

 this is the description that your book once。😊，So yeah this can be a black box of your traffic light controller that you have T and TB as input and these are output LA and LB and we have also clock input and reset so don't forget about reset there should be always a reset signal for your controller in order to say that okay I'm going to start from this estate so there should be kind of initial estate for your FSM that you start from that。

By the way， did we resolve the problem in YouTube screen。Can you help and start this speech？

So this is also the problem in Zoom， yes。

![](img/d14fb3afe8d5ec668fee5df1dca90851_3.png)

Yeah， just stuff and start。

![](img/d14fb3afe8d5ec668fee5df1dca90851_5.png)

This one。I think that is great now I should do it。Yeah。Okay。Yes。So， now， let's。

There are all the FSM for this controller。So we want to design it more。

 you can actually also do it Mill as a homework if you're interested。

 but more FSM is actually very easy for these kind of examples。

 so we have state zero that we consider this is an initial estate this kind of prioritization that you consider that whenever you reset you start from S0 and in this S0 you consider that output basically the light for Avenue A is green and the light for Avenue B is red this is your state zero。

So as long as we have traffic in A。We're going to stay in this estate that's the smartness part of our controller and when there is no traffic we after five seconds we move to state1 and in state1 basically we make LA yellow and the other one is a seal red then from S1 unconditionally we move to S2 after some time。

And then in S2， we're going to make light for a red and the other one should be green。

And then we need to a state in this estate until as long as we have traffic in Avenue B。😊。

When there is no traffic， we move to a state tree then it's going to again kind of intermediate a state that we make a delight light for Avenue be yellow。

 the other one should be a steel red。And unconditionally， after some time， we move to S0。

This is so easy， right？Any question。Good。So this is， of course， more referM because your output。

Can be specified only by this state。So whenever you see a FSM and you see that outputs are specified internally inside each state。

 that actually is a very good sign that this is a more machine， essentially。Okay。

So now let's see how we can make a circuit， like implement these FSM in hardware essentially。

 so first we need to start with transition table， so we have a current estate and also inputs depending on these inputs we can move to different estate。

Okay。So from S0。If。Traffic A is zero。No matter regardless of traffic B。

 we need to move to basically S1 right so when it is zero。Traffic B is actually don't care here。

So this actually true St is already also considering some kind of simplification because。

I mean you could repeat oh， you can say that okay0，0，01 for example。

 but you know that when you are in state0， the status of Avenue B is not important for you。

 so you can already put X here which shows a don't care situation。

So you move to S1 after that and when youre S0。And you still have traffic in a。

 you want to stay in a zero so nextus they should be a zero when you are in S1。

 no regardless of traffic in A and B， you just go to S2。And when youre in S2 again。

 regardless of traffic A， but if you don't have traffic in B in B you go to S3 and when you're in S2。

 you basically staying in S2 if you have traffic in B and again when you are in S3。

 you just go to S0， so this is the next state which shows you the combinational circuit the combination of circuit needs to generate these output essentially depend based on these current state and also these inputs。

So now we need to somehow encode our estate， this is one encoding。

 so we have four states here and we can encode them with 0001，1011。

We're going to see also other kinds of encoding in a bit。

But this is one kind of encoding that basically it ensures that you use。

Less number of flip flos essentially， because for this。

 you can only so your register needs to have only two flip flos essentially。

Then you can using this encoding， you can actually move it to this true table。

 and then you can have S prime1 and S prime0， and then you can actually make it more clear essentially。

 so from S0 we want to in this status we want to go to S1。

 which meaning that next state should be 01。Now you need to basically write a equation for each of these outputs。

 so for S prime1， we know that from this current estate。

So we need to check what are ones right so basically we know that we go so this should be one when S1 is0。

And S0 is1， regardless of T and TB， so this is one of them S1 prime。Times a0 and a zero or。

This state。Which is not a statistical combination of inputs。Which is 1，0 x0。 So it's going to be S1。

S0 prime and also TBb prime。Or this line， which is S1 S0 prime and TBb， right？

So this is S prime1 and also for S prime0， you can again also see only right equation for the bonds。

 you already know that from SOP like some of the product。So and then if you can also easily write it。

Any question？So this shows actually the combinational circuit that you need to have in order to provide S prime 1 and S prime zero。

 and this is going to be the input for your next essentially。

So then you can also simplify it S prime one， if you check。

 you can see that we can simplify these too。To S1 and S0 prime。

 and then it's going to be S1 prime and S0 or S1 and S0 prime。

 which and again is going to be x or so you can simplify s prime1 to S1 x or s0。

But S prime zero is already simplified。Christian。Okay， of good。

Now we need to do the similar stuff for output here actually output is very easy because it's a mood machine。

 so whenever it's more you can easily generate output based on the state。

 so our true stable is only related to the state， we have essentially for state that we encoded them with two bits。

😊，So we have 00011011， and for each of them we need to define the output for LB。

 LA and LB so in S0 we know that it should be green。

 the light for Avenue A and the other one should be red and so on and so forth。

Then you need to encode output， so for green， for example， we encode it to00， yellow。

01 and red on zero then。You need to basically you know add this encoding here。

 so each of these green like LA is going to be two bits， so this is LA1 LA0 and LB1 and LB0。

And then basically based on this current state， you need to write these values。

And then you need to write equation。 So for each of them for LA1， basically。

 we know that it is one only。I mean in these two lines， which S1 is1 and regardless of S0。

 so it's going to be LA1 is equals to S1 essentially。LA0 is only1 when we have S1，0 and S01。

 so it's going to be S1 prime times S0。And so on and so forth for LB1 and LB0。嗯。Is that clear？Yes。

S and S0Yeah so S1 and S0 is actually the encoding of our states so we have four states right S0 S1 S2 and S3 so when you want to encode them you use two bits for them。

S underscore one， this is not difference between this one and that is kind of underscore so S1 is the most significant bit of that estate and S underscore0 is actually the least significant bit of that so you are using these two bits in order to show your estate essentially。

😊，Yes。😊，So。你 to anyone what to calling to use the。Craience。

 only the questions that we have for the super hard right。

So like we just have to if you want the most simple form of equation， we just have to try out。

So there are actually some automatic way to simplify， I mean。

 Caral map is actually one of them that we haven't covered like in this course。

 Car map is actually quite fun and it can be useful for circuits that they they have input up to either five or six。

Yes。Oh okay， you are talking about encoding Okay， yeah yeah， yeah， exactly。

 we're going to actually have a slide about encoding。😊。

And encoding actually affect the simplicity of your design and there is actually a trade off between the number of flip flos that you are using and also the simplification of the equation。

 so it's actually a designer job to decide which encoding is the best。

For this one here is an just example we are considering this encoding without any discussion。

 but we're going to also see trade off leaders so that's a great question yeah。😊，Any other question？

Okay， good。I guess we are not a still good in YouTube。It long as the dining of screen。

Let's make it do its in break， right。跟因为多呢。Everything else。Just change the。

I don't know why if we have problems today。好什没。Oh。自己。我。他啊。ますね。It是什么。Yeah。Yeah。我怎。Can yet fix the。

Okay。使いま。Okay。Yeah， let's continue。So this is also the FSM output that we provided now let's see the schematic of this FSM。

So this is going to be the circuit that we are looking for。

 the combinational circuit for the to generate the next state。

 the combinational circuit to generate the outputs and also our estate register。

So this is the schematic for our state register we use we encode our states into two bits。

 so essentially we have this register that has only two bits， which easy。



![](img/d14fb3afe8d5ec668fee5df1dca90851_7.png)

And then we need a schematic for。

![](img/d14fb3afe8d5ec668fee5df1dca90851_9.png)

This is really annoying， I don't know what's happening today。Okay。没得问题。

Okay so to generate the next state so that was the circuit that we had right so we know that S prime 1 is s1 x or a0 so we have this x or gate here and this is also the circuit for S prime zero so you can you know write you know draw this schematic for this circuit so that's the combinational circuit that we have to generate the next state signals and also we need to add the combination of circuits for outputs these are our equations for LA1 to LB0 and we just you know draw the gates here and this essentially is going to be your full circuit。

Any question？Okay， good。So let's also quickly check the timing diagram's going we're going to actually look into timing with a lot of details next week。

 but today just to prepare you for that first of all we have this is basically the the signals that we have。

So if we consider this there are this clock reset and T and TBB， these are the inputs。

And also we have some kind of outputs here， so this S prime1 to0 is actually your next estate。

And S10 is going to be your current estate， which is already stored in your estate register。

 and these are your outputs essentially。So the reset signal that we are considering here is actually asynchronous。

 so if you think about it， we discussed about synchronous and asynchronous circuits right yesterday。

So this FSM that we are considering here is actually mostly synchronous because it works with clock。

😊，But reset signal is asynchronous， meaning that whenever you just triggers reset。

 you're going to reset the whole system， so for reset you don't wait for clock cycle and that's actually usually the case for many of our circuits today because。

Reset signal actually comes with a lot of priority and sometimes with some safety reason so whenever people wants to reset they don't want to basically waitit you know for any few nanosecond or even lower so they just want to immediately reset the system so that's why basically people usually use asynchronous reset we're going to see how we can actually make a synchronous reset in very luck that we're going to cover today and next week but this is something to just prepare your mind for that。

So that's why you can see that when we basically kind of assert the reset signal or activate the reset signal。

This。S prime 10， actually， sorry， the corner of the state emit after some delay gets to zero。

So it doesn't wait for the clock signal you can actually see that here we consider some delay so that's actually the case in real life first of all clock signals are not that sharp they are usually like this so there is a rising age which is not completely sharp the same thing for reset for other inputs so usually they are kind there is a delay until they get to the high value。

And also after seeing some each of these basically values there are going to be some delay in order to get to the value that you're looking for so here after seeing this reset you can see that after some delay we get to the S zero and。

This combinational circuit， also the input for S prime 10 also get to S0 after some time。

And these are also the outputs that we have， but that also withs some D essentially。

So this one is first， after some delay we get to this and also some delay to green and red red。

So you can actually also continue that。Let me see yeah。

 at this stage that you basically pull down the traffic a。有。Yeah， this happened in this。Exactly。

Yeah here you don't have traffic a anymore， so this combinational circuit that you have says that okay。

 next state should be S1。But that happens in the clock H， essentially。

 so the next state in your state register will happen as one in this clocks in this edge。And also。

 when it is S1 after some time this current estate， I mean， next estate should be S2。

That's why we have delay here and then after we wait in S2 and then in this rising edge we went to the current estate going to be S2 and you can continue that for other。

Basically， cases。But we're going to look into delays and timing a lot next week。

 so if you don't understand everything here， don't worry about it。Question。够诉。

So let's get to this encoding that one of your colleagues also asked。

So how do we encode the state bes there are three common state binary encod with different trades one is fully encoded and the other one is one hot encoded and output encoded so let's see an example traffic light with four statess green yellow red and also yellow plus red。

Yeah， so this is our Swiss traffic line。So essentially we have forest states and now we want to encode them。

With binary encoding or full encoding will we use the minimum possible number of beats essentially。

 which is use the lo two of number of estates beats to represent this state so here we have four estates。

That means we need two bits to encode them so that minimizes the number of flip flos but not necessarily output logic or next state logic so here is a tradeoff that you can assume with 100 encoding each bit encodes a different estate so we use number of beats to represent that say we have four estates in this example we consider four bits。

And then exactly one bit is hot for a given estate。

 meaning that this is going to be our estate encoding， 00，01，00，10， and so on and so forth。

So that'sit， simplest design process， very autoattable。

 and also the output logic is going to be so easy to design。

 but you can see that it comes at the price of more beats and more deeplo flows essentially。😊。

There is also another way of encoding， which is output encoding。

 which is possible usually for more machine。So in more machine。

 we know that outputs are directly outputs are only dependent on the state right so you can basically make it directly accessible in the state en coding。

So for example， since we have three outputs in light color。

 we can encode state with attributes where each beat represents a color。😊，So here is the example。

 so we have four states。We call it we can actually have three beats here， 001，010， 100 and 110。

 and you can see that beat 0 encodes green light output， beat 1 can encode yellow。

 right output and beat2 encode red right output。So with this， for example， here saying that okay。

 both red and yellow should be on， so if you use this encoding you can actually easily design the output。

 there should not be any actual logic for output anymore because your estate already shows the output。

So that minimizes output logic， but unfortunately it only works for more machines。

Which is understandable。Why is it the case， Why you cannot？Why cannot I use it for Mii machine。W。

Because in Mii machine， the output is also dependent on the input on the external input and you don't know about them right。

 so you cannot essentially encode output using your estate only。😊，Okay， so in the end。

 the designer must carefully choose and quoting a scheme to optimize the design under given constraints and those constraints can be number of flip flops。

 your output circuit。Overall， area performance， power， I mean many。

 many other constraints that you can imagine。There's also look into the trade off between Mo and Mii machine。

 so we already covered this that what is more and what is millli。And for that。

 we can actually use this example from your book。That we have a snail that is smiles whenever the last four digit it has crawled over our 1101。

 so essentially there is a snail you can see here。😊。

Thats scrolling and sees basically beats whenever sees a pattern of 1101， this nailil smiles。

Which is so important， I guess。😊，And then we need to design more and mesem of these snails spring。Um。

So this is the let's first start with more， for example。😊，Okay。So in Mo FSM。

 so you want to check the pattern of essentially 1101 so you start with this initial estate。

 which is zero。And then you say that okay if I see one， I will go to the next state。

 if I also see again one I will go to another state and then zero to another and then one to another。

 so meaning that if you see1，1，0 and1， you get to the state which you know that okay I already seen the pattern that I was looking for right and then you can then call this estate to one so this is more refer same because outputs are specified by the states essentially。

There are also some basic transition here that， for example， I can explain a bit more。

Here is exciting， for example， so you see one one if you see again one you should state here right because you said okay。

 this is one one， I see another one， so it might be。You know。

 beginning of another one one essentially。Pattern so you keep staying here as you see one。

 or for example， after when you get to the final state。

If you see0 you will get back to the reset state， but if you see1。

 you actually get back to this estate because now you are actually considering that these pattern can overlap essentially。

 meaning that if you have 1，101 and then 101 this can be actually also another pattern right so that's why you from S4 if you see1 you move back to the S2 in order to detect。

😊，は。嗯。In order to detect these patterns， essentially。Overla patterns so this is more。

 but we can also make it me now you can see that outputs are actually specify on transitions。

 so you're in S zero。😊，And then as long as you see zero。

 you will stay in a zero and the output should be zero。When you see one。

 you go to the next state and also the output is zero and so on and so forth， but here。In S0 S3。

 when you see 1， you go back to S1 and also make the output1。

Because you don't need to go to another state to say that okay。

 I already seen one and then output should be one， you say that I'm in the S3。

 meaning that I already seen the pattern of1，1，0。If I see another one。The output should be one。

 so I will encode that output actually in the transition。

 That's actually exactly the sign for milli machine。

 So whenever you have a milli machine in FSM outputs are specify on transitions。😊。

Not only they state because it depends on the state and also the inputs。Is it clear？Question。Okay。

 sounds good。So what are the tradeoffs here？Yes，Great。

 yeah that's one of the it trade of is more FSM always has higher number of estate。

 so that comes with some overhead。But is there anything that we think more is better than Mil？Yes。

 it's easier to encode program yes， it's easier to sometimes to reason about it also。

But there are also some， there is also another very important thing about more。Which I'm。是。

You guys seen a kind of glitch in previous lecture。

 right Do you remember there was a input that there was a glitch？Very short pulse。

 I don't know if you remember。So usually in more FSM， in more machine。

 your outputs are much more stable， and that's very important because。😊。

Because the output is defined by state by the state register and a state register are actually stable because they are registers。

 right？But in millli machine， your output actually is calculated based on the state。

 which is stable and also the inputs， but inputs may not be stable enough。

So there might be some glitch。Some， you know， high pulses， which is， which is just very， I would say。

Short term， it should not happen， but that happened because of some timing issues that we're going to also see more later next week。

So if that glitch， for example， happens， your outputs going to also see a glitch。Which is not good。

So in millli machine， usually people observe that outputs may not be that is stable enough。

Also in mill machine， you have a long combinational circuit。From the input to the output。

 essentially。So in general， in design， people try to actually minimize the sov combinational circuit as much as possible。

 So in more machine that's good because you have a short combinational circuit。😊。

To generate next safe and also another combination circuit， which takes input from only state。

 but in milli machine， you have input to the output and assume that you combine several milli machines together。

 then you have a very， very long combinational circuit。

 which can actually makes you crazy when you want to design it， yes。😊，Since。

F crops also so expensive and。More states， can you say it's usually from。

 if you want to minimize the amount of transistors that we use that really really takes。

I should say that maybe in the past， yes， yes， of course。

 when you really is thats your main effort to reduce the number of leaf flos。

 probably you should go with Mil， yes， Milly。But first of all。

 the cost is actually overall because sometimes your output logic might gets more complicated when you have Mili。

😊，Also， the costs for flip flos are not that high in today's technology。

 so is easier you can make flip flows， but yeah， I mean it depends on the current technology as well as also the tradeoff that you're concerned yes。

要你上知道所。So。More efficient。So。That's true， the things are those memories like a strand Dm and those that they are simpler。

Usual they are not used for such circuits essentially， so we're going to see about that later。

 but for example the registers that we have inside the processor， there are actually flip flops。😊，O。

You can design flip flos a bit easier， I mean with less number of transitionistors。

 there are a lot of research on that that people make flip flops with less number of registers。Sorry。

 less number of transistors， I don't know why is it register， last number of transistors。😊。

But overall， the cost of flipfl is much higher compared to RARAM and DM also cash。

 like in the processor architecture caches， for example， they are a SM。

 like you have also main memory which is DM， but the register file and registers that the processor has usually are actually kind of flip flops。

Philiplos are very good for synchronization， essentially because they worked nicely with clock。

Question。Okay， yeah， so we summarize kind of trade off between Mood and Milli。But in the end， the。

Unless we specify explicitly in the for example， exam question that you should design Mu or Mili。

 do you have that freedom to design it merely or more？😊，Or the way that you like it。Okay。

 so that's a procedure for FSM。We kind of summarize we determine all possible states of our machine and if we develop a state transition diagram。

G this is done for a basic textual description and you need to determine the inputs and outputs for each estate and also figure out how to get from one estate to another and let me finish this and then we can take break。

And as I approach， we can start by defining the reset state and what happens from it。

 this is typically an easy point to start and then continue from to add transition state。So yeah。

 and then building an FSM is like programming， but it's not completely like programming。

And FSM has a sequential control flow like a program with conditional and basically how to like go tos essentially。

Yeah。Okay。So in the end we're going to use these FSM in order to， for example， design control logic。

 FSMs are really good for designing controller and in your today's machine， modern computer system。

 we have controllers everywhere so we have a controller that control the microarchitect of the processor。

 we have controller to control， for example， your memory controller， your caches。

 your storage system， there are many， many controllers in the system and people use different FSMs。

SoThere might be also a way that you combine all these FSM and make a very quite big FSM with millions of states in order to control the whole system。

 but usually the way that people design is that they design thisjoin FSM and these FSM needs to somehow communicate to each other。

 so that's the way that people make bigger state machine。

So we're going to see a lot about process or design later in our future lectures。Okay。

 so we are done with the first part of today， so let's take break and get back when they're in builds。

And we will continue with lab and other stuff。But。

![](img/d14fb3afe8d5ec668fee5df1dca90851_11.png)

![](img/d14fb3afe8d5ec668fee5df1dca90851_12.png)

给你给你一会儿你来俾你。Thank you for sending。Yes yes。Live it and。



![](img/d14fb3afe8d5ec668fee5df1dca90851_14.png)

![](img/d14fb3afe8d5ec668fee5df1dca90851_15.png)

![](img/d14fb3afe8d5ec668fee5df1dca90851_16.png)

![](img/d14fb3afe8d5ec668fee5df1dca90851_17.png)

![](img/d14fb3afe8d5ec668fee5df1dca90851_18.png)

![](img/d14fb3afe8d5ec668fee5df1dca90851_19.png)

Now， or you can hear me now， mads。Ma not know。需要。这啊。We cant hear you。Can you hear me Yes。

 Constantius。

![](img/d14fb3afe8d5ec668fee5df1dca90851_21.png)

![](img/d14fb3afe8d5ec668fee5df1dca90851_22.png)

![](img/d14fb3afe8d5ec668fee5df1dca90851_23.png)

そま。啊对对。Okay， let's get us started again。Thank。他在家里。Is everything going fine on Zoom， YouTube？Yeah。

We had some infrastructure search issues， but things are。I guess under control。

 thanks to our great Ts。Great。So I think this is also a kind of lecture that you guys been waiting for it。

I'm going to introduce you the labs and also provide some ejis。

I put Atber's name actually here on purpose because he actually he's the main person for labs and he's leading labs。

 he's also attending this conference to present HC conference that that I said to present his paper。

😊，So yeah， but in general， if you have questions about das， you need to， I mean， you can， of course。

Come to me， but AtOre is the main person， essentially。Okay。

So we're going to say about logistics first。😊，Our lab session。

 you know that is on site and we have four days， this information is already known for you so I'm not going to bore you。

And basically we have these times and also these rooms， just make sure that in Friday。

 the first session， we have different rooms。So， this should be。Easy for you to cover。

And the first session is going to be next week on Tuesday。

 so make sure you attend I mean those people that going to attend Tuesday session essentially。

And you know that you will work in groups of tool， we had two options。

 which I think we are already aware of that， so things are already defined。

And every group we receive an a Fiji board to work with。

 so make sure that you attend the first week of the lab。

 I mean you should attend all the lab sessions， but first week is also important because you're going to get a Fiji。

And please follow moduleodles for details。The grading we have 10 labs and we have 30 points in total。

 so you know that 70 points is coming from your exam and 30 points is coming from your labs so with that we're going to have 100 points that is going to somehow scale to one to six。

So we will put the lab manuals online on our webage and this grading policy we have in class evaluation。

 like in lab sessions， evaluation， which is 70% and mandatory lab reports， which is 30%。

And there're going to be one point penalty for late submission of the report。

 so you should finish the lab within one week after they are announced。

You can also use your grades for labs from past years， this， for example。

 the Mole page for last year。We had actually， in the past， we had the students that， for example。

 in 2023， they wanted their lab grade from。2019， you know， so don't worry。

 we have database we can fetch from I don't know， whenever you want。😊，Just let us know exactly。

 essentially。And for a question， you can email us using this basically mailing list。

 this will email send to all TAs essentially that we can and also we're going to have model for。

So what we will learn in these lab sessions， we're going to see about this transformation hierarchy and we're going to understand this software hardware interface。

 micro architectitect and logic， specifically labs。So。

 and how to maketer between performance and area complexity in your hardware implementation。

 There are hands on experience on hardware prototyping using FJs。

And debugging your hardware implementation， using hardware description language HDL。

 which specifically you're going to see very large how to use it and this hardware design flow and as well as computer AD design tools。

 short as CA tools。So what is an EGA， EG's state stands for field programmable G array？😊。

This is one example of Fiji， there are many， many different examples Also in the market in the world you can see if Fiji is a software configurable hardware substrate that makes a Fiji so exciting because there is a chip but that chip is not hard coded essentially so you can implement。

😊，kindind of any circuit as long as your circuit can fit in that fji because each f4ji has limitation in the number of lookup tables。

 number of I don't know flip fls， multiplex， whatever， so each fJ has a limit。

 but within that limit it can implement everything that you want。😊。

So this has reconfigurable functions， reconfigurable interconnection of function， which is very。

 very important and we're going to see a bit by， but you have a lot of switch boxes。

 you have a lot of switches that they call switch box connection box and all these switches can be reconfigured in order to connect a logic block to another logic block。

Which is very important for FPG to implement your circuit。

 and also we have reconfigurable input and output in FPG。

So you have already seen this slide from Professor Mutu's lecture that essentially we have this flexibility from CPUs。

And this is quite programming is， but as we go through this basically spectrum。

 you're going to see more efficiency， but at the same time you might have basically less programability。

 so if fidges is they are standing kind of in middle between completely a6 and also something else after GPUs that they are accelerators。

So we have a fidges in today's session， and these are some slides that I just want to motivate that a fijit that you're going to use not exactly the fidge that you're going to use。

 but the concept。Is very useful and many systems are actually using a Fiji modern Fiji。

 this is one example in that use for deep learning platform for a Fiji。😊。

And this also from another system that they use a FiJ to solve complex science， engineering。

 business problems that require high bandwidth， enhanced networking and very high compute capabilities。

There's also another aG use for DNA sequencing， which is important for genome analysis。Byinformatics。

 you may know when you want to that can actually provide a lot of applications， including。

Personalized medicine to also you know， to。Limit I mean mitigate this outbreak of our disease。

 so all these are important in general analysis and DNA sequence is also one of the very very early stage step of that。

 so effs are very useful for that as well。And have also in our group。

 we have used F FiJs in many of our studies， these two papers， gateatekeeper and sneaky snake。

 both of them are actually a FiJ based accelerators for bioinformatic applications。

And you can learn more about it by checking this paper。

 we also use basic fjis for other applications again this also basic colors is for genomics。

 we also use a FiJ for weather prediction， stencil applications。

 so these are different application that essentially you can use a Fij to accelerate them。

You don't need to know all details of course， about them。

 just this is a slider here just to motivate you to say see that how a phg can be useful to improve performance。

In our group we actually we have developed a system called in the past we were calling it SotC。

 but we actually extended much more and we improve it and now the name is actually Diham Bennder Atrb is the leader for this project actually。

 so that's why he's also your HTA in this labs。So this is an open source f based infrastructure to experimental all studies on D。

 so you can actually do a lot of studies on DRAM。We're using this DM Ben， which is kind of。

 for example， you can play with all timings of your DM， your commands that you you're sending to D。

 and that can help you to understand many of hidden stuff in your DM and also design techniques in order to benefit from functionalities that they are actually already available in DM。

 but people may not be aware of that。So for example， in one of our work， recent work。

 we showed that commodity of the shelf Dm chips。They are capable of doing computation。

 they are already capable of doing functionally complete Boolean logic。

 so you know what is functionally complete right so you can implement N nor and or and not operations using commercially off the shelf D chips so that's what we for example。

 got from this theem bendnder system。😊，So you can also， if you're interested。

 you can check SotC and Dam Bennder on our Github page is already completely released。

And this is also the paper if you want to learn more about it。

Thiss also one of a picture from this system you can check。

And this is also this Ro hammer study that the first paper that we publish in this area that we show that essentially by opening and closing or activating and deactivating a row in a D row multiple times。

😊，Or let's say fast enough you can actually cause errors in adjacent or neighboring growth in D so that's a phenomena we called it I mean they called it as Rohammer it's called as Roham that basically breaks one of the main importance like this isolation principle of Dra chips so you can actually by activating and deactivating one D row you can cause errors and later works they use this phenomena to actually design attacks security attacks so this is Rohammer that you probably know about it because from Professor Mulu's talk。

But basically we use our system to have a lot more deeper look in Rohanm and also uncover a lot of stuff about Rohanm。

As well as one of the techniques that basically industry provided and they thought they actually claimed that this solved the problem Rohir。

 but later on with this work and other works we show that this is not the case so yeah essentially you can use this kind of Dam Bennder infrastructure to do a lot of studies。

There is also another work that we published in 2023 that we showed that actually that there is also another phenomenon called ropepress。

 we actually call it ropepress that if you keep one row in the D active for a long time。

That can actually cause errors in neighboring roles。

 so we call it row press and we also again use the Ben。You can for example。

 generate random numbers inside your DRm and random numbers are important for many。

 many applications， so we get to this generation of random numbers in DM using this DR vendor infrastructure。

Okay， so I don't want to bore you more， but this kind of infrastructure also can be used for other memories。

 for example this one is for characterization of flash memories and it's actually from quite past in 2012 until 2018 or so that we had this kind of infrastructure that we studied flash memories and we uncover a lot of reliability issues as well as mediaigation techniques for all these reliability issues in the flash memories of that time essentially。

😊，If you want to learn more also about flash memories like this error characterization of flash。

 I would recommend you check this paper， flash memories are really exciting。

Is actually one of the very， I would say。Nice， listen。For every researcher。

Because when people were working on flash memories in 1990 or so。

So flash memories are way behind of their performance back then and many there are many people that may see that while you're working on this kind of technology。

 this not going to work at all。And but now you can see that those people were completely wrong。

 so you had to actually work on these emerging memory technologies to make them possible that can actually change many people's life and now the main reason that for example。

 we have smartphones is flash memory。😊，Otherwise， you could not， for example。

 have a hard disk drive in your smartphone you know， and it gets you that rotate in your。

Pockets to have your memory essentially， so it's very interesting to see why we need to work on emerging memory technologies。

😊，Okay。You can also use FJs a lot for prototyping this one example that we design a prototype in order to use processing using D。

 so we showed that for example we can have a holistic end to an F4J based framework for processing in D that you use your D in order to do computation。

You may not know completely what does it mean exactly。

 but essentially you are using your D to do computation and this P you can actually implement them in a prototype。

 the whole system is closed， you can see you can implement the whole system essentially。😊，Okay。

And these are also for another work， metata， and you can see that Atberg here， this guy。

 he got this best paper of art at HighP for this work。Okay。

 so let's have an overview of our lab exercises， any questions， by the we？Good。

 so this is our FJ board basis3。😊，U。This is actually is not badboard， I mean it's quite capable。

 but of course it's not you know as capable as modern FGs that people use。

 but you can learn a lot of fundamental things about these FGs so there are many actually stuff going on these F bar。

 you have USB connection， you have video out VGA， you have micro USB， you have power switch。

 you have seven segment displays， these are a lot of LEDs that you have you have switches that you can control use them as an input for example。

 you have push buttons。And this is your refugee check。

This shows that when you want to design a system， the brain actually usually is so small and there are many。

 many things going on around it to make interface and that's why actually interfaces are actually very expensive in the computer system。

😊，Okay， so at the end of exercises， we will have built a 32 bit microprocessor running on the FiJV。

So it will be a small processor， but it will be able to execute pretty much any program。

 so I think this is very exciting that we will learn how to design microprocessor and each week we will have a new exercise that in the end will guide you to that microprocessor essentially。

So you're also encouraged to experiment with the board on your own。

 we may have some extra boards for those who are interested， unlikely， I would emphasize on that。

 but you can ask a first when we see。And it's not possible to destroy the board by programming。

 so don't worry。Okay。So in lab one， we're going to throw a basic circuit。

 it's going to be about comparison。So you just need to draw a schematic of that circuit and we don't have a4J programming involving that one。

But we encourage you to do it later when you have understanding of FVJs。

In La two we want to map our first circuit with VG， we're going to start with Ed。

 which is very simple and we design a circuit that adds two one bit numbers。

 which is going to be a full ladder and then we reuse this one bit full ladder in order to make four bit addition。

😊，And essentially you need to implement design a Fiji board and use input switches that I showed in that picture。

 there are some switches that you can use as the input to the Fiji and also the output of the Fiji goes to LEDs so you can see the output on those LEDs based on the lights that they are lighting。

In La3， you're going to use actually seven segments in order to show the result of La two。

 essentially， so that's train you how to design a combination of circuits for refugees。In La four。

 we're going to a finite thete machine that we design these blinking LEDs for a card term signals。

And this implement and basic implementation and use memories because it kind of a sequential circuits。

And also， we should be able to change the blinking speed。

 so you're going to see in your lab material essentially。In La five。

 we're going to see how to implement an ALU。And that's actually the first kind of step in order to get to your processor。

 so you will design your rail that can do some arithmetic operations like addition， subtract。

 multiply comp， and some logical operation like and orrange so on and so forth。

Then in lab six we're going to test our value basically whenever you design you need to verify it and that's the verification part that you need to design kind of test page to simulate your design and in La6 the focus is to teach you how to simulate and test the functionality essentially。

 so we learn how to debug your implementation and to resolve problems essentially。😊，In La seven。

 we are going to write an assembly code for the microprocessor that we are looking for。

 we will use the MIPS and that implement a program which you will later use to run on your processor。

 which。It sounds quite exciting at least to me。In lab 8。

 we will use we will basically make this full system integration will that this will be covered in two weeks。

 so essentially。We have 10 labs， but La 8 is actually kind of two laps。So we have La 81 and La 82。

 essentially。And then we learn how a processor is built and we will complete your first design of a MIPS processor and we run a snake program on it for example。

 like this。Okay。And in La9， we analyze the performance of the processor that we design and how we can improve the performance by adding some other instructions like multiplication。

 bit shifting， and so on and so forth。Okay。So that's all。

 but you can see the material for every lab you will put it on website， you will check it。

 I encourage you to check it early enough and you attend the lab session by kind of you know prepare mind as much as possible。

😊，Okay， let we also provide a bit more detail about Eges。

 so what is an FJ we already know that it stands for field programr data array。😊，And you know。

 this is stuff。So this is a high level overview of effigs that we need to configure logic blocks。

 so all these。Rakangle square， let's see。They are kind of logic blocks that you need to configure them in order to implement some functions。

 and then you need to configure also these switch boxes。Or switch blocks。

 essentially in order to make connection of these circuits。

And then you have some audio blocks and basically that you can use them。

 you can again also configure them in order to see the output like when you check the data sheet of fiji。

 you know that you're going to see that， for example， some of these。These are your paths。

They are connected to some of some outputs in your board。

 like some of them are connected to seven segments， some of them are connected to， for example， LED。

 some of them are to switches， so you can actually configure them nicely。

There are two main bi blocks in Effvis lookup tables and switches。And I guess， I mean。

 you already know about lookup tables， it's a memory that you can implement like when you have LUT of three input。

You can essentially implement any tree input function using data。So。

 and then also you have switches that you can configure them in order to make connections。

 essentially。So this is a three bit input LluT that you provide one output， one bit output。

 and it can implement any three input function as you know。So this stuff。

 I think is already familiar for you from the lectures Professor Motulu。

And then essentially you can combine these LUTs in order to this is still tree input。

 but how to implement complex function meaning it features are composed of many LUTs and switches。So。

 in the end， the。Yeah， this， for example， is a fiji chip and this a small dot is actually this for example。

 so you have a lot of these。😊，And then you need to basically combine all these LutTs to create bigger function。

 for example， if you have three input LutTs。And your function is for input。

So you can think of how many three input Ed you need to use in order to make your four input。

Function。Think about it。But yeah， so modern and feature architecture。

 they typically use elus with six bit， so they are six euts and we have thousands of them。😊。

And we have megabytes of distributed on chip memory that all these un chip memory are essentially used to configure。

LUTs and also switch boxes so whenever for example you want to configure this switch box。

 for example here to connect this wire to this wire you need to somehow configure it and there are small memories that you can actually configure each of them using a bit stream and that makes that connection happen essentially。

So yeah， exactly this is。😊，For rany memory but at the same time for better efficiency fVJ also has some hard coded special purpose hardware blocks for example multiplierers are usually very expensive and if you want to implement multiplierers with LUTs their performance it might not be good so there might be some asI specialize special purpose hardware blocks for multiplayers and whenever for example you have a multipler in your design you just use that for example。

Modern basically a fi they might actually have， they might have also processor。

 so there might be some microprocessor on your f Fiji chip or also decide your micro Figji chip。Yeah。

 exactly， even a general papers processor can be embedded within the fuji。不是。

And this is an example of modern refger platforms zing as z inc ultra scalepl。And again。

 this kind of advantage and disadvantage of fidgejis that you know essentially， as advantages。

 we can say that an algorithm can be implemented directly in hardware and we have high specialization。

 high performance and high energy efficiency。We have low development cost， of course。

 compared to custom hardware design， which is a， for example， and we have short time to market。

And usable and reable for many purposes， so that's why FJs are quite useful and widely accepted。

 but of course they also have disadvantages， so they are not as fast and power efficient as dedicated hardware customized for an algorithm。

And reconfigurability comes at a cost significant area and latency overhead as well as I would say reliability overhead us also so there are all these switch blocks and you are controlling all these with some memories so if something happened in that memory for example one zero goes to one or the other way around then the whole circuit is just can be wrong right so there are a lot of reliability issues that also can happen in a fijis as well as other circuits。

 but that's also one of very important things know about e fis yes so the latency。

Usually still possible to run。Could you on the general purpose。I would say usually yes， yeah。

 that's usually the case。Specifically because on a general purpose person， you have。

This sequential program so there is this stuff that I mean even though you can also have some parallel programming but still there is a program that there are a lot of sequential instructions that you need to go over than 101 but if fidges are kind of they are assembling hardware which has a lot of concurrency so that's why in general their performance is much better but at the same time they comes at the cost of。

The stuff that I mentioned and also their performance is not as good as AsIC and custom devices。😊。

Very good question。Yes。😊，think you already have some sort of， for example。Like。

Some specific part of which of the Yes adapt no no probably no yeah usually so yeah I mean that's setting actually today's systems are actually heterogeneous and they are using general purpose core they are using GPUs in GPUs they also have tensor core that kind of customized for that application so actually today's system are combining all these difference basically platform so in a modern system we have CPUs actually this is also as Professor Muso also mentioned this shows ample Apple M1 chip which has actually has GPUs。

Has also general purpose course a Fijis， maybe not a FiJ， but many other acceler。

 so basically today's system we're combining all these。

And that's why because we need there are not many， not every application can be accelerated in either of them。

 so you need to benefit from all these things to be。Any other question？Okay， great。

So to program an Ephiia we are using computer aid design or CAD tools， As have many resources。

 LUT and switches， and they are hard to program manually， of course。

 so it's going to be very headache if you want to do that。

So how can we represent a high level functional description of our hardware record using the FJ resources？

And then we need to select the resources to map our circuit2 and then optimally configure the interconnect between the selected resources and generate a final configuration file to properly configure an fPJ so if you don't have Ka we need to do everything manually but luckily we have cat toolss that we have this program problem and definition and then we use kind of hardware description language like very log and BHDL whichre going to see in a bit so that's your job or our job but after that we use cat toolss so there is this logic synthesize that synthesize your very log programming essentially to logics and then there is this placement and routing to place your logics on all these fPJ configuration blocks and then how to route them by configuring all these switch box。

And then after placement and routine we will get to this B stream generation that essentially that BT stream needs to flow to your refugee and configure every single LUTs and memory that you have on your Refe so after happening after this BT stream generation and that communication you're going to have your circuit on your refugee essentially。

 and that is automated luckily， fortunately with different tools。

 but in this course we're going to use z links to Rivato tools。😊。

So Vivada is a software tool that helps us throw out a Fiji design flow and this tools provides tools to simulate also our design to validate the correctness of the implementation。

 debugging and many other things also。Weva also provide drivers and graphical interface to easily program the feature using a USB cable。

And in this application already installed in computer rooms in our lab rooms， essentially。

So you can also check basically tutorial of this rivado using this。Basically， video。

 I'm not going to play it now so you can play it at home。对。Arenive。I'm supposed to play， but yeah。

Have would just。Okay， so keep in mind that you do not need to install water on your laptop。

 I mean you can do it if you want， but lab pieces already have it installed。

And please do not ask Ts to grade your labs outside of lab hours。

And stopping your lab files in the correct format， so the format is already specified in your lab manuals。

And please double check your upload files and do not incorrectly submit， you know。

Because that can cause zero points for you。And double check your grades essentially。

So when we want to find larger grid， we will send an email to remind you。

 but very important that you check your lab grades by then and let us know if something is missing and then we can fix that problem in time。

 hopefully， okay。😊，So that brings me to the end of this lecture。

 but I want to also talk a bit start at least very very quickly。

Just to give you some foot for thought and then we're going to continue very look next week。

 so can we go to lecture。For C。Mus。Honest。Can we go to a 4 C？But。Okay。



![](img/d14fb3afe8d5ec668fee5df1dca90851_25.png)

Sorry， council。

![](img/d14fb3afe8d5ec668fee5df1dca90851_27.png)

Yeah。是不。So。通。Yeah。不知道。啊。Yeah。Yeah。こ。So。I think can handle this。



![](img/d14fb3afe8d5ec668fee5df1dca90851_29.png)

Okay。Thank you。

![](img/d14fb3afe8d5ec668fee5df1dca90851_31.png)

Yeah。Right。Okay。It's all good on zoom。Yeah。对。哦。

![](img/d14fb3afe8d5ec668fee5df1dca90851_33.png)

![](img/d14fb3afe8d5ec668fee5df1dca90851_34.png)

It was tires screen。这就不你说。Is it okay？边退。対しかな。嗯。O。欢迎。All good。Okay， so。We have 12 minutes。

Of course we cannot cover this lecture， but we're going to see a little bit about this。😊，So yeah。

 this is the agenda for not today much， but anyway we will basically we're going to get to we want to get to this processor next week and the weeks。

 I guess after how to design a processor。😊，But now let's also quickly talk about Harvard description language and very luck first。

 I want to use some pictures to motivate why we need that。So， this is a。The chip in 2017。

She was one of the strongest sheep back then。And its had。1。75 billion transistors。

So people were kind of what are we' going to do when we have billions of transistors and nowadays actually we are way away from that。

So in about 47 years， we have basically a million fold growth in transistor counter performance。

This is also another chip in 2021， which has 16 billion transistors。

This chip is in Apple Mbon Ultra in 2022 that has 114 billion transistors， which。

You can see that it's growing and growing so of course it's not easy to configure every single transistor you know by our own so that's why we need some you know tools for that this also surplus in 2019 that has 1。

2 trillion transistors and largest GP back then had 21。1 billion transistors。

And another version of Cbrauss wave scale Ageging 2 has 2。6 triion transistors。

And also we also checked what Nick Wiippedia says about it and as I expected。

 memories are actually having way more transistors， so like flash memory in 2022 has 5。

3 trillion transistors。Or for example。Yeah， GPUus in 2022 has had 18 billion transistor。

 so you can actually see that here is also very important。So the DRam includes about。12。Quarter。

Qudrillion yeah thousands of basically trillion transistor and that's about 97% of the of the old transistors so that shows actually that most of our systems transistor are actually spending on memories so。

Make sure that you always meize that that basically memories are actually very。

 very expensive in terms of number of transistors。Okay， so how to deal with this complexity。

 we are using hardware description languages and what we need for hardware design that provides ability to describe and specify complex designs and to simulate their behavior。

 functional timing and to synthesize using automatically design as we showed like Vialdo as a CA tool。

 basically。So hardware description language is enabled all the above。

 and they are designed for basically describe hardware and we have different version of it。

They called as HDLs， but very like VHDL are the most common HDLs。

 people actually both of them are useful。But in this course， we're going to learn about very luck。😊。

And of course， if you learn one， it's not hard to learn another one。Okay， so as I said。

 there are two went on HDS， very large。And we shared here we provide some history about it that you can check if you're interested。

But that's not the most exciting thing that we can bring from this course。Okay。

 so why specialized languages for hardware so HDLs enable easy description of hardware structures。

 so specifically you can also you can think of using why not using for example C programming you know to specify hardwares the reason is that I mean HDLs are customized for hardware and hardwares we have some basically components。

Like we have wires， gates， registers， flipops， clock， rising， falling edge。

 and all these basically components or specification that they are not necessarily provided in sequential programming like the C++。

 for example。So that's one reason another reason also is to enable basically parallels so in hardware we have a lot of concurrency so every single actually all these transistors。

 all gates they are actually operating in parallel so there is no sequential thing happening in your design so that's why actually if you want to model your hardware using for example Cpro or using Python is going to be very headache because it's very hard to simulate that parallels and that's why actually our simulators that people develop for example simulator for GPU using C++ these simulators are very hard to design and also they are really slow because so they need to actually simulate all these complexity and all these concurrency that we have in the hardware which is not the easy thing to do so HDDLs enable that and all hardware logics can operate concurrent in HDDLs。

And most of the above is a specification， simulation and synthesis for your heart rate。So HDLs。

 basically we have some key design principle that we should consider。

 we have this hierarchical design that we always need to design a hierarchy of modules for our system。

So in a complex circuit， you actually。You can see that there are many blocks。

 but each block actually can be basically structured but many， many gates。So we use some predefined。

 we call them primitive gates like and and or， these are actually some kind of leaves in your hierarchical design that you don't need to go below。

 yes。The three k as。Yes， yeah。And simple modules are built by instantiating these gates。

 like components like multiplexer， so we're going to see more about it later。

So basically you need to make a hierarchy of your design so you can have a top down approach that we're going to see in a bit or bottom up approach to design your big system so top down approach you have a top level module which for example。

 your top level module is let's say microprocessor。

But then you're gonna say okay my microprocessor can would have some submodules and then you need to design each of these sub moduleles。

 but each sub moduleule also can have some sub modules and then you're gonna get to some leaves and these leaves are actually a primitives the one that you don't want to go below of that for example in very low you can say that okay my gates are those leaves you design you may combine some gates and make some bigger logics like for example add multiplayers and then you may consider add or multiplayers or these arithmetic units as your leaves essentially but anyway there should be there're going to be some instance that you don't want to go below of that and this the kind of top level methodology that you might have you can also think of bottom up design methodology that you first identify the building blocks that are available to to you or to us and then we build bigger modules using these building blocks and these modules are then used for higherle modules until we build the。

Top level module in the design。 so you can also grow the other below。

And I should acknowledge that in our system， so as a designer， whenever you want to design system。

 you actually need to use combination of boths， so you need to have kind of top down approach。😊。

First， because you should be motivated to what you want to get， but then when you want to implement。

 you usually use the bottom of approach so you design your I mean you make this hierarchy using top1 approach。

 but from the implementation wise usually go bottomtimore。😊。

So in order to define a module in very large。So module is the main building block in verylock that's a notation。

 we first need to define the name of that module and directions of its ports like input and output so this is an example module that we have and it has three inputs ABC and output y and then we want to describe the functionality of this module essentially。

So this is the example， very low code for that。You start with defined definition of the module。

 you say these are keyboards， essentially module， and then the name of module， which is example。

And then you have these port list， ABC and y these are ports and then basically you need to define which which of them is input。

 which of them is output so here for example， ABC are inputs and y is your output。

And then basically this part， you need to specify the functionality of that module and in the end you have this end module which close your block。

And also you can also have different style so these two definition both are correct so here you say that module for example test aB by and then you say input a input B output y you can also say module test input a input B and output y so both are correct and it depends on your style the way that you want to write。

So what if if we have multi bit input and output， we can use define using this kind of range。

 so you put range end and range a start。And that shows the number of beats you have so number of beats is actually range n mind the range is start plus one example。

 so for example here you have input 31 to 0 a that means that actually a is actually a value which is 32 beats。

And then you can specify every single of bit of ape using this notation， A31， A30， A0。

 and so on and so forth。You can also do， for example， this B1 you don't need to put zero always。

 you can say that for example output 15 to8 B1。And this basically B1 has 15 until B18， essentially。

This is also another example7 to zero， and you can see。And you can also have this input C。

 which is single bit signal。So here， when you say 31 to0， actually it represents a 3 a 32 bit value。

 so we prefer actually to define it as is， but you can。All you can also define it as 0 to 31 a。

 but that's。That's not very common to use when you want to design define a multi bit value。

 you usually use this kind of notation 0 to 31 when you want to resemble kind of array definitions。

 so you have different array and you want to define every bit of it。Okay。

 so and it's also good to be consistent with our representation， multi bit signals。

 always we can use this kind of notation and for whenever you want to design the a area。

 use this kind of notation， okay。I think it's a good place to stop。

 We will continue very luck next week。 Have a nice weekend。😊。



![](img/d14fb3afe8d5ec668fee5df1dca90851_36.png)