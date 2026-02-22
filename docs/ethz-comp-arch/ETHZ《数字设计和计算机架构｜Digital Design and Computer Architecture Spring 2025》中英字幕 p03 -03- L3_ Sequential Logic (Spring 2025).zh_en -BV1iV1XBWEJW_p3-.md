# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p03 -03- L3_ Sequential Logic (Spring 2025).zh_en -BV1iV1XBWEJW_p3-

![](img/a22e513401106860d19b2c28b3136253_0.png)

Yeah。不这。Yeah。Okay。Yeah。坐上。いてです。本然。Give a second。The audits going make the one second。

This USB can connect directly to this。And this的人 just。No no， it's not the correct now。



![](img/a22e513401106860d19b2c28b3136253_2.png)

![](img/a22e513401106860d19b2c28b3136253_3.png)

![](img/a22e513401106860d19b2c28b3136253_4.png)

Yeah。How but now， all good， okay。は、那です。Good。常。そ。还是。あさか。はいか。Is it good， can you hear me okay？嗯ん。Yeah。

啊这好子。Okay。You heard the bell， let's get started。Delar still coming in。

It's good that there are many people who are here。Looks like there's an event going on。

 so maybe it was difficult to enter。Okay， today we're going to。

Continue with combinational logic first， and then we're going to jump into sequential logic。

 so we're actually going to be able to build circuits that are meaningful。😊。

Based on the components that we have started with。And there is nothing magical over here。

 remember we start with the transistor and we build logic gates。

 we're going to build more logic gates and everything is logical。😊，Okay。

 I don't know why this is not working。Okay， yeah， as I said first we will complete combinational logic if you remember we covered a bunch of combinational logic blocks starting from basic logic gates with the decoder multiplex server。

 we're going to use them again today to build memories。😊，We did we built a full adder。

 I'm going to show you again and we stopped that programmable logic array and last time we covered standard form representations。

 some of products and products of sums and also we did logic splification we have Boolean algebra which you had known hopefully before right a little bit at least with maybe different notation but it's the same in the end it's all logic Boolean logic。

😊，So we also discussed that a programmbo logic array enables some of products representation and enables building any circuit and this is what we did last time this is was one of the maybe it was the last slide actually we were implementing a full adder using a PLA and programammbo logic array essentially has。

😊，All input combinations。The sector decoder if you remember it's a three input decoder over here ABC and all input combinations whenever one input combination is enabled only one of them is raised so if a is0 B is0 c is0 this is one and everything else is zero that's the operation of a decoder if you remember last time right so programmable logic a in itself use the decoder and you can actually connect the outputs coming out of these gates to the inputs of these or gates and this is really sum of products representation and this was the connection that we built to realize the truth table of full ladderer using a programmable logic array。

 I didn't tell you exactly how you would program the connections and you don't need to know that except for connecting these inputs to these outputs of the end gates to the inputs of the or gates over here but there may be many ways of doing that that's beyond the topic of this course but essentially a programmable logic。

😊，Enables sum of products representation in a programammable way。是。

And enough outputs in your programmable logic array， okay？Makes sense， right。

Now I'm going to introduce logical completes， which you may have seen also。

 that's a very basic concept， but any logic function we wish to implement could be accomplished with a PLA。

😡，Now this's not magic because you knew this before。

 programmable logic implements a sum of products form and we said some of products form is a canonical representation of any truth table。

 any truth table is any logic function in the end， so I just proving you what I just said over here right。

😡，Basically another way of looking at this， PLA consists of only end gates or gates and inverters。

 meaning if you have end gates or gates and inverters， you can build any logic function。

 but you knew that before also because that's again the product sum product representation。😡。

You just need to program the connections based on the small products of the Nintendo logic function。

So basically， we call the set of gates and or not logically complete because we can build any circuit to carry out the specification of any truthth table we wish without using any other type of gate。

😡，Now this is nice， right？But it's also true that Nand is logically complete。By itself。

 So if you just have a Nand gate， you can build anything because you can actually represent end or not using Nant so is nor by itself I'm not going to prove this。

 but it's fun for you to。T it out。Okay。😊，So that's logical completeness。

 Another way of looking at it is some products form。😊，Okay。

 now let's look at some more combinational box that might be useful in the later lectures。

 plus in your labs。😡，I will not go alter everything combinational because that would take a really long time。

 many， many lectures， we're not going to go over for example multipliers， et cetera。

 your book has some combinational blocks and I would recommend if you're interested in looking at combinational blocks reading the chapters that I recommended earlier。

😊，And these are some of the examples。Okay， so a comparator。Comparator sounds good， right？

Or let's start with an equality checker you can build the compr yourself。

 so equality checker is a comparator， it's comparing two values and you compare if they're equal so the idea is to check if two and input values are exactly the same bit wise。

😡，for。24 bit values to be exactly the same。 Each of the bits at the right position should be equal to each other。

 right， So we're going to build that four bit competitor and it's not going to be。

It's the higher level module picture modular picture will look like this。

 basically we're looking at two inputs， A and B， each of them is four bits。

 that's the notation we will use。😊，And basically， this is checking whether they're equal。

If A and B are bitwise equal to each other， if every bit and the right position is equal。

 then you'll get a1 at the end， otherwise you'll get a0。😡。

And this is how you would build that circuit with X gates。And again， you can convince yourself。

 so each bit you check is a3 equal to B3， this xnor gate evaluates to one if a3 and B3 are both zero or both one。

 okay？😊，Otherwise it evaluates to zero and if any of these evaluate to zero。

 meaning if any of the bits is not equal bits are not equal between the two inputs。

 then you'll get a zero at the end。😡，For this end gate at the end to evaluate to one。

 all of these x nor gates should evaluate to one， that's the function end for input end。😡。

And for all of them to evaluate to one， each of the bits that are input to the X gate should be equal。

Makes sense， right that's the ignore function again。

 you can convince yourself if you forgot what is what is ignore。You can look at the truth tables。

 there's no magic over here。Okay， so that's our equality checkr。Sounds good。😊，Okay。

 so if you want to build other stuff like whether to check whether something is greater than or less than whether a is greater than B or less than B。

 then you need to build a subtractor， which I'm not going to build。

 but I'm going to show you a picture where a subtractor exists。😊。

In this thing that I'm going to call that arithmetic logic units。

Has anybody heard of arithmetic logic unit before ALU okay that's good if you haven't heard don't worry you're going to learn about it this is essentially the unit that does both arithmetic and logic as you can see based on the name it exists in all processors and this is really the core execution unit if you we will see more on later but basically the basic idea is to combine a variety of arithmetic and logic operations into a single unit and module but this unit will perform only one function at a time that's the idea and one function will be dictated by what we will later call an upcode but I'm going to call it a function today but you will see when we talk about ISA later on it will tie to the higher level of software structure as well。

😊，But usually it's denoted with this sort of symbol。

 you usually see AL sometimes you don't see AL and it kind of looks like this and this symbol is arithmetic logic unit。

 it takes two inputs A and B each of them are M bits wide and then has an output and bit wide there may be other outputs also but in this case we see only one and there as you can see a function input F input over here that's three bits so this arithmetic logic unit is capable of distinguishing between two to the three functions eight different functions and to be able to distinguish between those functions you need kind of a decoder F is F specifies your function in three bits and you need to decocode which function you're actually going to execute based by having a decoder internal and you will see that soon but assuming that this is a specification of the functions someone needs to specify this of course later we will see how we will specify this based on the specification of instructions at architecture at the higher level we're not dealing with that yet we're going build。

😊，to that， for example， if an encoding of 0，0，0 specifies that this arithmetic logic unit should output y equals a and B。

 so that's a logical operation as you can see， but y n。😊。

This is a or B this is a plus B in this case it's actually a plus a addition it's an additional operation so don't get confused this is not used for future use let's say and there are other interesting cases over here A and not be a or not be a minus B set less than etc ceter we're not going to talk about everything but your book covers it and this is the complete logical specification of that unit over here as you can see。

😊，So in this case， function is implemented in a different way than I imagined， but it's fine。

 you can imagine different ways of building it， but this one this is one way of building their atological if I actually specify this you could have built in a different way。

 So let's take a look at one example I'm not going to go through everything over here clearly but you can read it。

 There's no magic over here。 for example， let's let's take a look at let's take an interesting case。

 let's assume that the function is0，10 bits 2 to0 is 0，10。

 what happens in this So here's a multiplexer over here。 This multiplexer。

 outputs y that's the output， let's go backwards if you will our bits F10 in this particular case is10。

10 is 2。 So the result should come from here。😊，So we're going to take this。

And pass it to the output based on the specification of the last two bits of f so what is this this comes from the adder as you can see。

 thiss an adder and this adder takes a on one side unconditionally thiss not dependent on the function。

it takes something from here conditionally based on this f and you can see that it's another multiplexer。

 if F2 is equal to0， which is what I specified that we want to take examine。

 then it takes B so this passes B， this passes a， you get a plus B at the end and a plus B propagates to y if F2 is0。

 F1 is 1 and F3 or 0 makes sense right？😊，So that's how you get a plus B。 Now。

 let's take look at a minus B very quickly。 a minus B differs only in。F2 right this is 010。

 this is 110， so we still take this this output of this adder， but F2 is in this case one。

 which means that we take the complemented thing over here。😡，Okay。

 so this is actually a tooth complement， basically complemented。

 basically you do a tooth complement of B， which means that you get minus B and you add a to minus B over here。

 make sense。😊，Okay， you can read more about that later on。Okay。

 so I don't want to go over all of this， but you can see some other ones over here。 Okay。

 so so again， I showed you kind of the subtractor using tools complement representation You can read more about that。

 but there are other。😊，Combination logic structures like shifting， rotating。

 which you will do in your labs， maybe not everything。

 not rotating maybe but shifting multiplication division。

 so all of these are built using logic gates and modules that we have seen。😊，Okay， no magic right。

 and if there's a mistake， you can find it。You can actually build better structures also。

 and this is one way of building the ALU。So AL of course depends the functionality of the ALU depends on what you add to it in this case you have eight functions。

 one of them is not used， but you may have 32 functions。😡，You may have actually 64 functions。

 so it could be something very capable or something not as capable。😡。

And you clearly run into tradeoffs in terms of capability， functionality。

 as well as the air overhead and the latency， et ceter。😡，Makes sense。Okay， good。 Okay。

 so if you want to learn more， there's more， I'm going to show you a couple more things that will be useful later。

 one is try state buffer。😊，This is an interesting thing because it's nice to it enables really gating of different signals into a wire。

 I actually told you that very briefly in an earlier lecture it looks like this it's one of the simplest structures。

 basically if you look at the truth table if enable input is0 the output is floating basically whatever it's connected to a is not connected to y if an able input is0 if enable input is1 a gets connected to y basically y gets the value of a makes sense right。

😊，So floating signal is a signal that's not driven by any circuit we have seen it before。

 remember if we don't connect any of the top part， PmoOS part as well as the NOS part of a CMOS gate to the output。

 you get a floating signal on the output。😡，We said that it's not that bad and that's how I foreshadow the tri state buffer now we're going to see how tri state buffer works and why it's useful。

So a floating signal means that it's not driven by this circuit。

 but there could be another circuit that's driving this y or y that's connected to。

 so now you can connect multiple trit buffers to a single output and decide which one to enable which one to disable it so where this is useful we will see。

😡，Okay， floating circuit signal we discussed this already it's open circuit floating wire。

 so I try state buffer if you think about acts like a switch right if enable is0， the switch is open。

 a is not connected to y if enable is one， the switch is closed， a is connected to y。😊，Sounds good。

 right？Okay。So why is it useful now let's imagine why are connecting to the CPU and memory？😡。

These are big blocks that we're going to think about at any time。

 only the CPU or memory can place a value on the wire， but not both。😡，If they both place a value。

 then there's some collision on the wire， you'll get short circuit。😡。

You can now two dry state buffers， one connected， one driven by the CPU and another they're driven by the memoryme。

 and they are both connected to the same wire， let's called a bus。😡。

And you ensure with your control logic that at most one is enabled at any time。

 so this is one example later we will see this as part of a larger processor。

 but right now we're building up。😡，So this is CPU， this is memory and I'm going to call this a shared bus bus is essentially a collection of wires and this exists in real processors in real processors like this system。

 that system over here， this system over here， there's a system bus where different components get connected to and they communicate with each other through this bus。

So in this particular case CPU is connected potentially to the shared bus memory can also be connected。

 but by designing the control logic such at any given time。

 only at most one of these control signals are enabled or one you ensure that either the CPU puts a value onto the bus or memory puts a value onto the bus but not both at the same time right So why is this useful CPU can put some value and then send the value to memory now your book has。

😊，The bigger picture。Whi basically， for example， in this case， the processor。

 if it wants to put a value on the bus the control logic sets the enable to one。

 no other control logic should set these other enables to one。

 only the processor now gets connected to the shared bus and the value gets loaded or gated onto the bus and this value propagates。

😡，Based on physics principles and assuming the processor， let's say he wants to， for example。

 write this value to an ethernet controller to go out of the network。😊。

This value goes through this buffer， this is just a buffer as you can see it's not a tri state buffer。

 but it could also be a tri state buffer in this case it's a buffer and this ethernet can take that value and do whatever it needs to do with it。

Makes sense， so now we're really connecting different components these are high level components that we are not designed。

 but they operate based on all logical principles that we're going we have been using。

 but the basic value of the triSt buffer is enable communication， it's one method。

 one logical structure that enables communication by enabling different components to place some logical value on a wire。

😡，Makes sense。 Well， good。 Okay， this may be simple， but it's good to think about that。

 So tri state buffer is interesting because it's a switch you can， you can play tricks with it。

 I'll go through this relatively quickly， but this is a multiplexer。😊。

It's a tri state buffer implementation of a multiplexer， it's a two to one multiplexer。😡。

You can see that if s is0， y is equal to d0， if s is 1， y is equal to d1。

 basically you select between d0 or d1 based on the value of S。😡，Makes sense， right？

And this is your book's notation， it's not the best notation。

 but S the inverted value of S is the enable input to this tri state buffer and the regular。

 not the inverted value of S is the input enable input to this triSt buffer yes。😊。

The enemy from us offers。You kind of has to communicate between developers buffers or between someone。

To enable the correct from bus buffers。 And for that， we need another kind of bus shared bus system。

 I mean， Yeah， what I said over here in this， in this case， your book just shows buffers。

This basically is okay， right， somebody puts a value onto the shared bus and everybody sees it。😊。

In this case， right， but if you don't want everybody to see it then you need another you need to make those tri steak buffers。

Makes sense okay， so in this case your book decided for simplicity or whatever reason that these are buffers and not tri state buffers they don't have enable inputs that's the only difference。

😊，But yes， if you want that communication to happen between just the processor to memory。

 for example， there needs to be a system that enables the processor to gate the value and another system to enable only the memory to receive the value。

😡，But then you need try take buffer。Okay， so that's a multiplexer using trisstate buffers。

 you can take it to the next level， that's a four to one multiplexer using trisstate buffers。😡。

And again， enabling inputs are。Controlled based on two bit values S1 and s0 select values if you remember from the multiplexer。

 we're going to build these multiplexers more and more so that's why I'm kind of exercising you over here if S1 and S0 are both zero these zero gets connected to y as you can see right and then you can play the logic game and figure out all of these Okay so it's be beautiful I think。

😡，Weca call this was the For1 multiplexer that we built using and then not gates and or gates before。

😡，走。It's also interesting to see that multiplex are part of the multiplex is a decoder， right。

 I didn't say that last time exactly。 but if you look at this part， there's a decoder。😊，Okay。

So multiplex trende quarterss are kind of like sisters， Okay， yes， using the floating。おちたさあでま。我就唔知。

O这。Its one depending on。I mean， logically yes， right。

 logically you can do anything except as you put more and more things that are connected to a bus。

Lower level abstraction kind of breaks at some point because you're loading the bus much too much potentially and the capacitance on the bus is increasing and as a result you may not be able to operate things very well。

So this is the logical abstraction， but if you take the logical expression abstraction too much without knowing what's going on underneath。

 sometimes you may write things。😡，Okay， so it's always good to know what's going underneath a little bit。

😊，Okay。Okay so let's take a little bit deeper a little bit more underneath how would you actually implement this trit buffer using transistors this is one implementation over here again I will not go through this in detail you can you can because I don't want to go into that lower level abstraction more than needed。

 but this is again not magic this trit buffer is not magic you can see that this was an inverter we had instead of having an inverter we actually have an enable signal。

😊，Connected to the output。And enable bar is controlling the top one and enables controlling the bottom one。

 So if you can convince yourself as the enable signal set to zero， both of these transistors are off。

 so neither。😊，The high voltage nor the low voltage is connected to the output。

 if an signal is set to one。Both of these transistors are on， and this looks like an inverter。😡。

So all this an inverting tri state buffer， and then you can add another inverter to actually get a non inverting tri state buffer。

 so there's no magic as you can see。😊，Okay so now we've covered essentially everything that I wanted to cover clearly there's more but we don't have time for it。

 let me quickly talk about boolean algebra simplification a little bit more because I want to introduce some things that we're going to use later on clearly we have done this and you should be able to simplify this full ladder in aOP form this is kind of like the PLA type of form but you can also build this without a PLA as you can see this is our full ladder if you want to simplify this full ladder you can use Boolean algebra you can use different methods etc but I'm going to。

😊，Show you other ways of simplifying things as well so this is a simplified full ladder these equations are actually good to know so the sumbit is an Xor of ABC in and carry output it is a three input majority function of ABC and these are the simplified versions。

😊，Okay， of course， you can express XOR with n and not or just nagateates。

 but I'm not going to do that over here。Okay so automating simplification actually is important。

 I'll just give you the key idea of how electronic design automation tools operate they really operate based on these equations and what they essentially they want to they try to reduce the number of gates or inputs and reduce implementation costs so that you can get better latency and power and each gate has some sort of characteristics assuming it's implemented in some sort of underlying technology right so for example three nanometer CMOS technology developed by TSMC and in this particular library that's optimized for low power end gate has some latency characteristic and it has some power characteristic not just end gate it has to be some input and gate to input end gate has this characteristic as an area characteristic so for every single gate you may have these characteristic and the goal of the design automation tool and if you don't have that design automation tool the goal of the human who's actually doing that mapping。

😊，I to figure out a mapping from a high level Boolean equation to a really nice implementation that satisfies some goal。

 the goal may be lowest power， highest performance， lowest latency， lowest area。

 a combination of all of those you can see that the design space can be huge right。😡，So in general。

 minimizing logic is good。😡，But mapping the minimized logic to the underlying gates。

 sometimes you may not want to complete the minimal one。

 but a little bit less minimal logic that maps to better gates right it's good to think about that。😡。

Okay but automated design tools do all of that today to some level of goodness and they're much better than in the past。

 but almost always they use Theorms and boing algebra， for example。

 one key tool is really uniting theorem there needs to be systematic techniques that these tools behave so uniting theorem is important it basically simplifies this function right if you look at this function。

😊，B's value changes within the rows where f is equal to one right this is called the onset。

 essentially f is equal to one， this is where the function is on which means that you can eliminate B right sorry a's valued yeah A's value does not change within the onset rows if an input can change without changing the output that input value is not needed so b is eliminated a remains。

😡，Because if you look at this， this says。F's value doesn't depend on B， right？😡，Makes sense， right？

Whether f is 0 or 1， which are the only two possible values in our algebra。😡。

The output is always one so I don't care about B that sounds good similarly so you could also have figured this out of course。

 but this is a simple equation， you could imagine a truth table with I don't know 30 inputs and I don't know 20 outputs now you can actually play these tricks by figuring out where things change or that don't change based on the onset okay and you can actually develop a program that figured that out。

😡，That program may operate on graphs and different things， which we're not going to go into。

 which is also a fascinating topic， but that's not the subject of discourse。

The subject of the story should show that this is possible to do and hopefully give you an intuition that it is possible to do again the same thing over here G's value G's onset is here and it's not dependent on B so in this case you can again sorry it's not dependent on a in this case so regardlesss of whether or not a is0 or1 G is1 so G is really be prime in this case okay so these are the techniques essentially the essence of simplification to put in words you find two element subsets of the onset where only one variable changes its value the single varying variable can be eliminated okay。

😡，And you can do that for a larger number of variables， also a large number of elements。

Now let me introduce one more thing， priority circuit。So we're going to assume that we have。

Some requesters， this could be these could be implementing what I showed you earlier。

 there could be some requesters that are requesting a wire， for example。

 so that you can enable an input to be gated onto the wire。😡。

We have some priority levels and then outputs are grant signal for each request。

So let's say we'll at a four bit prior target imagine that bus requested by four processors or the earlier picture where you had four things that could potentially be connected to the bus we're going to assign a priority level to all of them and these could be the enable signals that go into the tristate buffers outputs are wise inputs are A's and a3 a2 a1 and a0 are different processors in this case and the priority level in this case is static meaning if a3 requests。

😡，the， the bus。It should get it， it has the highest priority。😡，So。If you think about it。

 these are the request signals from A3， A2 A1 A0， and these are the who got the。Bus signal。

 if y 3 is one， a 3 is granted the bus。 If Y 2 is1， a 2 is granted the bus， If y 1 is1。

 a 1 is granted the bus， if y with0 is1， A 0 is granted the bus。 Of course， for this to work， no to。

Let's say requesters should be granted the bus at the same time， Okay。

 and were going to we're going to build the truth table then the truth table looks like this basic。

If a3 is1 set to one， the output by 3 is 1 and everything else is0。Now you can simplify this， right。

 A3 is essentially Y3 is essentially a3。Okay， if a a3 is 0 and a2 is 1。

 y2 should be one and everything all of the other outputs should be0， again。

 priority a2 has priority over a1 and a0， but not a3。😡，If a3 and A2 are not requesting。

 but a1 is requesting， y1 should be1 and everything else should be0， and if only a0 is requesting。

 y0 should be 1 and everything else should be0 and if no one is requesting all of the apple should be 0。

 right？😡，Now， what I built over here is a priority circuit that kind of control these enables， okay。

 just to。Connect the dots over here， maybe I should have copyied that slide over here because it's a bit far。

Yeah， this thing over here， so these enable signals can be dictated based on the request signals coming from processor。

 video， ethernet and memory and enable signals are y3， y2， y1 y0。😡，Or yeah。

 and the request signals are A3， A2， A1 AU。Now this is how you can connect things。

 you can have a priority circuit。Does that make sense？Okay， now let's simplify this priority circuit。

 This was our tooth table。I'm going to introduce something to the truth table that's called an X。

 it is an important thing that's going to make your life easier in the future， x means don't care。😡。

Basically， it means I don't care what the value of the input is。😡。

I'm going to collapse this truth table into this truth table with x's， so if a3 is1。

 I don't care what a2 a1 a0 are y3 is1 and y2 y1 y0 should be0。😡，Same as here。

 if a3 and A2 are0 and1 respectively， I don't care what A1 and A0 are。

 this should be my output over here。😡，Okay， so we can now we understand that right now you collapse the truth table。

 this makes our life easier because we can express the equations much more nicely。😡，So for example。

 here， y3 is equal to a3 because I don't care about anything else over here。

 any other input I should say。😡，Y2 is equal to a3 bar。A2。

Which is over here and I don't care about the other ones， they could be anything。

This is essentially the uniting theorem in action， I told you the uniting theorem with two variables。

 but we've collapsed them into dont cares over here。😡，In the uniting theorem。

 we could have made that don't care also right， I don't care what B is。

 the output of the function is really depend only on these inputs。Okay。

And this is the realization of our priority circuit。

 which is actually simpler and easier to read than the truth table as you can see。😊，Okay。Okay。

 what I'm not going to cover is carnal maps。😡，Which is really fun。

 but we don't have time for carnel maps and it's not really used in general。

 but you can imagine a pictorial representation of minimizing circuits。😡，Actually。

 this could get very complicated I shouldn't say very simple if you have more than five inputs it's very difficult to visualize things that's the reason why it's not used in general。

 but you could have a pictorial way of minimizing circuits by visualizing opportunities for simplification we saw that kind of in the uniting theorem if these value doesn't change when A's value changes with different combinations you can eliminate B you just need to visualize it we kind of visualize it but I'm not going to go to so this is to study on your own I'm not going to ask you anything about that in the exam etc but you may want to have some fun。

😊，Sounds good。Okay， okay， now we're done with combination logic。😊，Any questions？

On combinational logic， yes。こいの五十かスケジとさキャなやだ。Sa it again。はいさんもおじ。I mean， you could， yes。Yeah。

 you could use any technique to answer the question， no problem。

As long as you get to the right answer。Okay。Now we're going to start sequential logic。

 which is going to add。😡，A real flavor to ourrc circuits because so far we have a disadvantage we cannot remember anything you have done right and as humans if you don't if you cannot remember anything you have done。

 you're not fully functioning。呃。Okay， so let's see。

Today we're going I don't think finish is going to be realistic。

 we're not going to be able to finish sequential logic today。

 but we're going to continue tomorrow and we're going to move to a hardware description language and very log and timing and verification and we're going to discuss labs also a little bit tomorrow。

😊，Okay， so this is what we're going to see， we're going to see circuits that can store information。😡。

I'm going to build up to a lot of these well in some order， not the same order。

 and we're going to look at concept， important concepts like state and clock。

 and I'm going to also introduce asynchronous versus synchronous that's going to be even though we're going to swim synchronous circuits all of these in all of this class。

 it's important for people to know asynchronous as well because it's a good contrast to the clock concept and we're going to talk about finite machines。

😡。

![](img/a22e513401106860d19b2c28b3136253_6.png)

So these are some readings basically just to show you that how important memory is。

 we're going to see a importance of the memory a lot going into the future。

 but no real computer can work without memory most of the computer is actually memory if you think about it and we're going to start building these memoriess in this lecture。

😡。

![](img/a22e513401106860d19b2c28b3136253_8.png)

In fact， memories are even if you look at a processor chip。Most of it is really sequential。😡。

So this is the importance of sequential logic I would say these green parts for example。

 are all sequential logic and I didn't mark everything sequential over here and people are adding more and more 3D stacking technologies where you have more and more sequential logic。

 more and more memories I could keep going through this this thing for example。

 most of it is really memory。😡，Most of it is sequential。Okay。

 so what does the sequential mean so if've seen combination logic。

 the circuit output depends only on the current inputs， right？😡，That's combinational。

But we want circuits that produce output depending on both current inputs as well as what we have done in the past。

😡，Past input values， these are circuits with memory， essentially。

You can also think of this a storage elements， there needs to be some storage element basically to store the past results。

 if you will。😡，The question is how can we design a circuit that I can store this information we're going to start with very basics。

 we're going to call this entire thing a sequential circuit。

 so a sequential circuit is not just a storage element。

 but also the combinational circuit that goes along with it。😡。

And the whole purpose of this to solve a problem at some point。

 that's why would map the inputs to the outputs。So we need to talk about capturing data and this may be a little bit surprising if you haven't done your readings。

 if you have done your readings， I'll show you something slightly different。😡。

And there are parts in Harrison Harris that I don't quite agree with when in there are an S Latch。

 so you should take a look at my explanation， also Harrison Harris's explanation。😊。

But we're going to start with something basic cross couple inverters。Looks like this。

This is combinational logic。うん。Or is it combinational logic？

It's built using combinational elements that we have seen。😡，But what I have done here and what。

People do here is you have inverter， you have another inverter。😊，And we have cross coupled them。

 meaning we took the output of this inverter。Called it Q and connected to the input of this inmerter。

 And we took the output of this inmerter called it Q bar and connected the input of this inmerter。

Sounds good， right？Now。This has two stable states。If  Q is1，  Q bar is0。😡，And if  Q is 0。

  Q bar is one， right？That sounds good， and that's logical。

So these are the stable states and again you can read your books books are fine in all of these it also has the third possible metatable state with boths outputs oscillating between0 and1 we'll see this later again this is below our digital abstraction but if for some reason somehow the outputs are not fully zero fully one at the analog level lower level voltages are lower you actually go into an oscillating state you keep oscillating between0 and 10 and 10 and1 at some point you settle this is meta stability you don't need to know about that really for the purpose of this course but it's important to know because we're going to build some more complexity into our cicus to avoid that。

😊，Okay。So this is one problem that the circuit has。Sounds good， right。

 Is there any other problem this circuit has， Well， I guess I kind of gave away。

This can capture data right we have captured a value of one in q or a value of0 in q and that keeps going right it never ends it has as long as this is powered on q is one or zero unless you go into the meta of stable state we're going to ignore for now okay。

😡，So we captured value using combinational logic structures we actually built as sequential storage elements。

😊，Now the problem I see here is， how do I set Q？😡，There's no way I can actually change Q right unless I go physically do something to the wire。

 there's no input over here， basically it's not useful。

 even though it is the most basic sequential storage element。

 it's not useful because we don't have a control mechanism for setting Q。😡。

Now we're going to build that control mechanism。It will also have a method stable state。

 and we're going to try to avoid that and we'll keep adding complexity， as you will see。😡。

So basically more realistic storage elements have a control mechanism for setting cube。

 so we will see the Rs sch soon， but I want to give you a bigger picture first before we go intoRS stch。

😡，Because we're going to go into memories a lot later on， R stches。

 what we're going to discuss in this lecture are expensive memories， they're going to be big。😡。

Expensive in terms of area， power， latency， everything。

Most of memories that we have are not expensive memories。 They're very small， very cheap。😡，Like STm。

 for example， Sm is actually one of the more expensive ones。😊，So this is the S chat。

Just to show you that what we have seen earlier is actually used。

 This crossco inverter actually is used。In caches， for example， of your processor。

 that's the cross coupled inverture that we have seen。It has a control mechanism， as you can see。😊。

Which I'm not going to go into right now， but basically by。Enabling and disabling these transistors。

 you can put a value in or out into that Q and Q bar， okay？😡。

Don't worry about it so don't if you don't understand how this works right now。

 you can actually imagine how this works by this is the transistor that you enable or disable okay。😡。

We will get back to SGM and actually DM later at lecture 20 or so。😡，Okay。

 but today we're going to cover latches and flip swaps。

 expensive stuff because these expensive stuff is also needed when you actually have design processors。

😡，To give you the big picture before we go into the suspense or finish the suspense of how we actually control this inverter expensively。

These are very fast parallel access， but very expensive， one B will cost tens of transistors。

 staticogram caches in processors relatively fast， not as fast as lights and flip flos。

 It's also expensive but less expensive one bit costs about plus six transistors dynamicy ra。

 which is essentially all of the memories of today。😡，They're slower。

 it has a lot of issues like special processing， but it's very cheap。

 one bit costs only one transistor plus one capacitor。

 that's why you can have gigabytes and gigabytes of it。😡，Other storage technologies even cheaper。

 flash memorying hard disk tape。😡，They're much slower， access take a long time。

 they also have some other characteristics that we will talk about even cheaper， okay？

We're going to build a memory hierarchy based on this。

 So we're starting with the very basics of the memory hierarchy with latches and flip plots。

But those cross coupled inverters are actually the beginning of everything they are actually used in a strap。

😡，Okay。Now we're going to build a controllable cross coupled。

 controllable something that builds on the concept of cross coupling。😡。

It's going to be called the Rs Latch initially when you may see it， it may actually be surprising。😡。

But you need to work out the equations and make sure you understand it， it looks like this。😊。

Your book has a no version of it， I'm going to show you a NandN version of it。

 but if you cross a couple two Nand gates。😊，It's called NRS Latch reset or set latch okay so this is one N gate over here it's output is Q。

 this another N gate， it' output is Q bar and Q is connected to one input of this bottom N gate。😊。

R is connected to the other input and Q bar is connected to one of the input over here to the top down gate and s set signal is connected to the top。

😡，Now， data is stored at Q in versus Q bar， just like the previous one。

 but now we have a mechanism for setting or resetting。

 we added more inputs and more complex gates as you can see。😡。

S andR are control inputs so that we can set or reset Q now there is aquiescent or idle state where both SNR are held at one if both S and R are one。

😡，Whatever was stored in Q remains and whatever was stored in Q bar remains so basically if S andR are one。

😡，Whatever value was there is remembered right so we're going to call it Q previousview Q equals Q previous。

😡，You can convince yourself this is the case。And your book actually helps you a little bit also。Now。

 if you want to set this， what do we do， We drive， okay， this is a mind of its own。 We drive S to0。

While keeping R at1 now if you drive s to0， this end gate evaluates to well。

 this N gate evaluates to one because this n is0 and there's a inverter Q becomes one。

And this is one， R is one。We said that keeping R at one。 And this becomes 0。 So this is 0。

 So if you don't violate anything， that sounds good。 So basically， if you want to set。

You drive S to zero。And two becomes one。While keeping r at one okay， if you want to reset。

 you do the opposite， you drive r to0 while keeping S at one and again let me go through it again。

 I think it's the same thing happens at the bottom basically the things flip if r is0 Q bar becomes one。

😡，And this is1， s is kept at 1， so Q becomes0。😊，So our invariant are satisfied， everything is good。

This is good。Now， the surprising part is。You don't want to do this your book is not as clear about this。

 but you don't want to do this in the end because this leads you to emit a stable state later on there are two reasons why you you don't want to do this SNR should never be zero at the same time。

😡，🎼Because if you do S and R 0， Q is1， Q bar is1。 You violated something fundamental， right。

 This should immediately raise flags in your head。My basic logical assumption is Q and Q bar are complements of each other if I set essence r to zero。

😡，I get Q equals Q bar。I violated the rules of Boolean algebra， so I should not do this。

And that gut feeling is correct， you should not do this。😡，伊问 though。You may think that it's okay。

It leads to some meta table state so we're going to call it for basically so this is our truth table if R and Sr1 Q keeps the previous value。

 if you want to setq to1 you set you input S0 r1 if you want to resetq to0 you do this01 and you never do this let me finish and then we're going to take away why not well this should be enough but there's another reason。

😡，呃。Essentialially this is what I said， you break your invariant， which is logically wrong。

The second reason is， if SNR。They were zero and if you transition back to one at the same time。

 basically figure out what's over here。😡，Q and Q bar begin to oscillate between1 and0。

 and their final values depend on each other。 It doesn't meta stability that we're going to see。😡。

And you can actually try to simulate this on your own。

 but there's some analog simulation that you may need to do in the end。

 because you violated something depending on the strength of the structures，😊。

The oscillation may actually eventually settle to two being equal to 0 or one。

 but there's some randomness。 And this this could be a random number generator， actually。

But let's leave it at that for now， random number generators actually take advantage of some sort of lower level hardware unpredictableness。

 and this could be one of those okay。😊，We're going to talk about that。

 essentially if we don't want to do that。😡，So how do we fix the problem？

Let me introduce the Gd Dlasht and we're going to take a break。

So how do you guarantee correct operation of this？😡，Well， ensure no one is able to set SNR to zero。😡。

I introduced two more Ngates， sorry。It's becoming expensive basically now what I've done is。

D is the input that I want to set Q with。😡，And I have a right enabled signal。

If this right enable signal is0。😡，I don't change anything over here。

If that right enable signal is one。😡，Q should get the output of Q should become equal to D。Basically。

 Q takes the value of d when right enable signal set to one， let's go through this if this is one。😡。

You get D over here。Invertted and invertted again， right？If this is one。

 you get D bar over here and again inver it again okay。

 again you can you can you need to go through the truth table， which I will show you in a little bit。

 but SNR now can never be zero at the same time。😡，Again。

 you can convince yourself because it's really controlled by right A and D。Makes sense。

 so you could have said earlier SNR， I'm going to forbid it so that no one does it whenever you do that。

 when you connect complex circles to each other at some point SNR maybe becomes zero okay。

 you can say I forbid it and everybody obeys that rule no。😡。

It is possible that everybody potentially obeys that rule but someone use that shortcut and there may be a glitch as we will see later on in the timing lecture where SNR maybe become zero at the same time and you run into a metatable state that you may not be able to get out of for a long time okay so let's take a look at the gated Dla operation this is input there two inputs right enable。

😡，D， if d is0， if right enable is 0。Nothing changes。 This SNR actually are one， if you remember。

 And if SNR is one， Q is equal to a Q previous。If right enable is one and d is 0， then  Q becomes 0。

 if right enable is 1 and d is 1，  Q becomes1。 so basically this is what we want。

 we we write D into Q if right enable is one， otherwise Q remains unchanged。😡。

And this is a good structure。This is basically this doesn't violate any logical principles depending on inputs and it also doesn't have metastable states Okay。

 this is a point we will take a break and then we'll build up to other structures so let's be back when the bell rings。

😊，Yes。christmas 一。嗯。我什么。算。错。你把这张。好。嗯。这不会。说话这。当月时候。そす。ますね。个。嗯。Thank you。Yes。系。So。算。H。And没。Yeah。

All right。Right。Yeah。开始。Okay。So now we know how to build something that。

Doesn't violate anyil logical principle and also it doesn't have a metastable stage which you will learn about in the timing lecture。

😡，But you see that we had to use one， two， three， four na gates for it。

And you remember from the past and N gate is some number of transistors， four transistors right。

 so that's 16 transistors for you。Not cheap。Yeah。Just to give you an idea， DM cell， one bit。

 it stores one bit in one transistor。😡，Using one transistor and one capacitor， much smaller。Okay。

 so hopefully this is all clear right now。Because we're going to build up from now on。

 we're going to make it even more complicated for our purposes later on。😡。

We're going to add a copy of it in front of this one。😡，But there will be a good reason for it。

 as you will see。😊，So we're going to actually double the number of transistors that we're going to use in a sequential circuit。

 in a finite safe machine specifically soon。😊，Okay， but please， so okay， some of you asked。

 what should we do readings in the book？If you understand everything in the lecture。

 I don't think you need to do the readings， frankly。😡，But of course。

 readings are good for understanding better in the lecture。

 but your book also has parts that are not covered in lecture。

 and I would recommend focusing on parts that are covered in lecture。

 okay and you can recognize them。😡，Okay。I don't， for example， we didn't cover multiplier。

 you don't need to do the readings on multiplier unless you feel like you want to learn about multipliers。

 okay？😡，I'm not going to ask you about multipliers and if I ask you about multipliers。

 I'll tell you what a multiplier is and then build stuff。😊，Okay。

 you may need the multiplier later on， though。Okay okay so this is the gated d latch now we store one bit。

 how do you store more bits， I'm going to introduce the concept of a register which is a very simple concept you basically put these multiple d latches in parallel。

😡，So how can we use D Lates store more data instead of one bit。

 this is our D Latch representation as you can see it has a right na signal and D I just rotated it this way as you can see and I got rid of the Q bar。

 we don't need Q bar for this purpose。😡，Basically use more dlatches and put them in parallel like this if you want to store four bits for example these are four bits this is the most significant bit in general that's the notation that's the least significant bit。

 but we're going to see that later on also。😡，Basically。

 we have a single write enable signal for all latches to enable simultaneous writing of a four bit value。

😡，This is a four bit value right and this is the four bit output。Now we can basically。

 this is a structure that stores more than one bit and can be read from and written to It's a register。

 That's the definition of a register。This register holds four bits and data is referenced as Q bracket3。

 colon zero， closed bracket okay，re going you're going to use this notation and you're going to use this sort of notation in very log later on。

😊，So it's simple， simple， but this is a module also。

 so this is the internal representation of the register module。😡。

This is the module level representation of a register if you see something like this。

 this is register X， a four input， for output register with a right enable signal， as you can see。😊。

Okay， later we're going to add a clock to it for a good reason， as we will see。Okay。

 now let's build memories a。Because this is a register that's a standalone register， right。

 What if you add many of these registers？😡，Like four of them or even two of them。

And you want to choose between register 0 and register  one。You can put those registers。

Let's say on top of each other and then pick one of them， multiplex the data outputs。

But you need to recordcode the address， figure out which one you're addressing。

And then pick the value coming from the right register， Okay。

 we're going to build that memory right now， I kind of explained it。😊。

But before we build that memory， what is memory memory is really comprised of locations that can be written to or read from an example memory array with four locations may look like this logically this is you can see basically four locations require two bits of address。

 00011，011 every unique location memory is indexed or addressed with a unique address。

 four locations required to address bits because you need to have log two to the number of locations right？

😡，In this case I show you what data is stored each location stores eight bits again this an example。

 I'm going to show you another example at the logic level soon this is all higher level addressibility is the number of bits of information stored in each location so if you look at this example location zero zero stores eight bits。

😡，So you could have a register， that's8 wide， right？😡，So this register。

Instead of having it four wide， you could have seven to zero and Q7 to0 over here。😡，Makes sense。

 right？So you can basically change the concept to different parameterize the concept。Okay。

 that's addressability and the entire set of unique locations and memory is referred to as the address based Okay。

 in this case， our address space is。😊，F， we have four locations in memory， right？

Does that make sense？And each location has eight bits。Okay。😊，Okay， a real memory is much larger。

 billions of locations。And each location may have more than eight bits， right？Okay。

 we're going to see those memories again later on now we're going to build a very simple memory。

 but the basic concept is applied to later memories also。😡，So how do we address memory。

 So let's now implement a simple memory array。With three bits addressability。

 meaning each location has three bits。😊，And at a space size of two， meaning only two locations。

 location zero and location one， each location is storing treatments。😡。

Now you can imagine what we're going to do。😡，We're going to have one register。

That's three bits as opposed to four that we've shown earlier。

 that's going to be in our location zero， and we're going to have another register。😡，Another 3 Bs。

In location one。That's our total six bits， nice。Now we're going to figure out which one to access based on address decoding。

 we're going to add a decoder。😡，And that decoder will also enable us to select or multiplex out the right output from the right register。

😡，So we're going to start with this， this is our one bit。😡。

And we're going to basically replicate this everywhere。

 but we're going to do it just like a register earlier okay how can we select an address to read。

 this is what I said in word in let's say written form because there are two addresses address size is one bit。

😡，That's what I kind of said， right？Now these are orbits。

 or you can think of this as our register also， but I want to show the internals also because internals are quite regular。

 as you will see。😊，I'm going to add some circuit tree， so this is location zero， these three bits。

 and these three bits are location one。😊，So I need to have a way of whenever I say address zero。

 I need to get the value here。😡，Here。Here out， So how do I do that， I need a decoder basically。😡。

So I take the adder bit， there's only one bit。If address speed is 0。I get the data out。

 so this is a multipler， so this city decoder。It's a two to one decoder。And this is a multipleer。

 a multiplexer always is a decoder inside remember。

 so decoder is actually multiplexer is actually kind of。😊，Distribute it。

 but let's say let's say lets let's say examine this if adder as a bit as0。😊。

This wire evaluate values is to one， meaning that the input to these end gates are all one。

 meaning that。The result of this Andy says whatever is stored in this flip flop or sorry latch in this case。

 you'll see the flip flop later。😊，It drives here and because of the function of the decoder。

 if at as bit is 0， this is1 sorry， if address bit is 0， this y is 0 and this n gate of value is a 0。

 so the output of this or gate is not dependent on any of these。😡。

Because this address is not decoded。And the output of this。

 each of these or gates is which it maxes is actually dependent on the values that are stored up here。

Makes sense。Again， there's no magic， this is all basics， what we have seen。

Now we willll call this the wordline or decod address。😡，This is the address decoder。

 and this is multiplexor together with decoder Al bit， Okay， so we've seen these structures before。😊。

And you can convince yourself that this operates this way。 I've kind of gone through it， but。

If you haven't followed completely， you can do it， it's all logical。

Weve built up all of these structures， there's no magic here。

 You can actually go through the transistor level of every single one of them。😡，Okay。

 so remember multiplex error just to jog your memory it selects one of the n inputs to connect it to the output here we're selecting between one of the two inputs there are two locations one two we're selecting between either of those based on the address zero or one okay and we're doing it in parallel for。

😡，These two， these two and these two， and if we're reading for matter0。

 we're going to get the values of these in D2， d1， D0。😡，Okay。😊，Okay。So， that's reading。

Reading is good。 Now let's write to this。 Writing is going to be similar to what we have seen earlier。

 We're going to have a write enabled it。 How can we select an address and write to it。

Same things over here Now we're going to in addition to the address。

We're going to also have a right enable bit。 Ad is going to do the same thing。

 Ire the right enable bit。 You get to the previous picture that I showed you。Yeah。Right enable。

 if right enable is one and the address is one。This gate really value to。

This one and then right enable of this one will be one okay。

 if right enable is one and address is zero， then you write right to the top part。Okay。

 if you're unable zero， then you're not writing， okay？😡。

So the operation is basically what we have seen earlier。

 except you're controlling multiple locations gated by the signals coming out of the address decoder。

 remember， this is still our decoder。😡，So if you want to write to address 0。

 you set the right enable signal to one and set the address to  zero。😡，Makes sense。 Okay， good。

 Now let's put it all together。 Let's enable reading from and writing to memory。

 This is what it looks like。😊，Actually， I've shown you this already。

But you need to have a data input I kind of shown you the data input also actually this is the data input that you write with the right naval signal and this is essentially our data dlatch earlier。

 so it operates exactly as what we said if you're writing to address0 then this input D gets transferred into the output of the D latch which is whatever is over here Q essentially but it's not shown over here。

 but if you want to write and read together you need to have the right circuit3。

 which is what I shown you and you need to have the read circuitry which is why I shown you earlier。

😡，And this is our final memory， this is a perfectly functional memory with two locations where each location stores three bits。

😊，And you can read from it， and you can write to it。 The grand laity of reading is 3 Bs at a time。

And you can do it at only one location at a time， right you can do it at address0 or address1。

 but you write to all threebits at the same time， or you read from all threebits at the same time。😡。

Makes sense。Okay， now you want to make it bigger。Here's the bigger one。Not that much bigger。

 but we multiplied it by two now we have four locations with three bits。😡。

If you want to make it four locations， eight bits， add five more of these to this site。

 I don't think we have enough space over here right now but let's take a look at it。

 what I have done。😡，Made the address decoder bigger if you have four locations。

 your addresses should be two bits。😡，And your decoder should decode two bits。

 remember decoder is a pattern detector， it detects which pattern is enabled the pattern it could be 00。

011011 and that's essentially what we're doing that's why we cover decoder as one of the basic circuits。

😡，It enables us to really address each of these four three bit locations。😡。

And multiplexer here enables us to select each of these bits。

 D2 D1 D0 from one of the four locations。😡，Okay， yes。

We question for a better understanding kind of reading。Yeah， one location。呃。In this case， yes。

Basically， yes， as long as you're applying some input， you're reading one location all the time， yes。

😊，But you can think about how to disable that using tri state buffers， et cetera， right？But yeah。

 you can build other structures on top of this。Okay， so this is our memory。

 hopefully everybody understands it。Now， this is an example from one of the books on reading location three。

😡，You can read location 3， supply address 311 set right able to zero。

 these are the gates and wires that are enabled。As you can see。

 the data that's stored in location three latches。Get propagated to output of the memory so essentially the inputs to the meme are these sorry are address address bits right na bit and also the data bits that you want to write if right na bit is one and the outputs are really these bits okay。

😡，You can simulate this in， you can convince yourself hopefully。Okay so decoder I'll go back。

 remember when I introduced the decoder I said it's useful in determining how to interpret a bit pattern。

 it could be the address of a location and memory that the processoror intends to read from that's exactly what I would read it。

😡，So we use the decoder to figure out which of these three bits to read from。

 three bit structures to read from。And this is recall the multiplexer。

 this just to show you that there is no magic in any of this。😡，Okay。

Okay now I'll have a little bit more fun because you're going to do this in your FPG labs。

 you can implement these logic functions using memory as well basically you can store values in your memory and you can implement functions we have seen this actually before in decoder but it's going to be similar you can have memory arrays that can perform Boolean logic functions so in this case our truth table looks like this。

😊，As you can see， this an end function。You can have to the end location and bit memory it can perform any n input M output function you have seen this before actually in the last lecture but now we can have actually sequential storage that enables us and your book actually kind of obfuscates things but meaning it doesn't show everything over here it basically says that there's a bitbl but you can imagine something that are connected over here so I will not go through this in detail but you can think about it so lookup table it's a lookup table it's a memory area used to perform logic functions。

😊，Each address。Is essentially a row in the truth table。

 each data that's stored corresponding to that row is the corresponding output value。😡。

So this is basically。You can build this， you can build this truth table with what I shown you over here。

 I think my picture is better than your books frankly， because just ignore these two parts over here。

😡，Essentially， you have。You can implement the truth table。

By storing the right bits initially over here， meaning。😡。

This is your truth table right if the address is0 zero。

 your output should be0 only if the address is11 your output should be1 so you store zero here。

 zero here， zero here， one here， and whenever you apply。😡，An address combination。

 you will get the end function。Makes sense right okay。

 so if you're confused about the Bitcoin terminology。

 don't worry this is a more generalized terminology over here that were we're going to go into later in lecture 20 or so。

😡，Okay so why am I telling you this because this is the type of structure that's used in a lot of FPGs to implement logic functions。

 your book also talks about that， I will not go through this if you're interested you can look at it。

 but I'm not going to have youre responsible for this because it's not also that fundamental。

 but essentially FPGAs enable things that look like this， you can have different lookup tables。😡。

And by programming the inputs， the data values stored in the lookup tables。

 you can implement different functions in FPJ so when you actually put your logic that you design onto the FPJ。

 you will program some of these lookup tables this is another programmable logic essentially you program the bits inside the lookup tables you can think of it as you program the bits over here such that you implement a logic function that's quite powerful。

What expensive also， and A And B， remember， and A and A And B。

 if you want to implement it using purely combinational logic it's。😡，One gate。It's an an gate。

If you want to implement it using a lookup table， you need all of the circuitry。

 right that's why F PJs are expensive。😊，In terms of hardware to do the same function as a hardwired circuitry。

 they need to use a lot of gates。But the advantages they're quite programgmable。O。Okay。Well。

 this is what we covered also last time this was we previously we had hardwired。

Remember we basically in the last lecture， we implement the function that outputs one when there are at least two ones in a 3 bit input。

 and I had hardwired the inputs。To logic1 and logicg zero。

 but you can actually have many locations associated with them and you can do the decoding。Okay。嗯。

Any questions。Now let's jump into sequential logic circuits。

 we have some basics on how to store data。😡，What is the sequential logic circuit。

 we've examined this now we'll remember how to use what we have built to remember past inputs。😡。

But I will introduce some concepts first， how many of you have used something like this？Okay， good。

 this is a combinational circuit。It's a combinational lock when the combination is correct。

 the thing opens。And。The combination， basically the output output。

 meaning that thing being open or closed， locked or unlocked， depends only on the current nience。😡。

How many of you have used this？Where it remembered what you've done。Probably not this。

 Probably you use something like。This， and many of you have use this。

This is a little bit more secure， potentially I don't know maybe， but this is sequential。

 basically this opens depending on past inputs。😊，Right，Let's take a look at how that operates。

 This is an notion of state。 Basically， this is an notion of state。

 The other thing is not an notion of state。So in order for this lock to work。

 it has to keep track of past events， meaning it has to remember things， so for example。

 you can set the passcode to turn right to number 13 and then turn left to number 22 and then turn right to number three。

😡，And if you do that sequence correctly， this thing unlocks。Imuming you start with the locked state。

Okay。😊，So there's always an assumption what is the state that you stuck with also， Okay。

 basically the lock is not open and no relevant operations patients have been performed。

 that's state A。😊，And then you may have another state that's locked but the user has completed R 13。

 that's state B。😡，And then you can be locked， but the user has completed R 13 and left 22 in sequence。

😊，That's state C， and then state T is unlocked where the user has completed R 13。

 L 22 and R3 in sequence。So therefore are states basically。

 the state of a system is a snapshot of all relevant elements of the system at the moment of the snapshot。

 that's state basically。😡，Makes sense。To open the lock。

 you need to go through states A through D in order。😡，If you mess up at some point。

 you go back to state A。This is actually a finiteate machine。

 I'm going to introduce that more formally later on is if anything else happens， for example。

 if you instead of going to L22， you go to L21 or L5 after R 13， the lock returns to state A。

 there's an internal finiteate machine there。😊，And this is our finite take machine basically so this is state diagram。

 this completely describes the operation of the sequential lock， and you can convince yourself。

 this is from your book one of your books， you can read the book also it says essentially the same thing that I said over here at this point。

😊，So let's take a look at an example over here， this is state A we're locked and no operation has been done by the user if the user inputs anything other than R 13 meaning moves the Noob to somewhere other than right 13。

 you stay here right but if they do R 13 then you go to state still locked。😡。

But now you're waiting for L22。And if the user actually inputs L22。

 you go to another state that's still locked， but you're now waiting for R3。😡。

And if the user inputs R3 does r3 at that point， right， turns it up to location3 to the right。

 then you unlock， okay。And there needs to be some action to make it locked again at some point。

 but we're not going to talk about that okay so we will understand these state diagrams fully later today。

 but hopefully this is something you're going empathize with based on what I said right this fully describes the operation of the state we're going to use the state diagram to fully describe the operation of a sequential circuit essentially because that is a sequential circuit implemented using non-electronics。

😊，I mean， it could be electronics internally， actually。Okay。

 so let me introduce something else very quickly， sequential luck we saw as an asynchronous machine actually。

😊，Modern computers are synchronous machines， so we're going to make our life easier so that we don't go crazy over here。

 we're going to use synchronous circuits。And if you ever design an asynchronous circuit。

 you will understand what I mean by going crazy。Okay。So basically。

 in an asynchronous circuit or machine， state transitions occur when they occur。

There's nothing that synchronizes when each state transition must occur。😡。

This is very hard to design in general， it's prone to a lot of bugs， eta。😡。

Whereas if you're a synchronous， there's something that dictates when state transitions take place。

 basically you divide time into intervals。And。State transitions take place after fixed units of time。

 and we're going to go at the clock。Controlled in part by a clock， but in part by other things also。

 as we will see in Z。So these are actually two different design paradigms of machines in general and also computers in particular with different tradeoffs。

Okay， let's take a look at another simple example of state， how many of you drive cars？😡，Okay。

 how many of you have seen a traffic light？Okay， more than probably that's a super set of people who drive cars。

 right， hopefully。Well， I don't know， actually。Yeah， hopefully， okay。

 but basically a standard Swiss traffic light has four states。I say Swiss traffic light。

 so this is not the same everywhere in the world。There are different conventions you may have figured out in the wrong way or in a bad way potentially。

😊，Because this is a safety critical system let's say yeah， so basically youre green。

 you could be yellow， you could be red， you could be red and yellow， hopefully I got this right。😊。

Okay， now they have different meanings， which we're not going to get into if you drive cars。

 you know， the meaning hopefully。And the sequence of these states are always as follows。

 you go from A， B， C， D， and then back to a。Now there may be different amounts of time you spend in each of these states。

😡，But they're controlled by something synchronous， it's actually a clock。

So you could actually design a Swiss traffic light。😊。

But how do you change state so I'm going to introduce a notion of clock and this' is going to be important。

 this may be surprising initially when you see it， but when you understand it。

 it's clearly what enables us to synchronize。😡，So when should the light change from one state to another。

 that's the key question over here。😡，So basically， we're going to use a clock to dictate when to change state。

😡，This is essentially something that oscillates， it's a signal。You can think of it as a wire。That。

Goes high for some time and that goes low for some time and then goes high for some time and that goes low for some time。

Between zero to one logically。😡，And it keeps doing that forever。Okay。

 people actually designed these things using quartz， crystals， for example。😊。

But this could be a driver or when state changes。😡，For example。

This is what it looks like for one clock cycle， you may stay at state A。

When the clock cycle finishes at the beginning of the next clock cycle， you may go to state P。

You may stay in state B for another one clock cycle， and when the clock the next clock cycle begins。

 you go to state C。And you could keep doing that that's a very simple one。

 or you could design a state machine that stays in each state different number of clock cycles。😡。

That's also possible， in fact it should be possible based on what we've seen so far you should be not you should be able to but you could design a design circuit that stays in different clock cycles for different state different amounts of time we're going to design something different later on okay so at the start of the clock cycle the system state changes meaning this clock edge positive edge clock during a clock cycle the state stays constant keep it that way because you do some computation potentially during that time in this case the computation is very simple you stay at that state you keep things green but we're going to see a smart traffic light。

😡，During that clock cycle， it may actually do some computation and say。

 I'm going to stay in green for a little bit longer。😡，Right， you may have seen those smart。

Traffic lights。Sometimes you don't think they're smart， of course。

 may it may basically compute something， how much traffic is coming from here。

 how much traffic is coming from here， how much backup of us happened over here during that clock cycle。

 you do that computation and you decide。😡，I'm going to switch the state to B。

Makes sense or you decide I'm going to stay name。So at the beginning of a clock cycle。

 you go to a new state potentially during the clock cycle， you do some computation。😡。

At the beginning of the next clock cycle， based on the computation you've done in this clock cycle。

 you go to another state or you stay in the same state。Makes sense。

 this is a state machine basically。Okay， in this traffic light example。

 I kind of assume that with traffic light stays in each state an equal amount of time。

 but hopefully I motivated why you may want to do some other computation。😡，Okay。

 so essentially the clock is a general mechanism that triggers transition from one state to another in a synchronous sequential circuit。

 it synchronize a state change that costs many sequential circuit elements， there may be many。

 many elements like this， many， many traffic lights in this particular case。😊。

You have combination logic that evaluates for the length of the clock site。

 so that smart traffic light doing it's taking inputs from many places， it's doing some computation。

 that's combinational logic。😡，It's producing some output saying。

 do I want to go into what is the next state that I go into and what do I output。

 what should the color of the light be？😡，So it's basically doing some combinational computation and at the end it's changing the state and's also potentially providing an output right so that's combinational logic。

😡，Sequential logic is storing the state， whether the state is green， red。Yeah， et cetera。Okay。

 so clock cycle should be chosen to accommodate maximum combinational circuit delay。

 meaning you do have some computation， you imagine some smart traffic light that has some computation。

 you design the circuit。😡，And you choose your clock cycle based on whether you can actually satisfy that computation。

😡，Makes sense。So we're going to see timing later on， we're not going to discuss it today。

 but keep this in mind。O。So this is synchronous， clock enables synchronous。

 synchronous control can be easier to get correct when the system consists of many components and many states asynchronous is very hard if you want to design a smart light using asynchronous。

 no clock， no notion of clock that's actually very difficult you'll get into a lot of race conditions and you may actually get a race condition meaning some state changes another state changes and you cannot control things easily。

😡，Okay， asynchronous control may be more efficient because there's no clock overhead here。

 we're going to see later in timing， for example， there's an overhead of clock because you need to。😡。

This clock needs to go into everywhere in the machine。

Every every state element should be connected to this clock that's an overhead first of all。

 you need to generate that clock that's another overhead and you need to satisfy the timing with respect to clock that's another overhead and we're going to see those issues later on so synchronous has a lot of overhead in terms of latency but。

It's a whole lot easier to design and people don't go crazy。😡，Designing it， okay。

But asynchron is very interesting for research purposes， Okay。

 so we will assume synchronous systems in most of this course。Now that we know all of these concepts。

 let's design a finiteate machine， or let's introduce finiteate machines first。😊。

So what is a finite state machine， it's essentially formally a discrete time model of a stateful system。

 it has state， as we have seen， each state represents a snap snapshot of it a system at a given time。

 as I already said。😊，And usually FSMs are depicted pictorially， they don't have to be。

 but pictorially it shows the set of all possible states that a system can be in。😡。

And how of the system transitions from one state to another？And FSM can model many things。

 essentially any machine this can model the world actually。

We have a very big and complicated FSM finite machine， except we don't know how to represent it。

 I think。😡，Okay， we will see later we're not going to model the world in this course。

 we're going to model a microprocessor we're going to design I'm going to show you a finite state machine of a very simple microprocessor in lecture 1112 or so Okay we're going to build up to that。

😡，Okay， basically an FSM enables us to pictorially think of a stateful system using simple diagrams。

 I've kind of shown you diagram now we're going to see more diagrams so it consists of five elements I'll go through this quickly a finite number of states that's why it's called finite infinite is something that we cannot think about and design state is we were essentially the snapshot of all element elements as we've discussed a finite number of external inputs。

😊，A finite number of external outputs， as we will see。

 an explicit specification of all state transitions。😊，How to get from one state to another？

And an explicit specification of what determines each external output value。😡。

Essentially how you generate the output， okay， so it's really a combination of sequential and combinational logic。

😊，So there are three separate parts in logic。😡，One is the next state logic。

 how do you go from the current state stored in your state register。

 which is the next element to the next state， what is the value of your next value of your state register in the next block cycle？

😡，State registers store the current state of the system。

 and output logic determines what should the output be based on the inputs and the current state register。

😡，Okay， it looks kind of like this basically， this is our state register。😡。

We're going to add a clock to it soon。So far we haven't added it remember the DL DL is not going to work for this purpose。

 or we're going to introduce something else。This is our state。Based on the state。

 we can generate some output as a particular type of machine， don't worry about that。

 but based on the inputs and the current state， we determine the next state actually output can be determined based on the state as well as the inputs as well this that doesn't depict the general case。

😊，Okay， this is state register， as I said at the beginning of the clock cycle。

 next state is latshed into the state register， remember synchronous。

 next state is latshed at the beginning of the clock cycle immediately。

 there's some timing we're going to ignore for now and we want the next state to be that state to be available during the entire clock cycle so that we can do computation on it。

😡，So we want that element that satisfies these requirements。So we have sequential circuits。

 state register。Input is the next state， output is the current state。

And at the edge of the clock cycle， churn state gets the value of next state that is generated over here。

It stores the current state and load the next state at the clock edge， combinational circuits。

 essentially the next state logic determines what the next state will be at the output logic。

 it determines the outputs okay now let's take a look at the sequential circuit。😊。

How do we implement the state register。Basically， we want two properties。

 we need to store data at the beginning of every clock cycle。

 clock transition determines when input is acquired， even if we're staying at the same state。😡。

We want to obey this， right because that's what synchronous means。😡。

Hopefully everything was clear so far。And the data must be available during the entire clock cycle。

 hopefully I motivated that earlier because we have a lot of inputs and we want to do our computation and we want to have the entire clock cycle and we set the entire clock cycle so that we can make an intelligent decision。

😡，When the clock rises again， goes from 0 to one again。 right。

 So let's take a look at this pictorially。 This is our input Regtry input。

 and there's our registertry output。If our input changes， this is basically next state。

 so when I say register input this is the next state over here， this is the output current states。😡。

And when the clock rises at the positive clock edge， in other words。

Register input that you have gets latched into the register。😡，So this is what we want here。😡，They're。

Combination logic operates using value zero inside the register input and that value doesn't change until the clock rises again from zero to one。

 the register captures the value one only at the clock edge from zero to one okay。😡。

This is very important because we want that value not to change because the combination of logic is evaluating based on the past input。

 if that value changes in the middle over here， that combinational logic will get confused because that's one of the inputs。

 right？😡，Okay。😊，Okay。So this is the desired behavior we want。

Basically here there is some change in the input， but that doesn't get reflected because it doesn't happen over here。

 right？😡，Here there's some change in the input it gets reflected at the clock edge again right basically if input changes in the middle。

 but not when the clock rises at the synchronization point， then you don't want the output to change。

😡，Okay， so this is what we want。Now the problem with Latches， what we designed so far。

 it doesn't give you what we want。😡，So this is ourr gateated delatch。Currently。

 we cannot simply wire a clock to the right na of a latch。Whenever the clock is high。

 thelash propagates D toq。Basically， thelash was transparent。 I'm going to show you in a little bit。

 basically assuming that you wire the clock to the right able。

This is one way you could actually build what we want it's not going to work as we will see because Latch immediately changes its output value and you can imagine this based on what we've seen so far so this is our registertry input this is where D changes so this is the。

😡，And we said。Yeah， clock to right Na over here， the behavior is fine right because right Na。

 meaning clock is0 over here， when clock is zero， the input changes  Q doesn't change。😡，Okay。

 that's the Dlach we've seen unfortunately here clock is one。And the input changes。

 so the output immediately changes， this is not what we want because we want the state register to change its output only at the positive clockage when the clock becomes goes to one。

😡，Again， another undesired behavior happens over here， the clock is high。

 meaning right and na is one over here。😡，If D changes， the input changes。

 the output immediately changes again it's not what we want。

 we want the output to change only at the clock edge， only over here， here， here， here， here， here。

 and not anywhere in the middle。😡，So these are problematic basically。

 this is why we cannot use a latch as a state register in a finite take machine because it will change。

😡，At least the way we wire the clock over here it will change and there's no way of wiring the clock to a D latch it will change its output in the middle of a clock cycle and that's not what we want want we want the state to be stable for the entire clock cycle so how do we fix this。

😡，Basically， how can we change the latch so that D input is observable at Q output only at the beginning of next clock cycle and  Q is available for the full clock cycle？

😡，Basically， we want a new storage element that allows us to read the current state throughout the entire clock cycle。

 entire current stock cycle without changing。😡，Without this current state changing and not write the next state values into the storage elements until the beginning of the next clock cycle。

😡，So now I'm going to through this D flip plot。 I'm going to double the size。

 We want state change on clockage and data available for full clock cycle。 We have a D latch。

 I'm going to call this the first latch。And this is the second latch。

And you've seen both of them before because they're the same thing。

 except we connected them like this and input this here and output'll put this here。

 there's some intermediate thing that is not going to be visible to anyone。😡，So what happens。

 I'm going to wire the clock this way。Clock。系。Enables right enables this one clock low。

 right enables this one。 Okay， now let's take a look at this behavior when the clock is low。

This is right enabled， Dvalue gets passed over here based on the operation of the D launchch， right？

😡，But it doesn't go over here because clock is low and right na is0 over here now when the essentially we called firstlash propag D to the input of the second latch。

Q doesn't change， which is exactly what we want now only when the clock is high。

 second latch latchches D， meaning when the clock Q stores D right when the when the clock goes high。

 this is right enabled。😡，And then this D that you passed over here when the clock was low goes over here。

😡，So in other words， at the rising edge of the clock， clock going from zero to 1。

  Q gets the value of d。😡，Makes sense。Okay， I'm going to take the question later because we're very close to the end zone that hold it for a moment。

😊，So you represent it like this。Hopefully that's clear， you represent it like this。

 this is our abstraction module level， you have a D latch Q Q bar。

 you don't need the Q bar necessarily， and essentially at the rising edge of the clock Q gets assigned D at all other times Q is unchanged internally it's two d latches。

 but now it satisfies our state register behavior。😡，O。Does this， yeah， quickly。En any that right。

Because I think we I might be mistaken when you have the clock enabled， you can write over here， yes。

 no no no， on the other side， we write on first the country。No， you because this is inverted。

So when the clock is low， this D gets propagated over here。😡。

makes sense only one clock transitions from low to high。

 the value over here gets propagated over here。That's right， yes， exactly。InOkay。Okay。

 that's a very good question we'll talk about that later， Yeah， okay， okay。😊，Okay。

 so this is also called a rising edge triggered clock edge triggered flipflop the flipflop samples D on the rising edge of the clock。

 this is called a positive edge， when clock rises from zero to1。

 D passes through Q and when otherwise Q holds its previous value。😊，Okay， I think I've actually。

 this is actually explaining everything that I said earlier。

 this flipflop is an edge triggered state element because it captures data on the clock edge as opposed to level triggered state element。

 which is a latch。😊，Okay， if you want to actually do this for multiple bits。

 you can have multiple parallel D flipfls， this is a four bits state register and you can represent it this way。

 as you can see this register stores four bits and this is four wires。😡，And internally， remember。

 this is what it looks like over here。😡，Okay， I think this's a good place to stop because now given all of this。

 we're going to build a full finite stake machine starting tomorrow。😡。

And then we're going to keep building up。Okay， I'll see you tomorrow。Yeah。



![](img/a22e513401106860d19b2c28b3136253_10.png)