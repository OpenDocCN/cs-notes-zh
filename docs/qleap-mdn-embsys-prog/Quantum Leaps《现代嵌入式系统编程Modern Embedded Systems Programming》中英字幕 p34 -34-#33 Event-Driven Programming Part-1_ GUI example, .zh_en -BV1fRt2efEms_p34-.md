# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p34 -34-#33 Event-Driven Programming Part-1_ GUI example, .zh_en -BV1fRt2efEms_p34-

![](img/0d15aa8d34846bab9d7eb6f8f532a488_0.png)

🎼Welcome to the modernern embeddedded System programming course。🎼My name is Miro Samak。

 and today I'd like to start the new segment of lessons about event driven programming。

 which is an important stepping stone in understanding modern software of any kind。

 not just modern embedded programming。In this lesson。

 you will learn the main concepts of event driven programming based on its origins in graphical user interfaces。

 which went mainstream during the personal computer revolution in the 1980s。

So the plan for today is to explain why graphical user interface abbreviated to GuI required a new programming paradigm and how this new paradigm known today as Evanrvan programming really works。

Specifically in this lesson， you will see the most important characteristics of evan drivenven programming exemplified by the original win32 API that was designed back in the 1980s and still works today even on the latest 64 B Windows 10。

With this background in the following lessons， you will see how these main characteristics of event driven programming can be applied to real time embedded systems such as your Tva C Lapad board。



![](img/0d15aa8d34846bab9d7eb6f8f532a488_2.png)

But let's start from the beginning。🎼Perhaps the most consequential from the programming perspective was the invention of the mouse in the mid 1960s。

 Well， this basically characterizes what we've been pursuing for many years in what we call the Auged Human Intellect Research Center at Stanford Research Institute。

 There's Don Andrews Hand and Menlo Park。And in a second。

 we'll see the screen that he's working and the way the tracking spot moves in conjunction。

With movements at that mouse。I don't know why we call it a mouse， sometimes I apologize it。

 started that way， and we never did change it。

![](img/0d15aa8d34846bab9d7eb6f8f532a488_4.png)

![](img/0d15aa8d34846bab9d7eb6f8f532a488_5.png)

But it took another full decade to work out the technical details of how to actually implement the ideas。



![](img/0d15aa8d34846bab9d7eb6f8f532a488_7.png)

This eventually happened at the Xerox Palo Alto Research Centre Park in mid 1970s。The mouse。

Is a pointing device that moves a cursor around the display screen。

Themon of the auto computer developed at Xerox Palo Alto Research Center around 1973。

 a selected window displays above other windows， much like placing a piece of paper on top of a stack on a desk。

Compared to command line systems of the day， such as a teletype or a terminal。

 the implementation of a graphical user interface required a paradigm shift。

Here is the main problem in a command line system。 the only input device is the keyboard。

 and the only output device is the bottom of the screen。

 which scrolls up like an electronic teletype。

![](img/0d15aa8d34846bab9d7eb6f8f532a488_9.png)

Consequently， as I am trying to illustrate in this piece of pseudocode。

 the software can still have the traditional sequential structure。Basically。

 the software waits for a key press， after which it echoes the character to the screen and then processes the key press。

 which might cause some more output to the screen。There is no question of where to produce the output。

 because it always goes to the bottom of the screen。But with a graphical user interface。

 the situation is fundamentally different For starters， you now have multiple sources of input。

 the keyboard and the mouse。

![](img/0d15aa8d34846bab9d7eb6f8f532a488_11.png)

This is a problem which I am again， trying to illustrate with a piece of pseudocoat。

If you explicitly wait for the keyboard， for example。

 you are unresponsive to the mouse input and vice versa， if you start with waiting for the mouse。

 you are unresponsive to the keyboard。So first， you need to find a way to somehow wait for multiple inputs simultaneously。

But assuming that you have done this downstream of such a blocking call。

 you now have to check which one of the multiple inputs has been actually received。Moreover。

 with a keyboard， you no longer know where on the screen the output needs to be produced for as you would have to know which part of the screen has been active。

 which is called the keyboard focus in today's Gui programming。But with the mouse。

 there are even more fundamental problems。 The mouse provides two dimensional input。

 So you have the X and Y coordinates on the screen。 plus the state of the mouse buttons。

But the row coordinates are not sufficient to take a meaningful action。

 You need to additionally know which object on the screen is at these coordinates。For this。

 you would typically call the service of the Goi system。

 But since this would happen for every mouse input。

 you could just skip the step and always let the goi system find the object at the current mouse coordinates。

This effectively means that the mouse can produce many more kinds of inputs。

 such as object I D in this pseudocode， All of them。

 depending on the constantly changing situation on the screen。

I hope that you start to see that graphical user interface introduces new levels of complexity。

 which are not in the same ballpark as the command line interface。 In fact。

 Goy programming is an entirely different ball game。Therefore。

 no wonder that goi programming required a different way of thinking。

 The key insight that enabled a workable solution was to focus on inputs。

 which are called events or messages such as the key presses。

 mouse moves and the secondary inputs from objects on the screen， like buttons， desktop icons。

 scroll bars， et cetera。The focus on events means that the events drive the software not the other way around like it was in the sequentially coded command line programs。

To see what this event driven paradigm really means and how it works。

 I've prepared a simple hell wind goy application running on windows。

You can download this project as lesson 33 from the companion webpage to this video course at statedmachine。

 com squistart。Once inside the project directory， I've just clicked on the Hello Wins S Llen solution file to open it in the Visual Studio 2019 Community editionition。



![](img/0d15aa8d34846bab9d7eb6f8f532a488_13.png)

If you wish to follow along， you can download Visuals Studio 2019 from the Microsoft website。

 The community edition is free after registration。

![](img/0d15aa8d34846bab9d7eb6f8f532a488_15.png)

But even though the development environment is quite modern。

 the software is written in sea using the ancient Windows application programming interface API。

 which Microsoft developed back in the 1980s。It turns out that unlike other more modern APIs in other programming languages。

 this low level132 API in C demonstrates the main concepts of eventrov event programming in their simplest and most direct form。

So let's just walk through the simplistic Windows application。

 which is my adaptation of the Hello Windows program from the book programminging Windows by Charles Peel。

This book， first published in 1988， became the Windows programming Bible back in the day。

The code begins with include Windows。 H header file that defines the Windows API types and constants。

Next， you can see a prototype of the W& D pro function。

 which will be needed to initialize a quote unquote virtual table。

 and which I will discuss in quite a detail in a minute。But first comes the win main function。

 This is the main entry point to a Windows Gui application and plays the same role as the main function in the conventional C environment。

 except in a Gui environment， the entry point takes more parameters because a Gui application is more complex。

Here in the simple H windows application， some of these parameters are not even used。

But next comes an interesting part where you prepare the window class to be registered with windows。

I've specifically formatted and commented the initialization so that you recognize that here you engage in a kind of object oriented programming。

 As I explained it in the last lesson 32 about O， P in C。So specifically。

 you first see the setting of the attributes of the window class instance， W and D。

 such as the window style， the mouse cursor for the window and the window class name。But next。

 you can hopefully recognize the assignment of a unquote virtual function。 The Windows procedure。

 wind pro specific for this Windows class。

![](img/0d15aa8d34846bab9d7eb6f8f532a488_17.png)

Here the Windows API designers use the simple implementation technique of embeddding a pointer to virtual function directly in the attribute structure。

 which I mentioned in my last lesson about object relateded programming in C。



![](img/0d15aa8d34846bab9d7eb6f8f532a488_19.png)

Next comes the call to Windows to register the Pre Windows class。And finally。

 the call to create window plays the role of the constructor because it creates a window object based on the just registered window class。

Once the application window is created， it is shown on the screen and updated。

 But then after all this initialization， the wind main function enters the event loop。

 also known as message loop or message pump， where the program performs their real work。

 This is the most important part of every event driven program。

The event loop has a very specific structure， consisting of two main steps。First。

 the call to the get message Windows API blocks and waits for any input from the keyboard mouse or the screen。

When any of such events occur， the Windows system recorded as a message object and places it in the message queue for this application。

Get message then unblocks and copies the message from the queue to the MG object。

 This is how the event loop solves the problem of waiting simultaneously for multiple events。

 as I tried to illustrate in the pseudocodeat before。If the state is returned from get messages 0。

 it means that the application has been closed。 And so the event loop needs to be terminated by executing the brake statement in this case。

Otherwise， the message is passed to the dispatch message Windows API。

 which then calls the window pro registered for the current window。

You will see the window pro for this simple H Win application in a minute。

 But before leaving this piece of code， let me summarize the key properties of the event loop。

The first key property is that an event loop uses special message objects to record all events potentially interesting to an application。

These message objects serve only for communication and can be conveniently stored in the event queue and later retrieved for processing。

Because of the message queue， events can be delivered both when the loop is waiting for them and when the loop is busy processing previous events。

In any case， the Windows system only records the event as a message and places it in the message queue。

 but does not wait for the actual processing of the event。

This type of event deliver is called asynchronous and means that event producer。

 which is the Windows system in this case， executes independently from the consumer of events。

 which is your application in this case。In other words， these two activities are asynchronous。

 meaning not synchronized。 Later in the session， you will see some experiments that will demonstrate this asynchronous nature event delivery。

The second property of the event loop is that the dispatch message call must necessarily complete and return to the event loop before the loop gets around to the next event。

This means that event processing proceeds in a run to completion RTC steps that cannot be interrupted by processing of any other event。

And the third key property of event loop is that it makes calls to your application code。

 the Windows pro。This is backwards compared to what you've been used to。

 because in all your previous experience with real time operating system， For instance。

 what you saw in lessons 20 through 26， your application was calling the services of the art。

 But now the event driven Windows system is calling your application。

This property of the event loop leads to inversion of control compared to the traditional sequential programming。

This is the key characteristic of all evanrovvin systems and is the essence of evanrovin programming。

 The inversion of control is really what it means that events drive the application and not the other way around。

So now let's take a look at the wind prock for this Gui application。First。

 to understand this signature， you need to see the declaration of the message structure that I skipped until now。

The MSG structure happens to be defined the Win user dot H header file。

 which is included from Windows dot H。As you can see。

 the types of the four parameters of the wind prock are identical to the first four attributes of the MSG structure。

I only took the liberty of renaming the first parameter from H W And D window handle to me to make it more clear that the Winpro is a member function of the window class。

 This is the naming convention for member functions introduced in lesson 30 about implementing classes in C。

Actually， as you saw in Win mainine， the windpro is not just a member function。

 It is a virtual member function that is specific to the type of the window class registered with Windows for this application。

I also took the liberty of renaming the second parameter of the wind prock from message to Sig。

 because this is the part of the message informing you about the kind of event that was recorded in the message in the modern Evanvanrvan programming。

 This information is called the signal of the event。 So I named it Sig。And finally。

 the last two parameters， W parameter and L parameter are the event parameters that provide additional information about the recorded event。

 The meaning of these parameters depends on the event signal。Inside the wind progue。

 the main job is to process the received message。 This requires to first determine what kind of the message you are dealing with。

For this， the Windows programmers use the switch statement based on the integer signal of the message as the control expression。

Each case statement then represents a different message kind that needs to be processed。

 according to that signal。The case statements are labeled with the symbolic names of various message signals。

 which are listed again in the Win user dot H header file。For example。

 the WM create signal corresponds to numerical value 1 and is sent to the wind prock when the window is created。

Similarly， W M destroy responds to numerical value 2 and is sent to the wind pro when the window is about to be destroyed。

 In the latter case， the windp calls the postqui message API。

 which inserts the W Mqui message into the programme's message queue。Which， in turn。

 then causes termination of the event loop。This is an interesting example showing you that an application can asynchronously post events to itself。

But in all cases， the windp also sets the local variable status that records the status of processing。

 For example， when windp handles a given message， it sets the status to when handled。

The status is then returned back to the Windows system， So there is the two way communication。

 Windows tells the windp which message to process， but then the windp reports the status of processing back to Windows。

Now， perhaps the most important message that Winrop needs to handle is the W M paint message。

 which the Windows system generates when it determines that part of all of the window needs to be repainted。

Your Hello Windows application handles this by painting some text in the center of the window rectangle。

The details of all this are not that relevant for to day。

 except perhaps to note that the painting displays the current values of the counters for keyboard presses and mouse moves。

What is more important， however， is that these counters are defined as static variables because they must outlive the many invocations and returns from the wind prock。

Notice that if you would define the counters as the local automatic variables。

 they would go out of scope by every return。Now， you might be curious where these counters are actually incremented。

So， here they are。The WMK down counter is incremented in the WMK down message。

And the WM mouse move counter is incremented in the WM mouse move message。In both cases。

 the processing must also include the call to invalidate API to tell windows that the window rectangle needs to be repainted because otherwise the new value of the counter won't be updated right away。

This is another aspect of the two way communication between the application code and the Windows system。

And finally， the default case handles all the message signals that the windpro did not choose to handle explicitly in one of the provided case statements。

In that default case， the wind pro calls the default Windows pro provided by Windows。

This is a very interesting design that has huge implications。

 because this is how the characteristic look and feel of the Gui system comes about。

To explain what I mean， let's just run this H Windows application and see what it can do。Well。

It turns out that the application has the usual window with the window bar and the title。

You can resize the window。You can move it around。You can minimize it。You can restore it。

 You can maximize it。But you have only explicitly coded the counting of mouse moves and keyboard presses。

Yet the application can apparently do all these other things as well and really looks and feels like any other Windows application。

 This is all thanks to the default window pro， which provides these other behaviors for you。

The default case in your we pro might not look impressive at all。But to appreciate it。

 you only need to scan through the hundreds of Windows messages defined in windus dot H。

Most of these W M underscore message signals go through your wind proc。

 and most of them are handled by the default Windows proc provided by Windows。Yet you。

 as the programmer， can be blissfully unaware about all this complexity。

 because all you need to know is a handful of messages that you actually handle。

A good way of thinking about this design is that it is layered in the order of hierarchy。

At the lowest level of the chier is your coat。 It has the first shot at every event because every event is sent to your wind prock first。

But when your code does not explicitly handle an event， it is not ignored， but rather。

 it is passed on to the window system， which is at the higher level of hierarchy。

The other names of this hierarchical design are the ultimate hook and programming by difference。

 These two names mean exactly the same thing， but emphasize the different aspects of it。

Ultimate hook emphasizes the ease of attaching or hooking up your coat to every event。

Programming by difference emphasizes the fact that you only need to explicitly program the differences from the default behavior。

But at this point， I hope you are starting to realize that you already saw something similar in the previous lessons 29 through 32。

 where you learned about object oriented programming。Specifically， with the O P perspective。

 you can view the design as a class hierarchy in which the Windows system is the base class with hundreds of virtual functions。

 one for each message signal， Windows applications such as your Ho win or Microsoft Word are then the subclasses that override the selected virtual functions in their Win pros。



![](img/0d15aa8d34846bab9d7eb6f8f532a488_21.png)

All right。 So this was a quick code review of a simple event driven Hello Windows Gui application。

 I hope that it gave you main ideas of how this programming paradigm works。



![](img/0d15aa8d34846bab9d7eb6f8f532a488_23.png)

But no introduction to e drivenvin programming would give you a correct understanding without contrasting it with the traditional sequential programming and the role of blocking within the code in particular。

And this is exactly what I'd like to briefly explain in the last few minutes of this lesson。

As an example of sequential programming， let me pull up some code from lesson 27 about their real time operating system。

 Arts。For instance， here is the sequentially coded Bki 3 thread。

 which blinks the red LED on the TVV C launchpad board。

So let's try to something similar in your event driven windpro。 For instance。

 let's say that you want to briefly blink an LED after pressing any key on your keyboard。

From the code review before， you know that the right place in the Winprock is the WM key down case where the keyboard presses are handled。

A traditional sequential implementation would be to turn an LED on and then wait。

 meaning block for say 200 milliseconds to actually see the blink and then to turn the LED off。

The Windows API actually provides an equivalent to the delay art of service， which is called sleep。

The Windows sleep API blockss and waits for the specified number of milliseconds。Also。

 you obviously don't have LEDs on your Windows computer。

 So instead you could just display the LED state as text in the center of your window。

As in all other cases， after changing the text to display。

 you would need to invalidate the window rectangle to force the repainting of the window。

After the sleep delay， you would change the LED text to off and invalidate the window rectangle again。

As the other state variables， the LED text pointer needs to be defined a static in a wind prock。

And finally， you need to augment the painting of the window。

By adding the LED text to the displayed string buffer。So now， let's simply build。

And run this programme。When you press the keyboard once， the LED state does not change as expected。

 even though the keyboard counter increments。 So your code for the LED does not work。

 as you imagined。But wait， it's getting worse when you press several keys in quick succession。

 The program freezes and does not update the keyboard counter immediately。

Then after a considerable while， the keyboard counter jumps all at once by some big increment。

Actually， when you press several keys。And also wiggle the mouse。 Nothing happens in the application。

 and no counter gets incremented until both keyboard and mouse counter jump by a big increment。

All this is obviously not good because the application appears frozen and unresponsive。 Also。

 the massive jumps in the displayed event counters are rather strange。

It turns out that the behavior is a consequence of asynchronous event posting and queuing of events inside windows。

The problem is that the sleep delay blocks the wind prock and prevents it to quickly return to the event loop。

When the event loop spins too slowly， the keyboard events accumulate in the event queue。

 Only when finally， all the WM key down messages with their blocking delays are processed。

 the event loop un clocks and quickly processes all other events。 Hence。

 the sudden jump in the counter values。This problem is well known。

 and Windows programmers have a name for it。 They call such an application a pig。 And believe me。

 you don't want to be a pig。The old rule of T for Windows programs is that if anything requires more than about 100 milliseconds。

 it should be broken down into shorter pieces by using events。

So this explains the lack of responsiveness and the freezing of your program。But remember。

 the LED update after key press events didn't actually work。

And the reason for that is even more interesting。From the event driven perspective。

 every blocking call in your code， such as sleep， really means waiting for some event to happen。

 Then the unblocking means that the event has occurred。

The event you get after unblocking might not be explicitly named， but still。

 it is delivered in the middle of processing of another event。 W M key down， in this case。

But this violates the run to completion semantics of event processing。

 which the event driven Windows system assumes。Quite specifically。

 they call to invalidate wreck right before the blocking sleep has no effect because the wind pro does not return back to windows at this point。

Therefore， Windows has no chance to send the W M paint message to the wind pro to actually update the LED state。

 Therefore， you never see the update。So as you can see。

 any use of the sequential programming paradigm and especially blocking is a bad idea in event driven systems for two reasons。

First， it clogs the event loop and destroys the responsiveness of the programme to all events。

 not just those that block for a while。And second， it violates the ranto completion semantics universally assumed in all event driven systems。

This is the most important takeaway from this lesson I want you to remember。

 Sequ programming and evanandering programming are two distinct paradigms that don't mix well。

 So always keep them separate。This means that in an event driven program。

 you need to use a truly event driven solution to implement your LED blink after key press feature。

To this end， instead of sequentially blocking with sleep。

 you can use the Windows facility specifically designed for this purpose called the timer。

 which you can set to generate a special event called Wium timer。

In the given number of milliseconds in the future。And this is really all you need to do in the WM key down case。

Because the rest of the processing then goes to the WM timer case。Of course。

 you need to finish the processing in the usual way with the only additional step to call kill timer。

 because otherwise the Windows timer will keep expiring periodically with the programmed interval。

Interestingly， in this case you use the W PR message parameter。

 which in this case holds the ID of the timer that generated the WM timer message。

So let's now see how this works。Let's first， start with isolated key presses。As you can see。

 after every key press， the LED changes its state momentarily to red and then off。 Now。

 let's try bursts of key presses plus wling the mouse at the same time。

You can see the LED status changes correctly and the event counters keep updating。

 so the application remains responsive。This concludes this quick introduction to event driven programming using GuI and Windows API as an example。

You have learned quite a few new concepts which are summarized here for you to be called event driven。

 a program must possess most of the characteristics listed in this chart。

 but perhaps the property that sets an event driven program most apart from a sequential one is no blocking inside the application level code。

I will come back to this issue in the next lesson where you will learn how event and programming applies to real time embedded systems like your Tiva C Lapa board。

 I hope you will join me for this fun。If you like this channel。

 please give this video a like and subscribe to stay tuned。🎼You can also visit statemachine。

 com s quickstart for the class notes and project file downloads。🎼。



![](img/0d15aa8d34846bab9d7eb6f8f532a488_25.png)