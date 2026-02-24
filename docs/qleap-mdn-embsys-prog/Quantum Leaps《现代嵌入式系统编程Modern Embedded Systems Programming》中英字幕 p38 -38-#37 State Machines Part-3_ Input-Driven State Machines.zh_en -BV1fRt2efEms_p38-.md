# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p38 -38-#37 State Machines Part-3_ Input-Driven State Machines.zh_en -BV1fRt2efEms_p38-

![](img/5f77835565ce1f20a3a5d9beaf9072ca_0.png)

🎼。Hello and welcome to the Mo embeddedd systems programming course。 My name is Miro Sammock。

 and in this third lesson on state machines， you'll learn about the other types of state machines used in software design and how they compare to the event driven state machines that you've learned so far。

😊，To understand state machines in this broader way， you need to go to the beginning。

So let me pull up my usual historical timeline where you can see the important developments that influenced our embedded programming discipline。

As you can see， the interest in state machines started almost 70 years ago when in the 1950s。

 George Moore and Edward Milley from Bell Telephone Company published their seminal papers on formal methods of synthesizing digital circuits。

In those papers， they outlined the usefulness of state machines for designing such circuits。

So first off， perhaps the most important observation is that state machines originated in hardware design as software was really in its infancy at the time。

It turns out that this deeply influenced state machines so that even to this day。

 state machines used in software carry a lot of the baggage from their hardware origins。

 I will provide some examples of this， later in this lesson。But going back to million more。

 they were concerned with digital circuits that had internal memory or state of some kind。

To appreciate the challenge， first， let's consider digital circuits without internal state。

 Such circuits are called combinational， and examples include or gates end gates， X， or gate。

 inverters and combinations of such elements。For example。

 here you can see a combinational circuit that performs additional of two inputs A and B。

And it produces two outputs， A plus B， and they carry from the addition。

Both the inputs and the outputs are digital signals that can be either high or low。

 representing logic 0 or 1。Because digital circuits work with logic values。

 they are often described by truth tables that you learned in math at school。 For example。

 here is the truth table that fully describes the workings of the half utter circuit shown in the schematics。

As you can see， the outputs depend only and entirely on the inputs。

 and there is no need to remember any history of past inputs。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_2.png)

However， consider for example， a problem of detecting a rising edge of a digital input a。

 that is we want the output y to go high only when the input a changes from 0 to 1。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_4.png)

Such a problem cannot be solved with any purely combinational logic。

 because the circuit obviously needs to remember the previous state of the input a。

Here's an example of the circuit that would do the job。

The most important new component in the circuit is the memory element shown here as the D flipflop。

 which remembers just one bit of information。This is the state of the circuit。Also。

 there is now a periodic clock signal connected to the flip flop。

Which controls when the flipflop stores new information。

 This clock provides a global un event to the system and determines when the inputs and outputs are allowed to change。

Circuits driven by a clock are called synchronous， and both million more focused predominantly on synchronous circuits。

There are many reasons why， to this day， essentially， only synchronous circuits are in use。

 and I will mention some of them in a minute。But going back to the edge detection circuit。

 it also has two blocks of purely combinational logic。

 one for determining the output based on both the current input and the current state and another logic block to determine the next state。

The workings of the circuit can be again described by the truth table。

 but this time the table needs to list also the previous and next state of the system。

Ill leave it to you to pause the video and convince yourself that according to the truth table。

 the output Y is1 only when a was 0 before and is one now。

But the trust table is not the only useful representation。

An important insight of the original articles by George Moore and Edward Meley was to abstract the states of the system by naming them。

 and then by applying the automata theory to depict the truth table information as a state diagram。

The association between the state names and the output values of the flip flos is known as binary encoding。

 And here， the encoding is particularly simple。 State name S 0 is assigned to the flip fob value 0 and as 1 to the value 1。

With this encoding， you can draw the following diagram as proposed by Meli。

States are represented as circles labeled with their names。 So， for example。

 after we said the state of the flipfl is 0， which is represented as a circle labeled as 0。

The arrows coming out of the states correspond to the lines in the truth table and in the merely representation。

 they are labeled with the possible values of the inputs。

 as well as the outputs produced in each case。For example。

 the input 0 in S0 leads to S1 and produces the output 0。

Input1 in S 0 leads back to S 0 and produces the output 0。

Input 0 in S1 leads back to S1 and produces the output 0。And finally。

 input 1 in S1 leads to S 0 and produces the output 1。

 This is when the circuit detects the rising edge of the input A and drives the output Y to high。

This circuit is called the Mili state machine because there is a direct connection between the input and the combinational logic for the output。

However， for reasons that I'll explain in a minute。

 it is often better to separate the inputs from the outputs and allow only the current state to determine the outputs。

This leads to the more restricted circuit， called the more estate machine。

So here is an example of the circuit to perform the same function as the previous mealli circuit that is to detect a rising edge of the input A。

More state machines typically require more states than merely state machines to perform equivalent function。

 which you can see here by the presence of two D flip flops。On the other hand。

 there is no direct connection between the input A and the combinational logic for the output Y。

Only the current state that is the outputs of the flip flops influence the output y。

And here is the truth table for the moor circuit。 As you can see。

 the state encoding now requires2 Bs， whereas the 11 B combination is not used。As before。

 the truth table can be translated into a state diagram where each line of the table corresponds to a transition。

But the Moore state diagram is slightly different in that transitions are labeled only with inputs。

 Outputs are placed inside the states because outputs depend on the states only。

So let's quickly go over the truth table and see how it corresponds to the more state machine diagram。

After reset set the flip flo start in the 0，0 state， which is encoded as as 0。

 this state produces output 0。Input0 in a0 leads to S1， and S1 produces output 0。

Input1 in a0 leads back to a0 and as0 produces output 0。Input0 in S1 leads back to S1。

 and S1 produces output 0。Input1 in S1 leads back to S2， and S2 produces output 1。

 This is the detected rising edge。Input 0 in S 2 leads back to S1 and S1 produces output 0。

And finally， input 1 in S2 leads all the way back to S 0， and S 0 produces output 0。Okay。

 so I hope you now see how it works。 And given the state encoding。

 you should be able to go back and forth between the state diagram and the corresponding truth table。

Of course， what you' have seen so far was a very simple example with just 1 B input and 1 B output。

 but the approach can be generalized for multiple bits of input and multiple bits of output。 In fact。

 this is exactly what million more papers were all about。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_6.png)

![](img/5f77835565ce1f20a3a5d9beaf9072ca_7.png)

Here is a generic structure of such circuits with internal state。

 The central component of the circuit is the current state register comprised of multiple D flip flops。

 which are all driven by the common clock signal。Both the current state bits and all the input bits are fed with the combinational logic block。

 which decides about the next state。The next state is then fed back to the state register to become the current state on the next clock cycle。

The current state is also fed to another combinational logic block to generate the outputs。

Additionally， but only in the Mili machine， the inputs are also fed to that logic block for outputs。

The synchtron nature of the circuit is reflected by the following timing diagram。

 which shows the operation of the edge detection circuit discussed before。As you can see。

 synchronous means that all signals are allowed to change only when the clock is high and must remain stable when the clock is low。

 Of course， this ties everything to the clock and is quite restrictive。

Circuits without a clock are possible and are called asynchronous circuits。In fact。

 the original mini paper discusses such circuits as well。

But it also mentions the biggest problem of asynchron circuits， which are race conditions。

 A well known already in the 1950s。I've introduced software race conditions back in lesson 20。

But race conditions can happen in hardware as well。

 when the propagation delays through the electronic components can lead to different outputs。

 depending on their relative timing。The problem of race conditions in hardware turns out to be so intractable that to this day virtually all digital electronics。

 including all embedded CPUs， are synchronous。But even synchronous circuits are not completely immune to race conditions。

 For example， as you can see， the milling machine's output rises a clock cycle sooner because it responds directly to the input rather than waiting for the state to change。

But this faster reaction can occasionally lead to race conditions because the state of the circuit might change in the same clock cycle as the inputs so these two changes can raise each other。

For these reasons， more state machines are often preferred。

 even though they are a bit slower and a bit more complex than the meal machines。All right。

 so these are the original hardware state machines。

 But now the question is how all this relates to the state machines used in software。Well。

 if you search the web for software state machine， chances are that you'll come up with something like that。

Or like that。Or like that。These are apparently state machines。

 but they are very different from the event driven state machines that youve learned in this video course in lessons 35 and 36。

And I don't mean here the cosmetic change of state presentation as circles versus rounded corner rectangles。

No， I mean the real difference in what drives the state transitions because these are apparently not events。

 Instead， transitions are labeled with inputs， as well as expressions built out of those inputs。

 For example， you can see expressions containing logical or and as well as comparisons like equals greater than or just true or always。

So what's going on here and what are those inputs。Well。

 it all goes back straight to hardware estate machines where inputs were simply bits or groups of bits。

In software， groups of bits that can change are called variables。So， for example。

 one bit of input could be represented as a Boolean variable pilot's lever。

 which could take values up or down。Another input， such as millisecond counts。

 could be a 16 B variable that takes value 0 through 2 to 16th， et cetera。But at this point。

 I hope you notice something familiar。Yes， these Boolean expressions of inputs are simply guard conditions that you've learned in the last lesson 36。

 Indeed， in the more advanced tools， such as state flow by math works。

 the same company that makes matlab and siming。 The transitions are labeled explicitly with guard conditions。

 because you can see the characteristic square brackets。So the next even bigger question is。

 when do those state machines run and when do they wait？I mean， with e drivenvan state machines。

 this was very clear。 An evanrvan state machine runs only when there is a new event to process。 Also。

 when no events are available， an eventvan drivenvan state machine simply waits。

 meaning that it doesn't do anything。But the input driven state machines are different。

 They run un always， or unquote periodically， whereas typically you would know from the diagram how frequently that is。

Sometimes a state machine is shown in the context， like here in the simlink model from this wider context。

 you can guess that the state machine must be driven by some clock， which means periodic execution。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_9.png)

But other state machines of this type run always。 For example。

 state machines are frequently executed in the while1 super loop directly from the main function。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_11.png)

You also encountered such a state machine in this video course where in lesson 21。

 about fore gra background systems， I showed you the non blocking state machine version of the blinking implementationation。

State machines executed from the while1 superlo take all the available CPU cycles。

 regardless if there are events for them or not。Regarding the terminology of calling these type of state machines。

 it does not seem to be further established。 I already use the term input driven state machines。

But I have also seen other names like controller state machine。

 because the state machines of this type are commonly used in process control。

 like the one shown in the simullink model。And I've also seen periodic state machines。

Because they often execute periodically。However， this name would suggest some well defined periodicity of execution。

 whereas the simple state machines in the while1 superlo might be executing in a very irregular fashion。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_13.png)

For example， when all guard conditions in the current state evaluate to false。

 the state machine can finish in a matter of microseconds。

 But when some of the guards evaluate to true， the execution can take many in milliseconds。

 This means several orders of magnitude difference。

 and it's hard to talk about any well defined execution period。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_15.png)

Which leads to yet another term used for describing this type of state machines。

 which is paled state machines。This term captures the fact that such state machines constantly pull the inputs to discover the really interesting events that need to be handled。

In other words， state machines of this type combine the even discovery by paring the input with the state machine logic。

In that sense， you can view the inputs to the state machine as unquoteproto events。 That is。

 inputs are variables that need to be pulleded and combined in guard expressions to distill their real interesting events。

But speaking of the inputs， they are typically external to the state machine and originate either directly in the peripheral registers or in the interrupts。

For example， the button input in the state machine is read from a GIO register in the Arduino function digital read。

 Likewise， the variable time is read from the millisecond encounter returned by the function meis。

The millisecond encounter is updated in Arduino in the system clocktic interrupt。

The main point here is that the external inputs are variables that are shared between concurrent entities like peripherals and interrupts。

I really hope that by now in this video course， you have learned to be very circumspect of any such sharing because anything that changes asynchronously with respect to your code's execution can lead to race conditions。

 data corruption and other problems of this kind。For these reasons。

 input driven state machines could be compared to the asynchronous circuits mentioned before。

 while event driven state machines to the synchronous circuits。This is just an analogy。

 not a precise equivalentence。 so please don't take it too far。

 But the main reason for this comparison is the asynchronous nature of inputs driving the input driven state machines。

The external input can change at any time， including during the state machine processing。In contrast。

 events in the event veryin aid machine are queued and guaranteed not to change during the whole run to completion step。

For example， consider the input driven state machine from a popular article embedded state Ma implementation。

The state machine used as an example in this article controls the landing gear of an aircraft。

It is called directly from the while1 super loop and happens to be implemented as a set of functions held in an array。

 each function representing a state。I will discuss the various state machine implementations in the future lessons。

But for to day， let's just focus on the input， which， among others， include here。

 the gear lever variable。The intent of the guard condition in state gear down is to detect the rising edge of that input by testing the current value of gear lever。

 as well as the previous value stored in the local variable prev gear lever Now inside the function for the gear down state。

 if the gear lever variable changes asynchronously in an interrupt or is read directly from a GIO register。

 for example， it can be down when the guard condition is evaluated。

 but it can change to up when the value is stored in prev gear lever。If this happens。

 the rising edge of this input will be missed， and the guard condition will never evaluate to true。

 This aircraft will never take off。Please note that it doesn't matter if the gear level input is accessed directly or perhaps through some functions similar to digital read from Arduino。

The solution to such problems is， of course， buffering the inputs。 By this。

 I mean copying the values of the external inputs into local variables。

 which are then guaranteed not to change over the run to completion step of the state machine。

To show you how this can work in practice and to finally get to some coding for this lesson。

 let's go all the way back to lesson 21 about the foreground background systems。

To base today's code on that lesson， copy lesson 21 directory to lesson 37。

Get inside the new lesson 37 directory and double click on the project lesson to open it with Kyle Microvision ID。

To remind you quickly what happened back then at the end of lesson 21。

 you've seen a non blocking implementation of the blinklinky application directly inside the wild1 superlo。

 This was exactly an input driven state machine that you officially learned today day。

This input driven state machine is coded with the usual switch statement based on the current state。

 where in every case for each state， you can see the characteristic if statements。

 These are the guard conditions typical for an input driven state machine。

Here is the reverse engineered state diagram of the state machine。As you can see。

 the actions are associated only with transitions。 So this is a meal type state machine。Now。

 there is only one input to the state machine， which is provided by the BSP tick counter function。

This function reads the Ltic counter variable that is constantly updated in the cystic handler interrupt。

So， indeed， the thick counter input changes asynchronously to the execution of the background loop。

Also in this state machine code， you can see that the T counter input is accessed twice in each of the states。

 so it could be different at each access point because it changes asynchronously。

This happens to be tolerable in this small toy example。

 but still buffering would make it more robust for any future modifications。

Please also note that the asynchronous nature of the input does not change。

 regardless if it is accessed directly or by means of a function call like BSP take counter。

All right。 So the first order of business to will be to buffer the tick counter input in the local variable now so that the input will be read only once in each rental completion step through the state machine。

Downstream from setting the local variable， you can now replace all direct references to BSPtic counter with that local variable now。

Let's quickly check how this works by building the code。And loading it directly to the board。And。

The green LED still brings happily。So now let's extend this example by adding the blinky button functionality similar to the previous lesson 34 and 35。

This will give you an opportunity to add a second input， the SW1 button。

The job for today will be to react to the SW1 button。

 which should turn the blue LED on when depressed and turn the blue LED off when released。

You start coding this new feature by adding the BSP function to access the SW1 button。

The implementation of this function will read directly the GPIL register and return one if it is non0 and0 if it is。

You must also not forget to define the SW1 button bit and to configure the SW1 switch as GPIO input with digital function enabled and with the pull up register enabled。

Now， inside the actual state machine， you add automatic variable button for buffering the button input to the state machine。

 You initialize it by calling the new B SP S W1 function。Also。

 to detect the changes in the button input， you will need to remember the previous value of the button in the static variable prev button。

You initialize this prep input to the inactive state of the SW1 button， which is1。Now。

 you add the guard condition to detect the following edge where a previous button was not 0 and current button input is 0。

As an action， you turn blue LED on and you save the current button to pref button。

 Since this is really an internal transition， you don't change the state variable。Otherwise。

 you add the guard condition to detect the rising edge where previous button was 0 and the current button input is not 0。

As in action， you turn the blue LED off and you save the current button to pressf button。 again。

 since this is really an internal transition， you don't change the state variable。Now。

 you copy and paste the same reactions to the button into the other on state case。

The input driven By button state mission is now ready。

 so you can clean up some unused code and build the project。 Let's check how this works。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_17.png)

After loading the code to the board， you can see that the green LED still blinks as before and that pressing the SW1 button lights up the blue LED。

But to look more precisely， I'll use a logic analyze。In this view。

 the top white trace labeled as W1 shows the pattern input。 The three traces below show the red。

 green and blue LEDs respectively。The trigger is set to the following edge of SW1。

 so when I start the logic analyzer， only the greenery is togg as expected。Now。

 when I press and release the SW1 button， the tray triggers and stops。As you can see。

 the pressing SW1 turns the blue LED on and releasing the SW1 button turns the blue LED off。

 this is all exactly as expected。But if you look more closely， you can see that in this case。

 the Sw1 traces bounced once before setting into the depressed state。 This is， of course。

 the bouncing of the electrical contacts that you already encounter back in lesson 27。

In this particular case， your state machine keeps up with a noisy signal and manages to turn the blue LED on and off。

But sometimes the state machine necessary a bouncer to， as in this case of releasing the button。

This might or might not be acceptable in your particular application。

 but the problem is that you have no control。This is all because the sampling of the inputs is coupled with the execution speed of your input driven state machine。

 which can vary widely depending on what the state machine happens to be doing at the moment。

So in applications where you need to keep up with your inputs that might change faster than your worst case state machine sampling rate。

 you might need to decouple the polling of the inputs from the state machine execution。

Such decoupling gives you an opportunity to preproces your raw inputs。 For example。

 you might perform some digital filtering of the inputs like de bouncing of your raw SW1 button input。

Then you need to add some layers of buffering or queuing of the inputs so that they are not lost。

But this leads more and more towards eing state machines。Because really。

 every input driven state machine can be quite easily converted into an event driven state machine。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_19.png)

To see how， just go back to the code and look at the buffer inputs。

If you simply wrap them into a structure。And name an instance of its Evity。

 you create an event where the inputs become the event parameters。

This grouping of inputs has an additional benefit of packaging together inputs that represent a consistent snapshot。

An interesting question now is about the signal of such an event。

This depends on when and how your state machine gets to run。 If it simply runs as often as possible。

 like here in the while1 super loop， you might call this event a generic sample。

This is a low quality event with quite an erratic repetition rate。

But to finish the conversion of your input driven state machine to event driven。

 you can add the pointer E to the event instance EvT。

So that all the inputs are now accessed via the event pointer E as event parameters。

I hope you can see how this code starts to resemble the dispatch function of an event driven state machine from the previous lessons。

So let's try to build this version and check how this works。Again， the green LED blinks as before。

And the SW1 button turns the blue LED on and off。

![](img/5f77835565ce1f20a3a5d9beaf9072ca_21.png)

But in a logic analyzer， you can still catch instances of the bouncing button input and unreliable response of the state machine。

Of course， this is to be expected because the single buffering of inputs now inside an event does not change the execution rate of the state machine。

So here comes perhaps the most important observation for this lesson。

 The reliability and robustness of a state machine depends not just on its type input driven versus event driven。

 but also on the environment in which the state machine runs。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_23.png)

That's exactly why I have introduced state machines in the context of event driven active objects with queuing of events back in lesson 35。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_25.png)

![](img/5f77835565ce1f20a3a5d9beaf9072ca_26.png)

But state machine applications form the whole spectrum from input driven state machines executing in their while1 super loop without any buffering of inputs through increasingly event driven state machines with generic events and guard conditions to fully event driven state machines running inside active objects with full event queuing。

All of this does not mean that input driven state machines are all bad to the contrary。

 input driven state machines bring a whole number of advantages in situations where external discovery and queuing of events is difficult or inracical。

 For example， computer games execute code periodically， in response to the generic frame event。

 which comes 30 or 60 times per second。In a computer game。

 the discovery of interesting events is very much part of the game itself。

 and it is impractical to perform at this externally to the programme。For example。

 an interesting event might be proximity of some enemy。

 this is ideal application for input driven or periodic state machines。

Another application area is in robotics， where again。

 the robot software runs periodically at a certain frame rate。

 and the discovery of the interesting inputs from the sensors to the robot very much depends on what the robot is trying to do and what is happening around it。

Finally， input driven state machines are very useful to discover the external events for the event driven state machines。

For example， the switch de bouncing mentioned earlier is demonstrated in the previous lesson 35 and 36。

It turns out that the debouncing algorithm is a very special input driven more type state machine running periodically from the systemtic interrupt hook。

 This is actually 32 state machines running simultaneously capable of debouncing 32 switches at the same time。

😊，But I have to leave the discussion of this implementation to the next lesson。

 where I will focus exactly on the various sleep machine implementations。

This concludes this lesson about input driven state machines。I apologize for going a bit over time。

 but it's really hard to squeeze almost 60 years of state machine history in less than 30 minutes。

If you like this channel， please give this video a like and subscribe to stay tuned。

 you can also visit statemachine。com/vio course for the class notes and project file downloads。



![](img/5f77835565ce1f20a3a5d9beaf9072ca_28.png)