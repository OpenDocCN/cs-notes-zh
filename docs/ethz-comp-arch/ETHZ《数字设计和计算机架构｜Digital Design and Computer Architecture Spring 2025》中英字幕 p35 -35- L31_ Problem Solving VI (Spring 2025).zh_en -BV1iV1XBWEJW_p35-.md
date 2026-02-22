# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p35 -35- L31_ Problem Solving VI (Spring 2025).zh_en -BV1iV1XBWEJW_p35-

![](img/e0165f14e47b78875a94120c278bb24f_0.png)

。Okay。Should I start？Okay。那就是。对。But。嗯。真。继续。Hey， all welcome to our live problem solving session。

 we're going to solve the exam from last year。And I will start with the first question the first question is about Boolean algebra and the question description asks you to complete the true table first based on the description given in the question and then kind of do some simplifications first let's start with the true table。

The problem explains that you have four bit inputs and you have two different outputs and then the first output is factorial。

 which is only one when the input number is a product of all positive integers that are less than or equal to the input number。

So it's a bit of a complex description for zero but the solution for zero is given so we have to go through the next so this the second entry is one and one is a multiplication of one and then all the smaller positive numbers which is none so this is one for factorial and the second input is two two is a multiplication of two and1 so this is also one for the others and if you go through the same description for all the other numbers you will see that it's never the case for any other numbers so all the entries should be zero for the remaining ones and then the second second output is called d4 which is only one one the input4 bit number is divisible by four。

And this is only the case if the input number is zero or4 eight。And I need to fade eight and 12。

Which is this。And all the ones， other ones are zero。

So I was a bit fast in that part because it's like a simple task。

 but if you have any questions we can go through that section。

 otherwise I will go through the other sections。Okay。

So now based on this truth table that we prepared， the question asks you to prepare like or simplify two things。

 the first one is the。Therefore， first， we should write it in the sum of products representation。

 which is。嗯。A not， B nu， C not and B nu， which is the first one from here， and the second one is。

A not， B， C note D not。And third one is a B not C not， D not。

 And then the last one is ABC not and D not。 So this is the sum of all the products that this。

This output is one and we are asked to simplify this thing and the way we simplify is we're going to merge the terms that have most entries common。

 but like differ by one and then this one if you get into the parent of a not C nu and D nu we will see that this is equal to B nu and B。

 B nu or B， and then the other one is if you get into practice of a C nu and D nu this is also B nu。

Or B。We need to do the simplification in this way first。Sorry。

 so we need to first realize that B or B nu is one because either one of them has to be one and if you have at least one one。

 the resulting solution is going to be one so these are done and then the D4 is simplified to a not C not D nu。

Or A C notes， D notes。And we can get this into C not not parentheses by ordering a not and a and in the same logic。

 this is also one a or。AU because either one of them has to be one and another result is CO or DO for this solution。

Sorry， seeing not and D not for this solution。If you have no， okay。Fs to star resort。5在可以是。对。

I mean if you cannot find a simplified solution and if you are not sure that for example what you find is the most simplest one you can use the KEs but I think for this solution it's very straightforward once you come to Cinaina it's very obvious that you cannot simplify it further so kernel maps will be a waste of time but if you have time in the exam like if you solve through all the questions and you just want to make sure that you find a simple solution yes and also even if you did not get the really final solution you will get partial credits so I would say do not waste your time on CarnoEs unless you solve all the other questions。

Okay， anything else？And then last question。Wwhich is about the simplest representation of factorial output。

 but this question is a bit different in the sense that we have to represent the simplest output using only node gates。

 but I think the easiest way is to start with simplifying the factorial expression and then we can think about how we can kind of map it to nor gates。

And factorial is。If you also start with sum of products representation is equal to a nu。

 B nu C nu D nu， or a nu B nu C nu D， or a nu B nu C and D nu。In the same way。

 we can simplify this equation because if you just check these two expressions， for example。

 everything is common except D， and if you get this into a not B not C app parentheesis is D not or D。

And a nu B nu C D not from the the third term。In the same way we can see that this is actually one because d or D node either one of them has to be one and then in a or gate if you have at least one is s1 and this equation is equal to a nu B nu C nu or a nu B nu C and D nu we can get this into a nu B nu parentheesis which is C nu and C D nu so we have to simplify this part and if you cannot see how you can simplify this part very easily and if you have one this who input for example you can just like come up with a simple true table for C and D。

And kind of see the simplified thing。And if you see from the expression， if the c is0。

 the expression is going to be one for sure and if c is1 the is the also has to be0 and if both of them are1 you get zero and that's why you only get01。

 both of them are1， this part is equal to c not。Sorry， C D and not。 So it says a land gate。

Then we can represent this equation like this， so factorial is equal to a nodes， B node and C nodes。

And now we have a very simple equation， but the thing is is this cannot be represented using only nor gates is is so the way you can like can kind of transform what you have in terms of products ands to nor gates is by negating it two times and using the demogons low so if you can negate it two times and then it's going to be factorial so distribute the first not to the terms is's going to be a or B or Cd knot not。

And then there's only this also the second nu and how it works is that you will negate all the。

Iput onces since we had A and B in the not form we ned and then we just get them without a negated one and then you should convert all the sums to products and products to sums。

Now， we have almost everything in the。In the Norgate form so if you have a Nor gate we have three inputs now one is the first one is a the second one is B and then the other one is CDd because if you negate something two times you will get the original thing but the thing is CD is not in the Norgate form so everything is done so we need to figure out how to express CD in the Norgate form and CD is equal to C negated twice we just use the same thing which is equal to C not。

Or be not， not。Yeah。So now we can see that this output is actually equal to Nor gate with two input C nu and D nu。

But C not and D not also cannot be。Cna and Dna should be compete with using only Nor gates as well and there's a simple trick for this。

 so for any input if you have the negd version。It's equal to the。Noring the input width itself。

 so basically if you just or the Cs and get the negated one it's going to be if you get the north so basically of two Cs。

 you get the C nu。And then you will need to do the same thing for D nu。

 so it's also a nor of D with both these basically。And instead of C。

 you need to have a no gate with two C's， and instead of D， you need to get a no gate of2 Ds。

And if you kind of merge everything， you have one。A or B， or C， not。Or D nutss。

 actually all of these two things and everything in a Norway and this is how you can represent the factorial output using only Nor gates。

I guess that explanation was a bit more confusing than the other ones do you have any question and it' also the solutions are a bit different than the ones in the solution sheet that I think is a bit simpler yes。

工就系佢。Os， sorry。And maybe I can go over that part again， so which part you couldn't see。嗯。嗯。

Which is a CD， okay？So we have the AB as is and then we have the CD input to Norgate so we have to represent CD using on nor gate and this is we use the same thing of negating it two times and it becomes CO or D or nor of CO and D nu and the next thing to do is can we should represent CO and D nu using Norgate and the simple thing to do this is using a Norgate with both inputs from the same signal so if you just have a Norgate where both inputs is C you will get the CO as the output。

This is like a simple thing that you should actually consider because it's used a lot actually and it's the same thing for N gates as well。

 so if you have to represent S circuit with only N gates， you can negate it in the same way。

And this is the final final result that you should give but actually don't have to you don't have to draw the na gate to find a solution。

 but it's just like easier for you to visualize。But yeah， any other question？Okay。

Then for the second question。Dll will， I guess。Okay。是。See。Okay。是。Sure。对。啊。Oh。Yeah。啊。Yeah。Thanks。是。是。

Yes。Al right。I had the fortune of getting the FSM question， so it's a simple one。😊。

So the finite state machine question。啊。Yeah， should be easy points， but the caveat is that。

It will be graded quite strictly probably so it's easy to get it right， but it's also easy to lose。😊。

Points unnecessarily， so read super carefully and then you should be golden。So in this one。

re you're supposed to assign some。AController for the polyban， which broke down。So it has two doors。

 which will be outputs and B。And。You can see exercise starts with a specification， quite precise。

Specation， hopefully。And when you go through this， I guess I。Want to read it out for you。

 but when you go through it basically try to look out specifically for any kind of point of that might indicate states already in this case we already gave you the states that you will be needing。

But。Yeah in this year exam you might not be given the States， I'm not sure。

What you should look for is kind of anything that could be a state， right？So here， okay。

 we very nice highlighted them in bold for you so there should be idle states。😊，And then， unload and。

Emergency and transit states as well。嗯。And another important piece。Ofて。

Puzzle view is that you can see there's there's multiple places where we're talking about numbers of passengers So for example we're saying okay。

 the polygon is full when it has two passengers。And when it's again full and idle so somehow the control depends also on the number of passengers。

 then it will do X Y and D and then it will unload all passengers so somehow the passenger count drop to0。

And then the last passenger， so once you're at zero has exited， it becomes id again。

 and then finally there's some additional specification date when it becomes over full。

Which is more than two passengers。Then it will go into emergency mode。So based on that。

 I think there's the key takeaway that we should be doing some kind of counter。

RightSo we should count the number of passengers we're getting and looking at the inputs we get。

 fortunate， there are indeed inputs for the number of passengers that enter。

 So we get 01 when a passenger leaves。 So second pit kind of stands for。Someone left， and we get 1。

0 when someone entered。So， these are the。2 main inputs， I guess。 And then there's two。

Special case inputs， name nothing happening， which you mostly can just ignore。And。

Then one1 is a special case where the Pobon has arrived at the station。

Without anyone entering or living。嗯Okay， so。Let's draw the FSM。

You're asked in sub question A to draw a more type FSM。

 so again it's one of the places where you should be extra careful in reading check if it's more type or mealli type。

So more type FSM means there are some hints in that exercise， I guess in case you forgot。

 but the outputs are basically given at the states， not at the edges。嗯。

So somehow you should parse what's given in the question and fill out the according door output A and B。

 so what did we say I believe。First bit a holds the door open when it's one Okay。

 so let's start in idle state， the passengers can enter through door a so。

Certainly a should be open That's a one and。B should be closed。嗯。I believe okay。

 if you didn't infer it from this that B should be closed。

 we have also this statement down here after the last passenger has exited door B closes。

 so it certainly uniquely determined that this has to be zero。Then while still idle。

It remains that door A should be open， B should be closed。Then once we go into transit， let's see。

Do we be specified explicitly I hope so right when it's full and id poly goes into transit the other station will with both doors closed so it's both zero zero then okay you can imagine that unloading will happen through doorB so once the station is reached should unload all passengers through doorB。

Whileildor A is still closed， so let's call the unload states。0 and1 and0 and1 okay。

 and then the emergency state， let's see here， okay， it opens all doors， remains there。

 so it opens all doors。On one， fine， so that's the state's already done have the exercise basically but。

Again， it's really easy to mix things up here， right？If you， I du't know。

 if you do something really bad and invert 0 and 1。That's a good way to lose lots of points。Right。

 so next。Easy place to lose points here is to not draw a start arrow so you can see here in the question A you're I mean you're simply asked to draw a complete FSM right which in particular involves during the transition edges then you should draw the input bits for each edge and you should specify the output bits for each state and for the edges in particular you should have a start the reset edge so don't forget that one。

嗯。I mean， I don't mind if you lose points that way， but I assume we would。

RightSo we wanted to start in Ile State for sure， initially polybon is in idle state。

Now we should count。Well， I conveniently labeled the states Ile zero and Ile one。

With the intention being， hey idle zero means there are currently zero passengers in the polyan。

 Ile1 means there's currently one passenger in the polyan and。On the other side。

 unload two means there are currently two passengers in the polyan。

 unload one means there's currently one passenger there。Clearly， when you're given states like that。

 you don't necessarily have to use the same interpretation that I or whoever designs the question did when giving you the states。

But maybe you can get a hint from it and maybe youd also don't get name states， right？

Maybe don't get states at all。Right， so in this case。

 assuming idle0 means zero passengers currently ats see what happens on input bit 00。

 there should be no change。 So okay， it would usually be a self loop right， so something like。

This but in the question we're saying okay any input pitch for which no outgoing edge is specified is assumed as a self loop so basically in most places you can leave0 or0 just open omitted and it will be assumed self loop if we don't write this in the exercise it's good that you write it if you make that assumption that will leave edges undefined within an F7 basically。

But you can certainly define them text。Right， so。If nothing happens， we stay there， sure。

 then let's see if we have a passenger enter。We are go there。

Right so one0 we have now one passenger we were at zero passengers now we have one passenger but we're still idle let's see if we had a passenger leave from zero passengers that doesn't make a whole lot of sense so you still need to have an edge defined even if the input doesn't make sense right but。

In this case， the master solution also leaves it open。 the idea is。

It turns out it's a self loop right so if you just don't say anything so here in the case see01。

 you would say we stay idle。It doesn't matter as long as you sure， go ahead。Yeah yeah yeah。

 you can also do more loops， it should be clear that。Whatever you do。Somehow。

 there is so much for every input。😊，And in this case。

 right for whatever there is no input we said would be considered a self loop， yeah。

 you can do multiple self loop， whatever you want to do。嗯。嗯。I guess it gets a bit more tricky in。

In the millli type FSM， you need to be a bit careful with the output between。

Countrys input and output bits。Yeah， alright， so。Basically， it's fine to。

Essentially ignore states that don't make sense or edges that don't make sense。

 but you should define them in some way。嗯。And okay。

 let's continue here so if the polygon was idle and it derives the station that's also kind of a nonsense edge。

 so let's leave that open as well。And assume it's a self loop。 If you're in id1。

 so we couldn't have one passenger， we could still have a passenger leave， right， So let's see。

Input as0 one， except one passenger left。That we would go back to being idle and having zero passengers。

Now， you could argue that well， in the question。Specified all passengers should enter through door a。

 why did we just have a passenger leave that should be a nonsense edge as well， but。K we。

I this thing down here， so not passengers sometimes slip through incorrect doors or even through closed doors。

嗯。So that sounds ominous but the entire points behind that statement think is that。嗯。

It really you shouldn't rely on the state of the Doris。For the correctness of your edges。So。

 we could totally have。A passenger slipped back out through the door they were supposed to enter。

 and we handled that here， we go back with an edgech。Right。

 so if you have one passenger on they are in idle state， if you get an additional passenger。

 you go into transit。嗯。As specified where when it's full and idle of poly goes into transit to the other station with' both doors closed。

So full is at least two passengers， we had one passenger， we added one more。

 now we go into transit right away。That's fine now during transit。What happens。Well。If you have a。

Passenger entering or leaving。So if you have a passenger leave during transit。

 I guess they fell out as specified here， if you have a passenger fall out during transit。

 so it should go into emergency mode sure it's。😊，Let's try to avoid losing passengers along the way。

 but if we do， we go into emergency。And then we have also the option if the polybu becomes over full at any point。

 so at least to the passengers。Then you should also go into emergency mode now。

The only two times we really have at least two passengers is in transit and in unloading。

 so if during transit somehow there's a passenger hopping on unexpectedly and the polygon is too heavy now it's over full。

 then we should also go to emergency as specified here。Right， and then in emergency。

 we just remain there。 as you can see， there's no outgoing ads。 essentially。

 essentially it remains there as reset to id state。 So you could again draw this with kind of。

You know， self loop and specify everything， or you might as want to specify no and to rely on the fact that。

Specifying nothing means a self loop， as we said here。Right right。Then from transit。

 assuming we didn't get anything unexpected happening， we should eventually arrive at the station。

So we should get a signal 11， poly1 arrived at the station。

And then we would be in in state unload two。Because we had two passengers on board。

 we're now unloading two passengers and there are still two left to unload。

If you're currently in unload tool and there's an additional passenger entering。

 and you get the same issue again， the polygon becomes over full and you should go to emergency mode。

That's fine。Now， hopefully， instead of entering， doing unloading。

Passengers lead leave so we can have the edge 01， go to unload  one。 There's only one passenger left。

And if we unload another passenger， we go back to iddle。喂。If during Unload one。

 you have another passenger enter again。Then we go back to Unload2。

 we're still trying to unload our passengers， but then。哦。Unfortunately， we have two again。

And the other edges， we can again leave unhandled or rather。

Assumed a self loop because they make no sense to get as an input。Right。

G more questions about this part。 Hopefully I got， hopefully this looks the same。

 now on the master solution。 Let's see。嗯。Yeah， looks about right。Okay。嗯。嗯。Yes。Sorry。对不起。是。对是。

That's right。 Yeah， yeah。 So we specify up here， right here。Okay， at any point。

 it stops in emergency mode where it opens all doors and remains and reset to the initial I state。

 that's kind of an external thing resetting。W。Yeah。Okay， boom。So嗯。Second part of the question。

This one should be rather easy points if you solve the first one carefully。

So now you're supposed to design in a second FSM that's based on the first one。

AndThen you should ring a bell。 So what that means is your output bit should be one。

Whenever the earlier Mo type FSM opens or closes the door。

 and it's constantly ringing in the case of an emergency。So， I'm。And by the way。

 it also says you're supposed to use as a meal type for someone。Right。Now。

Meie type recall meli type means there's no more outputs at the states。

 so the more type FSM there were these output bits right of the state or even placeholders for it。

 here there are no placeholders because the output bits in a mealli type FSM is supposed to be on the edge。

So you're supposed to kind of。Take the same FSM， right。You need to keep track of the same states。

 somehow。Every time you're in a state here， you're supposed to be in the same state over here。

 so you need to keep the same control logic if you will。

 but your outputs need to be different because well you need to have a bit one whenever your door is here change。

So what you can do essentially is just copy all the edges for now。At least the edge's input bits。0。

Thereer one。唔知咯。玩玩。Therere one。嗯。Are you missing any， yes we are。Okay， I think now it should be good。

 Don't forget the reset date again。Okay， I omitted now the unnecessary self loops again。嗯。

What's important to note here is that， first of all。

 we have to give an output bit for each of these edgees。And。

The self loops now right since we're just making an assumption what a self loop supposed to mean if it's undefined and we're saying。

 okay， if you leave something unspecified， it's a self loop without a bit zero so if we need anything else in a self loop we have to explicitly specify that self loop。

走嗯。Let's see what our output is supposed supposed to be。

 so the bell should ring whenever the more type FSM part a opens or close the door well between idle states。

 it certainly doesn't change anything。So if you just remain a little bit of different passenger count。

There should be no bell ringing， no doors open or close we close from idle state to transit。

 we of course close the door right we start。Driving。So the output is one。

 then when going into emergency state from transit， we open all doors。

So certainly both of these should be an output bit1。If you go for transit into unloading。

 you should have a one because you open the unloading doorby。And then between unload states again。

Nothing changes。 So no bell ringing。And between unload and iddle。

We do have a bell ringing because we open the closed doorrby and we open the A。Right。

Now there's one more edge missing here。That's what I pointed out before， any self loops are assumed。

Out to theory if they're not specified。So。When we read the specification of the emergency state。

 it says。The bell is constantly ringing in case of emergency。

 So when we are in emergency state on any input。So let's say input X X。

 you could also specify all four inputs， if you will。

 but if you put X X or star star as a placeholder it， that's fine。Then it should also be ringing。

Okay。Okay。Yeah。You're right。 thanks。 See， that's how， that's how easy to lose points。 And。

 and I even put colour there。 Thanks， right。😊，Yes。It should be one because want we open door A。

 I guess。Now hopefully you have an output at every age。Yes。Any questions。W， and they can go。

On the next one， I guess， thanks。是。What's next for。嗯。嗯。結。Am I audible？Okay。对。Okay。

This is a relatively very simple question。I A BS micro architectureitecture circle。

 whether each of the following is an aspect of the IA or the microarchitect。

 so generally IA refers to the interface between。The underlying hardware and what the software sees or what the programmer has access to and microarchitecture is how underlying hardware is actually implemented and is working。

嗯。In the exam， please also pay attention to this note。

 I read over very very quickly now we will subtract one point for each incorrect answer and award zero points for unanswered questions。

Okay， let's get to the first item， two level global branch predictor so as a programmer。

 like in general softwares I need to know about that， so that's how things are implemented。

Location of the bits that identify the destination register in an add instruction。

 so that is what we actually need to know want to write program。

numberumb of the instructions fetch per cycle again micro architectureitect ratio of the number of floating point to integer general purpose registers。

 so here the ratio is not like very important but we know the number of registers so we need to know how many registers we have to work with both floating point and integer so subsequently we can also have。

Calculate the ratio of them。Let's see ISA。Number of integer arithmetic and logic units or ALUs。

 again， we don't need to know about it。It's just how things are implemented。

 instruction issue width of the processor or pipeline， it's again micro architecture。

 but if the reasoning behind any of these choices is not clear please stop me。嗯。Nice， okay。

So CMD supports ISA because then we need to know whether we can use it or whether we can use it in our software code。

呃。L3 cash replacement policy in micro architectureure width of the database bus to memory。

My architecture architecture， we don't necessarily need to know the widths of it from outside。

The size of the addressable memory by the program， so that is clearly ISA。

 the number of cycles it takes to execute and add instruction， micro architecture。

Ability to choose a specific cash replacement policy using operating system core that is ISA so if the system had already a replacement policy which we couldn't choose then that would be micro architectureitecture because that's how the underlying thing works but here it's referring to a scenario where we can from the software sites select which replacement policy to use in our hardware so that's why we choose ISA here。

Number of read ports in the physical register file， so that it's micro architectureitect。

Fun of each bit in a programmer programmable， prefectures。

 configuration registers so that is going something programmable， the user can change it。

I say number of L3 cash banks that goes into micro architectureiture because that refers to how things are implemented actually。

So are all these choices clear to you？Okay then。I think we're done。不是。是。嗯。没嘢。好唔。Yeah。Yeah。对。嗯。对。Yes。

佢佢吗。So you can solve the fourth question of the last semester final exam， which is very low。

So the first one， yeah， like。嗯。So the first question asks。

 what does this code do analyze the following whereload model and answer the question？

Let's first take a look at the module。Sm is called my mystery module。

 it has three inputs four inputs， clock n in one in2， and one output which is in rack。

 which is out and one register variable， which is VR1。So here we have always postage clock block。

 here we have two main。If closes。And then this is the always waste block。

So let's take a look at the remaining part， assume that the inputs in one and in two always have the following values in one is6 to4 bit and hacks that as single base its total of I guess 16 digits。

So here， please note that this every digit is four bits。So here into is eight bits length。

And it has eight bits， just eight。Digits， so it asks what unss the signal voltage does the out signal get in the following wave form the other。

So we need to fill this all 11 gray boxes。So let's start。

So for the first one we know that so this is Pos log right and this always block what happens is in that when we let' say start executing this block the variables that are assigned in this block updated at the end of the cycle which means that this post clock zero will be executed here but the results updated after this cycle so here we know that the initial value is zero like so the out becomes zero。

So here， this outs will be updated using this one。So here we see that enable is zero。Right。

 so we go to this if close enable is0， we cannot satisfy this one and variable is one is initially one here。

So that makes output is again have the same value as the previous one， which is again zero。

So this postage clock1 will affect this one。So here we see that there's a。

 let's say in enable has increased rise。 That means that enable becomes one now that means that this if close。

 which is in the。A12th line。Will be satisfied， but that means as variable one becomes one。

 but it becomes one after the always block executed。 So now it's still zero。

So here we go to this if block into variable one。What that means is into zero bit。

We check this route， but it is one。You'll satisfy this one and then out。Will become0 plus。This。

So I know you're not familiar or this one， this means that this is the base。And this is。

How many bits youll count afterwards。 So let's。Do that with example。

 So we know that variable one is still one here。 So what that means is maybe I can write here。

In  one，0。Plus 8。Which is equal to in1，7 to zero。So you start from this space， you count eight bits。

So we take a look at here， so we know that each digit is four bits， so we take zero1 hour from here。

So what that means it's zero plus one output will become one after executing this。

So means that here is one。So when we execute this one。So。The one is one now。We are one。

And out this one， so let's execute that one again， so enable is now。It doesn't matter。

 variableable one is one， so we don't go into that loop， that block。 and we checked this if。

28 first one， so variable one is not one。 Now we go into that one， so variable one becomes two here。

But it will be updated after this。Always block executed。 So here line 24， we'll check into first bit。

 not the second bit， but the first bit。First， but is one。So it means that we will go into this。Clos。

 so outs will become out plus。In one variable， one multiply 8 plus 8， which that means。In one。8 plus。

You will do like out is one in one is。Its two now out become three。So， now we will execute the。

Third one was such third。So here we。But is。Out， which is three。It was three。 and this one is。

 we know that we already know this is also three。 This is 8 bits。

 So 3 minus-3 is 0 now out becomes 0。So now we will continue doing that again and again。

So here again variable one was four now we get the four4 is one and that means that we will perform addition out was zero and。

Garding corresponding in one is4， which makes out4。 And then we execute again， the fifth one。

 the in two is one again。 And what that means is os will be updated as four plus。Five here。

 which is equal tonight。And then we will execute that。So again， it's， I guess， yeah， one here。

And then we will go into disclose， we will increase the rare one and we will check this if。

 which is one， and we will perform addition again out was nine in one。Is now this。Part is 6。

 which makes 50。And then。So we increase the V  one and make it out 50。 Now， in the next cycle。

 we execute。Again， they always block where one is now， I guess，6， yes， and which is0。In the in and2。

 So which。Which means that we need to perform subtraction here。It was 15 and this one is seven。

Makes it a， I guess， yes。Okay， now we perform the same thing again now where one is 7。

7 bit of into is one means that we need to。So here sorry so where one was seven right so we increment where one by one。

 which makes it eight， but the problem here is where one is three bits so eight is actually four bits right one000。

What happens is that ver one takes the least significant threebs。

 means that you reset the ver  one to zero， so in the next cycle ver one becomes zero again。So。

 but let's execute this side， so where one becomes zero here。We checked seven bit off in two。

 which is one。And then we perform addition8 plus 8， which is 60。 Now in the last cycle。

 we know that very is zero and you see that enable is also zero what happens here is that enable is zero。

We don't go into that log and where one is also zero， don't execute that log。

 it's the same as the first site。So output will get the values as the same as the last cycle。

 which is 60。So， that's the。First question。Do you have any questions on that one， yes。谁这。嗯。提供。嗯哼。Yes。

 yeah。 So you need to keep track of that。 it's a little bit tricky。Yeah。

 but you see there's a pattern over there， you increase by one， you get eight bits of chunks。Yeah。So。

 the second question。Check。是。This one is relatively easier than the other one。诶历史。

So here says that there are numbered blanks， one to five in the following parallel of code。

 and we have to choose one of the options。Overhe。So let's start with the first one。

So the model called my model， inputs clock， input reset， input data。

 and we don't know the type of the results。So when we checked the choices， output， output track。

 output track 0 to0， and input track so we can understand that there is no such thing as input track。

It's a syntaxer， we can eliminate that easily from just looking at the second line。

 So when we check the line 24。We see that they used assign so if it was re。

 we couldn't use assign here because Re can be only let's say updated inside always loop。

 always block and we cannot use assign keyword for this one we should use let's like this state so which means that result is via and we won't use Re over here and here。

 so which makes a is the correct option。So for the second one。It's state and it asked。

 I think it has the type of the state， it says defining a two bit signal with an initial value of zero。

So you can understand that it says initial。So which means that will change。In the cycles。

 and we use state inside of the always block， right， So which makes it。Breite。

So we will use rec here， so it says that defining2 bit， so that's why we cannot choose B。

 so the only option is a。So for the third one， it's line nine， I guess。

 and since the set the next state to2 bit one1， which is three。So we check the a1 bit3。

 it's not possible's it's not a correct syntax because so this indicates the base right in the binary base we only have either0 or1 so you cannot say one bit3 over there if you want to use three。

 you can use hes at aimilal or decimal base so it's not syntax correct this one and B is also the same。

If it's a binary base， you can only use one or0 so in the C。You see that it's a decimal base。

 it's 11， yeah we can say that， but it's2 bit length。

 but our variable is 11 is4 bit length right so again it's not correct。So D is the correct one。

 which is three， then you don't explicitly say anything like the bit length and the base。

 it directly says it's a decimal base， so you can easily use this one。

 which means like decimal base three。So the correct answer is P。 So for the fourth one， it says。

Line 15， set the next state to two bits 0，1， if all bits of data are one。 so what that means it's。

It's beginning of the， let's say variable here so we can understand that this should be like reduction type of thing。

 So that's why we can we will eliminate a here。Indeed indeed。

 it doesn't make any sense One data is like。Again error， so only choice are B and C。

 so we know that it says that if all bits of data are one。

So which means that we have to perform and reduction and then we will understand that if the orbits are one right。

 if if we use let's say C it's a logical negation so we have As。

 eight bit of data it will get the least significant bit and that's why you won't satisfy this let's say concern so the correct answer is B。

So the last one is。5th， it's in the again， line 24。 It says that assign sign。

1 to result if the state has any bit set to one， otherwise assign bid0。 So we know this again。

 this administration， right， so。It's in the beginning of the， let's say， the variable。

 So we cannot use C over there。 So we know it's also said that。Has any bit set to one。

 so it should be all right in or if any of the input is one， the result is one。

 so it's we can easily say that it's or reduction， which makes it a。

Do you have any questions on that one？Okay。Thanks。Okay。不是。没。Hello。So this is another true。

False question。嗯。Before I start with the questions。

 the policy for these sorts of question we have is basically if you circle the incorrect answer。

 we deduct one point。If you do not circle any of the answers， if you leave it blank。

 you don't get any points and if you do it correctly you get in this for this question you get two points each question each。

Tru fourth question。Okay， so I'll start with the first one， so I already have the answers。

Circleled here。So I'll start with the first one and I'll try to explain the reasoning behind the answers。

The first one is a main memory access typically consumes less energy than a register file access。

And this is false because typically it's the other way around right we have our register files inside the CPU。

 it's very close to where we do compute so it's a small structure compared to main memory。

 so it takes much less energy to access it than main memory。

The second is building a larger memory array by increasing the length of the array's word lines and bits increase the cost。

But does not increase the access time of DNA。So the first clause is correct， it increases the cost。

But the second part is incorrect because。Increasing the length of the arrays。

 word lines and bit liness will increase the access time because we have longer wires to drive。Yes。

应该。就是。Right like。Yes。I think you can do that， yes， it's a good abstraction， yes。Okay。

 the third one is activating a D cell。Temporarily destroys the value stored in the DM cell。

So this is true because if you remember from the lectures， main memory lectures。

When we activate a DM cell， we're activating a word line that connects the cell to the bit and after the after the cell is connected to the bit line involved share is charge with the bit meaning that。

Whatever value it was holding onto。Is now essentially gone because。

It shared the charge with the bit the charge level in the cell is no longer as it was before we accessed it。

Well what happens is if you wait for a little longer。

 the sand amifiers will be enabled and then write the value back to the cell。

 so temporarily the value is destroyed， but it will be written back。And that's why this is true。

The fourth one is DM cost in dollars or Swiss franc's Herbit is much higher than that of SRAM。

This is。False， because。I mean， the real reason is really manufacturing technology limitations but。

Another way to find this out is basically we don't have。

SRAM that is as dense as Dam in our systems today and the main reason。Is essentially cost。ok。

Dram costs much less to produce per than era。The fifth one is the memory hierarchy of a typical computer system comprises different memory technologies。

Again， if you think about the two most common things we have in the memory hierarchy。

 the caches are built usually using SstrM and the main memory is usually。Built using data。So。

 that's why it's。True， and if you if you look at storage。

 that's even only a different technology like SSDs， we have flashlash。嗯，你。Recently。

 accessed data should be kept。At the bottom level in the memory hierarchy， bottle level meaning。

 the main memory or disk。But not at the top level， meaning caches。

And this is false because if you're frequently accessing a data。

 you want to keep it close to your processor。So you want to keep it at top level because you can access it much faster。

putting it in。Main memory or disk does not make much sense because you spend more energy and more time to access that data。

嗯。A program with no branches has high temporal locality in its instruction memory references。

So a program with no branches will have an。They'll have instruction memory references like these right so these are。

White addresses。This is just an example。And imagine we put our program starting from the zero address and main memory。

 and each instruction is four bytes。We'll have an instruction memory reference stream like this when we execute this program。

It will go on forever and there's no way for this program to access。A byte that it accessed before。

In terms of instruction memory reference， because there are no branches in this program。

So we'll just move on， this means。And none of the instructions this program brings it access。

 it uses twice， that's why there's no temporal locality being exploited here。Is this clear？Okay。

And then the next one is a cache that has a blocklob size equal to。

The worst size of memory access instructions， okay， it's not visible now。哦。Okay。Yeah呀。

Cannot exploit special locality。Yes， so let's look at what we have today typically。

So you have this cache line size， let's say of。512 bits， right？

And let's say your word size is 32 bits。This means you can fit 16 of those words in this cache line。

嗯。Why this is important is。You will access this word from your processor。

 the processor executes a load of instruction too。This word that I highlight here。

But we will end up bringing all these other words。In the cache line to the cache。And。

If there is special locality in the access pattern of the processor， memory requests。

It might be the case that we will。For example， next， access this word。

And this cache essentially enables us to exploit spatial locality。

But the cache we're describing here has a block size equal to the word size of memory access instructions。

When the processor accesses a 32 bit word， it will bring end up bringing the whole cache line， right？

So， theres。There are no other words that we can access in that cache line。

And there's no special locality to exploit。Okay， is this is the reasoning behind this statement being true。

Is there any problem with that？冇。Cool。The next one is memory banking enables concurrent access to the memory structure。

This is correct。 if you remember again from the main memory lectures， we can have。

In the case of data specifically。We can activate one row in a bank and immediately after that we can activate another row in a different bank。

Essentially， at that point we say， okay， we can access these banks concurrently right。

 we overlap the latencies of many different operations。Okay，10 is。In DM。

 accesses to different rows in one bank。Can be serviced faster compared to accessorieses to the same row in one bank。

呃。This is false so the first clause is describing so this part。Different novels in one bank。

 this is describing a raw conflict。That means you have a row enabled。Basically。

 this access pattern will have a lot of raw conflicts or bank conflicts， this means that。

You enable it all。You spend some time to satisfy the latencies， the timing parameters。

And then you precharge that row， you enable another row， you precharge it。

 enable it's like a double side row hammer attack if you。就是慢么大。So， basically， to。

To service the next request， the memory controller has to close a row， open another row。

Closing and opening rows takes。Long time， let's say it takes。This takes TRC amount of time。

This second part describes access to the same rows， same row in Momac， this is a row hits。

And then then we only have to wait for the memory controller has to only wait for。

A very smaller latency that is like TCCD， which is TRC。

 you can think of it as around like in the order of 45 nanoseconds and TCD is much smaller like I don't know。

 smaller than two nanoseconds。Basically row conflict and we're questioning role conflict and role hit latencies year yeah。

C that我。Thank。あみで。不道。可有。Not exactly like that just。

It's just that when you have a row already enabled and you want to access another row。

 you have to first precharge the bag， like close the open row and then activate the next row。

 like the actual row you want to access。And youll have to wait a very long time。

To do those operations， but if you already， if you're accessing a row that you have enabled。

 that means you're servicing that access from the row buffer。

So it's already enabled you have the data ready， ready to be pushed through the IO essentially out of theM。

That's why it's much faster。Okay。So 11 is PCM is non volatile。

 which means PCM retains stored data even when it's powered off。And this is correct。

 because that's how PCM works， I guess this is some sort of。You know。

 you know what non volatility means and then you just。嗯。You just decide that this is correct。Okay。

12l is if a hypothetical system is not constrained by cheap area， memory cost， energy consumption。

DM would be the best memory technology to use in that system。This is。False， because when you。

When you're not constrained by these three things。Essentially you would want to improve like you're looking for the best performing memory technology。

 right that would be。Not data one example is Sstr。 you you can have S arrays at the。

UmProviding the same density as your D because we don't care about cost or area or energy consumption。

We chose the fastest。Memory technology， that wouldn't be the。That's why this is false。

13 says the entire page table is typically stored in physical memory。嗯。This is false。

And the reason for that is if you think about the page table for a program because you have to have。

And the。嗯。Many mappings from all possible racial ad to the physical ades。

 we have these multi level page tables， which enables us to essentially。诶。

Have some of the possible mappings。Not in physical memory。

So this has something to do with the multi level page tables。If this is not clear。

 I can come back to it。Otherwise， I'll just， yeah， I'll move on for now and you can at the end。

 let me know。So 14 is virtual to physical address translation is on the critical path of a memory access。

 this is correct you have to， I mean your program uses virtual ads。

You have to translate that visual address to the physical address。To。To access main enemy。

That's why it's on the critical path of a memory access。And finally。

 virtual memory makes programmers and architects tasks easier。This is false。I mean。

 the first part is correct， which maybe makes programmers tasks easier if you。

Because the program at least does not have to care much about。Memory allocation。

 they still need to care about it， but not as much if you don't have virtual addresses。

But micro architectects tasks are not necessarily easier because they now have to implement。

These new structures that translates from mutual adacy to physical adies and potentially improve on them。

 that's why。This is false。And that's the end of。Question 5。Yeses。你啫。そうです。I think here。Where's。

Basically， the entire pitch table is。Typically stored a memory。

 what's the like what's the other alternative and then you think about disk right。

 but it it's not stored at all is a better way。To think about this question。

 I think basically you don't need in in the multi level page table。

 you don't need to have some levels initialized at all right。

You put enough mappings into your physical memory such that。没 you不 only the necessary my that。嗯。O。好。

嗯。嗯嗯。Yeah。Okay。嗯。See， can you hear me， guess so。So this is the classic performance evaluation question。

So in the introduction， it tells you that you are working on a project called awesome Meory。

 where your goal is to optimize the memory hierarchy for a particular core architecture。And。

Basically， you're evaluating two different systems。

 one system that is the baseline system and the other system that is this OM system。

And then travel away these two architectures， you run some tests and the tests are described here in this one to three。

 so first you collect some performance metrics for single thread applications at one to four。

 they run in isolation in the baseline， so they run by themselves each one of in a core。

Then you create two application mixes to perform a mood program simulation。

 so you have two course basically you're going to run one application in one core in another application in the other core and they are going to run concurrently both in the baseline and in the。

Also main configuration and we are going to evaluate those two application mixes。

 mix one has application one and two and mix two has applications three and4。

So you run all of those tests and you collect the data that is in this table here。

 so if you look at the table you have the execution mode a single thread of moodot programme。

 the application mix， is only reasonable is only relevant for the MoOot program case。

 the configuration both the baseline and they alsoM， the applications and some metrics。

 so here have executed instructions， executed cycles， less level cash misrate。

 branch misprediction and different bank conflicts。

And then he's going to ask you to do a bunch of small questions on top of it。

So the first question is asking you to calculate what is the instruction per cycle IPC of which one of those four applications when running in isolation in the baseline configuration。

 so IPC as is written here actually is the number of instructions。Divide by the number of cycles。

Of a particular application。And so basically you need to check the table and fill up the instruction in this cycle。

 so for application one， the number of instructions equippedted is 100，000。And the cycles is 40，000。

You don't need to do the math on this particular part of the exam if you just leave it like this like 100。

000 divided by 400，000， I'm going to get you I'm going to grade you I'm going to give you 100% of the question the exam if you try to do the math and don't write down the equation and write down the the wrong value I'm going to cut your points because I don't know which math you did actually and if you do math and I cannot follow all of the steps like that there is beginning of the end there is a high chance of me reducing some of the points because I don't know exactly how you grant from A to B so the best thing to do in a performance evaluation question is just leave it like this and you're safe。

So then you continue doing this for a lot of the applications， IPC of application2 is going to be。

 again， all of them are 100，000 actually。And just this day。Number of cycles is going to change。

Is 8800，000 for F2 is here。😔，And then， 500000。And20 to。Okay， this is good any question here？Okay。

 it's quite straightforward。And then here is telling you probably you are not familiar with this metric and but we are given the definition so in the end becomes again a math problem so to ensure that the system throughput of a core system to measure sorry the students uses the weighted speed up metric which sums the instruction per cycle I perceived that you just calculated slow down experience by each application compare with many applications running alone so when you run two applications in a system that has shared resources there's application can experience a slowdown because for example if they want to access the out cache or then du they are going to have to compete for those resources so this metric is basically measuring that slowdown that you are on top of the treading or multi parallelism that you're input into the application。

So basically the way you to calculate system throughput or way to speed up for Oload mix is that is the sum of the applications running in that Oload mix where the nominator here is the IPC of that application when it's running in a share environment divide by the IPC of the application when it's running alone so this might be confusing if you' not familiar。

 but you're going to break down the calculation in two steps so it's going to be more or less fine。

So first here is asking to calculate the IPC shared for A application one。

 two and three and four of the four applications when they are executed concurrently in the Mo program application mix for baseline and are configuration so the calculation is the same IPC is steel instructions。

Divide by cycles。But then you're going to consult another part of the table。

 so here you have the table have the Mo program workloads for the mix one have application one and application two and is asking for the baseline so you're going to get the instructions for this row here is again 100。

Thous0 divide by the number of cycles， which is 200，000。

And this is the value for DIC shares according to the table。

For application one and then he's asking to do the same thing for the configuration of alsoM so you look again here in the stable Moot program mix one。

 alsoM application one， the instructions now change to 80，000。And the number of cycles is100 to。

Again， you can leave the math like that you don't need to solve the math。

So you do the same for application。Two， again， you go to the table application to here。

For the baseline number of instructions， again。100000 number of cycles is 900000。And then again。

 for also Ma for application2。Is this row here， number of instructions is 80，000。

And number of psychos is400，000。Just notice that these numbers are really small。

 I need to make it larger next time。And。And then you continue doing that for application three and application four。

 I'm going to look at the solutions actually please。You' see for some time， but is basically100000。

If I did about 60000 here。Here is 80，000。😔，W did buy 400。And this is a。100000。Right by 20000。900000。

Bye bye，20000 again。Is there any question here how this was calculated？

Mussically line probe the room。Maybe I look through the solution here。

That is more beautiful than my handwriting。嗯。Any questions？Okay， I to give a minute for to go。😔，Yeah。

 don't worry about those small values here。 Don't expect you to calculate them。

So then it asks you to calculate the weighted speed up for each one of the two applications mixes when running the baseline configuration。

 so if you look at the equation here， let me remove this。

So weighted speed up is the divide you need to divide the IP when running in a shared environment divide by the when running alone。

 So this is going to be for mix one mix one have。Application 1。And application2。

So the weighted speed up is going to be the IP PC。Shared。For the baseline。

 right of application one divide by the IPC alone。Of application one plus the IPC shared。

Of application to divide by the IC。Aone of application to。

 and you have already calculated all of those in the previous two questions actually。

 so you can just copy and paste the values over here。

So one thing that is that a lot of people got it wrong。Maybe was not a lot。

 but was not was not one or two people in this question and was not necessarily a problem with understanding the numbers so the sum of of a divide by B is different than。

A1 plus A G， let's see。对呀。So those two things here are different。

So a lot of people last time was actually summing the IPC shares of app1 and E2 and dividing by the IP alone of sum of the IP alone of a application one and application2 that is mathematically wrong so the sum is you need to do any fraction a fraction first sum with another fraction。

I think this is what people were getting wrong last year。嗯。

So here you just collect the values that you calculated in the previous questions so here should be I'm going to put the here I have the fraction numbers already so I'm going to put them here 0。

5 if divided put 2。5 plus 0。11 divided equal0。1，2，5 again。

 I don't expect you to we don't need to write like this you can just write a fraction if you just write here。

 for example。嗯。I think that should be。I this correct。I， is here。

 So which value is the one that calculated here。 If you just do 10000 divided by 2000， divided by。

The IPC alone of application one is this one， 100000。I'm getting from here。Divided， by 400000 plus。😔。

For application2 is 80，000。Divide by the hundred thousand。Divide by。Is all value here。

That is good enough。To get the points， so just plug and play the numbers and that's good。

Is there any question here？Yeah。So basically and then in the next one is' going to ask to do the same thing for mix two。

 so mix two has application3 and application4， so it is going to be IPC shared。App 3。

 divide by IP tune。Oh， sorry， alone。3 plus IPC shared。😔，A 4 divided by IP PCC alone。E。For。

 and if you look at the。Previous。Previousreviewous。Exercise that we did in question A and B。

 these should be 0。16。Divided by 0。2 plus5 divided by 5。嗯。그。Okay。

 so this question D was also some question that people got something wrong last year。

 so now is asking to calculate weighted speed up when the application mixes are running in the awesome and configurationration so you do the same thing so wait to speed up。

IPC， shared。E 1， mix 1 is F 1 and F 2。Divide by the AP PC， alone of app。1 plus IP shared。E 2。I' see。

 along of app。2。So if you look at the the previous。

Questions with already calculate the IPc shared right of app1 at2。

 E1 and app2 the awesome configuration right so you have them here。

But we don't have the IPC alone of app2 running on the OM configuration and if you look at the table this information is not given as well because actually you don't need that information and you're calculating when your alone baseline system is your baseline configuration that you run the applications you don't need to run them again in the OM so the IPC alone is when you're running that application in the baseline system alone is this slides called baseline right。

So a lot of people got I guess， confused with this and didn't they said， oh， I cannot couple this。

 but actually you again is just use IP alone of the baseline because when is the single threaded system。

So I'm going to do this one just because might be confusing。

 so the IPC shared of F1 that we calculated before。Also， man is 80000。Divided by the100000。

And therefore for app 2 is。80000， divide about 400000。And the shared IP。

 the E alone of F1 and F2 is of the baseline that calculated in the first question， so it's 100000。

400。嗯。100000 invited by 80000。And this is the answer。Yeah。Again， I'm going to highlight depth。

This is really important you cannot sumator the numerator and the dominator when you have a sum issue and I would give you that you would grade your wrong because not a grade I'm going to I would cut your points because everyone should know this。

嗯。And then the same thing for mix2 and mix2 is F3。Close F 4。So this is IPC shared。

Of F 3 divide by IPC alone。Of app 3， plus A PCC。She。And four gloves。ABC alone。Apple。4。

 and I'm going to look at the solution because I don't want to copy the whole values。This is 0。

2 divided by。0。2。乐丝。5， divided by 5。哦。嗯。Okay， is there any question here？

Great quite straightforward and then there is a more qualitative question here so is asking that the students do not want to review the primary technique behind this awesome and configuration when asked they provide a list of architecture techniques and told you that some of them could be the reason behind awesome system throughput improvements awesome memory systems throughput improvement。

And so the first one is that alsoMm increases the less level cache capacity by two times that of the baseline also me random minds the memory request to reduce this the bank conflict also mem employs a perfect branch predictor that always predict a branch direction correctly and also MAm employs efficient hardware perfecure and it's asking you which one of the above cannot be a possible reason for also mens higher performance over the baseline and explain your reason based on table one so basically need to。

Look if one of those metrics are one of those metrics here are being affected by one of those things that are saying here。

 so the first thing is that also maybe increases the less level cash capacity by two times of the baseline so look at the table here less level cash capacity you're going to look at the you're going to compare。

Alsoso mem and the baseline for a single application right so if you look at the miss rate for the less level cache for the mixed one versus in the baseline versus in the also mem you can see a reduction right is's not necessarily a two times reduction but it's definitely a reduction in the number of less level cache misses so and usually when you apply a technique in computer architecture usually you don't see necessarily a linear impact of like oh you reduce the number of they improve the case size of two times it does not mean that you're going to see a decrease in less level cache miss of two times but you should see a decrease if your application have some degree of excess going through the less level cache so just that indicates that okay this might be true。

That' is possible。Also memorand domain mine my memory request to reduces reduce the wood here du bank conflict again you look here there is a column du bank conflict and you can see there is a reduction in the du bank conflict when you go from the baseline and the also mem configuration so okay this might be true as well。

So the answer is the tree but I'm going to go to four Also memory implies a efficient harder perfecture so what does a harder perfecture does it brings data right from a memory to the cache to try to avoid you're going to for avoiding you to miss on the cache right so you going to increase in the hits the number of hits that you have in the cache so again you can see that is a decrease the number of mees that you have in the cache so because of that you're going to see increase hits right as a ratio so this also might be true so it can also be possible that this is a possibility。

The third one also employs a perfect branch predictor that always predicts a branch direction correctly so there is a column here that have a branch misprediction and you can see for all of the configuration is always 1% so it might be the it might be the case that you your baseline branch prediction is already so good and you don't even if you improve it you don't see improvement or might be the case that you don't see an improvement。

U。Because this is not a technique and then there is a key word actually perfect if it's a perfect branch predictor you should never mispredict。

 so this is the answer three。😊，So you could argue in all of those things that I said。

 you could argue that there is no decrease in the brain misrediction。

 you could argue that this value is not zero and should be zero。

 all of those things will be reasonable explanations。

And that is pretty much that is there any question related to this question？冇点。Yes。死去。没问题。

You're going to have a six minutes break right now。Hello， everyone。Let's continue the。Solving system。

So I'm gonna solve the Tommaula's algorithm question and as you may have seen throughout the course out of order execution and Tommaula's algorithm is one of the most fundamental concepts in modern processors。

And I'm sure there will be a related question in the exam。

 either some sort of out of order execution question or the So algorithm question。

 So let's start with the definition here。 So what do we have we have any in order fetchs。

Out of order these paths and in order retirement execution engine it's the same as the ones described the during the course。

And it says that it employs Thomasula's algorithm， right？And we have the following characteristics。

Four pipeline stages fetchs， thecode， execute and write back。

 it says that the engine can fetch one instruction per cycle， decode one instruction per cycle。

 and write back the result of one instruction per cycle。The engine has two execution units。

 another to execute art instructions and the multiplier to execute model instructions。

The execution units are fully pipelined， the other has two stages。

 E1 and E2 and the multiplier has four stages E1， E2 E3 E4 and the execution of which stage takes one cycle please whenever you read these characteristics be sure of whichs are relevant for the question you're solving because not all of these here are relevant to the question some of the characteristics here are not needed for you to solve the question。

The next one is important that's why I'm saying that it says that the other has a two entry reservation station。

 What does that mean we can perform two additions at the same time and the multiplier has a three entry reservation station we can store three in flight multiplications and you can see that in the。

Next here we have two entries here for the addition。And three entries for the multiplication。

 So this is a really important detail that you should。

T down a note when you solve the question in the exam。So the next one is also really important。

So this is important one an instruction always allocates the first available entry of the reservation stations in top to bottom order。

Of the corresponding execution unit。Top to bottom means that。For example， here， as you can see。

The first question， this one is the。All this one。Right， why， because it's in the bottom。Jim。

So full data forwarding is available during the last cycle of the execute stage。

 the tags and data are broadcast to the reservation station and the registered table。

What is the register layer table， the register layer table shows us for its register。

 the validity of the register， whether the register depends on some specific computation from the reservation stations and this is pointed to with the tag so as you can see in imageS B。

Here some registers have some tags。For example， register R5 depends。Yes。Oh， sorryry， yeah。

Now yeah sorry sorry I will fixed that so here register r5 depends on the tag X。

 so the tag X is basically the tag that says okay whenever we compute the tag X。

 we will be able to populate again r5 and know it's current value。And it says here， for example。

 an add instruction updates the reservation station entries of the dependent instructions in the E2 stage so the updated value can be read from the reservation station entering the next cycle。

Therefore， a dependent instruction can potentially begin its execution in the next cycle。

 this information is not really important given the questions that we will have later。

The multiplier and other have separate output buses which allow both the other and the multiplier to update the reservation station and they're at in the same cycle。

 again， given the questions this is not really relevant。

And then instruction continues to occupy a reservation station until he finishes the ride back stage。

The reservation station is ded after the right pack stage。 This is important only for。

A small amount of let's say information that are needed in the exercise。

So let's go to the problem definition then so the processor is to fetch and execute five instructions just note this down we need to at the end you need to report five instructions。

 even though as you can see there is reservation stations there are four tags。

There is probably one instructions which was executed before these four tags exist in the reservation stations。

So as you can see here in the reservation stations， we have Z X， Y and T。

 these are four ongoing operations， but we have five instructions， so there is at least one in。

 basically there is one instruction that was executed before all these in flight because the snapshot was taking taken only with these four in the reservation stations。

不警。Assume the reservation stations are all initially empty and the initial stage of the Reg table is given below in figure A。

Instructions are feds thecode and executing as discussed in the class at some point during the execution of the five instructions。

 a snapsshot of the state of the reservation stations and the register li table is taken Figure B and C show the state of the R and the out of the snapsson time and it does indicate that the value has been cleared a question mark indicates that the value is unknown to you a question mark doesn't mean that there is no value it means that you just don't know it and you don't care about it right don't confuse yourself with that。

So let's see the questions。Based on the information based on the information provided above。

 identify the instructions and provide the data flow graph below for the instructions that have been fetched。

Please appropriately connect the nodes using edges and specify the direction of each edge label its add with a destination architectural register and the corresponding tag Okay。

 let me give you some hints on how you can start solving this so that you don't。

Let's say fall into the trap of going into loops of trying to figure out which are the registers。

 okay。So let's start with something so the first thing you should do is try to find out what are the simplest instructions which do not depend on anything else right so let's see here we have an addition right what is the tag of the addition。

It's Z， okay， and to which tag does this correspond， it corresponds to R8。

What does that mean whenever we finish the computation for the tag Z at the reservation station we will update Reg8 so for sure the destination register for this a instruction is register 8。

好。So we know that this one， you can start writing it here because don't go from paper to paper。

 so it's like this is R8。And as we can see， there are two registers which are valid and there are values are ready。

😊，The values are 28 and1。So you need to find out from the snapshot of the registerlia table。

 which registers have the values 28 and1 as you can see are at least two registers with these two distinct values。

 this is R1， and R2， r1， 28， R21。Okay， these two registers are ready and which means that there is no computation where these two registers are destination registers and they need to be updated。

And our8 is going to be。Updated using the additionion result of R1 and R2 so the first thing you could do in the data flow is the following。

So start with the most simple one， so you have a node which is。They registered at one。

Then you have the register R2。And you create a data flow， right， so you have a plus。

And what is the outcome of this， The outcome is。The tag， which is Z。And the destination register。

 which is R8。Is everyone care with that？不见。Okay， let's move on to the next one。 So we saw this one。

 You can cross this out。We found out this one， okay， we do not need anything else with the additions。

 right？Or we might need， but we'll see。不解受。As you can see。There is a register。

So we need to find one instruction then which was executed before all these instructions right as I said there are five instructions。

 four of them are in flight so there is one which was executed before all of these right and we need to find it before we proceed to these instructions to the rest of the instructions but James。

 how do we do that？We go to the first instruction that was pointed here， right， it's x。And Hud says。

X。Which is。R 5， right。Depends on the value。50。😊，The register number one source register and the value1。

And what can you see here， you can see。That are two。And R3 have the values one。And50。

So what is the cut here？The catch is that if you've seen the initial state of the register A table。

R 3 did not have the value 50。R3 had the value three so which one is the first instruction that was executed before everything it was the one that updated register r3 okay。

 and we need to find what sort of instruction this should be。So from all these values。

Which values can end up in the result 50？嗯。It's R 7。Plus R4。

So only there will be distinctive values in the exam so that you will don't have a conflict on how you come up with a 50 right so R3。

 R4 and and R7 and end up adding and giving the result to R3。So。Okay。So you know that for sure。

 the instruction add are3。From R4 and R7 is the first instruction executed before every other instruction。

 so continue with that one in the exam let's say that you have here。All 4。

I will leave a gap for a specific reason。Let's keep it R7。And。嗯。Let's do the additionion。

And you take。Here the tag doesn't matter because it's a previous instruction。

 you can assign the tag in whichever way you want。The result is not free。Okay。

Is there any questions up to this point？好钱。So。This way， given that we found this instruction。

 we also know that x。Is the result of the multiplication over R3， which is 50？

And of a valid register with a value 1， which is R2。Right so the next instruction。

 the first instruction which was executed is this one。It's R5。

As the multiplication result of our three。To耳to。进。嗯。So。This is done before everything， right。

 and we take our two。Multiply it with what？With R3。And as a result， what do we have？Tag x。

 which is the tag of R 5。And the destination register， which is our file。Is that clear？不见。

Then you go and check the next ones。行。Okay。不是。你说。是。Okay， then we're searching for y。

Why depends on the following registers？Tag X， register with tag X and the register with value 20。

Which one is the register with value x from the previous step you go back to your data flow you see that the register with the tag x is register r5。

 so for sure one of the source registers is r5。And then the value 20 and you check from your table。

 is there any real with value 20？In this table， we don't see any register with value 20。

And we go to the initial table。Do we see a register with value 2 n0， yes we see we CR R7。

 but in the latest table the R7 depends on value y， so what happened here？

The destination register is the same as a Shos register。So we use the initial result。

 the initial R 7， but we overrite our seven， right？What do we do here？We used our seven as a result。

We multiply it with x right， and we end up we end up in y。Or 7。Jame。

So we have how many instructions do we have so far。

 instructions is equal to the number of your nodes， right， you have one node here。2， three， four。

 we missed one instruction， which is the last one。嗯。Okay。My。What is the destination register of T。

 The destination register of T is。R9， so for sure it's a multiplication that involves as destination register register R9。

And what are the values of the source opera？23。Which is of six。And50。Which is R 3。

Right that's pretty straightforward， we multiply r6 with R three and we get the result now nine。嗯。

That's why I left some space here。So， you get。A six。Multiply are six without three。

And you get the result T or9。So right now we have all the five nodes that we need。

Which corresponds to five different instructions。And we need to figure out exactly what right now we need to go to the second exercise which says filling the blanks with the five instruction sequences in program order。

 there can be more than one correct ordering， please provide only one correct ordering。

When referring to registers， please use their architectural names。

Place the register with a smaller architectural name on the left source register box。Okay。

 so I will ask one question。As we saw， R1 and R2。We add them and we end up in our eight， okay。

The question is， can this be the first instruction？Why can't it be the first instruction？Sorry。

So I'm saying that we saw that adding R1 and R2。We end up in our age。

 which is independent of the rest of instructions， can it be the first instruction？

If it can't be the first instruction。Then when do we add three to our。

When do we come up with the result r3 from adding R r7 and R4？

Is that possible like the result of our three is not in the reservation stations？

So this is not possible if you add first R1 R2 to the this nation register rate it wrong。

 that's not possible。Because we don't have the previous instruction。

Which is R3 from our foreigner 7 inside the reservation stations， so don't be confused with that。

 The first one is one that doesn't exist in the reservation stations， which is add。R 3。Rre 4， R 7。

After that， you can place this one， as I mentioned add r1， the add R1 and。R 2 to r8。

 this you can place it anywhere you want， but it cannot be before this instruction。OrJa。

 so for example， I can do here add。R2 R 8， R 1 and R 2。Okay， so what's the next one。

 The next one we need to do。Is we use the register R3 and the register R2。

To come up with a result in R5 so it's a multiplication。The result is in our file。R3 and R2， I mean。

 yeah the opposite way。Because it's not important， but。Yeah。And then so we did this。We did this。

Theyically let me call it differently so we did this， we wrote this one， we wrote this one。

 we wrote this one， then for sure here you need to keep the order correct。Right。

 the order should be correct， do not mess up the order between the nodes because R 7 depends on the new result of our 5。

Which means that the multiplication is。Sttored in the Reg R7， which is the Y。

And it's the result of the multiplication between our five and which one are seven。And the last one。

It's the multiplication between R6 and r3 in r9。This instruction。And this instruction。

From what I always explained so far can be placed anywhere after this instruction， right。

 why because the opera are not used， the destination registers are not used as a result in any other instruction。

That's it。 I think if you were able to like concentrate a bit and set quickly。

 which are the easy instructions to determine then it will be an easy question。Thanks a lot。Okay。

Yeah。是。是。Okay， the next question is about GPU and CD。

So this is actually one of the common questions in our exams that you need to calculate the CM utilization rate。

So yeah， I will quickly go over to Christian。So we define the C utilization of a program that runs on a GPU as the fraction of C lanes that are kept busy with active threats during the runoff program。

So and we usually， I mean， we should calculate it at the end of the application， not in the meantime。

So usually we have a quote that you need to analyze it。So here in this code。

 you can see that this is actually a C code that's going to be basically offloaded on a GPU kernel。

So you have a four that the number of iterations is。1024。And in each iteration。

 we have several instructions。So we have first this simple instruction。

 then we have a if condition instruction。 There are also some instructions inside the if block。

 and at the end we have this。Instruction， right， So the total number of instructions inside the for loop is K plus 3。

Yeah。So we are about to actually off each iteration to one thread。So since we have 1024 iterations。

 means that the number of threads that we need is 1024， right？Okay。So， now， let's see the。Questions。

So the first question is that how many wars does it take to execute this program？

So we know that basically the verb size。It is 32 threads。Yeah。And since we have， basically。

So the number of wars。ul be。The number of。Treats。You goodbye。Varp size。是。So we have， as I said。

 1024 threads。And each warp is 32 thread， which means that we have 32 warps。I guess it's clear。

 right？Okay。I mean， usually in these questions， the first part is so easy。

But it gets a bit more complicated， but this actually last year was quite easy。Yeah， yeah。审批的意思。

So in this example， yes， so yeah， the number of threads per verb is equal to number of sea delays。

Yeah。So in part B， you are saying that assume that the condition for the EFA statement is。

I mode 16 equals to0。Then we are saying that what is the number of instructions k in the body of the conditional block。

 basically we want to understand the number of instructions inside the if block。

Such that the CD utilization is 11 over 32。Okay。So we need to actually calculate the。Sem utilization。

 parametric。With the K and then try to solve the question。

 So usually when you want to calculate the utilization rate， you need to see。Basically。

 the number of。Active。Ts。Divided by。Ideal number of threats。嗯。Okay。😊。

So our ifA statement is i mode 16 equals to zero， which means that in every warp。

There are two traits。Thread I D 0 and thread I D 16。That they will take this branch。Other than that。

 they will actually。They don't enter the ifpl and they go to this instruction K+3。So。啊。In every verp。

 there are two threads。That they actually take。Or execute K plus three instructions。

And the rest of threads in every bar， which is 3。Execute。Only three instructions。This one。

 if instruction and this C equals to blah， blah。And the ideal case that we want is basically。

 we want that all 32 trades。Actually execute K+ three instructions。So this equals to 11 over 32。

So you need you can easily cancel out these two and then we have these 2 k plus 3 plus 90。

Equals to 11。不是。And then we would have nine。Equals to9， which means that。K is 7。Is it clear。I mean。

 the key point is to come up with this equation。不其呃。Yeah。

 which is not hard to come up because so we know that because of these EFA statement。

 all warps are the same。The only difference is interver that some trades actually they take the branch and other than that they don't。

So you can actually write the equation only for one work because。Alld verbs are the same。Okay。

 we will repeat this again in the。Next one also okay， so part C is a bit harder than part B。

So we just changed the EFA statement is saying that we will enter the EFA statement if I mode 16 equals to zero and the same。

And I is less than 512。嗯。So with this ifA statement， we understand that basically if。

If the T ID equals or greater than 502l， we won't take the branch for sure， right？

Which means that the first 16 Vps。They may run inefficient because some of the threads inside the warps。

 they may take their branch。Some of them they don't， but their last 16 barbs。They won't actually。

 they will run fully efficient。Because none of the trades would take this branch。

So when you want to write the equation here for this new equation。

 you need to actually consider different ver。Okay。So there are 16 verbs in the end。

That all of them have have 32 traits。And all trade actually， they run all three instructions。I mean。

 only three instructions。Because。They run this， they run this， and since they don't take the branch。

 they only run the last instruction。Yeah。But there are some warps， I mean。

 the first 16 wararps that they don't， they have some inefficient runs。

So we can say that there are 16 verps。That in each of them， two threads。Exeecute。

Cve plus three instructions。And the remaining 30 trades， they run three instructions。

And here we would have say， okay， we have 16， I mean， the last 16 verps。They have each of them。

 they have it has 32 traits。And all of them run three instructions。But the difference is here。

 So we want to have。16 warps。Each show them 32 traits times。Co plus T 3。So this is equals to 508。

Okay。So， then we need to。Solve this equation。So we can cancel out 16。

And we can also cancel this eight， this is four， this is four。And will we have。Yeah。Okay。

 I guess I think right yeah，96。Plus。2 call  three plus 90。Equals to。560。Thats 20。Oh plus 3。

Then we would have 18， K， core plus 3 equals to。in-60， which is。So， then。This is 7。And then。

 car is fourth。Is it clear。ok。Yeah。嗯。Okay， so the next one。

 the next question is about branch prediction。In here we have some information about the system。

I will mark them as we read。😔，Great。Okay， so we know that the processor implements an in order pipeline with multiple stages and each stage completes in a single cycle。

And it only stall after we see a conditional branch instruction and in other times we just complete all instructions。

Without stalling。 So here we have the we have a。Code so in here we see two loops and in one the loop depends on the value of this register。

 which is r1。And we subtract one from R1 in each loop， in each iteration of the loop。

 and we check if it's greater than zero or not， if it's greater we go back to loop here。

And the second one is not important because it's not conditional。

So in here we have a table with results for some R1 values。

 we know how many cycles they take to complete。And the question。

 the first part of the question asks first how many stages are in the pipeline and second。

 how many cycles does a conditional branch instruction cause the stall？

So let's give them some letters。 So this one is should be called D to be consistent with the。嗯。

Soution that you know。 Okay， so we can now。Formte the number of cycles that each of these will take。

So let's say C is the number of cycles。So， we know that。

The first instruction will complete after it goes through the pipeline and since each stage take one single cycle。

 we will get the result of the first instruction。In peace cycles。

And the rest will take one cycle each since this is pipelined， so other instructions。

 let's say the total is I will take this many cycles。

So this is the number of cycles that we would get if we didn't have any stalls and let's say that we have B as the number of。

Conditional branches。So each time we see a conditional branch， we will be stored by the。

So that's the final formula for a number of cycles so when we check this table。

 we can put like some numbers in place。So let's first do R1 equals2。

So we know that this loop will execute two times。Because we subtract one in each iteration。

 so we know like。Okay， so we can write the numbers in place so it takes 7 to one cycle。

 we don't know the number of stages so it be it should stay as this。

And we know how many dynamic instructions we will execute， it's also stated in the question。嗯。

Which I cannot right now see， but it should be。50。Okay， so here。Right。

 and so let's write it there and we know B is two because。For I1 equals。好。It's not。 Okay， sorry。

 So for this one， we know that P is 2， which means that this is。I written this。

And let's write it for r1 equals four as well。So， similarly。If you can write this。😔，And。

We can solve the system and see 2D is。12 and from that we get that D6。

And when we put this in place in any of these。Formulas that we know P is 10。So。

Do you have any questions？Yes。嗯。So it should be always given because then you wouldn't be able to put eye in place and you wouldn't know basically or we would say if it's like a。

嗯。I guess it's always given yeah， or otherwise you could deduct it if it ends without an outside like interrupt so in this question we say that we need an external interrupt。

 that's why it's given。And yeah。Okay。So。Right。And。The second part of the question。

 so in here we have a Mr。 branch predictor that we don't know how it operates。

 so this means that for some of the branch instructions we would get no stalls for some if we have mis predictiondictions we would still see stalls。

And in here we have this here for r1 equals four， we know that with this new design。

 the program executes in 77 cycles。Okay， to compare to this。

So here we know that it took this minute cycles8 to3。So， the。

Basically the difference between both cases is that in one of them we didn't mispredt one。

 we didn't get the stall， so we know that the difference between these two cases is six which is equal to one conditional branch instruction calls stall right。

 so we know that in this case。We could predict one of the conditional branches correctly。

So let me write it here。 we had in total four conditional branches for this input。

 so three of them are mispredictions。And one is correct。Okay。So in here。

 the question says gives like different predictor designs and we are evaluating if it's possible to see this outcome with these different predictors。

So the first one is static branch predictor， which we have always taken or always not taken。

 the answer for this one is yes because。In here， like you said， okay。Let's first write the。

Outcome of this， like we know that the first okay， from here when we give four for R1。

We know that the first first branch will be taken because this is correct and second one will be taken and the third one will be taken and the last one will not be taken。

So we know that with this and this we should be able to evaluate these predictors。

 so let me copy that here taken taken taken not taken and so in here the answer is yes and when we see。

If we predict always not taken， we will have one correct prediction， right。So yeah。

This one should give oops， this one should give the same outcome。And for B。

 we have last time branch predictor for again， the same outcomes。

You can see that if we predicted what was the outcome of the last branch。In any time here。

 we would be able to guess like two of them correctly at least regardless of what we predicted this time and you could also guess this one correct if you started with taken。

We wouldn't be able to get like one correct prediction and three mis predictions。

 so the answer for this is no。And for。Yeah， and for C。

We have backward taken forward not taken so for this one we still we again need to go back to the code so for this loop what we have as the address of this the target like the。

Destination of this is backwards。Considering this， if we predicted backward taken and forward not taken。

 we would have said for this loop， it should be always taken， right？

This would give us like for this taken， taken not taken， we would be correct for these。And。

We would mispredict the last one。So this would also give one correct prediction now three incorrect predictions。

 so this is also now。And for this one， as you can see。

 we would be able to get this outcome because again。For this。诶。Backward not taken is basically it。

 it would end up。Predictted not taken， not taken， not taken and not taken。

 and this would give the correct one which。Also is the outcome that we are looking for。

 So this is yes， okay。Do you have any questions？Okay。嗯。Yeah。嗯。Yeah。Thank。그。Okay。Okay。

So I guess we are done with the main part of the exam because is the this one is a bonus question。Oh。

 I guess we will have another question from the main part of the exam， okay？So what I observe in。

reIn the past years is that many students do not actually all these bonus questions。

Partial related with the， you know time not being enough for some students。

But I'd like to mention that you never know where the easy questions are。 So plastic bonus as well。

 So this is one example that we have quite an straightforward question。

So this is about data professionion and as you can see， we have， can I zoom in here？Oops。Yeah。

 we have this kind of access pattern here right so it first goes like a a plus1 a plus line。

 it goes like this So if you look at this straight in this access pattern。

New access address A and then so this is a cashline address。And then you immediately， after that。

 access the next very next cacheline， a plus one。And then you jump by eight cache lines and access to a plus9。

 and then you do again like stride of one and stride of8， so it goes like 1，8，1，8，1，8。

So we want we already know this access pattern。And we also know like what kind of professorfes are implemented in a system and we want to calculate some metrics based on those basically。

 and for those bad metrics you already have the formula， how you calculate them here as well。So。Okay。

 I don't remember the first question， let read。So you design a strip Profecure that observes the last three cash block requests。

Based on like what you have。Okay， so。Yeah， so it observes the。The last three aes。

And tries to find what is called constant Str。Between those aes right so if you don't have constants right basically you don't do the professionion。

 it's a way of building confidence basically。And as you can see。

 this threat keeps changing at every axis here。So basically。

 this kind of professor would not issue any professor requests。

So the question is asking about the coverage of prefech requests here。

 so it means like the coverage means here like total number of proof requests used by the program over total number of main memory requests without the prefeccher。

And as it will not issue any Q requests， the answer is zero here。

I'd like to show you the answer sheet as well， so as you can see here we don't just put zero percent。

 we also provide an explanation， so if you just put zero percent for this kind of question the exam is very likely that you will not get any point even if the answer is correct。

So please， as it's stated in the question， show your words， sorry here。Yeah， show your work。Please。

 show your work。Okay。So the second bullet point is。Here you design a。Yeah。

So you design an envelope professorure， so for every member request， basically when you access a。

 you pro the next and cache lines like a+1 a plus to a+ M。So the question is asking。

 what would be the coverage of professionion if you set this end to two？So here。

 if you remember the access pattern， it goes like a a plus1， a plus9， a plus 10， things like that。

 right？So， for。嗯。When you， when you access a。It will create a request for a+ one。

When you access a plus 1， sorry， a plus one and a plus 2， right， when you access a plus one。

 it will create。Profess request for a plus2 and a plus 3。So you will have this kind of profession。So。

So let's check like the percentage of or like how many of these pro requests are actually useful。

So once you have a， you already access a plus one in the future right。

 and perfection a plus one is something useful basically。So this is a successful profession right。

 and you also pre a plus two， but you never access it in the access pattern so you never use it。

So it's not good。And if you just simulate this a little bit。

 you will see that actually 50% of your profession requests。Become useful so。

The coverage really becomes starts。So let's move to。Other parts。So， here。

As you create professional requests， you will have more memory accesses and it will eat up from your available memory bandwidth。

So here we are questioning that。So again， if we have n set to2。

 what would be the bandwidth overhead to the system？And here also you're given a formula。

So you need to basically calculate the ratio of number of meme requests with the professors over number of me member requests without the pres。

So this is very clear here， so if you simulate again。嗯。Okay。

 so there is something that we need to highlight here。

 so if multiple proof requests are generated for one memory address。Only one request goes to the D。

 So you have a pro request for， let's say you access a， right。

 and then this creates a perfect request of a plus one。And then an A plus 2， right？So later in time。

You need to access a plus a plus one， right， but you don't create this member request because you already pro a plus one。

So you don't have to do this access， right。Or in other words， so you access a plus one。

Either we have professional or normal requests。This will result in like a plus2 and a plus3。

So you can see that you have two a plus twos， two a plus ones here， so for those。

 you will perform one memory access。So。If you simulate this like this。

You can see that for every two memory requests， we will actually end up having three memory requests because of the professor。

So that's why actually this overhead in terms of this metric。Itcomes three over two。Okay。Sure。嗯。明白。で。

这。That it was fine， so。You won't have to work perfect your。叫什么？不的你思说。Yes， so yes， you're right。Yeah。

 I actually wrote it here。 Miss， Yeah， there's a mistake here。 Thanks for highlighting that。

So value you access a。The professor will get a plus one and plus two。

 and when you need to access a plus one， you will have that in the cache。

And your next success will be going to a plus9。And then this will pur a plus 10 and 11。Yes， yes。

 so it's like one headphone mis。And then at the end， you will at end get like 50% here。Okay， yeah。

 thanks for a reminder， sorry correction。So， okay。So we want to have， okay。

Now we are in this question。So now we want to have 100 person coverage mean that。

By performing professors， we want to get all the data that we want to access in the future。So。Again。

 our access pattern is the same A A plus one。And then a plus9， and then a plus 10， it goes like this。

 right， So I want to have a professorture。That will successfully pur both this and this and this。对。

So， yeah。So when I access a， I want to pro a plus one and when a plus one is accessed。

I guess in this case， we also assume if it's access from cash， so it's basically a memory access。

I will get access to a plus perfech a plus9 as well。

 so to do that with this of this kind of prefecture。We need to set n to8。So that。

So that we can pre fetch a plus one within the prefes for a and a plus9 within the prefes for a plus one。

ok。Okay。Yes， so。嗯。So again， this is the bandwidth overhead calculation。

That we have for this new professorcture with like n of eight。So here again we need to simulate。

 I will not simulate actually it's all results here。So。嗯。

You can consider this like for a memory access how many professional operations I will have。

So when n is8。So with professors， you will have。One， memory access， let's say， the real access。

And eight croufetch operations， right？So。So this is like basically what changed with the professor。

And if you look at this。 So accessing a will perfect fetch all these a plus 1。

 a plus 2 up to a plus 8。And then once you have a plus one access。

This will create per for a plus2 to a plus9。And some of these will not be repeated because these are the same addresses。

So you can see that when you simulate for this particular access pattern。

 when you access two different locations， you will end up having nine accesses。

 so it's nine over two。So， yeah。And this is the end of this question。不是。嗯。嗯。啊。Yeah。是。嗯。是。그。嗯。Yeah。い。

跟住系咩啊。嗯。う好き？是。嗯。是。So this was the last question in the exam last year。

So the question is about cash reverse engineering。And。It is a pretty long question。

 but with the right technique， you can solve it easily。So the question goes like this。

 you are trying to reverse engineer the cash associivity of in a new release system。

 you already know that the cash has fee for replacement policy。

And eight blocks and a block size of four bytes so so we will start with an empty cache。

And then the application accesses five byte addressessses in the following order。

 and this is the order of accesses that we have。So。What do we do do with this。

 so we assume that you can access three more addresses after this this access。

And then observe the cache hit across these three axis。

So so this is the premise of the question and so the question the first question is which three addresses should you access in order to identify the set asciivity of the cash so the options are one way two way。

 four way or8 way。And we can have multiple solutions in this question。

 but we have asked for the lowest possible addresses that can enable the identification of set sociivity。

So啊。So the thing is we need to provide the answer in in detail。

 we need to give every step and then that will fetch。

The full points so now that we know we the these are the things that we know the fee for replacement policy eight blocks and block size of four bytes so with eight blocks we can have these four associ so the way we should solve this question is to basically look at how we can。

look at the state of the cache after these initial five axises and for that I will write the associivity so I will initially write one way。

And。Okay。So then I also have two way。是。嗯。And then four way。AndFinally， they way associate with。嗯。

So here the boxes represent each cache block and the cache block sizes four bytes。

So let's see what is the state of the cache and here I will just represent each block with the starting address which can be of the starting byte address so here you can store zero to three。

4 to 7，8，12，16。20，24，28， and then。In the in the first one。

 you could also store 32 and it goes like this。So here you can store 0。4，8。转。😔，And then 16。20 and so。

And here you will have four，0， and4。And then，8。16。24，32 like that。

 and the other byte addressessses can be stored in the second set。

And here you get you can store any all these addresses that you can access so let's look at the state of the cache after the first five axises so you have two which falls into the first block。

 so you have two here。Then nine， which is when the in this block three， which we starting at SS8。

 so you have。You can store it here and then 16。25。And then 33 is again。

 it can be only stored in the first block。So we need to replace that and so I'll strike it and。

Make it 33。So next， if we look at the two way。Associivity， we can re two here。And nine goes here。

Where the starting address is 8， then 16 goes here and 25。Because the。Standing address is 24。

And then 33 is the address which has to go to the first set。

And here we again replace the current block because of the replacement policy and we replace with the fiO replacement policy。

 so this will go and we'll have 33 here。And then in case of four wave， we will have。都。9。16。25。

And again，33 is basically going in the first set and well replace two with 33 because of the Fi for policy。

And in case of eightway， we will store all these addresses。Without any replacement。这身态。

So now this is the state of the cache and we'll have to access three more addresses。So here。

 the trick is to find three addresses， which can give you unique。

 which can find unique associivity or unique hit rates across these associivity。

 So you will have to find three addresses， which can give three hits in。嗯。

InIn one of the associate duty。One by three and another。2 by three。And0。So。

 so youll have to find the addresses which can provide you these can these hit rates and considering that you you need to have three hits in one of the。

In the one of the Associ dutiesities， the trick is to find basically three addresses which are already accessed in this initial five address addresses that you that the application access so that you will always have a hit rate。

So we'll start with。Let's say2，9 and 16 are basically the starting addresses of these blocks，0。

8 and 16。If you choose anything in the middle， let's say four or 12， you will still have a miss。

In all these。Associivity， so with0，8 and 16， let's see what is the state what what will be the hit rate in one way。

So we axis0 again， which means that 3233 has to be replaced。

 we will have0 and herell have I'll just mention the hit sign misses。So you have one miss。

Then it is is already there， so you will have a hit。And 16 is already there。

 so we will have another hit so you will have two by three。And in case of two way。嗯。

YouSo let's access zero again， so when you access zero you replace one of the blocks here。

 so we had 16 before， so that was the that was the earliest access that came so we'll replace that with zero。

And then， which means that。It or miss。So you'll have one miss because the address was not there。

 it is a hit because it's already there。And 16 is not there in any of the in the first set。

 so you will have to again replace 33 so that you can still access 16 so you will have。Another is。

 So here the hit rate is one by3。And then if we go to four way and if we are accessing 0，8 and 16。

So zero is currently not available the block。In the cache。

 so we'll replace 9 with zero because of FA。Then so。So you like one miss。Then 8，8 is also not there。

 so you replace。This one we did。And then 16 is also not there because we just replaced it and then we'll replace it with 16。

 so you will have two more misses so here you will have zero。And with 0，8 and 16， you， you can。

Get three hits because you already have these addresses or the the cache blocks。With these addresses。

 So you get three hits。So here we found a unique solution or found these three addresses which can identify the associivity clearly。

 but if you solve this question further and try to try to see other addresses。

 you will also find that you can get the same solution for0， 16 and 32。But I will let you solve this。

 but and I will not show it here， but if you because we are asking for the lowest possible utteres。

 we will still go with 08 times16。Any any questions？西瓜。Okay， so。Okay。嗯。哦，这是。对。啊。在这 some。So still。

百度实力。我。是吧。No， I think this kind of a question demands such an approach because we are asking for the three addresses and which associivity to identify the sector asciivity。

 you can of course use such a solution there， but I think if you kind of look at the sequence access sequence you can find out that find out what kind of associivity basically from the sequence itself in those kind of questions。

P。So now we。We'll look at the next part of the question， which is to which is。

A continuation of the first part。 and here we are asking for what is the associivity of the cash。

 if the cash hit rate observed over the three extra addresses accessed in the part part one where if it's zero。

 then we are saying so。If it's 0， then it's4 way。So。Then one by three is basically。Okay。

And one by three is two way。是。And。Two by three is one way solution。So， and one is the8 way。

So this is pretty straightforward you used the solution from the previous question and then previous sub questionion and get the answer for this。

Now， the third question is when you access the three addresses you determined in part one。

You observed 100% hit rate across these three axises。

Now your friend asks you to access four more addresses in the following order and you get these four other addresses。

Which of the above four addresses would result in a cash miss。

 So the the key part of this question is to is that we are given this100 percent hit rate。

Information and we only get 100% hit rate in8 way solution。So if I redraw the gateway。

 the state of the cash after the。Last。3 axises。So。啊。So this is the state after the last eight axises。

 but now we are given four more excesses and we need to find out what is the which one of these accesses results in a cacheshm。

And here you can see that there is 32 and there is already a block which is having the the address 33。

 the byte address 33， which means it will be a hit。

And then you have zero and because there is a block which is having two， you you get a hit。

8 is already there because of nine and you already get a hit。

28 is not there because this is this block stores 24 to 27。

So this one will be stored in 28 and this is。This is a Kashmmus。So the answer is 28。

So that's it yeah for the first part I think you need to also you need to look at other addresses。

 but the lowest address is the one which we which we solve here。

 but you may this may not be true for other questions。Thank you。对。啊。



![](img/e0165f14e47b78875a94120c278bb24f_2.png)

。嗯。啊学生。Can you hear us。哦。

![](img/e0165f14e47b78875a94120c278bb24f_4.png)

冇想。是。Yeah。是。

![](img/e0165f14e47b78875a94120c278bb24f_6.png)

![](img/e0165f14e47b78875a94120c278bb24f_7.png)

嗯。Hello everyone， can you hear me？Hello， A， can you please wait， We are trying to share the screen。

Hello。😊，Can you hear us Yes， I can hear you Yeah， can wait for a few minutes。

 we are trying to set up the screen sharing here okay。Okay。Yeah。Yeah。Okay。Okay。Please good。Okay。Y。

So that's done on your camera as well。Yeah， I think it's not very convenient for me now so okay。

 I'm sorry， so yeah， let's first take a look at the question so we are given a in order pipeline processor that has。

第一。😊，Five stages in the pipeline。And we have the instructional format that like this。

 where we have the destination in the first end the two opera。That follows。So the first question is。

What's the AOU latency for the addition and multiplication command？

So we can take a look at the pipeline diagram that shows that corresponds to each of the。

In instruction， we can see that for a multiplication instructions we have。

Three stages in the execution stage。And for all the additions。Either the ad immediate or add。

From to registers， they all take。One stage in the in the。AOU。

 so it's pretty straightforward that the addition take one cycle。

And multiplication takes three cycles。Okay， so for the second question does this process to implement data forwarding so the purpose of data forwarding is to。

Forward the。Results that are needed by following instructions before they are written back to the register files so we should look at the later half of the pipeline to see。

Whether there's some。呃。Data dependent instructions。

Has already resumed execution before the input data is。

Writ back and we so the first step to do is to find these instructions that have data dependencies。

 so we find that in instruction four and five。hos， sorry。In instructions four and five。

Register R5 is written to at instruction4， but it's also an input up in instruction5。

So and if we take a look at the Pyon diagram， we can see that in。

Instruction five already starts the execution stage while instruction4 is still in the right in the right back stage。

 so we can say that there's a。Data up。The professor implements。

Data forwarding and it's between right back and execution stage。Yeah， so the next question is。

 so we observe。In this pipeline diagram， the decode stage it takes。嗯。A variable number of cycles。

 sometimes one cycles， sometimes two cycles。So， one of the。

Possible explanation for this is because we have up to。

Two operas that are that comes from the register file。

 so it takes more cycles to read both operas from the register register file and we we can also verify this。

Hypotheses by taking at in by taking a look at instruction two。

 so this is an ad immediate instruction， so only one of its。呃。Oprint comes from a register file。

 so our six comes from the register file which will take some time in the Decode stage but five is an immediate value so it doesn't take time in the de stage and we see indeed it only takes one cycle for the decode stage also take a look at。

The fifth instructions that we just saw。That has the that that that has one of the。

Data forwarded from the right back stage of instruction4， and it also takes only one cycle。So oops。是。

So， we can。Oh， which sorry， actually like this shouldn't。

Impact the number of cycles in the vehicle state because yeah the result is forwarded from the right back stage and。

And anyways， but still like for the second add immediate instruction。

 we can observe this so we say that。对诶。The reason for the variable latency in the decocode stage is because of。

呃。Because of。嗯。呃。The need。To read。Up to two operas。Yeah。From the。Register file。呃。If one of the。Yeah。

Ont。There's an immediate。Or being forwarded。It takes less cycles， only one cycle。Okay。

So up until now is to any question， so feel free to interrupt and I will just continue to the。对。😔。

The rest of your questions。Yes， so here let's have this diagram here as well。So， following the。

The previous question it's asking， what is the minimum number of。

Read and write port for the register file that corresponds to this pipeline。呃。A diagramia。Um。So。

Because if。As we said in the previous question。The instruction needs two operas and none of those are being forwarded it will take two cycles。

 so this means that it will have。One read court at minimum。😮，Because。It takes。Two cycles。To read。

Through operas。From the register file。And for the right port。嗯。

It also has a minimum of one right port。Yeah。呃。This is because so if we take a look at。第。

Right back stages。We can see that。嗯。诶。Let's say here ins 12。And also cycle eight。These two cycles。

 we see both the。The right back stage and the Decode stage。

They are using the register file at the same time， so this means there's at least a dedicated write court that is different from the read court so that yeah this write back end register read in the decocode stage can happen at the same time。

Because。right back。And decode can happen in the same cycle。对。Okay， so。

The next question so can we reduce the execution time of this piece of code by adding more read or write port in the register file？

So。First we， we should be very clear that adding more guide ports shouldn't help performance because。

Yeah， we don't see。Because you order the processor。

 you don't write multiple values to the register file in the same cycle。But indeed。

 adding a read report will help the。Performance because as the previous two questions has shown。

 if our instruction needs two opera that both comes from the register file。

 they have to be serialized because there's only one report so first let's say adding a read report。

Can reduce。Execution time。This is because。We can read。Both。Opers。From the。Rf。

At the in the same cycle。Yeah。So now we need to calculate the speed。So， let's have。Just here。U。Yeah。

 as we as we said， by adding another read report， basically we reduce the。呃。

The two cycle decode stage to only one cycle。So what we can do here is just merge or D1 D2s into。

 let's see。D1， and let's。Write down this pipeline diagram。So D1， D2 will become just D。E1 e two， E 3。

Memory right back。😔，Fch decocode。😔，Y one。And we still have to wait for the memory。Right back。Fch。

Decode three stages of。Multipplication。Memory， right back。And for the fourth instruction， we have。

Yeah。呃。Fch。Decode。嗯。Wait for。呃。Wait for， wait。Which for E1。😔，Wait for memory right back。😔。

45th instruction， we need to hatch。😔，But。Because of the。Data dependency。嗯。This is only D1？And。For R7。

 for R5， this can be forwarded from the right back stage。So we can execute E1。Memory， right back。

And finally， they lost the instructions we have。呃。You can fetch。😔，诶。Ftch decode， wait for E1。

Memory right back， so yeah， this is a bit tiltuted。So， let's。Separate。😔，灯。Okay。

And check if they're aligned。Yes， so。With one more report， we finished execution at P Cy 13。

So the speed up is just the old。Number of cycles 16。

 so  over 16 over 13 is our speedup by adding one more report okay。So for the next question。It's。

Yeah。So it asks， is it possible to run the code faster by adding more data forwarding past？

To the original pipelineython。So let's get the original pipeline here as well。So because as we said。

 the purpose of data forwarding is to forward the the results from the。

ALU directly to the previous stage of the pipeline without having to wait for the memory and drive back stage。

 so here we are looking for the opportunities。That。Let's see one some。

Some data comes out of the AOU from the execution stage。

 we should try to forward it to the next dependent instruction as early as possible。

So we observed that。Yeah。The original forwarding happens at the。呃。Do you write back page？😮。

So it's forwards the。Result from the。Right backstage to the execution stage。But here。😮。

We can actually start forwarding by just from the memory stage。

Because our code doesn't involve any memory instructions。

 so the memory stage basically does nothing so we can basically just。

Move all of these parts one cycle ahead and this leaves that。An execution time of only 15 cycles。

 so the answer would be。So yeah。It's possible。😮，By。Add。Forwarding。

From memory stage to execution stage。And the speed up is。15 sorry is 16 over 15。Yeah。嗯。Yeah， so this。

Concludes this pipeline question。Is there any？Quest you have about these solutions。Wait， how soon。

 there is one question。Okay。Okay， hello， my question is。

The stall that we do on the second instruction right like we have to wait so that the memory stage is below the right back stage is that we have to do that because it's a in order pipeline is that the reason？

Okay， so you're referring to the original pipelineon diagram right， so yes， yes， yes。

so can you say again like which instruction are you looking at Yeah instruction two we are finished with the execute stage becauses an add instruction then we have to cycle yes yes it's because it's an in order pipeline so yeah you have to wait before the previous instruction has released the stage you need next yes okay thank you。

Yeah， no worries。Any more questions？

![](img/e0165f14e47b78875a94120c278bb24f_9.png)

Okay， then thanks a lot， H。

![](img/e0165f14e47b78875a94120c278bb24f_11.png)