# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p02 -02- L2_ Combinational Logic (Spring 2025).zh_en -BV1iV1XBWEJW_p2-

![](img/eff507112917a3e6efb2d8a0453a5fad_0.png)

left off。Yeah need to test it like。Both the critical path。Okay， let's get started。

Well come back Fridays are always thinner in terms of people are attending but's because it's still good to see an almost full room I don't know if there are people along the other room but in the other room that I still cannot see maybe there are some。

And no， you can come here， there's space here， but maybe you like the。Fewer people in the other room。

Anyway， talk we're going to continue wherever we left off yesterday。

 hopefully yesterday was exciting。Was it interesting， cool？Okay。

 we're going to learn more stuff today， hopefully but。Okay。Before I start。

 I'll remind you there's an extra credit assignment that you know there are some readings and I would definitely recommend you to the readings。

😊，Because they will help。And these are the readings that are kind of foreshadowed for the future next week。

Today what we're going to cover is build on what we did yesterday。

 yesterday we started with some basics of course plus we talk about transistors。

 we talk about transistors a switch I'm going to very quick to overview that we started building logic gates we're going to build more logic gates today we're going to talk about Boolean algebra have you covered Boolean algebra before。

😊，Yes， at EthH。Yes okay I'm going to go through those relatively quickly maybe there are parts of boolean algebra that you did not cover but that's going to be relatively quick well hopefully when I say that usually it takes time and then we're going to jump into a combinational logic circuits Boolean algebra is useful from our perspective so that we can design circuits and also we can minimize them we want to reduce the cost of the circuits and boolean algebra both the theory as well as design tools that build on that theory will enable us to minimize the circuits as you will see and then we're going to build combinational logic circuits I already said the last one。

 minimizing logic circuits okay these are some reminder slides we discuss that all computers all modern computers at least are built using the same building blocks and remember this is just to jog your memory these are some of the topics that we delved into yesterday we talked about general purpose versus special purpose the differences between them so this is an example of a tradeoff and。

😊，right that we did at a high level at least and then we jumped into introducing transistors and we discussed transistors at an abstraction level that's going to be useful for us in the rest of this course。

 we don't talk about the analog operational properties of the transistors but we really talk about the transistors at a as a digital substrate。

 you turn it on or off。😊，That's it and that's all you need to know really in this course and we talked about different types of transistors。

 n type and P type， and we said that n type is turned on。

 meaning when you apply it hurt on when you actually apply high voltage to the gate。

 meaning it acts as a piece of wire， it's turned off if you apply low voltage。

 zero volts to the gate， it acts as an open circuit， the wire is broken basically。

This is a very nice abstraction to enable building digital circuits。😡。

And we showed that you could actually light a bulb by replacing the wall switch with a transistor。😊。

N type or P type。Okay and then we started building logic gates。

 you remember this picture from one of the later slides that we covered yesterday we built the inverter first and you can see that inverter requires two transistors p type connected to the power rail high voltage and n type connected to the ground rail which is low voltage and this is a structure that we introduced I'm going to talk about that again complementary metal oxide semiconductor you have p mods at the top and n mods at the bottom and this inverts the signal single input signal to the opposite value if it's three wts you get zero wts if it's zero volts you get threevolts but for later we're going to basically say three wts corresponds to high logical one and zero wts corresponds to a logical zero this could be encode quoted in different way of exactly opposite way you need to encode in one way and if you encode it。

😊，Logically， you basically get an inverter in the logical domain makes sense， right？

And then we built a Nand gate which essentially is end and an inverter behind it。

 if you think about it that way and this is the function and we call this the truth table if you remember truth table specifies the operation of a circuit by enumerating all possible combinations of the input in this case you have two inputs AB which means that each of them take can take two logical values so you have two to the two two to the power of two combinations。

 four combinations for each input combination you specify what the output bit should be。

 this is a two input one output function as you can see and we can build an input and n input functions as we will see later on today these are very simple basic building blocks to begin with and we said that if you want to build an end gate you need to start with Nant and then add an inverter behind it and today we're going to go a little bit deeper as to y that is the case if you actually read Harris and Harris section 1。

😊，And probably you figured out why this is the case。

 why we cannot build an end gate with only four transistors。

Because if you actually know the operational principles of the transistors。

 just like a perfect switch， you should be able to build an end gate with only four transistors。

 but we cannot because they're not perfect switches as we will see。

 so an end gate is essentially an end gate plus an inverter added to it so the inverter actually inverts this output over here as you can see this output here is the inverted version of what you get out of the end gate。

😡，And these are the logical， I guess module level pictures of these basic building blocks and as I mentioned yesterday。

 the bubbles are always inged， bubble always says inmer and we're going to have some fun with bubbles today。

😊，We're going to do some bubble pushing。Does anybody know about bubble pushing？Okay， you will see。

It's fun。😊，There's actually a lot of fun you can play with you can do with gates but we won't have enough time so this is the last slide I finished with I basically said this is a general form we use to construct any inverting logic gate this is CMOS gates structure you have two networks you have a POSs you have one network that's made up of PmoOS transistors it could be transors in series or in parallel but these transistors are connected to three walls because POSs transistors are good at pulling up the output。

 they're very bad at pulling down you never connect them to the ground。

 you always connect them to the top which is in this case three wallst。😊。

And then when the transistors are parallelalleled， the network is on， when the transs。

 if one of the transistors is on， that's the operational parallel， if you go back over here。

 for example， these two transistors are in parallel。

 the PMOS transors are parallelalleled and the three watts get connected to the output only if one of them is on or both of them are on。

😊，Well， not only if one of them is on or if at least one of them is on okay when the transors are in series。

 the network is on only if all of the transistors are on just like we have seen here。

 these two N transistors， both of them need to be turned on so that the output is connected to zerovolts and you can see that in the true table over here。

 both of the input should be one so that these M transors are turned on so that the output gets pulled down to zero。

😡，And these are complementary， meaning when both of these are on。

 both of these are off because of the way we introduce the transistors。

 Pmost transistors get turned off when you apply one to their gate and both of these are off。

 so this part of the circuit gets disconnected from the output。😡，Okay， hopefully this makes sense。

 right？Okay， so I already said actually， what I was going to say over here。

 exactly one network should be on and the other network should be off at any given time。😡。

Because if you violate this， if both networks are on。

 meaning if three wts over here gets connected to the output and also zero wts here gets connected to the output。

 then you're in trouble。😡，Because this is called a short circuit and you'll get likely incorrect operation。

 this is basic electrical principles again。If both networks are off， this is actually not that bad。

 meaning neither three wts nor zero wts gets connected to the output。😡。

This is also called output is floating。😡，Meaning opposite undefined。

 in some cases this may be acceptable， as we will see later on。😡，In many cases。

 if you're going to use that output for something， it's not acceptable。

 but if you're actually going to use that output to load a wire。😡，It could be acceptable。

 We're going to see tri state buffers later on tri state buffers actually operate this way。

 So the first is very bad。 you will burn the circuit。

 Perhaps the second is depends on what you're doing If you know what you're doing。

 then this may be okay。😡，Does that make sense if it doesn't make sense wait until the tri state buffer later today Okay。

 so why do we have this structure， you may say that okay， I could build a much better end gate。😡。

Does anybodyDid anybody try， yes？You can have the and。是婚是。Exactly， yes， you could add the。Let me see。

 you could you can have the。And Moton series。It connected to the three walts。

And you could have the POSs in parallel connected to the zero volt。If you think about it。Let me see。

 I think I'll do this。anybody can someone help me to do this？I don't know why it's going this way。

 maybe you can do the computer。Let's see if we will get it right。I hope so。



![](img/eff507112917a3e6efb2d8a0453a5fad_2.png)

我。So this is three volttz。I want to build an end gate right， and this is my end moss。

This is my output。And this is my Pmoss and I never want to do this probably， but I'll do it。

So end gates will should give you a one if if both of the inputs are one， so this is a， this is B。

I also have a here， and I also have B here， sorry。And then this is ground。

And this is your output why in our terminology。Now this should be an end gate， right？

Because the output is assuming these are perfect switches。

 output should be equal to three volts only if A and B are1。😡，Otherwise。

 it should be equal to zero wts， right and it works。 It's complementary also。

 except the problem is these are not perfect switches。This transistor。

 this is N moss that I used over here， I violated what I said earlier。

 I should use only Pmoss connected to the high voltage。

 This N moss is terrible at pulling up the voltage。😡。

Because of the underlying operational characteristics。

 which you should learn if you actually design microelectronics。

 it will pull up the voltage to maybe 1。5 volts if you're like。😡。

And these are actually also terrible at pulling down the voltage。😡，So when one of them is zero。😡。

Then this actually also doesn't pull down very well， so maybe you get。

 I don't know some voltage is just not necessarily zero。😡，Right。

So this is good to understand if you don't understand the underlying operational characteristics。

 then you would basically， if you treat the transistor as a perfect switch。😡。

You would basically not understand this， right you can build an end gate like this。😡。

But because of the way。Transistors cannot work as a perfect switch because of their analog operational characteristics。

 and the reason is really whether they transmit holes or electrons， as I will mentioned。

 but I have not go into a lot detail because it's really analog circuitpy after this point。

 this end gate is not acceptable at least using POSs and NmoOS transistors。😊，Does that make sense？

Okay， now we can switch back。

![](img/eff507112917a3e6efb2d8a0453a5fad_4.png)

I hope I can figure this out， I guess。You can help me。

So probably you were suggesting this sort of end gate， right？It's a good try。

But not in this technology， you can come up with maybe some other technology where you could do it。

 but people cannot couldn't come up with that yet。Okay。

 this is what we need AI for AI basically I say switch to this and then it should be able to switch。

 right？😊，Okay， any question so okay， this is what I said over here in this slide。😡。

Pmost transors pass ones well but zeros poorly holes carry charge and holes are good at passing ones but not zeros。

 similarly Nmost transors pass ones poorly as a result because electrons carry charge and electrons yeah essentially they are very bad at pulling up the circuit okay that's you don't need to know this in detail。

 but I wanted to show you that if you try to be clever with the underlying circuit tree。😡。

If you don't know how the underlying circuit there really works。😡。

You may come up with something that doesn't make sense， right？So that's why you need to be careful。

 you really need to know how the underlying thing works。

That's why what we did was an abstraction and the abstraction was it's a switch under some conditions。

😡，Okay， that's why we built this end with six transistors as opposed to four transistors that I tried earlier。

And if you want to know more about it， you can read section 1。7。

 or you can take a microelectrons design course。 Okay， so let's take a little bit deeper。

 I'll ask you a question。 Which one's slower Transistors in series that are connected series or transistor in parallel。

Who says series is slower okay that's good who says parallel is slower nobody so you win so a series is slower because it's longer right you have longer wire and longer wires lit longer resistance and resistance is what leads to latency。

😊，The question is how do allevgate this latency， there are actually tricks people play again using underlying knowledge of transistors。

 I'm not going to go through this， but this is interesting to think about people build for example。

 this is a Norgate for input norgate that you can build with only NOS transistors without a PmoOS actually there is a POS transistor over here。

 but it's very weak。😊，People used to do this in the past when it was difficult to manufacture PO transistors。

Makes sense okay， you can convince yourself that this works as a foreign input no gate and it does actually。

 but today people don't do that as much unless they're really constrained by area or something this is actually good for area also as you can see yes。

 what does it mean your。😡，Weak meaning basically， it doesn't。😡，That's a good question basically。

 it doesn't get turned on with quickly。Does that make sense？

It still there's still some latency over here， but it's not as much as latency as4 p most transistors。

😡，Okay。😊，Okay but again， this is for fun you can play tricks I'm not going to ask you anything related to this it's good to know okay。

 let's talk about power consumption this is the last thing I'm going to talk about at a lower level because it's very important I think so whenever you actually build a transistor and power it on it consumes power。

😊，Whenever you switch the transistor apply some voltage to the gate。

 it actually consumes dynamic power， so there are two types of power consumption。

 dynamic power and static power， dynamic power is a power that's used to charge the capacitance as signals change。

😡，So essentially。😊，A signal changes from zero to one or one to zero， for example。😡。

So this is the basic power equation， how many of you have seen this before， dynamic power。

 some of you， maybe not that many， how many here you you？Okay， not that many okay， fine。

 but basically every circuit has some capacitance because you have wires and gates。

 it could be one or more transistors an end gate for example can be represented with some capacitance。

😊，え。And then you apply some supply voltage to it as we have seen。

 and there's also some frequency at which you change the values。

 this is actually going to be the clock frequency later on as we introduced the clock in sequential logic。

😡，And power is really a function of capacitance times the square of the voltage times frequency。

 again this is based on laws of physics， so if you have higher capacitance meaning higher loading lots of transistors on the output will connected to the output。

 you will consume higher power， if your supply voltage is higher you will consume higher power。

 if you are charging frequency is higher， youll consume higher power right？😊，Usually。

 if you want to increase the frequency， you also want to increase the voltage so that you can actually do that fast switching。

😡，Meaning that frequency is actually a functional voltage。😡。

So voltage actually cubically affects power， meaning if you increase voltage。

 you get a cubicle effect on power， so voltage is very bad for power in general。😡。

You want to this is why existing circuits try to reduce voltage as much as possible。

 as we have mentioned yesterday， yes。😡，或者是他。あ工。s usually when we try to。Well。

 that's the static power， well that's the voltage Time current。So we're talking about dynamic power。

 when you're dynamically switching， this is what happens。

 but when you're not actually applying any switching， you're not changing the values in the gate。😡。

When signals don't change， you still consume some power because the transistor leaks。

 it's not a perfect switch， another example of this basically。

 theres some current that's always leaking inside the transistor because it's connected to either high voltage or ground。

 and this is the static power that you consume。😡，The voltage times some leakage current that you have。

So the overall power that you consume is a function of dynamic power。

 how often you switch if you're not never switching。😡，Something is leaking， for example。

 in my cell phone， in my pocket， I'm not doing anything。😡，Hopefully it's not doing anything also。

 but if it's turned on， it's leaking， so the battery will leak。😡。

Over time because the circuit is actually draining static power consumption， essentially。😊，Okay。

 I already said this， I think。So this is good to know energy consumption。

 probably you know from basic physics that energy is an integral of power over time。😡，You basically呃。

Do that to figure out how much energy you consume and you need to include both static power and dynamic power。

 clearly dynamic power depends on what you're running。😡，On the gates， right if the。Again。

 I don't necessarily need to go back to program， but if you think about a microprocessor。

 the microprocessor consists of many millions of gates and the program is exercising many of these gates。

😡，And every one of them is consuming dynamic power if they're switching。😡，Also。

 every one of them is consuming static power。At the same time when they're not switching and the total energy consumption you get is the combination of those powers over time。

Does that make sense？O。It's good to know because this is going to be important well it's clearly very important today right this is also one of the reasons why it's good to reduce the circuits because as you make the circuits larger。

😡，Capacitance becomes larger and clearly， capacitance is an effect。

 and it's also good to reduce voltage。 and ideally， you want to reduce frequency。

 but frequency has implications on performance as well as we will see in sequential circuits。😊，Okay。

 so these are some common logic gates that I added some more over here， we saw。

 I guess we didn't see the buffer but buffer is essentially a buffer it amplifies the signal because sometimes signals lose strength when they travel and you may not want to amplify them。

 but it's logically it has no effect on the input as you can see inverter bubble remember and N or nor and there's XO。

 probably you seen XOR also。😊，Yes， okay。Okay， we're going to see XO more later and then there's XOR of course these are how they shown in module level picture victorially we can build larger gates。

 we can extend the gates to more than two inputs， we can do a three input n gate。

 10 input nor gate this is an example from your book that shows a three input N gate。😊，Again。

 you can make it bigger and bigger， but the trade offs web that we discussed apply。

 so if you keep adding more transistors in series。😡。

That's not very good in terms of the latency of this gate right if you have a 10 input n gate with 10 seristries in series。

 the latency will be high。😊，Yes。I think there should be some kind of solve。Yeah， opposed the current。

嗯。Be that。Not as significant， yes， but。We can discuss more。Okay。Any questions？没也是。Aary。我は。I mean。

 they could， so especially when you're powering things up， for example。

 you may have some current spikes。And they actually may have impact on。

 certainly they have impact on the lifetime of transistors。No question about that so high voltage。

 high current those actually affect reliability of the circuits。

 especially when the circuits are very small。😡，So no question about that。

 but these are very good questions that we're not going to get into。

 we may get into something similar at some point， but not yet yes。😊，It。Oh， I see。 Well。

 I think you need to。Yeah， you need to keep track of it normally your book doesn't do a good job in this one。

 but normally what I do is when when a wire branches from another one， I put a black。呃。

black circle there， your book didn't do it， but here you need to carverse it like B goes here。

 A goes here and C goes here， right？😊，Yeah。😊，That's a bit unfortunate， yes。Okay， any other questions？

Yes， when you increase the spot， kind of decisive influence。哎，我's。

Because I think wouldn't it be better to simply have like multiple end gates and then one kind of puts them together Yeah。

 yeah， exactly。 so basically as opposed to building a huge end gate like 10 input no gate。

 maybe it's better to have many two input no gates。And to create an no out of them， right。

 that's what you're saying， Yes exactly。Because the latency that you get over here may be much worse and the power that you get over here with a huge N gate may be much worse than a two N gate。

😡，But these are very good things to think about。😊，Which we will not necessarily go into if you want to go into all of these then you need to actually get a proper logic design course。

😡，And logic design takes multiple semesters to study in electrical engineering。

But very good questions。You guys are touching into all important topics in how you design microproors。

Robustness， latency， power。Okay okay I'm moving on。

 I'll go through this relatively quickly because we discussed Mooreore's law with some folks yesterday。

 essentially the reason essentially what we discussed transistors have been getting cheaper that's what Moore's law is about。

😊，You can put more transistors on a single chip， assuming the area is constant， right？

And this is dictated by Moore's law， which I'm going to assign you as an optional reading。

And this is Moore's original picture where he plotted the year of fabrication and number of components per integrated function on a chip and he basically figured out that it goes like this。

 this is log， this is log scale as you can see， so it's growing exponentially。😊。

And this is another picture that I like actually， where he plotted circuits that are manufactured in 1962。

 1965 and 1970， and he basically showed that the relative manufacturing cost per component。

 you can think of component as a transistor in this case。😊。

Has a sweet spot so in 1962 that sweet spot was here， if you actually manufacture 10 components。

 10 transistors， let's say you would minimize the cost in 1965 you would actually reduce the size and as a result you could actually put more components at lower cost and in 1970 you could actually put even more components at lower cost。

😊，Makes sense， so basically by reducing the size of the transistor and other circuitry。

 you can put more components in the same area。😡，え。And these are some recent pictures that show that you can actually get many more transistors today actually。

 we're at the level of 60， 70 billion transistors per chip。Okay。

 I'm going to let you read the paper which is actually a nice paper， an old paper， as you can see。

 but it's good to read some fundamental paper， it' only three pages。😊，And you can see。

That he is predicting over here by 1975， 10 years later。

 economics may dictate squeezing as many as 65，000 components on a single silicon chip today where it's almost 75 billion。

Okay， and also there are some interesting things that he mentions。

 will it be possible to remove the heat generated by tens of thousands of components in a single silicon chip？

😡，This is what we had in early 2000s or so people actually were designing putting too many transistors and power was a huge issue and as a result people moved to more lower frequency chips that do parallel processing GPUs are kind of an example of that。

😊，Okay， so how do we keep Moore's law essentially how do we put more transistors。

 How can we make the transistors smaller and smaller， This is actually a huge topic today Again。

 this is below our levels level of abstraction， but it's good to think about it because a lot of things that we're going to do in digital logic in architecture builds on the transistors and these low level components So we want to manufacture smaller transistors and structures。

😊，It's difficult today because some structures are already a few atoms in size。😡。

To be able to do better， we want to use materials with better properties that can be manufactured much smaller。

 so people have actually innovated a lot in this area， I'm not going to talk about that。

 making sure materials are compatible is a challenge here。😡。

Precision manufacturing is extremely important today。

 that is a lot of geopolitical implications also， unfortunately。

 but people try to use light to at least extreme ultraviole light to etch or pattern very small structures on silicon and you need machines like what I'm going to show you later on。

 and there's a lot of innovation at these levels。😊。

And creating new device technologies is also important these are different types of transistors basically you've seen NmoOS and PmoOS but there are many。

 many different types of transistors that operate on similar principles。

 but not exactly the same principles and again so there's innovation at the levels that we're not going to cover that's the purpose of some of these slides over here so if you're interested in this stuff then you should definitely talk about think about like microelectrons design fabrication technologies。

 precision manufacturing， etc。😊。

![](img/eff507112917a3e6efb2d8a0453a5fad_6.png)

I'll recommend you a five minute video on transistor innovation it's very high level but I like this picture over here。

 this is the relative size of a transistor that was manufactured in 1971 I think this is the first Intel and this is the relative size of a transistor today you cannot see it。

😊，Okay， and these are some of the machines that I used today to manufacture things again I'm not going to go through the detail because this is not our subject。

 but it's fascinating the amount of engineering and innovation and science that goes into these machines so that you can actually these is a huge machine。

😊，It's basically the goal is really to get the light to the right place and to the right precision so that you can etch one of these really small transistors at the right place。

😡，That's the right type。

![](img/eff507112917a3e6efb2d8a0453a5fad_8.png)

On silica。So you design a huge machine and infrastructure for that so that you can do this at the nanometer level。

 which is fascinating， I think， again， if you're interested， there's a lot of information。

 especially the IEDM conference talks about some of these things。

 but then there's more at other conferences So my point is innovation at the bottom actually enables computing a lot even though we sometimes forget it sometimes our thinking is clouded by this high level stuff like AI。

😊，Yes， AI， but what is it based on right it's really based on all of this innovation that has happened and if none of that happened that AI wouldn't happen also so it's good to think about the stack。

😡，Okay， that's why I mentioned this there's plenty of room at the bottom yesterday。Okay。

 so this is your extra assignment too， because it's so important， don't use AI。😊。

I want your personalized review of Moore's paper that was written in 1965， it's only three pages。😡。

Actually， maybe two pages or so。Does that sound good。All right。Okay， any questions？Okay。

 now let's jump into combination of logic circuits because we've covered the basics。

 we can now build logic circuits， we actually built gates。😡。

Our next step is to build some of the logic structures that are important components of the micro architecture of a computer。

 we're going to build the micro architecture after this。😊。

A logic circuit is really composed of inputs， outputs， and a specification。

 there are two types of specification， which is functional specification。😡。

Fiming is not important that everything happens immediately or with some latency。

 we're going to talk about functional。😡，I know what's happening here。Internet connection on stable。

 Everything is good。Maybe。As long as it's online it's fine。

 I guess so functional specification describes the relationship between inputs and outputs。😊。

Timing specification describes the delay between inputs changing and outputs responding to that we're going to have a special lecture on timing which is important and that's going to be the only lower level lecture that we will have。

😡，Today we're going to be functional， so there are two types of logic circuits。

 one is combinational logic， the other is sequential， Com logic is memoryless。😡，Basically。

 you don't remember what you have done， you take the inputs， you transform them to outputs。

 but there is no memory。😡，Outputs are strictly dependent on the combination of input values that are applied to the circuit right now that's why it's called combinational it's basically based on the combination of input values it's also called combinatorial logic in some books but you don't need to worry about that in your books later we will learn sequential logic later meaning next week。

😡，It has memory。Structure stores history and this can store data values， clearly sequential logic。

 plus combination logic together is very powerful， as we will see。😡，And in sequential logic。

 outputs are determined not only by the combination of the current inputs。

 but also by historical things that are stored in the circuit， as we will see like in memory。😡，Okay。

So now we're going to go into bulloleing algebra and I may go fast。

 so stop me if I'm going too fast because I'm assuming that you've seen a lot of this。😡。

So functional specification of outputs in terms of inputs is is essentially how you specify a circuit based on inputs right so what do we mean by function。

 of course， function is really a unique mapping from input values to output values。

 we've seen functions earlier and is a function or is a function not is a function right all of those are functions。

😊，The same input values produce the same output value every time That's good。 There's no memory。

 output does not depend on past input values。Okay。😊，So this is an example of a full1 bit adder。

 we're going to see this more， but if you would want to do one bit binary edition。😡。

you add two things A and B， and then you have a carry in。

And you compute the sum and you also compute the carry out just like you do decimal edition。

 you do binary edition right you've seen binary edition before。

 and this is actually the functional specification。

 it turns out sum is a X or B X or C in and carry is a three input majority function A and B or A and C in or B and C this is really the majority function of two out of three values as you can think about。

😡，But you can also specify this a tooth table and optimize it as we will see。😡，Okay。

 there are simple equations we've already seen these so I'm going to go through these relatively quickly。

 this is not， this is end， this is or， and we've seen representations also pictorially gate representations。

😊，And this is the person who's responsible for the algebra that you've learned。

 Boolean algebra is the algebra on ones and zeros with n or and not all patients。

So you start with some axioms， there are some basic things about objects and operations you just assume to be true。

 we're going to see some of these， you've probably seen this early， right？😡，Okay， good。

 that's why I'm going fast but stop me if you're and you'll study this。

 you'll have exercise about minimizing things as you will see in homeworks and we've asked questions in the exams in the past also these are the easy questions I would say。

We drive some laws and theorems， these allow you to manipulate boolean expressions and also importantly that and this is the reason why we're really studying it。

 this allows you to simplify boolean expressions you may have a very complicated boolean expression if you and if you actually implement it using gates that are at the level of the complexity of the equation it may be a very expensive circuit。

 but if you actually simplify it the circuit will be much smaller as we will see。😡。

And then we can derive more sophisticated properties useful for manipulating digital designs represented in terms of building equations。

 basically because we built everything on top of this digital abstraction。😊。

one and zero and we can build gates that are able to manipulate things with and or and not operations。

 we have an algebra that can specify the operation of this hardware essentially and this is very nice because this is really the theoretical basis of how you can design hardware and how you can optimize hardware and how you can reduce the size of the circuit that's why we're talking about this。

😡，And interestingly， there's also this theoretical basis and all of these laws and theorems enable you to automatically design hardware and automatically optimize it's called electronic design automation。

 you can specify a function and that function is specified in terms of a tooth table and a computer program goes through that tooth table and generates hardware completely。

😡，Of course， you can specify things at a higher level also， perhaps like a computer program。

 and as long as you can convert it to some tooth table form。

 then you can actually design a circuit for it automatically as well。😊，It's fascinating， I think。

 Okay， that's why we're covering it。 Okay， so probably you've seen a lot of this， but。Let's see。

 there are only two elements in the Boolean algebra，0 and1， and they're not equal to each other。😊。

result of end and all stay in the set you start with。

 there's commutative laws A or B is the same as B or A， and that applies to end also。😡。

There are identity elements， A or z or a， A and1 is a。There's distributed laws， basically。

or distributes over end and n distributes over or also that's good。

 you can convince yourselves of these these are axioms you can prove them we can well you can yeah exactly complement is basically there's a complement element ending your an oing with it gives the identity element for example a or a bar is one either a is true or not a is true that logic basic logic right？

And a and a bar cannot be true at the same time， right， basic logic again。

 so duallT how many people have seen duallT before？

Maybe all the axioms come in dual form anything true for an expression is also true for its dual so any derivation that you could make that is true can be flipped into a dual form and it stays true so more formally this is what you do actually it's better shown with an example but a dual is formed by converting every end operation to an or operation every or operation to an end operation every constant one to a constant zero and constant zero to a constant one but you don't change any of the literals or play of the complement so if you look over here。

😡，This is one。Equation， and this is the duall of it。😡，And both of them are true again。

 you can convince yourself， but this is what I did， essentially I follow these rules。😡，Okay。

 let's take a look at some of these interesting duals， so x or0 is x x and 1 is x。

 so this is really the dual， okay。😡，X or x is x this is something you can simplify right you don't want to build an or gate for this for example。

 right that's true for and also Okay， x bar bar is x X as you expect Okay commutative law is also a dual actually。

 as you can see over here Okay， so there are some other useful laws Associative laws we already discussed order parentheses don't matter distributed laws。

 we also also discussed it， but again， these are duals。

Let's let's take a look at the simplification theorems a little bit。

 so x and y or x and not y is equal to x because you can actually prove that right and then the dual of it is looks like this it's also x。

😊，This is actually very interesting x or x and y is actually equal to x again you can comm yourself of it I'm going to do that in the next slide。

😊，And do of it is also true。And again there's another one over here that I'm not going to go through these are actually useful for simplifying expressions。

 so whenever you see something like this in circuit you can reduce it X and again real programs that go through circuits to optimize things do this as we will see later on but we're not going to build that program if you want to build that program take a logic synthesis course is called hardware synthesis or logic synthesis you basically optimize circuits okay let's prove some of these。

😊，So this is the theorem x and y or x and y prime x， you first distribute x， take out x essentially。

 x is distributed over y plus y prime。😡，And clearly， y plus y prime y or a complement of y is 1。😡。

And then x and1 is x right Okay， I did this one， you can do the other one again very similarly。

And this is what you get。So clearly you can prove this， right？So there's no magic kick。

The Morgans law is actually useful， as we may see。 Have you how many people have seen the Morgan laws。

 Okay， that's good。 So I'm going to go through this thread really quickly again。😊，Basically。

This is what it says。You can think of this as a transformation， right。

 you have a function A or B or C， you take the complement and complement twice。😡。

A or B or C means at least one of A， B or C is true。

 and the Morgan's version of it says it is not the case that ABC are all false。😡，So it's logic again。

 basically， right， you can express things this way or you can express things this way。Now。

 why are we bothering through this， Okay， now we've gotten to the interesting part。

 These conversions are useful。 They're basically converence between different types of logic functions。

😡，They can prove useful if you do not have every type of gate or if some gates are more desirable to use than others。

 for example， you've designed a extremely fast nor gate， as we have seen earlier。

 maybe pseudo andmost nor gate and you want to use it all the time。

 you want to convert everything to N。😡，You go through these transformations to convert everything to Nor gate。

😡，Makes sense。Okay， that's the idea basically， for example。

 nor is equal to and with inputs complemented now we're going to do some bubble pushing so this is a nor。

😡，As you can see， but it's also and with inputs complemented So what do you do one one fun way of doing this is actually you take this bubble。

 you push it to the inputs。😊，The bubble goes to the inputs and you change the gate from more to end。

😡，Sounds good。That's bubble pushing basically if you haven't seen it before。

 Nand is equal to or with inputs complemented also， so this is Nand。😊，And you take the bubble。

 push it to the inputs X and y both get bubbles inverted and then change the gate to or now you get or with two complement inputs make sense these are equal basically now your tradeoff is if you designed a very nice one of these gates you pick that and you actually try to match your Boolean equations so that you actually maximize the use of the gates that you really need that you really want to use。

😡，Okay， that's why these are useful。Okay， now let's talk about using these buildinging equations to represent a logic circuit。

 I think some of this is already clear， but we're going to go through some formal way of doing this。

 how many of you have seen some of products form。😊，Okay， good。Maybe some of you have seen。

 but I didn't see a lot of fans yet。So basically， we want to represent the function of accommodation logic block。

 meaning functional specification， and we want to methodically transform the function to simple functions。

 we want to have a good starting point for everything。😊。

Because these different things can lead to different hardware realizations。

 and we want to enable logic minimization or simplification from a common basis， if you will。😡。

we want to automate this process， as I discussed earlier and I already mentioned these names。

 so the issue is different bullolean expressions lead to different logic gate implementations。

 meaning different hardware area， cost， latency and energy properties。😊，做。

So where we start with this really standardized function representations so that we can actually do this very methodically these are called either sum of product form or product of sums form。

 these enable a single universally agreed on way of representing a Boolean function starting from its truth table this is also called canonical representation I'm going to give you an example so some of products form。

😊，Let's take a look， assume that you have a truth table of Boolean function F。😡，呃。

Maybe I'll just give you an example。就。This is what a function looks like， right？

These are three input， one output function。😡，If you want to represent it as a sum of products form。

 you find all of the input combinations。😡，These are going to be called minterms for which the output function is true basically you find all of these there are five of the input combinations and you express the function that way input combination ABC is 011 so for this function to evaluate the true for the output to be true。

😡，Either ABC should be 011 or it should be 100 or it should be 101 or it should be 110 or it should be 111。

This covers all possible cases under which the function will evaluate the truth。😡。

And that's how we represent it basically F is equal to one if a bar B C is true or A B bar C bar is true or A B bar C is true or AB C bar is true etc so let me finish this and then we'll take a break does this make sense so this is very simple as you can see but this is a way of representing function essentially F is in a very standardized way。

😡，F is the or of all input variable combinations that result in a one and all Boolean equations can be written in SOP form。

 this is a maximum kind of a max it's not a maximal form。

 but it really includes all input combinations with all literals。😡，Okay。

Let me define quickly complement， you already know what a complement is。

 lital is a variable or its complement。😡，Implicant is a product or end of literals。

 These are some examples of implicants。 Minterm。 Now this is important。

 This is a product end that includes all input variables and some of product forms always include midterms as defined over here。

Maxter， it's really the sum or that includes all input variables。

 we're going to use this in product of sums。😡，So essentially a tooth table is a unique signature of a boolean function。

 but it's an expensive representation。😡，A boolean function have as many alternative boolean expressions。

え。So if they specify the same thing， why do we care， right different bulloleing expression。

 the reason we care is different bulloleing expressions lead to different logic gates。

 different costs。😡，That's why we want to start with a canonical form and minimize it as much as possible。

😡，So I've already said this， but let me find a good place to finish over here。

 each each midterm is a product of literals over here， each midterm is true for that row only。😊。

I think I actually the function over here if you already specified it like we said with Minterms。

 these are Minterms， meanterm is each of these values that evaluate to true over here and the function evaluate the true if any of the products or any of the minterms causes the output to be one so you can verify this if you apply input 101 it activates this term and you get a one at the end even though all of the other ones are zero。

😊，Okay， I already said all of this so you can these are for your thing I'm going to finish with the short end because the short end is important。

 so if you agree on the order of the variables you can represent a function much more simply than a truth table。

😊，You can enumerate each row with a decimal number that corresponds to the binary number created by the input pattern。

 so what does this mean？😡，If you look at the order， the order is increasing right there 00，0，0，0，1。

01，0，01，110，0， and 10，0 is decimal 4 if you think about it， one，2，4。😡，So this is called Minterm four。

 so if you want to specify this function， a three input function。

 you can specify it in terms of which minterms evaluate one in this particular case。😡。

Mein terms four，3，4，5， six，7 evaluate one。😡，And you can use a summation notation。

 so basically you don't need a too table to evaluate a function。

 you say this is a three input function and these are the midterms that evaluate one and this is how I compress that too table into this thing。

😡，Makes sense， right， you need to know which how many inputs you have in the function， of course。

 three input one output。😡，Okay， so this is a short term notation， basically， as you can see。Now。

 what you can do is。You can， if I give you this， this function consists of inter termsims 3，4，567。😡。

You can figure out exactly what these are because it's a three input function without looking at the truthth table。

 you can actually say this is my function。😡，And then you know that this is not a minimal form clearly you basically go through minimizing using Boolean equations and this relates a plus PC again。

 you can convince yourself I won going through this relatively quickly because this is boolean algebra which you have seen but what you have not seen is。

😊，And agreed upon way of canonically representing a function in some products form。

And this is the realization of the function。 If you realize the function using all of this。

 which is the agreed upon way。😡，Wwhich is the basis of transformations to begin with。

 it's very expensive， but if you actually simplify it using different methods。

 one of the methods is actually using Boolean algebra， axioms， TMs。

 all of the laws that we discussed， you'll get this one。😡，Okay， so this is a good place to stop。

 I'm going to continue and finish this and then we're going to talk about combinational logic。😊。

So let's be back at， I guess， one minute after the bell rings and then we'll continue。Yeah。



![](img/eff507112917a3e6efb2d8a0453a5fad_10.png)

![](img/eff507112917a3e6efb2d8a0453a5fad_11.png)

嗯。Okay。あだはい。嗯，补查。可以。有啊系。Oh。Okay。时候。Yes。Okay， need to anything I don't know。 you tell me okay。Yeah他。

不是了。所以在电话。Okay。Okay， let's get settled down。People are coming in。你先。あそ。Yeah。あで。Okay。

So we're talking about SOP form。Someum of products。

And I think one thing I should emphasize is you can write a function like this and this is single input。

 you need to specify how many inputs there are in the function， otherwise at M3。

 you don't know what it's referring to right in this case if I say if I tell you I have a three input one output function if I tell you that。

😊，あ。Let's see。 only M0 function is equal to M0。 You know that the function value is to one only if A B and C are all zeros。

 right。Makes sense， you have to know how many inputs there are。😡。

And I may have gotten a little bit fast in the earlier part of the lecture because I kind of assume that you know Booleing and algebra。

 and I think you do， but maybe the notation is a little bit different。

 some folks told me that in the past also the notation we use in digital logic in general is the notation I use over here。

😊，You basically have dot or nothing if you want to do end of two variables and you have an plus。😡。

To do or。Does that make sense that's different from the notation you use probably？😡。

In prior classes right so you need to get used the notation sorry about that。

 but that's how people have evolved in different fields， maybe。😊，Discrete math versus digital logic。

 Okay， so now you know how to represent。 if I tell you， I have a three input function。

And I have these midterms in that function that you know exactly what that function is。

 you can go ahead。😡，And minimize that function basically， right？对。

And minimization happens using bulling algebra of rules。 Again， I will not go through this。

 otherwise we will not cover anything really interesting。Okay。

 so sum of products form actually you could implement the sum products form directly in logic。

 you could actually do a logic that looks like this。

 I'm not going to do that I'm going to show you another one over here。

 there' another three input function as you can see it could be implemented this way it's two level logic as you can see right it's one level has end gates in this case you have three minterms so you need 3 d end gates and the second level is always an or gate for a single output right so you basically the first level computes the different minterms using end gates and the second level ors them。

😊，This is a perfectly fine implementation at the logic level。

 you could actually use the gates underlying transistors。😊，Except it's just too expensive， right？

Does that make sense， that's why we go and simplify this and if you go and simplify this。

 essentially basically so P form is perfectly defined as logic implementation but doesn't lead to minimal logic directly。

 you need to simplify it。😡，Okay。So this is a summary of canonical summer products that I'm not going to go through。

 but essentially logically， so Pform presents the function as a sum or or of all products meanterms that cause the output to be1 hopefully that's clear right you figure out which meanterms lead to one and you or them that's it。

😊，Now product of sums is another way of representing things。

 I like some products because it's easier， but once you deal with products of sums you can actually once you understand products of sums you can actually deal with it also。

😡，A formal way of thinking about product of some it's really the deorgon of sum of products of F prime。

 meaning the complement of F。😡，I don't like thinking about it this way I like thinking about it as a truth table or this way essentially find all the input combinations max terms for which the output of the function is false we're going to look at the other part essentially not the input combinations where the output was one we're going to look at the input combinations that are where the output is zero and then you end。

😊，Essentially， F or product of some forms can express the function as end of all input variable combinations that result in AU。

😡，So we're going to do the same thing， except we're going to deal with the zero outputs。

 we're going to take that and we're going to say the function is zero if any of these input combinations is zero。

 any means and。😡，If。IfIf a is0， B is0 or C is 0， the function is0， I don't care what these are。😡。

If a is0 b is 0， c is1， the function is zero， and that's what this max term is about if a is0。

 b is 1， C is 0。😡，The function is zero， I don't care about the other ones。Makes sense， right？

So this a bit less I don't think it's less intuitive but you need to get used to it essentially the reason it's called product of sums is it's really product of these sums now you have ors over here and end over here okay。

😡，So each sum term represents one of the zeros of the function basically the functioning values to false IE output is zero if any of the sums。

 in this case， max terms。😡，These are the max terms causes the output to be zero。

 Don't get too bogged up bogged down in terminology。 Everything is， I think。

 relatively simple over here。😡，Okay。So basically， if your input is 0，1 and 0。

 it activates this max term and that max term evaluates to 0。 these max terms。

 even though they may or may not。Evalate to zero， you get essentially zero in the end。

 you don't care about these other ones。😡，Okay。I think I already said everything over here anything ended with zero zero so but that will be0 so thiss another way of actually specifying the circuit as you can see right I've already said all of this actually it's the same thing Sean in Gates。

😊，Okay， so how do you write it？😡，Essentially， you need to figure out the parts where the function is zero。

😊，Or input combinations。Truth table roles， in other words。If you have a zero in the input column。

 it's a true literal， if you have one in the input column， it's complement literal。

 you or the litals to get a max term。😊，Which is basically this， for example。

 let's take a look at this one010， you do a， B bar C， A， B bar C， and you order them okay。

 that's the max term and you add together all the max term max terms for which the function zero okay that's how you get it。

😡，Which is very simple， hopefully。Or you just remember。

 you do the product sum of products and get the de Morganorgan of SOP of F prior。😡。

Which is not how I would do it。Okay， so you can actually do you can actually have a max term notation over here also these are the max terms associated with different combinations of inputs and this is our short term notation now。

😊，We use a capital M for max termsm， and we can specify this function as sum the product of max termsm 012 because those are the ones that lead to zero if you saw it in the previous case。

😡，I think I've kind of said this already now note that this is not the complement of the science's function。

 this is the same function that we've seen earlier， same function where mean terms 3， four， five。

 six，7 specify the function max terms01 to also specify the function right？😡，Okay。

 there are some useful conversions I'll go through these real quickly。

 but also I already said this basically mid term to max term conversion。😊。

Basically rewrite them mid termm short end using the max term shorthand。

 you basically use the indices that are not already used。😊。

You can do the same thing exactly the opposite way also these are the same functions basically。

 these two specify the same functions。These two specify the same functions also。Okay。

You can expand F to F prime。By changing things like this。For example， this is function。

 prime is actually meanterms， the opposite meanterms。

 the meanterms that you didn't use and prime is again max terms that you didn't use hopefully this is clear right based on the truthth table based on the logical structure you can figure this out。

Again， I already， I'm not going to go through this because it's kind of boring。Okay。

 now interesting thing is you can using Boolean algebra you can simplify the SOP or POS form of any function in a methodical way。

😊，You start with this canonical form。Basically， you can start with a truth table to begin with。😡。

And then you turn the truth table into SOP or POS form。

 and then you use Boolean simplification rules。 We're going to see how to do this for full ladderer later。

 but essentially full ladderer， you can start with the truth table and simplify it to these forms。

Makes us。So this was the circuit that I showed you earlier， this is a sum of products form。

 it's least a two level logic we're going to see that two level logic later on today also again。😡。

This is a simplified form。😡，It's still in two level logic， but it's simplified， as you can see。

 this is not some product。 So if someone gives you a three input function and tells you。

 is this in some product form， this and the answer here is yes。😡。

But here this is not in some product form because it's missing some literals right it's a three input function and you know that this is missing A and this is missing C。

😊，Which means that this is not in some products form。Makes sense。Look at。Okay。

 any questions now we're going to jump into a combination of blocks。

 that's the booleing algebrabri cover for now。But it's going to be useful in designing combination of blocks。

😡，That we will build it upon， yes。你这些仔。アりた。Yes， exactly if you simplify， you may lose redundancy。

Which may be bad， as we will see in timing。It's good in terms of reducing area。😡。

It may be bad if you have some errors in the circuit， et cetera。It's good to think about it that way。

 so there are always trade offs。😡，You cannot say something is good or bad necessarily。

 you need to think about what metric is it good or bad for right minimizing the circuit is good for reduce。

😡，In area， it could be good for reducing latency， so going from here to here， clearly less area。

 right？😡，Probably less latency。Based on what we have seen。

 but you do lose some redundancy in the circuit。Maybe if there's an error in one of the bits。

 you will not be able to tolerate it。😡，Ored you'll tolerate it less。😡，Okay， and with timing。

 we will see something else when you do the timing analysis。Okay。All right。

 let's cover some combinational blocks， so we build combinational blocks to build computers essentially and we've seen already some of the gates now we're going to see more。

😊，Essentially， combination logic is grouped into larger building blocks to build complex systems。

 and then we're going to add sequential logic on top of the source。

 but let's keep combinational for not。😊，That the reason we do this is to tame complexity。😡。

Because they think about the billions of transistors right you cannot just look at it with transistors。

 you need to actually do a hierarchical design we're going talk about that also so you need to group the transistors into gates。

 you need to group the gates into larger blocks called modules and maybe modules into even larger blocks right processors etc。

 so that you can tame that complexities so we're going to build a hierarchy。😡。

We want to hide the unnecessary gate double details so that we can emphasize a function of the building block。

😡，So if we're going to examine some things， I hope you have not seen this， Have you seen decoders？😡。

Before some of you were。And of course， and of course here， okay， no。

 no is a good answer anybody else， Okay， that's good multiplexors full ladder and programmable logic aids we're going to see more actually this is a more complete thing I'm not sure I don't know if you're going cover everything today。

 but let's see how far you'll get。😊，And these are all combinational。Okay。

 let's start with the decoder。You got is fun。It basically does what it says。

 it decodes an input pattern。😡，Now what does that mean， in other words。

 it's an input pattern detector。😡，You have N inputs。😡，And two to the nals。

And only one of the outputs will evaluate to one。😡，Depending on the pattern。That comes as the input。

Hopefully that makes sense， right？I already said this， I think。

The output that is logically one is the output that's corresponding to the input pattern that the logic circuit is expected to detect。

 so's say go guys， there's a two to four decoder。😡，This is our tooth table。😡，Now we have two inputs。

 four outputs， as I said。😡，Y zero is one？Only if both of the inputs are zero。

 y1 is1 and only y1 is one。😡，我们也。The inputs are01 and y2 is1 and only y2 is1 only if。

A1 the two inputs are 10 and y3 is 1 only if a1 and a0 are 11 now you can see that if y 0 is raised as an output you know that the input pattern is00 right and you can basically you basically decod the input pattern。

Makes sense。Okay， that's good， a lot of pattern matching circuits actually use this。Very simple。

 very basic and。We're going to abstract it this way if you actually see an abstraction that looks like this two to four decoder。

😊，This is our module and this is how we're going to tame complexity。

 we're not going to represent it with underlying gates or transistors。

 but I'm going to show you underlying implementation with gates soon。😡。

So this means that y3 is raised， meaning one， if a1 and A0 are both one， okay？Okay。

 so hopefully it's simple。Now this is the gate level implementation of that decoder or one gate level implementation of that decoder。

 right？😡，you can see I built it using and gates and we can inverge A and B and this is my notation you had a question earlier。

 this is how you can say based on my notation that this wire over here，😊，Belongs to this， right。

 That's how you go out of it and you don't confuse these two wires over here。

Hopefully that makes sense。There are other notations potentially。

 but basically this end gate evaluate to one only if A and B are both one。

 this evaluateval is to one only if A and B are 10。😊，And01 and00， that's your decoder over here。

 very simple， and you can check it clearly with my pictorial representation。😡，Okay。

 so hopefully this is clear。This is a two to four decoder， you can have a three to8 decoder。

 four to 16 decoder。😊，I don't know， pick your favorite number， 1010 to 1224 decoder。

And in modern memories， we have gigabytes and gigabytes。And they actually have decoders。

 so what's the function of this decoder？😡，We can have specifying address， for example。😡。

If your memory is， for example， let's say one gigy， I think that's2 to 30。Now，4 gigs let's say。

's 2 to 32 bits， if you will。Through 32 bytes。You need a 32 input decoder。

 and that specifies your entire address range。 Okay， we'll see that later on。

 So decoder basically can tell you which。Part of your memory to enable so that you can get the data。

It's this's called an address decoder， particularly， yes。

F saw the when we looked at what Google uses for video， according the。Yeah。

 but that's a different kind of decoder， that's an overloaded term。It could be used inside yes。

 inside the circuitcus， it' is a very basic building block。

 it could be used for many many different purposes。Okay。Okay。Okay。

 basically the decoder is useful in determining how to interpret a bit pattern。

 I've given you one example it could be an address。😡。

It could be the address of a location and memory that the proor intends to read from。😡。

You get address8 and you want to figure out which location to read and the decoder essentially enables that line that goes that location。

😡，This wire， for example， in this case， the address could be two it's a very simple address and you get this line and that line actually enables you to read from that part。

 we will see that when we talk about sequential circuit if you don't understand right now。

 it's okay right now we're looking at how to detect a particular pattern。😊。

Or it could be an instruction in the program and the processor needs to decide what action to take。

 so how do you encode an instruction instructions usually encode as a bit pattern。😡。

Bit pattern 000 means do an add bit pattern 001 means do a multiply bit pattern010 means do a square root。

 bit pattern 011 means do a subtract。😡，This is how you specify instructions so that the computer can understand them。

😡，YouThis is called encoding and someone specifies an instruction how do the computer recognize what is that instruction and we will see this when we talk about instructions at architecture you need to take let's call an op code。

 the big pattern is called an up code and there needs to be some circuit pre decoder in the processor that basically takes that up code and decos it。

😡，Assuming that your bit pattern is 10， it tells you that， oh。

 it's this instruction that I'm going to do so it enables some logic that ensures that that instruction is executed。

😡，Make sense。This is how you detect how we interpret a bit pattern basically again。

 you will see this， but it is important because we're going to build on all of these logic structures to build a microprocesor and they're all needed。

 as we will see。😡，Okay， multiplexer how many of you have seen this one， okay。

 people have taken logic design courses， maybe have seen it or something similar this is also called the selector。

😊，It selects one of the n inputs to connect it to the output。😡，Let's see。

 based on the value of a control input called the select input。😡。

So let's start with a very simple two to one maxs multiplexer selector。😡。

So two to one max has two data inputs。😡，And one， select input。If the select input is 0。

 output is equal to data input 0。 As you can see， if the select input is one。

 output is the same as data input1。Basically selects。

It chooses one of the inputs to pass to the output。😡。

And this is the module representation of a two to one max。😡，These are， I mean。

 this basically if the select input is zero。This bit D0 becomes output y if the select input is1。

 the bit D1 becomes output y。😡，These could be actually many bits。😡，We have to select and a zero。

 you select a 32 input， 32 bit data and put it onto a 32 bit output right it could be。

 but right now we're dealing with bits later， you can generalize it。😡。

Make sense right basically you're selecting something。

 this is good for choosing what to do in underlying circuitry。😡，Okay。😊，Okay。

 this is the low level gate implementation。😡，That we will hopefully not need in the future because we know what the module does functionally。

 right？😡，But this is to convince yourself that you can be realized with true level logic in this particular case。

 but it's not some of products form。😡，And you would recognize that because you have three inputs。

 as you can see and we have here two inputs so we've simplified it so basically what this does is if select input is one。

outputput will be。B over here， if the select input is zero output will be a over here and you can convince yourself again me pictorially choosing select input0。

 this becomes one so this end gate passes a， this becomes zero so。😡。

This is let's say zero in the end and a or z or a， right？

Whatever value is of a will be output putto here， Okay， that's a selector basically。Okay。

 weve already said this， but the output C is always connected to either the input A or input B。

 output value depends on the select value or select line， also all S essentially。😡。

So this is another pictorial way of looking at it if you select lines are usually shown this is a control line usually shown at least thiss not always the case but usually Pat and Patel does a good job I think Harris and arrows also does a good job in it with an empty arrow whereas data lines are usually shown with like darker arrows like this over here here it's white here it's black so this is select or control line and this is data lines and you pick one of the data inputs。

😊，Okay。Another way of representing this in it。Different kind of truth table。

 not just ones and zero is this， this is a truth table， except it uses a kind of different structure。

 right？😡，You just。Inputs are part of the output over here。 They're not shown over here。

 So in that sense， it's not a， let's say， kosher truth table。

 It's a truth table that you can interpret as a human， but it's not a truth table the way。

We defined it， you， it doesn't have all the input combinations basically because inputs are over here。

 but it's a good way of thinking about it because this enables you to simplify things nicely from a logical perspective。

 right？😡，Humans are not necessarily machines that just use ones and zeros as you can see right Okay。

 so basically if select input is0， I'll put C is a， if select input is one， I'll put C is B。

 I like the street table。😊，Okay。Okay， I'm going to do this task for you in the next slide。

 using two to one mues， you can actually have four to one mugs。😡，You can do it at the gate level。

 you can do it at the module level， and this is the module level and this is the gate level and you can convince yourself that this each one of these two to1 maxs。

😊，Now we have two select inputs because we want to select between four things， four data inputs。

So you。Log two to the forest2， so you need to have two bits， select inputs。😡。

And you connect S0 to the first level， so you have two to the one maxes over here and you have the second level select using the second select input and this S0 also propagates here here so this is S0。

 this is not an output from the max。😡，It's the downside of your book， I guess a little bit。

And you can convince yourself that this select zero， if it's0， selects d0 and if select one is also0。

 it you select d0 to the output， that's what we want。😡，If both S0 and S1 is 0。

 we should say select d0。 if S0 is1， S1 is 0， we should select d1 and you can again convince yourself that this works。

 and this is the gate level representation that I'm not going to go through。😡。

But you can see that it's very similar to two to the1 maxs。Except yeah。

 it's not two to the one anymore， it's four to the one， four to one maxs。Makes sense。Okay。Okay。

 so learn Moxes， multiplextures are good， and we're going to have a little bit more fun right now with multiplexs because they enable some things that you're going to use in your FPGAs。

😊，Any questions before I move on？So now you know how to detect an input pattern。😡。

Now you know how to select。😡，And input data based on a control input。😡。

So you can actually combine these things as we will see when we build memories。

 we're going to combine these things actually。😡，Okay， I'm not going to get ahead all myself。So okay。

 one interesting thing about multiplexors is they can be used as lookup tables to perform logic functions and a lot of FPGs do things like this。

😡，Okay， this is from your book。This is a logic function。

 it's actually a logic function that we've seen It's n y is equal to A and B。😡。

You can formulate this truth table as a multiplexer， so how do you do it？😡，Inputs， in this case。

 AB are select inputs。😡，But then you also have some inputs that you hardwire。😡。

So if A and B are both zero。😡，The multiplexer selects the zero zero input。

Which is hardwired to zero ground。Sounds good， right？Only if A and B are both one。

 the multiplexer selects the one one input， which is hardwired to one logic， three volts。

 if you remember。And y is equal to that？So this way we built an end gate using a multiplexer。

Pretty expensive。 You don't want to do it。But there may be cases where this is cheaper。



![](img/eff507112917a3e6efb2d8a0453a5fad_13.png)

And there may be cases that where this is actually useful。

Does that that make sense using a multiplexer input is a。😡。



![](img/eff507112917a3e6efb2d8a0453a5fad_15.png)

If a is0， the output should be0 as expected， That's my end。 if a is one。

 the output should depend on B。Which is as expected now you have a multiplexer that implements an a gate in a simpler fashion。

😊，Does that sound good okay so it can have fun this is an XO now XO is normally complicated but with maxxes actually you can make it cheaper maybe I don't know。

 but this is another way of doing it again a X or B this function is a X or B or if the two values are equal you get a0 if there is a difference you get a1 in fact we're going to use this an equality checker later on you can express it like this if a is0 y should be B if a is1 y should be v bar and this is the multiplexer implementation of it clearly you could implement it using and you can actually simplify it using the way we discussed but now you use multiplexer logic。

😊，Sounds good， right？This another example， more complicated one。😊。

Nowll I can go through this forever， but I'm not going to do that。

 I guess basically this is the sum of product form。

 this is the implementation of a sum of product form using a multixxi。😡，All of the inputs are here。

 all of the essential input combinations are here， and you basically wire the input combinations that evaluate to one to one。

 which is high power by voltage， you wire the input combinations that evaluate to zero to zeros and then your multiplexer selects the right input combination makes sense when you apply the input okay clearly a bad idea because it's expensive voltage right but it's doable。

😡，Now， why it could be a good idea if you want programability and your FPGs。

 existing FPGs actually work with structures that kind of look like this， not exactly， but similar。😡。

In the sense that if you want to implement a function。You can specify it using a lookup table。

 it's also called a lookup table。😡，In fact， what I did was at kind of a hardwired lookup table。

 you could make it more programmable， which I'm not going to go into right now。

 but when we talk about memories you can imagine how to program it later on。

 but this is a three input lookup table output is one bit input is three bits。😡，喂。Wiring the inputs。

The way you like so that you can specify any function， any three input function。😡，Okay。

 multixer choose one of the eight data inputs that corresponds to the three bit select inputs and these are your data inputs so your function is three bits。

 your output is one bit and you can specify any function this way as long as you can write what you what you are supposed to select based on these inputs。

😡，Now let me give you an example， I already said all of this basically I already said this this is also called a three lot。

 it can implement any three bit input function， for example。

 if if I want a function that outputs one when there are at least two ones in a three bit input，😊。

I basically figure out which of these input combinations have two ones。😡。

And I set the ones that are at least two ones to one。Which are did these once， right，0，1，1，1，0，1，1，1。

0，1，1，1 and everything else to zero。And when I apply my input over here。😡。

This function will evaluate to one only if at least two of these inputs are going to be one。😡，So。

 if I set。If I program， if you will， these。Input data lines to the right value。

 such I that I specify my function， I can evaluate any function。

 and this is good because in NFPG it's called a configurable program reconfigurable system。

 you can implement any function， you can implement a multiplication for example。😡。

You can can specify。I don't know4 by four multiplication as an8 input function。

 and you don't need to design a multiplier for that。

 you can actually have a lookup table that has two to the eight。😡，Inputs。

And you apply two of the four bit numbers as a select input to that lookup table。😡，Makes sense。

 this way you don't need to build a multiplier， you do multiplication using a lookup table。😡，Okay。

 so FPGs operate using these principles and you're going to program these FPGs。😊。

That's why I cover this because it's really interesting and important okay。

 you can also similar to doing logic using multiplexors。

 you can do logic using decoders so we should not make decoders feel lonely。

 they can actually do logic as you can see over here。😊，So in this case， this is Ax nor B and。😡。

Using a tool of4 decoder and by adding an or gate at the end。😡，A decoder， what does a decoder do。

 it gives you the inters actually， right？😡，It's good to think about that。

So a decoder gives you all of the minterms because it's two to the four right if it's three。

 it gives you eight outputs， so the minterm that's enabled actually gets a one at the end。😡，Now。

 if you do or you actually get an SOP representation of that， right？😡，Which is nice。

So basically XnoR means A B and A bar B bar or a bar B bar if any of these meanters is true。

 this function is true and decoder it gives you all the mean terms and you have the second level over here so actually we've seen this before。

😡，When we talk about SOP form。We kind of talked about a decoder at a Boolean level。

 not at a hardware level。Okay。Now let's do more things adding adding things so you've done binary edition and you're reading binary edition I'll go through this relatively quickly。

 but this is an M bit binary number added to another M bit binary number B。😊。

It's similar to theimation， you go from right to left one column at a time and you generate the sum and a carry initially the carry into the zero as you normally zero。

😡，Well， it should be zero if you're doing addition， if you're doing two complement subtraction。

 which you should read in the book， it carry in is actually a one and we're going to see it if time permits。

 let's see。😊，So this is sum zero， which is a0 plus b0 at the bit level。

 and then you generate a carry。😡，Someone is a plus E1 plus carry in from the zero level。

And you generate a carry out to the next level， okay。So that's what the carries are。

 so truth table or binary edition on one column of bits within two em all print looks like this。😡。

Basically， you look at bit by bit。AI， B carry I， and then you generate the carry I plus one and then some I。

Okay， and you can convince yourself this is the addition。 Let's take look' look at one of these。

 basically。😊，Okay let's say we'll get one of these so if you're if a is0 b is one and carry is one the sum should be0 because one plus one is2 and two in binary is really zero so you generate a carry because two is greater than the largest value that's representable in binary form so this is what it is so that's correct so you can verify all of these so if you want to do an n bit addition you really do n1 bit additions right。

😡，You do this bit， generate the carry， and then you do these three bits and then generate these or this bit and generate the carry。

 so it's really a sequential process basically。😊，Okay。

 and this is the SOP form implementation of an adder， we're going to simplify that later。😊。

These are all of them in terms over here， essentially thiss a decoder。😊。

And then you choose the right things in the decoder and or them to get the carry out and the sum make sense right I've done basically what we've done earlier。

 nothing fancy， this is our full ladder， expensive ladder because I didn't minimize it。😡。

The way you can minimize and this is the module level representation。

 if I tell you this's a full ladder， you should probably know what it's doing binary ladder。

 of course， it's not a decimal ladder， but now you can also realize that this is x so。😡。

SI is really an exor of AI， B I and carry I， and chrry is really a majority function。

 And that way you can simplify it。 That's one way of simplifying it。

 or you can simplify it using boing equations。There are multiple ways of simplify flying things。

 so I'm going to show you major majority x or later Okay。

 but now that was one bit adder that's good we can do addition in one bit。

 How do I I build that four bit adder， as I said earlier。😡，You basically。Chain these full ladderers。

 This is a single bit adder carrying in a zero。😡，It generates a sum carry out is fed into the next bit。

😊，Bit one， it generates a carry out and some this carry out is fed into the next bit。

 this carry is fed into the next bit this carry is fed outside because we have only four bits。😊。

That's a forbidd。Okay， you can convince yourself that it works， which I'm not going to do here。

Makes sense， right？This is also called a ripple cararytter if you heard the term lip ripipple carry。

😡，Carry is basically rippling across one bidadders。

This is a very simple adder you can build from1 bit adders。Now there's a downside of the Sader。

LLatency， right this， and we're going to say that， okay。

 basically in order to evaluate the last bit you should be。

 you should have evaluatedd everything before。😊，This is serial and people actually came out with many。

 many different ways of designing adders Harris and Harris covers some of them I'm going to give you one basic idea of one of the adders。

Essentially， if you don't want。To wait。For Terry to ripple through slowly。

Let's say 30 bits or 31 bits。You may decide a logic to accelerate the carry generation。😡。

Right some generation is not a problem， some generation。

 well I guess some generations is a problem also because you're waiting for the carry。

 but basically the critical path is really the carry generation。

So if you accelerate the car generation using some specialized logic。😡。

You can actually start some of the later sums earlier。

 maybe speculatively because you don't know the exact area potentially。

 or maybe not speculatively also。😡，So this is a carrier look ahead adder。

 what it does is it basically looks at four bit blocks。

 this is a four bit block where each block is a ripple carry adder。😡。

But there's also some specialized logic that quickly calculates to carry based on logic equations。😡。

Not based on rippleary edition， you basically look at the adder as fold four bits specified as a boolean function using some products form and you minimize that function。

😡，And you generate carry4 directly from all of those bits。😡，Makes sense。Okay， keep that in mind。

 this is one way of accelerating care generation people have come up with many。

 many interesting ways， which I'm not going to cover if you take a computer or arithmetic course is fascinating。

 I think。😡，Okay。L， programmable logic right。This is actually what's going to be an example of programmable logic that can be also a configurable potential。

😡，We call the sample product form， we didn't talk about that for no reason。

 sample product form leads to two level logic。😊，A PLA programmable logic array enables the two level SOP implementation of any n input M output function programm logic array actually looks like this kind of except as programmable connections between the inputs and inputs to these end gates and also outputs of the end gates to the inputs of the or gate okay so basically you can program these connections over here actually you don't have programmable connections necessarily here you could but in this particular programmable logic array example。

 you generate all the minterms and you decide which minterms to connect to the or gates。😊。

To specify a function。Okay。😊，You could implement hardware like this and people have implemented hardware like this。

 it's expensive but it's very flexible， as you can see。

 you can implement anything by programming those connections Don't ask me about how you program the connections right now。

😡，There are different ways of doing that in the past people have done fuses for example。

 but if you can be more programmable using Maxs， for example。

 multiplexors is one way of programming it， but we're not going to go into how you program it。

 but we're going to see that you could actually implement any function this way。😡，Okay basically。

 you can implant any collection of logic functions one mission to。

 assuming there are three inputs and at most three outputs over here。

 you have an array of n gates followed by an array of or gates some of the products form。😡。

How do you determine the number of end gates essentially aOP。

 the number of possible interterms for an end input logic function。

 you need a PLA with2 the end input end gates？😊，And each of them should specify one of the mentors。😡。

The or gates depends on the number of output cons in the truth table。

 so if your function has one output， the other two gets unused in this particular case， right？😡。

So let's take a look at it， what do you do to implement a logic function。

 you connect the output of an end gate to the input of an or gate if the corresponding meanterm is in theO。

😊，It's kind of no brainer， right basically we're implementing the SOP direct。😡。

In hardware by connecting the midterm to the or gate。😡，And this is a simple programmable logic track。

 essentially these connections are programmable。😡，You can imagine how to do this using Maxs as multiplexors。

 but again we're not going to look at the circuit be right now。

 you can program the connections from end gate put to or gate and post to implement the desired logic function。

😡，There's other type of programm logic， which is FPGs。Which we're not going to talk about。

 but they use lookup tables also。Okay， so PA looks like this basically， you have an and array。

 you have an or inputs and then implicants， these are all essentially。😡。

The midterms and then yellow laptops。So this is one example function again， I will not go over this。

 but basically these are the programme connections in this case they were nice they added these blue things。

So basically this in this case， x evaluates to a bar B bar C， which is coming from here。

 these three things。😊，And or AB C bar and you can see that y values to AB bar， okay。Okay。

 and this is another way of looking at it， this is， yeah。Okay。

So how do we implement a full ladder using a PLA， let's take a look at this we you saw the full ladder earlier。

😡，We saw the truth table。And we're not going to change the truth table。

 we're going to look at the sum product form， sum product form says， let me see。😡，Okay。

 let me not get out of myself， let's take a look at some I over here some I is true basically you need to connect these mid termsms AI B I carry I should be010。

😡，呃。10， zero。Well， you cannot read sorry001010，100。

111 and you can again convince yourself that S is connected to those minterms over here you programmed this logic such that S is connected to that and you need to program the logic such that ch I is connected to the midterms where it's one at。

😊，And you don't need this output。And this midterm happens to be not connected to anything because clearly this midterm doesn't lead to a one。

😡，Either in Car or some。That input should not be connected to any outputs and we don't need this output。

 So this way you don't need to design an add， you have a PLA。

 you program the connections from the midterms to the or gates。😡，And this is your adder。

 do you want a multiplier specify your multiplier the same way， have a Pla large enough。

And program the connections。Beautiful， right？There's another benefit of the sample product form you could actually do this with product of some form also but。

😊，That's your exercise for you， if you like。Okay， logical completeness。So much time to be out。Oh。

 okay。I think I'm going to stop here， any questions， any burning questions。All right。

 have a good weekend。 I'll see you next week。😊，Oh。

![](img/eff507112917a3e6efb2d8a0453a5fad_17.png)