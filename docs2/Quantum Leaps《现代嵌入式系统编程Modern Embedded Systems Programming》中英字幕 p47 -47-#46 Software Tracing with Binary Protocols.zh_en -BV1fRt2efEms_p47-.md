# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p47 -47-#46 Software Tracing with Binary Protocols.zh_en -BV1fRt2efEms_p47-

![](img/efb9446db7914b7d37d7d9858b2b8182_0.png)

Hello and welcome to the modern embedded systems programming course。 My name is Mirosak。

 and in this lesson， I'll continue the subject of software tracing Today。

 you'll see a mature software tracing system called Q P Spy。

 which is much more suitable for real time embedded software than the primitive printf debugging from last time。

😊，As usual， let's get started today by copying the previous lesson 45 to lessons 46。

 get inside the lessons 46 directory and double click on the project lesson to open it in the microvision IDE。

To remind you quickly what happened so far， in the last lesson。

 you added the Myprint F instrumentation to your code to generate some real time information about the code execution。

The print of software tracing seems to do the job and everybody uses it。

But the approach is very intrusive。 For example， this simple printout took almost 800 microseconds。

 and the overhead occurred in the interrupt context。

These three simple printouts produced in quick succession， took over 3 milliseconds， and again。

 they occurred in the time critical path through the code。

So while s tracing is immensely useful and indeed indispensable。

 print F style tracing is not the smartest way to go about it。

The main problem is that this approach combines the production of the tracing data and sending it out over you art the ITM or some other mechanism。

 which is very time consuming。To help you realize what's happening here。

 imagine a fire truck racing to an emergency。 This would correspond to your time critical path through the code。

But instead of fighting the blaze and rescuing the victims。

 the fireman starts filing a situation report to his boss， which takes him an hour。

 This is what software tracing is and how a millisecond feels to a modern CPU。

To make it even more ridiculous， the report that the fireman is producing is not in his native language。

 like， say English。 No， the report is in a foreign language such as Chinese。

 So the poor fireman must painsistinkingly translate every word。

This is how it is for the CPU to produce a foreign human readable print F output formatted into ASI characters as opposed to the native binary format。

All this seems ridiculous， but this is precisely what happens in the print F method。

Please note that the report itself is not the absurd part。

 We all understand that the report is useful， just like self retracing is。

But it is foolish to do this when something much more urgent needs attention。

A better solution would be for a fire fighterighter to wear body cameras to capture the details with minimal distraction。

 Then later， after the emergency， the fireman could inspect the recorded footage and submit his report。

And， of course， the report should be in the native language of the fireman so that he won't waste his time on translation。

This analogy lays out the general structure of a more reasonable software tracing strategy。

The tracing information should be recorded quickly in native binary into a memory buffer inside the microcontroller。

 This takes only microseconds， which is important because it happens in the time critical path through the code。

 On the other hand， the slow process of sending the tracing information to the host。

 which takes milliseconds， must be decoupled from recording the tracing data and occur when the CPU has nothing else to do。

To this end， most real time colonels have a notion of an idle thread。

 which you first saw in lesson 25 about the artis。The scheduler performs a context switch to the idle thread when all application threads have done their job and are waiting for more work。

This is the ideal place to send the tracing data to the host。All right， with this introduction。

 let me show you a real time software tracing system called QP Pi that works as I've just described。

I will start by replacing my printf with QP pie and then demonstrate how the whole system works。

 After this， Ill peek under the hood to explain the main elements。

The QP by tracing is already built into the QPC framework you've been using for several lessons。

 so you don't need to include any additional header files。

But just like in the simple tracing system from last time。

 the QP pie instrumentation is normally inactive。 You typically activate it only in the spi built configuration introduced in the previous lesson。

 Similarlyly as last time， you need to define a preproces macro to activate the instrumentation。

 In this case， the macro is Q underscore piei。Now， you need to replace the my print of macros with a Qs by equivalence here。

 you no longer use the format string because you insert the raw binary data directly into the internal memory buffer by calling it the appropriate macros。

For example， to output a string， you use the macro QS underscore STR and to output an U in8 T value。

 the macro QS underscore U8 other macros of this type are available for other data types。

The whole trace record， as it is called in Q S， is surrounded by the macros， Q S。

 begin I D and Q S N The parameters in the Q S begin I D macro are used to for run time filtering。

 which Ill explain later。All right。 so now I just replace all the other my print of instances with the equivalent Qs trace records。

The next step is the board' specific code for software re tracing initialization and sending the data to the host。

This is equivalent to their last lesson board specific My print F in it， and F put C implementations。

Here， I delete the print F code and paste the new Qpi code。

The most significant difference in the code for Qspi is that you must provide the tracing buffer in Rem。

 which you then pass to the Qpi function Q S in it buff。Also。

 compared to the simple print F from last time， Qespi provides more functionality。 For example。

 Qpi implements data input for receiving commands from the host。

 This also requires a small buffer in ran A you are interrupt to timely handle the received data and the callback functions to handle the target reset and various commands。

Additionally， QPI provides a precise time stamp based on a hard retirementr。

 which you need to initialize and read in the QS callback function。As I explained before。

 the most time consuming job of sending the tracing data to the host should be done in the idle thread of the underlying real time kernelel。

In this case， you are using one of the built in kernels in the QP framework called QV。

I will explain this and other kernelels in the future lessons， but for now。

 it's only important that Q V also supports the idle callback。

So you place their code similar to what you used for sending bys over the you art in the last lesson。

 The critical difference is that now you only send the bys when the you are this ready。

 and you no longer busy wait for the you art to become ready。

Because now you access the UA registers in the idle callback。

 you need to move the definitions of the registers and data bits to the top of the file。Finally。

 you need to replace the Myprintf in it macro with QS in it。

 and to actually see your user defined trace records。

 you need to enable them in the QS global filter。So this is about it for the BSP dot C file。

 So let's try to build the project。The compilation error is about the old my print F tracing that was still inserted in the main C file。

But this file has been automatically generated by the QM modeling tool。

 So let's make the changes in the model and regenerate the code。For that。

 you can go to today's lesson 46 folder and double click on the Timebo。

qM model file to open it in QM。Next， you double click on the time bomb class and open the state diagram once there you click on the boom state and add the QS trace record to the entry action。

Finally， you regenerate a code。Close QM。And reload the changed main C file in the microvision editor。

When you try to build the project now， you still get errors。

 but these are linker errors about missing Qpi facilities。To fix that。

 you need to add Qs by source code to your project。The simplest way is to create a new group。

Name it QS。And add existing files to it。The files are located in the QPC framework。As our C folder。

Q S subdirecty。You need to select all the files there。As you are added。

 the Q S group is only needed in the spy belt configuration and should not be included in the debug belt configuration。

 Here is how you can do this in the microvision IE。

 You need to switch to a given configuration like DBG in this case。 right。

 click on the group and open the options for group pop up menu。

And uncheck the box include in target build。Notice that the Q S group icon and all files in it have a red adornment to show that they are excluded from the DBG belt configuration。

But that embellishment disappears when you switch back to the spy configuration。All right。

 then try to build again。And what do you know， the project builds cleanly。

Let's download this to your TV C Lapaboard and first see how the tracing output looks in the generic serial terminal。

 the same one you use in the last lesson with myprint F。Well， there is clearly some output produced。

 but it looks like garbage in the standard serial terminal。Actually。

 you should have expected that because the QsP output is in binary， not in a human readable format。

To correctly parse the binary Qespy data and display it in human readable format。

 you need a special program called Qespi， which is similar to a standard serial terminal act like termite。

You can get it from Quanum Lis GiHub， the Ks repository containing Cuesp and other useful software tools。

 The prebuil executables are available in the releases section where you can download Cus for your host operating system。

Assuming that you've downloaded release for Windows， go to the directory where you've unzipped ks。

Step into the bin subdirecty。And。Copy the path through the clipboard。Now。

 close this standard term terminal and open a command prompt。

 type C and paste the cuts bin directory。

![](img/efb9446db7914b7d37d7d9858b2b8182_2.png)

Finally， type Qs by minus C Com port number of the virtual comp of your TVva seaboard to find out which comp port that is。

 you can open Windows device manager。Now， reset the board and watch the output produced in Qspi。

Press the SW 1 switch and watch the time bomb count down， and finally。Explode。As you can see。

 the Qs spi tracing output is equivalent to that produced before with my print F。

 except now you have additionally a precise time stamp of each Qpi trace record。

But the true advantage is in the real time performance of the Qpi tracing。 to illustrate that。

 let's use the logic analyzer， but to get more information。

 let's add toggling of the test pin to the code。

![](img/efb9446db7914b7d37d7d9858b2b8182_4.png)

Specifically inside the cystic handler ISR， turn the test pin1 high right before the Qpi trace record and turn it back low right after。

Please note that the test pin 0 is already turned high upon the entry to the ISR and turned low upon the exit。

Rebuild the code。And reow the board。Reset the board and watch again the ksP output。

Press the Sw1 button， and watch the output。In the logic analyze analyze view。

 zoom out and find the clockctic that produced the SW1 trace record。

 You can recognize it by the spike on test pin1。Now I zoom in and measure the total cystic ISR execution time on test pin0。

 which is 13。2 microseconds。Out of this， the generation of the Q sp trace record took 8。

8 microseconds。This needs to be compared to the same S W1 button change output produced by printf。

 which took 0。799 milliseconds， which is 799 microseconds， almost 100 times longer。All right。

 so the microsecond level real time performance of the cu by tracing means that the approach is indeed much less intrusive on your system than printf。



![](img/efb9446db7914b7d37d7d9858b2b8182_6.png)

But this is just the tip of the iceberg of the Cupi capabilities， because thus far。

 you have only seen your own tracing instrumentation added in the form of application specific trace records。

However， the QP framework also has its own internal instrumentation that produces the predefined trace records。

 which are even more efficient than the application specific records。You see。

 software tracing is particularly powerful in combination with the event driven paradigm because of the inherent inversion of control。

 Just think about it。 an event driven infrastructure such as the QP framework controls the application。

 not the other way around。This means that almost all interesting interactions in the system must go through the framework。

The framework is then like a funnel， providing an obvious opportunity to be instrumented to output detailed tracing information about the application's behavior。

This is all without any tracing instrumentation of your application code。Of course。

 this is not entirely new and traditional artistes have been instrumented for tracing applications as well。

 but an artist does not work on the principle of controllingversion。

 so it can only provide information about tasks， semaphos and other such blocking mechanisms。

In contrast， an event driven framework knows about event driven elements such as every state machine in your application。

This is something that an artist doesn't know。In fact。

 let me just demonstrate the tracing of state machines by enabling the pertaining predefined trace records inside QP。

Rebuilt the project。Louded onto the board。Open Cusp as before， and press reset。



![](img/efb9446db7914b7d37d7d9858b2b8182_8.png)

Next， press SW1。As you can see， the tracing output still contains the application specific user records。

 but now it also includes the new trace records such as dispatch， SD the exit， ST entry， Tra， etc。

These are apparently state machine activities， but the associated data is rather cryptic。

 although you should recognize the RA and wrong memory addresses。Well。

 this is the native binary information and from the embedded board to present the data more user friendly。

 the AcP software system needs symbolic information just like a traditional single step debuggger。

Obviously， this problem is not specific to Qpi， and most software tracing systems have to solve it one way or another。

A few approaches that I found are based on extracting format strings from the tracing instrumentation in the source code。

 For example， the software tracing system called Tice uses a special precomped tool written in the go language to modify the tracing macros in the source code and to extract the format strings。

That information is subsequently used in the Trid host utility。

 which then performs printf like formatting on the host machine。

 Another realtime tracing approach presented at the recent CP now conference also extracts format strings from the tracing instrumentation。

 but applies modern C+ with templates and tools written in Python to extract the strings and replace them with hash values。



![](img/efb9446db7914b7d37d7d9858b2b8182_10.png)

![](img/efb9446db7914b7d37d7d9858b2b8182_11.png)

The main problem of such approaches is that the external symbolic information must be generated and then preserved from each and every software rebel。

 The need to match the symbolic information to the exact version of the code executing on the target is a big logistic problem in itself。

Therefore， Cupi takes a different approach in which the symbolic information is generated by the target。

 so it does not need to be generated externally by some precomped tool and can never go out of sync。

Thecuspi approach becomes clear when you take a bit closer look at thepi output。

You should recognize two types of addresses。 First， are addresses starting with hex 2。

 These are Ram addresses of objects， like your time bomb active object。Second。

 are addresses starting with Hex 0。 These are ro addresses of code。

 such as your state handler functions。Finally， you also see event signals as smaller indigent numbers。

All that means that if you can provide the mapping between the addresses and symbolic names in your code。

 the CuP host application should be able to display the symbolic information instead of the raw binary addresses。

And this is exactly what Cuspiy allows you to do by providing the so called dictionary trace records。

First， are object dictionaries that produce symbolic information about the addresses of objects。

 For example， here is the object dictionary for your AO time bomb active object。

Please note that AO time bomb is a pointer already。

 so you don't need to use the address of operator to obtain the address of the object。

Second are signal dictionaries that produce symbolic information about the event signals。

 They take two parameters， the signal enumeration and the address of the associated state machine。

 because signals can be in principle state machine specific。

 The letter pointer can be 0 for global signals。And finally。

 function dictionaries provide symbolic information about your state handler functions。

 You can type them manually like the other dictionaries。

 but they can also be generated automatically by the QM modeling tool when you check the Q as fund dictionary box in the state Ma property editor。

After regenerating the code and updating it in the microvision editor。

 you can see that QM added the function dictionaries in the topmost initial transition of your state machine。

So this is about it as far as the most essential dictionaries are concerned。

 And it wasn't that difficult， was it。All right， so now let's rebuild the code and load it onto the board。

When you reset the board now， you can see the dictionary trace records produced。

And you can also see that most of the raw hex values are now replaced by the symbolic names from the dictionaries。

This is all useful information， but these are still not all the predefined trace records in the QP framework。

 So let's enable all of them。As usual， rebuild。And download the code onto the board。

Reset the board now that all trace records are enabled， you see the high frequency tick。

 but that is a bit too much to disable just that one specific trace record。

 You need to first find out which predefined record that is。



![](img/efb9446db7914b7d37d7d9858b2b8182_13.png)

Once you know that， you can use the same QS global filter API， except for disabling a record。

 you use a negative value like so。After the reset， you no longer see the tick trace records because they have been filtered out。

But the trace now contains more information， although evidently。

 some object dictionaries are still missing。These are the trace records related to the internal time event inside the time bomb active object。

By now， you should be able to provide that missing object dictionary。 So I leave it as an exercise。

Instead， in the last segment of this lesson， I'd like to explain what really makes the Cup software tracing tick。

 And that is the internal binary data protocol。 Let's start with harvesting the raw binary data precisely as they as sent from the embedded board for that。

 it is convenient to start the cup utility in a directory where you wish to store the data。

 For example， a temporary directory on your disk。Now， after relaunching Qpii。

 you can type H on your keyboard to see the quick help of the keyboard shortcuts。

Will use two commands as for saving the binary data and O for saving the screen output。At that point。

 Cuspi opens two files in the working directory， whereas the base names are generated automatically from the current date and time。

Now you can reset the board and press S W1 button to collect the trays。



![](img/efb9446db7914b7d37d7d9858b2b8182_15.png)

After that's done， you type O and S again to toggle the collection of screen output and binary data respectively。

So here is the raw binary data。And here， the corresponding human readable screen output。

It's interesting to note the sizes of these filess of 3 and 10 kB， respectively。

This means that the binary data represents a natural compression of the tracing output by a nontrival factor of over 3。

In other words， compared to the formatted ASI data， like in the print method。

 you can send three times more trace information in binary。

But that's not the only advantage of the binary format。In addition。

 the binary protocol can detect errors and gaps in the data。To simulate an error。

 I will delete a by somewhere in the captured binary file。

This corresponds to dropping a by in transmission。Now I exit Qspi by pressing X and relaunch it with the minus F command line option with the file name of the binary data。

This means that Cusp will read the input from the file instead of the comp port。

When I ran Cusp in this playback mode。It reports bad checkum error and data discontinuity from sequence 60 to 62。

Which means one missing trace record with sequence number 61。

 If you would like to learn more about the Cuplay data protocol。

 it's described in the online documentation I keep referring to in this video。

 A link to the documentation will be included in the video description。But to summarize here quickly。

 this is an HDLC type protocol that allows instantaneous reynchronization after any error to minimize the loss of useful data。

You just saw this in the example where only one damaged record has been dropped and the receiving Q sp was able to immediately find the next correct record。

As far as the embedded side of the tracing implementation is concerned。

 the crucial property of the Cupi binary protocol is that it allows the data to be removed from the internal buffer in any chunks entirely independently from the record boundaries。

 Still， the receiver is able to immediately find the individual records and parse them correctly。

That concludes this lesson about software tracing suitable for real time applications。

 The subject is vital because embedded systems are very opaque by nature。

 and it's difficult to know what's going on inside。 Of course。

 I could only show the most basic features of the tracing system as it can do much more。 For example。

 software tracing can be a cornerstone of testing embedded code。 Also。

 you can use it for monitoring your embedded devices via a remote host based user interface。

If you like this channel， please give this video a like and subscribe to stay tuned。

 You can also visit state machine slash video course for the class notes and project file downloads。

🎼Finally， all the projects are also available on the Github in a Guum Les Reository Mo embedded programming course。

 Thanks for watching。

![](img/efb9446db7914b7d37d7d9858b2b8182_17.png)