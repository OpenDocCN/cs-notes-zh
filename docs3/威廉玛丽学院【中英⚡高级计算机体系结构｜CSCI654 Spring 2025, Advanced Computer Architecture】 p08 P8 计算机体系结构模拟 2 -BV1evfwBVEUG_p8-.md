# 威廉玛丽学院【中英⚡高级计算机体系结构｜CSCI654 Spring 2025, Advanced Computer Architecture】 p08 P8 计算机体系结构模拟 2 -BV1evfwBVEUG_p8-

Okay， let's get started。 So last time we stopped at this point， we're talking about the zero engine。

 So the engine that controls all the events in the simulation and how it。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_1.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_2.png)

Aances times。Right， so I will skip this part。 I will directly go to the last part。

 That is the essential part of the zero simulation code。

 So in a zero simulation engine want to execute one event after another。

 even if they're scheduled at the same time。 They will be executed in certain order。 Okay。

 so how is the event order is actually determined if their schedule at the same time。

 quick answer is we do not really decide them。 Now we consider they should be independent and it shouldn't really matter that which one excuse first or execute later。

 the。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_4.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_5.png)

Order is actually determined by goes hip implementation to the hip。 When you pop。

 if they have same time event， then。It really depends on what's the internal implementation of the he to give you the next event to exclude。

 Okay， it can always guarantee that is the earliest time， the earliest time to execute。

 but it cannot guarantee which one it returns。 It cannot guarantee the original order as scheduling。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_7.png)

就 last time were talking about serial simulation， then。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_9.png)

Let's start with parallel simulation today。When we talk about。When we talk about sequential。

Synchronous sequential logic， we know it's a group of registers and combinational logic and this combinational logic and that combination logic。

 these two logics， they actually they are executing in parallel because theyre executing within the same tip right then。

They， both of them take their input， right， their input， and they can generate output。

 either if there's a loop or if there's no loop， right， they always。For a certain type of input。

 they generate output and。They will get the input from this cycle。 They will generate some output。

 They can never actually get the output of this this C。

 So the second C will never get the output of this conventional logic within the same cycle。

 It must be the next cycle right So that that is to say any behavior。

 any logic in in digital circuit。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_11.png)

For every cycle we have a fixed input then we do calculation we generate a fixed output。

 the fixed the output may becomes the state or may control the state of the next cycle in this way。

 if we have many computational logics in your simulation。

 we actually can simulate all these things in parallel right So that means if events that are scheduled at the same time can be executed in parallel in this way。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_13.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_14.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_15.png)

We can support parallel simulation。 Let's see how we support parallel simulation in。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_17.png)

あきた。So remember， we have an engine， right， Engine has these five。

 Each engine has these five functions implemented， so we want our parallel engine to follow the same interface。

 so it will follow the same interface。 It only still have this five。

Method then from the perspective of a component when they are scheduling events for the future。

Or when a user is implementing a component， the component is the most part that the user may want to implement the digital circuit logic right。

 so in this case they don't really need to know if they're working with a parallel engine or working with a zero engine。

 they only need they only they knowing or we're working with an engine and I can schedule an event and that event will happen in the future。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_19.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_20.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_21.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_22.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_23.png)

So it really， I would say this is a programmer transparent way of implementing a parallel simulation。

Then how does the parallel simulation work， then the code is actually a little bit long then it's much longer than zero simulation。

 so let's look at this code together then would we will then you will understand how it works okay so at the beginning it's basically the same when there's no more event we just exit right then here we set a log。

This is a pulse lock， just the same same thing as zero simulation。 Now here we have two functions。

 one is determining what to run， when is run run round。 So what is a round。

 A round is basically the event that are scheduled at the same time。Okay， run run。

 That means we run all this。 We handle all this event if they're scheduled at the same time in one cycle。

 Now here we run， run。Runds， right， we run multiple rounds here。Yes。Here， I want to say。

 I don't know if you notice that。In Akita， we typically hate comments。

So for all the code that I showed you。Those are real code。 Those are the whole full。

 full codes And I'm showing you。 It's not something I remove the comments and showing you there。

 We hate comments。 We think comments。 So these are not comments。 These are not comments。

 These are code documentation。 Okay， so for go， if you not go the go packet， go up。PPKj dot。

 it's a website。 and then you can check the automatically generated documents。

 So those are documents that you can view in a web page。 Those are documents。 Those are not comments。

 So within a function， we rarely write comments then so for people who pro writing comments。

 They think if you have comments is the code is easier to read then like typically I have the opposite feeling that I find when you write comments。

 the code is becomes harder to read， especially in real word。

When you are dealing with this scale of code it's okay， but when you're solving a complex problem。

If you don't care about coding quality， it can easily grow to hundred thousands of lines long。

 then you write comments there， then someone else will come and start to modify your code。

 but forget to modify the comments， then the comments has mismat with the code then the comments is misleading so rather we care about the readability rather than how many lines of comments that we write in our code So how we can guarantee readability is we try to use function names instead of code。

Okay， we think。Determine what to run and run round is more。These function names。

 you can just consider their， their comments， but they're always， they're very。

 very likely to be describing what is actually happening with this function。 So we use。

 we break we break down this long function into smaller functions。

 And for each group of functionality， we use。Smaller functions to fix this， to achieve this goal。

Okay， there are lots of debate on comments then my general consideration is unless there's something that is really tricky。

 then we should avoid comments as much as possible。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_25.png)

Okay， so let's read the code a little bit。 I by a little bit。

 So we are breaking down into the determine what to run。 Now here。

 the determine what to run is basically just to find the time that we need to run the time so。

Basically， in each Q group， I'll talk about Q group later。

 but you can consider there's a a list of queuees for primary events and a list of queues for secondary event。

 So we find the earliest time in in primary queue and a list of。

At the earliest time in in the secondary queue and we said the primary queue and the secondary queue。

 So if the primary queue time is earlier then we consider we're running primary events。

 otherwise we're running secondary events， but here we only just say。

 oh this is the time that of the next round that we need to execute。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_27.png)

ok。Then here comes the run round function。So run round function， we get Qs， ignore Q channel for now。

 then if we're running secondary events。We're doing this。 Then we first emptied the Q channel。

 Then we run events until we cannot run more until conflict。

 We try to run as many events as possible。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_29.png)

ok 咁。So let me slide explain what Q Chan here is doing。 So in0 simulation， only have two Qs。

 primary Q and secondary Q or。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_31.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_32.png)

Or you can consider there's only one queue for simplicity。Now， we find in parallel simulation。

 we want to execute these events together at the same time， right。 Now this。

 we are actually pumping out events from this queue and dispatching them to the runner and runners are executing。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_34.png)

While we're pumping out events from this queue， we kind of are locking this queue so when we're locking this queue but the events when we're handling events。

 they want to schedule new events into this queue so this queue becomes a global performance bottleneck that everyone is waiting for this queue so it has to first dispatch everything so they can handle new schedule event on the other side this new events when they're like want to in into this queue they have to be serialized so it have to in one event into another event。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_36.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_37.png)

So we realize that becomes an a global。A global bottleneck。

 That's why we convert a single queue into multiple queuees so that even we're pumping out events from one queue。

 we may be able to schedule into other queuees so that these two things can happen at the same time。

 So it's a performance optimization。 What is a queue channel。 It's a channel。

 in it's a channel iss a。Gos a parallel simulation feature。You can consider it's a pool of Qs。 Now。

 whenever we want to pop up， pop up a queue， we actually can retrieve a queue from the channel。

 Let's just get a Q from the pool。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_39.png)

ok。So we first emptied the Q chain so that this pool。

 we want to take all the queues out of this pool so that no events can schedule in it。

 We have to make sure that this queue。We dispatched all the events from this queue that are scheduled at this time this time。

 then we put it back into the queue into the pool so that other events can can schedule event into this queue。

Okay， this can be a little complex， but not something super essential。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_41.png)

Then we run events until conflict。 Now， I think this。

Code start to get something that you're rather familiar with is very similar to zero simulation。

 So here we have this Q， right， We range through the queues。

 If there events we get something from the queue， if the event event time equals now。

 if it's within this round。RightNow we do Q do pop。 we remove from this queue。

 Then we run this event with a temporary worker。 Okay， we run it with a worker。 Now， otherwise。

 there's something wrong。 Then eventually we put this queue into the pool。 right。

 This is a syntax of putting this queue into the pool。

 So the only special thing is run event with temp worker。 Let's look at run events with temp worker。

It's instant run event with time worker。We call go Y time worker run。

 This is a very simple syntax that means We're starting a new thread。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_43.png)

To run this event。 So pretty much here， we're using one thread to run one event。

Goold thread are much lighter weight。 So although we have millions， billions of thread。

It's not a big problem。 We can handle them。So here there's a weight group at one， right。

 This is a synchronization。 So remember here we have， tos go back a little bit。

 We have this weight group that wait。 So we have to wait until all these events within this round to finish。

 Then we can start the next round。 right So this weight。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_45.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_46.png)

Is a synchronization。And that's what I say， it's。Big performance overhead for Akita to we're doing a something that is called a conservative parallel discrete event simulation。

 A conservative discrete event simulation means。We are。 We do not interrupt the time。

 We guarantee the time still goes in the certain in the right order， then。嗯。So that ideally。

 the exertion result or the predict time in parallel using parallel simulation should be exactly the same as0 simulation。

Okay， so we do not interrupt the time order。 The chronological order is maintained。

The good thing is the accuracy is somehow guaranteed。

 The bad thing is it cannot reach very good scalability。 Okay， so there's some。

 there's still space for research to make it more。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_48.png)

The performance to be higher。Okay， so we add one event。 Then we are waiting for this event。

 this weight group， this number， this task to be done。

 So here this run event with time worker or run time worker run。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_50.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_51.png)

Its actually very simple。 It's basically the same code as0。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_53.png)

A zero engine， right So we get the time we do some s check。 we call a hook。

 now here this is when the event are actually happening。 and we call a hook after the event again。

 then weight group is done when it's done。 That means we're reducing that weight group counter add one。

 we're reducing this counter down by one。 when it becomes zero。 we consider weight group do weight。

Its completed。 You can pass that point。ok。So this is。The parallel engine。人。

So the key idea is only one sentence if events that are scheduled at the same time can be excluded in parallel in a kitta。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_55.png)

ok。Then so how many of you know solid design principles？Soli design principle， really no one。

 solid design principle is a software engineering concept。ok。No one， right， then。It's very important。

 Now I hope everyone can learn it if you write some non trivial skill program。

 some slightly ladder scale program。 solid design principle is very important， is very， very useful。

It's actually five principles， now I'm trying to just go through these five principles and see their examples。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_57.png)

In。How we use these examples in in the simulator to。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_59.png)

How many of you， how many of you know design patterns。Okay， only a few of you。

 I think the under where  3，0，4， the software development course teach design patterns， right。

 and probably also solid design patterns。So these are five principles。

 S is single responsibility principle， always open closed。

Then this is probably the most important principle。 L is the list of substitution。

 I think this is probably the least important one。嗯。It's not that relevant for gold。

I is for interface segregation。 D is for dependency inversion。

 So I will go through every principle with you。While we're introducing the simulator dependency inversion principle depends describes this behavior。

 So for if you want to make it the program really simple， you say， oh， I have a handler right。

 handler handler， let's say internally， we may need an engine。Actually。

 the requirement of need the engine violates I principle， but let's not talk about I principle here。

 So here we have an engine， right， the field。The field of zero is a field belongs to the handler。

 When I schedule an event， I can schedule to this engine。Right。

 so I need a reference so that I can schedule future event。

Then if you do not consider the structure of the program， you may just say， oh， I have。

 I wrote a zero engine。 and I'm happy with that。 I'm just directly say， oh。

 this engine should depend on this zero engine。 So this engine， I may write a code like this where。

Eジ。0ero engine。Or I'm going to put a star here。I'm going to write some code like this right So what's the problem with this code for smaller scale program is not a big problem。

But。It's a hard dependency。 That means or handler， this particular handler。

Have a hard dependency on a zero engine。 One day， if I want to replace zero engine with something else with a parallelel engine。

I have no way to replace it other than modifying the call here to Per engine if you think。

You may have hundreds of different components in a simulation then replacing them is not a realistic task。

Right， so this is a hard dependency。The goal of dependency inversion。Is。

To eliminate all hard dependencies。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_61.png)

What it should depend on。 You should not depend on。

You should not depend on anything that is concrete， but you should depend on an interface。Right。

So I depend our engine。I depend on engine。This is an interface。 Then this is an error。

 Thisarrow is implement， right。呃，The implement。 So zero engine and parallel engine in both implements the engine interface。

That means if I write here ask。Not zero engine by the engine。

Then my engine field is flexible that I can change to whatever engine that I want。Right。

 I can even write a new engine。Here， right， That's another engine。

So this is dependency inversion principle， then this is。You can consider this is a dependency。

 but implementation。嗯。It's also a depend。 It's also a type of dependency， why。

You can see these arrows are not like， in random。Direction is always pointing from this subfield to this。

Interface， why is it， Because you can consider this error as aware of。So the handler。

 because it has an engine in this case。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_63.png)

In this case， the handler is aware of the existence of a zero engine。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_65.png)

In aware of， right。In this case。The engine aware of the the handler is aware of the existence of the engine interface。

 but it doesn't know the existence of a zero engine or aar engine。 It doesn't know it's not aware of。

 right。Then the zero engine and parallel engine， because there are。Iplementing an engine。

Let's consider Java for a little bit。 right， When you in write a Java code。

 if you want to implement the interface， you need to write class zero engine implement。Eine， right。

 you have to write that of code。 If you do that， you are aware of the existence of engine for go。

 it's a little bit different story。 You can be not aware of the engine。 That's another type of story。

 But let's just come back to the。Ol school object or programming way。 So in this case。

 parallel engine and serial engine knows the existence of engine。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_67.png)

So what is dependency inversion， dependency inversion is previously we have this dependency downstream。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_69.png)

right。This aware of downstream， but here。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_71.png)

We have this dependency。At this point， going upstream。

RightWe inversed this arrow rather than directly depending on this thing where reversed。Inverse。

To go upstream。That's why it's called dependency inversion principle。In this case， we。

Can remove any hard dependency。 So basically， when you write a handler。

 when you write a piece of code， a class or something， astruct or something， when you have a field。

 You know， oh， this is my dependency。 I need to。 I， I depend on engine。At this point。

 if it's a concrete type。It's a validation of dependency immersion principle。

 Then you should consider creating an interface in between two。

Make it dependency inversion and to prevent heart dependency and to guarantee that you always have the possibility to replace something。

Okay， so we can later on， you can see throughout the development of Akita。

 we try to use dependency inversion principle as much as possible。 Im pretty much sure。

Akita part M GP may slightly violate that， but Akia part should be no problem。

 Always following this rule。ok。Any question。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_73.png)

No question O。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_75.png)

So that we're done with the time management part。 the engine part。

 So we're now moving to Akita components， which is another important part。

 So what is Akida components is a basic element of Aqab based simulation。

 So what is component then you can consider each computational logic is a and it's a sausage register as a。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_77.png)

As a component。 But since we are going towards architecture level。

 we do not really think at the individual register and a computational logic level。

 we consider components as a larger element like a CPU core， a GPU core， a cache， memory controller。

 network controller， those things are components。 Still。

 there's no certain rules for you to say at what granularity or creating a components。

 It's solely okay that you create a components that is a gate。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_79.png)

Okay， it's totally okay。 You can also create a component， say。You know。In a CPU later。

 will talk about like pipelines。 Now you can consider each stage of pipeline as a component itself。

 You can also consider Ho corere as a component。 So either way works。 There's no certain requirement。

 say， what's the grandularity for components。So what is is a we typically draw a component in this way。

 just a block。I know in some other simulators components can be called different things。 for example。

 Gen 5 calls a component a same object then some other simulator even just call it a box or block theyre pretty much the same thing。

Nothing really new here。So what is a component in code， it's an interface。No。

 are you familiar with this syntax。Or at least you can guess what's going on here。

So this are called embedding， right。 embedding is basically。A little like inheritance in。In Java。

 so named is an interface by itself。Right。Named is the interface by itself。

 The handler is an interface by itself。We already talk about handler interface。 handler has one。

Md that is handle。 handlele what handle an event。Right handler。

 Now we talk about Hable port owner later。 And other than these four， by the way， name。

 they only have one matter called name。 So basically， we say this one， this is something has a name。

Right。Then other than this， we have a notify receive a notified port free。 Later on。

 you can see these two functions are super useful。O， so。Component is a large interface。

 It can contain many different things there。Then why we want to have this have these smaller interfaces。

Because we want to support this interface segregation principle。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_81.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_82.png)

That is the I principle。ok。D is dependency inversion。 I is interface segregation。Yeah。

What is interface aggregation in the philosophical engineering domain？

An interface aggregation principle or IP states that no code should be forced to depend on matter it doesn't use。

Do't have an example。 No， I don't have an example。 I I think I haven a。

 This one is actually a good example。 So a handler。A handler， right。

 This is in the environment of a handler。Or you can just consider it as a。Component， right。

 componentonent needs to have engine。Combinnet needs engine to schedule event。Right。

 so eventually this one will say H is this handler dot engine。到 schedule。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_84.png)

Right。So， remember。You can go back a lot of slides。 Do you remember what the engine interface。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_86.png)

Eine has five， at least five functions， right so。That the handler。Require run pause。

And continual functions。Does it require that。Those functions。It， it doesn't。

We only need to schedule future event。 We don't need to control the run。

 We don't need to trigger the run in a component。 We trigger the run in the main function。

We trigger a run in main function。 So this。Is what I say。A violation。Of the。I principle。

 interface seggregation principle。W， because we're forcing this handler to depend on the run and pause function。

Although it doesn't really require to depend on those functions。

So what is the best way to solve this problem？

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_88.png)

The best way to solve this problem is rather than providing an engine interface。

We provide another interface called schedule， called event Schr。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_90.png)

An event scheduler。 Then we let engine。To use this method， the engine should be an event scheduler。

If it's an engine， it should be an event schedule， in this case， if it's a component。

 it should bename。Right，In this case， an engine should be an even scheduler。 So here。

 rather than an engine。We should depend on an event。Schedulule。Okay， so this， if I make this change。

 I'm following the I principle。I only depend on event scheduling features。ok。

That is something that we're trying to improve in Akida before then。嗯。I think we're almost there。

 but Im not I cannot guarantee that we have to solve this problem everywhere。

 So there are still lot of components that are depending on engine。But not a I don't。

 I think this is a not super， super important problem as compared to the dependency inversion principle。

 dependency inversion principle really makes your software super flexible。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_92.png)

Okay， so come back to simulation， complex architecture simulation。

 now this is not software engineering course， so for a component。We have ports。

 so if a component needs to communicate with another component it needs to go through ports and port support component component communication Now if we send things out we call it or the unit they communicate we call them messages or in other like in other computer architecture simulator or if you write a paper。

 they the committee kind of more prefer to be。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_94.png)

Packet， packet。Packets or packages。I'm always confused with these two these packets， right。

 So this domain typically can prefer packets。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_96.png)

So when you say a network package， you send a package out， none。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_98.png)

It receive a packet。 So this is a networking terminology。 But here we just call their messages。

 We send them messages。So if you come from the Akita V1 or V2。诶。Time if， by that time。

 if you were using Akita， we call messages request。 then we think request is a very common term。

 right， very easy to use。 Then we create a problem。 We send a request。

 Then what's the thing that respond to us。 It's a response， right？ So it creates a huge。

Dlemma or problem for us that we're saying。A response is a request。Now。

 because we' are sending request， right， then the something come back is a response。

 but what we are sending is still a request。 So a response is a response is a request。 It makes a。

These term is really confusing， so we change it to messages， so a request is a message。

 a response is a message that makes much more comfortable。So what is a message。

 messageage is a piece of information that is transferred between components and has two interfaces。

 two functions。The more important one is the meta。 Now it returns the meta data associated with this message。

Right， so what is in the metadata it contains an I D identifier， a source destination。

 a traffic class， traffic by。 Okay， so here， let's say I D， why we need I D。

 We need to record that which message is sent it needs to be unique。

 That's why we have this clone message， clone method。So we guarantee。

 let's say sometimes we can we have a component component A sent to B。

 then B is only something like a router。 So B is or just pass message to the dispatcher。

 the pass message to the next point， so it actually can reuse this message to send to the next level。

 but because of the I， we have to guarantee the I to be unique。 So we require that message or。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_100.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_101.png)

All disposal。 they're all single time use So use once you discard it。

 If you really need the same message again， clone it and use the clone version of message。

 So a clone the message most of time is basically the same thing， but only the I is different。Okay。

 so message might not return this thing， source and destination。We know。

 we want to know where we send it Tao and where we' are sending it， Zhou。

This is a relatively new change。 This change is less than two months old that we're starting to use remote port。

 I think like there are several of you are using similar Akita is probably still not really aware of this change。

 Previously， we have a reference just port and remote port here is a type alias。

Or another type that is basically a string。 So it just requires say， we only。

 we don't need to have a reference to source port and destination port on their own， but we。

We just need。The name of them， that's good enough for the routing purposes。系。

Why we make this change in others？There are several reasons one reason is in the future we want to support serialization。

 so we want to prevent circular serialization dependency。Now that important。

 you just want want you know there's a source and destinationation attached to each message。

There's a traffic class and traffic bys。 Traffic bys is easy to understand if you say on this message is 1000 B or 4 by。

 like how many bys it depends on how long time you need to pass this message。

Traffic class is more related to virtual channel than were when we will talk about it when we introduce network on design。

 So traffic class is basically。诶。Not being really being used is more like a future proof field。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_103.png)

O， so let's look at the port， what port can do。Now port is a much more complex component。

 It's unnamed。 It's hookable。 Then we talk about hook later。嗯。As remote， convert then。

Convert the hook。 sorry， convertver the port into a remote port。 Basically return the name。

 It's exact same。Exact same function method as the name method。 Okay。

 then their setter and getters said connection with the connection that is attached to a port。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_105.png)

So connections are outside the components and are connecting two port together。Okay。

 set connection and component， what is component that is the owning component of this port？Okay。

 now there are a set of methods， for example， deliver。So you can see I write a comments here。

 These a few functions are for the connections to call。 So connection will deliver a message。

 put the message into this port， notify available， till this port of the the connection becomes available retrieve outgoing。

 So when we're sending out retrieve a message from the buffer or peak outgoing so。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_107.png)

Pick and retrieve or。To commonly used term in Akita。 The peak means。Pak and retrieve。

 They all applies to buffers。 Peak means we get a reference to the first element in the buffer without destroying it。

 without removing it。 Rettri means we return that one and also destroys it。Okay。

 both of them return messages and same thing here is basically symmetrical to connection， right？就。

We'll have more explanation later。 I will go through you with some of key functions implementation to let you know what white ports are actually a super important。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_109.png)

Element in Akida。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_111.png)

So ports。是。Within every report， there are two buffers， one's incoming buffer。

 wine's outgoing bathroom。嗯。And also， these changes are not very old change than in V 3。

In V three time， we each port only maintain the incoming buffer。

 and the channel maintains the outgoing buffer。Which we find it's very confusing。

 nobody can remember this。 Now we just make it simple to say port maintains both buffers。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_113.png)

Okay， so then there's a connection， the outgoing buffer send messages to the connection and incoming buffer sends the messages to components。

 okay。Should be straightforward enough。 And actually it's。The connection should extract， should。

Retrive outgoing。Then the connection， the the component should retrieve incoming。Right。

 just retrieve elements from these buffers。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_115.png)

Okay， so what is a connection， The connection is。Also， it's much， it's actually much simpler。

 So I only want you to look at plugin method in plugin method。We just associate a connection with a。

Without port。Okay， then the port also has a connection。 Then when call we call plug in。

 we also set the。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_117.png)

Port to be。To work with this connection。So one connection can be connected to as many ports as possible。

But one port can only connect to one connection。Okay， so again。

 in is a connection can connect to many port and because we have the source and destination。

 it can send from any source and destination as long they're connected to this connection。Right then。

 but a port must work with only one connection。It can now then also go with another connection。Okay。

 and we actually have the sanity check so that if， if this port is already connecting to something。

 if we try to replace a connection by connecting to something else。能。You will panic。

 There's an arrow。And also this unplug method， we also leave it there for future proof。

 although we never implemented it。For computer architecture。

 it's very unlikely that you change configuration while your program is running。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_119.png)

So unplug is a never implemented feature。So I want you to look at a default port and actually there's only one port implementation。

 So if you want to have the port， have another feature。Copy paste this code。Implement your own port。

 Okay， then using this dependency in version principle。

 you can always re replace a port of a component。 And because your port is still following the same interface。

 you may have new functions。You can always use your new port for a。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_121.png)

For your component， okay？So this is default port， nothing really special， it has a name。

 it has a component， it has a connection， its all single element， it's not a array。

 it has an incoming buffer and outing buffer there's a log thats prevent some race conditions。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_123.png)

So when we create a new port， we need to specify what is the owning component with the incoming buffer cap and outgoing buffer cap。

 the capacity。Right， with the how large are they。Then basically we create， we knew a port。

 we set a component， we do an incoming buffer， we create a new outgoing buffer。

 and we set a name by the way in go， if or're not that familiar with go go doesn't really have constructor。

 so they just use this simple new function to construct some element。Okay。

 and also in ghost turn in Akita， there's a naming convention。 Now， we name something as this。

We name something as GPU。0， it's all example， right， We don't really have to be GPUus。 GP PU 0 S。1。

到 C U 0。Dot incoming buffer。Okay， this is always the naming convention for Akita。

They're separated by doubt。 if it's theory， if it's a theory of。

If if it's a group of or list of elements and a symmetrical element we use in this square bracket。

 that basic means whenever we have a square bracket here，0 and1 have the same configuration。O。

So those are naming conventions。 There's are new function。 then there's no real logic here。

 So I want you to check this code， this send code together。

 So something I'm pretty proud of the Akita coding quality is。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_125.png)

Pretty much every function I can put on a slide。There's no super long functions。

And this is the whole function。 this is really the whole function。Okay。

 so we first unlock it and see whenever before we exit the program， we unlock it。

Here we do message must be valid。So if you do not care about coding quality。

 you may just put all the sanity check there， but we know this is probably less relevant to the real logic we put it in a separate function and the message must be valid。

Whenever you see must， that means if it's not valid， it will panic。O， that's a convention。

Message must be valid， we had some sand checks， for example， source and destination must be given。

 They can be empty。And source and destination。The destination cannot be this port。

 you cannot send back to yourself， right basically there are some sandy check in this function。

Now it not super important， but here we see if we cannot push， we cannot put in outgoing buffer。

What do we do is we return a new send error。 We see there's there's an error we cannot send it to because I don't have buffer。

Right， then the main component will wait and retry in the next cycle will do something else anyway。

Or it's not important。 It may just discard it。 It really depends on the component logic。Then here。

 let's look at this one， outgoing buffer up push。 and we push a message in the outgoing buffer。

 Then eventually the connection will take it away and were delivered to the destination。

 just we don't know how long it will take。This part is hook， not super important。

 And here this is a little important is。If it's empty right。

 if it was empty then and there's a new message arrives。

 we need to tell the component it notify says does send we need to notify the component。

 their support wants to send something then the connection needs to wake up and start to work on and deliver thanks to the destination okay we need to notify the connection。

In a cycle based simulation， if you consider connection is a component。

 we may just simply tick connections。Takeick tick tick every cycle the connection right here。

 definitely there's a performance improvement trick。 If this connection is idle。

 then just don't wake it up。 Now， if there's no nothing to send on this connection， don't wake it up。

 Just don't even schedule an event on it。 Don't take this connection。

Only when we needed to do something。 we notify it。Okay， it's not if I send。Okay。

 deliver is the other way around。 Now we see how we can eventually deliver something into a port。

 You can see there's definitely some。Sysymmetric implementation， right。 So log。

 check the incoming buffer if we can push， if we cannot push， we say a send arrow。We say， oh， theres。

 we， we cannot deliver at this moment， Try again later。嗯。我审啲。Thank you。Yeah。

 this one is outgoing buffer， right， so for sending out is outgoing buffer。

For deliver is incoming buffer， pretty much is only the incoming buffer and all buffer is different。

RightThen involvevo cook incoming buffer or push。 then eventually we notify this component or there's something。

 There's a new message。 W up and process it。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_127.png)

So the port here is a kind of intermediate between a component and connection and wen them up whenever there's in request that it needs to be responded。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_129.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_130.png)

Okay， let's look at the incoming retrieve incoming。

Then who is calling retrieve incoming is basically the。Retrive incoming。

 The component is calling retrieve incoming。 right， I also need to think for one second。

 So who is calling which one。The retrieve outgoing is basically exact same code。

 So probably I won't just show it。 So here we try to pop it， try to pop it from the message。

From the buffer。 And when we pop it。It's empty， right when when if it's new， it's empty。

 we return new。Right， so it's still which。Process special cases at the beginning and return early so that we can prevent reduce one level of indentation。

Then this item must be a message， and we call a hook， then。So， if。This incoming buffer does size。

Equs capacity -1。 That means it was full。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_132.png)

Right。It was full。 right now， it's not full。 We have at least one space available。 In this case。

 we need to notify the connection， say。So the connection maybe may think I'm fully occupied。

 Like if I'm fully occupied， just don't try to retry sending it。

 sending sending it to this component， right， But this time I'm not full。 So if the connection。

Have something to send to me， the connection can wake up and notify the connection。

 say this port becomes available， just try again if you have something to send to me。Okay。

 so that's why I need a notify available。 So similarly， on the other side。

 we have a notify available for the component。ok。That's a。The implementation of。Theport。Now。

 for connection， I'm now going to show you the implementation of a connection。

 connectionion has longer code， but。Not very complex， just。So we have a direct connection。

 Direct connection。 You just can consider it as a wire， a piece of wire。

 You can always send something from one place to another place without latency or。

If you consider a buffer it one cycle latency， right。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_134.png)

就。I will assume that you can imagine how the component connection works。 So let's see an example。

 a Ping simulation， create a pure pure event driven simulation in Aqta。Okay。

 we want to simulate a pinking example。 So ping。你서。Network protocol， right you send it。

 send you try to see if nothing is alive or not。 You send a ping message and wait for a response。

 So we just want to simulate this process。 So a send a p request to B and intentionally we let the B to wait a little bit and it will send a pin response back to a。

 So here we want to make it simple。 So we said these are direct connections latency free。

 So we have to add a little bit latency， So we add a latency to B okay in theory。

 if you are doing a network simulation then you should have a latency on the on the connection。

So let's let's just go through what type of event we need to have and what messages not we're sending。

Lookal through this example is。We need an event to say， at this time， we need to start a ping。

To send this pin out。 So we have a start p event。This， when the starting event is called。

 they send it to this port。 Then after some time， this connection will will guarantee this。

questThis request to arrive at this point， so this is a receive。So receive it's not really a。Event。

 so that's why I'm drawing at a circle。When we receive it， should we should be。

Bs notify receive function should be called。So P should be notified that this message is received。

In this case， since not a delay and we know this delay， say two seconds later， we need to respond。

 then we schedule an event two cycles later， two seconds later。So there's an event and these event。

 these two events are definitely should have different behavior and since we want to keep A and B are the same。

 we have to have another event。Okay， now when this。Even is。한 do。Then we send it back。

 we send a ping response back， and then it receives the ping response。

 and we know what's the latency of the Xron trip。So two events and two messages。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_136.png)

And this， basically。What we need。So how to implement it is to create a message。ya。

Whereors credit event。Okay， for even later。 Let's create messages first。We create message。

 We create a ping message。 We only need a message meta， right。

 Then we can associate any data we want with a message。 Now here， we only request。

 we only re attach a sequence I D。So that we know which one comes first。

 the return may be in different order。The pink message， the meta is simple。

 the sell boiler boilerplate code。 Now we need this to return this message Meta。

 clone is also boilerp code， right。Then generate the response。

We need a one message method called generate response。

 It always generate this p response and have this information。What is a ping response。

Its similar to it， very similar， but do we have a response to access string。O。

 and also has sequence I D。 Meta and clone are pretty much same。 But here we need a get response to。

Message that to say it， it's a string which should be the I D of the request。Okay。

 so that we know which request I'm responding to。Okay。

 this response to field is the I D of the original request so we can match the request with the response when we receive it。

so。We say we have actually have other interfaces。 We still have the request interface and response interface。

 Request interface is the message plus a generate response and the response message is the is a message plus get response to so we know which is a request and which is a response。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_138.png)

Then we create messages we can create events， two events， one star pin event。

 we also associate the destination information say where do we want to send it as part of the event。

Now， for this event， respond pin event， we attach which which message we're responding as part of the event so that when we。

Handling this event， we know the context。Right。So if you may not。

 you may not know what event base event base is basically abstractstruct。 So this is embedding。

 It's a little bit similar to inheritance in Java。 So if we're embedding this event base。

 we automatically have。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_140.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_141.png)

The method。The other than this new， we have time handler is secondary so we're basically just trying to avoid you writing too much boiler play code so that you have these getters ready。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_143.png)

ok。你开心。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_145.png)

Okay， since we have。嗯。Since we have a event and messages。

 let's try to make it work and try to create a component。 So in Akita。

 we just simply call every component comp。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_147.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_148.png)

能。All components should be named the comp， but the package or the folder name should tell oh this what component this is right and also we do require the one package one component。

 Don't try to create multiple components within one folder。Comumbor base is。

Also similar to event base is just provide you the bodyplay code。

 We have one port that's called output。 Okay， now we have an engine。 So see here。

 this is a violation of IP principle interface seggregation principle。

Right not a big problem or work on it。Probably in V 5。 So start time， we're recording the events。

Time and next sequence， I D。Some internal state， you can consider this state are registers for a component that need to remember。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_150.png)

So let's go through this process so remember。A component is a handler， right。

 So the handle is probably the most important function within a component。就 are handling events。

Although we don't know what type of events we are handling at this moment。 So in this diagram。

 we' are doing this star ping and this respond ping， ping， not pin。AtThese two points。

 right or some in this point， two points。 We have a log just to prevent this event being handled at two different。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_152.png)

In two different events at the same time。For most of time， you don't really need this log。

Because later on， we are going to implement tick components。 You are only。

 you don't even need to implement handle。 You only need to implement the tick function。

 But that's something we're going to talk in the next lecture。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_154.png)

就。Are familiar with this syntax。This is one of my favorite syntax in goal。

 so this is called type switching。Here this is an event， right。We don't know what Ti it is。

But we're switching according to the type。 And other than doing this switching， we're actually。

Define another variable that has the same time E and this internal E within this switch， this new E。

Has the type of starping event or endping event。Okay。

 so it's a type conversion plus a type switching。 If it's a starping event， we do this。

 If it's a responding event， we do responding。Respond to big。Right，Otherwise。

 we cannot handle event of type。 blah blah， bh。 What's the type， right。

 There's something that we don't know how to handle。 We can only handle these two events。right。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_156.png)

And let's see how is how star pin works。So， stopping。It has takes an event。

 star event and ping message， ping request， and sequence I D。We create a message， right。

 this is word how we create a message。The ping message our source is。See Da output as remote。

It's my own output， right？Then this event has a destination。

 This destination is where I need to send it to。So event has a destination。 that's my destination。

 Now I try to send it out。I try to send that out。Assuming it's successful。

 I record my start time in this time。Right，Then next sequence I plus plus so。

This is a logic of a regular component。 We'll see more example later。As long as you don't feel。

 this is totally no way to understand this good， no need to remember it。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_158.png)

O。Notify receive。 This is a component not ifify receive。 whenever we notify receive。

 we also retrieve incoming， right， we retrieve incoming according to a message type。

 either a request or response， we process them differently。Okay， we process。

So I typically have this naming convention， this is really Akita's naming convention。

We say process message。Handle event。ok。Still convention。

 there's no certain reason why if say process an event， handle a message。It's totally okay。

 but just to prevent confusion， we try to say process message， handle event。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_160.png)

Now， not if very receive， now how we handle process pin。Then basically， we create an event。 We know。

 current time plus 2。Right。say， two second latency。

We just scheduled this event to happen two seconds later。Then everything would put it in the。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_162.png)

Event handling。Process。데 한도。Then handle this message。 right here we're talking about this process。

 Re， Ping， respond， respond to the ping。Similarly， we create a message we need to say oh。

 we're responding to the original message sequence sequence I D。Then。We set a source and destination。

 Then we output port。 we send it through this output port。 So there's only one port。 So by the way。

 in Akita， the port is always bi directionional， right。

 You can send through a port and you can receive from a port if you want a unidirectal。Port。

 you just don't send through it。 If you， if you read only a port， you just don't send through it。

 If its right only port， you just don't。Take message from it， okay。So all logic is in the component。

Okay， so this is simple， right So when this event happens， send create a message and send it out。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_164.png)

Eventually， you say handle notify receiver again， whenever we receive this response， we receive it。

 we get the current time， we can find the corresponding star time， right。

We find a corresponding star time。 and simply pin。The sequence Id with a duration， what's a duration。

 What's a latency。Okay， super simple small example that explains to you how this。how how this。

Very simple Even driven simulation works。ok。This is not a full code。

 although I try to show you most of code is probably less than 100 lines。

 and theres still some bother play code to say how to create these components。

 how the connections are connected。There， the code are in。In a Kida repository， you can check it。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_166.png)

So wait a minute。 Then there's a problem here。 Do you see any problem。

I can I can tell you the problem is in this line。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_168.png)

H。No， it's。It not should be locked because the handle would lock everything。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_170.png)

Right，Deer means。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_172.png)

Extro this before it returns， right？So。It doesn't need to be locked， what's the problem here？

Do you remember what this function returns。Sent function returns an arrow。Right。あ。Wrong direction。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_174.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_175.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_176.png)

Thiscent。Sand returns a sand arrow。So。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_178.png)

In this example。In this example， were ignoring it。This is a small example。 It's okay。

 It's very unlikely to have network congestion。But what if in a more complex example。

 in a more complex code I sent， but I failed because。The buffer is being occupied。

 I don't have enough buffer。嗯。So if I want to support that。

I will return a send error whenever there's an error， if I send failed， what I can do。嗯。Pnic。

 no panic is not good， so。Yeah， yeah。 panic is not good because。I still need to continue。

 right theres it's so common that I try to send something but I cannot。 It's very common。

 I shouldn't panic。 It's not something I cannot reserve is we should actually schedule create another event。

 star another starping event in the next cycle and try again。Right。So。Then the problem is。

1 we can know that。One， we can know we can send out。 just keep retry。

 Keep retry every cycle until we can send out。 Maybe that's 1010000 cycle out。

So the notify available method can help。RightThe notify available matter can help， but just think。

I don't want to think about a solution， but at least to think about how complex that can be。

Right you need to consider this thing for every component and。

YouYou retry or you don't retry you wait notify available when notify available， you retry。

That's super complex， right， I don't want to implement this on my own。

So I can tell you MGBM at the early age。It's a pure event driven simulation。Very quickly。

 I cannot suffer from it。 I cannot tolerate pure event driven simulation。 I just think， oh。

 I really hope I wrote a psycho based simulation。So then。

 but I know even driven simulation has a advantage of。Its performance is higher。

 so I want to want to give up event driven simulation。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_180.png)

That's why I come up with a technology technique called smart taking， but before that。

 I say what's the problem with pure event driven simulation？



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_182.png)

So create event， create a lot of extra code。 It's annoying。

 You need to thank all the type of event that can happen， right。난。Event can have interactions。

Now where if you have two different events that should happen at the same cycle？Then there儿。

Changing different things of a component at the same time， it's really hard， really hard to reason。

About， right， and。When you need to retry， very likely you are just doing for many many researchers。

 computer architecture researchers their time they don't want to waste time。

 They want to do whatever the simplest they want to do。

 They simply don't want to use the notify available。 They just， oh， let's go with to retry。

 Keep retry until it works。 reschedule， reschedule。If you reschedule an event。

 it's even slower than cycle based simulation。Right。

 because you have to create this event and schedule it and schedule it putting in the heap。

 it's not free。It takes time time， so in this case。We try to use some method。

 better method to mitigate this problem， and it's called smart ticking。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_184.png)

So we call this event driven performance with cycle level difficulty or complexity。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_186.png)

So incyclb simulation， we try to do tick tick tick tick。For all the cycles， right。

Now it's super simple， but。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_188.png)

呃。But we say it can have slow performance。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_190.png)

Then how we can somehow implement a cycle based simulation。Within on top of the event driven。

 event driven simulation engine。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_192.png)

It's basically this， we do。When whenever I had no event。We let the ticker。

 Ter is the actual component， right， We simply let the tick。 So in this case， my。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_194.png)

Component only need to implement the one tick function。I only need to implement one take function。

When I'm done with T， I just simply take later。 take later is implemented in this way。I can。

Find the next tick according to my frequency。 I make the tick event at the time。

 then I don't care about secondary at the moment。 let's say schedule tick event does schedule tick。

 Now just schedule next tick so it will keep going on。Never stops。 So your if you write this code。

 your your simulation will never stop。 We need some external stopping mechanism。 For example。

 if you're running a program， you need to know like all the instructions are executed。 then you ex。

Explicitly。Or， I start exit at some point。Right， so don't don't expect your simulator engine can stop You will never because you always have take event。

Okay， so。What about we the advantage of event driven simulation is skipping some ticks， right？

 So when we can skip some ticks， how we can support skipping ticks。Then okay， I need too。So。

Let's talk about frequency later， let they say。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_196.png)

We say if we want to skip ticks， that means no kicks are not necessary。Right， those ticks。

 if we still take it。It's not useful at all。 So what are non useful tick， when take is not necessary。

 We say whenever the global state。Will be the same if you tick and not tick。 It's the same。

In this case。We can safely say this stick is not necessary and we can skip this stick， right？

So that means this tick， remember this tick is only applies to one component。

 So since it will only update the state of this component itself。

 that means if there's no state update。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_198.png)

If it doesn't update any internal state， any registered state。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_200.png)

会 say。We。We say iss safe to skip this stick。Or in other way， if we're not making forward progress。

Forward progress is basically a sign of。The sign of a forward progress means an internal state update or send some message out。

 successfully sending some message out if we do not have progress。This ticket is not necessary。

I can you accept this statement。你。In what case， a state at has no update。Two cases。

 as we said before， right if these component is fully idle。No request going through this cash。

In this case， we say we don't need to take this element on the other side。

If all the outgoing buffer are full。We， but we still want to try to something， send something out。

Thenhan unless the external environment is changed。

This tick continue taking will not make any new progress。

 will not make state change because we still want to send them out。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_202.png)

If we cannot send them out， we have no way to make forward progress。 in this case。

 the tick is not necessary。Okay， so can we test these two cases？Then definitely you can test。

 say outgoing buffer if they're full or if they're idle。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_204.png)

But it's actually very easy。If we have no progress in one cycle。If we， if we tick。

If you take a component， this tick function， this component can tells me。

 can tell the engine if a progress is made or not。Right， it's easy。

 very easy to detect as it's trying to make a state update。 But for some reason， if it cannot。

Then we say there's no progress in this cycle， so if we have no progress in this cycle。

 now we have to wait until either this case or this case are being resolved。

 then we can continue ticking。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_206.png)

Right， so these two cases are when when external environment changes， that means。Idol for idol。

 if there's a new task arrives。

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_208.png)

Task are from components， right， from another components。So if new task arrives。

 that means a new message arrives at this component。There may be a new task。

 then I need to wake up and continue working on things。On the other side。

 if one ports outgoing buffer from full to not full state。

It is full to at least a one buffer slot state。Remember， see how port implements this thing。 Now。

 this is congested when， if it's congested， now when this buffer。

 when this ongoinggon buffer becomes from full to not full state， then we can。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_210.png)

![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_211.png)

Schedule this。Now we can wake up this component and start the tick again。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_213.png)

ok。So in this case， we can rewrite a ticking component。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_215.png)

Handle function in this simple way。There are only。2。5 more lines in this code。

 the main progress part。Is new。 So this tick function needs to tells us me。

Need to tell me if progress is made or not。Is there a state update？

And is there a you send a message now out。 Did you send some message out。能。If made progress。

 I take later。 Otherwise， I don't take it。If I don't schedule a new take event。

 that means I put this component to sleep。오케이， 나는。We're running out of time and we're also running out of slides。

 so let's stop here， let's start to talk about smart taking in next two phase class。



![](img/f82727d71a2f1dd0a2eea62ed8aff0d1_217.png)