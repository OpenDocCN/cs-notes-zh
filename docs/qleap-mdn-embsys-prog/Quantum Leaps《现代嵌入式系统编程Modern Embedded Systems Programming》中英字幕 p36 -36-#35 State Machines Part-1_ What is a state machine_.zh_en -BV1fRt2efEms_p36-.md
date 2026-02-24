# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p36 -36-#35 State Machines Part-1_ What is a state machine_.zh_en -BV1fRt2efEms_p36-

![](img/5aea05c86586b5f5a2b1b6b171c92835_0.png)

🎼う。Hello and welcome to the moderndern Emded System programming course。My name is Miro Samak。

 and to day， I'd like to start a new segment of lessons about state machines。

 This subject is closely related to eve and programming and active objects introduced in the last lesson。

🎼M。As it is actually a continuation， let's get started by copying the previous code for lesson 34 to lesson 35。

Get inside the new Les 35 directory and double click on the project lesson to open it in the Ar Kyle microcrovision IDE。

To remind you quickly what happened so far in the last lesson。

 you have learned about the best practices of concurrent programming and the active object design pattern that naturally implements and automatically enforces these best practices。

You also started to build your own event driven active object framework called MicroCAO。

 because it was based on the traditional microCO2 artists。

Which is then applied to build a small blinky button application。But already。

 that small example showed some looming problems with the event driven an approach。Specifically。

 the part of the coated blinks The green LED required you to invent a Booleion flag that was called is LED on and which you needed to remember the state of the green LED between the timeout events。

Please note that the Boolean flag was not needed in the original art of' thread。

 because in a sequential code， the waitinging between events happened by means of blocking inside the OS time D LY function。

After receiving the expected event， the code unblocked and simply handled the event because you knew exactly which event was received。

 Therefore， you didn't need to do anything special to remember where in the sequence of events you were。

This is an example of maintaining the context between events naturally and automatically。

As it turns out， this automatic contact management is quite expensive because as you recall from the previous lessons about the arts。

 the context of a thread during a blocking call requires a whole private stack in the precious RamM。

 but the automatic contact management surely is convenient。

 if you can live with hard coded event sequences。All this is in star contrast to evanrven code。

 which cannot block and instead has to return to the event loop after every event。

 Such code obviously loses the stack context between events。 Consequently。

 Evanrovvan systems tend to use less stack space， but instead require a different form of preserving the context from one event to the next。

The most popular is the manual context management where programmers invent flags and variables。

 such as your isL on flag in your blinking Ba active object。This approach seems to work initially。

 and is Dion flag certainly didn't loom as a big problem in a simplistic blinky button event of an active object。

But in most real life programs， such approaches almost guaranteed to degenerate into unwieldy spagheti code。

 which I'd like to quickly demonstrate with the evanger and visual basic calculator example。



![](img/5aea05c86586b5f5a2b1b6b171c92835_2.png)

I understand that this is not an embedded system， and it is not even written in C。

 but it illustrates， well， the main problems without the need to explain how a calculator like that is supposed to work。

So the visual basic for operation calculator obviously adds subtracts， multiplies and divides。

But if you try some less usual sequences of key presses。

 you would discover quite a few corner cases leading to crashes or misleading behavior。

 One such corner case is the following sequence of operations 3。Plus， minus- equals4 equals。

 The calculator crashes with runtime error 13。One might argue that this is a meaningless sequence of events。

 but at the same time， it is also obvious that no user actions should crash the software like that。

So the calculator apparently has trouble correctly responding to events in different contexts。



![](img/5aea05c86586b5f5a2b1b6b171c92835_4.png)

But if you look at the underlying code， you will find out that managing the context is really the central concern here。

 and most of the code is devoted to it。Even though you might not be familiar with visual basic。

 I hope you can recognize a bunch of variable declarations with the sole purpose to remember the current context。

 For example， the decimal flag remembers whether the decimal point has been entered to avoid displaying multiple decimal points in a number Similarly。

 the nu ops variable remembers the number of opera entered so far to distinguish between the first and second opera in an expression。

 and so on。Then there are a bunch of event handler subrouts each designed to handle a group of related key press events。

 For example， the minus key that confuse the calculator before is handled in the subroutine operator underscore click。

 which handles the plus minus multiply and divide keys and happens to be the most complex one。

Here you can see that the various flags and variables are checked in nontri conditions。

 then modified and rechecked again so that it is really hard to know for sure which path through the code will be taken in a given situation。

Apparently， a four operation calculator is already complex enough to reach the limit of such manual context management because attempts to fix one bug tend to create another。

The real problem here is that the variables and flags provide too much of redundant and poorly organized information。

 which then can easily become internally inconsistent。

But the improvised context management reflects the correct intuition of the software developers that you don't need to remember the whole history of past events。

 only certain aspects of it。Specifically， to handle events correctly。

 you just need to remember the relevant history， which is only what influences the future behavior of the system。

 and events don't contribute equally to that relevant history。For example。

 an electronic controller for a computer keyboard generates either lowercase or uppercase key codes。

This behavior depends on whether the shift key has been pressed or released。

 but it does not matter which other keys have been pressed or released or how many of them were pressed。

Therefore， the whole relevant history of the keyboard can be reduced just to two classes。

The normal class where the keys generate lower case codes and the shifted class。

 where the same keys generate upper case codes。Which leads to the most important concept of state。

State of a system is an equience class of past histories of a system。

 all of which are equivalent in the sense that the future behavior of the system。

 given any of these past histories will be identical。

Thus the concept of state is the most efficient representation of the relevant history。

 It is the minimum information that captures all irrelevant aspects for the future behavior and abstracts away all irrelevant aspects。

The concept of state naturally leads to the concept of state machine。

 which is the set of all states that is equivalent classes of relevant histories。

 plus the rules for changing from one state to another。

 These rules are called transitions and capture the fact that some events contribute to their relevant history。

 while others do not。 These events influencing the future behavior trigger the state transitions。

A very nice aspect of the state mission concept is its compelling graphical representation in form of state diagrams。

In the modern Unified modeling language UML notation。

 states are represented as rounded corner rectangles with the name of the state in the name compartment and regular state transitions are represented as arrows labeled by the triggering events。

In the UL， you can also have so called internal transitions， which do not cause change of state。

 but only execute actions in response to a given event。

These are represented just as triggering events inside states。

The actions are listed after the s character and are allowed on both kinds of transitions。

 internal and regular。Additionally， every state machine needs to have an initial transition that points to the default state。

 which is active when the state machine is created and before any events are dispatched to it。

 a state machine can have many more features， and there are many kinds of state machines using software。

 including the modern hierarchical state machines， also known as UML state charts。

I am going to cover some of the most important variants of state machines in the future lessons。

But for today I just want you to remember one universal feature in all state imaging formalisms。

 and that is the run to completion RTC event processing。

RTC means that a state machine can process only one event at a time。

 so the processing of one event must necessarily end before the processing of the next event can begin。

Well， surprise surprise， the RTC semantics universally assumed in all state machine formalisms matches exactly the RTC semantics assumed in all erian systems such as active objects you' have learned in the last lesson。

So in other words， state machines are an ideal mechanism to specify the behavior of active objects。

As an example， let's build the state machine representing the behavior of your blinky button active object。

 but without the is LED on flat。

![](img/5aea05c86586b5f5a2b1b6b171c92835_6.png)

For this， I will use the freework Q M graphical modeling tool from my company， Quantum Lis。

 This is not to say that you necessarily need such a tool to apply state machines。

 a piece of paper or a whiteboard for drawing state diagrams is completely adequate。

 especially in the beginning。

![](img/5aea05c86586b5f5a2b1b6b171c92835_8.png)

But for a screencast like this， an electronic drawing tool is more convenient。 Also。

 while you certainly know how paper and pencil work。

 it might be more interesting for you to see how to use a graphical modeling tool。

When you launch Q M for the first time， it opens the new model dialog box。

 whereas you can choose from a few models as your starting points。

 One of them blinkly seems close enough to what you are doing。 So let's select that one。Next。

 you can rename your new model to By button， and you can choose the location of your model as the directory of today's lesson。

Okay。So the model already comes with a blinky state machine。

 but I'll delete it so that you can see how a state machine like that is built from scratch。

So the design process typically goes as follows。A good place to start is the default state and the initial transition。

 because this establishes the initial condition of the system。At this point。

 you might not even know how to name this default state， but don't worry。

 because it will become clearer as you flesh out the initial transition。

In case of your blinky button， the initial transition will perform the following actions。

 Turn the green LED off and arm the time event to expire in the off time。By the way。

 the Q and tool provides two fields for specifying the action。

 The smaller field is for the pseudocode， which is just a very concise comment as to what the action is all about。

The bigger field below can contain the actual code in C， which， if provided。

 will be used for automatic code generation。 Only the pseudocode is shown in a diagram。

 which reduces the clutter。But going back to the state machine。

 the actions on the initial transition mean that the default state represents the off state of the blinky button。

 So let's name it off。Now， when the time out event arrives in this off state。

You need to turn the green LED on。And you need to arm the time event for the on time out。

But this means that you can no longer stay in the off state， So you need a different state。

 which logically should be called on。 So let's add the on state and point the transition to go there。

Now， when the timeult event arrives in the on state， you transition to the off state。

In the actions on this transition， you turn the green LED off and you arm the time event for the off time。

At this point， the blinking feature is complete， but this is the blinky button state machine。

 so it must also handle their button pressed and button released events。

These events will be handled in the so called internal transitions， which just execute actions。

 but don't trigger a change of state。 The internal transition for the button pressed event。

Turns the blue LED on and shortens the blink time for the green LED by 2。

The interim transition for the button released event。Just turns the blue LED off。

But these two events need to be handled also when the greenene is on。

 which means that you need to repeat the same internal transitions in the on state as well。Of course。

 such repetition is perhaps not a big deal in a toy example like your blinky button here。

 but in real life projects， repetitions like that can and will pile up。

 This is exactly the problem that modern， hierarchical state machines are designed to address。

But I have to leave the discussion of hierarchical state machines to another lesson。

Because today I'd still like to show you how you can implement the just designed Blinky button state machine in C。

The implementation technique I'm going to show you is not necessarily the most efficient or elegant。

 I will discuss other implementations in the future lessons in the state machine segment。 But today。

 Ill show you the most straightforward way。As you remember from the state machine definition。

 the main job of a state machine is to remember its current state for that。

 you obviously need a variable， which in state machine implementations is commonly called to the state variable。

The most straightforward way to represent the state variable is to simply make it an enumeration of all possible states。

In the By button state machine you have states off and on。

 so the enumeration will define off state and on state constants。

The state variable replaces all flags and variables that were part of the improvised manual context management。

In the simplistic By button example， this means that you can get rid of the S LED on flag。

 which might not look like a much of an improvement。

But please remember that in more advanced state machines， like， for example， the calculator。

 you have still only one state variable， which then replaces many more variables like those ones you saw in the visual basic example。

But moving on， now you need to decide where to put the state machine code。As it turns out。

 the ideal place for this is the active object dispatch function。

This is because the surrounding active object framework calls dispatch only when there is an event to process。

 Otherwise， the active object is completely dormant and does nothing。

This happens to be exactly how a state machine operates。 When there are no events。

 a state machine just waits in its current state and does absolutely nothing。

 This dormant condition is depicted in a blue collar in the Q M modeling tool。

Only when an event arrives， the state machine is activated to process the event in one of the transitions。

 This active condition is depicted in red color in the Q M modeling tool。With this understanding。

 let's now recode the Blinky button dispatch function as a state machine。At this point。

 let's still keep the original code for reference， but remember to delete it eventually。

Starting with the initial transition， the way it is organized in your micro CAO framework。

 the initial transition needs to be executed when the dispatch function receives a special in event signal。

To implement this， you check if the event signal is innitzig and if so。

You execute the actions on your initial transition， such as blue LED off。And。

Arm the time event to fire in the off time。After all the actions。

 you set your private state variable， conveniently accessible through the me pointer to the target of the initial transition。

 At this point， you can explicitly return because you are done。

Now comes the most interesting part of coding the states In this most straightforward method。

 you use the switch statement that discriminates based on your state variable。

You can then immediately provide all the cases for all the states in your state machine。

After all the possible states， I recommend that you add the default case where you can put an assertion because reaching the default case means that your state variable has become an invalid state。

Now， you can flesh out the state cases for this。 You use the second level of switch statement。

 but this time， discriminating based on the event signal。For the off state。

 you find that the first signal it handles is timeout， so you provide a case for it Inside this case。

 you execute the actions listed in the diagram。But you also notice that this is a regular state transition that goes to state。

On。You code it by explicitly changing your state variable to on state。

The next event handled in your off state is button pressed， so you'll provide a case for it。

The actions associated with this internal transition are the same as you already coded in your old version。

 So you'll simply copy it from there。Note that an internal transition causes no change of state。

 so you don't modify your state variable。The last button released internal transition in your off state is coded in a similar way as button pressed。

Yeah。Again， you don't modify your state variable。Next。

 you move on to the on state where you have that timeout event。After the actions。

You code the regular state transition。Which goes to。The off state。

The two remaining internal turn transitions in the on state are handled identically。

 as you have already coded in the off state。 So you will simply copy over that code。At this point。

 you have implemented the whole state machine。 so now you can delete the alt code。

But now I'd like you to take a step back and recount what just happened。Well。

 the state machine is not necessarily smaller than your old code。

 but this is mostly due to the repetitions in handling the button events that I promise to address in the future。

More importantly， however， I hope you have noticed that the whole state machine coding experience was very different than any et you' have written before。

Specifically， once you have worked out a few simple rules of mapping state machine elements like states and transitions to code。

 you could apply them mechanically。 The actual coding did not require much thinking because all the thinking has been already done when the state machine was designed。

In fact， I hope you can now imagine how a modeling tool like Q M could automatically generate such code by applying the same simple rules as you did。

By the way， QM can actually do this。 It can automatically generate code from your state diagrams。

 although it uses a different implementation strategy than you have just seen。

 I'll explain other state machine implementation strategies in the future lessons。

But going back to your today's coding experience， I hope you can now quite easily see how every part of the code corresponds to the parts of the state diagram。

This property is called traceability between code and design and is a required property in safety。

 critical software。And the last point I'd like to bring up is that now。

 you know how to extend your code。 Should you add new states or new events to your state machine or change things around。

 You know exactly which parts of the code need to change。 This property is called extensibility。

 and this is another a great benefit of using state machines。All right， but to wrap up for today。

 I still need to check whether the state machine code actually works， so let me do it right now。

The compiler reminds me to clean up the SL on flag from the constructor。But otherwise。

 the same machine code built with zero errors and0 warnings。

So let me load the code to the Tva Lachpad board。And run it。Well， as you can see。

The blinky button exampler works just as it did before。

This concludes this first lesson in the state machine segment。 In the next lesson。

 you'll learn about other variants of state machines。

 as well as the common misconceptions and misunderstandings about state machines。🎼。🎼。

If you like this channel， please give this video a like and subscribe to stay tuned。

 You can also visit statemachine dot com squiickstart for the class notes and project file downloads。



![](img/5aea05c86586b5f5a2b1b6b171c92835_10.png)

Yeah。