# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P7：-07-Lecture 09 - Extended and Timed Automata.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Okay。All right， ready go。So now today we are going to start talking about models of discrete behavior and in particular we will deal with a mathematical model of behavior which is finite state machines that are very much used in all kinds of different applications。

 so for example， the screen your cell phone is essentially govern controlled by finite state machine。

 your vending machines when you put the coin into a vending machine and the code comes out is a finite state machine。

So let's see how this works and what。

![](img/0131f77353ad1202ef031a522dd2d483_1.png)

These objects are。 So before doing that， I recall， in general the definition of what an actor。



![](img/0131f77353ad1202ef031a522dd2d483_3.png)

呃嗯。I。Now， an actor is a mathematical object。And we say first of all。

 that the system is a function that accepts an input signal and yields an output signal。

 so very basic， very simple， so signals in signal。So the domain range of a system function are sets of signals right which themselves cells are function so this one in mathematical terms is a functional view of the behavior of a system now in general we are used to think about a system like you give an input and then you have a reaction you see an output now in the actor model you see the entire set of sequence of inputs and the output is the entire set of of signals of value of a signal okay so from a function of time into another function of time that's what the system does now which is not the point to point input output the relationship is function to function。

Now， why do we do this， Well， it's more convenient to deal with this model。

 especially when it comes to composition。And we'll see that not this time， but the next time。Now。

 on these models， functional models， you may have parameters right that describe a family of possible relationship between input signals and output signals。

😊，So for example you can have an amplifier according to the level of amplification you get a different output right so that is a parameter there is a position of a node so very basic stuff all right so the mathematical notation you say that s which is a system。

 the actor model of a system maps x into y where x is a function and y is a function so we go from a space of functions into a space of function all right。

😊，Now， discrete systems， What are discrete systems。 Well。

 discrete systems deal with discrete signals。Now what is a discrete signal。

 the kind of intuitive notion is the fact that you don't have a continuum of values。

 but you jump right from one value to the next and in general our mind is used to think about a discrete model where there is a finite number of levels of the signal but doesn't have to be there to be discrete。

 the only thing。Cannot occur， but you have an infinite set of values between any two points。

Fite point。 so that's the only thing that we have to worry about。

 So a discrete model then is something that maps a discrete signal into a discrete signal。

Now this one is an example that we are going to use throughout the class that is a garage counter。

 so what does a garage counter do is that you have a finite number of spaces in a garage。

 you know it sometimes for example like airports， you have numbers or like say 22 which means there are 22 spaces in this part when you see a red science I don't even try to come in。

 there is no space。And this is what it does so is this model that you see here so now what do we have to do in order to give an idea of how much space there is if I can get in or not now of course where two counters right so one counter is how many cars come in right and the other counter is how many cars go up。

And in fact， you see there are a arrival detector， but as an output。

 the signal arrival and a departure detector that has a signal。

 departure information now what do we need to know what kind of signal is arrival。

 do we need to have a real number associated to it？😊，No。We just need to know if the car is coming in。

And the same reasoning， the departures that we need if a car is depart。

So that is only the only information that carries is that I am there as a signal or I'm not there。

 which means a car is coming， nothing is coming okay so let's call a pure signal it's only two notion is there is not there this are called pure signal Now by the way you could encode a pure signal with Boolean algebra so you can say nothing0 is there1 but is not exactly where semantically is just we think what matters is there。

😊，This signal exists or doesn't exist。So and in fact there is a pure signal and the counter up is a mapping from the real res which is。

Timeイ。And the space that consists of two。V use。Absent present，Now there is， of course。

 the down function is exactly the same。And the counter is something with sums。

 whatever signals come in。 Now， this is an algebraic sum in the sense that。Of course。

 if I have a certain value。Which means how many spaces I've got there if they signal。嗯。

Laving comes in when I have to increment by one。 and if a signal comes in and say on coming。

 it has to decrease by one。 Now this one is we are interested in finding out how many spaces are left。

 Of course， you can do the opposite by saying how many spaces are available right So it' I mean available are taken。

 So its you can go either way。Okay， so the counter is a function， in fact。

 it takes a time into absent and present in all possible combination and is outputting。Absent。

 so no signal， nothing， which means there is no space， union n， so a set of natural numbers。

 set of natural numbers is 1，2，3，4，5，6，7，8 so on， and so that tells me how many spaces in have been taken garage。

😊。

![](img/0131f77353ad1202ef031a522dd2d483_5.png)

All right。So this is a mathematical model， what happens now what we want to say is now the concept of reaction reaction is another intuitive concept right so you get something in and you react to it right。

And in fact， most of the embedded system of interest are reactive systems。So they sit in environment。

 if they see something that the environment produces， then they react to it so for example。

 a reactive system is your bra system in your car right so it sits idle when you press a breaking pedal and it reacts to the fact that you have press the pedal。

 the breaking pedal。So when a system reacts。It does two things。 It changes its state。

 and it produces some output。Okay， so in the case of the example of the car， if you press the。

Breaking pedal， when there is a auator that takes that pressure and translate into pressure on the disc of your wheels。

 Okay so that's an up is the command that is given to the actuaate。嗯。So in this particular case。

 the possible outputs are the display of how many spaces are left or how many spaces are taken either way。

Now they。When we say changes is internal state right so we have this notion is always very intuitive。

 the notion of state so Im in a particular state so right now I'm walking。

 I am in the state of working， I stop I change my state from walking to standing so that is describing what the system where the system is。

 there is no output the state， the concept of state doesn't have associated enough is a separate thing is a separate thing so in a mathematical model like this you have to give to information where I am in terms of the mode in which my behavior evolves and what is my output。

Okay。So that's the notion of internal state。 and we'll see later mathematically what the state is in more precise terms。



![](img/0131f77353ad1202ef031a522dd2d483_7.png)

Now of course inputted outputs are always defined at a reaction。

 so when something happens when you have a set of outputs。

 so we said before but the inputs are in a state take value in a particular mathematical domain。

 so in this particular case is the set of functions up and down into absent and present and so in old possible combination which are feasible。

😊，And the outputs are also into a set， which is the mapping of the signal which is count into absent union natural numbers。

So this is what we already said， but this is specified separately。

 so a practical parking garage is a finite number of Mmo spaces。

 so we can assume that a coding of the state of that particular system which is the garage。



![](img/0131f77353ad1202ef031a522dd2d483_9.png)

Is the number from 0 to n。 So that represent our full I M as a garage， right。

 So it is a intuitive notion that that is state of the garage。So date 0 of 1，2， to n。



![](img/0131f77353ad1202ef031a522dd2d483_11.png)

Okayright， now how do I。Can I capture this thing into yes。食的见。Ever， is it always the case that？

We define the state to be equal to the output space so in this case example0 to m is basically the possible values of the output is a choice of encoding。

 but is's not always possible， meaning that the state is a different concept than the output so for example。

 assume that the output is a real number so for example。

 the speed of the car but the state is I participate I don't participate that is a discrete right so but the output is continuous so if I associate the state of the output then I have any finished that's not so good so we are really separate things right so sometimes people there are cases in which it's convenient to represent the state as an output now is there only a way of describing a state。

No， you have choices but the most important thing is that if you remember from ordinary differential equation and the like and linear system theory。

 a state is essentially a summary of whatever has happened to a system before so an interesting thing is that in a linear system。

 what you can say or also whatever signal that is decribable by a first order differential equation that to find out what happens to your system in the future。

 the only thing you need to know is where you are now plus link。😊。

So you don't care about what happened two years ago， because all of that is into that state。

 right That state is a summary of all the information I got。Okay， so in this particular case。

I can encode this information about the mathematical model that we were saying before into this notation。

 so the notation is made of nodes and every node is associated to a state。

And then as and the as are associated to the transitions。 So when I go from one state to the next。

 I say from this state， I can go here。So for example， again， in my motion， I can go forward。Okay。

 so there is the state。 Alberto is moving forward。 The next state is Alberto standing and the next state okay。

 Alberto goes backward， dangerous right Okay， so that are the three potential errors right So if I'm going forward its difficult that I go immediately back you can imagine that I am forward stopping back right So the transition is that。

😊，If I were really an acrobatic could do this very fast， so I don't need to go through the standing。

 so there would be an arc that goes from the state walking forward to the state walking backward。

 so that arc is representing what happens right to my state。Now。

What will be the label that is associated to this？Moving from one state to the next。

What is the reason why Im changing one state of an x is because there is a yes。

 there is an action right so I'm reacting so there is an input so the input is the trigger of this change of state and in fact these labels these arcs carry a label that say under what condition I go from here to there。

Now， it's also convenient to。Associated to this arc， also a value of the apple。Okay， so in general。

 for finite state machines， you have two fields associated to the a to a transition。

 One field is a condition under which you move and the slash。What the value of the output is。

Well see later on that there are machines in which you to find out what is the value of the output you have to sit on the arc。

 and there are machines in which you can associate an output always with the state。

but there are two different kind of machines and well see later what is very difference between the two machine。

 one is called the moeller machine， the other one is called a mill machine。 So anyways。

 so what is the condition in which in this coding Im moving from state0 to1。

Is remember that the encoding of the state is the number of space that have been occupied。

So if we're going from 0 to 1， of course， there must be a car that comes in。😊，Right。Now。

 is that the only thing that I need to worry about now， this one I could indeed make a state。

Diagram like this in which I only look at the presence or absence of up or down。

 right In this particular case， you see that the guards of。

Conditions that I put on the arc is actually a logical expression in which says up up。

 So the car is coming and not down。But does that mean that a car is coming in and no car is coming out？

那。In this particular case， we have to have a notion of simultaneity So if the car simultaneous come in and comes out。

 then the state doesn't change， stays the same。There has been in action。

 but the system is not reacted to it， it stayed into the previous state because plus 1 minus1。

 same right？😊，Okay， so that is the reason why you have a condition。 Now。

 what is the slash one is the outputs because there is a display that tells me how many spaces have been occupied。

 Now， this particular case， you say， well， gee， you know， one is state1。 So it's associated one to。

Special kit。Okay。Now嗯。So this is also important to figure out that there may be transitions。

외 donウ don tell youば。And the transition that I don't tell you about in this diagram is when up and down at present at the same time。

 we said already that when。When input and output are present at the same time， nothing changes。

 So how would you code that information？What would you put in in that diagram to。

 to give that information， It is up and down are present at the same time。Very nice。 Very good。

 So it's called a self look， right， so you don't move， right， So big information。

 But if you don't say it， it means that the final state machine is incomplete。😊。

Meaning that I don't give you Veizations for all possible combination of a inputs。

But in this particular case， it's incomplete， but is obvious how to make it complete。

 which means all possible combination of input and outputs。 I have always a transition。

 that tells me what happens。 right It just， I chose not to put it down because it's trivial。

There are some machines that are incomplete and the notion of incompleteness could say I don't care。

 know these things that I don't want to know about because they are never going to happen so we are not there。

Which is very interesting because actually， when I say this particular condition。

 I don't care what happens is a freedom。😊，Since you don't care what happens。

 I can make it do whatever I want。And so it's a degree of freedom。

 which I can use to optimize my design。Alright， so this one is obvious， right。

 If the counter up is is incrementing your one to up to n。And then whereas you are in M。

 there is no space available or your rich full capacity。

 and so whatever it doesn't make sense to say that an app is coming because there is no space so actually you would have a bar that is preventing the new car to come in right so it stays there until someone leaves。

And when someone leaves， you go to state n -1， okay。It's very simple。

 I don't think that there is any doubt about this Now。

 The interesting thing is that the the in the really interesting thing is that condition that tells you what happens what when。



![](img/0131f77353ad1202ef031a522dd2d483_13.png)

Certain。Environment variable change。 So some inputs change。

And they are called guards because in some sense we are sitting there like this if they prevent your system to move unless that condition is vary。

 thats the reason why they are called guards right。😊，And guards are logic formula now， of course。

 with the most trivialial logic formula is。😊，The simple value of the variable。

 right that's as simple as possible gar。But there could be any possible ch logic expression。

Of the input variables， okay。In this particular case is an end and a negation。

Okay so this the guard is specified using the short end up and not down so we already talk about that now there is another important point which is the notion of initial state now in this particular case I put zero over there and I assume that my system starts with no CApar。

So that is my initial information。 Now， if I don't give you the initial information。

 can you say what happens to the system？Big question mark， can I or can I or I'm stuck。

Is it essential to give an initial condition。Yes it is absolutely essential because remember that the state is information what happened in the past so if I don't tell you what happened in the past where the heck do I know where I am so you must always give initial condition now mathematically if you have x dota equal to f of x you cannot solve a differential equation unless you have initial condition same story it's exactly the same thing。

 so it's nice that if you look at mathematics and if you look at physics in this particular case the garage open scope。

😊，They carry the same information right so mathematics reflects what happens in reality and there is a one to one correspondence between a mathematical concept and what you intuitively need to do in order to be capable of telling what the garage is doing so initial condition is always very important。

Now嗯。I don't know how many of you has done a class on computer architecture or computers。

 but there is an interesting point。Of course all of you have got a blue screen on your wonderful Microsoft system now less frequently。

 and it's not as frequent as many years ago， but you get the blue screen and then invent boom black right？

😊，And to to to to to to rebooting。 now what does that do is bringing you to a known state。

Which is very good state， so switchever off start from0？What do we do when the TV set doesn't work？

I'mplan。What do we do We set Ven initial state。 Okay， so that's it。

 So initial initial state is important。 You cannot do anything without the initial state。

The output we already said is a way of labeling， I mean。

 we can say what the output is by labeling the transition。



![](img/0131f77353ad1202ef031a522dd2d483_15.png)

And the mathematical model， we can do all the set the， yes。😊，Yeah。Already in。Well。

 it depends because supposed you are in a state， right， and then the output changes， right。

What does that mean？Something else has happened right and otherwise I'm an onterministic so which means that I have to introduce another state。

 so my encoding of the state is incorrect。Or you can say， well， in this particular state。

 I can have a sequence of outputs， but then I would label that with a sequence。0，1， two， three。

 four whatever。I arrive at that safe， yes。Go back to。well no， because they one。

 the output1 is telling me that one space is taken in this particular case unless it goes down and still taken。

But this is an important point。Because it's the semantic that you associate with a signal now。

 for example。When you have a sensor D to a converter， right？You have different models。

 right a D2A converter， what happens but you have a digital thing and you convert it into an analog。

And so what happens is that you， for example， is some signala and then you put it in the real space。

Now， then since it's discrete， you wait sometimes when you have another point， right？Now。

 how do you go from here to here， right？Electrically， so what happens to a electric circuit。Any idea。

There are two ways of doing it， of course。And one is called sample and hold。

And the other one is that simply simple。Simple and hold。

 what does it mean that the value is maintained？which is like this so the output is maintained state at that level。

 then a new thing happens and then I go up。 So it's just like a staircase right。Other times is that。

 okay， this the value when chunkng I go down to 0 and it's another value boom go down to 0。

 It is not simple and hold。 And there are two different circuits that do the same thing。

 So there are both A to D converters。 No， D to a converters， but they operate in a different way。

 So in general， most use model is simple and hold。 So you keep the value。There， right。

In this particular case now this is a semantic of a problem， right so we know that one is the state。

 and I mean， in this particular case， the output is the state right。So。Is the semantic or？

But you could have， for example， well， assume that there is now， this is also a stay constant。 Okay。

 supposeupp that you want to know how many。Okay， if you can cross the street， right？Now。

 then the car goes by， the counter goes up， so I can cross the street， but immediately after that。

 I go down to0， I can cross the street。 So this way output in this particular case is。

It doesn't hold right so it's not that once it's there。

 I cannot cross cross the road forever So this but is a different semantics。

 So according to what you encode in the model， you have a different situation。Okay。

 so now then the mathematical notion is that you have a set of states and this set to be a finite state machine has to be finite。

 finite number of states。There is a space of inputs in this particular case。

 since we use the actor models of systems， these are functions。The input is input function。Now。

 the output same thing are output functions。 And then there is a。Infam。

Function here is called update。 The update is what makes me do a step in the finite state system and what produces the output。

 so let's update。 So I'm updating the behavior of the system。Now。

 the update is also called the transition function also sometimes improperly because the transition function is simply telling me if I'm in this state and this condition occur。

 what is my next state？So that's me。Next state function or the transition function。 Okay。

 and then there is the output function that tells me， given this input and given this state。You know。

 given this state and giving us this input， this may。Okay， so which。

In principle and should always be。 So is a different function right than the next state function。

Sometimes it can be merged， as we say before， for example。

 the case in which I can encode the states the output then is the same it doesn't make any damn difference。

 but in general it is not the case so from states cross inputs you get you go to states cross outputs。



![](img/0131f77353ad1202ef031a522dd2d483_17.png)

Now this is finite state machine notations， so you have states and you have guard action that are associated。

 notice that the output sometimes are called actions。

 so its what the system does when it takes the transition。搜一个。

Guards that tell you when you can take the transition an action that corresponds to that transition。

Now there are sometimes mathematical I mean graphical notation to tell you what is the state0。

 the initial state and in general is a double line right so if you have a circle you have double circle if you have an novelval you have a double over that tells you what the initial state is because now we say state1 state 0 this and so it's easy to say oh okay this is the initial state but very often when you do designs you give the states not a number。

 but you give it a semantic notation so I I'm standing andm moving this kind of thing so the states are not labeled state 0。

1，2，3，4 also because if you want to document what the heck finite state machine does its better to be descriptive so every state should tell you what the meaning of that state is and so in that particular case unless you specifically indicate what is。

Initial state， then there is no way that you can infer it by looking at the label of state。



![](img/0131f77353ad1202ef031a522dd2d483_19.png)

Now these are examples of guards on pure signals， pure signal， meaning again。

 we are working in the Boolean space because there are only two values in this。Space。

True means that transition is always enabled。 So you have one over where means okay。

 I always take that transition。 There is no constraint upon the changing of the。 Now。

 P1 says that transition is enabled if the P1 is present。 So the pure signal is there。

So not P1 is that I take the transition of P1 is not present。

P1 and P2 means that transition is enabled if both P1 and P2 are present at the same time。

P1 or P2 means that I take the transition when either p1 or P2 is taken。

Now p1 and not p2 means of course， if p1 is present and p2 is absent when I take the transition。

So that we already discussed that before， but just to summarize what we say。



![](img/0131f77353ad1202ef031a522dd2d483_21.png)

Now。Sometimes I told you there are inputs and outputs that are not pure signals。

 They are numerical values。 they can take the state I always to be finite。

 now otherwise you don't have a finite state machine so but the input and outputs can belong to the so I can say p3 so transition is enable if p3 is present。

 p3 equal to1 means I take the transition if p3 is present。

 but its also equal to1 so I give an information there。

 now the important thing is p3 larger than 5 means that I'm going to take that transition only if the signal p3 is present and is larger than 5。

So I can associate inequality andequities on the guards。Of the finite state machine。



![](img/0131f77353ad1202ef031a522dd2d483_23.png)

Now this one is a thermostat， is's an example where the information about America value is important。

 Now this one is a finite day machine that you find when you go in your hotel and you know sometimes I go crazy because they are not so well adjusted so what happens that you said okay I would like to have 70 degrees in my room and what happens is that you go 71 and a boom cold air but 6 I boom hot air and then you have a heart attack。

😊，You keep on getting cold air in a hot air in a very short sequences right that's a controller action that is not so very good anyway。

 So this is exactly the same。 So what you get is that you stay in the cooling stage as long as the temperature is larger than 18 degrees so I keep on blowing cold air until I reach 18 then if the temperature is less or equal than 18 so I reach the thresholder of it in centigrade when I go into heat so I。

Heat my room Now， as long as the temperature is less than 22 degrees， then I blow hot air。

 Now notice that is 18 and 22。 Why is that to prevent what I say before now。

 if you go to some mos or mos or dingy places。 then this is not well set。

 So you have the two boundaries are too close and then you get this phenomenon or beam boom。

 beam boom， beam boom all the time now 1822 is enough to have some respite especially during the night。

 but the thing is not blowing so that is temperature less than 22， you stay in heat and of course。

 if the temperature is larger or equivalent。 22， when you go into the cooling mode and you stay there until the temperature is larger than 18 degrees okay。

Now it's interesting because this particular finite state machine。As a self loop that keeps on going。

 right so it keeps on staying in a particular state for a while until that numerical condition is verified。



![](img/0131f77353ad1202ef031a522dd2d483_25.png)

Okay。Now with a reaction occur， so suppose that all inputs are discrete and reaction occurs when any input is present。

 then the transition that you see there will be taken whenever a current state is s1 n x is present。

Now， what this is is what we call an event triggered model。

Which means that I'm changing state when something happens and as soon as it happens， I change state。

That's the reason why it's called event trigger。 So might transaction take place when that event is occurring。

Right。Now this is the best， right in terms of application is a nice thing，Now嗯。

There may be a situation， and my God， it did happen， so this is a history， a real story。

That there was a controller of air conditioning in a car。

 right And so you know that the the air conditioning car you have the up and down， right。

 So you can set refresh on， you know， increase by one degree or decrease by one degree。

And so this controller is very simple， it was implemented in an alpha Oomeoca where that was like 15。

 20 years ago， so no problem now。But they had one thing the designers forgot。

To specify what would happen when they up and down。

Ar would be pushed at the same time because nobody was who was so crazy to do that。

 So they didn't consider it there are children in a car and they love to push all buttons in any sequence。

😊，And so guess what when the system went bananas， you had to reboot the car。

 so you had to restart the car， not a good idea。😊，And so that is the reason why it is important to think that event trigger may be good。

 maybe not why， because when event trigger you have two events that occur at the same time and you have two reactions that are enabled at the same time。

 so this is I don't know what to do and it shuts off so not good。😊。

So event trigger is good in general because its the fastest reaction to what happens outside。

 but you got these horrible situations that sometimes create havoc so instead of event trigger there is another mechanism it is called time triggering。

Now， anyone volunteers how you could specify time trigger。Behavior。

 notice that event means something happens。 I react immediately time。Time is involved， right。

What happens is that the transition。Mistan， some input has changed。And。

Time is the richer certain value， and so that is time。I can only make transition at specified times。

So if we steal in the previous example， I can still find a way of tricking the system。

 but in general， what happens is that if the two signals occur together inside，This particular thing。

 I'm not reading them， I'm not considering them。When the trigger comes in， which is a time trigger。

 When I read the value of it is in there and I could have already to say。

 taken care of this inconsistency， right， So nothing else。

That is the difference between event trigger and time trigger so event trigger is as I say before is the most intuitive is the fastest reaction that you can dream of。

 it can yield to problems like we said before over the twobut push at the same time。

 there may be a sequence of command that come in really very fast one after the other which are contradictory and you may enter into very bad behaviors right so thats a reason why in general time trigger mechanisms are safer。

And so when you have safety critical system。😊，You prefer to use Ste trigger。

Architectures or protocols， or whatever you want to call it， yes。Yeah， well。

you don't see anything Okay， because， okay， so sometimes。

This is something that I fired many graduate students upon this thing。

 sometimes people say that the transition takes zero time。

Right and the communication takes zero time is not so。

 I mean it's stupid to say so it doesn't matter why， because what happens between this and this。

 I don't see right it is not there right So I see only the effect of that at a particular。Instance。

 right。And so remember this。 Okay， so because this is the essence of your question。

 So I don't see anything in there because it doesn't matter。 It doesn't exist in my model， okay。Now。

 then very interesting question is that what do you think the word is？

The word is vent or is time trigger。Well， of course。

 if we go down to the nano second is a different step， but they're assuming in our normal life。

Our environment is event trigger or time trigger。Any wild idea。You could make both。

 but principally mainly the the natural。Behavior of our。Is event is a event right， So， for example。

 anything which event event is also， you could also say it is an asynchronous system， as synchronous。

 So things happen whenever they want， right， and they are not lining up。Now。

 the notion of a time trigger or synchronous system is that you line up things。

 you make sure that things are lined up。So you order things。

 So you make a disordered word more order。 So you eliminate entropy， right。

 So you try to take entropy away。 but indeed， as we say before， the word is asynchronous。

 So the word is。イベント not。And so now the point is that how do you？Implement a synchronous model。那。

Oops， when you implement the synchronous model right you have to figure out ways of making an asynchronous word synchronous。

 so what would you do？😊，The clock， the clock right the infamous clock right the clock is a reference。

 a time reference that produces the trigger is still trigger right its trigger iss event trigger。

 but on one particular event that is the clock。😊，So and that is a way in which you trick an essentially asynchronous system to behave synchronously。

But when one of you tells me。That the synchronous system when there is a clock。You're fired。For sure。

 that's nothing to do because this model， the finite state machine model， is without time。

 there is no notion of time in it。The notion is transitions。

Is that what matters on a finite aid machine is a transition。 there's no time， no time whatsoever。

 Now the clock you use to implement a synchronous behavior， but it' not the synchronous behavior。

Is a trick。Okay， is an implementation？Fiction， right， So it doesn't exist in some sense。

 So you make it。Do that。 All right。

![](img/0131f77353ad1202ef031a522dd2d483_27.png)

So a reaction occurs whenever something is presented to them。Of the office。

Now suppose that x and y are discrete and pure signal， when does this transition occur。

 the environments a reaction and x is absentive， this is a complete event trigger model when the transition will never be taken because the reaction will only occur when x is present。

So otherwise doesn't know what to do。Stay there。 Okay Now， when you have a clock， you know。

 the white clock sometimes is a horrible thing to do。 horribleible meaning is wasteful， wasteful。

 right。So to have a clock， you have to have the cycle of a clock， right？The cycle of a clock is a。

Regular period， So every so many second or so many nanosecond pi or whatever。

You have to give it ping and input， right。Now suppose that I sleeping right nothing happens in the world is just I'm sitting there doing like this and then the clock comes in and ping。

 I wake up， I do something， stay there， nothing happens boom goes back to sleep ping okay so every time you do ping you know circuit work。

 power is consumed to do absolutely nothing right。😊，And so when you study what the cycle is。

 you have to balance the fact that you want to be able to catch signals when they come in。

 and at the same time you don't want to wake your system up too often。

 So when you have a timeter protocol， for example， wireless communication。

 TDMA right tiny division multiplex。You have tricks of all kinds of sort in such a way that not your entire node wakes up when the clock comes in。

 not only small tiny piece of a circuitry。😊，Now， that circlely detects something when wakes up everybody。

 but if nothing happens， it's only that small piece and goes up and down。 so power is。😊，Optimize。

 okay。So for every solution， there is a downside and there is an upside。

 So you got to choose which one you care more， So is efficiency or is safety。

 This is the trade of efficiency。Event trigger， safety， time trigger， okay。



![](img/0131f77353ad1202ef031a522dd2d483_29.png)

Now， when does this reaction occurs， because input or discrete and interaction occurs on the tick of and external of clock。

 that is a time trigger， we already say that the key event that allows the key guard that allows me to move from one state to the next is the clock。

So the clock has always ended with all the inputs， real inputs to the system。

And so if the clock is down， nothing happens。😊，The clock is up， I do something。



![](img/0131f77353ad1202ef031a522dd2d483_31.png)

Now the default transition we already talk about is when I don't tell you what is happening right so in the case of the car coming in and coming out。

 we say that the state would not change， but I didn't indicate it with a cell flu saying I'm staying well。

Now， when this is a default transition。So I'm not telling you but is there and is obvious what it is and so it's hidden its a ghost transition。

 whatever you want to call it， but it is there and so these are also called default transition there are many ways calling it so default is as good as anything。



![](img/0131f77353ad1202ef031a522dd2d483_33.png)

诶。Now嗯。The important thing is that in general is a good idea to show the default transition。

 if I produce outputs， of course， because I have to have a place where I'm going to put the output on and so I show the transition nothing is changing but is producing an output。

 so I show it。So in this particular case， you see is a traffic light controller Im sitting green and there is no reason why it should change from green to yellow。

And so I'm sitting there， but I keep on outputting green， right？

So that that I need to say same thing yellow， nothing happens。 So I stay there。

 So there is the default transition， but it has an output associated to it。 I may as well。



![](img/0131f77353ad1202ef031a522dd2d483_35.png)

呃 displayplay。This is a particular case where it doesn't have to be shown because if you use the control。

 which is a pure signal， yes。Sa的嘅。这。By that argument that if you want to show that outputs remain switched on when you're in a particular state。

So in the Gar counter example are。Semantic， yes， well semantic。

 if you wanted to have a complete finite machine， Yes， I should。 So if nothing happens。 in fact。

 not up， not down there I stable。And so that would be an explicit。Deult transition， okay。

But in that particular case， if I assume that the display of the counter is a persistent signal then I don't need to show it because my output is not changing。

Okay， and also in this particular case， notice that I put the signal instead of saying heat， right。

 I just say eat on。Which means I switch the heat around and then it stays out and so I don't need to tell it because the signal already encodes the notion。

But I stay。 So that is the reason why I told you guys that any time you have a problem， right。

 and you want to encode that problem with a particular mathematical notation。

 There is not a single unique way of doing it。There' is a better way of doing it。

 but there are many different ways in which you can do it。

And so it's up to you the creativity or the quality of the good system level designer is to find the right encoding of the problem。

 right quote unquote I mean the efficient encoding of the problem efficiency is related number of states。

 a number of transitions that can stuff okay。😊，So this is again， is not a God given。

 so it's as always， a model is a representational reality。

 a representational reality you can have in many different ways。



![](img/0131f77353ad1202ef031a522dd2d483_37.png)

Now， there are a few definitions about finite state machine that are useful when you read the literature sometimes may contain this information。

 so it's good to say what they are， so stuttering transition。

So startuttering transition is potentially an implic full transition that is enable when inputs are absent。

 So for example， when you have。If you。Think about the time tri model。

You could qualify a startering transition when the clock comes saying nothing has happened and I keep on looping on myself。

 rights startuttering。 So it means that I don't do anything， right sit there， sit there， do nothing。

 Okay now receptiveness， the a finite state machine is a receptive if for every changing the input。

 something happens to a finite state machine， So some kind of transition is taken。So if I want。

 for example， to detect fire， it's better to have receptive machine。

 which means that whatever if I have a fire， the thing wakes up。

And there's the noise that we are all expecting to do if there is nothing we don't want the siren to go off right so this is a receptive。

 meaning that no matter what happens， I always have an answer so that's a receptive machine。

A finite aid machine is deterministic if given a state and given an input。

 there is only one next input and one next state I'm going to。😊，Now， I could represent。

A real problem。Also， as a nondeterministic finite state machine， which means of the same input。

 I can go to two different states。Now， that would be interesting because if I want to know what my system does。

For a particular input I can go in two states now if I want to know all the possible states I can reach。

 I have to keep two traces right I have to look at the finite state machine and there are two potential choices that my machine has taking so it makes life more miserable to find out what the system does what is the advantage of doing nondeterminative finite state machine you can compact the representation right。

Because I'm trying to eliminate things that I don't care about。So。

And we'll see later on what we can do， and in fact there is a bunch of theorems。

 let's say that if you want to eliminate nondeterminism。

 you can have an exponential blowup in the number of states。And then there is a famous construction。

 which is called therabin Con that transforms any non deterterministic finite state machine into a deterministic one。

 but is explanation。So essentially， you have to make all the possible combination of next state as an additional state。

 right？And so now you have2 to V N potential additional states wherein is the number of。

States where I can go from this state。All right。Determinist we say。

 example of a nondeterministic finite state machine is this one。

 the two red arcs are transitions that。Are taken under the same input。

So I can go either in that state or I can stay in my state。 So for example。

 suppose that I have a traffic signal which is triggered also by the presence of a car right so for example。

 I mean the famous country road problem the country road problem is that if you have a standard traffic light which works on time triggered right so often goes from red to yellow from red to green to yellow to red always like that but people get very n because on the side。

 there is no car comes across or you have a bunch of cars sitting where waiting for a signal turn green right and there is no need why that signal should be red because there is no car on the sides So there is a sensor that detects if the car is well or not now it so happens that as soon as a car comes in it's not that you switch immediately。

To green on this side， Otherwise， you have a pile up。 you wouldn't believe， right。

 So you go into a waiting state。 So you wait to see what happens。 Now。

 that waiting state right is a different state， but or you can stay。In the same cycle。

 and that is what the two red arrows are telling you， that under a particular event。

 you can go either to the next state or stay in the same state in this particular case。



![](img/0131f77353ad1202ef031a522dd2d483_39.png)

So behavior interests， we were talking about the behavior of a finiteing machine。

 What is that behavior of the system， right， The behavioral system is what a system can do， right。

 So it's and I exhibit a behavior， meaning I see what I do over a period of time under a potential sequence of input。

 So a behavior， as it says， is a sequence of nontating steps。Now what is a trace。

 a trace is attached to a behavior and simply recording all the values state input and outputs。

 so it's a sort of black box for airplanes and black box of airplanes do exactly the they take a trace of a behavior of a plane。

Now a computation tree is actually a graphical representation of all possible traces。

 so it's like you have a finite data machine and you flatten it up forever possible the inputs you show where an x output is and for every combination of input you have to branch out and so it's a linear graph it goes like this there has no loop except a final loop that comes back to the beginning。

And is much， much infinitely bigger than the finite state machine。 The finite state machine。

 if you think about it， is a very complex way of representing a set of behaviors。Okay。

You represent this set of behavior by the rules that you have to follow to create the behaviors。

If you want to know what happens to the system， you apply the input in sequence and you see what the system does。

And so you are exploring one behavior， you are taking one path into this computationalal tree。

Miscomp thing。So the beauty of state models is the fact that they encode in a finite way an infinite number of behaviors。

Potentially infinite number B。So now final state machines are in general very good。

 especially when it comes to check safety properties。Now。

 safety properties means that no matter what sequence of input are coming in。

 you are not falling into a bad state a bad state when say， well， engine blows up， right。

 that's a bad state right。Or airplane crashes。 That's a very bad state。 Okay。

 so you want to show it under possible set of inputs， all possible thing。

You never get to a situation where we can， or the airplane crashes。Now， in a finite state machine。

 you can investigate the behaviors。And see whether you hit the bad state or not。

 if you never hit the bad state and you're cool， right， my design is safe。

 So safety properties are checkable in finite state machines。

 So we are going to see towards the end of a class methods。To do this reachability analysis。

So you analyze what can be reached and what can never be reached。

So the safety properties are bad state， you never want to go there。

There are another class of properties that are the liveness properties in which you want to say that I always can get to a state。

😊，So it a complement of what we say before。Now， that is much more complicated。

To verify liveness is a beast right Saty is much simpler as a problem in itself。

 and there are efficient algorithm to do so， even though are efficient but not cheap by any means so。

Yes， how can you decide that you don't make sure that ensure you're not going to get to a state if you're not coded for that state。

 so is it like a port for a state that you don't want to get into？Yes， of course， yeah。

 I give you yes， I give you the finite state machine that describes a behavioral a system， right？

Then I give you the set of bed states and I have to tell you what these bad states are right now the point is that when you actually compute on this finite state machine。

 there are data structures that are particularly efficient so that you can compute really fast next state function so you want to show that for。

And。Transitions。In your next state function， the best statement is not。 Okay， so let's say。

This story， okay。AndSo you don't know because it depends on the initial state and on the sequence of inputs。

 So if the best state is isolated， there is no transition it takes the when is trivialvin。

But sometimes it's very difficult to determine， I mean you don't have a graphical representation right because it would be too big and so you have encoded representation in short representation the next state function and so in order to see what are states and if you reach the states or not you have to apply this next state function starting from the initial condition。

and then you can prevent some inputs from occurring。That will not take you to to a bad states。

 So the controllers do that a controller， What happens， What do they do is that inputs come in。

 And then I prevent the finite state machine to go into states。

That will lead me eventually into a bad stuff。 So I cut that off。For example。

 I don't know how many of you have followed the story of the American Airlines plane but went down in。

In New York， right？Well， that was a bad state reached。 right。

 So what happened is that in the controller， it was not taking you to a bad state。

 interesting things， the man， the bad guy was driving， but took。

I don't think the plane we took to the bad state， why。

 because the plane was going up at too steep an angle， lost lift。

And so what the automatic control did is that you say， oh， if you do like this。

 we are going to go into a store and we are going to crash， so how do you increase the lift？

you nose down right you got nose down because you increase the speed you get the lift and then you go up again right but you had the turkey pilot and the turkey pilot saw the plane doing like this we were crashing and was taking up and the more the plane wanted to go down because it was losing the speed the more the guy was taking it up and the more speed he lost until boom stole catak bomb so the controller was preventing you to go to the store right。

😊，And so the controller was changing the state of the system to avoid to go into that state。

 so that's what controllers do。Now， also tells you that if you have two controllers that don't agree when disaster always strikes。

 so don't do that。Or teach the pilot what the guy is trying to do。 Okay， so that is。

An example of how design is important， Design for safety is really important and how it is also important to model the environment。

And when you talk about environment is not only the environment， meaning the speed of the air。

 but also the turkey human。And so why autonomous driving is so very good because we take a human out of the loop。

 so 99。99% of all accidents on streets is because the driver is drunk， the driver is texting。

 the driver is upset， the driver is a heart attack， whatever the driver， take the driver out。Okay。

 so that's my recommendation， take where I out。I'm much more confident about these machines than whether I。

So use of nodemins， there are two ways of using nondemins。Which are very important and interesting。

 The first way in which you use nonde is to say， I don't know。So for example， right now。

 I don't know if she's going to stand up and hit me。Good， right， Why not， you get Ch bank professor。

 I don't like it Ch， right， okay， so if I don't know where she could exhibit bad behavior。

 then I don't take into consideration。 If I want to be super safe， I'll take a distance， right。😊。

So that I can react。 So it's nondeterminism。 So I have to say she is possibly going to hit me or possibly staying。

Inner seat。Maybe fall asleep。 But you know， that's okay。 It's not dangerous to me。

 This is a nondeminist， right， because I don't know what she may do。 I don't have direct control。

 So I don't know。 And so nondetermin is is that。Under these particular conditions。

 she can react this way the other way， the other way， okay。Now。

 the other way in which I can use the nondetermin is is because I have not decided yet。So I want。

 for example， to have an implementation of a system that does something。

 and I've not decided yet if I'm going to take this particular implementation of that particular implementation。

That I is not that I don't know。 I've not decided。So now。

 assume that you want to establish safety of the behavior of your design。

So how do I take care of these nondeterminants？I have to check all possible behavior where she' is going to exhibit。

 right。And then I have to say that for whole air behavior， I'm fine， So take the distance。 I'm fine。

 don't worry， Thats one， that's the way in which you deal with what you don't know and what you have not decided if you want to check safety of your design。

 The thing what you have to say， that there exists in implementation that exists a determinationization on my finite aid machine that is safe。

😊，So for her， I have to use for all her behavior for what I have not decided yet。

 I have to say that exists， at least one decision that is making my assistant safer and then of course I was going to choose that but you see the difference if there is a semantic difference in using nondetermins to say I don't know what happens。

And what I've not decided yet is a degree of freedom。 Now， this case， is not a degree of freedom。

 It's actually taking away degrees of freedom。 The other case is representing degrees of freedom。

Okay。We say that already nondeterministic finite state machine， of course。

 are more compact because if I wanted to display all possible behavior that she may have。

 I may have a uongous I don't know how many behavior you can have but I assume many and all possible gradation from very bad to very good and so I have huge amount of states right that I have to instead if I say I don't know is more or less like this right so I clamump all this behavior into one and then I'm using nondetermin is to represent what she may or may not want to do so that's what I say a potential exponential and nondeterministic behavior of course I can build a tree of computations for nondeterministic behavior and I have to see what happens for all possible situations that corresponds to different choices that I'm going to take into a finite state machine which is a royal pain in the day。

So the point is that nondetermin is's very good to represent Its very bad when you want to do things on it。

 Okay， so let's。Very bad because you always have to deterize it，So it's good for representation。

 but then when I want to do something， I need to explore all possible condition and choices。



![](img/0131f77353ad1202ef031a522dd2d483_41.png)

Dong related points。 What does receptivist mean for nondetermin finite aid machines。Question for you。

 Think about it and then come back to me。 Now， notice when non deterministic doesn't mean probabilistic behavior。

Okay， now there are things like probabilistic finite aid machines。

And what are probabilistic finite state machines， they say that。

Now I know a little bit more about her model。 And so I say there is a probability001。

 I hope that if she's not going to hit me。And there is a probability， say，10%0，1。

 she's going to fall asleep。 and there is probability。9 at 0，9。

 where she's going to be nice and quiet and following the lecture and being a nice person。 Okay。

 so that is a probabilistic model of her behavior， which is not nondeterministic。 Why。

 because I know what are the condition under which she behaves this way the other way and so on。

 So probabilistic doesn't mean nondeterminist。Its deterministic as deterministic can go。Okay， yes。

りも多。Soた niceして。The controller of a computer， yes， not the entire computer is impbi。😊，model也是呃男女。

Of course， because some of the phenomena are based on quantum mechanics。

 so it's not known deterministic， is highly statistical modern statistics。

 is's governed by statistical。What， that is the。Yes， exactly。 It's not known deterministic。

 It's probabilistic Mac quantum computing will be a probabilistic。

Because this transition can be taken with this probability。

 this transition can be taken with other probability and so on。

 and so the question to ask to a probability to finite aid machine is say， if I give this input。

 what is the probability that I'm going to this state？But it's not。No， it's deter。

It'sBecause probabilistic means， you know， it's essentially nondetermins， I say before。 I don't know。

 I really don't know anything about it。 Probabilistic。 I know the model， right。

 I know the probabilistic model。I know so。 So。スてアテ。Yes。Yes， yes， indeed， because I have a model。

 you know， I know what happens。Because the probability of a high associatedci Veization。

I well is characterized。 Now， in on the  deterministic finite State machine， I have no idea。

I can go here。Could be， but he's not。I don't know。 You see， that is the difference。

 Nodemin this means I don't know nothing about it。Okay， probabilistic。

 I know a probability I know something flip。😊，Ifhi flip a coin is deterministic。

 but is probabilistic。Because I have a distribution。As I said before， the behavior she is exhibiting。

 I don't know what probability she's going to have， for example， I suppose that I drive a car right？

And what is the you know， I don't know what may happen of the mountains right maybe a big bull there that comes down and hits me how do I know you know I have no notion of a piece of rock coming down and so that's nondemins right I don't know。

 could be， could be not。After you model every probabilistic。

 So what is the probability of the rock hitting me boom， And， in fact， you know， for example。

 the insurance cars the insurance companies。They work on probabilistic models。嗯。

But they assume that there is a probability of everything。

 and then they measure what is a probability we are losing money。And they priced it accordingly。



![](img/0131f77353ad1202ef031a522dd2d483_43.png)

Okay， so sometimes it's usable to model a continuous system。

 so an infinite dimensional system into finite state machines and what you do is that you can discreittize for example。

 space right so in the hill climbing robots， you can say instead of having a continuum。😊。

tellslls you with position you can put overlap a grid and then you can say the only information you want is that I am in this block of a grid or I in this grid block of a grid I'm in this block of a grid。

 and so that becomes a discrete grid。So it becomes a funny state。Systemム。



![](img/0131f77353ad1202ef031a522dd2d483_45.png)

Now， this one is and this is real， so this one is actually a finite machine that represent an engine controller。

Now interesting point now if you follow this from Delphi。

 now if you put all of the thing that you see on the node are the description of what the state is。

And the arcs are labeled the guards and all that， what happens if if you take this action。

 this action or the other action now is interesting because this is indeed a F state machine and is given the control to the spark plugs。

 recognition。And iss giving you the control over the injection。

 how much gas you inject into a cylinder， right。And when you。Hit。The spark inside the engine。 Okay。

 so this engine control does all of this。Now， the interesting point is that if you look at the actual system。

The actual engine is a discrete system or is a continuous system。

So the movement of a pitons is continuous right So the control the representation of a control action is discrete。

 but we actually this call hybrid system。 So there is a piece that is continues when a piece that is discrete and this is a piece that is discrete they represent and summarizes the behave。

 This one our Ven initial state， the state， the input output transition usual stuff。Now。

 there is also an a model of finite state machines in which you can hide the state inside and you can represent the behavior of finite state machine as a set of。

Function at the input function at the output in that finite state machine is a mapping of the space of the input into the space of the output。

 Now， this particular case， I wouldn't。Possibly use this model， but you could use it。

 And it's particularly useful to combine finite state machines， but。

You lose all the advantages of finite aid machines。 so don't do well， in my opinion。



![](img/0131f77353ad1202ef031a522dd2d483_47.png)

So what we'll be able to do if an machine， a way to represent。

The system for mathematical analysis so that a computer program can manipulate it。

 a way to model the environment of the system， as we said before。

 a way to represent what the system must do and must not do So as a specification and a way to check whether the system satisfy it。

Requirements in an operating environment。Fite state machine is good。 Now。

 can I represent everything as a finite state machine E too bad。 No， O， so but it's a nice model。

 Every time you can use it， please use it。 Okay， next time。😊。

