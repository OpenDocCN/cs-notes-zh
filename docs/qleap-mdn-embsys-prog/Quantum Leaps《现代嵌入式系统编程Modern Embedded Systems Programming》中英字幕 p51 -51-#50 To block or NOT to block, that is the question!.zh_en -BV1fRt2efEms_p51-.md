# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p51 -51-#50 To block or NOT to block, that is the question!.zh_en -BV1fRt2efEms_p51-

![](img/3423570510011c7fda851d7fa4a4108a_0.png)

🎼Hello and welcome to the modern embedded systems programming course。 I am Miroamec。

 and in this lesson， I'd like to explain why to block or not to block is the single most fundamental question determining the architecture of your embedded software。

 In fact， the issue of blocking is the most important discussion we can have in embedded programming。

 even though many embedded developers don't realize that。

Let me start by reminding you what blocking is and that it occurs in two forms。

 Bey polling and blocking through context switching as in a real time operating system， Arts。

 Besy polling， should be familiar to everybody， because this is how the introductory blink application is invariably coded。

 For example， here is the basic blink example from Arduino。

 The blink code heavily depends on the delay function。

 which happens to be the most frequently used function in all Arduino programming。

Its whole purpose is to wait in line for the specified number of milliseconds by blocking the progression of the code。



![](img/3423570510011c7fda851d7fa4a4108a_2.png)

Internally， the delay function is implemented as a busy polling loop。



![](img/3423570510011c7fda851d7fa4a4108a_4.png)

The same idea of blocking in line to wait for certain things to happen is also the fundamental feature of any traditional real time operating system。

 artist。For example， here is the blink functionality coded as an art's thread。Of course。

 the arts Vtaask delay function works internally entirely differently than the busy polling delay from Arduino。

I devoted the whole lesson number 25 to explaining the efficient blocking in an arts。Still。

 the purpose of the Arduino polling delay and Riarto's Vta delay is the same。

 And from your perspective， as the application developer， there is no difference in their behavior。

But why is that important。Well， because the ability to block and voluntarily weight anywhere in your code is considered the most valuable property。

 and it presumably simplifies your software development。 In fact。

 the ability to block is the main argument for using an art in the first place。 For example。

 here is an introduction to the P X 5 arts user guide。



![](img/3423570510011c7fda851d7fa4a4108a_6.png)

![](img/3423570510011c7fda851d7fa4a4108a_7.png)

In the section， why use an artus， you see the usual crit of the superlo called here control loop and the difficulties with scaling it up while maintaining the loop's real time response。

 But the really crucial argument is about blocking。For example。

 if process secondary task needs to wait for something such as an I O operation。

 blocking would clog the whole control loop and may adversely affect the timing of the process primary task。

In lesson 21， youll learn about the valuable software property called composability。

As long as the components of the superlo don't block， they are largely composable。

 meaning you can keep adding or removing them， and the loop will still work。

But the minute you introduce any form of blocking into any component， you destroy the composability。

Interestingly， the presumed workaround in this scenario is the necessity to create a state machine in process secondary task。

 which is seen as a complexity and overhead。But let me unpack this statement because suddenly mentioning the state machine is a legal thought that requires an explanation。

To understand why a steam machine might be needed， let's go back to the original Arduino blink example。

Here， the code description explains the blocking nature of the delay function and recommends checking out the By without blocking example to avoid blocking。

So let's go there and inspect a nonblocking code。This implementation centers around the Arduino millis function。

 which provides the current number of milliseconds and returns immediately without blocking。

If the expected weighting interval has elapsed， the code checks the LED state variable and depending on this state。

 select the desired new state of the LED。If you watch some of my previous lessons in the state machine segment。

 particularly lesson 37 input driven state machines。

 you should recognize this F L statement around the LED state variable as an improvised state machine。

 Unfortunately， the blink without delay state machine is not equivalent to the original blink。

 because it allows only one interval for both the LED on and off state。In contrast。

 the original uses two different blocking delays， so you can very easily use different intervals。

Anyway， for a clearer， reusable and equivalent example。

 lessons 21 provides the blinky input driven state machine calleded explicitly。

So that is an instance of a state machine that P X5 Art's user guide was talking about。

Without blocking， the code must necessarily return to the loop。

 but it must also remember what it was doing to find its way back next time。

This is what the state machine is for。Now， let's look at how an artist solves the problem of non composability of the blocking code。

 So the artist's approach splits the single control loop into multiple control loops called threads or tasks。

 Now， each such thread can block and actually must block， even if it didn't block before。However。

 the blocking does not interfere with the other functionality because they run in separate threads。

 Multile threads can voluntarily block and wait in line for multiple events in parallel。

I explained all this in the lesson segment about the arts。

 where you saw how the artes can juggle all these threads。

The critical element of the art's operation is that each thread maintains its own private stack and that stack maintains the context while a thread is blocked so that it can find its way back after unblocking。

So here is a summary of the embedded architectures discussed so far。

Simple superlos with blocking calls fall into the two block column。 They are intuitive。

 but they don't scale because blocking destroys composability。

One way to make a superlo extensible is to avoid blocking by restructuring each function in the loop into a non blocking state machine。

 whereas the input driven state machine variety is the most frequently used。



![](img/3423570510011c7fda851d7fa4a4108a_9.png)

Actually， the most commonly used are inrovvisised state machines， also known as spagheic code。

 but let's be charitable and assume developers are somewhat familiar with state machines。



![](img/3423570510011c7fda851d7fa4a4108a_11.png)

The other way of making the superlobe extensible is to use an artus。

 which allows you to create multiple superlos。This approach is definitely in the two block column as it doubles down on blocking。

 because every art thread， except the lowest priority thread in the whole system。

 must block for other threads to run。This general landscape of embedded architectures has existed since Artes became mainstream in the 1980s。

Consequently， most embedded developers believe these are the main and only games in town。

But this is no longer accurate。 In recent decades， more architectures and new approaches have been introduced。

 mainly in the not to block column。Basically， blocking is no longer considered as good or desirable as it used。

 and state machines， especially the modern event driven state machines。

 are not considered as bad or onerous。 Let me explain。Regarding blocking。

 one notable trend is that concurrency experts drastically restrict blocking in their art based designs by applying the event driven paradigm。

For example， the article managingaging Concurrency in complex embeddedd systems by Doctor David Cummings describes the event driven an architecture used by NASA JPL in all its Martian Rovers。

Cmming's paper recommends the event loop structure I introduced in lessons 33 and 34 of this course。

The event loop blocks only at the top and should never block afterward。

 Cming's paper describes various temptations to apply blocking and cautious to avoid it in all circumstances。

 So even though traditional artes such as V X works art used in the NAsA rovers are capable of blocking in any number of points。

 the experts advise to avoid that blocking。At least that is what they found to be critical for creating reliable mission critical software。

Now， regarding state machines， the constantly running input driven state machines are indeed a lot of overhead。

 but these are no longer the only option。 Event driven state machines， such as Ul state charts。

 run only when events are present and otherwise don't use the CPU。

These state machines beautifully complement the event loop and the active object design pattern I introduced in lesson 34。

 However， the innovations in the non blocking column do not stop there。 The obvious question is。

 why pay for the ability to block in an art's kernel and not to use it。😊，Well。

 there are much simpler and more efficient real time kernels that cannot voluntarily block。

 but don't require multiple stacks for threads。 either。

 Such kernels have been known and extensively used in the automotive sector。



![](img/3423570510011c7fda851d7fa4a4108a_13.png)

In the next lesson， I will present a simple， cooperative single stack kernel of this type。

 which is called Q V and is part of the Q P real time embedded framework。However， right after that。

 I will present a fully preemptive single stack kernel called Qque。

 which is also part of the QP Real time framework。 The preemptive Q K kernel is fully compatible with the rate monoatonic scheduling R M S s rate monoonic analysis RM A method introduced in lesson 26 in the artist segment。



![](img/3423570510011c7fda851d7fa4a4108a_15.png)

In fact， Q K is even more suitable for RM RM A than a traditional artist kernel because blocking is avoided。

 which vastly simplifies the real time analysis。

![](img/3423570510011c7fda851d7fa4a4108a_17.png)

In summary， the ability to block is the most critical defining characteristics of any embedded software architecture。

A traditional blocking art is still the dominant approach that this is changing。

 There is much more innovation in the non blocking architectures， and they are gaining more traction。

 especially in mission critical systems。

![](img/3423570510011c7fda851d7fa4a4108a_19.png)

If you like this channel， please like this video and subscribe to stay tuned。

