# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P11：-11-Nondeterminisms of shared-memory concurrency.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

In this session， I'd like to jump into a new topic which is about shared memory and its relaxed behavior and ordering。

So let me start with an example。 So in the previous lecture。

 we discussed that the spin lock should be annotated with what is called acquire and release orderings。

 So that means that the。

![](img/3d9859334b93c3a50952732df984ab76_1.png)

So let， so let me tell you in more detail in the log function， you are going to compare and swap。

The inner value， which was a boolean atomic bullolean。

 And this boolean value is replaced from false to true。And the ordering is acquired。

The meaning of this is unclear now， so I am going to tell you the exact meaning of this， but anyway。

 this is just written here as an annotation。And if this is successful。

 then it is going to break out and then return and at from that time you you have acquired the lock。

On the other hand， in the unlock function， you are going to just store the falls to the atomic boolean inside the the lock。

And here also， you are going to annotate the the store with release。Okay， so far so good。

 and the algorithmm of this spin log is quite understandable。

 it is atomically trying to replace first2。So if multiple servers are contending and they all want to acquire a log。

 only one log invocation will succeed because only one will replace the false value to2。

And also an unlock function is storing false to the inner boolean value。

 that means that if so by the contract or invariant， if you have a corridor log。

 then the inner value is true。And by setting the value to be false， then you're going to say， oh。

 Im done with accessing the inner data， so please allow the others thrust to acquire a lock。

 I am now releasing the lock。That's the meaning of this tooring the false value to the inner value。

So firstly good。And。But what is this meaning of this order acquire and release， So without it。

 what happens？

![](img/3d9859334b93c3a50952732df984ab76_3.png)

So it is a simplification of the above code into two stress and the Str1 and the spin astr just assigns the value to the inner data。

 and it is assigning false to the log variable。😊，And on the other hand。And in the other thread。

 it first acquire the lock by replacing the lock value from false2 and then read the data。

 And here we are simplifying the assumptions that the data should be for you too。

 We are just asserting that。So the challenge here， so this code will not work in its own。

 the challenge here is that instructions may be rewarded。So in the Str 1。

 the storing this 4822 data and storing fall to log。

 they are not ordered in the C programming language and other programming languages and architectures like arm and。



![](img/3d9859334b93c3a50952732df984ab76_5.png)

![](img/3d9859334b93c3a50952732df984ab76_6.png)

X，86。And as a result， these two instructions may be reordered。

And log equals first may be executed before theta equals 42。On the other end， in 2。

 the reoring also may happen， and if that happens， this assertion may occur。

Before this comparison swap。So this is actually happening in the real implementations of the architectures and program languages。

 so it is the reality we have to admit that。😊，And in the presence of those instruction reorings。

 the assertion may fail if any of the reors renderodors in thread1 or renderorings in thread2 any of them happens then the assertion may fail let me see why so here if the threat1 is viewered then equals force may be executed first and then this threat2 may resume the execution and it is trying to atomically switching。

 replacing the log value and then the assertion。However。

 the data has not been initialized because that once instructions are ordereded。

Data equals 42 are not executed yet， so we cannot assert that or assertion fails on this equality。

On the other hand， if threat2 is routed， then assertion data equals 42 may be executed first。

 and if it is the case， then the assertion fails because data has not been assigned yet by threat 1。

So the more of the story is that if any of the reing happens， the may fail， and as a result。

 we need to forbid such reorings。ARe and choir are such a men for forbidding these renders。

When log equals false is released， then it is not going to be rendered with the above instructions。

And if this lock that comparison swapwa is annotated with the cho， then the。

The instruction will not be routeed with the later instructions。



![](img/3d9859334b93c3a50952732df984ab76_8.png)

So so that's the reason why in this code these are ennoted with such reorings。

 this inner that store false will not beed with the above instruction and as a result。

 all the modifications or all the the references to the inner data will not be rendered with this unlock function。

Furthermore， in the lock function， it is annotated with acquire function and as a result。

 all the accesses， all the read accesses and right accesses to the inner data。😊。

After this log function， I will not be reordered with this s function。

So that's the proposal of this acquire and release。



![](img/3d9859334b93c3a50952732df984ab76_10.png)

So far so good。But。This is an example of re drawings， an example of a way to forbid the retors。

 so in this lecture from on we'd like to study how so how much instructions may be reed and how can we forbid such reors to our purposes。



![](img/3d9859334b93c3a50952732df984ab76_12.png)

So let me first summarize the problem， the challenge we want to address。

 The challenge here is non determinism。 Basically， instructions may be reed。

 and it introduces a lot of non determinism。 And as a result， we need to somehow。

IHave a way of reasoning about this nondemin them。So let me tell you in more detail。

From so in sequential programming， memory is just a mapping from location to bitete。 Here。

 the location may be addresses， but it does matter for our purposes。

 So memory is basically a location to byte mapping。😊，But the problem is that you。

 you can no longer be able to think of it as。Just plain storage。Because of these two nanodeminiums。

 so first source of nanodeterminium is very much expected。 the stresss are interleaved。

 so load and in instructions of multiple stresss are interleaved and as a result。

 they may have a comminatorarily explosive number of behaviors due to the instruction orders among multiple stress。

So this that's the first social of naatomism， but it is very much expected， by the way。

 because anyway， there are multiple threats and they are executed one at a time。 And as a result。

 we should be able to reason about the all possible。

In orderings or interlavings of the threat executions。

The second source of naattheism is a little bit more difficult to expect this the reoring that we discussed just before。

Load store instructions inside a single thread may be routeed。

And as a result the unin behaviors may happen。So in the previous example。

 I said that res may break the invariant of the spinock。

It may happen for other kinds of con programs， so I will show you the examples shortly。



![](img/3d9859334b93c3a50952732df984ab76_14.png)

So okay， there are two major sources of nondeomminism in the shared memory。

 and we need a strategy to tame those nondeomisms by forbidding on the unintended behaviors。

So each source， source one and source two have a way of taming。And for the source1。

 threat into living and the nondeterminism arising from threat into living。

 we are going to apply atomic instructions。Here， example is a concur counter。

 Let's it is a simpler example than spinlock。 And so I will show you。Of this。And。

Suppose that there is a shared integer that is initialized with0。And two stress。

 A and B are trying to implement it by one。So a programmer may write this。 Oh。

 let's read a pointer by a loading instruction and then add one one to the value and store back。Okay。

 so first good， but it is actually not a counter because of the interlings。

 so it may be possible that the thread execution are unfortunately interleaved and as a result the end result will not be 2。

 So it should be2 if it is counter because threat A and thread B are each incrementing the value by one。

 but if the thread execution is unfortunate， then the resulting value is one。 so heres the example。😊。



![](img/3d9859334b93c3a50952732df984ab76_16.png)

![](img/3d9859334b93c3a50952732df984ab76_17.png)

Srt A reads the counter value， which is 0 and Str B is also reading the counter value。

 which is also0 because it is not yet been incremented。😊。



![](img/3d9859334b93c3a50952732df984ab76_19.png)

And a is storing the value 1， which is0 plus 1， and B is also storing the value 1 because it also read the value 0 from the counter。

😊，And the end result is that the counter is one， which is very wrong for a counter。

 and it is actually an unintended behavior due to unfortunate scheduling。



![](img/3d9859334b93c3a50952732df984ab76_21.png)

So， let me explain why。So， the。The scheduler first executes the load instructions of the tattooooth rice and then stops between here。

Reading and store in between the scheduler stuffs， the executions of the stress。

And then it resumes the execution for it to stress。And this unfortunate。Unfortunately。

Inter living or unfortunate sleeping inside this at this just like at just this point result in the the unintended behaviors。

 So culture is not atomically incremented。 That's the reason why this program is wrong。

So in order to for such unintended nondeterminism， we basically want to mandate that scheduler cannot stop here。

 scheduler can stop here before the loading instruction or artist the story instruction。

 but it cannot stop at the between here， because if that happens。

 then the strange behavior of a counter may occur。🤢，So in order to do this。

 we should introduce an instructions that atomically read and write to the target location at the same time。



![](img/3d9859334b93c3a50952732df984ab76_23.png)

![](img/3d9859334b93c3a50952732df984ab76_24.png)

So it is usually called Atomic instructions or Readmod right instructions。

 because it reads and modify and writes back to the target locations。

There are a few instructions that do that， for example， swapwab， comparing swapwab and Fnet。

 but for this example， what we need is a Fette。😊，It is。

Doing the thing that is very much expected from the name。

 it reads or fetches the value and add1 and then store back to the target location。

 That's the meaning of fetchingnet。And if you use such atomic and readmodifier writing instructions。

The counter no longer shows the unintended behaviors because the scheduler cannot stop in between the read and write of the instructions。

So that's the reason， the reason is that in the implementation。

 the architecture provides also provides this rich modify writing instructions that is guaranteed to be executed and in in。

In atomically。So that's the reason why it can actually be implemented on top of these architectures。

Okay， by the way， so as a result， in any scheduling。

 either A or B may execute its instruction first and without loss of generality， we can say that oh。

 let's execute a first。😊，And if that happens， it will atomically increase the target location by  one。

 so counter becomes one in here。And B cannot interrupt the execution of A and execute its own instructions because a selection instruction is atomically executed。

😊，B is the same。 B is fortunate is atomically executed， so it cannot be interrupted。 and as a result。

 at the end of the execution， the counter should be2。

 which is the intended behavior of the of the avoid counter。

So more of the story is that threat to living may introduce magnetandatomism。

And that Bdeomism can be taed by what is called Readmod。😊，Write or RMW instructions。

The second source of natanism is， as I explained in the previous spin lung example， the retorings。

 the reoring happens because architecture and program languages try to perform optimizations as if it is a sequential program。

So let me tell you this， so if data equals 42 and flag equals 1 are just executed in a sequential program。

 then they are stores， independent stores to the different locations。

 so it is not at all a problem to reorder those instructions。

 because you cannot observe the reordering of data equals 42 and flag equals 1 here。

So so the architecture and the compilers have evolved to perform such optimizations because it is beneficial for it may be beneficial for the performance of the resulting program。

😊，But if it is a concurrent program， then the result of this optimization is may be of jobable。

 That is the problem we want to address in this in this。Session， basically。Okay。

 here this message passing example is simplified from a spin analog example。

 so spin is also a kind of message passing。 a thread， for example。

 a third A is writing a value for you to do data。😊，And it really is the lock。

And another thread may acquire log， and in that time the message has been passed。

 the message that the data should be for you to is passed from the release to another threads acquire of the spin log。

😊，And if that happens， the message is past and now in the another thread。

 the data should be for it too。😊，So this flag variable is basically similar to the lock variable in the previous example。

 and this data is the inner data that is protected by a spin log。

 So there are analogy between this message passing example and and the spin example。😊，Okay。

 as I told you previously these two instructions may be reored in the left right and the two instructions in the right side is also possible to be reed。

😊，And that's the reason why we need to protect it。Song。If the retoring in the left thread happens。

 as I said， flag can be set and flag can be loaded and the assertion may fail。

And if the instruction in the second straight may be rendered。

 then the assertion maybe is executed first and in the assertion may fail。Okay。

 so this is very much unintended behaviors for the purpose of this example。

 because in this example we want to use flag as the signal variable and we want to pass the information that the data should be for you too。

😊，From the first thread to the second thread。Okay， so that is basically the problem we want to address and such additional behaviors that is not observable in the intelligent semantics that is only possible due to reoring is usually called to relaxed behaviors in the literature of this concur programming。

😊，Okay， so the reason why this doesn't have a specific name is that threat inter living is very much expected。

😊，You are not going to。Itesis arises from of the fact that threats are executed in peril。

But this is different。 The rendering is arising from the fact that the underlying one time systems like architecture and compilers are performing optimizations。

So it is specifically named as relaxed behaviors that the。

 if a behavior is arising only from re drawingings。So。

 so the thread inter limit semantics is standard。 So and it is the actual。

 So it is this interimming semantics alone is quite studied well in academia， but。

 but the semantics due to renderorings have been studied only for the last five or 10 years。



![](img/3d9859334b93c3a50952732df984ab76_26.png)

Because it is the。The it is difficult part of the concurrent programming。

 and yet it is actually used in it is the reality that is implementable in the runtime systems。Okay。

 so it is problem。 the relaxed behaviors are problems。

 Then we somehow want to tame the relaxed behaviors。And the way to do so is， as I said。

 release an acquire and other kinds of ordering primitives。And。

The primary way to do so is what is called that if the offenses are inserted in between， for example。

 between de equals 42 or n flag equals 1， then it is guaranteed that the two instructions will not be ordereded at all。

😊，If。The fence is inserted at between the first and second lines of the second stress。

 then it is also guaranteed that these two instructions will not be ordereded。

And by inserting finances， we can quite restore the environmentvariant of this concur program。

 the data I should be for it too in at the assertion lines。😊，The other way is， as I explained。

 really acquire ordering because it。Because the release for this。

 the reodoring of the previous instructions and the and the release store and acquiring instruction for this。

 the reoring of the acquiring instruction and the later instructions。😊，And as a result。

 they are strictly ordered and weathering is impossible and the relaxed behavior is impossible。

If we are annotating them， we release and acquire orderings。Okay。

 that is basically the the last orderings of the message passing example。

 and actually there are a bunch of other kinds of rederings， for example。

 in for a C and C plus plus prong languages and including and also rust and other kinds of。😊。



![](img/3d9859334b93c3a50952732df984ab76_28.png)

![](img/3d9859334b93c3a50952732df984ab76_29.png)

![](img/3d9859334b93c3a50952732df984ab76_30.png)

Language level systems from language。Any combinations of access instructions can be routeed。



![](img/3d9859334b93c3a50952732df984ab76_32.png)

Low store and readM right， it doesn't matter all two instructions can be reed as far as they are not accessing the same location。

 so if you are reading from X twice， then they will not be reed， but if youre， for example。

 writing to different locations and they can be freely reed。

And it doesn't matter whether the instruction is store or load or readermodifier right。

 all instructions can be ordereddered。 That is the contract between the programmers and the compiler and the compiler is more than happy to reorder those instructions。

 it is actually happening in the real world。

![](img/3d9859334b93c3a50952732df984ab76_34.png)

![](img/3d9859334b93c3a50952732df984ab76_35.png)

And as a result， many kinds of strange behaviors may happen。

 so let's suppose that the x and y are all0 at the beginning of the execution and for this example in the left right X is assigned with 1 and then it reads y。

😊，And in the second example， Y is assign 1 and R the the。I mean， in the second thread。

 y is the sign 1 and then x is spread。😊，And the cache is。

 is it possible for these two rows from to read 0， that is the initial value。

At the at the beginning of the execution。So it is possible because the store and lows are possible to be routeed。

And also， these store and load are also possible to be ruled。And if that happens。

 then this R1 and r2 can be 0 at the same time because they are routeed and they can be reading the initial value 0 before storing the values 1。



![](img/3d9859334b93c3a50952732df984ab76_37.png)

Recall that this is impossible in the interlibing semantics because either x equals 1 or y equals 1 should be executed first。

 and if that happens， then if x equals 1 is executed first， then r2 must be 1， because x is 1。

 is executed before the execution of this r2 equals x。



![](img/3d9859334b93c3a50952732df984ab76_39.png)

But it is not。The case in the presence ofors， in the presence of reors。

 R random r2 can be routeed to the beginning of each thread。

 and then they can read0 from the initial value。

![](img/3d9859334b93c3a50952732df984ab76_41.png)

Similarly， there is a symmetric I mean， there is a similar behavior。

 a similarly looking behavior that is called a store hoisting。



![](img/3d9859334b93c3a50952732df984ab76_43.png)

In this example， it is reading the value here。And then writing to the Y。 It is reading Y。

 and it is writing to X。And the question is， is it possible that this our risk from the later store here and R2 risk from the。



![](img/3d9859334b93c3a50952732df984ab76_45.png)

AndThe the later store here。In the inter livinging stics。

 it is impossible because either the loading the left thread or the loading the right thread should be executed first。



![](img/3d9859334b93c3a50952732df984ab76_47.png)

And if the store if the load in the left thread is executed first。

 then it should reach from the initial value 0。

![](img/3d9859334b93c3a50952732df984ab76_49.png)

And this behavior is impossible in the intering semantics。



![](img/3d9859334b93c3a50952732df984ab76_51.png)

But again， if the instructions may be reordered。This y equals 1 and equals 1 can be executed before their corresponding companion read instructions。

And if that happens， it is possible that Ric is 1 and r2 is 1 at the same time。

 because x equals y equals 1 are already executed before the reading from these locations。

So in the actual architecture in， for example， arm。



![](img/3d9859334b93c3a50952732df984ab76_53.png)

This load hoisting happens about once in， once in， for example。Thous00 or 10000 times。

And store hoisting happens once in millions or 10 millions times， so it is rare， but it is happening。

 That is a problem。And it is worse that the， it is rare， and it is。

Because this relaxed behaviors is observbable only rarely。

 it is really difficult to find the bug due to these relaxed behaviors because in the test it usually work。

But this code will be deployed to the production and it will fail there if we are going to stress the systems with these relaxed behaviors under a heavy production workload。



![](img/3d9859334b93c3a50952732df984ab76_55.png)

So because of this， it is much more difficult to find such a bug， such a concursory bug。

And there are many other kinds of Java the the test cases like this。

 So Java Quaduality test case is one of the most important and one of the most well known test cases。

And you can click here。😊，And see what's going on there and what should be possible and what should be impossible in relaxed behaviors。

By the way， the three examples are wrong because it is written about 20 years ago。

 and it no longer holds in the modern understanding of the relaxed behaviors。



![](img/3d9859334b93c3a50952732df984ab76_57.png)

So please， for the purpose of this course， please make sense of the above examples。

Please understand what's going on with the examples and how they should be allowed in the by the possibleuterings。



![](img/3d9859334b93c3a50952732df984ab76_59.png)

![](img/3d9859334b93c3a50952732df984ab76_60.png)

Okay， so as I said， the， we can forbid the。They relax behaviors by inserting ordering primitives and。

The first way to do is release a acquire so restore， as I said。

 cannot be reored with all linear instructions and acquire load cannot be reored with later instructions That' is the reason why this message passing example will release acquire synchronization actually achieves the purpose of this example。

😊，two threads are properly synchronized so there cannot be the unintended relaxed behaviors。

Another way to forwardbi such behavior is， as I said， we are going to insert offs in between。😊。

And if that happens， all the instructions before this fence are ordered before all the instructions after the fence。

So similar to the above example， these two instructions are ordered and these two instructions are ordered。

And as a result， the unintended behavior will not happen for this example with sequentially consistent fan synchronizations。

So asF， what is called SF is forbidding any reoring across itself。

 and this relax is just for placeholder tag that says， oh， I don't impose no orderoring constraints。

😊，So this is this plane， there is no ordering constraints that is specifically applied to this store and loading instructions。

 but thanks to these fences， anyway， they cannot be routeed。Okay， so far so good。So far。

 we discussed the challenges of relaxed behaviors and how to ta them with this release acquired synchronization or a synchronization。

But we need to somehow know better about the semantics of these relaxed behaviors and orderings in order to build bigger systems。

 so this is just a small example， but in reality we want to deploy or large scale concurrent imp parallel systems that includes our large quite large data structures。

 concurrent data structures。😊，And in order to do so。

 we need to know the precise meaning of these robust behaviors and orderings。

 what is specifically allowed in architectures and program languages and what is specifically disallowed in the in the architecture and program languages。

And how to order them， how to order the relaxed behaviors with these fences or access orderings。

 that is the question we need to answer before writing a real world realistic and concurren data structures。

So， in the。There are roughly three three approaches to modeling relaxed behaviors and orderings。

 So I'm not saying that this is actual execution in the architecture or problem languages。

 but they are just modeling for programmers。😊，The runtime systems are executing concurren programs as if it is in the model。

 so for the purpose of concurren programming at the higher level。

 we only need to know about the models， not the actual implementations of the instructions。😊。

So the first model or the first approach is just disaligning the sharedmable accesses altogether。😊。

So there can be spinlocks， there can be some set of provided constructs or primitives for concurren programming。

 including spinlock mutax condition variables， etc。

 but it disallows the use of any other kinds of shared removal accesses。And if that happens。

If there is no short material of access， then it is guaranteed that there will not be any relaxed behaviors。

And as a result， we are effectively killing all the relaxed behaviors。But there are two problems。

 The first problem is that shared renewable accesses are essential。

 so they are actually deployed in the your world production systems。

The reason is that the SMs are I mean， they are essential for performances。

Less behaviors are there for optimizations， and if we are going to deppose or remove all the optimizations that is done by the runtime system。

 the performance will be dropped。We need to tame the relaxed behaviors in such a way that it will not reduce the performance too much。

 but still it achieves the synchronization that is necessary for our purposes。

So the approach1 is too slow or it is not inefficient sufficiently。

And the approach2 is constraining executions by what is called axioms in that axiomatic semantics。

 we are going to construct a execution graph for each execution。😊。

And you're going to have many actions that is describing what is intended and what is not intended behaviors of the execution。

So it is there are two problems。 It is less intuitive than the operation semantics that you you may learn from the program languages course。

So it is just deciding whether complete execution is valid or not。

 and as a result in my understanding， it is very much less intuitive than the operational ses。😊。

And the second problem is that it allows what is called autose behaviors。

 which is a very bad behaviors that cannot be easily adopted by the real world programmers。

 and this bad behaviors is allowed by this xxiomatic semantics。So so it is a problem。And as a result。

 all the original principles are not valid in the amatictic semantics。

In this third approach or certain model is the what is called the Pro semantics and we are going to model these realor and behaviors with operational semantics so and the Pro semantics is a major step towards this effort。

😊，And， and we are going to study these promising operational semantics at the last lecture。

So to summarize today's lecture， we studied the problems or non determinence studies arising from concurrent programming。

 and one is thread into living and the other is retorings。

And we saw the examples of those and how to tame those two kinds of nondeminism。

And for taming the relaxed behaviors that is due to the possible reorings。

 the second also of done determinism， we have fs and excessorings。😊，And。

For the precise semantics of those， those relaxed behaviors and ordering。

 we are going to study the promising semantics from the next lecture。

