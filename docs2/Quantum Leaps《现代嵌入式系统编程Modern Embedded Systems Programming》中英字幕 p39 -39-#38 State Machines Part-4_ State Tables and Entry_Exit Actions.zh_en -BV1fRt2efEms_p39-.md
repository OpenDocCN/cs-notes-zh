# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p39 -39-#38 State Machines Part-4_ State Tables and Entry_Exit Actions.zh_en -BV1fRt2efEms_p39-

![](img/f4f78a8950f3378cb7f513cd97bda9a8_0.png)

🎼Hello and welcome to the modernern embeddeded systems programming course。 My name is Mirosak。

 and it is fourth lesson on state machines。 You'll learn about state tables。😊，🎼In the process。

 you will see how to implement state tables in C and how to extend this implementation to add state entry and exit actions。

So far in this segment about state machines， you have learned the most straightforward nested switch statement implementation in C。

 For example， the time bomb project from lesson 36 was implemented that way。

The whole state machine was coded in just one dispatch function and consisted of the switch statement that discriminated based on the state variable。

Each case handled a separate state。Within each state。

 you had another nested switch that discriminated based on the event signal。

 The cases were all events handled by this particular state。

A variation of this implementation technique was also applicable to the input driven state machines that you've learned in the previous lesson 37。

For instance， the blinky button project from that lesson was again coded with the switch statement around the state variable。

 But because the whole state machine handled essentially just one event。

 the low quality sample event， there was no need for the second level of the nested switch based on the event。

 Instead， each state contained guard conditions that checked the event parameters to discover the truly interesting events。

But as I mentioned in those previous lessons， this particular state machine implementation is not the most efficient or elegant。

 It's just the most straightforward and therefore the most common。So today。

 I'd like to show you another implementation of a different kind based on state tables。 Again。

 I don't think that this technique is the most elegant or efficient either。

 but it demonstrates a different way of thinking about the problem and therefore is a good stepping stone to understanding other state machine implementations。

Also， state tables are a quite popular representation of state machines。

 so you definitely need to know how they work。Actually。

 you've already seen some state tables in the last lesson 37 in the part about merely and more state machines for describing electronic circuits。

Because the inputs of those state machines were logic signals， the tables were truth tables。

 but they can be easily generalized to events。For example。

 if we just use the al assigned names for states and name the events low for 0 and high for one。

 we can rewrite the to table as follows。But then notice that for every stay in this one dimensional table。

 you repeat all the events。 This means that you can reorganize the same information into a two dimensional table。

You leave the states as they are， but you' list events along the second horizontal dimension。 Now。

 every cell in the two dimensional table contains the pair。

 next state and action to be performed for the given event in a given state。

So these are the state tables， one dimensional and two dimensional。

 They both contain exactly the same information and both correspond one to one to the state diagram。

 just as the original trust table did。All right， so now let's apply the same technique to represent the time bomb soft wased machine from lesson than 36 as the two dimensional state table。

First， open up the project from lesson 36 and look up all the events that are posted to the time bomb。

These events are enumerated in the BSP。 H header file and R button pressed。

 button released and timeout。Now， let's open up the model of time bomb。

And see which states you have in your state machine there。These states are wait for button。Blink。

Pause and boom。For each state， you look whether it handles a given event。 For example。

 state Wait for button handles the button pressed event。

 so you put the next state and actions in the corresponding cell of the table。

For all events not found in a given state， you put ignore， or alternatively。

 you put error if you believe that a given event should never arrive at that state。



![](img/f4f78a8950f3378cb7f513cd97bda9a8_2.png)

You do the same for the blank state， which handles only the timeout event。Now， in state pause。

 there is a problem because this state has a guard condition with one transition going to the blink state and the other going to the boom state here。

 I just put both these next states。 But with the question marks。

 these are then further explained as the footnote to the state table。

An alternative notation is to put the whole guard conditions directly in the table。

 but that leads to quite a clatter。 You'll see how to work around it in the actual code。

Which leads to the most interesting question for today day。

 how to use the state table representation as a basis for the actual implementation。



![](img/f4f78a8950f3378cb7f513cd97bda9a8_4.png)

So for today， copy lesson 36 directory to lesson 38。

 get inside the new directory and double click on the project lesson to open it in the microvision IDE。

The first question in implementing the state table is how to represent it in code。Well。

 the C language supports two dimensional arrays directly。

 so you can have the time bomb table array with the first dimension corresponding to the number of your states and second dimension to the number of your events。

A noteworthy trick to codify these dimensions is to place a special constant at the very end of the enumeration for states。

 which I call max state。And another in BSP dot H at the end of the enumeration for event signals。

 Max Sig。If you keep these max constants at the end。

 you will automatically keep track of any changes inside your enumerations。Now。

 the most interesting decision is about the type of the entries in your time bomb table。Well。

 some state table implementations make each entry in such a table to be aed with a whole bunch of members like guard conditions。

 new state， transition action and other elements。However。

 this abundant information in each and every cell of the state table makes the table very complex to initialize。

 takes a lot of memory， and most importantly， makes even a simple state machine implementation fragmented into literally hundreds of little functions。

So instead， I recommend a much simples solution in which every cell in the array simply holds an action named here time bomb action。

This action function can then evaluate guards and can also change the state internally。

 so no separate next state information is needed。The time bomb action is a pointer to function to be called when a given event arrives in the given state。

 I already used pointers to functions in several lessons in this video course。 For example。

 in lesson 15， about the start up code and vector table。

In lesson 23 about real time operating system and in lesson 32 about polymorphism in C。

The best way to specify a pointer to function in C is through a type de。

 The actual point to function must be in parentheses， followed by the parameterist。

The action function will return void。To get an easy access to data members of the time bomb。

 the action function will take the point or me。And to get access to the event parameters。

 it will also take the pointer E。With this definition， you can now start filling up your state table。

Please note that the state table is completely known at design time and fixed at run time。

 Consequently， it can and should be constant。 This is not only safer because the compiler will not allow you to change the con state table。

 but it will also allow the state table to be placed in Ram。

 instead of taking up space in the precious Ram。But the cons object has to be initialized right away at its definition。

 The only way to perform this in C is by using the C array initializer。

To simplify the job and to avoid mistakes， let me place comments with the labels for all the signals enumerated in B and speed H。

And all states enumerated inside the time bomb class。

But you have to be very careful here because the indexes into the state table array must be consecutive and start at 0。

 However， the signals in BSP dot H don't start at 0， but rather are offset by the user Sig constant。

 This offset is then defined in micro C O dot H errorer file where you see that the very first signal with the default value 0 is in it Sig。

So the complete list of signals in your state table must include in itsse at the beginning。

Now you can fill out the table cells per the state table you' have designed before。

 except the in signal will be handled only in the wait for button state in the time bomb in it function。

For each signal state combination that is being handled。

 you insert a pointer to function with the name， time bomb followed by the state name。

 followed by the signal name。For example， the state wait for button handles the button pressed event。

 so you insert here point to function， time bomb underscore。

 weight for button and underscore pressed。If a given signal state combination should be ignored。

 you insert the time bomb ignore function pointer。You proceed like this。

 effectively copying your initial design until you fill out the entire time bomb table array。

The last step is then to define all the functions used in the table。

So starting with a time bomb in it， you provide the prototype corresponding to your time bomb action pointer to function and just copy actions from the original topmost initial transition。

As you are at the initialization， the state variable。

 me state must be initialized to the weight for button state in the constructor。

 This is because me state will be used as an index into the state table。

 So it has to have a well defined value。 The action function for the weight for button state and button pressed event is implemented the same way。

 Again， you just copy the action from the original nested switch statement。

They ignore action is just an empty function。The blank timeout action function is done the same way。

And so is the pause timer action function。 You just copy over the corresponding case from the nested switch statement。

So now you can clean up the old code inside the time bomb dispatch function and reimple it with the state table。

The code here is remarkably simple and elegant。 Youll take your time bomb table and index into it with the me state variable and the E Sig signal。

Then you call the selected action function via a pointer。

 You pass the me pointer and the E pointer as parameters to the call。

A good idea at this point is also to assert that the variables used as indexes into the array are in bounds。

As a final touch， you can add the static keyword to all your time bound functions。

 just as it is already done for the dispatch function。

This is a good programming practice because the static keyword limits the visibility of the static elements inside the given module and prevents any accidental access to them from anywhere else。

All right， so let's build the code and load it to the Tva C Lapad board。

So now in the second part of this lesson， I'd like to introduce another big improvement in state machines。

 which can eliminate many annoying repetitions in both your designs and code。For example。

 in your time bomb state machine， the state blink can be entered through two different transitions。

 The button pressed transition from waitful button and a timer transition with a guard from pause。

In both of these transitions， there is a group of actions read LED on an arm time event for one half second that is repeated。

This is because these actions are a required preparation for the Bling state。

 and so they must be executed whichever way the Bling state is entered。

These actions logically belong to the B state， and it would be much better if you could attach these actions explicitly to that state。

And this is exactly what entry and exceeds to states allow you to do。Specifically。

 you can provide an entry action to state blink and put there the actions that always need to be executed upon the entry to that state。

As you can see the your mail notation for this is the word entry or just the letter E inside the state shape。

 followed by the forward slash and the list of actions。

You can then remove these actions from all the incoming transitions。

But you don't need to apply the entry and exit mechanism just to the repeated actions on transitions。

 In fact， you should take a critical look at your entire state machine and check which actions would better fit into states rather than transitions。

For example， the action green LED on in the topmost initial transition rarely belongs to the weight for button state。

 so we can put it in the entry action and remove it from the transition。Now。

 whatever is done in the entry actions often needs to be undone in the exit actionss。 For example。

 the green LED turned on upon the entry to wait for button needs to be turned off upon the exit。

 whichever way the exit happens。 So you should move that action from the button press transition to the exit from the state。

Similarly， if the blank state turns the red LED on in its entry action。

 it should turn it off in its exit action instead of doing it on the transition。On the other hand。

 the arming of the time event that also happens on that transition logically belongs to the Pa state because it determines how long the pause state will be active。

Finally， the action to turn all LEDs on to simulate the explosion logically belongs to the entry action to state the boom。

So here it is your time bomb state machine version that performs most of the actions in states rather than transitions。

If you remember the last lesson， state machines that associate actions with states are called more machines and state machines that associate actions with transitions are called meal machines。

So in a sense， what you have just done is that you converted your time bomb state machine from merely type to more type。

But I wouldn't take the merely more classification from hardwareed machines too far into the software domain。

Because typically， software state machines have characteristics of both merely and more machines。

For example， your time bomb still performs some actions on transitions。

 such as the action on timeout transition in state pause， and this is O。Having said that。

 my decades of experience with software state machines shows that the more type state machines with actions associated with states tend to be generally better。

 cleaner， more robust and more maintainable than million machines with actions associated with transitions。

So now the last step in this lesson is obviously to implement your more version of the time bomb state machine using the state table technique。

You have， of course， many options to incorporate entry and exit actions into the state table。

But one possibility is to apply the same idea that you already used it for the initial transition。

And that is to add two new special signals and reenn it into the microCL。 a chatter file。

Now you immediately need to add these signals to the state table as well。

 because otherwise the table won't match your event enumeration。

And then you need to insert entry and exit action functions for all states that handle them in your state diagram。

So for example， your state Wait for button has an entry action and an exit action。

State Blink also has both entry and exit actions。On the other hand。

 state pass has only entry and ignores the exit。And so， does state boom。

The next step is then to define the entry and exition functions that you've already placed in your state table。

The waitful button state into action turns the green LED on。

And the exit action turns the green LED off。The blink state entry turns the red LED on and arms the time event for one half second。

And the exit action turns the red LED off。The past state and reaction just armss the time event for one half second。

The boom state entry action。Oh， wait， you need to remove the transition action already placed in the entry to blink。

So the boom and action turns all the LEDs on。And finally， in your dispatch function。

 you must actually call the correct exit and entry actions when the transitions are taken。

But here is a problem。 How would you know that the transition was taken。Well。

 one solution for this would be that the action handlers themselves would tell you what just happened inside。

Specifically， an action handler could return an enumerated status information， such as。

Trants will tell you that the transition was taken。

Handled status will tell you that an action was handled but without taking a transition。

Ignoreed status will tell you that an event was ignored。And finally。

 in its status will tell you that the initial transition was taken。With this。

 you now need to add the status return type to the signature of the action handler。And of course。

 you need to go back and add the status return to all your time bomb action handlers。

So starting from the top， you need to add return in its status to the initial transition。

You return the handled status from the entry action。And from the exuction， as well。

You return trans status from the transition action that changes the state。Again。

 you return the handled status from the entry and exit actions。

And you return transt from the transition actions。Finally。

 you return the ignored status from the ignored action。With that preparation。

 you can get to modify the dispatch operation to add calling the accident entry actions on transitions。

First， you define the status variable as well as the prev state variable to save there the current state before any potential transition。

Next， you execute the appropriate action from your state table。

 but now you save the return status into your variable。But next。

 you check if the reported status corresponds to a transition。If so。

 you assert that the new state is in range。And then you call the state table action corresponding to the previous state and the exit signal。

At this point， it really doesn't matter which event you pass to the action。

 because the exit action should never use the event。

 It is there only for compliance with the action handler signature。 Therefore， you can pass here。

 the0 pointer。After the exit from the previous state。

 you need to enter the current state so you call the state table action corresponding to the current state and the entry signal。

Again， you can pass the zero pointer for the event parameter。

But you are not completely done yet because you still need to correctly handle the state entry after the initial transition。

So if the return status is in status， you just enter the new state as before。

 but you don't exit any state。And this is about it。

 You try to build the code and load it to the board。Reset button， green light。SW 1 button，5，4，3，2，1。

 boom。Well， it still works。This concludes this lesson about state tables and entry exit actions to states。

To summarize， the state table represents a different type of the state machine implementation strategy because in contrast to the nested switch that was pure code。

 state table is data driven。Specifically， the implementation is centered around the state table data structure。

 which is then indexed into by both states and event signals。

 Other data driven state machine implementations， include representing states' data objects。

 which are then interconnected and traversed at runtime to execute transitions。

The main advantage of the state table of representation is the highly regular structure that forces you to consider all possible state and event combinations。

Also， the implementation provides relatively good and deterministic granttime performance。However。

 the technique has also many disadvantages。The whole state machine code is highly fragmented into a large number of little action handlers。

Also， state tables themselves tend to be sparse with a lot of gaps。

 like even in your case of a trivially simple time bomb state machine。

This is because the event signals are used as indexes into the table。

 and it is difficult to avoid gaps in the numerical values of the signals。 For example。

 the event button released is not handling the current version of your time bomb。

 but it might be needed somewhere else in the system。

 and it is generally difficult to optimize the numerical values of signals for multiple state machines。

But perhaps the biggest disadvantage of state tables is that they discourage adding new states and events。

 because that requires adding the whole new column or a row into the table。

Developers perceive this as a lot of overhead， and therefore， they tend to avoid it。 Instead。

 they add internal state variables and guard conditions。

 which leads back to the spaghetti code and defeats the purpose of using state machines that were exactly intended to avoid the spaghetti。

In the next lesson， I will show you another state machine implementation strategy based on a reusable event processor that I consider most optimal。

If you like this channel， please give this video a like and subscribe to stay tuned。

 You can also visit statemachine。com/video course for the class notes and Project file downloads。

Finally， all the projects are also available in GitHub in the Quantum Lis Reository Moern embeddedd programming course Thanks for watching。



![](img/f4f78a8950f3378cb7f513cd97bda9a8_6.png)