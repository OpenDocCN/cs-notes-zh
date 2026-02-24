# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p22 -22-#21 Foreground-Background Architecture (_Superloop_).zh_en -BV1fRt2efEms_p22-

![](img/9bd7d41b414d26acf0049550194360b6_0.png)

Welcome to the Moern Emmbded Systems Program course。

I'm sorry for my long absence since posting lessons 20。

 but I'd like to make it up to you by announcing a new group of lessons about the architecture and design of embedded software。

Today I am going to introduce the ubiquitous foreground background architecture。

 also known as the Superlo or mainine+ interrupts。Apart from being interesting in its own right。

 foreground background is the starting point for all embedded software architectures。

 and among others， it is an important stepping stone to understanding a real time operating system。

 Arttos， which was perhaps the most requested subject for me to explain。

 so you can view this lesson as a prerequisite for the upcoming lessons about the Arts。

 as well as other architectures。To follow along today's lesson。

 you need to download two pieces of code from the companion website to this course at statemachine。

com/quixstar The first is the lesson21 project that I prepared in advance and the second piece is the QPC framework which you will use in most of the upcoming lessons in this group。

🎼You need to unzip these two downloads into the embedded programming directory on your disk。🎼，🎼Yeah。



![](img/9bd7d41b414d26acf0049550194360b6_2.png)

This lesson also uses the Ar Kyle MDK toolet from the Ar Company instead of the eclipse based code composes studio from Texas Instruments。



![](img/9bd7d41b414d26acf0049550194360b6_4.png)

The reason for this change is that I ran into problems with the latest CCS7。3。

 which was simply blocked by my antivirus software。

I made all sorts of attempts to reconcile the CCS with my antivirus， but I ultimately failed。

 This is among others one reason why this group of lessons took longer to prepare。In the end。

 I decided to treat the setback as an opportunity to introduce you to the third very popular and excellent arm Kyle MAT tool set。

 which is just as good as the IR tool set， and in my opinion， easier to use than eclipse。

To get KyleMDK， you can start from Arm。com and choose the development tools。

 microcrocontroller and Emed development menu。Alternatively， you can simply Google for KyleMDK。

Either way， you will land on this MDK page。As you can see in the comparison of available MDK editions。

 there is a free code size limited light version which will be perfectly adequate for all projects in this video course。

Click on the download button and fill out the usual download form， click the submitit button。🎼你。



![](img/9bd7d41b414d26acf0049550194360b6_6.png)

While you install the KM decayK tool set， you might want to familiarize yourself with a documentation。

 The toolet comes with the getting started videos and a guide in the PDF。



![](img/9bd7d41b414d26acf0049550194360b6_8.png)

So assuming that you have successfully installed Ar KyleM Dec toolet。

 you can go to the lessons 21 directory you have just downloaded and click on the provided Microvision project file。



![](img/9bd7d41b414d26acf0049550194360b6_10.png)

When you run the K Microvision IDE for the first time， you might need to register the license。

 which in my case is MDK light evaluation version， you can get this license online by clicking on Get license via internet。

🎼，🎼う。Also， the first time you open a project for the Tva Launchpad board。

 you might need to install the so called software pack。 You open the pack installer。

And select the Texas Instruments Tva C series TM4 C123X series packC。

 which includes your specific microcontroller。Okay， so finally。

 you can get to the code for today's lesson that is actually very similar to what you had back in lesson 8。

 in that it simply blinks that green LED on your TVVC launchpad board。

The only difference from the previous version is that delay function now called BSP Delay。

 because it is defining the board support package BSP， which you first encountered in lesson 15。

In this lesson， you will see how to take the concept of the board support package to the next level。

Before you go any further， let's just build this version of the Blinky program and check that it still works by opening it in the microvision debugger。

🎼When you run the program， you can see that the green LED blinks by staying on for about a quarter of a second and off for about three quarters of a second。

🎼。🎼Now， going back to the editing mode， let me explain a few things about the BSP delay function。

Unlike the previous crude delay implementation from lesson 8。

 BSP delay is based on the cystic interrupt， which delivers more precise timing because it does not depend on the speed of the compiler generated code。

In this new implementation， the cyst interrupt is programmed to fire at a rate of PSP tick per second。

 which is defined as 100 times per second in the PSP。 H header file。

This BSP second constant is subsequently used to configure the cystic interrupt。

The cysttic interrupt handleler simply increments the local L underscore tick counter variable。

 which is declared both static and volatile。The volatile qualifier has been introduced back in lesson 5。

 But here， let me quickly remind you that when you declare a variable to be volatile。

 you are telling a compiler that the variable might change unexpectedly。

 even though no currently performed program instructions change it。

 which is exactly what can happen when the variable is modified in an interrupt。

 the BSP underscore take counter function simply reads and returns the current value of L underscore take counter variable。

 But as you surely remember， from the last lesson 20 to avoid any array conditions between the cyst interrupt and the code that calls BSP take counter。

 the access to such a variable must occur in a critical section。 That is with interrupts disabled。

Finally， the BSP delay function first read the tick counter and stores it in the automatic variable start。

 Next， it enters appalling while loop， which constantly read the tick counter value and computes the difference from the start。

 The loop continues as long as the difference is smaller than the specified number of clock ticks。

 Please note that the twos complement arithmetic， which I discussed in lesson 2， handles properly。

 The discontinuity when the tick counter rolls over from all f's to 0。😊。



![](img/9bd7d41b414d26acf0049550194360b6_12.png)

![](img/9bd7d41b414d26acf0049550194360b6_13.png)

At the end of the day， however， the BSP delay implementation。

 just like the previous crude delay function， is based on the same primitive idea of polling。

 so it ends up wasting all the CPU cycles until the specified number of clock ticks  eapse。However。

 for this lesson， the most important point is that the software structure of the By program has all the characteristics of the so called foreground background architecture。

 also known as main plus ISRs， which is very common in smaller embedded systems。As the name suggests。

 the architecture consists of two main parts， the endless background loop inside the main function。

 and the interrupt handlers， likesistic handler， and possibly others， comprising the foreground。

The interrupts running in the foreground preempt the background loop。

 but they always return to the point of preemption。

The two parts of the system communicate with each other by means of shared variables like Altic counter。

To avoid race conditions due to preemption of the background loopbe by the foreground interrupts。

 these shared variables should be defined as volatile and must be protected by briefly disabling interrupts around any access to them from the background。

The timing of the execution of the various functions called from the background loop is not well defined because it depends on the time spent inside the loop that typically varies from one pass through the loop to another due to conditional branching in the code and interrupt activity。

 For these reasons， any the operations with strict time constraints cannot be reliably performed by the background loop and must be pushed to the interrupt level。

 running in the foreground。 However， they tend to make the interrupt longer and they might start to interfere with the background loop and with each other。

Still， due to its simplicity， the foreground background architecture is very popular in high volume embedded applications such as。



![](img/9bd7d41b414d26acf0049550194360b6_15.png)

Consumer electronics。Home appliances。

![](img/9bd7d41b414d26acf0049550194360b6_17.png)

Toys。Remote controllers。And countless others。

![](img/9bd7d41b414d26acf0049550194360b6_19.png)

Foreground background is also exactly the architecture used in various maker platforms。

 such as Arduino。Here， for example， is the Arduino version of the Blinky program。At the first glance。

 you might not recognize it as a foreground background because Arduino hides it inside its library。

But if you take a look at the main function inside the Arduino library。

You should immediately recognize the familiar background architecture consisting of initialization。

The setup function。And the endless loop。Repetitively， calling them loop function。

 note that the for loop with empty control is equivalent to the while1 loop and is a C language idiom that means for ever。

Aduino has of course also the foreground level consisting of interrupt handlers Here， for example。

 is the system clocktic interrupt service routine ISR。

 which increments some counters just like your cystic handler。There is also， of course。

 the matching polling delay， which is perhaps the most frequently used function in Arduino programs。

Now let's go back to your By background code and notice that you can still organize it a bit better。

For example， the initialization part is board specific。

 so it logically belongs to the board support package BP。

 So let's make a BSP in function inside the BSP module。Place all the initialization code there。

🎼And call it from Maine。🎼你。Next， notice that switching the LEDs on and off is also board specific。

 meaning that the code will need to change if you used a different board with LEDs attached to different pins。

Therefore， you should move this code to the BSP as well。Specifically inside the BSP module。

 you can create BSP functions to turn LED of various colors on and off。

Once the functions are defined。You can simply call them from the background loop。Of course。

 you need to add the prototypes of all the new BSP functions to the BSP header file。う。And finally。

 notice that now you can remove all board specific stuff from the main code。

 such as the MCU header file， the LED pin numbers etc。You can move all this stuff into Bsp。

c because your background loop no longer depends on any of these details。As you can see。

 the code compiles and links error free。The end effect is that your main code is completely insulated from the board。

 the background code only specifies what needs to be done while the BSP code specifies how to do it。

This way of separating concerns， the what from the how has many advantages。First。

 your main code is smaller and self explanatory。 You really don't need comments to understand what's going on。

The second advantage is that you could run this main code on a different board or you could use a different development tool chainin。

Of course， you would need to provide a different BSP implementation in the Bsp。c file。

 but you don't need to change a single line of your main application code。

It is even possible to run your main application on a desktop PC。

 which is not an embedded board at all。 Now， let's check experimentally where your By program spends the most of its time by simply breaking into the running code。

As you can see， the program stops in BSB tick counter function。When you inspect the called tag view。

 you can see that BSP the counterer is called from BSP De， which in turn is called from main。

At this shown location。In fact， you have almost no chance at all to find this program doing anything else than delaying its execution。

When you draw a flow chart of this background code。

 you can see arrows going backwards the flow of control。

These are the polling loops where the coat spends the most of its time， and therefore。

 they are shown with thick lines。I will call this type of code both blocking and sequential。

The code is blocking because it waits for events such as a timeult event after expiration of a delay in line and does not progress until the expected event arrives once the event arrives。

 however， the code naturally progresses directly to handling the event because the code downstream the blocking call provides the right context for the expected event。

The code is sequential because the sequence of expected events is hard coded in the sequence of instructions。

For example， the Blinky program expects a timeout event of duration of one quarter second after turning the green LED on and another timeout event of duration3 quarters of a second after turning the green LED off。

But it is also possible to arrange the background code differently in a non blocklocking fashion without thealing loops that busy wait for specific events to show this alternative。

 I make the sequential implementation inactive by surrounding it with pound if0 and pound and if。

🎼Now I add the new non blocking version of the backgroundground loop。🎼Yeah。🎼When you build。

And de back this version。🎼う。🎼是说。You can see that it blinks exactly as before。

But when you break into the code， you can see that it always stops inside the main loop rather than inside some other function。

When you look at the flow chart of the nonblocking background code。

 you can see that no errors in the flow chart go backwards。

 instead all arrows point forwards without blocking the main background loop。

 so the program spends the most of its time right in the main loop， as indicated by the heavy lines。



![](img/9bd7d41b414d26acf0049550194360b6_21.png)

Compared to the sequential and blocking version， the non blocking main loop spins hundreds of thousands times per second instead of only once per second in the sequential code。

This means that the main loop can handle events as soon as they arrive in order in which they arrive。

In other words， the non blocking code is driven by events， and therefore I will call it event driven。



![](img/9bd7d41b414d26acf0049550194360b6_23.png)

Of course， there is a price to pay for this increased flexibility and timeliness of such non blocklocking code。

 and that is the apparent higher complexity。The event driven code is more complex because the sequence of events this code can accept is no longer hard coded in the sequence of instructions。

By the way， the non blocking code is structured here as aaling state machine。

 This is unfortunately not the norm in the majority of real life projects。

 you will see rather convoluted and deeply nested E then else branching based on the value of many global variables。

 also known as the spagheti code or a big ball of mud。

I cannot go into details of state machines in this lesson about foreground background systems。

 but I promise to come back to state machines in several upcoming lessons actually。

 as they are fundamentally important in embedded systems programming。



![](img/9bd7d41b414d26acf0049550194360b6_25.png)

This concludes this lesson about the foreground background architecture。

 which is fundamental to understanding all other architectures used in the embedded software。

You saw that foreground background can be implemented either using the sequential paradigm with blocking or with the event driven and non blocking paradigm。



![](img/9bd7d41b414d26acf0049550194360b6_27.png)

![](img/9bd7d41b414d26acf0049550194360b6_28.png)

In the upcoming lessons， I will explore all these options。

 starting with the introduction to real time operating systems in the very next lesson。

If you like this channel， please subscribe to stay tuned。 You can also visit statemachine。

com/quistart for the class notes and project file downloads。



![](img/9bd7d41b414d26acf0049550194360b6_30.png)