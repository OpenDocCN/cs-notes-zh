# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p21 -21-#20 Race Conditions_ What are they and how to avoid them_.zh_en -BV1fRt2efEms_p21-

![](img/1166b4a453e69e17c3764fd1a7be68a1_0.png)

🎼，🎼Welcome to the Moern Emded System programming course。 My name is Miroseec。

 and in this lesson I'll finally tackle the subject of race conditions Today。

 you will learn what race conditions are， why they are dangerous and how to avoid them。

🎼To remind you quickly what happened so far in the last lesson。

 this course switched the development toolt to the Eclipse based code composeosr Studio。

The project directory structure established in the last lesson 19 looks as follows。

🎼The CS subdirecty contains the eclipse workspaces for the lessons of this video course。

 This directory was created by the code composer Studio Eclipse based IDdeE。

🎼The CMC subdirecty contains the Cortex microcrocontroller software interfaceface standard header files If you have not done it yet。

 you need to create this directory by unzipping the CMC's archive which you can get from the project downloads for this video course。



![](img/1166b4a453e69e17c3764fd1a7be68a1_2.png)

🎼Finally， you should have the lessonson 19 directory with all the code and the CCS project files。

 which you can also get from the project downloads for this video course。

🎼Of course you can have any other lessons in this directory as well。

 but for today you only need the three directories described so far。

🎼To create a new project for this lesson， make a copy of the previous lesson 19 directory and rename it to lesson 20。

🎼With eclipse based IDs， you typically cannot simply open the project by double clicking on it。

 Instead you need to first launch the Eclipse IDE and then import the new project。

 as I will show you in a minute。While launching code composes Studio。

 make sure that the selected workspace is CCS that I described before。



![](img/1166b4a453e69e17c3764fd1a7be68a1_4.png)

🎼After eclipse finally opens， it should contain one project called Lesson。

 which you created in the last lesson 19。🎼Before importing the new project for lesson 20。

 you need to delete the old one from the workspace because the new project will also have the same copied name lesson。

 an eclipse does not accept two projects with the same name。🎼When you delete the project。

 do not check the box， delete project contents on disk。🎼Now。

 you can finally import the copied project for lesson 20。 Choose file import menu and select。

🎼Existing project into Workspace。🎼Click next and browse for the lessonsson 20 directory。

🎼You should see the lesson project in the lessonsson 20 directory。

 click select All and the finish button。🎼At the end of all this。

 you should have the lesson project open in eclipse。

 but this time this is the new one corresponding to lesson 20。

🎼Let's first open the two source modules you have here， which are main。c and BP。

c and put them conveniently side by side。🎼The main code consists of the customary endless Y1 loop in which the green LED is turned on and off。

🎼The BSP code contains the Cyic handler interrupt service routine。

 which is set up to fire twice a second to toggle the blue LED。🎼For this lesson。

 let's modify the main code by commenting out the two lines which turn the green LED on and off by means of the special data bits array of GPIO registers that I have explained in lesson 7。

🎼Instead of using the data bits array today， you will simply use the data register。

 which controls all8 GP lines attached to the bits 0 through 7 specifically to set the desired bit you will read the data register logically or it with the LED green bit and then write the result back to the data register。

 You are doing all this not to distribute the other seven bits of the data register which control other things than your green LED By the way。

 if you don't remember how the bitwise operators work， please go back to lesson 6。

🎼To clear the desired bit， you will read the data register。

 logically end it with the inverted LED green bit and write the result back to the data register。

 I specifically used the lengthy way of writing these expressions to show you that the GIO bit is set or cleared by a read modify right sequence of operations。

 but these expressions can also be written more succinctly by means of the or equal and the end equal C operators。

 Please remember， though， that these short forms perform exactly the same read modify right sequence of operations。

🎼When you build and load your program with a TVC Lachpad board。

🎼You can see that it blinks the LEDs as before。🎼When you break into the code and single step through the main loop。

 you can see that the green LED is switched on and off， exactly as you programmed it。🎼Also。

 when you set a breakpoint in the cystic handler， you can see that it still toggles the blue LED every time it is called。

🎼So your program seems to work as before and an inspection of individual elements doesn't show any problems。

What's you not to like？🎼But if you watch the board for a while。

 you can notice that the blinking of the blue LED is no longer as regular as before。Specifically。

 sometimes the LED seems to pause for a whole second or even longer。🎼To find out why it happens。

 let's set a breakpoint at the line that turns the green LED off and open a few new debugger views such as disassembly and registers。



![](img/1166b4a453e69e17c3764fd1a7be68a1_6.png)

🎼Now let's single step through the code in assembly。🎼First。

 the address of the GPIOF data register is loaded into R3 and R2。

 and then the value of the data register is loaded again into R2。🎼Finally。

 the BIC instruction clears the green LED bit encoded as the immediate argument 8 in the R2 register as well。

 Please notice that all these machine instructions are generated from one short line of your C code。

🎼But before you execute the B I C instruction， let's trigger thes interrupt。 I mean。

 an interrupt can happen at any time。 So why not here。🎼To triggersistic。🎼Open the NVIC register set。

🎼Scroll to enVC in control。🎼Write one to the pen S T set field。And press return。

🎼Before you run the code， restore the core Reg's view and set some break points。

 place the first breakpoint immediately after the BIC instruction and the second in thesistic interrupt handler that way you will know which piece of code executed first you should be already familiar with this trick from the previous lessons about interrupts。

🎼Finally， you are ready to run the code by clicking the resumee button。

🎼You cannot single step because it will disable the interrupt。🎼Well， as you can see。

 the first breakpoint hit is inside the systemtic handler。

 so it must have executed before the other breakpoint after the BIC instruction。

This means the thesistic handler has preempted the previous code at this exact point。

🎼So now when you step to the Ci printerler code。🎼You can see that it turns the blue LED on。

🎼And then it returns。Back to the PIC instruction。🎼Now the BIC instruction clears the green LED bit in R2 and then stores the R2 in the GPIO data register。

Whoops。This last store instruction extinguishes both the green and the blue LEDs。

This is a problem because the code was supposed to turn only the green LED off and exactly not change any other GPI orbits。

🎼I hope you start to get a sense of what just happened here。

 The code that turns the green LED off is the sequence of read modify right operations。

 but the sequence was interrupted after the read， But before the write。

 the interrupt changed the state of the GO data register by turning the blue LED on。 However。

 the interrupted code was unaware of this change and still used the previous value of the GPO data register stored in R 2。

The problem that you have just experienced is called a race condition。



![](img/1166b4a453e69e17c3764fd1a7be68a1_8.png)

🎼It occurs when two or more pieces of code that can preempt each other access a shared resource in such a way that the result depends on the sequence of execution of these pieces of code。

 Of course， in a toy blinking example， such a race condition is not a big deal， but it can be。

 in fact， a deadly bug。Imagine， for example， that instead of just toggling the blue LED。

 the cystic interrupt switches on a cooling system in a nuclear reactor to prevent the reactor from overheating。

🎼In this case， the cystic interrupt has just turned on the cooling system。

 but the main loop turned it off again， just a fraction of a microsecond later。

The result is that the cooling system remains off when the reactor melts down。🎼With this in mind。

 I hope you start to see why race conditions can be a problem。

 but I'm not sure that you fully appreciate how nasty they can be。

The problem is that race conditions seem to defy logic in the sense that each individual piece of code works correctly。

🎼The problem only occurs when the pieces of code are executed together and preempt each other in various places over which you have no control。

🎼This results in bugs that tend to be intermittent， hard to reproduce and hard to isolate。

 as typically there are only narrow time windows when preemption leads to bugs。

This means that you might be testing your system for hours or weeks。

 never noticing any problems still， some catastrophic race condition bugs might escape to the final product。

All this makes race conditions the worst possible kind of bugs you ever want to deal with。

They are the direct consequence and a huge price for using interrupts。

It seems that nothing good in life， not even interrupts， comes for free。

🎼So now that I have sufficiently scheduled， I hope I'd like to discuss two main strategies of eliminating race conditions。

 The first strategy is based on the concept of mutual exclusion。

 which means that you make sure that only one piece of concurrent code can execute while accessing a shared resource。

🎼In the case of your Blinky program， you can implement mutual exclusion by simply disabling interrupts around turning the blue LED on and around turning it off。

🎼This will preclude preemption by the cystic interrupt and will eliminate the race condition。

🎼Let's quickly take a look at this modified version in the debugger。🎼First。

 the intrinsic function disabledable IRQ generates just one machine instruction， CP IDI。

🎼There is no function call overhead here， which is the beauty of using intrinsic functions。

🎼Similarly， En IRQ generates also one instruction CPIeI。

🎼Both these instructions execute in just one clock cycle。

 so the additional overhead of disabling interrupts is really small。🎼By the way。

 the section of code between interrupts disabling and enabling is called a critical section。

🎼So now let's repeat exactly the previous test of triggering the cystic interrupt and setting the break points to find out the order of code execution single step up to the BIC instruction。

🎼Trigger the cystic interrupt in the NVIC。🎼Set a breakpoint just after the BIC instruction。

🎼And another one in the cystic handler。🎼Run the application by clicking the resumesume button。

As you can see， this time the cysttic did not preempt the main code。

 but instead the breakpoint at the SDR instruction was hit。🎼However。

 the cystic interrupt is not lost。🎼It fires as soon as the interrupts get enabled。

🎼When you single step with the interrupt code， you can see that it turns the blue LED on。

The interrupt then returns back to the main code at the top of the loop。🎼In summary。

 the introduction of critical sections serialized the access to the shared resources。

 the GIO data register in this case， and made it atomic， meaning indivisible。

 with critical sections in place， the three pieces of code， the system interrupt。

 and the two critical sections can run either before or after each other， but not in the middle。

 This is what mutually exclusive access means。🎼But even better than mutual exclusion is to avoid race conditions by not sharing any resources in the first place。

🎼So let me comment out today's code to leave it there for you to experiment。

🎼And revert to the original code。🎼This original code does not use the data register。

 but instead it uses the data bits array of 255 GPIO registers。

🎼I have devoted almost entire lesson 7 to explain how this array of GPIO registers works。

 so I won repeat it here。🎼But the main point for today is that the array provides a separate register for every possible combination of the8 GPO bits。

 so the registered data bits LED green is different than the register data bits LED blue。

 for example， This means that there is no sharing of the common data register。

 and as you will see in a minute in this assembly， there is no need for the read modify right sequence either。



![](img/1166b4a453e69e17c3764fd1a7be68a1_10.png)

🎼Setting a given bit is accomplished by a specific atomic right to the dedicated data bits register。

 and so is clearing of a given bit。🎼So now you'll finally understand why the hardware engineers at Texas Instruments have designed the GIO registers in this peculiar and complex way。

 They did it exactly to separate the various GIO bits to avoid the need of sharing them and thus eliminating potential race conditions in the software。

 These folks did the heavy lifting in hardware so that your life as the software designer can be easier。

🎼This concludes the lesson about race conditions in the next lesson I will talk about prioritizing interrupts and about other ways of disabling interrupts on the arm cortex and processor。

If you like this channel， please subscribe to stay tuned you can also visit statemachine。

com/quistart for the class notes and project file downloads。

