# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P12：-12-Promising semantics (1_2).zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

So in the previous lecture， we discussed that there are two major sources of non determinism in the。

In the semantics of conquered programs。The one is the threatening to a living。

 The execution of multiple stress are interlived with each other。

And the order of the execution introduces nondeminism。

And the other major source of magnetatomism is the redering。Inside the thread。

 multiple instructions may be ordereddered are resulting in what is called to relaxed behaviors that would be impossible with only inmipans but made possible by the reodderings。

And in the previous lecture， we also discussed that we need to find the semantics。

 the good semantics for such relaxed behaviors in order to reason about the current programs。

In this lecture， we are going to study what is called the promising semans， which is。

 I believe the the。Best of each kind。 And the state of the art。Athmantics for concurren programs。

So this is actually made by me and in three years ago。

 I published a paper that is called Promising Smantics for Re Mecurrency。

 which defines the relaxed memory concurrency semantics for C and C++ or rust programs。

So let me tell you a little more about this promise semantics， because it will。

 its semantics will be the basis for the or the other。All the constructions of concurrent objects。

 including logs or data structures or some garbage collectors。

 And in the design of such concurrent object， we are going to。

Use the semantics to reason about the correctness of those concurrent objects。So at the high level。

 the problem semantics is also on interliv operational semantics。

 The threads are executed one at a time， and each threat has turned。So it is an inter semans。The。

 the good story is that the good good news is that it is still not that crazy difficult。

 It is inter living。 It is just expected from the the nature of the conquercur programs。

But bad news is that it in order to model relaxed behaviors and ordering。

 it is a little more difficult than what is called sequentially consistent semantics where where the threads are only executing。

For just plain memory and this display plain program。

In order to track the relaxed behaviors and ordering。

 So it introduces a few ideas that is listed here。 There are four key ideas。

The first key idea of Promantics is that it uses the memory that is a little more complicated than the sequential memory in the sequential memory。

Me is system the mapping， from location to value。So for each location， there is a value。

 it's a memory in the sequentially consistent semantics。On the other hand。

 Pro semantics has a multivalued memory。 Basically。

 it tracks the history of all the rite that is performed to the memory。😊，The， the reason is that it。

We want to allow what is called un load hoisting。That means that a later those should be able to be reed so that the later those can be executed before on earlier year instructions。

🤢，So in order to model this instead， we are going to have a motivated memory that tracks the all the history of the。

😊，Execution。And then the load to read from on old value。So， that that effectively。

Allows that effectively the models， the loting。So we， I will。

 I will show you the example of this later。 So so let me be more concrete about this idea at the later slice。

The second idea of problems is what is called memory adjacency for modeling read modify writing instructions。

So as we discussed in the previous lecture， Read Mor instruction should be exclusive with each other。

 for example in the implementation of the acquire function of a spin lock we said that oh。

 if there are two stress that is trying to acquire a single lock。

 then we need to make sure that only one of them has successfully acquired the lock。That means that。

 that means that we need somehow。Somehow。Oder。W wouldly acquire attempts。And allows only one of them。

To succeed in read modify writing instructions。So in order to allow only one of them to succeed it。

 we somehow need to。嗯。Constrained， constrain the behavior of Israel modifier rights and bemoral consistencyency is a way of constraining such behaviors。

So for this， I will also show you examples later。 So please wait a little bit more about。This。

The third idea is what is called the views in order to model possible orderings and possible relaxed behaviors。

In the， in the promising semans。 So it is basically constraining our threats behavior。

 constraining relaxed behaviors， constraining orderings。Reoders， basically。

AndThis is also a concrete content in the later slice。And the last idea is a promises。 That is also。

That also inspired the name of asthmamans， promising semantics。

And this is in order to model what is called store hoisting。So recall that Lu Hui sing is。

Reoddering a later low to all year。 St hoisting is similar。

 It is reodoring a later storm to earlier year。So in。In other words。

 we want to speculatively execute a later store。Even before reaching the even before the program counter reaches the to the store。

So in order to model this， we are going to let the threat to promise to store to a value。Then later。

 make sure that the thread will keep the promise。So that it also has some technical content and how to model these promises precisely。

 And I will show you in a later slide。So overall， these four ideas are forming a single semantics that is called a promising semantics。

 and it will。 we will precisely describe what is allowed and the。

What is this allowed in a conquerd program。So which behavior is allowed and which behavior is disallowed is？

It is the。Yeah， it is defined by this promisingmatics。So， and。

And the and one important note that this is that actually what is actually happening in the hardware。

In the hardware， there is a lot of optimizations inside micro architectureit。

 and these optimizations are very much different from the internal working of this promising semantics。

Promacymatic is just a modeling of such relaxed behaviors。 So it is modeling in the sense that this。

Internal working of these promise semantics is not actually executed。

But it is proven that it is enveloping what is actually happening in the hardware and compilers。

So in that sense， it is just sub model。But the purpose of a model is that it allows the programmers to more easily reason about the program。

So the purpose of this promising semantics is letting users to reason about the concurrent programs on this semantics。

 which is presumably simpler than on the hardware semantics。So。Yeah。

 that's basically the proposal of these promise semans。And I will explain the I one at a time。

 And the first idea to explain is the。Multivalued memory。 So let me show you a slide for this。So。So。

 yeah。In the。

![](img/3bb788c993886ce8506d2e1057e5dab0_1.png)

In this mantics， memory is no longer just the simple mapping from location to value。

 It is a mapping from location to a list of what is called messages。



![](img/3bb788c993886ce8506d2e1057e5dab0_3.png)

A message is consisting of a value。

![](img/3bb788c993886ce8506d2e1057e5dab0_5.png)

And a timestamp。

![](img/3bb788c993886ce8506d2e1057e5dab0_7.png)

Timetamp is basically a counter。 Count means that you are going to have a。



![](img/3bb788c993886ce8506d2e1057e5dab0_9.png)

You're going to have a value that represents the time of the。



![](img/3bb788c993886ce8506d2e1057e5dab0_11.png)

The at the at at the time of this writing of this message。

And the thread may read an old value from a location， as I said， in order to models to load hoisting。

 we want to allow a thread to read from an old value， old messages， basically。

So let me show you this example。 load hoisting is here。In the left thread， x equals 1 is executed。

 and then R is red。In the right thread， y cos 1 is executed and then axis red。

So the behavior in question is whether R equals alt equals 0 is possible。



![](img/3bb788c993886ce8506d2e1057e5dab0_13.png)

So in order for this to happen， this R should read from an initial value which has not been overwritten by these rights。

And R 2 is also reading from the initial value that has not been overwritten by this right。



![](img/3bb788c993886ce8506d2e1057e5dab0_15.png)

So how is it possible， so note that this is impossible in sequentially consistent semantics because either x equals 1 or y equals 1 should be executed first。

 and if it is the case， then r2 or r1 should be 1。

![](img/3bb788c993886ce8506d2e1057e5dab0_17.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_18.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_19.png)

So this behavior is impossible in sequentially consistent semantics。

 but actually it should be allowed in reasonable concurrent semantics because of the rederings these two threads are possible to be reed the equals 1 and irons y can be reed because they are accessing different locations and there is no dependency between them and same for the the right thread as well。

😊。

![](img/3bb788c993886ce8506d2e1057e5dab0_21.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_22.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_23.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_24.png)

So we want to allow this behavior。 So how to do this。 So。

 so this multivalued memory actually allows us to use this。



![](img/3bb788c993886ce8506d2e1057e5dab0_26.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_27.png)

So let's execute this program and result in how to manage to exhibit this behavior in this program。😊。



![](img/3bb788c993886ce8506d2e1057e5dab0_29.png)

Okay， at the beginning， we want to execute the left right and executing x a equals 1。😊。



![](img/3bb788c993886ce8506d2e1057e5dab0_31.png)

And at this point， we want to insert a message to the memory。



![](img/3bb788c993886ce8506d2e1057e5dab0_33.png)

So it recorded for each location， there is a list of messages。



![](img/3bb788c993886ce8506d2e1057e5dab0_35.png)

And the when x equals 1 is executed， we are going to insert a message。

 its value should be 1 because1 is written。😊。

![](img/3bb788c993886ce8506d2e1057e5dab0_37.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_38.png)

And for timest， we are going to choose anything。

![](img/3bb788c993886ce8506d2e1057e5dab0_40.png)

So we are going to just choose this。 So the actual value is not actually that very much important。

 Let's say it is 5 at times 15。 we are going to write X equals 1。



![](img/3bb788c993886ce8506d2e1057e5dab0_42.png)

So far second。And we are also executing the Y course1。



![](img/3bb788c993886ce8506d2e1057e5dab0_44.png)

So， and。Similarly， we are going to insert a message to the location y。

 and this message value should be one because one is written at this instruction。



![](img/3bb788c993886ce8506d2e1057e5dab0_46.png)

And you're also going to choose a timestamp at your wish。 for example， it can be 7 or 8。



![](img/3bb788c993886ce8506d2e1057e5dab0_48.png)

So note that the times timess of the different locations are very much different。

 So this one and this one is not compared， So they are in a different， different space。



![](img/3bb788c993886ce8506d2e1057e5dab0_50.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_51.png)

A namemespace of times stamps。 So even though this is 5 and this is 8 in times stamps they are not compared。

 it is It is nonsense to say that this is before this。



![](img/3bb788c993886ce8506d2e1057e5dab0_53.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_54.png)

So in the same location， they are ordered0 is before one because they they are in the same name space of a time stamps。

But comparing this one and this one or comparing this 0 and this one is not that important。

 It is just different。Okay， so first good， we wrote one to both X and Y and appended a message to each location。



![](img/3bb788c993886ce8506d2e1057e5dab0_56.png)

And now we are going to execute these3 instructions。 So in the left thread， we are going to read 0。



![](img/3bb788c993886ce8506d2e1057e5dab0_58.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_59.png)

From why。 So effectively， we are reading this message instead of the latest message that contains the value 1。



![](img/3bb788c993886ce8506d2e1057e5dab0_61.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_62.png)

It is specifically allowed in promising semantics because a thread can read an old value that is not overwritten by the then may be overwritten by latest rights because the information is tracked in the memory。



![](img/3bb788c993886ce8506d2e1057e5dab0_64.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_65.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_66.png)

0 is there in the memory so we can read it。From the left right。



![](img/3bb788c993886ce8506d2e1057e5dab0_68.png)

Similarly， we can read from x in the right thread because0 is there。



![](img/3bb788c993886ce8506d2e1057e5dab0_70.png)

Even though there is a latest message that is at that is more recent than the value 0， but。



![](img/3bb788c993886ce8506d2e1057e5dab0_72.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_73.png)

That's okay。 We are anyway going to read0 from the memory。



![](img/3bb788c993886ce8506d2e1057e5dab0_75.png)

Is is even if it is old。It is there in the memory so we can read it。



![](img/3bb788c993886ce8506d2e1057e5dab0_77.png)

So this basically allows load hoisting。

![](img/3bb788c993886ce8506d2e1057e5dab0_79.png)

Reading from an old value or those are hoisted across an all instruction。

 so it is the same thing but represented in a different flavor anyway we are going to able to read zero for both reading instructions in this single example in a single execution。



![](img/3bb788c993886ce8506d2e1057e5dab0_81.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_82.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_83.png)

So this basically allows root hoisting。

![](img/3bb788c993886ce8506d2e1057e5dab0_85.png)

Okay， this is the first idea of promising semantics multivalued memory。😊。



![](img/3bb788c993886ce8506d2e1057e5dab0_87.png)

And I'd like to proceed to the second key idea。

![](img/3bb788c993886ce8506d2e1057e5dab0_89.png)

Which is memory decency。

![](img/3bb788c993886ce8506d2e1057e5dab0_91.png)

Okay。So far second。

![](img/3bb788c993886ce8506d2e1057e5dab0_93.png)

But there is another example that is a counter， which is that， oh。

 if the left thread and right thread are performing a read modifier right， for example， fashionate。

 so it should be the case that they should it should be the case that they read different values。



![](img/3bb788c993886ce8506d2e1057e5dab0_95.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_96.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_97.png)

So。

![](img/3bb788c993886ce8506d2e1057e5dab0_99.png)

It is impossible for R1 and R2 to be 0 at the same time because they are atomically increasing the underlying value。



![](img/3bb788c993886ce8506d2e1057e5dab0_101.png)

So it is a proposal of this read modify right or updates or dispatchness。

 so we need to somehow constrain the behavior of the threads in such a way that reading zero for both threads is not happening。



![](img/3bb788c993886ce8506d2e1057e5dab0_103.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_104.png)

So instead of， so in order to model this idea。 So we have to adjust the memory。

 the message a little bit。In order to。In order to express this idea。

 we are going to say that oh message is no longer a pair of value and a single timestamp。

 but it is a pair of value and a timestamp range， so it has a volume now。So。

So volume means that it is no longer at a single timest， for example，5， but it is occupying。

 for example， timest from5 to 10 or 5 to 8。And why we do this。

 we are going to do this because we want to model read modify right in this way so。

In order to pan a message that is the result of a read modifier， right。

 then we require that the new message is adjacent to the old one。



![](img/3bb788c993886ce8506d2e1057e5dab0_106.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_107.png)

Adjaency means there is no gap between the two messages。 so they are now ranges。

And we want to make sure that if， if a message is read Mo right。

 then the two ranges of the previous and the current messages should be adjacent without gap。



![](img/3bb788c993886ce8506d2e1057e5dab0_109.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_110.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_111.png)

Okay， so it is enough explanation， and let me show you an example。In this example。

 the two threads are fresh and adding one。And let's say that we want to execute the left threat first。

And it can reze because there is a message that has a value 0。And now a message has a timet range。

And I say that it is from this to this。

![](img/3bb788c993886ce8506d2e1057e5dab0_113.png)

And the message should be one because youre atomically increasing the the underlying value by one and the value was 0。

 The value 0 is atomically increased by one， and the result is  one。



![](img/3bb788c993886ce8506d2e1057e5dab0_115.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_116.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_117.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_118.png)

Now in the 2， it is also trying to freshen at1， but at this time it should read one because0 cannot be updated once again because it its adjacenting position is already taken。



![](img/3bb788c993886ce8506d2e1057e5dab0_120.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_121.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_122.png)

So the right perspective in order to perform a ReadMifier right。

 it should be adjacent to only a single message， so only this one message can be readmodifier right。



![](img/3bb788c993886ce8506d2e1057e5dab0_124.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_125.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_126.png)

We read and modified and written。

![](img/3bb788c993886ce8506d2e1057e5dab0_128.png)

And as a result， it should be， this message should be appended after one。



![](img/3bb788c993886ce8506d2e1057e5dab0_130.png)

This cannot be appended right after this serial message because this position is already taken。



![](img/3bb788c993886ce8506d2e1057e5dab0_132.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_133.png)

Instead， it is taking this position and by incrementing the value one by one。



![](img/3bb788c993886ce8506d2e1057e5dab0_135.png)

And the result should be one because the original value is1。



![](img/3bb788c993886ce8506d2e1057e5dab0_137.png)

So in this example， we can see that， oh， it cannot be possible that the Rn and R2 are the same0 at the same time because of the memory efficiency。



![](img/3bb788c993886ce8506d2e1057e5dab0_139.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_140.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_141.png)

So this basically models the exclusiveness of the method0。🤢。



![](img/3bb788c993886ce8506d2e1057e5dab0_143.png)

Methage0 cannot be read， modified， and written by multipo。



![](img/3bb788c993886ce8506d2e1057e5dab0_145.png)

My multiple。Instructions， so that is basically the essence of the。



![](img/3bb788c993886ce8506d2e1057e5dab0_147.png)

Of the RMWs and this idea is captured by method adjacency in this semantics。



![](img/3bb788c993886ce8506d2e1057e5dab0_149.png)

Okay， so this is the idea， too。And let me proceed down to the third idea， which is about obvious。



![](img/3bb788c993886ce8506d2e1057e5dab0_151.png)

View is a little bit more difficult and it is actually starting to describe the reororings and relaxed behaviors。

So the motivation here is that multivalued memory which which was the first key idea of the promising semantics。

 it allows too many unintended behaviors so there is no constraint on the reason rights at all except for orders the me decency for read modify right the plain reason stores can arbitrarily read and write to any locations in any timestamp。

But it is too much。 It。 It introduces too many unintended behaviors。

 and we need to constrain the behaviors somehow。And such a constraint includes what is called coherence or what is called synchronizations。

 So coherence means that， for example， if you read from the same location twice and then the later is should be somehow later。

Read somehow should read a later value than the previous one。

 So when a single thread executes the the excesses to the same location。

 then the excesses should be somehow congruent with each other。 They should respect the order。

And the synchronization is already we discussed。 we already discussed briefly about release acquire and fences。

 and these are acting as a synchronizer。If there is a release and there is a acquire and they are executed as if they are executed the in the same thread。

So it introduces some constraint on the behavior of multiple stress， with the choir or fence。

So they are modeled as synchronizations， and the synchronization is also represented with views。

So so this is the motivation of the views and let me tell you a little bit more about the mechanism of these views。

 So first things first what is view。😊，A view is a mapping from location to the times stampamp。

So it is a definition in the Pros mans， and here are a few examples。

 The first example is a per set view。For example， we said that this bright green is for one。

 and this dark green is the。Strect 2， and each thread has a view for coherence。So。

The this left stretch view has pointing to。This message that is on value 1 for location x and value 0 for y。

That means that。The thread has acknowledged the messages， this message and this message。So。

And as a result， all the future accesses to the location X and y should somehow be constrained by the knowledge。

 The knowledge is that I know the messages1 and0， the messages are propagated to me。

 So in the future I should not access the overwritten values at all。So for example。

 if the view is at here， the threat1 should not read the value0 further because it is already overwritten by 1 and this message 1 is propagated to by myself。

 so it is not possible to read the old value。No longer possible。And also。

 there is a different kinds of view。 Now we see the second kind is a poor message view for release acquired synchronization。

😊，And in order to model the release acquires synronation。

 we need to somehow transfer the view from a single thread to another thread。So in order to do so。

 we are annotating a message with a view。That is just released from the thread。So as a result。

 this view， the scarlet view are annotated or faced to this message。

So this is represented as a message view。So I will tell you a little bit more about the detail of this。

 but here the key idea is just oh， there is a view that is picking a message for each location and this view is somehow managed in order to order the behaviors and remove the。

 too many la behaviors。😊，And the final kind of view is the global view for sequentially consistent synchronization。

 so there is an S fence that is a very powerful fence。

 and it is globally synchronizing with all the other SD。And in order to model this。

 we need a global view。And there are resource of you for assist synchronation。

So I will tell you a little more about all these views in a later slide。Okay， the first things。

 the first thing to do is。Moodeel incoherence with per views。So as I said in the previous slide。

 a portrait view is representing a thread acknowledgement of messages I insert1 and I have acknowledged the message1 for X and message0 for y。

 and as a result my view is like this。So acknowledgecledment means that I will never access unoverwritten messages。

 so I will not access this x equals0 because it is already overwritten by the message that I am pointing to。

So that is basically the key constraint that is imposed on the behavior of a threat。

And this models are per location coherence。So let's see the examples。 So in an R our coherence。

 two consecutive risks， this rate and this rate should be ordered。

Let me tell you a little bit more detail about this， let's say that in a different thread。

 x equals 1 is executed。😊，So as a result， there are two messages。

 the initial message that contains the value0。And the message that contains value 1。

Because it is just written by this thread。So there are two methods0 and 1。

 and here we want to read one is0。Is it possible， I am going to say this impossible because one is more recent value。

 n or two should not be reading on old value that is already overwritten by this the earlierist。

So let me tell you how to model this idea， how to model our coherence or read。

 read coherence in the promising semantics。So at the time that r1 equals0， I mean。

 r1 equals 1 by reading x equals 1。The threat view is updated to point to the value x equals 1。

So the thread here so is pointing to this message x equals 1。Right after this instruction。

 because this is a value 1 is read here。And after that， we are going to read X again。😊。

And at this time， we cannot read0 because Exycoone is already acknowledged by the earlier instruction。

And as a result， we cannot read the old value and we should read the latest value one here。

Because one is not yet overwritten by myself because I am pointing to this location。This message。

So overall， this behavior is impossible due to the coherence and the per views and if iron equal1。

 R2 should be 1 at the same time。Now we are going to discuss R W coherence， which is here。

 It is going to read X and then write to X。And if it is the case， we have to know that， oh。

 these are。Aicles x is should re 0。It should not read from the later right。

 It should not be one that is written by this， though that is basically the。

The RW coherence or read writer coherence， if there is a read and a later write。

 then there should be somehow ordered。How to model this。

 So when you read and when you read the value here， you are effectively acknowledging the message。

 So let's say that the view is like here。Then we mandate that a right should be written that the message should be written beyond the current view。

🤢，Of the the threat。 So if the view is here， the message should be put here。Here， here， here。

 it doesn't matter， but it cannot be put in here because。

This area is already overwritten by the current message here。So if you just read it。

 and then the right should happen later。So that is the rule of reading rights for this RW coherence。

As a result， when you read a message， then the message cannot be what is written later because this message should be written。

After the timestamp of this read。So it this， if， as a result in this example。

 reading one here is impossible。So similarly， or DOoli。

 there is a right read coherence or WR coherence， which means that if there is a write and then read and then it should not be reading on old value that is overwritten by this。

The same thing。By by writing1 to x we the perfect view is at this point， for example。

 and as a result we cannot read from the earlier message 0 is already overwritten by this message。

 so as a result this should be reading the1 instead of 0。

There is also right right coherence or Ww coherence。

 and if there is a2 right x equals 1 and x equals 2。

 and it should be the case that at the end of the day the memory contains the messages 1 and2。

 and they should be ordered， one is before and two years after。

The reason is that reason is the same by writing x equals 1， your perfect view is at this point。

 and after this you have to write the message and the message should be placed here。

Because the per view is here and you can write any anywhere you want as far as it is after the per view。

 but not here。Here is already overwritten by this message。

 so this cannot be placed with a new message that is due to this x equals 2。So to summarize。

 there are coherence。And in order to model these kinds of coherences are we。嗯。

We manage the portrait view。And reason why， all the accesses should happen after the constructs perfect view。

So read write， regardless of whether the access is read or write。

 it should happen after the current stress view。If the threat view is here。

 then you should read this message or later messages if there is one。And if the view is here。

 then you should write new messages later。On the other hand。

 reading and writing changes the currentizedized view， so if y view is here。

 then that the thread is reading this message y equals 1， then the view is updated。

 it is no longer pointing to this after execution it is now pointing to this message。😊。

So the view is also changed and the view constraints the future behaviors。

So it is intertwined with the execution of a thread effectively reducing maintaining the relaxed behaviors and ordering instructions when necessary。

😊，So this is the the the views。

![](img/3bb788c993886ce8506d2e1057e5dab0_153.png)

And this is a visual de。 when your view is here， then this area is readable and writeable。

 This area is already overwritten， so you should not access the the locations。



![](img/3bb788c993886ce8506d2e1057e5dab0_155.png)

Okay， and there are third example of the views。

![](img/3bb788c993886ce8506d2e1057e5dab0_157.png)

I my second example of the views， which is a per message view you。



![](img/3bb788c993886ce8506d2e1057e5dab0_159.png)

The pre message view is representing the view at the time of release rights。



![](img/3bb788c993886ce8506d2e1057e5dab0_161.png)

So if a if a view is released and the view is annotated with the corresponding method。

 which can later be acquired by another threat。

![](img/3bb788c993886ce8506d2e1057e5dab0_163.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_164.png)

So it is basically for modeling where this requires synchronization。



![](img/3bb788c993886ce8506d2e1057e5dab0_166.png)

Heres an an example。This example is already explained the little bit in the previous slide。

 x equal equals 1 and y equals 1， but with a release。😊。



![](img/3bb788c993886ce8506d2e1057e5dab0_168.png)

In the right red， y is red and f is1 we want to assert that x equals 1。



![](img/3bb788c993886ce8506d2e1057e5dab0_170.png)

Here the load here is a acquire and the story is a release and as a result there is a release acquired synchronization。

😊。

![](img/3bb788c993886ce8506d2e1057e5dab0_172.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_173.png)

So that's the reason why this thread should risk x equals 1。



![](img/3bb788c993886ce8506d2e1057e5dab0_175.png)

It can now read the old message because there is a release acquire and x equals1 should be propagated to the second straight at this time。



![](img/3bb788c993886ce8506d2e1057e5dab0_177.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_178.png)

So， that's the reason why。

![](img/3bb788c993886ce8506d2e1057e5dab0_180.png)

Authortion should succeed and in order for this access to succeed with Mo to model or transfer the view from the first rat to the second thread。



![](img/3bb788c993886ce8506d2e1057e5dab0_182.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_183.png)

And it is still to way this release requires synchronization。

 I will tell you a little bit more about this。

![](img/3bb788c993886ce8506d2e1057e5dab0_185.png)

So in order to see whether this is actually this assertion actually is guaranteed。

 we are going to execute it at the beginning， we are going to execute x equals 1。

 creating a new message x equals 1 here。

![](img/3bb788c993886ce8506d2e1057e5dab0_187.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_188.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_189.png)

So far so good， there is no difficult things to discuss solve。For now。



![](img/3bb788c993886ce8506d2e1057e5dab0_191.png)

And then now we are going to execute y equals 1， but without release。



![](img/3bb788c993886ce8506d2e1057e5dab0_193.png)

How to do this， We are first。

![](img/3bb788c993886ce8506d2e1057e5dab0_195.png)

Incrementing the per view。 So it is now S equals1 and y equals 1 because it is just。

 it has just written the new message。 So the view， the per set view is updated。



![](img/3bb788c993886ce8506d2e1057e5dab0_197.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_198.png)

And at the time of the writing， it is a release， and as a result， the message。

 the new message that is written here should be annotated with the view at the time of this release。



![](img/3bb788c993886ce8506d2e1057e5dab0_200.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_201.png)

So at the time of this release， the Per view becomes this。Because because the。

Because the x equal 1 is already written here and y equals 1 is just written。

 so the per view is here and this per view is annotated with the message。



![](img/3bb788c993886ce8506d2e1057e5dab0_203.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_204.png)

As a proof that， oh， this view is released at the time。



![](img/3bb788c993886ce8506d2e1057e5dab0_206.png)

And now in the second thread， it is acquire loading the value 1。



![](img/3bb788c993886ce8506d2e1057e5dab0_208.png)

And it is going to read this message。😊，But it is a acquire。

 So what it does is that the per message view here andnot it here。



![](img/3bb788c993886ce8506d2e1057e5dab0_210.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_211.png)

Is incorporated into the perfect view of the rice threat。



![](img/3bb788c993886ce8506d2e1057e5dab0_213.png)

And as a result。The， the， the thread， the right stress view becomes this。



![](img/3bb788c993886ce8506d2e1057e5dab0_215.png)

So recall that if this is not a acquire， then the view should be x equals 1。

 I mean x equals 0 and y equals1。😊。

![](img/3bb788c993886ce8506d2e1057e5dab0_217.png)

Because it is not a acquire， if it is not acquire， then only the view for y is updated。



![](img/3bb788c993886ce8506d2e1057e5dab0_219.png)

However， it is a acquired in this example。

![](img/3bb788c993886ce8506d2e1057e5dab0_221.png)

And as a result， the per view is incorporated into the。



![](img/3bb788c993886ce8506d2e1057e5dab0_223.png)

Into the。Per message， I in purse right for。

![](img/3bb788c993886ce8506d2e1057e5dab0_225.png)

And as a result， the second per view， which is represented as the dark green。

 it is updated to 0 to s equals 1 and y equals 1 that happens to be the same with a per message view。



![](img/3bb788c993886ce8506d2e1057e5dab0_227.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_228.png)

So as a result， this assertion should succeed because the view is here and this old message cannot be read by the threat。



![](img/3bb788c993886ce8506d2e1057e5dab0_230.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_231.png)

So the more of the story is that we want to transfer the per right view of the left right to the right right。

So as a messenger， we are going to annotate the message with the per message view。😊。

And we are going to。Annotate the first thread view of the left thread to the message。

 and this view is incorporated into the right thread。



![](img/3bb788c993886ce8506d2e1057e5dab0_233.png)

And effectively the knowledge that x equals 1 is written in this message that knowledge is transferred from this to this。



![](img/3bb788c993886ce8506d2e1057e5dab0_235.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_236.png)

From left to right。So this assertion should succeed。

 So that is basically the idea for modeling this synchronization of reviews。



![](img/3bb788c993886ce8506d2e1057e5dab0_238.png)

![](img/3bb788c993886ce8506d2e1057e5dab0_239.png)

So here is the last example。So here's the last example that means that there is almost the same example here。

 so x equals 1 y equals 1， y is red and x is red。

![](img/3bb788c993886ce8506d2e1057e5dab0_241.png)

The same X is written， Y is written， Y is red and X is red。

But instead of annotating with release and acquire， they are annotated with relaxed。

 that means that there is no ordering between with other instructions。Instead， there is an X fence。

 E fancy is a very strong fence that separates all the。

 all the instructions before and after this fence。😊，And as a result， similar to the previous example。

 x equals 1 and y equals 1 should be separated。😊，And this load and this load is separated。

 and this assertion should not fail of thanks to the strong ordering among the instructions。

How to do this， How to， how to。How to。Model this behavior， how to forbi this behavior in our model。

 So that is basically the question， and that is by maintaining a global view for S synchronization。

So let me execute again。If this is executed before the rice rate is executed first。

 then y should be 0 because there is no message that is different from the value 0。

 So nothing happens。 So assertion is automatically。Asser it because it is not executed at all。

 So we need to execute the first rat first。

![](img/3bb788c993886ce8506d2e1057e5dab0_243.png)

So x equals 1 is append to the memory and the view is updated， per thread view is updated。

And then we are going to execute an S， and at the time we are going to update the SC view with a Per view。

So S view is incremented to the per view of the left thread， so that is the internal walking of this。

😊，And then y cos 1 is executed that means the percent view of this one， y is updated to 0。21。So。

 so the crucial step here is the I view。 This acid view is the。

It represents that the per review of this left thread at the time at the time that this fancy is executed。

At the time that this is executed， only S equals 1 is executed。

 and as a result x equals 1 is written here and this view is pointing to S equals 1。Now。

 in the right thread， it is reading y cos 1。Updating its per view to point to y course 1 here。

And then execute an S。And this time。What is interesting is that。😊，Oh。

There are two things that are happen。The first thing is that I am also dating the S view。

I am acknowledging this message and this message， and this is incorporated into the S view。😊。

And the other effect is that oh， S view already has this view。 so my view is updated。😊。

My view is updated to from x equal 0 to x equals 1。Because the SC view is executed。

 and I need to acknowledge what is already en rotated with S view。So the view becomes this。So okay。

 let me let me， let me explain again。My preferred view is here， x equals 0 and y equals 1。

But it should be updated with my S view。And as a result。

 this x equal1 is automatically acknowledged at the time that Francis is executed。

This is very much expected because this sexycos one should be acknowledged here by the fact that it is executed before this fence and this is executed before this fence and this is executed before the assertion。

😊，So the per view should be updated to 0。2 exit cos1。at this point， point。On the other hand。

 as we discussed， y co 1。😊，It should be。Releaed to this A view because a later fence may also synchronize with me。

 and as a result， all the knowledge that is before the fence should be transferred to the As view。

And as a result， my per view and SC view are updated to the join of the two views。

 the join of the two View is x equals 1 and y equals 1 and as a result。

 my view and the SC view becomes the x equals 1 and y equals 1。😊，And automatically， the assertion is。

A safe。So this is basically the key idea of the views and this is explaining various things。

 so for example， synchronization and coherence and there are two kinds of synchronization with acquired synchronization and as synchronization that we learned in the previous lecture。

😊，So today we are going to stop here and we are in the next lecture。

 we are going to study the last idea of promise semantics which is promises。😊。



![](img/3bb788c993886ce8506d2e1057e5dab0_245.png)