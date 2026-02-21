# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p08 -08- L6_ Timing & Verification II (Spring 2025).zh_en -BV1iV1XBWEJW_p8-

あ。

![](img/cb6e40a2240f8c7095503d555bd1d173_1.png)

。は。啊这个。そう。所个3。あした？Okay。我是。Yeah。や。Yes。は。Yeah。Can you hear me？あです。あ。我。あ。要的进空。不。对。は。What。I。So。神。お。还有所。で。

我。Okay。じ。あ。来。さぞ。我也。然。放间啦。Thank。あ说。Okay。あです。他。しAl nice。あようございましす。呀我最喜欢。自己。你。そ。な。啥意思？好责。好。お。我。啊。そきまで。

责任。好的。そぞじ。Yes。还在。す。早。わかす。我是。个。おさは。有前的。哎。刚才。Yeah。あか。都。这一。老他。はま。个。也是。あても。好。Yes。是。あ。Oh。It是你。Okay。生散。S。

想分。他有内容的。谢行。去。要そ以。そ。全ね。🎼20加1所时间。🎼，くし。Okay。Let's get us started， is it too loud？I guess so。

is it better。So good afternoon， we back to another lecture in digital design Comp architecture。

 today we're going to continue。What we have started in timing and verification。

I've been waitingiting actually for this lecture because this is actually one of the most exciting topics in digital design。

 and I really hope that you guys also enjoy it。As a reminder。

 these are some readings that we have for this week and next week we're going to start for newman Pro of microarchitecture foundation that we need for that。

 so make sure that you also check these readings for next week。

And basically we were discussing about circuit timing yesterday at the very very end and we say that basically we already know how kind of investigate logical functionality。

 but we wanted to know about timings and how fast is the circuit。

 how can we make a circuit faster and what happens if you're on this circuit too fast？And basically。

 we mentioned that a design that is logically correct can still fail because of real world implementation issues。

And we basically reached to this point that we wanted to start about combinational circuit timing。

So the digital logic abstraction that we are using is quite convenient。That for example。

 we assume that we can outputful changes immediately with the input， so here is a not gate。😊。

And the a is the input。 And immediately after。Basically， first immediately a can go to zero。

 so this is sharp。And the output of this gate also immediately goes from zero to 1。

 so this is a convenient abstraction that we usually consider when we want to talk only about the functionality of the circuits。

 but in reality that's not the case， so outputs are delayed from inputs because transistors take finite amount of time to switch。

So。For here we have a buffer gate， this is be careful this is not a not gate so the input a actually goes from zero to1。

 This is also not that idea so it's not sharp and the output takes some time to react essentially so this is a delay that we have even actually this diagram is also a kind of abstraction because what we have seen in real world is actually something like that you know we don't really have。

😊，Lines in these kind of wave forms。And you can actually define different kind of timings so we're going to see the definition of them。

 but this is one of the timings， for example， the amount of the latency that you need to wait for for the output to start changing so this is the latency for that and here is also another latency that is kind of propagation latency。

 the latency that you need to wait until your output is stable essentially。

But we're going to learn about these definitions。So delay is fundamentally caused by capacitance and resistance in a circuit whenever you design a circuit。

 like every gate that you have has transistors。And first of all， when transistors gets on。

 they don't act as a。Basically single wire so they can act as resistors and also all of them they have a capacitor so you have also parity capacitance in all wires in transistors。

And also when you want to change the output， essentially。

Very likely you need to go through this R C delay。 So you need to。

Charge a kind of a capacitor and from your study， I guess in physics and from maybe from your high school also。

 you know that that would take some time so you cannot immediately charge a capacitors。

Similarly when you want to dischargege a capacor that would take some time so that's one of the reason another one would we also define at the speed of light so we know that the speed of light is fast but not so fast on a nanosecond scale。

So anything affecting these quantities can change delay， rising。

 meaning that going from zero to 1 and versus falling input。

 so each of them can also cause basically and cause delay in your circuit。

Different inputs have different delays。Re， if I want to also give you some insight is that think about the。

Nan the logic that we discussed the Nant circuitry in CMs。

 so we had two inmost transistor in series and we had two primmost transistor in parallel right in the pull up network so from that you can see that actually in pull up network you have two transistors that they are in parallel。

So from Kiop's law， you know that you can actually you have better current to charge a transistor。

 but in the pull down network you have two transistors that they are saved。

So that can actually reduce your cor， so that's very simple example that shows you basically different input so for example。

 going from0 to one in the output can take lower list time compared to going to one to0 or device vice versa and any different input vectors can also have different latencies。

😊，Also changing the environment like the temperature or for example。

 the voltage supply voltage that you provide to the circuit can also affect the latency as well as aging of the circuit so as you use your circuit more and more your circuit is going to age and with that actually your latency can increase。

So we have a range of possible delays from input to output。

That basically a designer need to deal with them。So we have in order to find a good kind of simple abstraction。

 we're going to define these two delays， contamination delay and propagation delay。

 contamination delay is delayed with until output， which is why starts changing and propagation delay is the delay until output finishes changing。

So we can see from this example， this is a circuit and AB are the inputs and y is the output。

So the moment that we start changing the one of the input， which is a。

 you can see from this circuit that this is the amount of time。

 the minimum amount of time that you need to wait until your output starts changing。

 so we call this contamination delay essentially so this is the amount for contamination delay。

And from starting the changing of the input and also until the output finishes changing we call this propagation delay。

 so this is the definition of propagation delay and that the first one is a contamination delay we usually need to when you want to make sure that your circuit is stable you need to basically make sure about basically you need to calculate propagation delays。

 but when you want to also make sure that any single change is not affecting the result of your circuit you really need to also be conservative and you need to check contamination delay we're going to actually see a lot about this in this lecture so don't worry if you don't understand it clearly now。

And this is a notation that we usually use in waveforms， this cross hatching means value is changing。

 so not it's just the kind of notation for waveforms essentially。Okay。

 so we need to calculate longest and shortest delay paths。

 we care about both the longest and shortest delay path in the circuit and we will see actually the reason in this lecture later。

Here is an example you have this one and here and then the output goes to this or and then you have an so you can by checking this circuit you can see that probably the critical path is going from a to the y essentially right so you need to go through this and and then through this or operation and then through this and operation so this is the critical path or the longest delay path of your circuit and very likely your shortest pass is going to be this from D to y right because it only goes directly to this gate。

😊，So。If you want to calculate， for example， the minimum latency of this circuit。

 you need to basically check the shortest pass。If you want to calculate the critical pass or longest latency of this circuit。

 you need to go through the critical pass latency。So essentially critical longest path for that。

 we calculate basically that latency of propagation delay is going to be two。

Basically one propagation delay of this and and then one propagation delay of this or and then one propagation delay of this an so in the end to have we're going have two propagation delay of and plus one or right and for the shortest pass latency we need to calculate based on the contamination delay as we already discussed so for and we only consider we consider the shortest pass of the circuit and we only calculate the contamination delay so the contamination delay of this whole circuit is going to be the contamination delay of this and essentially only right。

Does it make sense。Okay。So let's see with some examples here we can see， for example， this is the。

Circut and these are the initial input that you had like a 1， B 1， C 0 and D1。 So with that。

 if you calculate， you can see that the output of y would be1。Then you change the input a to 0。

 so this is your transition from 1 to0。And things needs to get propagated， essentially。

So this is actually a very good example because you need to go through all these gates。😊。

This end gate in the passive was1， but now because a is0。

 so you need to wait for that until n1 gets to0 and then when n1 gets to0。

 then this order also needs to get0 so you need to also wait for that such that n2 also get from1 to0。

And after having zero in N2， then you can actually also see that y goes from one to zero。So。

It's actually exactly propagation delay， so your delay is propagating as you go through this critical path of your circuit。

And for the shortest pass。Considering this basically initial vectors a 1，1，0 and1。

 and then for D you go from 1 to0 so you know that the output should go from 1 to0。

But this will happen very， very quickly。So this is the propagation delay。

But you can on here is a propagation data， but you can calculate the contamination delay that D when starts changing and until y also starts changing so because of that we calculate the contamination delay of the end gate for the shortest pass。

😊，Does it make sense， any question？But。Okay， so。Now Im going to provide some examples about propagation delays for some different gates。

 so here is an example of Rial Nant2 gate actually is from。😊，I see they are actually very famous。

 74 Xx， and they are from Texas Instru， as far as I remember， in the past they had TTL。

 which is actually completely different technology to make your circuit using BJT trans source。

 which they are different from Mmos。But after that， they also started using CMmos。So in this IC。

 you can see that you have four N gates。And you can use each of them separately， essentially。

So what I want to show you here is that essentially depending on the voltage。

 the supply voltage that you apply to your IC。You're going to have different latencies。

 so as you increase your supply voltage， your latency decreases。

And depending on the temperature that you are working on you have different latencies。

 so essentially you can see that by working on the lowest temperature and also the maximum voltage your latency would be7 nanosecond but it can be up to 135 nanosecond if you work with2volt and also the temperature of 125 so that shows you that basically propagation d heavily depends on voltage and temperature。

It also depends on the way that you implement your circuit。

 so here is an example of two different way of implementing multipleplication server to one。

This is the way that you calculate the meanter and then you do or and this is another way that you use a trit buffer and you can see that the kind propagation delay are different between these two designs so depending on how you implement your circuit you're going to have different also latencies。

Here is also another way of implementing multiplexer using two to one multiplexs。

But it also has different latencies。So basically the goal for this slide one to show that essentially these latencies of our circuit are heavily dependent on the voltage temperature。

 the way that you design and also the input vectors so we didn't show that here but essentially when you change for different input vectors you're going to have different latencies and our tools that they need to deal with all these latency calculation they actually need to consider different input vectors for accurate estimation。

😊，But here I want to provide this disclaimer that essentially it's not always this easy to determine the long and short path。

 so you observe that in that circuit if it's so easy to see what is longest and what is shortest。😊。

Basically not all input transitions affect the output， so this is very important to verify and also。

It can have multiple different passes from an input to output so your output is derived through different passes and you need to deal with all of them together to understand which one is the shortest which one is the longest so it's not really easy and usually it's automated using cat tools in reality also circuits are not all bit equally so different instances of the same gate have different delays here I showed you real Is that with some delays but in that theory also we have different version of that IC even for Ngate that they have different delays and access latents different delays essentially and wires also have non-zero delay because essentially wires also can be modeled by capacitors and also resist source and it can increase with the length。

And temperature voltage also affects circuit speeds。Yeah。

And even with when you put all these together， you can actually see that sometimes it can even change the critical path of your design。

 so when you use a different circuit and with different temperature also with different voltage。

 you might have a completely different critical path as you thought before。So in the end。

 designers assume worst case conditions and run many statistical simulations to balance yield and performance。

This is a normal usual way of designing， but this consideration of worst case and designing for worst case scenarios actually cause a lot of inefficiencies in our two day systems and you're going to see a little bit more later in our lectures that。

😊，We don't need to be that you know strict and always design for worst case。

 so you can also design some intelligent techniques that can decide based on the situation， you know。

 it can work for the best case or sometimes basically try to make the better the more intelligent decisions on the status that you have there。

 yes so doesn。It actually we will reach that later soon， yes。啊咁。

Those lawyer who to who can as a capacity， because I understand how it works as a。

That's also a bit out of scope of this course we can discuss later offline。

 but essentially if you're look into electronics。Espec usually you're especially when you have long wires。

When they want to model the way of you know the wire。

 they need to consider some capacitors and resistors， so there is a lot in electronics about that。

 but we can also discuss it off。Any other question？Yes， why does aging of the circuit affect。What。

 why what sorry say。Oh， aging， okay。Ageging can affect the effect effectiveness of your transistors。

 essentially， that's one reason， for example。 So your transistors when you。So normally， for example。

 you consider that your transistor when it's on， you know， it can drives that much current。

But after using it a lot， you know， doing it on and off on and off。

 it can cause some issues so its performance of that transistor can reduce there are also many other reasons for that which is again out of scope but we can also discuss offline if you're interested。

Was that insightful？我， yeah。Good。Any other questions？Good。So。Yeah。

 this is a summary of what we have discussed already about these delays。

Now let's also quickly take a look at glitches that we briefly talk about it。

So glitch or actually one input transition causes multiple output transitions。So here is an example。

 look at this circuit， we have this initial estate。And basically， we want to。But， no。

The initial essay actually was011。And the output is one essentially。

 and you want to move from one to0， so these input ones go from one to0。

So let's see what would happen。后。So the thing is that usually glitches happen when you have different paths to drive output and you have slow and fast paths so here you have this slow passs that's pass through three gates and here is your fast paths that pass through only two gates。

So as a result， you can see that the output would go from1 to zero。And then to one again。

 why is that？Because when you move from1 to zero here。

So this becomes zero and the output of this end would be zero and because of this or operation。

That this initiative was also zero， so this or operation is going to make the output to zero。

 but after some time you also get another value for this or which is one and then you need to go to one essentially so that's the reason that you might see somebleitches in your circuit。

So， glitches。Yeah， here is basically the diagram that I already discussed。

 why it's happening like that and the output for a very short amount of time。

 it can go to zero and then come to up to high voltage。Yes， and that time is T P D minus TCD。Yeah。

 around that， yes。But it's not that easy to calculate like this。 I mean。

 you can use this abstraction in your mind， but usually these delays are not。

And they don't don't don't they are not calculated like these numbers like these equations easily。

 so there are a lot of sorry。Like can to change。No， we don't we don't navigate。

What did you ask somebody like， is it just probability where is that。No， no， it's not probability so。

It is like。So first of all， these delay like contamination delay and propagation delay。

 they have very exact meaning， for example， propagation delay means like 50% of input to 50% of output something like that。

 you know。😊，So if you consider that， then you cannot easily say that you know propagation delay minus that so these are not that great。

 but I like your abstraction basically you know， it's good for understanding。😊，Any other question。

Okay， so this is optional I'm not going into it in detail if you were interested enough and you checked Car map that we had some lecture on it。

 not lecture， some slide that was optional you can there is a way to avoid glitches by going through the kernel map but I'm not going to cover it because you can check it if you're interested later this is optional as you can see。

But essentially you can what you can do is adding a circuit here， this additional end gate。

 so you can see that now this circuit is not minimal， so you're adding another gate。

 but by adding this you make sure that there is no glitch in your output。有。

So now the question is that do we always care about galitches？So first of all。

 leak fixing glitches is usually undesirable because it can consume more cheap area。

 more power consumption， and more design effort。And the circuit is eventually guaranteed to converge to the right value regardless of glitchiness。

So the answer is that no not always， so if we only care about the long term of state output。

 we can safely ignore glitches and it's off to the designer to decide if glitchches matter in their application。

So glitches also can affect some unnecessary dynamic power consumption as well because your output is going down and then coming off。

 so that's some power consumption that you're consuming。To avoid glitches， if youre at circuits。

 you know that those circuits are going to also consume power， so it may not force it。But。

You remember that， for example， when I was presenting about million more machine。

 I said that more machines are better in terms of avoiding glitches。

The reason is that in millli machine， when you change the input。

That input can also cause some glitch in your output。

 and that output might be also the input for some other millli machine。

And that can also cause some glitches in some other another millli machine and this can propagate so one simple glitch can actually propagate to many。

 many other circuits which can consume a lot of power so that's why we actually when we design our sequential circuit we usually prefer more machine as long as they don't you know they don't need to a lot of more states compared to millli。

And they can work very well for glitches， for example。Okay。

Now we can take a look at sequential circuit timing， which is a bit more interesting。

This is a recall for you that D flipof， as you remember that basically flipflop samples data D at the active clock H。

😊，So the important thing about DFF is that data must be stable when sampled。

Meaning that at active clockage so this is your clock cycle， so your clock cycle also is not ideal。

 so it cannot not you know goes to one sharp so it's going to be like diagonal and then essentially your data in order to be sampled。

Reliably。Should be a stable from this amount of time before rising edge of this clock。

 so this amount that we call it setup time。And it should be also stable。A bit after the rising edge。

 which we call it hold time。So if you dont follow， if you basically don't follow it。

 then you might get into some meta stability situation of Dlu flow。

 and then essentially in the end you don't know what is stored in that Dlu flow。So setup time。

 the definition is that time before the clock edge， that data must be stable。

 meaning that there should not be basically the data is not changing。

And whole time time after the clock edge， that data must be a stable。

And there is also another terminology aperture time。

 which is time around clock age that data must be stable， which is the summation of Tt andhold。

You had for no， okay， Yeah， I would we use an enabler for us。Sa the necessary sorry be using。嗯。

So for enable the flipfl， that， yes。For enable signal also you should make sure that you activate enable signal long。

 I mean， soon enough。But the thing is that you are not sampling enable basically。

Signaled in your D fl， it only talks about your data。The way that we implement you're asking， okay。

 no no， no， no， it's not about enabled you're going to see how we ensure that soon， yeah， yes。😊，敵ます。

Is its that don't care always have to flow。This is far。Yeah， like when you're saying that okay。

 D is changing， you know because there is a circuit there might be a combinational circuit that's driving D data here right so that circuit is causing some D to be like changing。

😊，There might be a lot of changing here， but I don't care。

 but what I care is that from this time this should be a stable。Yeah。Any other question？

So this is what I talked about mental dis if D is changing when sample。

 mental dis can occur and free flop output is stuck somewhere between one and zero。😊。

In the end output eventually settles， but this is not determined non deterterministically。

 so you don't know if it's one or zero essentially。

 and this is an example that for an N or latch that this is the region for meta stability that you don't something between one or zero and in the end you converge to one or zero in the end。

 but you don't know because this is non determinististic。



![](img/cb6e40a2240f8c7095503d555bd1d173_3.png)

So you should avoid， basically designers should avoid violating setup up time and hold time。

So similar to combinational circuits， we also have some timing that we should define for flip flops。

So the moment that we have this rising edge of clock and the amount of time that takes basically takes time for the output to react。

 so we have two， one is that contamination delay clock to Q essentially TCCQ。

 which is earliest time after the clock edge that Q starts to change， which is unstable。

 and we also have this propagation delay clock to Q。

 which is latest time after the clock H that Q stops changing， meaning that Q is stable。So yeah。

 essentially from this figure， you can see this is propagation delay from clock to queue。😊。

And this is your contamination delay from clock to queue and Q starts changing from this time and it basically stops changing and it's stable exactly at this moment。

Yes。In the stable state。Here the thing。Because your circuit as I said。

 like the way that we implement you flufl right it was for example two latches。

 first and second latch and each latch for example is a D latch and has。

 for example several n gates right it can be also some different version of it but overall there are some gates and all these gates needs to react you know to have some basically to have your output right so for example your output wants to rise from zero to1。

So it cannot get to one immediately。It will take some time and when you sample during that time。

 for example， you can see that okay， it's not so your one logic one might be like5 volt， for example。

 you know， so if you sample you're going to see that okay， at this moment my output is one volt。

Which is not zero， which is not one as the logical one。

Then you need to wait a bit more you're going to see okay my output is three volt and then fourvolt and then in the end iss going to be5 volt so you always want to have this stable situation that your output is zero volt which is logic zero or high volt。

 which is logic1。And between that is your unstable situation that you want to avoid essentially。

Any other questions， yes。It doesn't。Yeah， it can also depend partially on the gates that you are using。

 but in the end for contamination delay， it depends on your shortest path of your circuit and also when you want to calculate contamination delay。

 you need to actually consider best case scenarios for latencies essentially。

 in the sense that you consider everything to be fast as possible because for contamination delay we want to be as conservativeservly as possible because we want to say that the latency。

 the latency of this circuit。Is not going to be lower than this amount for sure。

 so for that we are very conservative。Because if you don't you're going to see that is very important。

 but you should know that the latency of this circuit cannot come lower than that。

 so you're going to even if you use different gates， you know that okay among these gates。

 this gate can have much lower latency so I'm going to assume that for example because。

We want to be conservative in calculating contamination。Yeah。Christian。哭。Perfect。Okay。

 so this is also another recall for you to jog your memory。

 you know that in sequential system design we have flip flos or registers and then we have some you know combinational circuits and that combination circuit can also derive another register registers or flipF。

So the thing is that multiple leaf flos are connected with combinational logic and clock runs with periodsios。

 which is TC cycle time。And this circuit must meet timing requirements for both R one。

 register one and R2。In this example， for example。So we need to ensure correct sequential operation。

 meaning that for example talking about this R2， we need to ensure correct input timing on R2 specifically D2 which is the output of this combinational circuit must be a stable at least T setup before the clock H and at least until T hold after the clock age。

 so this is the definition for setup time and hold time you need to make sure that D is a stable during this aperture time。

So then this means there is both a minimum and maximum delay between two flip flos。

If this combination of logic is too fast， so when we have clock。

When you have this rising edge of clock， this register can basically start changing， right？

And then Q1 is going to also start changing， meaning that。Then we have this combinational circuit。

And in the end， D2 will also start changing。So if this combinational circuit is too fast。

 then it might be also the case that for R2， we have this Thole violation。

You can see from this example here that we have this clutch and then Q1。

Start changing at this moment， which is the contamination delay and。

The moment that you have this change in Q1， this。Combinational circuit also starts reacting。

And then you also have this contamination delay for this combinational circuit。And in the end。

 your D2 start changing at this。Point of time。Even though it should actually stay stable until this point。

 which is TH。So you can see that now we have Thole violation。

So that's why our shortest pass latencies are also very important， specifically for Thole violation。

And if your basically combinational logic is too as slow， then you might have T setup of violation。

So this it takes that amount of time until you have stable output， basically stable data on D2。

 but this already violate T setup because this D2 should be a stable at this amount at this point of time。

In order to make sure that setup time is basically preserved。

So now we have potential T setta violation here。So we always need to make sure that we have safe timing and that safe timing depends on the maximum delay from R1 to R2。

The input to A must be a stable， at least he setup up before the clock age。

So let's make some calculation， this is for setup time constraints。

So essentially your clock cycle time should be greater than。

So you need to make some calculation about the length of this clock cycle。嗯。

So you have this propagation delay from clock to queue， so that's why we have this TPCQ here。

 and then you have this propagation delay for your combinational logic。Plus。

 you need to make sure that your D2 is stable before setup time， so you add it also。

 then you need to basically that's your clock cycle。

 so your clock cycle should be at least summation of these values。

So this gives you some insight here whenever you see that your setup time is violated。

One easy way to fix is to just decrease your clock frequency or increase your clock failure。

Of course， this is not desirable because that can reduce the performance of your circuit。

 but at least it can fix the correctness issue of your circuit。😊。

But we're going to see that for whole time， this is not that easy。

So in in every clock cycle you can see that we have wasted work。

 this is the only useful work that we are doing because you are doing some computation。

 you're calculating with your combinational circuit。

 but these two like a propagation delay from clock to queue and also this setup time they are wasted work that you need to basically wait for that in order to make sure that your fully flos are working correctly。

😊，And this is actually called as sequencing overhead amount of time based at each cycle due to sequencing element sequencing element timing requirements。

 and these are sequencing elements essentially。Fiff flops。Any question？

Does this equation make sense to you？第四。T clock should be greater than these values。Okay， good。

Usually， it's not that easy。I mean， it seems easy when you see it。

 but you need to think about it actually a bit more and to digest it。

 but when you get the concept you're going to see that this is very easy。Okay， so that's the。

Set up time， and。Essentially for your critical path。

 critical path of your circuit in the combination circuit would essentially。

Determinine your clock cycle。Because in this clock stack you can see that this propagation clock to Q is kind of constant。

 it depends on your flip fl that you are using， and setup time is also constant。

 you need to assume some setup time for your fliplog that you design。

But propagation delay of your combinational circuit can be different。

 and it depends on your basically the circuit that you're implementing。So overall。

 design performance is determined by the critical path and that determines the minimum clock period yield or maximum operating frequency。

If the critical path is too long， the design will run slowly。😊，If critical advice is too short。

 then each cycle will do very little useful work。 remember that that combination of circuit is the useful work that we are doing and all other like propagation D of clock to queue and T setup up is they are the sequencing overhead that we have so we need to make sure that。

😊，Basically， that sequencing overhead does not dominate， essentially your clock cycle。Okay。

Now let's take a look at whole time constraints。So for a whole time。

 we want to make sure that our basically D2 stay stable after the clock cycle。

 after the rising edge of the clock， at least for TH。So for that。

In order to calculate the minimum latencies， as I said， because we want to be conservative。

 we go with contamination delay。😊，So， essentially。The minimum latency that would cause D2 to change is contamination delay of clock to queue and contamination delay of this combinational circuit。

 and this should be greater than hold time essentially。And you can see that。

This equation has nothing to do with clock cycle。And that's why if you have whole time violation。

 you cannot fix it by clock cycle， as I said， with setup time， if your setup time is violated。

 you can just reduce clock frequency。But for whole time。

You need to basically sometimes you need to actually change your circuit。

 and we're going to see in an example how we can do that。

So your contamination delay of your combinational circuit should be greater than T hole time minus contamination delay of your flip clock to queue。

Okay。So these are basically summary of these parameters that you can also check later。

But now let's go over these numbers with some with this example。So this is our example circuit。

 we have four flip flos here and two flip flos here。

 and then we also have these combinational circuit in between。

And these are the latencies that we're going to assume。

 this is contamination delay for clock to queue， 30 pickcuse propagation delay。

 clock to queue and so on and so forth。Okay， let's make some calculation。

We need to calculate first latency propagation delay of our combinational circuit。Anyone， any guess？

Yes， so we have at it's 35 peopleseds。That most will predates。So it's three times3 like。Exactly。

So that's your long dispa。What would your contamination delay you just go with the short testpas。

 so there are two actually short testpas you have these short short testpas and also these two short。

And then you also need to get your contamination delay， so for each of them。

 we know that the contamination delay per gate is 25。

 then the contamination delay of this circuit is 25 because of。

So now we want to check setup up time constraints。So we know that clock Per should be greater than this equation。

So we just make this calculation propagation delay of clock to Q is 50 plus 105 that we already calculated and setup up time which is 60 then you're going to see that okay clock period should be greater than 215 pixel again。

 meaning that your frequency can be at most。4。65 gigahHtz。That's your frequency。

Now let's check all time。So for the whole time， the contamination delay of your。F flop is。

TD and the contamination delay of your combination circuit is 25。

 so 30 plus 25 is 55 and you can see that it's not greater than your whole time which is 70 and now we have whole time violationage。

😊，嗯。So any idea how can we fix it？嗯。Yes。😊，Yes。Essentially， you need to add logic。

In order to basically， you need to artificially increase the latency of your circuit。😊。

So you add these buffers。And then when you these buffer does not change your longest pass。

 still your longest pass is dead so setup up time calculation is not changing at all。

 but for the whole time now you have basically contamination delay of two gates。

 so it's going to be two times 25 which is 50 plus。嗯。30， which is 80， so 80 is greater than 70。

 so now we don't have full time we。Makes sense。Okay， let's see。Okay。

 so I think I'm not going to start clockscu because this we need some time。

 so let's have break until 315 and then we will continue。早。嗯。な。I。Yeah。没瑰。なで。あや。あ。等我这是。どち。好己人。啊正系这个。

I see。ありうい。あの？Right。え。Yeah。然后。ね。Okay， let's continue。We still have a lot to cover today。Yeah。

So we already talked about。Sequential latency and how to ensure we don't violate setup up time and whole time。

But essentially to make matters worse， clocks have delayed too。Basically。

 the clock does not reach all parts of the chip at the same time。

 and that's we call it as clock isQ time difference between two clock edges。

So here is an example for this flip flow， for example， your clock reaches at this。

At this certain time， but then this is your cloud source。

It may take a lot of you know longest path to reach to the second free flow。

 so definitely this free flow would also you know see the clock a bit skewed。

 which is because of long slow clock passs。So here also showing this waveform using our abstraction showing of waveforms that this is your clock source。

And point A， because it's very close to crsource is observing the same， but in point B。

 we are observing a bit is， and that can cause issues。

Here is an example from a real processor Al alpha processor that they showed the clock S in the chip。

 and you can see that in the horizontal axis or vertical axis of your chip。

 you actually see different s cubes。So now we need to revisit the top time and whole time。

Whyd we have Clark excuse？So。The thing is that for setup time。

 clock can arrive at register two before register one。Meaning that。

Your register too would see the rising edge of the clock earlier than register one。

 and that's why is it important it's important because your latency。

Your setup time now needs to be increased。So I show you with this example。

So this is your clock2 and it comes earlier and this clock1。

 and then you can see that Q1 starts to change a bit late because clock1 actually comes late and that' D2 also gets delayed because clock1 comes late。

And as a result， if you don't consider the fact that you have clock two is earlier than clock one。

 then you may violate the top time。So in order to fix this issue。

 we need to increase potentially our setup time and in our equation we just add SQ to this equation and we call it as an effective setup time。

 so you essentially you need to calculate a divorce case scenario for your SQ and then you add that to your setup time and that would be your setup time essentially effective setup time that you need to use it in your calculation。

So for a whole time。We think another way around， we think that we consider the clock arrives at R2 after R1。

So that can increase the minimum required delay for the combinational circuit。Why is that。

Anyone can provide some interpretation。不。Yes， the signal starts changing early because is' fast。 Yes。

 exactly。So Q1 and D2 they start changing earlier。Because we get this rising edge of R1 earlier。

 essentially， and that can violate whole time for R2。😊，So in order to consider that in your equation。

 you need to add TSQ to your whole time as well， and this is going to be your effective whole time latency in the end。

Good。Okay。So yeah that's a summary that basically you need to that increase your sequencing overhead because you need to add that S to your setup time and whole time and then you're going to have less useful work done per cycle and designers must keep a Sw to a minimum which requires intelligent clock network across a chip and there is actually research lots going on in this topic that people try to clock you know design the clock network in order to make sure that clock arrives at all locations at roughly the same time there are many。

 many different ways of doing that H3 for example is one of the famous way of clock network but there are also many other。

But that's still a big problem for designers， essentially。Question。

I remember that I said that in the previous lecture we had this example that we wanted to divide a clock frequency by3 and we were using FSM you know to divide a clock frequency by3。

 and I said that okay， this is an example， but this is not the way when you want to change the frequency of clock cycles。

Because if you get the clock network actually you have a different layers usually in your chips to rot clock wires and when you want to do some computation on your clock to change your clock you basically need to bring that clock wire to the to your logics and that's cause some delay actually that can exacerbate your SQ and that's why people try to not touch clock network at all so try to avoid moving basically doing computation on clock cycles so the clock can be only use as the input for your flipflps。

 but not as input that you want to also operate on clock and make a difference to your clock frequency。

 there are some analog circuit like PLL for example。

 that they are designed in order to basically change different frequency。

 provide different frequency of the clock。I'm not sure in the F FiJ that you are using in the lab if it is provided or not。

 but for example in F FiJ also you can choose the clock frequency that you want your design work and there is a PLL there that actually by configuring that PLL you can choose between the clock frequency that you are looking for。

Okay， so now let's get to the。Another interesting part of this lecture。

 which is circuit verification。And the question that we want to answer here is that how do you know that a circuit works？

So we design a circuit。😊，There are several questions that we want to ask， is it functionally correct？

Even if it is logically correct or functionally correct。

 does the hardware meet all timing constraints， how can you test for functionality timing？

And to answer that， we have different ways of that， we actually rely on simulations a lot。

So there is formal verification tools like SAT solvevers。😊，That。They are useful。

 they can provide like theoreticalical foundation that this design works。

But they're also expensive and you cannot use them easily for very， very complex and big designs。

We also have this HD timing simulation like Vivado that you're going to use a lot in your labs。

 and we can also do these simulations at the circuit level at the transistor level。

 using the tools like a spiceice， for example。But in general。

 testing large digital design is not easy and it's the most time consuming design stage。

 there are reports that actually like 70% of the design time in a modern processor actually needs to be allocated for this verification。

So a lot of effort needs to be done in order to make sure that that design works correctly and basically test engineers。

 they have to do a lot in the design process of their modern processors as well as any logic like memory chips as well。

So we need to make make sure the functional correctness of all logic paths， timing power etc cea。

 of all circuit elements， for example you want to make sure that your circuit is not going to consume power which is not load for example you want to put a circuit in your for example ear to use it and that circuit you need to make sure that your ear does not bear does not burn essentially right so that circuit should not for example consume more than I don't know some microbot。

You need to make sure right it's not easy， so you need to test it and make sure that design is not going to consume more than some amount of power。

So unfortunately low level circuit simulation is much stored than high level like HDL and C simulation and the solution that people devise for that is that they split responsibilities。

 we usually check only functionality at the high level C or HDL。

 which is relatively fast simulation time that lowers high code coverage and it's much easier to write and run test and then we check only timing power and etctera at low level。

 meaning at circuit level for example， so for that we don't do any functional testing anymore。

And then instead we try to only make sure that the functional equivalence is correct。

 so our circuit has this function like we test the functional equivalence with the high level model of the circuit that we have。

And for that， also there are some theoretical foundation that people are following。

Meaning that if your HDL circuit， HDL code， you follow the principles well and you write a good code。

 I mean your code is synthesizable well。Then this gate level synthesized version of that or even lower than transor version of that transistor level version of that would work the same like in terms of functionality would be correct。

 so the functional equivalence would be there， but your circuit level simulation might not basically might violate timings and that's another issue which you need to fix。

But still， this functional equiubvalnence is also hard。

 but easier than testing logical functionality at low level essentially。😊，Any question？对起。

So we have tools to handle different levels of verification。

 we have logic synthesis tools that guarantee equivalence of highle logic and synthesized circular level description。

 that's what I said so in Vivado when you input HD your HDL code the logic synthesizing tool that you have and Vivado is not actually the exact great example because the tool chain is for a Fiji but for example design compiler for a synopses。

 when you input your HDL code and your HDL code is synthesizable then your gate level output is actually has this exact logic that you are looking for。

But for timing verification， you need to use some other tools and this will check all circuit timings。

And there are also design rule checks to ensure that physical circuits are buildable， essentially。

So the task of a logic designer is to provide functional tests for logic correctness of the design。

 for the logical correctness of the design， and also provide timing constraints like desired operating frequency。

As well as also designer need to be involved also into timing as well as we already seen when we have whole time violation designer actually need to change the design so unfortunately the designer also needs to deal with timing as well a lot like how to fix the timing it's not only saying that okay these are my constraints and then make the circuit for me you also at some point the designer also need to find solutions in order to fix the timing violations。

There are tools and circuit engineers， and they will decide if it can be built， like in the end。

 tools and or circuit engineers will decide if your circuit can be built。

But we will first start with functional verification and we will actually go into a lot of detail in this part because you're going to use this a lot in your labs essentially。

😊，So the goal for functional verification is to check logical correctness of the design。

Physical circuit timing like setup time and whole time is typically ignored。

 like all time is actually usually or completely ignored in this logical correctness test。

We may implement simple checks to catch obvious bugs。

 but basically the goal is to not really make sure that your design is not violating any timing。

And we will discuss timing verification later so in this lecture， there are two primary approaches。

 one is logical logic simulation using C+ plus veryloc test routines or using formal verification techniques like sat solveware for example。

 but in our course we actually use logic simulation。So let me introduce you a test benchch。

 so test benchch is a module created specifically to test a design。😊。

We are designed that we want to test it， we call it the device under test， which is DUT。

So this is your test bench。That has different parts in this part you need to generate some test pattern like the patterns of different inputs that you are looking for。

 and then you input these test patterns to your design under test device under test sorry。

 and then you need to have a logic to check the outputs and make see that if everything going running correctly or not。

So yeah， again， a test branch provides inputs to the DOUT and that be these inputs can be handcrafted values or can be automatically generated using some sequential or random values。

And the test bench has to check outputlets of the device under test against handcrafted values again or a golden design that is known to be bug free we're going to see about golden design very soon but very briefly you may have a model of your design that you call it golden design and that usually is implemented with much higher abstraction and you're sure that that golden design is bug free。

Of course。To make sure that is also bug free， there is also a lot to do。

 But as long as you are sure that that golden design is v free。

 you can just compare the output of device under test with the output of your golden design。

 And then you can see that if your design works correctly we're gonna see more about that soon。😊。

A test bench can be implemented in HDL code written to test other HDL modules。

 or can we also circuit schematic use to test other circuit design。

 but we're going to use HDL code in this course。And as you also probably know。

 and we also discussed a bit yesterday， testment is not designed for hardware synthesis。😊。

So it only runs in simulation only and there are many commands in your test bench that they are not sthesizable。

 like definition of these timing， some delays that we're going to use in order to generate some pulse。

 so all of them are not really or maybe you have some function like print display I mean these are not synthesizable right but you're using them in your test bench in order to test your system for simulation。

And。This test bench can be also in HD simulator like Vivato simulator。

 or can be also in spice circuitcus simulations。For example， but spice circuit simulation。

 we are not covering at all in this course。 So don't worry about that。

Testment uses simulation only constructs like weight， for example， 10 nanosecond。

 or we are considering ideal voltage current source。

 and of course they are not suitable to be physically built。There are three ways。

 three common ways of very low test bench types， one it would be we call it simple。

Which in the end for input and output generation is manual and error checking is also manual。

 so you as a designer or the one that you are doing tests， you need to do all these tasks manually。

We can also do it have this in a self checking like input and output generation is manual。

 but error checking is automatic。And we can also do everything automatic。

 meaning that input output generation and error checking are all automatic。

 and we're going to see with some examples very soon。

So we're going to use this silly function to walk through these different kinds of test bin。

 basically the common ways that you can design。So this is a definition of your module and you can see that we are using gate this completely structural way of programming and we are using gates。

 not not and and or of course this is not the best way。

 but this is very good way of designing for the sake of our example that we're going to see today。

So before jumping through the different basically test bench that we can write for this code。

 let me introduce you some useful very large syntax for test bench one of them is initial block which is similar to always block you can actually also have some sensitivity least for initial but here for example we don't have an initial actually is executes only one so when you enter your initial block that's the difference with between initial and always block in all this block you always basically try to repeat it but in initial you only executed once。

😊，So you can use it in your redlock。And also this notation like hashtag 10。

 showing the latency that we wait or for example， do nothing for 10 nanoseconds。

And you can also print stuff in your console in Vivado， for example。

 you can use this Op dollar display and basically this string that you're going to be showed。Okay。

 now let's start with simple test management。This is our test Bench1。

 and we want to test our city function。So we need to instance instantiate from our function as you know so when you have this test bench actually your test bench is going to be your top level module。

 remember our bottom of design so your test bench you can consider as your top level module and there is a sub moduleule that you' are actually instantiating and that sub moduleule you're going to test it。

So your top level module test bench has no input output。But has some values like in。Internally。

 has some wires and registers。So you instant from your module that you want to test it。

And then you in the initial block， you're going to basically give some values to these。Inputs。Like。

 for example， you put a0， B0 and C0 and then wait for 10 nanosecond and then change the input C to1。

 then wait for 10 nanosecond and then another bit vector， another and another。

So once you have this and you can run your simulation。

 and then you can generate the waveform diagrams。And in waveform diagrams。

 you need to manually check basically the output and make sure that the output actually is correct for a different combination of these inputs。

So as you can see that this is easy to create， buts not really easy to check and it's not really scalable when your design gets more complicated。

😊，So as Pro is like easy to design， can easily test a few specific inputs like co cases。

 but as cons like not as scalable to many test cases and outputs must be checked manually outside the simulation。

 which is not easy and it's very much similar to printf style debugging when you want to debug for example your Java code C+ plus you know。

 one way is to add a load of printf you know， which is not the best way of debugging for sure。😊。

Another approach would be self checking test bench。So。Yeah， again。

 you are instantiating from your silly function and this is your initial block。

 you' are initializing these values。But then you're actually checking the output of these input in your code as well。

 so you are not checking the output in your vform， so you know that the output should be one for this input combination。

 so you are saying that if one is not equal to1， then display this input vector 000 fade。

So and with that， you can see basically some errors essentially。

 so Pros is still easy to design and easy to test。Simulator will print whenever an error occurs。

 but cons is still not scalable to millions of test cases and easy to make an error in hand coded values。

 so you make just as many errors writing a test match as actual code so there is no guarantee that you are not making errors while you are writing your test match right because I mean you can make errors。

 humans make errors。And hard to debug whether an issue is in the test branch or in your device under test。

You can also make it a bit smarter and you can use test vector file so you can put different basically you can make a file and then put inputs input vectors and the output that you are looking for in them like here is an example。

And then so this actually test vector can be created manually or automatically。

 manually designer just you know Fi it do or automatically can be also basically created using your golden model that we're going to also see very soon。

So the way that we use this test vector is that you need to read values from your file。

 essentially so you have a test vector and is' stored in a file。

 you need to read it for that your book consider that there is a clock so this clock has nothing to do with your the clock that you're going to you know add to your circuit for your sequential circuit。

 this is another clock that you're going to consider only for your test bench。

So in the rising edge of your clock cycle， you read from your file。

And apply input to your device under test。And in the following edge of your clock cycle。

 you check the output on basically of your device under check to see if it's working well or not。

 we're going to see with example。But just make sure that don not confuse this clock cycle with the clock that you are inputting to your sequential circuit。

 this is different。Okay， so here is a very low code for that。😊，So yeah， this circuit， for example。

 again， our city function didn't have a clock， but here we define a clock specific for our test bench。

😊，And we need to generate the clock cycle for that。

 this is a very normal way of generating clock cycle in your test bench。

 you need to always block and you say that okay begin clock one and then you wait for five nanosecond and you make your clock zero and then you wait for five nanosecond this means that your clock failure is 10 nanoseconds。

And this will repeat all the time because your always does not have any sensitivity least essentially。

Okay， and in the initial also a statement， you need to read， basically you need to open this file。

 example the TV， the file that we have all the inputs vectors and output。

 and mapped that to test vectors and test vector is essentially defined here is as an array of test vectors。

It is each element is actually4 bit in our array， why is it4 bit because we need essentially four bit right one three of them for inputs and one bit for output essentially so that's why we have four bits for each element of this test vector。

So you open this file and copy to your test vectors。

 so these read vectors and you also reset initial vector norm to0。

 meaning that you want to start your test from zero。

And the number of errors that you have observed so far is reset to zero。

And then you also reset the system。And then you wait， essentially， so that's your initialization。

Then we have this always at the positive edge of clock that you in the positive edge you are giving input to your basically device under test。

 so at the positive edge you read from test vectors vector none which is initially zero。

 so you are reading the first element。And then you're mapping that to your inputs as well as why expected。

 why expected， meaning that the output that I'm expecting。

That's why you are basically moving the output to this why you expected。

 so there is a stored in your fight essentially。And then we apply ABC inputs on the rising edge of the clutch and get what expected for the checking the output on the following edge。

So this rising and falling age actually or chosen only by convention， your book actually uses this。

 but you can use any part of the clock signal as you wish。

 so this is not really important just the concept is important here。So in the ne edge clock units。

 if it's not reset。😊，We need to check so if the outputs of the circuit in that negative edge。

Is not equal to my expected， then we can display errors， and then we increment our errors。

And in the end， outside of this， also we increment our vector none in order to test the second element and we need to go further and further。

And at some point you need to see that you need to have the end of your test vector。

 so you may fill it up as four bit binary Xxxx and you check it if it's that the case。

 then you say that okay， test completed with how many number of errors that you see。

So this is easy again to design and easy to test。And simulator will print whenever an error occurs and no need to change hard coded values for different tests。

 so you have this test vector file and you don't need to hard code it。

But as cons maybe be still error frun depending on source of test vectors。

 so how you generate that test vector essentially， are you using golden basically logic。

 golden model of your device， if that's also the case。

 how you're sure that that golden design is error free， so it is not really easy to check。

And also more scalable， but still limited by reading a file。

And might have many more combinational paths to test than will fit in the memory。

But we also have another way of testing， which in my opinion is the best one， automatic test bench。

Which we use golden models， any questions so far？嗯。Okay， good。

So E goldenden mother represents the ideal circuit behavior。

And must be developed and might be difficult to write。

So this can be done in any language or even in verylock for our basically silly example。

 the golden model would be as easy as this right so you had this basically veryloc code with a lot of gates but you could easily write the code with this assign a statement essentially so that's a high level abstractseion。

😊，So here it was easy， but for many actually real device designs actually coming up with a golden model is not that easy actually。

 and there is a team in the design that they are actually working on making this golden model。😊。

And make sure that is error free。Okay， so golden model is usually easier to design and understand and golden model is much easier to verify。

We hope for that， actually。So the automatic test bench is like that。

 so you generate test pattern and then you input that to your device under test as well as your golden model and then you check equality of the outputs of these two models essentially so the challenge is to we need to generate inputs to the design and this can be sequential values to cover the entire input test space or can be the random values。

Or something between or。Many other ways， also different ways。

So this is a way of implementing this test， so now you have two modules that you need to instantiate。

 you instantiate from device under test and also your golden model。

And you give them the same input vector， ABC and ABC。

 and then the outputs you need to check them if they are correct or not， essentially。

 so if output of device under test is not equal to output of your gold model。

 then you need to display some error is happening essentially。So as pro。

 of course this output checking is fully automated and could even compare timing using a golden timing model so people also came up with designing golden timing model to check timing of your circuit。

 it's not in the scope of this course， but you can search for it if you're interested。

And is' highly scalable to as much simulation time as it's feasible。

And leads to the reason that scalability is important because we want high coverage in our test。

 so coverage meaning that how many test vectors， for example。

 you could input and how much you can basically check the outputs and in the end if you have high coverage。

 then you are kind of confident that your design is working correctly。

And also the better separation of role， so now we can separate designers。

 some designer can work on device under test and some other designer can work on the golden model。

Devicice under test testing engineer can focus on important test cases instead of output checking。

 for example。And as Khan's creating correct well model may be very difficult and coming of it。

 good testing input may be difficult as well。So however， even with automatic testing。

 how long would it take to test a 32 bit add？So in such an add。

 32 bit add meaning that you want to add the two numbers and each are 32 bit。

 so overall you have 64 inputs。So you have two to the power 64 possible inputs。If you test one input。

 one input pattern in one nanosecond， you can test 10 to the power  nine inputs per second。

 for example， meaning that this amount inputs per day and this amount per year。

 and you still need basically 58。5 years to test all possibilities。

So that's clearly show that root force testing is not feasible for most circuits。

And we need to prune the overall testing in space。So that's why we can use， for example。

 formal verification methods to choosing important cases so you can you know。

Benefit from different way of ensuring the correctness and combine them in order to have more intelligent way of verification。

😊，And as a conclusion， I will say that verification is a hard problem and that's why actually。

 as I said， that 70% of the design time on average is allocated to the testing and verification of the modern processor。

 for example。😊，Any question。And all these test set devices。

 they might also they may fail after when they come to the market because you cannot have 100% coverage。

 essentially your test。Okay， let me also quickly go over timing graification and then we will conclude。

😊，Any question？But。So for timing verification， we have approaches。

 we can also do it at high level simulation and because we can model timing using this notation。

 hashtagX statement in the device under test。whichhi is actually useful for hierarchical modeling。

 we can insert delays in flip flops， basic gates memories， etcter。

 I also briefly mentioned that in cell libraries that you have there are delays of different cells。

And after synthesizing your circuit， your HDL code。

 when you synthesize it to gate level or to gates that they are defined in your cell library。

Then you can do simulation， which is postesis simulation， and in that。

 you can actually all these numbers， if you open that very low code。

 you can see that all these hashtag values。Minimum typical and maximum latency of gates， flip flops。

 everything is annotated in that very lock code。😊，In order to make sure that when you are simulating this circuit。

 you're considering timings of all these circuits， and that can help you to verify basically timing violation or not in your circuit using simulations。

So this is usually not as accurate as real circuit timing， of course。

 because we want to when we are using these numbers， we are basically abstracting the latency。😊。

And some sometimes we are actually considering worst case numbers， you know。

 in order to make sure that the the latency that I'm considering is not is。For sure。

 my design would work better than that。 So you actually consider sometimes a worst case latency when you want to embed that latency。

 you're very local。 So that's why in the end， if you have this real circuit timing。

 that would be best， but you cannot。Build your essentially your circuit。

For every timing verification。But there is also a way that you can use a circuit level system simulator like HS sps。

 for example， that you can syntheize and then try to simulate sp model of your circuit。

That has the model in transistors and this spice model can basically model all these resistance capacitors。

 transistors。That you have and then you can probably get much better understanding of your latencies。

But there is unfortunately there is no one general approach。Which is very design flow specific。😊。

For FG ASI， et cea， technology has a tools for this， for example， Xs to Rivado。

 what we are using for the lab is actually for FGs。😊，For ACI， for example。

 we have synopses or cadence tools， these are different companies and that can be used for VLSI designs。

So the good news is that our tools will tried to meet timing for you。

So we just define setup time whole time， I mean whole time is actually defined by your still liability essentially。

 but setup times for example， you can define， I'm sorry， setup， you can also define setup time also。

 but you also define， for example， the frequency that your design you want to work on and you can also define the clock SQ。

And basically， these tools， they are doing their best to make sure that they can meet the timing that you are looking for。

And in the end， they usually provide a timing report or timing summary。And in this report。

 you can actually get some understanding of worst case delay pass。

 like what is the worst case latency that you have from which input to which output？And for example。

 you can also get maximum operation frequency or any timing errors that were found。

But the bad news is that the tool can fail to find the solution。

And the desired clock frequency might be too aggressive and can result in setup time violation。

 for example， on a particularly long price。Or you might have too much logic on clock pass that can introduce excessive clocks。

 as I said， you should avoid having too many logics on your clock pass。

And timing issues with asynchronous logic also they can also cause issues。

So the tool will provide hopefully helpful errors and reports will contain paths that fail to meet timing。

 like when when it's failed， you can actually get query some of these reports and you're going to see that okay the setup time fail in a pass from input a to output y for example。

 and then that gives you a clue to go into your circuit and try to optimize your design in order to make sure because you can actually help your basically tool in order to finally meet your desired frequency for example。

Okay， and that these reports can give you a place from where to start debugging， for example。嗯。

So now the question is that how can we fix timing errors， so meeting timing constraint。

 unfortunately， this is often a manual and iterative process。

So meeting a strict timing constraint like high performance design can be tedious as well。

So we can try sentences and place and wrote with different options。

 so some because as I said these tools they are doing they are doing a lot of heuristic when they want to optimize and meeting your constraints so sometimes you can just repeat。

And that repeat can maybe fix the problem you know。

 because when you repeat and then you start with a different random seed。

 then that heuristic may work a bit differently and then you might be lucky and then everything would be fine you know。

 and then you're gonna get what you wanted。And you can also provide us some hints to these devices。

 to these tools for place and road that can be actually used in advance， for example。

 place and road for refugeGs。There are some people that they go into the place and route find output。

 and they try to edit place and route in order to make sure that， for example， they reduce latencies。

So you can try that， but in the end that may not work。

 and you can also manually optimize the reported problem path so you can simplify complicated logic。

You can split up long combinational logic paths， for example， if you have millili machine。

 you have several milli machines and you're connecting all these milli machines you have a very very long combinational circuit and that can affect your timing so you may decide okay now I'm going to use more machine and that can fix a lot of problems for example for you so a split up long combinational logic pass is one way it's not only by changing from milli to more you can also add registers in between so you can actually divide a combinational circuit into two by adding a register in between。

😊，And you're going to say a lot about that when we talked about pipeing in the process or in the microarchitectural process。

And also recall that fixing whole time violation， we might need to add more logics。

But there are some principles that we need to basically follow when we want to meeting timing constraints so let's go back to the fundamentals clock cycle time is determined by the maximum logic delay。

And maximum logic delay that we can accommodate without violating timing constraints so there are several good design principles that we should follow we're going to also look into this design principle later on when we also look into microprocessor design。

😊，But here I'm going to also provide them so critical past design。

 we want to minimize the maximum logic delay because this can maximize your performance。

And your clock frequency is defined by your critical pest design essentially。😊。

And you want to have a balanced design， so you want to balance maximum logic delays across different parts of the system between different pair of free flows。

 so you you might have one， for example， flip fl and then combination of circuit， another flip flow。

 combinational circuit， another flip flow。😊，So。Your clock frequency is defined by the longest combinational circuit that you have。

 You might have some combination of circuit that they are quite fast。

But your clock frequency cannot determined by them because you have other combination circuits that are quite as slow。

So it's very important that you make sure that your design is balanced。 For example。

 all these combinational circuit have the latency around， for example，200 piconds。😊。

It's not good that， for example， you have some combination of circuit in between that the latency is like。

 for example， 50 and some combination of circuit that the latency are， for example， 200， 500。

So then your design is not balanced， and that's one of the principles that you need to follow in order to have a very good design。

And another design principle that we call it， we like to call it bread and butter is that we optimize for the common case。

But we should also make sure that non common cases do not over the design， for example。

 in your this actually is going to be more。Detailed and easy to understand when we get to the micro process or design。

 But for example， when there are some input vectors or input patterns that you know that these input patterns might happen much more like very very likely and there are some input patterns that they don't appear much or they may not appear at all。

 So if you know that information you can actually try to optimize your system your design for the input vectors that they are very likely happen so that can provide better overall better performance。

 So that's why we are saying that you are optimizing for the common case but we should also make sure that those non-com case。

 they do not overwin the design as well。Okay。So we learned a lot in this lecture。

 we cover timing in combination circuit， timing in sequential circuit。

 and we also look too briefly about verification， how to functionally verify and timing verification。

And that brings us to the end of today's lecture and also end of digital design part of this course next week we're going to start with computer architecture and we're going to start with for Newman and topics that they are quite interesting Any questions。

Then I wish you a nice weekend。 See you next week。

![](img/cb6e40a2240f8c7095503d555bd1d173_5.png)

です。