# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p40 -40-#39 State Machines Part-5_ Optimal Implementation in C.zh_en -BV1fRt2efEms_p40-

![](img/9f85a71d713c3de6c0ac4f708fc48e5e_0.png)

🎼Hello and welcome to the Modern Em System programming course My name is Mirosak and in this fifth lesson on state machines。

 I'd like to show you the state machine implementation in C that I consider optimal according to the criteria that I enumerate in the process you will see how to build a reusable event processor to include this optimal state machine implementation strategy directly in the microcaAO active object framework that you've been building in this segment of lessons。

🎼うんう。To allow you for a direct comparison with the other state machine implementations presented so far。

 today you will keep working with the same time bomb example you used before。

So let's start with copying the previous lesson 38 directory and rename it to lesson 39。

Get inside the new lessonson 39 directory and double click on the project lesson to open it in the microvision IDE。

To remind you quickly what happened so far in the previous couple of lessons。

 you've learned a few state machine implementation strategies in C such as the nest switch statement and the state table technique。

All of them had drawbacks， but they also had some promising features。 So today day。

 you'll explore the ways to mix and match the nice properties while getting rid of the drawbacks。

But before all that， to arrive at an optimal solution。

 it often pays off to start with first imagining what that ideal should look like。

 and then to work backwards to the implementation in a programming language like C in this case。

So let's imagine that you are inventing a domain specific language， DSL。

 not so much to implement state machines， but to specify them。

Such a DSL would then be a textual representation of the state machine diagrams。At this point。

 please don't even think of the C syntax。 Let's just try to specify your time bomb stain machine in the most clear and succinct way you can think of。

Well， in the state diagram， the most prominent elements you can see are states。

 so let's start with that。The first state is wait for button。

 So here is the simplest possible way you can specify it as text。

This state has an entry action that you can specify as the wordent followed by the actions。

 which you can simply copy over from the existing implementation in C。

The state has also an exit action that you can specify in the similar way。Finally。

 the state has a transition triggered by the button pressed event。

You can specify this by typing the name of the triggering event followed by the actions in C。

The state table implementation explicitly assign the state variable with the enumerated constant for that state。

 but this is neither the most concise nor it is consistent with your state names。

 So let's specify the transition with the word trend followed by the target state in parenthses exactly as it is in your diagram。

Next is the blink state， which you specify the same way。

You just follow your simple patterns for specifying the entry action。The exit action。

And a timeout transition。To pause。The past state has only any action， and no exit。

But the timeout trigger leads to a choice point with guard conditions。

 which you can copy over from the previous C code。Here you only need to change the transition specifications。

The last state is boom， which has only n reaction where it simulates an explosion。

So this would be the specification of the time bomb state machine。

 except that you still need to add the top most initial transition。

Here you can reuse the generic state specification because you can think of the initial transition as originating from the special initial pseudostate。

 the black dot。This black dot soda state has only one transition。

 which is not triggered by any event and which goes to state Wait for button in case of a time bomb state machine。

So here it is a domain specific language， DSL for state machines that you've just invented。

 such DSLs actually exist， and most of them are similar to your invention。For instance。

 there is a special tool called the state Ma compiler SMC。

 which provides an easy to understand language for state machines。

SMC then can translate that DSL into several programming languages， including C and C++。

So for a direct comparison， here is the same time bomb state machine specified with the SMC DSL。

As you can see， the general structure is remarkably similar with the states playing the central role and other internal elements like entry exit actions。

 transitions and guards， very similar to your DSL。The biggest differences are in the specification of actions because SMC does not allow you to use C directly。

I will get back to the SMC example later in this lesson because right now I have a bigger fish to fry。

The idea is exactly not to use a special compiler like SMC。

 but rather to add a minimal amount of syntax directly to your DSL to turn it into a legal C program。

So let's see what you can do。Well， the state specifications could be turned into C functions。

 This should make sense because the main job of a state is to respond to events by executing action code and executing code is exactly what functions are for。

The syntax of your DSL is already pretty close to a C function。

 The missing piece in the signature is the list of parameters。But here when you look at the actions。

 you can see that they need to access the me pointer and also you need the current event signal to determine what event you are getting。

 therefore the state handleer functions need the same parameters as the action handleers from the previous state table implementation。

But now， the presence of the me pointer indicates that the state handlers are not just any functions。

 Rather， they are member functions of the time bomb class， just like the action handlers were before。

The coding convention for member functions in C， which I introduced in the segment of lessons 29 through 32 about object oriented programming。

 requires to add the class name prefix to all the member functions， so let's just do that。

Please note that you need to add the prefiix also to the target states of transitions。And finally。

 to finish off the signature， the word state now corresponds to the return value from the state handler function。

 This could be the same status information used before for the action handlers as to what happened inside the handler。

So let's rename status to state so that the specification for a state reached exactly as you originally designed。

Allright， so now you need to adjust the syntax inside your state handler functions。For this。

 you can reuse the design from the nested switch statement technique you've learned back in lesson 36。

Specifically， each of your state handler functions now corresponds to a K statement at the first level of the nest switch。

The second level of the switch based on the event signal corresponds then to the inside of each state。

This insight structure is exactly what you need now， so you can just copy it over。

As far as the entry and exit actions are concerned， the nest switch technique didn't support them。

But they can be handled similarly， as you already did in the state table technique by means of the special reserved event signals。

 entryIig and exitig that are already defined in a microcaO header file。Putting this all together。

 this is how the internal implementation of a state handler function could look like。

But according to the signature， the state handle function needs to return the status information。

 For example， after handlinging an entry or exition， you should return the handled status。

But having multiple returns from a function is against some popular embedded coding standards。

 such as misrai。 So to avoid violating such rules， you can declare an automatic variable status。

 which you will then set in every case statement and return at the end of the function。

Here you need to be careful not to forget to return the ignored status when an event is not handled。

 you can do this either by initiating the status variable。Or by providing the default case。

I prefer to leave status uninitialized and provide a default case。

 because then the compiler could issue a warning if I forget to set the status variable in some cases。

This particular compiler will do this when you provide the minus W conditional uninitialized and minus W。

 sometimes uninitialized options。Which leads to the case where you don't yet set the status。

 That is when a state transition is taken。Here， the trend facility is perhaps the most interesting aspect of the design。

It is closely related to the internal representation of the state variable because transition means changing the state variable。

Previously， in all your state machine implementations。

 the state variable was an enumeration of states。But today。

 it must be directly related to the state handler functions because they are provided as the parameter to the trend facility。

Well， this is a classic use case for a pointer to function。

 which can point at different times to all the different state handler functions comprising your state machine。

So in your C code， you need to type dev the state handler as a pointed to function。

 which has the signature of your state handler function。

Now you need to move the state enumeration before the state handle type de。

And you also need to move around the type devs for time bomb so that they appear in the right order。

So finally， you can define the trend facility as a macro with a parameter target。

 which it would then simply assign to the state variable。

But it would be also nice if the macro could take on the value trans status so that you can directly assign this to the status variable like so。

This is possible by means of the C language comma operator。

 which evaluates expressions from left to right and takes on the value of the last expression。

So the following will assign the parameter target to me state。

 and it will also take on the value trend status， which is exactly what you want。

This completes the transformation of the wait for button state specification to a state handler function in C。

 so let me quickly apply the same syntax changes to all other states in your state machine。

In this special initial pseudostate， you can simply return the trend status。

The last problem is that the trend macro references the state handler functions that are often not yet known to the compiler because they are defined later。

You can easily fix this by providing the prototypes of all the state handlers right after the time bomb track。

This list of all state handler functions roughly corresponds to the previous enumeration of all states。

So now you can delete the previous state table based code， but before you do。

 just know that your implementation based on state handlers falls in the sweet spot between the action handlers that are too fine in granularity。

And the monolithic nested switch implementation。You also no longer need the problematic state table。

 which was often sparse and thus wasteful and discouraged developers from adding new states or new events。

 The state handlers are much more maintainable。But their greatest advantage lies in readability。

 because now the state handles directly represent the main components of a state machine。

 the states inside those states， you can very easily recognize other state machine elements such as entry。

 exit actions。😊，State transitions。And guard conditions。In fact。

 I really hope that you view the state handles as a domain specific language that works directly at the high level of abstraction of state machine elements。

 not the low level C instructions。

![](img/9f85a71d713c3de6c0ac4f708fc48e5e_2.png)

All right， but you are not quite done yet because you still need to adjust the dispatch operation from the previous lesson to work with state handlers rather than the state table。

First， change the type status to state consistently with your new definition。Next。

 change the type of prep state to state handler pointer to function。In the assertion。

 changed the check of the state variable to make sure that it is not zero。

 meaning that it is initialized。Now， in the call to the state handler。

 you just remove the indirect layer of the state table and all the indexing。

Your state pointer to function variable offers a faster。

 immediate access to the current state handler。 When the state handler reports that the transition has been taken。

You again adjust the assertion to make sure that the new state is valid。

And you again remove the interaction layer of the state table in the calls to the state handlers to process the exit of the previous state and entry to the new state。

Here， you cannot pass null pointers for events because your state handlers always de referenceence the event pointer parameter。

But instead， you can use the immutable static and con events with the reserved entry Sig and exit signals。

So you pass the exit event to the previous state handler and the entry event to the new state handler。

Finally， you need to change the handling of the initial transition because your initial state handler does not return the in status anymore。

Instead， for now， you just check if the event passed to the dispatch operation has the reserved in signal。

 and if so， you skip the exit from the previous state。

The state mission initialization aspect will be redesigning the next step。

 but for now you just want something that works。The last thing that you need to change is the initialization of the state variable in the constructor。

 here you set it to the initial pseudostate handler。Now， you can rebuild the project and。

What do you know， The compiler reports no errors and no warnings。By the way。

 let's check if the compiler notices an uninitialized case of the status variable。Well。

 it actually does。I am sure you are curious how it works on your TVC launchpad。

 so let's load it and test。Reet。Green light。Butotton press。5ive，4，3，2， one， boom。 It works。



![](img/9f85a71d713c3de6c0ac4f708fc48e5e_4.png)

All right， this is very encouraging， but you can still do much better than this。

Because as it turns out the dispatch operation for your new state handler implementation is completely generic。

 there is really nothing specific to the time bio state machine there。

 and the exact same implementation would work for any other state machine like， for example。

 Blinky or something much more interesting， so there is an opportunity here to improve the design and include a generic state machine management right into your microcaO framework。

Specifically， the current design is that your micro CAAO active object framework provides the active base class。

 which you then inherit in your application level classes like your time bomb or Blinky or other such classes。

So now you can exploit this inheritance to consolidate the common elements。

 like the state machine management shown in blue in the active base class to be inherited rather than repeated。

 This is exactly what inheritance is for。By the way。

 if you missed my lessons about object granted programming in C。

 inheritance is discussed in lesson 30。But you can go even smarter about it。

 You can create even more useful class hierarchy by adding the FSN for finite state machine base class。

 which then will be inherited by active and also indirectly by time bomb and blinky。

The advantage of separating FSM from active is that FSM can be then useful by itself for passive state machines that are not necessarily active objects。

 Such FSMs could be then useful， for example， inside interrupt service routines。Okay。

 this sounds like a plan， so let's try to code it。So the first set of changes will be in the microcao。

h header file where you need to declare the FSM class based on the time bomb class。By the way。

 this type of code modification， where you want to improve the design。

 but without really changing the behavior is called a refactoring。

The trans macro will require some changes， but let's leave it for later when the context will become clearer。

In sign the FSM base class， all you really need is the state variable typed as the state handler pointer to function。

As far as the member functions of the FSM class are concerned。

 the contractor will take the initial state headr in the specific subclass。

 such as time bomb initial。The init operation will execute the initial transition and also an end action to the first state。

The dispatch operation will handle all subsequent events。

Now we will need to adjust the active class to inherit FSM。

Here you no longer need to remember the dispatch operation because this will be handled by the FSM dispatch。

Instead， you need to adjust the signature of the active constructor to take the initial pseudostate just like the FSM constructor。

Okay， so let's copy the FSM class declaration and open the microcao。

c source file to add the implementation of this class。

Get rid of the unnecessary stuff and start defining the member functions。

The FSM constructor simply initializes the me state variable to the initial pseudostate。

Let's skip the in operation for now。And go straight to the dispatch operation。

Which you already implemented for the time bomb state machine。

The only change here is getting rid of the check for the initial transition because this has been redesigned and is now handled in the init operation。

Speaking of which the innate operation is similar to this patch。

 but it is simpler because after executing the initial transition。

 you can simply enter the new state。But to enter state。

 you need the immutable static and cont entry EVT， which is local to the dispatch operation to avoid duplicating this event。

 you can promote the immutable event to the file scopepe。

Now you need to adjust the active class constructor because active now inherits FSM。

 so the active constructor must call the FSMs constructor。And finally， in the active start operation。

 you need to adjust the initialization of the state machine。Here you call the FSM Init operation。

Whereas you can pass an null event pointer because the initial transition is not triggered by an event and this parameter is passed to the initial pseudostate handler only to conform with the state handler signature。

The previous generic dispatch via a point to function becomes now the specific FSM dispatch。

The framework update is now finished， so let's check whether the file microcao do C compiles。

All right， so let's move on to the time bomb implementation。

 which needs a few tweaks due to the framework refactoring that you just did。

You need to delete the type tabs that were moved up to the framework。

And you also need to delete the state variable from the time bomb class because it is now inherited from the active and indirectly from the FSM superclass。

The last change will be to the time bomb constructor due to the changed constructor of the active superclass here you need to pass on time bomb initial state handler instead of the deleted time bomb dispatch operation。

 and you don't need to initialize the state variable because this is already done in the constructors of the superclass。

That should be all， so let's try to compile the updated time bomb implementation。Well。

 the compiler complains about the T macro because it cannot find the member state in the me tract。

This is because now state is no longer a direct member of the timebone class。

 but rather it is inherited from the FSM super super class。

The remedy is to modify the trend macro to explicitly upcast the me pointer to the FSM superclass。

 As you remember from the lessons about object augmented programming。

 such upcasting is always legal and OP languages like C++ perform them automatically。

And as you are added， you also need to cast the target parameter to state handler because of the slight differences in the parameter list。

Specifically， the me pointer of all time bomb state handlers points to the time bomb subclass。

 whereas the state handler pointed to function type expects the me pointer of the FSM type of the superclass。

Okay， so after these final tweaks， the whole project builds cleanly。Of course。

 the first order of business now is to check whether your time bomb still works。Button press 5，4，3，2。

1， boom。 It works。All right， but as you already have your new state handler implementation in the debugger。

 I thought that you might be interested in quantifying the execution speed。

 especially because I claim that this method is optimal。For this。

 you might use an interesting feature supported by Yotiva C Cortex M4 processor。

 which allows you to measure the number of clock cycles taken by code execution。Specifically。

 the CPU has a hardware block called DWT data Watchpoint and tracece。

 where there is a cycle counter register。So here is how you can use it。After resetting the CPU。

 open the microcao。 C file and set a breakpoint at FSM dispatch。

 your goal will be to time this function。Now， run the code free and press the button。

The breakpoint is hit because you are about to dispatch the button press event to your state machine。

Open a memory view and point it to the address of the DWT at Hx E 00，0，10，0，0。

The cycle counter is the second word。 Click on it and type 0 to clear it。Now。

 step over the FSM dispatch call， the cycle counter regis is now hex D F。

 which is the number of CPU clock cycles it took。 This is 226 cycles in decimal。

Assuming 40 MHtz CPU clock， this is about 5 microseconds。

But more meaningful would be the relative comparison to the other state machine implementations。

So for example， I performed the same experiment for the same transition with the state table implementation from lesson 38。

 and it executed in about 206 cycles。This is only 10% better than state handlers。

 even though the table is generally advertised as the fastest because it avoids the switch statements。

As it turns out， the new state handler method is almost as fast while being much more readable。

 maintainable and significantly smaller in terms of memory。

 because you don't need the big and sparse state table。

The nested switch statement method from lesson 36 performed the fastest at only 146 cycles。

 but this version didn't support entry and exit actions。

 which are both present in the measured transition， so this is not really comparable。

I am unfortunately running out of my time budget for this lesson。

 but I still promise to show you the state machine compiler， S M C。

 as yet another state machine implementation technique。

So let me open the second project lessons 39 SMC that will be also included in the download for this lesson。

This second project contains fully functional time bombm for your TVC launchpad board with SMC。

The central piece of the S C project is the Timeba dot S M containing the timebon State machine specification in the S C domain specific language。

Frankly， to me， such a DSL makes little sense because the SMC language is still just textual representation。

 not really simpler or more expressive than the direct state handler based implementation in C。

I mention it here only because various DSLs and special compilers have been quite popular back in the day。

 so you should know about this approach。And the microvision ID offers your way to assign the preproces tool to such custom files here you assign the SMC compiler。

 which is including the project， The only requirement is that you have Java installed on your machine。

So now when you build the project， the SMC compiler is invoked and it generates the F time bomb underscore SM dot H and dot C。

These files are included in the project， so you need to refresh them in the editor。

So here is the C code generated by the SMC compiler。You can examine it by yourself。

 but it is obviously much more complex than the state handlers。

The SMC code is based on the object oriented state pattern with several classes。

 including every state being a separate class。There is also a special context class for managing the state objects。

Overall， the state parent belongs to the category of database strategies which tend to be complex。

In contrast， the state handlers belong to the code based strategies， which tend to be simpler。

This concludes this overview of the various state implementation strategies。 Of course。

 there are many more variants， but they all tend to be combinations of the basic techniques which you have just learned。



![](img/9f85a71d713c3de6c0ac4f708fc48e5e_6.png)

My clear preference and recommendation is the state handler method。

 because I consider it the most readable and maintainable with good performance。

 both in memory use and in CPU time。

![](img/9f85a71d713c3de6c0ac4f708fc48e5e_8.png)

That's why this optimal implementation is now built into your micro CAO framework。In the next lesson。

 I'll move on to the modern hierarchical state machines。

 which are perhaps the most powerful design tool I've ever used。🎼，If you like this channel。

 please give this video a like and subscribe to stay tuned。You can also visit statemachine。

com slash video course for the class notes and project file downloads。Finally。

 all the projects are also available on GitHub in the Quantum Les repository Modern and Medited programming course。

Thanks for watching。

![](img/9f85a71d713c3de6c0ac4f708fc48e5e_10.png)

🎼う。