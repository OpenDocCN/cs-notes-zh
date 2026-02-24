# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p37 -37-#36 State Machines Part-2_ Guard conditions.zh_en -BV1fRt2efEms_p37-

![](img/b0c3fe36304c9d42aab80522632b21e4_0.png)

🎼Yeah。Hello and welcome to the modern embedded systems programming course。 My name is Miro Samak。

 and in the second lesson about state machines， you'll learn about guard conditions as a mechanism of making your state machines more flexible。

 This concept will be needed in the upcoming lessons where I'll discuss the promised added variants of state machines。

😊，As usual， let's get started by copying the previous directory for lesson 35 to lesson 36。

 Get inside the new lesson 36 directory and double click on the By button dot QM model file to open it with the freeware QM modeling tool。

If you don't have QM， you can download it from statemachine。 com。As part of the QP bundle。

To remind you quickly what happened so far in the last lesson。

 you have learned the very basics of state machines。

 you also designed a simple state machine for your blinky button application。In a nuts。

 a state machine is the most optimal solution to the very common problem where a system needs to react to events not only based on the event type。

 but also depending on the history of past events。For example， in your blinky button application。

 the timeout event needs to trigger different reactions depending on what happened to the green LED previously。

This is very elegantly handled by the off and on state in your state machine。In the off state。

 the timeout event causes turning the LED on and a transition to the on state to remember the LED change In the on state。

 the same timeout event causes turning the LED off and the transition to the off state to remember the LED change。

So this is how the reaction to an event depends on both the event signal， timeult in this case。

 and on the current state of the state machine。 However。

 this is still not quite flexible enough for manyial life situations。

The reason is that the whole structure of states and transitions in a state machine is fixed at design time。

But what if the behavior that is the reactions to future events depends on the user input。

 which is obviously not known until run time。 This means that for certain transitions。

 you cannot known at design time which state to transition to。To address this need。

 the UML state machine notation includes the so called choice， pseudostate and guard conditions。

The whole idea is actually very simple and is a way of combining a decision point from a flow chart with a transition notation。

Specifically， a transition can go into a choice pseudo state depicted as a diamond。

Out of this diamond shape， you can have several outgoing transition segments。

 each labeled with a guard condition depicted in square brackets。

Guard conditions are simply boolean expressions evaluated at run time。

 If a guard condition evaluates to true， the corresponding transition is taken。 Otherwise。

 the transition is considered disabled， meaning that it is not taken。

A special complementary guard depicted as Ls in square brackets evaluates the true only if all other guards from the same choice pseudostate evaluate to false。

Now， let me show you an application where such choice pseudostate and guards would be very useful。

So suppose that you want to use your TV C Lapad board as a controller for a time bomb。

 which should work as follows。After reset， the controller lights up the green LED and wait for the user to press the button as W1。

When you press the button， the board turns the green LED off and startsty out。

It blinks the red LED on and off three times， after which the bomb explodes。

 which you emulate by turning all three LED colors on。In other words， after the reset， green light。

And after the button press。Blanlink pause， blink pass。 blink pass boom。Okay。

 so now let's build a state machine for this behavior。Again， just as in the previous lesson 35。

 I will use the QM visual modeling tool with a previous By button model as my starting point for the time bomb。

I will save the model as Tbam do QM。And I will also rename the active object to time bomb。So now。

 as you remember， the initial transition should turn the green LED on and transition to a state with the time on wait for the user to press the button。

 Let's name the state， Wait for a button。Inside the weight for button state。

 the only event of interest is button pressed so you can get rid of the other events。

The button pressed event needs to perform the following actions， turn the green LED off。

 turn the red LED on， arm the time event to expire in one/ half second。

And transition to the blink state。Because as you remember， button press should be followed by B。

In the Blink state， you can get rid of all events except timeout that you just aren't on the transition to this state。

The timeout event needs to turn the red LED off， arm the time event for another one/ half second。

 and transition to the past state。Because as you remember， planck is followed by pause。

In the past state， you also need to handle the just aren time out event to get ready for another blink。

But wait a minute， where should it go with this transition？I mean。

 you cannot naively go back to blink because that would create an endless loop of blink and pause。

A brute force solution would be to add three groups of blink and pause states， because at this point。

 the time bomb is supposed to blink just three times。

But this is obviously a rather brain dead solution。

 not only because there are so many states that mindlessly repeat essentially the same behavior。

 but also because the number of blinks is likely to change。Indeed。

 the next feature could very well be that the number of blinks before the time bomb goes off needs to be adjusted by the user。

 so you simply cannot know this number at design time。So instead。

 a smarter design would be to add a blink counter to the state machine that would simply count the number of blinks。

Specifically， each time through the pulse state， the action on the timeult event would only decrement the counter。

Now， you need to apply the new concept for this lesson by adding a choice pseudostate。

 which you need to label with a guard condition。 The guard is simply a boolean expression B counter greater than 0。

 This guard means that you still have some blinking to do。So we go to the blink state。

But he should not forget to also perform actions to prepare for the blink state。

 such as turn the red LED on and arm the time vent for one half second。

You also need to add the complimentary Egar， which will go to the new state boom。

On this transition segment， you also need to perform actions to prepare for the state。

 such as turning all LEDs on to emulate the explosion。Of course。

 you still need to add the boom state。And point the transition segment to it。Finally。

 you need to initialize the blank counter variable to the total number of blink you wish to have。

 You can put it in various transitions upstream from the blank state。 for example， wait for a button。

All right， so now you just need to code the state machine。Again， like in the last lesson。

 youll be doing this manually， even though the QM modeling tool could generate the code for you。

But at this point， I haven't yet explained any other more optimal state machine implementation strategies。

 So let's stick to the straightforward nested switch statement technique that you've learned in the last lesson than 35。

So first off， you need to rename Blinky button to time B in your whole project。

After the global replacement， you need to make some manual corrections。And actually。

 since this is just a name change， the project should still build cleanly。 Now。

 inside the time bomb active object， you need to enumerate the states of a state machine。

 These states are， wait for button。Blink。Pause。And boom。

You also need to check the declarations of the internal private variables。

You obviously need the time event， so you keep it。 But instead of the blank time。

 you now need the blank counter data member。At this point。

 you can delete the no longer needed initial blink time constant。 But next。

 moving on to your state machine， you start with the initial transition。

As you remember from the last time， the whole state machine implementation goes into the dispatch function。

 So here for the initial transition， you turn the green LED on and transition to the weight for button state。

All states of your state machine go into the switch statement。

 which discriminates based on the me state variable。The first such state is， wait for button。

Here you handle just the button pressed event so you can delete all the others。

The actions on button pressed turned the green LED off。The rather lady on。

Arm your time event for one/ half second。And initialized the blink counter to3。After this。

 you transition to the blank state。In the blank state。

 you handle only the timeout event so you can delete everything else。

The actions on time out are turn the ra off， arm the time event for one half second and transition to the pause state。

Now， the paths stayed dissimilar to blink。 so I just copy and paste the blink code as my starting point for pause。

The first segment of the timemo transition only decrements the private meling counter data member。

But now comes the most interesting part of coding the choice point and the guard conditions。

 I hope you can see that the first branch corresponds to the if statement that simply checks the guard condition。

If this guard evaluates to true， you turn the red lady on。

 arm the time event for one half second and transition back to the blank state。

The complementary es card corresponds then simply to the elses branch of the original F。Here。

 you turn all the LEDs on to emulate the bomb explosion， and you transition to the boom state。

 Finally， the boom state handles no events， So it is an empty case statement。In summary。

 the choice pseudostate and guard conditions turned out to be simply ifs and analysis in your C code。

Please note that these are exactly the same As analysis that the state machine was designed to eliminate in the first place。

 Just recall the spagheti code from the visual basic calculator example I showed you in the last lesson 35。

So the moral here is that the guard conditions should be used very judiciously to many of them。

 and you'll find yourself back in S 1， spaghetti。Where the guards effectively take over handling of all the relevant conditions in the system。

 On the other hand， guards are sometimes unavoidable because they add the necessary flexibility to the state machines。

Therefore， one of the main challenges in becoming an effective state machine designer is to develop a sense for which parts of the behavior should be captured in states and transitions at design time and which parts require runtime flexibility of guard conditions。

 General， you should challenge yourself to use as few guard conditions as possible。All right。

 so the last order of business for today is to check how your code works on the board。For this。

 I'll simply upload the code to the board。When I press the reset button。

 the green LED lights up as expected。 Now， when I press the S W 1 button，3，2，1， boom。Okay。

 so now let's change the blink counter to say， count 10。And rebuilt the code。

Loow the code of the board。嗯。And press reset。Greenland。Good， now， the button，10，9，8，7，6，5，4，3，2，1。

 boom。This concludes this lesson about guard conditions。 Now。

 you are truly ready for the next lesson where you'll learn about the other variants of so called input driven or ped state machines and how they compare to the event driven state machines that I have been discussing so far。

🎼Yeah。If you like this channel， please give this video a like and subscribe to stay tuned you can also visit statemachine。

com/quistart for the class notes and project file downloads。



![](img/b0c3fe36304c9d42aab80522632b21e4_2.png)

🎼Yeah。