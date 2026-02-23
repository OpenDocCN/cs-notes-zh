# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p23 Lecture 22_ Speculation (Spring 2025).zh_en -BV1Xc19BnET7_p23-

![](img/8c764c83ba795ad9ea62ac75a09d1ed1_0.png)

Okay， let's get started in this lecture we're going to cover speculation and our focus will be especially speculation and parallel machines。

 parallel machines meaning multicore multiprocesor or multi threadreaded machines。

 this is another fascinating topic that has fascinated many people in the world and many researchers have done a lot of research on this and in fact my PhD thesis was on a topic called Runhead execution which is essentially speculation except it was not on a parallel machine。

 although it could be adapt to a parallel machine and other people later adopted to it in a parallel machine as we will discuss with the concept of dual core execution。

 but basically that's the idea that we're going to focus on today speculation。Oh。

 looks like we're having trouble。Speculation basically these are some of the readings that are required。

 soy at all multicar post a seminal paper on speculation。

 we will cover that Zos dual core execution work we will cover that again later on is there are two aspects of speculation speculation to improve single threaded programs and speculation to improve parallel programs the first two papers cover the aspect of speculation to improve single threadded programs how can we basically use speculation to parallellyze a single threaded program the second two papers cover aspects of using speculation to actually improve the app parallel performance parallel application performance one is transactional memory which is actually used in some systems today and the other speculative lock e basically transactional memory done underneath without support from the programmer at least without much support from the programmer。

And there are a bunch of recommended readings that I have， one is actually Stean。

 that should be Stean at all， a scalable approach to thread levelvel speculation。

 one of the earlier thread levelvel speculation papers。

 the other one is dynamic multithreading processor， Hymary and Ri calls paper， and there are many。

 many others that I will talk about during this lecture that I hope you will read about。

So let's the focus of this lecture is speculation and parallel machines what is speculation speculation is doing something before you know it's needed。

 this is the most general form of the speculation basically before you need something。

Do it for example， before you know that youre gonna fetch this instruction， fetch it。

 and you need that to keep the pipeline full right in a single threaded machine。

 So this is mainly used to enhance performance in the single processor context。

 you know of many techniques and you've studied many techniques previously especially if you have taken my class 447。

 computer architecture， which is whose lectures are available online。

 you can actually go back and look at branch prediction， for example。

 branch prediction is a form of speculation in the context of single processor you fetch the next instruction before you know that you should fetch that instruction that's the ideal branch prediction to be able to keep the pipeline full。

 Data value prediction is another concept。 When you load a data value。

 maybe takes it takes a while to load the data value。

 Why don't you predict that value so that you can speculatively process the dependent instructions and this breaks the data dependencies between instructions and enables。

Instruction level parallels。 Of course， you will need to verify the speculation that you did in branch prediction and data value prediction。

 right if you mispredicted the branch when the branch actually resolve。

 you need to recover from that mis predictiondiction such so that by redirecting the fetch to the correct destination or correct target of the branch。

 Similarlyly with data value prediction， if you mispredict the data value。

 all of the dependent instructions may be executed and you will need to recover from that by actually either reexcuting the dependent instructions or flushing the pipeline and restarting just like you would normally do with the branch prediction prefeting is another form of speculation。

 basically the process requests an address before it knows it really needs that address right could it could figure out based on the address patterns that are happening so far。

 For example， if the program is generating。If the program is actually generating addresses that are predictable。

 then the processor itself can start latching onto that address pattern， the prefeer。

 let's say the program has generated a plus1 a plus2 to memory to access， prefeer can start saying。

 oh， I expect the program will continue accessing。In the streaming fashion or striding fashion。

With a stride of one cash block。And the prefeer can start prefeing these blocks， right。

 and it's a form of speculation because the prefeer just guesses。

That the processor will continue accessing memory in the streaming fashion。Well in this case。

 you don't need to recover from it potentially right because there is no harm done。

 this is purely speculative whereas branch prediction normally is not purely it's a purely it's a speculation mechanism but it does affect correctness if you do not correct the outcome of the branch so these are some of the techniques we had considered when we covered speculation and single processoror context today our context will really be parallel machines or multiprocessors Basically what are the speculation techniques to improve performance on a multiprocesor system。

😡，If you would like to learn more about the single Pro context。

 I would encourage you to go and watch the Brach prediction lecture from 447。

 I believe it's lecture 10 or 11 and it's on YouTube。

And data value prediction and prefeting are also covered in lectures in 447 and you can find those lectures on YouTube as well。

 or I'd be happy to discuss that in a recitation。So let's take a look at the multiproster context。

 multiproster context， again other there are many speculation approaches， thread level speculation。

 transactional memory and helper threads， but we're going to examine many others so basically the idea is to speculatively paralyze the programs in a multiproor to improve performance。

To be able to do that， we would like to execute threads unsafely in parallel。 unsafely。

 meaning we do not know whether or not we should be executing threads in parallel。 right。

 That's the idea。😡，Thres can be from a sequential or app parallel application。

 This is the most general form of speculative parallelization。

 we want to parallellyze either a single thread application or we want to expose more parallelism from a more parallel application。

😡，Well， once you start executing threads in parallel without knowing that they can be executed in parallel。

 they might actually have data dependencies right， you need to somehow check for these data dependencies。

 let's say you've generated this thread zero， this is a thread that's executing and you start specly fork thread one。

 and you continue executing threadread zero。😡，And you do not know whether the thread1 has a data dependency with thread0。

 right before you start executing it。 But somehow this thread1 may write to a location that's later read by the thread 0。

 which means that they shouldn't be executed in parallel， at least purely。

 So hardware or software monitors for these data dependence violations。

 And once it detects that if they theres an ordering， data dependence ordering is violated。

 then the offending thread is sququaed and restarted right for example， this thread actually another。

😡，This is one form of data dependence speculation， that violation。

 it may be that the threat doesn load。And this thread may be logically earlier in the program。😡。

And this thread should have done a store and this thread did the load earlier。

 but this thread does the store later。 This thread got the wrong data value because it did the load much earlier because it was executed in parallel。

 if it were not executed in parallel the thread would actually this load would have been done later than the store and the hardware or the software somehow detects this and it detects this data dependence ordering violation this load must have been done before the store but because of speculative parallelization of these two threads this store happens later than this load as a result there is an offending thread offending thread is thread one in this case because it's logically later it should be logically later but it got the data value that stad that was not updated because it executing too early So this thread can be squashed and restart This is one way of actually monitoring and recovering from data dependence violations Why because this threads execution was unsafe we start executing the thread earlier than we new。

Whether or not it had a dependence across dependence to this part of the program。

If there's no data dependence， if you actually spawn the thread and it turned out that least happened to be totally independent。

😡，Then the thread commits， so one example over here is that basically let's say you have a single threadd program。

 you're executing it and you have a function call right and you execute that function call。

 normally you would execute in a single processor context。

 but what you can do is you can actually launch another thread。Thread one。

 let's say to execute this function called on a separate processor。

 and this thread actually continues from the return of the function。

And if this functions is completely independent。Of this threat。

And there is no data dependence violation detected， then you can commit the results of this threat。

 somehow you need to merge the results into the architectural state， but actually you can commit。

 right？😡，Because there is no dependence， so that speculative parallelization works in that case if you're doing a function。

 for example， that's for cleanup tasks that the processor actually doesn't need over here with this thread。

 this could potentially happen。Or if you're doing a function that whose results will be needed much。

 much later in the program， you can execute that function in parallel early on right now with the code that's going on that's not dependent on the function。

 And then later this function's results will be available to other。😡。

Instructions that need the results， right so this is one case where it's speculative parallelization can work。

 right？😡，For example， if threats basically if data depends are not violated， then the thread commits。

 the speculative thread commits， and if threats are from a sequential order originally that sequential order needs to be preserved if you're actually taking a single thread and parallellyzing it speculatively。

 the sequential order needs to be preserved such that thread commit one by one in order and we will see this。

😡，Basically， when threads execute specly， there needs to be intratread value communication。

 let's say you've decided to launch a thread on a function call over here。

Then these threads need to communicate somehow and this can happen via register or memory and let me talk about the different types of communication briefly because this will come up over and over in different kinds of thread level speculation mechanisms if the threads need to communicate through the registers。

😡，Basically this needs hardware support between processors right actually the other one needs hardware support too。

 but the fundamental difference between register dependencies and memory is dependencies between threads are known by the compiler。

😡，The compiler， for example， when it's compiled the program， it knows。😡。

Let's let's say you have a sequential program。Initially。

 and this chunk of the program is writing to register too。And this chunk of the program。

 let's say this is a function call， you go to function call。

 this chunk of the program is reading from register to， right？And theyint something with it。Now。

 if you execute this function call separately as a separate thread。

Then this dependence needs to be satisfied， right， this R2？

Actually is executing on the separate third over here now because function is actually executing in parallel with whatever comes after the function。

 destination of the function or return。Point of the function。And while that function is executing。

 this is reading R2 and this R2 is dependent on the other thread that was executing over here， right？

😡，So this can be detected by the compiler， that's the fundamental difference between registers and memory Reg dependencies can be analyzed and detected by the compiler because they're static。

 right they're not dynamic。😡，Of course， they're dynamic in the sense that they're dependent on the branches。

 right that's one difficulty。😡，But you know at least whether or not you may have a dependence。

Or may not have a dependence。 only the branch determines that dependence。

 but register addresses are known statically。Depenencies are known statically。

 so this register communication when it happens routine threads can be initiated by the producer of the register。

 which is this one or the consumer of the register depending on which one executes first right the compiler can say oh。

 this is dependent you need to wait for the value of the register or I did this wrong basically register to is used as a source over here。

Basically compiler can say， oh， you need to wait for the value of this register。

 it's coming from somewhere。😡，Or you need to send the data that value of this register because somebody else will need it compiler after analyzing that quote that can put in these hints。

If the consumer executes first， let's say this is a consumer thread thread1。

 and let's call it thread0。 if this one executes first in parallel with the previous thread。

 let's say， and this might happen if you parallelze aggressively。

 then the consumer stalls if the value is not ready in the register。It knows that it needs to wait。

 but the value is not ready in the register file。😡，And the pursuit producer。

 when it executes its forwards， so how do you know whether or not the value is ready。

 well basically there you can communicate with the register file and register file can have ready eventss for each register in the register file。

 you can add a ready bit for that particular threat in the hardware。😡，And the ready bit set。

If the value is available。If the and ready bit is not set。

 if the value is not available yet for when this threat starts。😡。

If the value of r2 has not been produced。😡，で。Ry bit for that R2 will be initialized to zero。

 and only when this producer executes it can basically set that ready bit to one。

So these ra bits are also called full empty bits。And these are actually needed to do synchronization between threads at a very fine grain。

 basically whether or not the value of a register has been produced yet。

And the producer says the Ray bit consumer basically waits for the Ra bit to become one。

 this is basically data flow between and full emptybits。

 one of the early introductions of this was Burerton Smiths，😡。

A seminal paper on a pipeline shared resource MIMD computer。And I'd encourage you to read that。

That is a good example of the use of full empty beds。

In the heterogeneous element processor that Burerton Smith designed at the time。

 and this is ICPP in 1978。But this is an important construct for communicating registers between threads。

 you can have full emptybits and memory also actually this is an important synchronization construct that enables one thread to produce a register or memory value and another thread to consume it and this is how you can synchronize it basically this is a synchronization where you've already bit。

😡，Is it synchronization variable？That can be supported in hardware and if you're doing thread level speculation。

 you should support this in hardware in registers， right？Okay。

 so you can read this paper for good use of full emptybits。If the producer executes first。

 on the other hand， basically producer simply writes the result and send the rate bits and when the consumer actually executes。

The consumer reads the value。And the producer can continue after setting the rid bit， of course。

 and we will see one example of this with the multiscalear processor。

 multiscalear processor actually communicates between threads this way。

 there are full emptybits in the register file and when a task as they call it produces a value that needs to go out to some other processor some other processor and a compiler analyze a task to know whether or not the value needs to go out to some other processor。

😡，Then the task when it produces the value， it basically sends the value across the register file ring and another processor that's needing that value captures it in its register file。

 but we will get that I'm getting ahead of myself， but this another reading that you should definitely do this actually required reading multiscalear processors in ISca  in 1995 by Sohi at all。

😡，Isca 1995 and this is one of your required readings。

 this is one of the seminal examples of thread level speculation done in done a hardware software cooperative way。

Okay， and they communicate registers values between processors this way， Okay。

 I've already said that this can be implemented with full emptybits in registers。😡。

Memory communication on the other end is very different from registered communication。

 the compiler has no idea usually about memory dependence。

 at least the difficult memory dependences the compiler doesn't know。😡。

Why does the compile not know because the compile doesn't know the memory address of operations and not everything is statically alyzable because of this for example if you use pointers in your program and dynamic memory allocation you allocate memory to a pointer and you allocate some other piece of memory to a pointer and you can assign any value to a pointer as a result these dependencies are dependent on the dynamic inputs to the program and how does the program behave based on those dynamic inputs and the compile cannot analyze that dynamic execution。

😡，As a result， memory communication is usually harder to satisfy between these different threads in speculative parallelization。

But if you're specly paralyzing the program， you would like to know if there's a store here。😡。

And if there's a load here。If this store and load actually overlap。

 it's because if this load actually overlaps with this store when you're executing this in parallel with this portion of the program。

😡，You would like to know that this load actually gets the correct value and it actually doesn't get this tail value。

😡，And similarly， there may be stores here and loads here。

 and you need to know if this store A is overlapping with this load B。

 because it may be that you don't want the store A done before the load B if they're actually overlapping with each other because this is from and logically later。

😡，Part of the program。So you need to preserve the dependencies， obey the dependencies。In general。

 in thread level speculation approaches， a thread performs loads speculatively and gets the data from the closest predecessor threat right？

😡，And it keeps a record that it has read the data。😡。

It keeps this record in the L1 cache or another structure， and we will see some examples of this。😡。

On the other hand， stores are also performed speculatively when a thread doest store。

 it doesn't wait。 when a thread does load， it doesn't wait normally Also， as as I said earlier。

 Basically， when a thread doest store， it may not be the oldest thread in the machine yet。

 So it buffers the update while it's speculative while it's not committed yet。

 basically places the update in the right buffer or in the L1 cache。 And when it doest store。

 it checks for successor threads for premature reads。

 So this implies an ordering between the threads， right you have the thread 0， thread 1， thread 2。

 threadread 3， thread 4， thread 5。 It can all be executing in parallel， but there's an order。😡。

Which is a sequential order。If you're actually paralyzing a single threaded program and executing them in parallel。

 in this case， you're taking these threats that are supposed to be sequentially ordered or chunks of execution that are supposed to be sequentially ordered and executing them in parallel。

Thread4， thread5， and looking at checking if they actually have dependencies on loads and stores。

 if they actually violate any load store dependencies。😡，So every threat can do the loads。Spulatively。

For example， assume that the loads are actually independent of any store。

 that could be one assumption。😡，And keep a record that they've actually read the data， this load。

 for example， loads from address A and keeps a record that， oh， I read from address A。

And this can be done in the L1 cache by setting a bit， saying， I've read the data， right。

 Sp a little red。And this thread zero later on， for example， executes a store to location A。😡。

At that point， it buffers。The store。And it also checks if there's a successor that has already read location A。

 right？If I successor did a premature read。Well， in this case it did right this load A happened before the store A。

 whereas it shouldn't have happened in that order， it's because these are logically sequential threats。

😡，Just because we've executed them unsafely in parallel， this load happened before the store。😡。

So we need to detect that dependence when the store actually executes。

 and that's when the dependence is detected。The store basically somehow figures out that figures out a destination load。

😡，Happened earlier where the shouldn't have happened until the store finished。

So if the successor basically did a premature read in this case， it needs to be squashed， right？

Squashing me。The thread needs to be restarted， perhaps。

 and maybe everything else needs to be restarted because you have now a data value dependence that was wrong。

 because some other thread may have read， some other data value that was produced by this load later on。

 and it got executed with the wrong data value。😡，Basically。

 you typically squash the offending thread and all of the successors when you detect such a data depends violation。

 when you figure out that this thread spec read the wrong value。😡，Well。

 you could do something smarter but complexity increases in that case right you could actually figure out only those dependent instructions that have gotten the wrong value and execute and you could selectively re- execute those instructions that are dependent right now this is a tough thing to do it's very hard to figure out selectively which instructions need to be re executed and people have looked at this problem and they found some solutions but in general it's a difficult thing to do。

😡，ok。So I've given you a lot of the concepts actually in thread level speculation。

 basically when you take a single threaded program and paralyze it unsafely。

 you run into these dependence issues and the key dependence issues are register communication and memory communication and you to satisfy those and memory communication needs to be satisfied dynamically。

 as I said over here。And this kind of communication can happen over here also right it doesn't need to be with the oldest threads。

 this is in this case the oldest thread and the youngest one over here。

But it could happen between Tread3 and Tread4， threadread3 Tread4 can do a load a。

 and later Tread3 can do a distort to load A and this needs to be detected and Tread4 and all successors need to be flushed or squashed。

Okay， dependence I versioning only true data depends violations should really cause a thread squash。

 right， it makes sense。😡，There are types of dependence violations。

 let's say you have in this case I denote load a and store a， this is the later thread。

 let's say the earlier thread does a load to a later thread does a store to a in this case it's really a name dependence so the hardware should really be able to handle this meaning there is really no dependence here。

 it's really an antidepend， it's not a true dependence right。Basically there's no reason for。

 let's say you have threadread0 and Tread Tread1， this does a load A and this does a store a。

 and this does a store earlier than this load， you should definitely ensure that this doesn't get the value coming from this store。

 right？And you should be able to do that by eating the name depends and how do you eliminate the name depends。

 well you do a register renaming right in this case these are not registers so you can do memory renaming。

Okay and well see one structure that does memory renaming whenever you would like to eliminate not two dependencies right after write in this case right after write dependence or right after read dependencies well in this case I guess read right after read dependence。

 sorry。😡，You can eliminate this dependence by renaming。these locations。

 because essentially the store is really creating a new value which just happens to be in that location。

 right A， you could actually think of the store killing the old value in that location and creating a new value so there's no dependence really。

 it's really a name dependence because we didn't have enough memory locations， for example。

 or you could actually create a new version of that memory location if needed， okay。

 the second one is that right after right dependence if one thread is doing a store to a and the next thread is actually doing the same store to a the hardware again should ensure that the stores appear in order。

And we've covered the subject earlier right if the true dependence happens when the older thread is doing a store to a memory location and when the younger thread is actually reading from that memory location with a load。

 in this case， if the younger thread actually read earlier then the store happened。

 then this is true dependence needs to be detected and it needs to cause a squash because the thread that's younger read the wrong value。

😡，So name dependencies in general， name dependences。

 the first two depends can be resolved using versioning basically every store to a memory location can create a new version。

 as I just described earlier， right， because the store is really using that memory location as an address。

 it's really creating a new value。😡，And once you have different versions。For example。

 whenever this store writes， it creates version 1， whereas this load is loading from version 0。

 so this load can get the correct value because it's really reading from version 0 at the time this thread is executing you have version  zero。

When this thread is executing， it creates version1 of that location。

 when this next thread is executing， let's say it doesn't store a， it creates a version 2， right？

And this thread actually creates all the version once this thread creates version twos as a result。

 there the name depends can be eliminateumd。Of course。

 this requires some hardware costs to tag the memory locations with the different version numbers and one example of this is described in this paper。

 speculative versioning cache in HPC 1998， and I encourage you to read that paper。

 this is one way of handling name dependencies that are not true dependencies okay。

The other question when you actually design speculative parallellation concepts is。

 where do you keep the speculative memory state？And let's take a look at that basically what is speculative memory state。

 whenever a threat specululatorative does a store instruction。

 you don't know whether that store instruction should actually be committed to the architectural state right because this thread may not be the oldest thread in the machine yet in the sequential logical order。

😡，Which means that somehow you need to buffer that store in instruction well there are two approaches to this where do you put this store。

 you can put it in a separate buffer， for example， you can put it in a shared queue store queue that is shared between threads right and the idea is whenever you do a store you have a buffer。

😡，And the thread puts its version number， for example， and thread ID。

Into this buffer and another thread later on checks this buffer to see if there's a store to get the data from right if this threat is the older thread。

 for example， if there's a younger threat that's executing， let's say it does load。

 it basically searches the store buffer to see if there are stores from an older threat。

To the same location， right？So this is the store bufferer approach， separate store buffer approach。

Now this is an additional data structure， but this is doable certainly。

This is very similar to the address resolution buffer in multiscalealar processors that we will cover because the address resolution buffer is a way of ensuring that store load dependencies are satisfied in multiscalear processors this is also similar to run ahead cache and run ahead execution that we have covered in 447 the basic idea over here is in run ahead execution you specully executing the program and while you're specully executing the program some store instructions actually right speculatively to memory you don't want to expose them to the architectural state because remember runhead execution is purely speculative and the mode instructions that happen in run ahead mode get their data values from if their dependent store instructions are executing runhead mode they get their data values from this run ahead cache。

And if you're interested in this more， you can read the runH papers that were assigned or that were discussed earlier。

On the other end， you can not have a separate buffer like this， but you can decide to。

Place the speculative data， speculative store blocks in the Alc in this case you can mark basically in the tag store。

 you have one additional bit saying speculative bit right speculatively modified bits and you will see this example when we talk about thread level speculation。

And this specully modified bit basically says that this cache block was specly written by this thread。

And normally， this is not visible to the other threats， right？😡。

You need to make them nonspeculative when the thread commits and you to invalidate them when the thread is actually squashed now basically what you're doing is you're really putting the store buffer into the cache and integrating with the cache。

 but you need to ensure that cache still operates correctly。😡，And this modifies the cache。

 but maybe you don't need an extra store buffer if you actually want to keep the specular memory state。

 so they're actually interesting tradeoffs related to where to keep the memory specular memory state and I'd encourage you to think about it。

 especially when we come to multiscalear and different kind of approaches to thread level speculation。

😡，Okay， I will now delve into speculation to parallelze single threaded programs。

 but before I do so I will take a quick break and we will get back to this very soon。😡。



![](img/8c764c83ba795ad9ea62ac75a09d1ed1_2.png)

![](img/8c764c83ba795ad9ea62ac75a09d1ed1_3.png)

Okay let's continue on where we left off。 we're going to talk about speculation to parallelize single threaded programs。

 That's part of the speculation lecture， and then we're going to focus on speculation to improve the performance of parallel programs Now this is a topic that has fascinated many people and there are many readings that I can recommend over here and these are some of the reference readings and all of them are required Well that's a joke the more you read the better of course。

 it's always good to read and understand the ideas and evaluate the different tradeoffs between the ideas this could give you a lot of good project ideas and this could actually enable you to do great research as well so I would actually recommend reading all of these papers。

 but some of these will be required， as I've already told you earlier and as we will put up on the website but I'll try to cover some of these these are the reference readings over here but there are many。

 many other readings that we can talk about。So the basic idea of taking a single credit program and paralyzing it on multiple hardware contexts is called thread level speculation。

😡，This is also called speculative multithreading and there are many examples of it。

 One example is dynamic multithreading， which basically I have briefly discussed。

 and I will give this reference over here， but that's an example of it a accurate and risk call。

I wrotete a paper in microcro 1998 about a dynamic multi threadreading processor。

This is one example of speculation which we will not cover in detail。

 but I wrote it over there because it's an interesting approach also。

 the basic idea is whenever a threat gets a function called，😡，Launch the function call on a separate。

Hardware context， so core0 executes the regular thread， core1 executes the function call now。

 and corere0 doesn't twiddle its thumb at that time。

 basically continues executing from the return points of the function call。😡。

So if you think about code， you have some code here and you have a call here， basically this call。😡。

Takes you to some function block and this function block gets executed over here and the next instruction that comes after the call。

 let's say it's an ad。The next block gets executed on this core zero right。

This is basically the function level speculation at that function。

 you start a thread and if there's another function within here。

 you start another thread right and if there is another function you start another thread in a separate hardware context so that's how you dynamically multithread the program at the function level now what happened what they did over here was if some of the values were not available。

 for example， were predicted to be produced by this function， they basically predicted the values。😡。

And actually， they predicted the value of the return value of the function。Return， register value。

Because function usually produces a register value that's returned。And if that's the case。

 then that register value is predicted and this return point is executed with that predicted value at the end of this function。

 this function generates some results。😡，And it also generates the register value。

 that register value compared to this predicted value and result if the prediction was correct。

 then the execution here was correct right if assuming that all of the predicted values were correctly predicted right all of the values that were produced by the earlier part of the program that must have been executed before the return point were correctly produced so there needs to be some checking to ensure that that happened and eventually the results get merged and they merged these the results using something called pre result buffers and I'm not going to go through that in detail this the more complicated part of the mechanism but that's。

They were able to parallelze programs at the function level this way。This one example。

 the other way that this particular paper paralleled the programs us with loop iterations。

 so if you have four loop for example。What you can do is you can take when you get to the beginning of the iteration。

 you can launch the next iteration in another processor。

 so basically you can specully say iteration  zero goes here， iteration goes1 goes here， core zero。

 core1， iteration two goes here， core2 and iteration three goes here， core3。

 as many chs as you would like。And this is another form of speculative parallelization， right。

 Basically， you can actually predict the inputs to the iteration potentially also。

 even if there are dependencies between iterations。 and you， of course。

 need to do everything else I said earlier， you need to ensure that the data dependencies。

 true data dependencies are correctly satisfied and the iterations execute correctly。

 if there is a depend violation， iterations are actually iterations as subsequent iterations that saw the dependence violation are actually squashed。

 So this is the idea of speculative multithreading thread level speculation。

 and people have especially looked at multithreading when you get to a function call。

 and multi threadreading。 when you get to an iteration。 Basically in a loop， you can。

 you can try to parallellyze the different iterations of the loop speculatively。

 and we will get back to these concepts over and over in this lecture。

But the basic idea Ive already given you， right， divide a single instruction stream speculatively into multiple threads at compile time or runtime。

 right？😡，And the G is specative。And you can execute speculative threads in multiple hardware contexts。

 as I've shown over here。😡，And eventually you need to merge the results into a single stream。

 for example， this function call needs to merge its results into the single stream。

 such that the results appear as if you've executed that single instruction stream sequentially that's the key idea。

😡，And of course， hardware software sometimes cooperatively need to check if any true dependencies are violated during the speculative execution and ensures the sequential semantics。

 because remember， we have sequential semantics in the single threaded program and we need to ensure that semantics。

 were only under the hood。😡，Pallyzing that single threadd program by utilizing the multiple hardware contexts that are present in hardware。

😡，So one potential way of actually doing this is threads gives me assumed to be independent。

 for example here， the function call is another executing another thread and the return point of the function is executing another thread。

 let's assume that they're independent。😡，And you can actually ensure use value and branch prediction to break the dependencies between threads in this case。

 the return value of the function can be predicted such that the quote after the return point can be executed assuming that it's independence right you don't need to wait for that data value waiting for that data value could be another option but that reduces the parallelism between the threads right if it's predictable it may be much better to predict that value that this thread needs to continue execution So basically you can use value prediction to break dependencies between threads and similarly you can use branch prediction too Of course you need to verify such predictions in the end because remember this' a single instruction stream that we specully parallellyzing and you can actually。

Vify these predictions by executing a safe version somehow， right。

 maybe always execute the safe version and also by checking some invariance right and we'll see one of those approaches and you can think of other approaches。

😡，So one of the earlier works in thread levelvel speculation was actually done here at Carnegie Mellon。

 this is Greg Stean's paper， a scalable approach to thread levelvel speculation from Todd Maray's group and this shows an example over here basically I will go over this example on the slide this is a hard to perize loop if you would like you have a while loop let's assume that this while loop executes many times basically you have two axises。

 one axis loads from a hash table using one index and the other axis actually writes to this hash table somehow and some value that's produced。

Now if you would like to parallelze this program while loop as a programmer。

 you have no idea if one loop iteration， iteration1 is independent of the other loop iteration right it may be such that the first iteration is writing to an index that the next iteration is reading or first iteration is writing to an index that 25th iteration is reading right but you have no idea because these indices are dependent on the data values input to the program。

 and as a result as a programmer it's very difficult to parallellyze this program by breaking the loop iterations to be executed as on different course。

 different threads right？😡，So but using pre level speculation。

 what might happen is basically the idea is to specully execute。

Consecutive iterations and consecutive processors。 So processor one executes iteration one over here。

 right This is called E1， let's say。Prorossster two executes E2。

This is the second iteration Prose3 starts executing E3， Pro 4 starts executing E 4， right？😡。

And these all execute dynamically in parallel。😡，And basically these dependencies are kept track of right for example。

 Proster  one reads from hash3， but that's okay， no other Pro has written into index 3 Proster 2 reads from 19 Proster 3 reads from 33。

 Proster 4 reads from 10， so the fourth iteration reads from index value 10。

 it turns out the first iteration actually writes to index value 10。

So this dependence needs to be detected somehow， so this fourth iteration cannot execute in parallel with the first iteration。

 really， right？😡，Because there is a dependence over here on the fourth duration actually should get the correct value。

Whereas it may execute and get the wrong value。😡，Because here， if you look at this in time。

 it's got the fourth iterations hash 10 read executed earlier than first iterations hash1 store。

St to index 10， index 2， which is 10。So in this case。

 this violation needs to be detected because in the sequential order of execution of this while loop。

 the first iteration should execute before the fourth iteration。

 so that's the idea in treadlow speculation， how do you actually detect this violation？😡。

And the idea is。You to use a coherence protocol to detect this violation， we'll get back to this。

 but assume that there is no violation， assume that dynamically these values turned out such that no thread wrote to an index that a later thread actually read。

😡，In that case， all of these threads attempt commit at the end of the iteration。

 and this attempt commit function， basically they check if there was a violation。😡。

If there is no violation at all， violation meaning the data value read by this thread was actually written by some other thread and this thread actually got the wrong value because it executed specully earlier if there is no violation then these threats can commit and this commit needs to be in serial order actually because you need to preserve the sequential semantics of the program remember this a serial program again。

😡，And these threads actually commit in the serial order。

 and the thread commits assuming the previous thread is committed and it has no violation。😡，Well。

 if there is a violation that needs to be detected and that gets detected with the Qs protocol。

 when this processor actually reads hash10， it doesn't know someone else has written。

 but when this processor later writes to this index 10， this memory address with index 10。

 it basically sends an invalidation request to this processor and this processor if it has read。

 remember the principle when you do a spec read you mark the cache or some location saying that oh I've actually speculate read this value and if later an in invalidation comes from an earlier E earlier processor。

 E is the right thing in this case because processors can execute later iterations also and earlier E。

😡，Actually write to a location that was specully read by a later EEC and you can determine this through the coherence protocol。

 the coherence message protocol sends an invalidation message to that address and this cache receives that invalidation message and checks if that block is actually specly read if the block is actually specly read which is the case in this case and if you're receiving an invalidation from an earlier E that means that you read a value specully earlier than someone else should have written to it as a result this a data depends violation and you read the wrong value。

Once you read the wrong value， now you need to squash this threat， this epicpo over here。😡。

And this shows how that is actually that actually happens over here so I'm going to go over this slide again in this basically this is processor  one and Pro 2。

 let's say you have E 5 and E6 executing and E 6 is the earlier E over here I'm sorry E5 is the earlier it's earlier and the logical sequential order E6 execute speculatively it basically does a load from this memory location and once it does the load it needs to send a read request and gets the data cache block in its cache and there are two values two bits added to each cache block saying whether or not this cache block is spec loaded and whether or not this cache block is specly modified as we've discussed earlier when we talked about stores and loads and memory communication earlier basically when this processor does the load this spec loaded bit is set。

To one。And it's set to one and later， let's say， and this processor continues executing with the value of the load。

 it gets the value of the load， but it's speculative， it may be not the correct value。And later。

 this E5s executes on processor  one。😡，And it basically does a store。

To the same to what happens to be the same location Q and P are the same basically but these are pointers so you do not know the location statically so you cannot paralyze this program Basically this does a store it changes the value from one to2 in this case the value was set to one over here with the load over here it changes the value from one to two it basically sets a speculated modified bit in its cache。

 but it's not important here that's for other purposes and it basically because it's doing a store it needs to send an invalidation message right to everybody else remember this is a cache coherent shared memory machine when you're doing a store to a cache it's an invalidationbased protocol in this case。

 it basically sends an invalidation message to all of the other processors that have the location either through a directory protocol or through or through a snoopy protocol this invalidation message reaches the L1 cache of this processor which is executing E6 and invalidation message。

😡，It also contains information about which E。Is invalidating， So it has this E 5 tag attached to it。

 And when the I cache gets this message， it checks。Oh。

This emation is coming to a specative loaded block， which has this bit set。

And it's coming from an earlier epic， logically earlier epic than the epicpoch that I have。

 which means that I've speculately loaded potentially the incorrect value， right？😡，And in this case。

 basically， you detect that this is a violation。Once this invalidation message is received。

 you know that you've read the wrong value and the violation is detected so there's a violation signal that's set to true over here now at this point you can start squashing everything actually but in this paper and they don't do that what they do is they wait until this attempt commits time and this attempt commit time actually checks whether the violation bit is set in the cache and if that violation bit is set then it starts a recovery process but basically it basically flashes this entire squashes this entire epic over here and squashes all of the other epics that come after it so this is how you can use cache coherence to detect read after right dependence violation through the invalidation messages Now if this was an update-based protocol you could do the same thing you could actually even be even smarter if it's an update-based protocol if there's an update based protocol this E would send a message with an update request to this location with its epic。

😡，Iイディ and theデータ。And you would still know that this is speculate loaded and you can actually say if the data value that you loaded doesn't match the data value that's sent。

 then you've gotten in the wrong value right then there's a violation If the data values actually happen to match。

 then you've gotten in the correct value by chance potentially because there are actually a lot of stores that are silence right these are called silent stores。

😡，And Kevin Leak is a paper in microcro 2001 on the silent stores and I'd encourage you to read that paper Basically this means that stores storing the same value to the location same value as the location had before so an updatebased protocol can have that optimization and it can check whether the data value has changed or not instead of checking only whether the address is going to be modified with some value that's not known okay so that's the idea this is how you can detect conflicts in thread levelvel speculation by leveraging the underlying coherance protocol This paper actually presented some results and I'll briefly go over them I'll encourage you to read this paper therere actually some promising results these are some applications and this is on aster single chip multiproster four processorster single multicore machine。

And。You can see the speedups there's the parallel region is over here and the speedup that you obtain in the parallel region。

 this is just the parallel coverage。 So if you see that the coverage of the parallel region is not very high。

 which means that MbelL's law limits the speedups to begin with over here but these show the results。

 for example， in some applications you get significant performance benefit with four processors up to 46% performance benefits and the performance benefit keeps increasing as you add more processors and remember this is purely done with thread level speculation。

 it's a single thread application parallelzed on some applications， for example。

 the Jpeg compression you get less benefit on the 8% on the overall program and 94% on the parallel region and you can see the speedup curves as you increase the number of processors over here。

 this is a single threadread version up to8 processors and this is the execution time of the region which is the parallel region of the program that they parallellyzed in this work So you can see that this application actually scales in the parallel region but。

Cs where for example， here， the performance increases up to four threads。

 but as you go up to six threads and eight threads， performance starts decreasing。

 execution time starts increasing。 In fact， the execution time with eight threads is worse than the execution time with one thread Why would this happen Well this could happen due to multiple reasons actually there are many reasons but in this case there are lots of dependencies between threads so there are lots of squashes That's one reason there's a lot of ping ping that starts happening because now the data gets distributed across the private cache and you get a lot of invalidmals because of the dependencies and theres bandwidth contention that also happens。

 these are basically could due to the problems that we've discussed in the bottlenecks in the parallel region and these are actually discussed in the paper。

 I'd encourage you to read this paper but thread level speculation approaches like this are quite promising the downside as you can see the upside is you can get significant speedup in the parallel region the downside is some speedups are actually low and the complexity may be high in the system。

So I'd encourage you to think about the events and disadvantages。Okay。

Let's move to another seminal paper， this's actually an even earlier paper that discussed threadlevel speculation。

 this is called multiscalear processors， and the key idea is to exploit implicit thread levelvel parallelsism within a serial program。

 just like what we've discussed earlier， but the approach is different here in this case。

 the compiler divides programs into tasks and the tasks can be defined unclear but we will discussed this。

 and these tasks tasks are basically the portions of a single threaded program。😡。

If you think of single field program as executing a series of instructions that are dynamic。

 that are composed of static blocks of instructions。

 these catas are some arbitrary subsetting of those blocks。So let's say this is your program。

And these are some blocks of instructions， your tasks are basically。Blocks in your program， right。

 task zero， task one， task two， task three， task four， they could be luiterations。

They could be functions， right， but the key thing is this is a sequential execution over here。Okay。

 and we'll see an example of this tests are scheduled on independent processing resources instead of executing them on the same processing resource。

 thread zero goes to one processor， thread one goes to another， thread2 goes to another dot dot dot。

They similar to it before。And hardware handles register dependencies between tasks because these are coming from the same program。

 there could be register dependencies， this could be writing to register too。

 this could be reading for Reg to right and there may be many dependencies hardware handles the register dependencies but compiler specifies which register should be communicate between the task because compiler knows that information right remember register dependencies are known to the compiler compiler when it creates the tasks。

 it basically says oh these are the registers that I need and these are the registers that I'm actually likely to produce。

 I can produce。😡，And this information is convey to the hardware it such that the hardware can communicate between the threads。

 and we willll see an example of this。And memory dependencies are handled through memory speculation。

 basically hardware detects and resolve to missspeculation between the tasks and through something called an address resolution buffer that we will discuss。

😡，So this I would recommend actually both papers over here。

 but the required paper is a Sohi paper multiscalear processor that appeared in Nisca 1995 this an earlier paper。

 the Expendable split window paradigm for expanding exploiting fineger and parallelism a lot of the concepts are not mature enough yet but it was also published in Nca 1992 and certainly the name multiscalear is more catchy right Expendable split window paradigm for exploiting Fger imp parallelism doesn't sound that catchy but when you say multiscalear it start becoming more catchy anyway that's a joke of it but basically this figure from the multiscalear paper clearly describes what they' are trying to do。

If you want to have a single threaded program and if you want to execute operations in parallel。

 you would like to execute instructions one by one and figure out have a large window or execution right to actually improve the performance of the program right out of order。

 improve the performance of the program by looking at a large window of instructions。😡。

And you already discussed why that large window is harder to build right and that led to the multi core increasing performance by building large instruction windows is difficult now if you have a large window of instructions and if you want to execute multiple instructions per cycle。

😡，え。One of the limitations is， for example， if you want to execute 100 instructions per cycle。

 let's say。You want to extract that kind of parallelism from your program to be able to do that。

 you need to look beyond many instructions in the instructions stream and also you need to have a width of 100 instructions per cycle and also you need to have a register file that can support the execution of 100 instructions per cycle which means that you need to have 200 ports right assuming each instruction has two input values。

 two source registers so building this multiport register files tough right and this was one of the reasons for Mo to multicor remember the K oquton paper in 1996 that discussed。

😡，A multiport register file is a part of the technology push of what makes single core single process unattractive。

 a similar reason happens here in 1992 and basically 200 port register file is not scalable so why don't we actually instead of having a huge large window why don't we chop up this instruction window and execute the different pieces。

😡，In parallel。In different processors， processor zero executes task zero。

 processor  one executes task one， processor two executes task2。

 and processor  three executes task three。Now each processor looks at a smaller window。

But you can process the entire window， maybe a similar size window in parallel。😡。

And the added benefit is each processor has a simpler register file， right？Why。

 because now in order to get the same bandwidth， let's say you want to do 100 instructions per cycle。

 I was very aggressive here， now you can do only 25 instructions per cycle。😡。

In each of these processors， which means that you only need 80 port。And of course。

 if you scale this reasonable values， if you say I want to do 16 instructions per cycle total。

 you need 32 ports here， building a 32 port in register fast， still pretty tough。

But if you want to execute 16 instructions， you just need to execute four instructions per cycle if you have four processors。

 which means that you need to have only eight ports per register file。

 and that's actually much more palatable。😡，So that's the idea basically now we have a distributed register file。

😡，Add smaller windows and you split the large window into smaller windows and you're extracting parallelism through the multiple hardware contexts。

😡，And you have this distribute register file， but you need to somehow ensure that the communication happens correctly in the register file and we'll take a look at how multiscalear does that。

 I've already given you the basic idea So the key idea exploits parallelism that is provided by a large instruction window in a sequential instruction scheme by chopping up that large instruction window in smaller tasks。

 smaller windows and executing tasks on those windows in parallel this not only improves the parallelism hopefully because you don't need to extract it from the sequential instruction scheme through auto order execution methods that are less scalable for example through the reservation stations。

 hopefully you can extract parallels much more easily if you create the tasks nicely and assign them to different processors and also this hopefully simplifyifies the hardware because you don't need to build these less scalable structures like large reservation stations large multiported register files because they are now distributed reservation stations are distributed over here multiport。

Register files are also distributed and you have few reports in each。

So that's the benefit and this is the model of execution model of execution is very similar as I've said here with the superscalealar processor you have a single centralized window and you have a single program counter and this is a dynamic instruction stream with multiplescalealar processor you have multiple distributed windows you basically have multiple program counters you have program counter zero program counter one dot over here and theres a task selection。

ATask assigner over here that assigns。Different tasks to different cores。

 so you need to have that centralized engine that actually assigns which task should go to which core。

Okay。So what is a task we've been talking about task。

 basically a task is a subgraph of the control flow graph。It could be a basic block。

 it could be multiple basic blocks， it could be a loop body， it could be a function。

 basically could could be a loop iteration， right？Task are selected by the compiler and convey to the hardware。

 and tasks are predicted and scheduled by the processor。😡。

And tasks may have data and or control dependence then they need to be resolved and this is how a multiscalear processor actually looks like。

 Basically it has these different it has a task sequencer that sequences through the tasks figures out the next dynamic task and assigned it to the next processor that's available and these processors or tasks are ordered in a logical order in the sequence order that they were assigned。

 the head task is the oldest task in process in the system that's executing on this processor and task are actually ordered in our round drop and fashion。

 This is the next oldest next oldest and this is the tail task。

 which is the last task over here and register files are connected through a ring basically when this task actually produced a data value that may be needed for a later task basically sends the data value across this ring and the tasks that need that data value base could capture them and place them into the register file Now this is how the full emptybits。

 remember the full emptybits in the register file yet set basically an earlier task。

Procer sends a produced value and the consumer task captures the consumed value from the ring and basically sets the full bit or ready bit of its register of the register that it's waiting and how does it know to wait for the register while the compiler specifies that oh。

 this register is actually going to be produced by some other task that's earlier than you because the compiler can analyze those dependencies。

 right？😡，オッケ。So there are several things that the compiler needs to do in multiscalear first is task selection。

 you need to partition the control flow graph of a program into tasks and there are many things that go into this。

 we're not going to describe this but there is a paper by Vj Kumar at all task selection for multiscalear processors that was written in 2001 I believe you can take a look at that basically there are several things that you need to do you want to load balance across different processors if one task has two instructions for another task is 2000 instructions that doesn't work so load balancing is important again we go back to the fundamentals the fundamentals is you would like to minimize overheads and minimize the bottlenecks remember the bottlenecks in app parallelel portion is load imbalance we'd like to eliminate that when we're doing task selection The second is we would like to minimize the synchronization overhead which means that we'd like to maximize wed like to minimize intratask data depends so the compiler can look at the control flow graphs and figure out the data。

flow graph also it tries to minimize task dependencies and also it can try to minimize control dependencies right basically if the control is predictable if the control transfers between the different tasks are predictable then this task sequencer can do a good job assigning tasks to different processors and predicting the next task which is good if theres a hard to predict branch。

 it's better to embed it into a task because if there's a hard to predict branch that affect only this task and nothing else then you don't need to flush all of the other tasks right the branch prediction can be handled solely within this task so it's good to embed these hard to predict branches with within the tasks and that's one of the jobs of the multiscalear compiler and you can read the paper for more detail on the benefits of this。

The second job of the multisscale compiler is to convey the task and communication information in the executable to the hardware for this。

 the compiler has the task headers and the task header specifies several things one is actually let me start on the second one one is the program counselors of the successor potential successor tasks right you can have potential multiple successor tasks in a control flow。

😡，Now this is a dynamic stream over here， but in the control flow graph you could actually have many potential successors and the compiler needs to specify which ones。

 what are the addresses of those successors， such that the task sequencer can use a prediction mechanism to decide which task to choose next。

 so let's say this is your task。Now this is your task dependence graph， if you will。

 or task flow graph。I didn't do this well， but you can imagine there could be many。

 many successors right to a task and maybe there's an indirect branch right so you have these three successors after this task and these successors need to be communicated in the header for this task。

Such that the task sequencer figure predicts which one to go to next， which one to sequence to next。

The task editor also contains information about the register communication。

 basically which registers are needed by this task coming from other tasks because the compiler partition the task right potentially needed and which registers are actually created by this task This is one bit per register the needed registers are actually not here but created registers are here but theres a need mask also Basically this indicates all registers that are possibly modified or created by the task these are actual liveouts of the task that's the C mask right it's basically a one hot bit vector of all the register that could potentially be modified There are liveouts。

😡，And the purpose of this is when you know that you actually are going to modify a task。

 when you let's say you this is your bit vector or the registers that are created create mask。😡。

Let's say this task is modifying register zero， register 5。And register 10。

And this task is executing on a processor with this create mask if another。

 remember register file communicates the values， if the register file receives r1 r0 in this case。

 from the ring， it says oh I'm going to create this r0 so I'm not going to use this basically I'm not going to forward this to the next task so this ensures that the register values are not forwarded un necessarily。

 this also ensures that this task actually when it generates the value forwards it to the appropriate places。

To other places that need it。There are also release instructions。

 the compiler also in search release instructions， which release a register to be forward to a receiving task。

Basically， we will talk about release instructions soon。

The idea well the idea of a release instruction is whenever it's executed。

 the value it generates is put on this ring， remember the ring。

 let me go quickly to yeah there you go， when a processor actually executes an instruction and it's a release instruction and it's writing to a register。

 that register gets put on the ring because it's releasing that register value and or forwarding that register value and that gets sent to a processor that's later on。

 and that processor basically captures that value if the value is not already ready in its register file。

 basically if it's waiting for that value and how doesn't know it's waiting for that value the compiler can specify that to the processor。

😡，Okay， this is an example multi scale program， basically this is an example code segment over here。

What this does is it looks for symbols in a linked list and if the symbol is not present in the linked list。

 it adds the symbol and does it for many number of symbols that are specified by this buffer size right So this is a hard to parallelze program because what happens is if you break it into iterations。

 you may get dependencies between different versions different iterations so you don't know it's very hard to analyze statically that there are no dependencies。

 So multiscalear can actually parallelze this dynamically and this is the multiscalear code。

 this is the example this is the header for the task。 this is the task itself。

 it's basically one loop iteration， you can actually study this on your own and it has a create math。

 these are registered that are potentially created。or liveouts from this particular task。

 these are the potential targets， it could be Al which is the U loop which you go back to this same iteration or it could be the al fallouts which means that you actually get out of get out of this iteration basically this is the task itself and you could either get out or you could either continue continue the loop iteration that does the search for the symbol。

 basically the task does the search for the symbol and these are the instructions that forward their values。

 basically register 20 register 23 those are produced with these instructions and they forwarded。

To other tasks because other tasks need them and this also produce a value other tasks needs their 4 and register 8 and register 17 happen to be。

Produced， but they're released with release instructions and we will see the reason for release instructions soon。

 Stop it means basically you stop the task when you reach this instruction。

 and I'd encourage you to read multiscalear paper to get more details。

 So how does forwarding registers between tasks happen Basically the compile must identify the last instance of a right of writing to a register within a task you don't want to you may be writing to a register many times within a task。

 but you don't we want to forward the only last value because remember these tasks are from a sequential sequential order。

Basically up quotes that write a register have an additional forward bit indicating this instance。

 when it's executed， should immediately forward the result once it's executed to the next processor in sequence。

😡，And stop its indicate the end of a task and release instructions tells the processing element to forward the register value specifically basically you don't you use it you can either use the forward bits or the release instructions and there are different cases let's take a look at these cases let's take a look at this let's say this is the task I'm not showing the control flow instructions here but let's say you have a load into R1 and another load into R1 over here Now the second loads value should be forwarded to the next task because next task is really sequential right this value is basically consumed within the task so this value is really dead。

Because it's overwritten over here regardless of which path you've taken to get to this block。😡。

So this load actually is annotated with a forward bit。

 additional forward bit indicating that the result of R1 should be forwarded on the rank once the load is executed。

😡，In this case， this's a separate case in this case， the task depending on the control flow it takes。

 can produce two different values for R1 right if the control flow is this way。

 basically this value of R1 should be forwarded to the next task if the control flow happens to take。

😡，え。Go this way， then this value of R1 needs to be forwarded to the next task in this case these loads are not marked with the forward bits。

 but there is an additional release instruction added once potential values are produced。

 then you know which value of R1 is actually needs to be forwarded。

 then you can just have a release instruction the compiler ensures that release instruction such that R1 is just released。

😡，and the purpose of the release instruction is basically when the release instructions is executed that register is sent on the rank to the next processor。

That's the idea。And release instructions needed in this case， also， as you can see。

 because if you go out this path。😡，R1 is not overwritten。

 but an old value of R1 needs to be forwarded。 If you go this path。

 a new value of R1 is produced and that needs to be forwarded。Okay。

So how does task sequencing get achieved， basically you have the headers contain information about what are the potential successor tasks and task prediction。

 the task sequencer which was here before needs to do task prediction and this is analogous to branch prediction and we've discussed branch prediction 447 you can take a look at that the idea is to predict the intertask control flow and in this case for example task are chopped up such that there is only one task following task A as a result it's very used to do this prediction or in this case task A has a very iter a loop that iterates many。

 many times and task B is the fullout task in this case this could be a highly predictable intertask branch if you look at this。

And the prediction may be basically very similar to a branch prediction right what is the next task coming in this case you have two task over here and you predict whether task A or task C comes after task A and the predictor can get trained and it can implicitly predict the branches within a task。

😡，So that's the idea， this is very similar to branch prediction。

 but it needs to be done and an important issue is how does a compiler form the task such that this prediction is maximized right the prediction accuracy is maximized。

😡，Okay， how do you handle intertask dependencies， there are actually control dependence and data dependencies across the tasks because the paths actually come from a single sequential street。

For control dependencies basically we predict， as we discussed， and within a task。

 there may be dependencies that are control dependencies。And if。If okay。

 let me go back to intertask dependencies。 If there is a mis predictiondiction in the intertask。

 subsequent tasks are flushed。Okay。But if there's a mis predictiondiction within the task。

 is intratask misprediction， and I'll show you one example of it。

 actually in the previous example I could have shown perhaps。

 let's say you have this task and this task starts out this way。And let's say you have。

Statement over here and else statement over here。And that's what this is。This is the if part。

 this is the L part。And then you go back， the Sahemock。If there's a misrediction over here。

 as long as that misprediction doesn't affect anything else。😡。

No other task needs to be flushed right this misprediction can be handled internally with a task because it doesn't affect the control flow going down Now it may affect the data values。

😡，That are needed by later tasks， but that may be okay。

 that's dependent that's handled to a separate mechanism， data dependence mechanism。 Okay。

 so basically， intratask mis predictiondictions are really handled within the task and they don't get exposedd。

 So it's good to embed hard to predict branches。Into the tasks。

 that's another job of the compiler that's doing this kind that's helping this kind of parallelization。

Data depend is， on the other hand， if data depends error through the register file。

 then we have mask bits and forwarding as I discussed， basically if a task is waiting for a register。

😡，Then it stalls until that register is available， right this is a full emptybit synchronization in the register file。

😡，On the other hand， for memory， we have a separate store buffer。

 multiscalear proposed a separate store buffer called address resolution buffer。

 and the idea is loads are speculative， loads speculatively load the values。😡。

And if they actually violated it， if they actually loaded a value， they shouldn't have loadeded。

 the task is squashed。😡，Let's take a look at this address resolution buffer。

 remember we've discussed there two fundamental ways of actually storing values。

or detecting store load depends， one is through a separate buffer and one is through the A1 cache in this case we're going to do it through a separate buffer。

And the idea is multiscalear issues loads to the separate buffer。

 address resolution buffer or the data cache at the same time， as soon as the address is computed。

Address resolution buffer A is organized like a cache。

 It maintains state for all outstanding load and store addresses。

And you can read this paper for a detailed discussion。

 an address resolution buffer enter looks like this basically。

For each stage it it basically it takes an address， its address index， and for each stage。

 if you will， stage meaning different processor， it is an entry for that address。

 and this may not be the best way of doing it， but you get the idea。

 I think this is basically a version of that particular location。😡，And this version says。

 did this stage or did this processor perform a load to this address and did it perform a store？

And the data value。 And for each stage， you have that specully loaded and specully stored bits。

 basically these are bits that are specully loaded and specully stored。

 You could put this into cache， but they decided to put in a separate buffer and this very separate buffer actually affects scalability。

Basically， when you do loads。let's say you miss in the aR address resolution buffer。

 when any processor does load if it misses in the arc data comes from the data cache。😡。

Because you have not seen any prior stores yet。And if there's an Rpi。

 the processor gets the most recent data to the loads。

 which may be from the data cache or nearest prior task with a speculative bits set to one。

 So if you go back to this， the loads can get the data value from the nearest prior prior task right So when you do a load。

What happens is the processor checks。で。Basically the processor checks all of the previous days。

 let's say stage two is doing a load it basically checks all of the prior logical stages in this case let's say head is the stage zero。

 it checks stage zero and stage one also to see if there is actually a store。😡。

Coming from those stages， if there's a store coming from both stages。

 then the stage two gets this data from here because this is the latest version of the data。

 if you will right that's the idea the load gets the latest version from this address resolution buffer nearest prior task with specully store bit1。

😡，On the other end stores， and if actually loads if the load instruction loads the data later。

 in some way， it sets its load bits。😡，As one over here such that if a later task comes and stores。

 it can detect that violation， right？😡，オッケ。Sttores aRP buffer speculative stores if there is a store from an older task when it doest store。

 it basically searches the entry of the aRP because this is the same block， same cache block。

 it basically searches to find any any later tasks that may potentially have loaded this value right so for example。

 let's say stay zero doest store to a location。😡，It basically adds the store， adds a data。

 sets the store bit， it also searches all of the later logically later locations。

 stages in this entry to see if anyone has the load bit set or maybe even the store bit set if anyone has the load bit set then that task got the wrong value so it needs to be squashed that's the idea basically it's say start the load forwarding mechanism and also misspeculation checking mechanism this is how you detect the misspec and when a task commits all of the task stores are committed to the data cache from the address resolution buffer。

😡，So basically， this is very similar to the specly loaded and specully modified bits that we saw earlier with thread level speculation right because it's essentially the same concept。

 except we are doing this not in the cache， not using the coherence protocol。

 but we are doing this with a separate data structure called the address resolution buffer。😡。

Okay and if you'd like to learn more about the address resolution buffer。

 you can take a look at this paper。 This is actually introduce a bank design for different processors and you have six processors in this case that can be part of the design but this is actually a centralized structure that is not that scalable。

 it may be easier to actually use the coherence protocol。

 some coherence mechanism to forward data values between different between different processors through memory and also to take violations。

 memory dependence violations so this was memory dependence violation detection right It's actually memory renaming right have you have different versions of the same cache block with the same tag in different stages of this arb entry as we've seen basically what a does is really memory renaming same location can have multiple different values。

Except they have different versions depending on which task actually modified or executed them。

But what it does not do is memory dependence prediction。Maybe we want to be more aggressive。Because。

When once you violate the dependence， you need to squash the task， it's already too late。

 you've already used the value， but if can we predict that early on you can actually reduce this intratask flushes flushes or squashes due to interior task dependency violations by doing accurate memory depend prediction and we'll cover that next。

 The idea is predict when you're doing a load instruction task。

 predict whether or not a load instruction will be dependent on a previous store and predict which store it is。

😡，And delay the execution of the load if it's predicted to be dependent on a previous store。

 and if you can do this accurately， then you reduce the amount of squashing that happens between the tasks and existing processors actually do this within the instruction window because within the instruction window。

 the problem is similar right you may have a store older store that's writing to a location that younger load is writing。

 but when the load executes it doesn't know that store has not even executed yet。😡。

So that's the idea and there are two seminal papers that I would recommend when Andreass more show was the dynamic speculation and synchronization of data dependence that appeared in IsCO 1997 that's within the context of multiscalealar processors and the other is crystals theemmers memory dependence prediction using store sets that appeared in IsCO 1998。

But let's briefly talk about handling of these store load dependencies because it is actually important in Autoward execution processor too。

 because in an Autoward execution processor you have the same problem The problem is a load's dependent status is not known until all previous store addresses are available。

😡，And there are two key questions one is， how does the processor detect depends of a load instruction on a previous store？

😡，The second， how does the processor engine treat the scheduling of a load instruction with respect to previous stores so that engine should not be here in the slides。

 How does the processor treat the scheduling of a load instruction with respect to previous stores。😡。

So let's take a look at the first question。 How do you actually detect the dependence of a load instruction Well one option is to wait until all previous stores are committed are done Comp their addresses right then there is no need to check this is the memory disambiguation problem The second option is keep a list of pending stores in a store buffer and check whether load address actually matches a previous store address this is the load store queue that we've discussed earlier in the multicore lecture and if you actually taken my classes my class 447447 in Autoward execution lecture discusses also the store queue basically keep a list of pending stores。

😡，How do you actually treat the scheduling of a load instruction with respect to previous stores basically when you get a load instruction。

 when do you schedule it， there are three options depending on different aggressiveness levels。

 the first is you can assume that the load is independent of all previous stores and schedule the load right away right？

😡，This is what we were doing earlier right with with a lot of the thread levelve speculation approaches that I've discussed。

 So second is you can assume load is dependent on previous stores。

 So the first one is the aggressive approach。 The second one is the most conservative approach。

 which is you can assume load is depend on all previous stores and wait until all previous stores and all tasks have completed。

 This is very bad because this reduces your parallels significantly especially if youre doing designing a very large instruction window。

 The third option， which may be more intelligent is to predict the dependence of a load on an outstanding store right Basically this is the idea of the memory dependence prediction。

So let's take a look at these three options a stream load is independent of all previous stores。

 the advance is simple and can be the common case right there may not be many stores that are producing valley to nearby loads。

😡，So there is no delay for independent loads in this case。

 right and previous research has shown that most loads are actually independent。

The downside of this is it requires recovery and reexution of load and depends on misprediction and when the misrediction rate increases the performance tanks in this case。

The second option is to assume the load is dependent on all previous stores。

 there's no need to recovery in this case because you're really waiting conservatively until all previous stores have been resolved。

😡，And that's the downside。 It delays independent loads unnecessarily。 So this performs badly。

 Also Third option is more intelligent。 perhaps predict the depends of a load an outstanding store。

 This is more accurate because it turns out load store dependencies persist over time across tasks also。

 So if you actually have。A single instruction window divided into these tasks。

 let's say task0 and task4， it may be that this is doing a store and this doing a load and this static store and the static load always are to the same address。

Now if you can figure this up， this's a great prediction if they're always the same matters。

 you know that when this task executes the load， if this store has not executed yet。

 you'd better wait for that store and that's the idea that's proposed by these two papers。

 Mosha was and Christsos and Emmer and I'll refer you to those papers I'm not going to talk about them in detail。

 but the mechanisms are basically built upon this idea。😡，And why would this happen， well。

 think about for example， stack based communication。

 it may be that you're storing a value onto the stack and you're doing a function call and you're doing a loads。

😡，For that value from the stack， right？Because you don't have enough registers， for example。

 right you're spilling the value。Into a memory from a register because you don't have enough registers and the load is later loading。

Or filling。The value， because you've spilled it earlier to memory， in this case。

 this is a very predictable dependence， right？So whenever the load executes you know that somebody else spilled it well unless there are rights。

 other rights to that location， but with spills and fills， there are usually no rights。

 So this is one of the reasons why memory dependencies persist between loads and stores Okay。

 so the upside of this is it's more accurate。RightThe downside is it still requires recovery and re executionution on mis predictiondiction。

 In fact， Alpha 21，264， this is one of the readings that I recommended to you。 Rick Kessler's。

 the Alpha 21，264 microcroproor paper that appeared in Irop micro。In 1997。

And if you have not read this， I would strongly recommend that you read it， the alphapha 21264。

Microprocesor that talks about a lot of the ideas that are introduced and implemented the alphapha 21264。

 which was one of the fastest processor of its time Basically Alpha 21264 when it executed a load instruction it first assumed that that load is independent of any store so it might have an executed and later of course theres a mechanism to verify if that execution was correct because it had load store buffers as I discussed earlier whenever store executed。

 it basically checked the load buffer and tried to find instructions that shouldn't have been executed。

 tried to find instructions that have a larger sequence number than than itself and also that has an overlapping address。

And the store detects that violation and once there's a violation。

 the load shouldn't have been executed and this loads that are found to be dependent are delayed basically the load instruction is marked with a separate bit in the instruction Ka I saying that this load should wait for all of the previous stores to finish so this was a hard measure basically saying that you should wait for all of the previous stores in the machine to compute their addresses。

😡，It didn't associate the load with a particular store。

 it associate the load with all of the stores and the machine。

 but that's the Alpha 21264 did this memory depends prediction and that memory depends prediction mechanism was actually quite effective of reducing the in terms of handling basically quite effective compared to both option1。

 which is aggressive and option2， which is conservative。😡。

And this is one example from crystals's and Em paper it shows basically the IPC on the y axis and different benchmarks on the X axis and shows the conservative approach which is no speculation and if you see that the conservative approach is quite bad in most cases the IPC is low actually it's the lowest in most cases it also shows the aggressive approach which is the naive speculation basically all load instructions are assumed to be independent of previous stores and this is actually better in most cases compared to conservativeserv approach because you actually this points to the fact that many loads are actually independent of the store so you'd better let them go and this last one shows the potential of perfect prediction you basically perfectly figure out if the loads actually dependent on a previous store with an oracle mechanism and simulate this and weight only for that store to be executed to execute this load and that actually provides the highest perform so there's actually significant potential with perfect prediction compared to。

Nive and both conservative and aggressive speculation mechanisms。

 well conservative handling and aggressive handling mechanisms。

 no speculation means basically the load waits until all of the previous store address are available。

So this shows that predicting store load dependencies are important for performance and actually simple predictors like what they propose in this paper。

 or the alphapha 21264 predictor can achieve most of the potential performance。

 and I'll encourage you to read the paper as well as the alphapha 21264 paper to see the different predictors and crystals and MMM paper provides a good analysis of their predictors and other predictors。

😡，Okay。Now we're done with multiscalear， I'd encourage you to do some comparisons on multiscalealar。

 basically how does this compare to superscalear out of order processors。

 there is some comparison with a single instruction window that we've discussed right？😡。

How does it compare to multicore processors This looks kind of like multicore right except we're specly parallellyzing things and except there is this weird thing going on with the register file。

 which is the roundrobin communication interconnection network that's tightly coupled to the register file How does this compare to other chip multiproor and SMT simultaneous multithing based thread level speculation mechanism like trade level speculation that we've discussed earlier the Stean paper。

So what is different in multiscalear hardware in these approaches and what is different in multiscalear software。

 I'm not going to go through this in detail， but one thing that I'll question is the scalability of finegrained register communication for example。

 the Collohan paper looks at the dust communication between different tasks through thequias protocol that already exists。

😡，And there is no。The register-based communication is not there whereas with multi theres a registerbased communication component and this is very fine grained and this adds another point in the register file。

 this wing stopped that goes into the register file adds another port into the register file right now you need to synchronize accesses coming arbitrate between access that's coming from the local processor as well as the ring that's going to the register file So how does the scale to many processors and this may be one of the Achilles heels of multiscalear implementation。

 this register file， very fine grainined register file communication may be difficult to implement in hardware because register file is a very important component that's on the critical path of the local processor Now if you add one more port to it maybe it becomes more difficult to design and also you need to somehow do arbitration between request coming from the local port as well as local ports as well as the side ports。

The second issue of scalability is the scalability of memory renaming and dependence speculation。

 How can you scale this， And this is usually a big problem with thread level speculation approaches。

 How can you actually。Make the memory dependence detection and violation detection mechanisms more scalable with with use of the coherence protocol。

 perhaps you can do that， but you can be as scalable as a coherence protocol right in multiscalealar the address resolution buffer is a centralized structure that's much less scalable than a directory- based coherence protocol for example。

 so this is something to think about also this is food for thought for you。Okay。

 let's move on to another specular parallelization mechanism。

 which is helper threading for prefeting。And we've looked at this idea in 447 actually。

 but the basic idea is to preexec a piece of the program solely for prefetching data before we were not solely for pre-fetching data。

 the multiscaler actually chops up the program it tries to merge the results in the end right whereas here we're going to use this additional context to purely pre-fetched data and in this case you only need to form a smaller version of the program that leads to cachemesis to be able to capture the most of the benefits。

😡，Basically speculative thread， this is the preexcuted program piece can be considered a threat and it actually can be launched as a thread and this can be executed on a separate processor or core on a separate hardware thread context or on the same hardware thread context in idle cycles during cachemes this is remember runhead execution does this right when you get a cachem you keep executing the speculative thread to actually you keep executing the program to actually generate prefetches in a speculative way。

😡，Okay， so this shows to generalize threadb execution here and these are some of the papers that I would strongly recommend for you to read。

😡，Basically， what we have， let's take a look at load in this case。

 but you can actually generalize as to any instruction that leads to some performance degradation。

 let's say we have this load and this is our main program the idea is while you're executing the main program you also launch a thread forca thread that executings a prunne part of the program that is concerned with generating the address of this load and that executes while the main thread executes and that leads to a cache miss and by the time this load actually executes in the main thread a lot of the instructions are redundantly executing the main thread this load hits in the cache because this speculative thread already loaded the value into the cache and as a result you get some speed up right now this load is not a miss anymore that's the idea and this idea is actually described in many different papers and these papers are an examples Ased execution is one example for example。

And you could do this for branch mis predictions also， let's say you have a hard to predict branch。

 you can start a thread， you can spec launch a thread that executes the dependent instructions that lead to the outcome of the branch and produce a prediction and once the branch is being fetched。

 you can read this prediction from a prediction buffer。And that's how we can predict the branch。

 and these papers concern themselves Chappelle at all， simultaneous subordinate micro threadreading。

 zil and soy execution based prediction using speculative slices that talk about some of these branch prediction issues also。

So that's the generalized with the generalized thread based pre execution。

 there are three key questions。Where do you execute this pre computationut thread。

 Basically you can think of this pre thread that's generating results。

 prefetes and branch prediction outcomes as pre computationut threat right Where do you execute this？

When do you spawn this pre computationutation thread。

 when do you terminate the pre computationut thread， these are key issues。

 I'm not going to go into these in detail， but we'll talk about several options。

 you can execute the precomput thread on a separate core。

 this leads to the least contention with the main thread right because the main thread is executing the main program and precomputation thread is executing。

😡，The pruned version of the program that will hopefully generate cash misses or that will hopefully generate range mis predictions。

😡，And。Basically， you have core 1， core  zero and core 1。

You can execute the main thread here and you can execute the speculative thread here。

There is no contention between spec and main trade in this case， which is good。

 but the downside is they are not communicating tightly together。

 they're communicating through the shared L2 for example。

 so communication may be hard to do this and they are private L onces， right？

You can do it on a separate thread context on the same core。You can have the main threads。

 you can have two thread contexts here， main thread and speculative thread executing here right in this case there's more contention so they can delay each other these different threads。

 but the upside is they can more tightly communicate through the online cache right the prefetch is going to the online cache right。

You can also do it on the same core and the same context， basically I'm going to remove this。

 but you have the same core executing the main threat and also the speculative thread。

And in this case， when the main thread is stall， you can execute the speculative thread。

 So there is some contention in this case， but maybe okay if you're actually executing the speculative thread in the same when the main thread is stall。

The second issue is when do you spawn to precaation trend。

 basically you have a load instruction here。And。Where do you find the four points？When do you spawn。

 if youve spawned too late？Maybe prefetch， the thread that's executed reaches the load later than the main thread would reach。

 right？Or maybe it doesn't overlap the latency of the cachem because main trade is going to reach that load anyway very soon if you spawn too early。

 let's say you fork over here。😡，And this thread speculative thread reaches the load and gets a cache miss and handles the cache miss。

 but this main thread may never need we reach this load because you spawn too early there are a bunch of branches over here and this thread actually will never reach the same load because the branches are taken some other way。

 right？So too early is may be bad also， and too early also can have other downsides， for example。

 this load may pollute the cache， this load may be kicked out before it's needed or it may out some useful value that's needed over here。

 right？😡，So it can cause cash pollution。Or you can spawn the pre computationut thread basically their tradeoffs associated with and these trade offs are important to do whether you're generating the threads in the compiler level at the programmer level or at the hardware level or you can do it when the main thread is stall right you can spawn the precomput thread and when the main thread is stall and people have looked at that also with one interesting paper about this is virtual multithreading。

😡，And you can read that。I believe it's an NA plus 2004。

This basically talks about the experiences of when a Mad is stall launching the prefetch thread on the same core nitanium processor。

And of course， run aid execution when the main thread is stall。

 run aid execution kind of launches a speculative version of the same program right and then by checkpointing you're actually generating a new thread。

 if you will that is of the same program the third question is when you terminate the precomputation thread basically you can do this with preinserted cancel instructions or if the thread is not being effective anymore you can terminate it maybe the main thread actually reached the point that speculative thread is actually trying to preft for it's too late at that point so the main thread can say cancel there can be a cancel instruction that actually cancels the speculative thread at that point or the runtime system can dynamically collect effectiveness and contention information about the threads and based on that information it can decide to kill the precomputation thread So there are a bunch of threadbased pre executionecution issues that we're not going to be able to cover。

 but this is a fascinating topic also and if you want to do a researching。

area is I would strongly recommend this paper by CK Luke。

 who on tolerating memory latency through software controlled preexution and simultaneous multi threading processors。

 basically discuss many issues in softwarebased pre executionecution and the goal of this paper is to actually generate pre-fetching threads for hard to predict data structures。

 for example， if you look at this here， the main execution can be going through a pointer chain and preexution can be going through the other pointer chains。

 for example， if this a hash table and you have many hash lookups when the main processor。

 the main execution main thread is doing a hash lookup on one key。

 the other processors can be preexcuting threads that are doing hash lookups on the future keys that may come up。

And there are a bunch of other ones here， but for example， multiple procedure goals。

 you can do function based parallelization， when the main processor is executing one function。

 the pre executionecution can be executing different functions。

 this way you can achieve function level parallelization。

And this paper talks about many issues and I'm not going to go over this example。

 but this is basically an example that shows this is actually from MCF it's a memory intensive workload from the spec 2000 and 2006 workload suites and this is an interesting workload basically what's happening here is you have a loop while loop here that traverses this a vehicle scheduling program by the way。

 you're basically trying to schedule vehicles to service customers and what's happening is there is a linkless traversal over here and for the different trips you do many linkedless traversals to find the right vehicle and while you're doing this linkless traversal the idea is to do pre-execution for the next linkedless traversal when you're doing the execution for this iteration why don't you start the execution for the next iteration so that's what this pre-ex start instruction does。

 it starts a preexecution of this part as an next iteration and the next iteration basically。

Exs the next traversal for the next trip over here。And there's a pre execution stop over here。

 and that basically ends the pre executionution for that next iteration。And there's a。Yeah。

 this preexeccut start actually starts。 so this is this is the main thread when you're executing the main thread。

 it's actually all of threads when the main thread is executing when it gets to this point。

 there's a pre executioncut starts that start from end4。

 which is which start from the next iteration right It sets up the next iteration it starts an next iteration in some other context and the main thread keeps executing this iteration and the preexecution thread now keep executing the next iteration right it also gets a preexcut start。

 now the question is do the next nested preex starts in this paper I don't think I believe they did not do it but you could do nested preexeccut starts right the preexecution thread can launch another thread that's another pre executionecution thread。

Okay， so the pre execution threat stops when it finishes the next iteration。

And the pre executionecution thread can also stop over here if there is no accelerationeration left。

 there's another preexcut stop over here。 so this is how we can actually parallellyze a program with pre executionecution thread and there needs to be some ISA extensions over here for example。

 preexcut start takes the start PC and some maximum number of instructions to execute potentially and generates the thread ID preex stop the thread that's doing the pre-execution can be self-terinated and preexec cancels mean some the main thread for example。

 when it does preex start it record the thread ID and can decide to cancel that thread later on and there could be many reasons why to cancel the thread and the paper talks about some of them。

So this paper actually shows some promising results also these are results from different applications within SMT real SMT simultaneous multiting processor at that time and basically if you look at this this is the execution time normalized without pre executionecution and execution time normalized with pre executionecution so with pre executionecution you get significant performance benefits on some of these applications so MCF gains 8% for example with two contexts MST the minimum span and tree computation gains about 36% rate tracing program 26% there are 23% some programs actually lose performance because pre executionecution consumes bandwidth and least the contention and there's a 5% degradation compressed for example。

And the paper is a very interesting paper to read。 So I would strongly recommend you to read it。

 There are a couple of other papers that actually discuss how to construct these backward slices。

 the threads， the pre executionution threads， and these zillist and soy papers are interesting reads over here。

 This is another example from one other Spec 2000 program， which is VPR virtual。Praise and ro。

The basic idea， well this is one of the loops over here。

 it turns out this is a costly costly branch because it has lots of branch restrictions and this is a costly cash miss。

Let's take a look at how you actually construct I'll just give you an example。

 I'll refer you to the papers for more details， but this paper talks about where you actually can insert the four point to actually prefetch for this particular program and you'd like to insert the four point earlier much earlier than this particular function before it's called in this case and these are some of the instructions basically the key question is when you actually try to generate a thread just to pre-fetch data or just to compute a branch outcome do you need all of the instructions。

If you needed all of the instructions between this point， this for point， and the loads。

 then having a pre execution threat doesn't make sense， right？😡。

The main is going to execute all those instructions anyway。

So usually actually it may make sense if the speculative thread actually skippped those instructions somehow but in this case we can actually reduce the program because not all instructions that happen between the four point and the problem instruction actually lead to something useful to compute the address of the problem instruction or the outcome of the problem instruction and this shows an example over here there are many instructions between the four point and the problem instructions but you only need this many instructions and you can count these one。

2，3，4，5，6，7 instructions or maybe eight instructions execute in the pre executionecution thread to actually capture to actually compute what's needed to compute for these problem instructions so we can prune the program significantly just to focus on these problem instructions as a result this pre-execution thread can be much leaner。

And the main thread， and it can execute quickly。Right now we will see the other there could be other methods of constructing this pre executionution thread。

 right， you could actually skip some instructions。 You could actually value。

 predict some instructions such that if you don't know the values， input values to the thread。

 you can predict the values coming into the thread because this is purely speculative right the goal of this thread is to improve the performance of the main thread。

 That's what you can achieve with purely speculative approaches。

Red execution is an example of this approach also remember this is a preexecution method for prefeting purposes and we've discussed this in an earlier lecture and there is a spring 2013 video that talks about runed execution this was my PhD thesis and other people I worked on the problem done this and much looked at it in order process in ICS 1997 but basically the key idea is when the oldest instructions the long latency cash miss the processor checkpoint to architectural state and enters a specative processing mode you could now consider this a speculative thread because its state is checkpointed in runed mode instructions are speculated preexcuted and the purpose of pre executionec is just to generate pre-fets just like this helper thread so re execution really generates a helper thread uses the main thread as the helper thread。

And al two mis dependent instructions are marked in mail and dropped such that space can be made in the instruction window for other instructions that are independent and the hope is that while the thread is executing。

 it's execute some independent instructions and it gets to some cache misses that wouldn't have otherwise been uncovered with the instruction window that you have and these cache must start prefetched and run ahead mode ends when the original misres at that point。

 checkpoint is restored and main thread starts reex from the beginning from the point point where the speculative thread actually continued execution to begin with So normal execution resumes basically what happened was instead of stalling for the load you switched in this run ahead thread。

 if you will that execute quickly and got out of the。

And actually prefetched prefetched for the main thread So let me give you this example and I'll take a quick break right after that basically with a small window this is what happens。

 the processor computes and it gets a cache miss and normally it stalls and later it gets another cache miss and stalls again with runite execution。

 the processor gets a cache miss and it enters this runite execution mode where it speculatively process the instructions。

 you could consider a speculative thread and while the speculative thread is executing it another load load miss and if this is independent。

 it can start servicing that load miss and this miss starts being serviced in parallel with the original miss runite execution ends when this first miss comes back from memory the processor's pipeline is flushed and now the main thread if you will starts executing because the checkpoint is restored and the processor starts from the program counter of the load one now load one hits because the miss is serviced and the processor。

Main thread continues execution after some point second miss gets complete and when this load to actually executes what happens is it hits in the cache right because this speculative thread that got executed during the stall cycles actually prefeched data for the main thread that gets executed in the non-stall cycles if you will So as a result you save significant amount of time with runed execution So runed execution is another example of speculative parallelization of the program just like a helper thread except runed execution uses the main program。

 it doesn't really prune the program。 it just uses the main program to actually generate cache misses Now going forward there actually interesting research issues here and I'd be happy to talk to you about it how do you actually make this runed execution to be more effective can you actually prune this program dynamically in this runhead mode to actually improve the performance and efficiency of runed execution and that's a very interesting topic going forward So I'll take a break here will start with slipstream processors at the beginning。



![](img/8c764c83ba795ad9ea62ac75a09d1ed1_5.png)

![](img/8c764c83ba795ad9ea62ac75a09d1ed1_6.png)

Of the next video we're back we're talking about speculation and speculation speed of a single program and I'll cover two techniques that were proposed to do this one is slipstream processors slipstream processor is an interesting technique basically the goal is similar to many thread level speculation approaches to use multiple hardware context to speed up single thread execution this is also called implicit parallelization implicitly parallelze a program the idea in slipstream is to divide a program execution into two threads。

The advanced threat and the redundant threat， the advanced thread executes a reduced instruction stream speculatively。

And the redundant thread uses results， prefetches， predictions generated by the advanced threat。

And speeds up using those results。😡，And ensures correctness。

 redundant thread basically executes every single instruction， but。

It executes it faster because the reduced instruction stream provides some execution hints to the redundant thread。

 That's the idea。The benefit is by having due two threads execution time of the overall program actually reduces so the core idea is similar to many threadlevel speculation approaches。

 except the key point here is to have a reduced instruction stream as the advanced thread so with a specular parallelization prefetching method that we've discussed earlier pre executionec method it's very similar to that method there you can have a reduced instruction stream as well。

 this is also similar to multiscalear， except multiscaler doesn't reduce the instruction stream if you remember thread levelve speculation that we talked about earlier from Stefan at all。

 they don't reduce the instruction stream here instruction stream is reduced and it's reduced dynamically and we'll take a look at how it's done。

And this paper talks about slipstream processor， improving both performance and fault tolerance。

 it actually discusses how we can improve fault tolerance as well because if you're redundant the execute instructions earlier in a reduced thread in some other process for example。

 you can try to basically when you redundant the execution instruction you can check whether the execution actually matches or doesn't match and it can achieve some kind of fault coverage by this kind of redundant around the execution of instructions。

Okay， slip streaming， the name comes from actually an interesting thing。

 one of those NASCAR or Formula one races right if you're a car racer， you would know this。

 basically this is from the paper and this is a really nice analogy actually because what you really have is one thread。

 one processor， one hardware context executing fast and it's pulling this back slower hardware context such that it also executes fast at the same time。

And this is the notion of slip streaming and basically what happens is at speeds in excess of 190 miles per hour。

 there's high air pressure that forms in front of a race car and a partial vacuum that forms behind it。

 This creates dragon limits the car's top speed。A second car。

Can position itself close behind the first one。 This is called slip streaming or drafting。 Now。

 this fills a vacuum behind the lead car， reducing its drag。 Now， the lead car can't go faster。

As a result of this， and the trailing car now has less wind resistance in the front。

And by some accounts， according to the paper， the vacuum behind the lead car actually helps pull the trailing car Now the trailing car actually can move faster also as a result。

 both cars can speed up by several miles per hour the two combined go faster than either can alone and that's the idea of slip streaming basically this front processor。

 the advanced thread can go fast and pull the slip streaming through slip streaming can pull the thread that's the redundant thread by generating results for it prefetches branch predictions results values。

And as a result of these values， the back thread or the redundant thread can go fast。

 and once it goes fast， it figures out whether the advanced thread is doing something wrong or not right so it can figure out it can synchronize what the redundant thread early advanced thread early on such that advanced threat doesn't go into the weeds。

Okay， so this is a nice analogy over here。Basically。

 slipstream processors detect and remove ineffectual instructions and run a shortened effectual version of the program or the advanced A stream in one thread context。

 and they ensure correctness by running a complete version of the program redundant or R stream in another thread context Shortened R A streamam runs fast。

 R stream consumes near perfectect control and data flow outcomes from a stream and finishes close behind。

The two streams together lead to faster execution by helping each other than a single one alone。

This is one possible hardware over here that I'm not going to go into this in a lot of detail。

 but this could be a multicore engine， this is one core executing A streamre。

 this is another core executing the R stream， basically advanced stream what happens is advanced there's a predict redundancy predictor and redundancy detector that figures out which instruction should actually be executed by the advanced stream。

 advanced stream executes those instructions puts them in a delay buffer and redundant stream takes them out of this delay buffer and we execute every single instruction but it basically uses we use the buffers。

 we uses the results coming from the delay buffer and advanced stream fetches data into the L2 cache and R streamam can actually read data from that L2 cache in this case this is an old paper but it talks about R stream state only but it's actually it can actually fetch data into the cache such that R streams caches are。

Warmed up by the time it gets to the instructions that's needed。 So that's the basic idea。

 You could do it in a multi threadit context。 You could do it in。In multi corere context like this。

 So the key question is audience is remove instructions in slipstream processing。

 And this is actually a tough part of the slipstream processor。 Basically。

 this I detector detects ineffectual instructions I convey them to the IR predictor。

 Ineffectual instructions are dynamic instructions that repeatedly and predictably have no obable effect。

 you would really like to remove that。 for example， if I're right。

 if a store is unreferenced after a point。You would like to remove it and why could it be on their because because of compiler optimizations。

 right， you can move the store。Somewhere before a branch。

And you take the branch and the storm may not be needed here。

 right it may really be needed on this path。But compile optimization may move the store。

 hoist the store up there for some reason non-modifying rights， for example。

 if you have a silent store， if the store is writing the same value。

 that's an ineffectual instruction， you can remove its dependence chain also backward dependence slice dynamic branches whose outcomes are consistently predicted correctly。

 these can actually be removed also because you have the redundant stream to execute when you do the wrong thing so a lot of loop branches and the instructions that are feeding those loop branches can be removed from this advanced stream and the removal happens from the R stream instructions IR predictor basically this IR detectoror operates on the redundant stream but IR predictor when the a stream gets to a program counter。

 IR predictor says， oh， you should not execute it because these instructions are ineffectual that basically remove the instruction from the advanced stream after repeated indications from the IR detector there are some confidence mechanism。

Read the paper for more detail， but basically ASt advancedance stream skips these ineffectual instructions and executes everything else and inserts their results in the delay buffer our stream executes all instructions but uses results from the delay buffer as predictions such that it can speed up。

So what if A streamream， one question with this kind of mechanism is what if A streamream deviates from correct execution。

 you can actually have a wrong prediction right in the advanced stream because A streamream may incorrectly remove some instructions or it can access some sta data in the1 data cache that's not updated right？

😊，How do you detect it， Basically， there can be a bch or malum mis prediction that happens in our stream。

And this is also known as instruction removal mis predictiondiction。

 and once this mis predictiondiction is actually detected in the back processor in the Rstream redundantstream because redundant stream。

 remember it's there for safety。 it's really there for correctness whereas a stream is really there for performance。

 remember you covered token currents that decouples performance and correctness Were really decoupling performance and correctness somehow here。

 the redundant stream is decoup ensuring correctness。

 the advanced stream is ensuring high performance by prefetching results by generating results for the R stream how do we detect it while basically when on the R stream branch or value mis predictiondiction happens in R stream at that point。

 a stream register state needs to be restored by copying values from R stream registers using the delay buffer or shared memory exception handler and you can read the paper and astream memory state needs to be restored also and the paper discusses one method of doing this but there are other efficient method so you can imagine that the speckcle of the written blocks by the a stream should not。

really get communicated to the R stream if they're really wrong。

 right R stream basically needs to access memory to get the correct data。

 So basically a stream memory state needs to be restored somehow。

So there are several questions in slipstreamream， how do you actually construct the advanced thread and how do you speed up the redundant threat the original proposal of slipstreamream was limited in my opinion basically dynamically eliminates the redundant instructions。

 silent stores and dynamically their instructions and dynamically eliminate limits ease to predict branches。

😡，Which is good， which but at leads to some complexity for this e。

 but there are other ways you can dynamically ignore long latency stalllls just like whenite execution does right when you get to a long latency cashm。

 you ignore it and you keep going。This way， you can create an advanced thread。

 And remember it's sun rock processor that we discussed in the multicore lecture。

 It's essentially what they did in a sense， right， You can think of that as an advanced threat and a redundant threat。

And that's what they called it， right？You have an advanced threat that dynamically ignores long waitancy cache misses。

 in that case， L1 cache misses， A threat。And you have an R thread that basically executes and this A thread executes instructions that are independent on the cachems and the R thread's job is to execute instructions that are dependent on the caches。

 so this is another speculative parallelization approach， soundss rock processor， right？😊。

Rewarded cards speculative parallelization with sounds lack rockcoster。

 their goal was to tolerate memory latency better。And the way they did it was through the advanced thread and redundant thread。

 that's very similar to slipstream， but advanced thread and redund thread are constructed differently。

 and also they execute different instructions。 So redundant thread is really not fully redundant in Suns rock because it executes only the deferred instruction。

 So you really partition the instruction stream into two in SunR。

 That's the main difference between slipstream and Suns rock processor。

 they call the simultaneous speculative threading。Simultaneous。Speculative。Fdie。

And I'd encourage you to read the some paper。 if youd like to get more information。

So you could do this that way or let's go back to slipstream other ways is you can statically construct an instruction stream that's based on profiling and that's based on some execution right that way you can reduce the size of the code that gets executed in the redundant stream and there's a paper that I would recommend you to read from Rochester a performance correctness。

 explicitly decoupled architecture。😡，If you're interested in doing research in this area。Explicitly。

Deupled architecture， and they use the compiler。😡，To construct the advanced screen。

And that way they can actually make the advanced one of the processors simpler as well。

 and this was published in micro 2008。I believe it's all of Gargan Michael Kang， Gargan Kang。

You can take a look at this paper。Okay how do you speed up the redundant thread that's another question right Or proposed actually we use as instruction results。

 control and data flow outcomes from the advanced stream。

 it turns out this is not that easy because you need to merge the results into into the redundant stream right somehow and the redundant stream is executing out of order。

 how do you actually merge the results coming from the advanced stream into the redundant stream if you would like to do that？

😡，There are other ways you can only use branch results， for example。

 to simplify things or prefeched data as predictions。

 Or purpose actually didn't evaluate the impact of memory because memory latency was very short in the evaluated architecture over there。

 So if you like to actually look at the。There are a lot of issues in reusing some of these results。

 and I'd recommend one of the papers that we have written in I computer architecture letters about on reusing。

The results of pre executed instructions。In a runed execution processor。

So this can tell you some of the issues。And reusing the results。Of pre execution。诶。

We have specific case over an execution processor。And you know about training execution。

 and a lot of the concepts are similar， right？So run execution has a thread that's kind of looking forward and that also can generate results。

And that can actually those results can be used by the main thread right instead of just the data values Now it turns out it's difficult to do this。

 as explained in this paper because you need to merge the results somehow。

 it's also not that effective because once you these results that are actually generated by the original thread or by the run ahead thread。

 if you will。😡，Are actually for those instructions that are not necessarily on the critical path。

 the instructions that are on the critical path are actually dependent on the cache misses。

Because cache mistakes much longer， so these distractions。

 reusing the results doesn't help that much in terms of performance， but it helps in terms of energy。

So it may be more interesting to actually design slipstream processors that actually where the advanced thread actually prefetches data for the redundant thread。

 and advanced thread also enables execution of mispredicted branches in the redundant threads in a more accurate way。

So that brings us to something called dual core execution。

 dual core execution is a similar approach to slip streaming。

 except it designs a front processor and the back processor or advanced thread and the redundant thread in a different way。

😡，The idea is you have one thread context that specully runs ahead on load misses and prefetches data for another thread context。

That's the front processor basically gets ahead of the back processor by not stalling on cache misses。

 That's the key idea。 So if you look at this you have two cores in this case it's like a chip multiprocessor a superscale out of order core。

 superscale out of order core here you have an in order fetch basically this front processor is like a normal processor。

 it doesn't skip instructions but what it does is it does run out execution on long latency cache misses。

And all of its results。Are put into this result queue If run execution is done。

 instructions that are depend on L2 cachems are not executed and they're just placed into the result queue to be executed by this back processor Back processorer takes instructions and the order that comes from this results to basically the dynamic execution order that has happened over here and basically re-excuts instructions it also executes instructions that were not executed because they were dependent on cache misses it basically checks the result of every instruction correctly one by one and eventually retires the instructions over here and if there' is a mismatch between the execution that happens over here and the execution that happens over here。

 this back processor is the correct execution and there is a flush that happens and instructions the entire processor gets redirected so the pipelines a it longer if you will this feels like a new pipeline stage in front of this back processor because back processor now gets instructions from here but now if you have long latency cache misses。

 you can do a runed execution on them over here。And you can still keep executing independent instructions and keep feeding them into this result queue and you can really have a very large instruction window if you will。

 because this result queue is really a PIF right it's a first and first out queue and you can scale its sites to be much higher your processors don't need to be that large and in fact they could potentially be in order course right they don't need to be superscalealar course but basically this result queue enables that。

😡，The look ahead of the window to be very large because all of the instructions in the window are all of those that are decoded by this score。

😡，Until those and all of the instructions that are decod by the score and they' are executing in the scores are included in the window。

 these instructions that are sitting in the result here are included in the window and there are a bunch of instructions that are in the window with the back processor that are being executed。

 so they're also windows sound you can actually have a very large instruction window by decoupling these two processors that way。

😡，Okay so let's take a look at this in a little bit more detail。

 basically the front processor this is an instance of slip streaming in my opinion except it's a very different implementation。

 The front processor runs faster by invalidating long latency cash missing loads。

 just like in run ahead execution。😡，Lowd misses and their dependences are invalidated。

 Remember the invalid bits or bogus bits。 Bra predictions that are dependent on cash misses cannot be resolved。

Okay so this leads to highly accurate execution as independent operations are not affected right independent operations can be executed in the front processor。

 they lead to accurate prefets to warm up the caches and they lead to correctly resolved misindependent branch mis predictiondis so if there's a branch mis predictionction that's not independent of a long latency cache miss whose data is not available then these mis predictionctions can be resolved and communicated to the back processor through the result queue。

😡，Mis dependence or you don't want to stolen on them。 That's how the front processor gets ahead。

Back Proster， on the other hand， we executes every single instruction that is coming from the front processor。

To ensure correctness and to provide precise program states。

 so it basically executes instructions that are dependent on misses and also resolve branch mis predictions that are depend on long latency cache misses and once that branch mis prediction is resolved。

 the entire system starting from the fetch unit of the front processor is redirected such that you start from the right point so the pipeline。

 the benchmark prediction latency is actually longer than the pipelines of these two cores plus the result view。

😡，So Backcroer makes faster progress with help from the front processor because it gets a highly accurate instruction stream。

 all of the branches that are independent on misses are resolved。😡，And it gets warmed up data caches。

 right this is nice。warmmed up datacasts are basically the benefit of runite execution right okay we're going to wrap up speculation。

 we're going to talk about speculation to improve parallel programs in the past few modules we've actually talked about using speculation in parallel machines to improve the performance of sequential programs and the idea was in general called threadlevel speculation where you would take a single instruction stream and divide it speculatively into threads such that you can parallellyze that instruction stream such that you can get higher performance out of it here our focus will be on already existing parallel programs。

 how can we use speculation， the idea of doing something before you need it or before you know you need it to improve the performance of these parallellyzed multithread applications。

And here a bunch of readings we're going to cover some seminal readings。

 some interesting readings and this is for your reference， this will be posted on the website。

 module website and these readings start from earlyley and Mos's seminal paper on transactional memory and speculative lock collision and speculative synchronization papers。

 accelerating critical section execution with asymmetric multi core architectures which you've read the original paper by Jensen at all that introduced load links to conditional operations that was a precursor to transactional memory and a bunch of papers the last four papers are on recent implementations of transactional memory in existing processor by IBM some Intel and AMD we'll cover some of these readings as we go along but what is the goal of speculation to improve parallel programs。

 basic goal is to reduce the impact of serializing bottlenecks in particular locks or critical sections the goal is to improve performance and improve programming。

And in this case， programming ease will be one of our utmost concerns and that was a concern for sequential using speculation to improve the performance of sequential execution as well right in that case we didn't want the programmer to create the threads to begin with but we wanted to use the underlying parallel hardware multithreaded or or multicore or multiprocessor and have that hardware to automatically extract parallel threads out of a single thread of execution here and there the goal was to improve performance as well as improve programming ease。

 the programmer didn't need to write parallel programs to exploit the underlying parallel hardware here are goals very similar except the parallel programme already written but there are potentially some bottlenecks in it that can cause serialization and it's difficult for the programmer to improve the performance of the parallel program。

To optimize these serializing bottlenecks， for example， locks， critical sections， barriers。

 bottleneck pipeline stages which we had discussed in an earlier lecture on asymmetry。

And the key idea is why don't we design why don't we design hardware to do speculative execution to improve the performance of such bottlenecks as well as improve programmer ease because the programmer doesn't need to worry about these bottlenecks one early example of this is transactional memory which we will cover in this case basically the programmer specifies what should be executed atomically and the runtime system and the hardware figures out how to do that。

 basically the programmer doesn't use locks， which are hard to program with as we will discuss The other example is speculative lock collision。

 which is basically transactional memory that is not exposed to the programmer at least not exposed as much to the programmer the programmers and locks。

 but the underlying system eitees those locks when the locks are not really necessary。

 basically executes critical sections in parallel if it's deemed that these critical sections actually do not conflict with each other。

Martinez's onres paper on speculative synchronization is very similar to speculative law collision paper。

Except it is also applicable to barriers and these two papers are worthwhile reading and this is Raj Ryan Goodman's final paper on transaction lock free execution of lock based programs。

 again， the programmer programs using locks and underlying hardware ensures that those locks are executed concurrently。

 the critical sections that are protected by the same lock are executed concurrently if they can be executed concurrently in a serializable in a fashion without data conflicts。

So let's take a look at first speculative lock collision and then we'll jump into transactional memory。

 these are the three approaches we will cover and these approaches bear a lot of similarities with each other and the key distinction is speculative lock collision is not exposed to the programmer whereas transactional memories is exposed to the programmer so it does change the programme model。

😡，And we will see， I will ask you to compare and contrast these on your own and think about what are the advantages and what are the disadvantages of speculative collision versus。

Transactal memory。So specative lock， many programs use locks for synchronization this is one of the synchronization constructs that we've covered earlier actually there are other synchronization constructs like barriers and also pipeline parallel stages and these synchronization constructs can also benefit from similar ideas and I'll let you think about how to apply these similar ideas that I'll discuss to those synchronization constructs and many locks。

 the observation is that many locks are actually not necessary。

 they're there for correctness preserving correctness but these locks are not necessary do not need do not need to serialize execution for example there are two main reasons for this。

 one is you may need a critical section to protect some updates to share data。

 but those updates may occur very infrequently for example。

 you need a critical section to check for example。Let's say you insert an element into a list after checking some condition and need a critical section to protect that access updates of the shared data structure but that updates may not occur all the time because it's protected by a condition and that condition may be infrequently true。

 for example， a store to a hash table may occur only infrequently during its execution and it may only update the data in the hash table once in a blue moon but you still need to protect that hash table because there may be a reader that reads at the same time that hash table is being updated that store is happening and every time you actually executes an access to the hash table that reader needs to go through a lock and request exclusive access to the hash。

Table even though that store occurs only once in a blue moon， for correctness reasons。

 every critical section， every access to that hash table needs to be protected through that lock。

Even though most of the dynamic accesses are actually unnecessary。

 this is called dynamically unnecessary synchronization。

 statically the synchronization is necessary because at some point in time there may be a case where a store an updates to a data structure can coincide with the reading of that data structure。

 but dynamically many， many times over the execution of the data structure you may not get any updates okay that's one of the reasons why logs are unnecessary because a store to the shared data structure doesn't occur frequently during any execution。

 but reads may be much more common。😡，And the second reason is programmers actually the first reason occurs because programmers can be conservative also right they can actually protect the data structure or the second reason again occurs because the programmers are conservative because updates can occur to disjoint parts of the data structure。

 this is more about the programmer actually， for example。

 think of a hash table and think of having multiple buckets in the hash table。

Access to one bucket in the hash table can actually proceed in parallel with accesses actually updates to another bucket right because these two buckets in the hash table have nothing at all to do with each other if I have to visualize what I have in mind if you think of the hash table basically hash table you get an access you let's say an address。

And you hash it in software and gets into a bucket。 and let's say address one goes to this bucket。

 and let's say you're searching for address one in the。

Linkked lists that's associated with that bucket。 this is one implementation of the hash table。

 this search of that address one in the hash table has nothing to do with， let's say you actually。

Inserting address2 into the hash table， but it happens to map to this bucket over here and this insert operation into the hash table will update this linked list and not this linked list。

 so they have nothing to do with each other。😡，But the programmer may protect the entire hash table with a single lock。

For programming ease。And that protection of the entire hash table serializes these otherwise potentially parallel requests。

 that go to different buckets。Which means that you first need to use address one and search for it。😡。

And then only after that， you can update address2， which matches to a different bucket。

 so these have to be serialized because there's a single lock that protects the entire data structure。

😡，Now this happens because。Whereas because the program was actually conservative， right。

 the programmer can actually protect have a lock for each bucket， right？Basically。

 the programmer can have lock one for buckets one and lock。2。

 four buckets 500 right or like 500 for bucket 500。

 basically the programmer can have as many locks as the number of buckets or maybe some other grand laity。

And this way now the program needs to manage all of these different locks in a fine grade。

 but now accesses to this bucket and to this bucket don't go through the same lock as a result you can eliminate this need for serialization because of mutual because because you have the same lock a single lock now you've eliminated that single lock you've distributed lock across the buckets so this actually used to eliminate。

 but many programmers program conservatively it's harder to program with finer grain locking finer grain locking is more difficult to implement because of the finer grain exactly you need to manage more locks whereas course。

Grain locking is easier to implement for the programmer。

 but that leads to dynamically unnecessary synchronization that leads to updates occurring to dising parts of the data structure。

 even though those updates having nothing to do with each other and that leads to serialization so these are the two reasons stores occurring infrequently during execution and updates occurring to dising parts of the data structure are the two reasons why many locks are unnecessary。

😡，So the key idea， once you observe that mini locks are actually unnecessary。

ASp lock collision specully assumes that the lock is not necessary and executes the critical section without acquiring the lock。

Fantastic key idea and during the execution of the critical section。

 the runtime system or the hardware in this case checks for conflicts within the critical section。

If two instances of the critical section are executing concurrently。

 the speculative lock mechanism checks for conflicts。

 and if they do actually conflict with each other， roll back the execution if the assumption was incorrect。

 the assumption is that the lock is not necessary and those two executions of the same critical section can proceed in parallel because they're updating different parts of the data structure or they're not conflicting with each other because there is no data conflict。

And the system checks if that assumption is actually true and if that assumption is not true。

 then the system rolls back execution and restart starts。 That's the idea。

 So these are actually from the paper and the idea is described in their large and Goodman paper on speculative law collision enabling highly concurrent multithd execution as one of your required readings。

And this shows dynamically unnecessary synchronization here， the two cases here。

 one example is you have lock and unlock and the update is actually protected by an if。

Condition and that if the condition is not usually satisfied。

 which that means that this critical section is usually not necessary。

Here is the example where I described on the board over here with the hash table。

 basically you have a single lock for the entire hash table and you do lookups for x and y。

 if these x and y happen to map to different buckets。

 then there's no need for these to be protected by the critical section when they're executing concurrently。

Okay。So what are the issues， basically speculative log collision。

 what it does is with the semantics of a critical section。

 speculative log collision tries to elight the lock right。

 it assumes that the critical section is not necessary。

But the semantics of the critical section still need to be satisfied because it's therefore correctness。

 right？And the semantics of a critical section is either the entire critical section is committed or none of it。

So how does speculative lock Egen actually provide that Basically there are many issues to solve in speculative lock collision。

 especially if you would like to do this transparently to the program first and S paper talks about how to do this via hardware purely in hardware there are several issues first the hardware somehow needs to detect the lock if there are lock instructions this is relatively easy but many ISA is actually like the lock instructions。

 they have constructs that actually implement synchronization using different instructions like Comp and exchange for example in X86 and these instructions need to be detected to detect the lock。

As well as detect the unlock corresponding unlock so you need to delineate the critical section boundaries remember with in bottleneck identification of scheduling we had the bottleneck call and bottleneck return this was published in aspos 2012 and this was in our asymmetry video basically those were there to delineate the critical sections or the bottlenecks here if you're doing it purely in hardware you need to somehow detect the lock and the paper discusses that I'd encourage you to look at that The second issue is how to actually keep track of dependencies and conflicts in a critical section right。

Basically， how do you actually ensure that you know what the critical section read？

Or wrote to this is very similar to thread levelvel speculation as we discussed earlier how to actually parallelze singleturn applications basically you need to somehow keep track of what is read by a critical section and what is written by a critical section and remember in thread levelve speculation what we did was we added extra bits to different memory locations。

 either the cache or address resolution buffer or special store buffer like the address resolution buffer saying this location was written or read by by this critical section basically each cache line at a read bits in a write bit added to the tax store tag entry。

We can do a similar thing， right basically， we can keep track of the readsets。And the right sets。

Of the two critical sections。And let's say you're executing lock A on this core and there's unlock A。

And another core actually starts executing lock A over here and it needs to go to unlock A。

 if we're going to parallelze this， these parts will execute in parallel and whatever is read here should not the reads。

All the memory locations that are read over here should not overlap with the right sets。

Os and Ser versa， right， the read sets。Of this critical section should not overlap with the right set of this critical section。

 and also the right set of this should not overlap with the right set of this。Great。😊。

Readets can overlap with each other the readet of this can overlap with the resetet。

 but there should not be a conflicting right， there should not be a happen before relationship that is violated here because the critical section semantics is either the entire thing is executed or none of it executed it cannot receive a value coming from this critical section over here okay basically somehow you need to keep track of dependencies and there are many ways of doing that actually you could keep track of whether or not there's a conflict between these two critical sections by using the protocol remember thread level speculation usequeus protocol to detect the conflicts when some other thread actually write requests this cache block as read exclusive。

Then the cache blockss read and write bits are set and if any of them are set。

 this means that there's a data conflict and one of the threads is aborted right in this case。

 one of the threads will go back to the beginning of the critical section。Okay。

How do you buffer the speculative state， This is very similar to what you've discussed， Basically。

 if you're actually having rights over here， having stores over here。

 what do you do with those stores， You should really not expose them to any other part of the system right because you do not know whether or not this critical section will execute。

Or not。The execution should be atomic， you should only expose these stores at the very end of the critical section over here。

And this requires buffering of the state and we've discussed how to buffer the state right address resolution buffer with one example。

 you could buffer in the cache， of course， you need to change the coance protocol。

 I said this doesn't get exposed to other parts of the system How do you check if a Thomasma city is actually violated how do you actually figure out the dependence violations right using the coas protocol was one example we've discussed earlier what I discussed just now or there's an alternative strategy right。

 maybe you actually keep track of the addresses that you read and addresses that you written to。

And you accumulate that in some data structure until the end， until right before the unlock。

 and then at the very end you compare those addresses to all of the other addresses that you've seen in the critical sections that are currently executing in the system。

So this is a different approach， you don't detect the conflicts right away。

 but you actually detect them by comparing these sets， read sets and write sets。

 and it can actually implement these read sets and write sets using blue filters， right？😡。

you will be approximate but approximate okay over here right why basically whenever you can have a balloon filter for the readet。

 whenever you read an address， you set a bit corresponding to that address and that bit vector can be small。

 whenever you write to an address you have another balloon filter， this is the read balloonlo filter。

😡，And this is the right bloom filter。Whenever the critical section writes to an address its rights sets the bits corresponding to that address and at the end of the critical section。

 these bloom filters for this critical section are compared to the bloom filters of all of the other critical sections that are currently executing in the system and if these bloom filters actually overlap somehow in a bad way in a data conflicting way。

 which means readets overlap with right sets and rights sets overlap with right sets potentially。

 then a conflict is detected and you know which transactions actually or which the critical sections conflict and the system can abort one of them。

 so that's one other way of detecting conflicts and people are proposed many different ways and I would encourage you to think about different tradeoffs associated with it。

Later， how do you support commit and rollback basically at the end。

 you need to somehow either commit or abort or de abort early whenever you detect a conflict。

 if you detect the conflict eagerly， so there are many concepts over here。

 you can detect the conflict eagerly。😡，Or lazily and we will get back to this。

Eager detection means whenever some other thread reads a cash block that is written or read。

Whenever some other thread basically requests this cash block and I we need exclusive matter。

 you know that there is a conflict right， you can easily take that conflict。That's the detection。

 or you could detect the conflict that the Ray hand design I discussed you。

 that's the lazy detection。This is the lazy detection approach。

 detect the conflict at the very end of the transaction or the critical section。

Eager approach detect the conflict as it happens at that time。

 and then there is a question of when do you handle that， When do you handle the abort， for example。

 When you detect it or do you delay at the very end， there is a trade off here。

 right if you detect if you have more a transaction， if you have bought to a critical section。

 recommend you detect the conflict， that critical section may not finish。😡。

Because you may be using your policy， that's not optimal。

Because some other thread may always be conflicting with this critical section， right。

 you may run into starvation issues。 So with eager handling of conflicts， you may run into。

Starvation issues but。It's quick to react。When it figures out the conflict。

 there's no reason to continue this transaction or critical section， right？You can quickly react。

And if the starvation is not an issue， this can be a higher performance。

 whereas lazy doesn't usually run into starvation issues because you can at the end handle in a calm head right。

 see， oh， what have I done， let me figure out which transaction or which critical section to abort actually so that I'm fair right。

😡，So this is less starvation issues， but is this could be could potentially be lower performance because the reaction time is slow。

 right？Basically， lazy conflict handling lazy aors can lead to slow reaction time。

But many of the issues over here can be classified as eager and lazy and I'd encourage you to think about that also how do you support committee and rollback how do you actually when do you actually abort。

 for example， how do you go back to the beginning of the transaction or beginning of the critical section I keep using the words transaction and lighted lock speculative lock collision in a sense interchangeably because they're very similar concepts but somehow you need to be able to support going back to the beginning and usually that supported via a checkpoint。

 register checkpoint because you don't update memory you don't need a memory checkpoint you buffer the speculative updates usually support that using a register checkpoint and if there's a conflict one of the transactions or one of the critical actions going back to the checkpoint。

So this is another important issue。And。Okay。So okay， basically。

 what were really trying to do is to maintain atomicity right if atity is really maintained。

 then all locks can be removed。😡，So what are the conditions for atmcy？

Data that thread is not modified by another thread until critical section is complete。

Or data that's written is not accessed， either read or written to by another thread until critical section is complete。

 So that's what conflict conflict detection is all about。

Ba if you know the beginning and end of a critical section。

 we can monitor the memory addresses read or written to by the critical section and check for conflicts with other parts of the code。

😡，If there is a conflict， we can detect it using the underlying coherence mechanism。

And that's what the SLE paper that I've assigned you actually talks about。

 how to use the underlying coerance mechanism to detect the conflicts。

 this is very similar to what we've discussed with thread level speculation。

 it's a scalable approach to thread level speculation paper。😡。

So let's take a look at the implementation a little bit。

 I'm not going to go into a lot of detail on S implementation。

 but basically the processor checkpoints the register state before entering speculative lock collision mode and its to enter speculative lock collision mode by detecting the lock。

In Sp of lock e mode， if there is a store in the critical section。

 basically the processor buffers the updates in the right buffer in the store buffer and doesn't make it visible to all other processors。

 but request exclusive access。For that particular cash block that it's trying to store， right？

That's the idea。So let me actually clean this up so that you can see a better picture of this。

I'll get back to this eager versus lazy， so I keep that in mind a lot of the issues that we will discuss can be handled eagerly or lazily。

 basically the pro detects a lock。Checkpoints the architectural state。😡。

And keeps executing and there's a score and this story goes into the right buffer。

And also it sends that we exclude the requests in the chous protocol。

When there's a store or load that happens， this also sets the access bit in this case。

 the paper talks about access bits basically one bit called the access bit not the read writeite bits。

 you could have read by bits， but this access bit is set whenever you do a store to a cache line or a load。

And the system triggers mis speculationulation on some coherence actions， What are those actions。

 this is very similar to what we've discussed earlier if there's an external validation to a block with access bit set。

 so if there is a coherence request that says inmailate。This block。And the access spin is set。

 that means that there is mis speculationulation because somebody else is trying to access that block or actually write to that block or acquire that block that this particular processor executing this critical section actually has written to or read。

Which means that there's a data conflict between two critical sections or this critical section and of the system other parts of the code。

Or if there's an exclusive access， not only in validation， but also read exclusive。

 this is basically the intention to actually write to request a block with the access bit set。Right。

So that's the idea。And also， if there's not enough buffering space。

 this particular implementation triggers mis speculationulation。

 So what does that mean basically you have lots of stores here。

 dot do dot store and eventually you run out of your right buffer entries， right you cannot put。

This latest story into there。Rpory because there are no rippories left Well in this case too bad the system says I'm going to trigger misspeculation。

 go back to the beginning of this particular critical section。

 Similarlyly whenever trigger misspec is triggered because of an invalidation or these exclusive written received to a cache block that has the access bit set。

 the processor goes back to the checkpoint it is taken at the beginning of the critical section at the beginning of the SLE。

Mo。Okay。And if end of the critical section is reached。

 which means that the proor detect unlock over here， if this end is reached， without misspeculation。

 all of the rights that are in the right buffer are committed。

 and this needs to happen instantaneously。😡，That's the idea。

 It needs to become visible to all processors that's committed right away。

 All of their processor should be able to get those values without atomically it's all of these tour need to happen atomically so that's the key idea。

 that's the implementation of speculative lo。It's very simple， conceptually easy。

 and lets let's actually compare and contrast this with accelerated critical sections。

 you've actually seen a different way of handling critical sections， which are accelerating them。

 Basically whenever you get to a critical section， take the critical section and ship it to a large course such that you can get out of it fast。

And Soally says， whenever you get to critical section， basically you like the critical section。

 keep executing and check for data conflicts。Their advance and disadvantage of both approaches conceptually as well as implementation wise in this slide we talk about some conceptual differences exc critical sections has several advantages because it can't speed up each individual critical section if you think about it you actually speed up by sending to a large chord at least as the goal of exc critical sections whereas speculative lock is more for latency hiding basically instead of serializing the critical sections why don't we parallellyze them such that we can hide the latency of these two critical sections。

😡，That's the idea。AS is an advantage。 And AS works even in the presence of data conflicts， right。

 If there are data conflicts， actually shipping them to a large core and serializing them there is a good idea。

 perhaps because you。You don't compare it to SLE， whereas SLE spec lock collision。

 if there are data conflicts between critical sections， it encourage re executionutional rent。

 one of the critical sections need to abort and re execute。

So that's one advantage of ACS or SLE doesn't incur re executionec over red since it doesn't specully execute critical sections in peril。

And the third advantage is accelerated critical sections actually can keep shared data and locks in a single cache。

 it can improve share data and lock locality， whereas this doesn't exist in S because in accelerated critical sections。

 every critical section is executed in a single place， single core with hopefully a large cache。

 whereas with speculative lock collision， every critical section is still executed in a different core where it happens to be executed basically。

Okay but exc critical sections also as disadvantages over speculative lock collision one is whenever you ship the critical section to a large core or somewhere else you need to transfer the private data and also the control to a large core this reduces the private data locality in which you've discussed when we talked about data marshalling in the asymmetry lecture so I'll encourage you to go back and look at that and this occurs overhead this overhead is not present S speculative lock collision private data space wherever the critical section is executed right。

The other advantage of accelerated critical sections it's whenever there's no conflict between the critical sections。

 Sp of lock collision just makes sense， right， it basically keeps going。

And it can parallelze these critical sections that would otherwise be executed serially X critical sections doesn't do much about that。

 even though there is no data conflict， the critical sections that serialized and finally X critical sections use a mechanism that use the large core and dedicate that large core for critical sections and let large core can actually reduce parallel throughput。

 but we've discussed that if you actually add SMT spec simultaneous multi threadreading to that core。

You can reduce that effect of the loss imperel tro。

 So these are some conceptual advanced and disadvantages of a criticalical sections。

And these some of the conceptual advance and disadvantages are actually talked about over here。

 basically this is a section section 8。2 from Suleiman adults a critical section execution with asymmetric multiple architectures paper which you've read and I'd encourage you to look at it again。

 basically it compares ACS to transactional memory speculative lock collision and transaction mule and speculative synchronization and these are actually approaches to parallellyzing critical sections。

 synchronization constructs and the idea as long as these synchronization construct。

 the same instance of the synchronization construct doesn't have a conflict with another instance the execute in parallel so this enable the hiding of the latency of the synchronization。

ACS actually is partly orthogonal to these approaches， this paper states。

 because when the critical sections have conflicts with each other。

 these approaches do not work because they need to roll back speculative execution to the beginning of the critical section。

For all of the instances of the critical section， except for one。

We ask ACS in regardlesss of however many data conflicts you have。

Its still obeys in locking semantics right in execution。 As a result。

 it serialized the instance of the same lock。Basically the big difference is these are latency hiding mechanisms。

 accelerated critical sections is hopefully a latency reducing mechanism for critical sections and also the locality improvement that you get with ACS doesn't is not there with SLE or transaction as we see it because accelerated critical section these approaches do not execute synchronization constructs in a single place so I'd encourage you to think about some of these advanced and disadvantages and I'll not cover this but this paper shows that critical sections for the critical section intensive workloads with not a lot of with some data conflicts actually accelerated critical sections performs better。

But of course， they're advanced and disadvantaged to these two different approaches and potentially you can combine both right one accelerates the locks and the other eites the locks。

 or synchronization constructs， let's say。The key question is how do you actually combine the both。

 I'm not going to give you the answers， but I'll pose the questions because these could be actually very good projects if you're interested in that as well。

 can you do better than both how do you actually decide whether to accelerate a lock or light a lock For example。

 I'll give you a hint if you can actually predict when you get to lock whether you will have a data conflict。

😡，And if the outcome of that prediction is， yes， it's likely that if I execute this critical section。

 if I eite this critical section， I'll have a data conflict and if it's on the critical path。

 then you ship it to the large core because it's important。If it's a critical critical sections。

 it's all that critical section， whereas when you get to the critical section。

 but prediction is that oh， I haven't seen a lot of data conflicts for this critical section。

 let me keep executing and let me light this， then you pick speculative lockage so perhaps you can do better than both by combining both ideas and sometimes you may want tolight the lock sometimes you may want to accelerate the lock and sometimes you may want to do nothing about it because shipping it to a large core may in cur more overhead than the benefit you get from the large core。

Okay。So I've covered speculative lock collision， which is a very promising way of actually improving the performance of parallel programs by hiding the latency of critical sections and we have already look at exc critical sections which was actually not a speculative mechanism。

 so the difference between speculative lock collision and another difference called more implementation difference is speculative lock collision is speculative whereas exc critical sections is really not speculative because it really obeys the locking semantics。

 it doesn't really try to parallellyze the locks whereas speculative lock collision tries to parallelze the same lock。

So let's go back to some of the four issues that we've seen in speculative parallelization before。

 remember there were four issues in speculative parallelization and these are actually applicable to speculative law collision as well。

 these were applicable to speculatively paralyzing a single threaded program as well So first issue how to deal with unavailable values。

 Do you predict them or do you wait for them Well， actually in speculative law collision。

 this doesn't happen because the program is already paralyzed and because you're not cutting the program already the values are available you're not really making things。

You're not really trying to partition the program at a point where some value is not available。

 the value is already available， you're trying to eite the lock。So that's是一点。

So this issue doesn't exist as much in speculative Laage。

 although you could view the potentially dynamic data conflicts between two critical sections as an unavailable value for another instance of that critical section。

 but we're not going to view it that way， we're going to view that as a conflict。

The second issue is how to deal with speckulative updates。Do you actually。

 are you actually eager when you just speak about this or are you actually lazy？

Eager means basically you update the original location and you log the old value。😡。

And then when you abort， then you need to undo from the log， that's a very aggressive way， right？

Eagers advantage in these case is you update the original memory location such that that update becomes visible。

 you don't need to deal with reupating the location at the very end。

 Now lazy means you buffer your updates somewhere and do not expose them yet to the original location now you have multiple copies right if you do buffering your multiple copies if if you do logging then you have the original copy is always at the same place。

 but you have a backup per copy that you need to go you need to go back to in case there's a data conflict with buffering。

 you're lazy， you basically postpone the updates until the end of the critical section。

 postpone the stores until the end of the critical section。

 the advantage is you don't expose them quickly， the disadvantages now you need to ensure that at the end they're all exposed at the same time That's the idea。

😡，So eager versus lazy applies over here too。And in the approach that we've discussed specul collision does it lazily right how to detect conflicts again。

 we've discussed that do you detect them eagerly or lazily right do you detect them right away or do you actually lazily keep track of reads and write sets and at the end of the。

Ctical section， you compare the read and rights sets and to figure out whether or not there are conflicts and finally。

 how and when to abort or roll back or commit， when do you decide that， how to abort。

 do you abort eagerly or do you abort lazily， E abort means you abort right when you detect the conflict between the transactions。

😡，Or do you mean the critical sections？La abor means you wait until the end of the transaction at the end you figure out which transaction to abort。

😡，Here， because you can always abort one or the other， it's not clear which one theybort。

And sometimes it it may be very unclear when you have many different transactions running at the same time。

 many different critical section instances running at the same time。How to commit is easier。

 actually， because you need to commit at the very end， right。And that's， that's important。

 There's one other issue is whom tabboard actually is important because。

And when to restart is also important because you want to ensure starvation freedom and you want to ensure fair progress for different threats for different transactions。

 you don't want to abort all the time the same poor transaction right if that's the case you'll run into starvation issues。

So doing this conflict handling in a way that's fair as well as high performance becomes an interesting research area in speculative law collision。

 as well as transactional memory approaches that we will talk about later basically the takeaway is eager versus lazy approaches that are possible for each of these issues and I encourage you to think about different approaches than their tradeoffs and there has been a lot of literature in this field。

 at least in transactional memory maybe less so in speculative law collision but in transactional memory that deals with these four different questions in speculative parallelization。



![](img/8c764c83ba795ad9ea62ac75a09d1ed1_8.png)

So let's take a quick break and then finally we will cover transactional memory and after that we're going to finish our module on speculation and parallel machines。



![](img/8c764c83ba795ad9ea62ac75a09d1ed1_10.png)

Okay。Now that I covered speculative lock collision I'll briefly cover transactional memory but transactional memory is actually speculative lock collision exposed to the programmer and that's actually a good way of thinking about it it does change the programming model significantly because it doesn't keep the lockbased programming model but a lot of the ideas of transactional memory are actually very similar to speculative lock collision that we've discussed earlier so I'm going to go through this relatively quickly and defer you to the papers that I'll discuss as well as some of the other literature that we will put up online but I'd be happy to take any questions related to this and give you a potential pointers in terms of potential research topics but the basic idea is remember we want to keep atomic execution of critical sections and the basic idea here is programmers specifies what code should be executed atomically as transactions。

And hardware and software guarantees autoomicity for these transactions。

Which means that the programmer doesn't need to deal with locks anymore。

 right the programmer all they need to do is delineate the transactions or what code needs to be executed atically。

 that's it。😡，There's no need for the programmer to lock individual buckets of a hash table。

 Remember that hash table example that I gave you earlier。

 there's no need for the programmer to do fine grain synchronization， fine grain locking。

 the programmer can say。Atomic。Hash table update， right？Atomic。Hash table of eat。We can sell。

So there's a bunch of code that does hash table reading somehow and a bunch of quote that does hash table updating over here。

And this doesn't need to be atomic another way of thinking a lot of this to begin。transactionaction。

An end transaction at the very end。You could use begin transaction and transaction。

And somehow the hardware software guarantees that this entire piece of code is executed all or not。😡。

And how does it do that well， similarly to what we have discussed earlier？

This is motivated by the difficulty of lock based programming lock basedase programming is not easy。

 as we will discuss in the next slide， programmers make mistakes because they need to protect everything with locks and if they want to get high performance and locks cause serialization right that is a form of blocking synchronization when a thread acquires the lock all of the threads that need to acquire that lock need to block。

😡，Basically， locks lead to blocking synchronization。Threads block， waiting for the lock。

And because of this。You want blocks to be small， as small as possible to critical sections。

 but if you want to make the critical sections as small as possible it becomes harder now you get into buggy programs this the fundamental tradeouts that we've discussed earlier。

 watch your parallel computer architecture is about enabling the programmer's job to be easier when writing high performance parallel programs that high performanceform comes from reducing the size of the locks and it's difficult to reduce the size of the locks because now you get into bugs。

 what if you incorrectly exclude something out of the critical section whereas that is important for correctness to be inside the critical section。

😡，Whereas well one way of getting rid of that problem is having a single lock for the entire program right for main。

 beginning of main， you say lock at the end of main， you say unlock and all the threads do that。

 Now this is terrible for performance right， because every thread is serialized with every other thread。

 You don't want that。 That's really bad transactional memory kind of gives that illusion in terms of programming。

 but this really easy the program。 the first one， you don't need to reason about any conflicts。

 any potential shared data updates at all。 transactional memory kind of gives that illusion to the programmer right。

 basically you can have a large atomic block and the underlying hardware of the software determines which atomic blocks can be executed concurrently without violating atomicity。

 That's the idea。Transaction memory is also motivated by the lack of concurrency in blocking synchronization you've kind of talked about this right blocking synchronization leads to lack of concurrency because you need to have serialization。

 but there are many cases where serialization is dynamically unnecessary if you add atomic constructs like this begin transaction and transaction then the ontime system can decide which transactions can be executed in parallel in underlying manner。

 there's no reason for the programmer to synchronize serialize these different accesses that do not require necessary synchronization dynamically。

So another form of term， basically this blocking synchronization is locks。

Whereas non blocking synchronization is transactional memory。Or。

Because when you get to a critical section， atomic block， you don't block， right。

 you don't actually wait for someone else to release a lock because there's no lock okay？Also。

 transactional memory is called optimistic concurrency。Whereas locks are called pessimistic concurr。

 why， because locks are really serializing every access to that shared data structure they protect right this is kind of pessimistic right。

 what if those accesses do not conflict with each other right as we've seen earlier。😡。

Where transactional memory is optimistic because there's no need to really serialize the atomic blocks。

 execute the blocks， and if there's a data conflict， you detect that conflict。

It's kind of optimistic in the sense that it works best if there are no data conflicts。

 and that's kind of the assumption right， the data conflicts is rare。

 so we're going to enlight the locks， we're going to execute these transactions in parallel。

And only if they conflict with each other， we were going to detect that conflict and roll back one of them Okay so let's take a look at these locking issues in a little bit more detail。

 locks are not great programming constructs， even though they work well， they have some issues。

 they have some problems that make it difficult or lowpers to program with them Basically what's a lock lock is an object。

 only one thread can hold at a time。To enable synchronization。For example。

 you can have a lock for each shared data structure。

 or you can have a lock for a portion of a data structure， maybe individual nodes in the linked list。

 that'll be hard to program maybe individual buckets in a hash table， that'll be hard to manage。

The usage is a thread waits for acquiring the lock， which means it can block for a while。

 waiting for the lock， and then it acquires the lock， it basically write to a memory location。

 for example， it can be a counter based lock， you can increment a counter。😡。

It accesses the critical section after that， and once the critical section code is done。

 it releases the lock， that's the model。This leads to several issues。

 one is correctness issues and the other is performance issues。

And we'll take a look at both correctness issues， if you want high performance。Well。

 you may sometimes need to forget a lock， right， at least under locking。basicallysically。

 this leads to data races and sometimes you get incorrect behavior because you may have forgotten a lock。

Why， why you usually forget a luckwell， you may be careless， yes。

 but sometimes you actually forget to protect some part of the code that needs to be protected because you're really trying to optimize performance in this code and to optimize a performance in this code you want to minimize the serializing constructs which means that you want to get rid of those critical sections that are large。

😡，That leads undering， that leads to data races and that leads to bugs that are necessarily that may actually。

Lad to incorrect execution。So data rice means basically you have accesses to share data that is。

Donown concurrently by different threads， thiss not necessarily a bad thing， right。

This may not be a bad thing for example， Accesses to logs are actually data ass when somebody is writing some other thread may be reading from it and that rate is necessary for synchronization。

 but for regular shared data， it may not be a good thing because when one thread is updating that share data。

 you may not want another thread actually reading that share data that's the whole purpose of synchronization。

 for example， when one thread is inserting to a linked list。

 you may not want that other thread to read from that linked list。

 especially if that read and insert will not be consistent。

'll not achieve the semantics you would like to achieve with that read and write。😡。

The second correctness issue is acquire in different orders， I'm not going to go into this in detail。

 but if you're actually protecting multiple different structures。

 you may get into a situation you have different orders of cars。

 one thread may acquire lock A and wait for lock B。In that order。

 because the control flow happens to take that thread that way。So it's can acquire lock A， acquired。

 and then it can wait for lock B and other threads。10。Acquire Lock B。And it gets to wait for lock A。

 but this thread is holding lock A and this thread， so it cannot make progress。

Whereas this thread is waiting for lock B and this thread has already acquired lock B。

 so this cannot make progress too bad now we have a deadlock right no thread is making progress。

This happens because you have different locks for different structures and if you add a single lock。

 it could reduce your concurrency right that's the problem you may actually want to protect only the data structure sometimes only the data structures sometimes and then you want both of the locks to be acquired when you want to protect both of the data structures when you're doing something with both of them。

So let's leads to Dlock， whereas if you have a transaction begin and transaction end。

 this doesn't happen because there is no acquire in release， there are no different locks。

 basically somebody guarantees that atomic execution is satisfied。

Let's take a look at the performance issues， well as I told you lockxley to conservative serialization。

 there is also overhead of acquiring the locks right if some other thread is actually holding the lock that lock needs to be brought to the cache of this other thread that's executing in this other core。

 so it takes time to acquire the lock so there's pingpononggging that happens because of the locks。😡。

It's difficult to find the right ground la of locking exactly because of what I discussed right if you actually make the locks course grain。

 it's easier to program but lower performance because of the overheads。

Whereas if you make the locks fine grain， it's harder to program and the performance is higher potentially。

 but there may be correctness issues and blocking synchronization is a cause of a lot of these issues。

So let's comparing contracts locks and transactions remember in locks。

 we had underlocking issues because the programmer needs to minimize the locks because they cause serialization transaction can help this because the interface is simpler right the programmer doesn't need to reason that much about what is really shared data and what's not shared data they do need to reason about what needs to be executed atomically but they can be a little bit relaxed about it because atomic means all or not and if the programmer wants the atomic can be a larger code section whereas in locks you have blocking synchronization so the programmer is difficult for the programmer to reason about that interface。

And reason about what will happen with when they reduce the size of the critical sanction right locks have deadlock due to log quaing whereas transactions have no ordering of locks because theres there are no locks to begin with。

 as we discussed。There can be no deadlocks in transactions unless the transactional memory manager somehow does the wrong thing。

But that's not the responsibility of the program。Blocky to blocking synchronization。

 whereas transactions are nonblocking as we discussed earlier， basically whenever there's a conflict。

 one of the transactions actually abort and the transactions go into the transactions is executed optimistically as we've discussed。

And finally， locks have conservative serialization。

 if they enforce forced serialization all the time。

 whereas basically for different instances of the same critical section。

 they're conservatives serialized even though serialization may not be necessary dynamically。

 whereas transactions serialize only on conflicts。The conflict is detected dynamically on serializations and enforced if there is a conflict。

 whereas if there is no conflict through transactions can execute concurrently。

 and that's the idea of optimistic concurrency versus pessimistic concurrency that we've discussed。

So transactional memory， if you think about it， it allows arbitrary multiple memory locations to be updated atomically in an all or none fashion。

😡，And there are several basic mechanisms which we've already covered actually。

 so I'm going to briefly go through these， one is you need to provide isolation and conflict management。

 you need to isolate these two transactions from each other。

Whenever this transaction is executing over here， this transaction should not see state because this is not updating that state and the other part of the system should not see the updates。

 which means that you need to do buffering you need to track reads and write per transaction and you also need to detect conflicts between transactions and we discussed this earlier version management。

 you need to record new and old values because you don't want them to be exposed new values to be exposed to the other parts of the system and we've talked about this in detail when we talked about S spec a collision earlier。

 and they are eager versus lazy ways of doing that right you could record the new values or in a log or in a buffer。

😡，Okay，Anatomicity is another mechanism that needs to be provided。

 Basically the transactional memory provides a mechanism for committing new values or aborting back to old values。

 You have all or non-semantics in a transaction that's what's really important just like speculative lock collision as we discussed earlier So issues are actually the same as other speculative parallelization schemes remember the four fundamental things actually I have three over here because one of them doesn't exist and you can think about what that is while you're listening to this video logging and buffering。

 conflict detection， abort rollback or commit。And remember these were the four things。

 how to deal with unavailable values， do you predict them or do you weight them this doesn't exist over here really because the values hopefully are available。

 but how to deal with speculative updates， do you do logging or buffering。

 how do you detect conflicts do you do it lazily or eagerly do you use the coherance protocol or do you actually keep track of readets and write sets and potentially balloon filters。

 how do and when do you do the abort and rollback and commit and also who do you abort on a conflict is important。

 do you do it eagerly and lazily， do you have a manager that actually manages which transactions which threads should commit transactions what kind of quality of service and what kind of fairness guarantees do you give to the transaction manager。

 basically these are all can be considered transaction scheduling if you will。

Which transaction do you actually award， which transaction do you commit。

 which transaction do you restart？And again， we've covered this a lot in the speculative lock collision lecture you can go back to it and a lot of the issues are similar with transactional memory and speculative lock collision。

 but there is an abundant set of papers that look at conflict management and transaction scheduling in transactional memory and I'd encourage you to look at those if you're interested in this there are many variations of transaction memory as well。

 this can be implemented purely in software which means that the runtime system somehow ensures that you actually satisfy these atomic atomicity semantics in the transaction so the upside of this is there are no virtualization issues right all of the items are virtual if you actually interrupt the process well you can actually keep track of everything in software。

Basically what are the issues with actually virtualization。

 let's say you get an interrupt in the in the middle of an atomic code block。

 it's okay if you have all everything handled in software right because software actually the state of this program is saved somewhere。

 so all of the information that you keep track of about the read set and the right set are potential are saved in the software so for example when you to read。

 write， read， right if you have software transaction these need to be kept track of in some data structures。

That keep the read set and the right set， right？And these data structures are part of the program and when the program is interrupted。

 those get saved somewhere， so automatically virtualization is handled。

 The downside of software transactional memory is its high performance overhead。

 All these operations that we've discussed earlier need to be done in software， conflict management。

 we to set tracking， aor management， all of them is purely software and that adds a lot of overhead into the system。

On the other hand， hardware， the upside is low performance overhead， Everything is done in hardware。

 Qs protocol specifies， for example， is's modified such that you abort transactions easily。

The downside is now you need support for virtualization and hardware。For example。

 what if you're buffering for rights are not enough？In hardware。What do you do。

 you don't have enough buffers for rights？You may need to virtualize if you want to support a large transaction that writes a million memory locations。

 where do you write those well maybe you virtualize those buffers right now this is this becomes more complex。

This also buffer virtualization is also needed when you get a contact switch in the middle of a transaction。

 whether if you have a long running transaction right and you want to take the context switch。

And the transaction is running in hardware。Now you have these hardware structures that are buffering the naga。

 for example， the read write bits in the cache， what do you do with them？😡，Too bad。

 You cannot blow them away because they belong to this transaction and they affect correctness right So when you get to a context switch you actually abort the transaction then well。

 that may not be a good idea because the transaction may be actually a long transaction。

 So what if you you will eventually need to complete it。 But what if it gets a context switch again。

 So we run into these issues of virtualization when you have pure hardware transactional memory And this actually should be HM over here。

 So I'm going to modify the slide right here。

![](img/8c764c83ba795ad9ea62ac75a09d1ed1_12.png)

![](img/8c764c83ba795ad9ea62ac75a09d1ed1_13.png)

If you will， and actually even save it。Okay。So and what happens when you do IO with believe in transactions right when you do IO usually context switch。

 how do you handle that， How do you serialize these transactions when they hardware when the transaction memory is purely in hardware So because of these issues again you have upsides and downsides you see between software and hardware people have looked at hybrid hardware software mechanisms and as you can imagine it a heterogeneous approach basically the basic idea is when buffering is enough and there's no IO or context switch use hardware transaction memory such that you get low performance overhead and executing transactions and switch to software transactions memory to handle long transactions and buffer overflows that IO and context switches basically。

That's the idea。And I'd encourage you to read papers related to there's been significant literature on this。

Let's go back to the beginnings a little bit and talk about some of the initial TM ideas and current implementations very briefly and then we'll conclude transactional memory in particular and speculation and parallel machines in general transactional memory is actually inspired by loadlink store conditional operations and Jensen paper from Loest Littlemore National La technical report in 1987 is the first one that introduced this。

 but the basic idea is to have an instruction that does an atomic update of a single cache line without any lock。

We don't want any locks。 We want to update the single cache line。

 How do we do it with some new instructions。 And that's the idea of load Linked and store conditional operations。

 This is to implement nonbing synchronization in existing Is。

 Alpha and MIps are the first some of the first ones to implement it。

 but arm and power PC have this X6 as a form of it。 The basic idea is you have two instructions。

 load linked。 load linked instruction。 L L returns the current value of a location。

 Let's say load load linked memory location A into arm 1， okay。

And then a subsequent store conditional to the same memory location will store a new value only if no updates have cured to the location and then you do store conditional new value。

😡，Right。And then you do an R1 and then remember location A。O。And this basically。And sure that。

If someone has updated the memory location A between this load and store， you figure that out。😡。

Because this store doesn't succeed。If some is updated， now you can check whether the store succeeds。

 I've butchered the semantics over here， but you can check if the store succeeds and if the store doesn't succeed。

 you can keep doing this。😡，If no success， which means that somebody has perturbed with the memory location。

 there was an update to the memory location and the value of the memory location changed。

 which means that somebody else must have changed it， then you keep。😡。

Going back and this is the program we needs to do this of course loop and keep loading。

We ask store conditional if it succeed， if it succeeds。Then you can keep going， keep executing。

That's the basic idea you enable to lock freeatomic update of a single cache line using these two instructions and these instructions are supported then the key question is how do you actually do lock freeatomic updates on multiple cache lines and that's where a transactional memory comes in earlyley and Moss was where in their seminal Ico paper which is assigned to you as required reading introduce this idea of transaction memory and you can leave transaction memory is a way of providing atomic updates for multiple cache blocks or multiple words at the same time。

😡，In their implementation， originally， instructions explicitly identified transactional loads and stores。

 and there was a dedicated transaction cash for buffer。

Basically buffering was not done in the cash but there was a dedicated transactional cash and unfortunately size of the transactions were limited to this transaction cash。

 so if you had buffer too many stores within a transaction that overflowew this cash too bad。

 you would have bought that transaction and execute it in a non-transactal way。😡，呃。

Or execute in a more protected way， right， in a lockway。

Okay so this is an example from the early and Moss paper I'm not going to go into this in detail。

 but basically what they say is our transactions are intended to replace short critical sections。

 For example， a lock free data structure would typically be implemented in the following stylized way instead sort of acquiring the lock executing critical section and releasing the lock process would use LT or load transactional to read from a set of locations。

Use Val to check that the values red are consistent， so there's no lock。

 you see you start keeping doing low transactional。

And then you do validate to check that the values red consistent。

 validate means if no one has updated them that's okay。

 they're consistent because they check the transaction cash。

Use store to modify a set of locations and use commit to make the changes permanent if either the validate or the commit fails。

 the process returns to step one。There you go。 That's the atomic part of it。

Okay so you can read the paper in more detail。 This is the beginning of transactional memory Currently there are many implementations of transactional memory。

 some of them are in machines that have never seen the day of light。

 some of them are in machines that you can actually buy and use today SunRck was one of the earliest implementers of transactional memory remember this was a machine that implement runite execution as well and actually the speculative lock collision and runite execution have similarities that bear with each other。

 that's one of the reasons why Sunro amortize the cost of either one of them by implementing them together。

 they implement runite execution and speculative lock collision or transactional memory why because transactional memory checkpoints the architectural states and keeps running ahead speculatively as well whereas runite execution has a very similar approach it basically checkpoints the architectural state and keeps running speculatively the program right。

So I'd recommend this paper that talks about early experience with a commercial hardware transaction memory implementation。

 which is onRx implementation， IBM Bluejean， which is a supercomputer。

 also implements transactional memory and recent packed parallel architectures and compilation techniques paper that talks about its evaluation of hardware support for transactional memory in IBM BlueG IBM system Z another processor that's used in mainframes of IBM implements transactional memory to ease programmer' job and these are actually very parallel machines that's one of the reasons they implement transactional memory the idea is to ease programmer' job and also improve programmer productivity in programming these machines so they have two types of transactions best effort transactions in this case the programmers responsible for the aors and guarantee transactions that are guaranteed to execute so guaranteed transactions are guaranteed to execute they are subject to many。

Limitations， for example， this transaction site length should not be more than this。

Now why are there these requirements， there are these requirements because the hardware structures this implements hardware transactional memory。

 the hardware structures that are there to support transactions are of limited size。

 and if the transaction for example has a right set that's greater than the buffering that's implemented in this processor too bad。

 the transaction will execute incorrectly。😡，The programmer needs to guarantee that the transaction satisfies some of these requirements。

 and if that's the case， the hardware guarantees that the transaction will always execute correctly and autoomically。

😡，On the other hand， if the programmer cannot guarantee that they should use best effort transactions。

 the programmer should is actually responsible for aing transactions and doing their own conflict management。

 Now， as you see， this makes it a little bit harder to program with transactions。

 It's not that easy anymore， right， It was the easy abstraction， Atomic。

And executes beautifully atomically。 Now， if you tell the programmer programmer。

 you need to actually figure out how many cache blocks you're touching in your critical section。

And based on that， I will guarantee you correct execution or not。Well。

 that makes it a little bit harder to program。 still。

 it's a different kind of reasoning that's required from the programmer at this point。 Now。

 this may still be useful for。Many programmers that try to optimize their code because it can ease their job in doing performance optimization。

 but for the average programmer who has no idea potentially about how many cache lines。

 how many cash blocks are touched by a piece of code， it will be a nightmare。

 potentially so it's important to actually virtualize the transactions。

 that's where the virtualization of the transactions becomes very important because if the transactions are actually virtualize the programmer doesn't need to worry about how big their transactions should be。

 if the transactions are smaller， you get better performance because you don't run into virtualization。

 for example， you don't run into issues where you need to context reach out and need to save the transaction state。

So it's still good even when you have transactional memory to reduce the size of your critical sections。

 its a fundamental issue， size of the critical sections， the smaller。

 the better because handling log transactions are actually costly in terms of both performance as well as implementation complexity Intel has well has an implementation of hardware transactional memory。

 again it has similar limitations for it to get good performance on code Intel has also has speculative lock collision as well and AMD also has a paper on their extension for lockfr data structures and transactional memory。

So this is my last slide on transactional memory。 There are many research issues on transactional memory。

 this was a very hot topic a few years ago with lots of papers being published in the architecture community now it's calmed down a little bit it's being implemented products and it's clear that it's not a panacea to all parallel programming problems although it could be a useful addition to the program toolkit in designing better parallel programs。

 One issue is scalability， how do you actually scale conflict management and version management to a very large number of nodes and I'll let you think about some of these questions I'm not going to give you answers but these are actually interesting research issues the second is complexity and complexity is mainly related to how to actually virtualize transactions without much complexity how do you actually run loan transactions and ensure that if they execute correctly in the presence of context which is and paging how do you actually save transactional state especially if you have hardware transactional memory。

 how do you keep track of。Read write sets when you actually need to move the transactions to software if you have hybrid transactional memory。

Handling IO within transactions is interesting and hardware complexity in dealing with all of this is interesting。

 Soft transactional memory， pure software transactional memory is unlikely to actually be very high performance enough to benefit a lot of programmers。

Because there's a lot of overhead in managing transactions， read writeite sets。

 as commits checkpoints purely in software that leads to significant overhead and people have tried to amortize that and reduce that overhead with lots of optimizations at the software level and compiler level。

 but that overhead still seems to be very high so hardware support for transactional memory is still needed and once you start having hardware support for transactional memory。

 then the key question is how do you actually virtualize it how do you keep that hardware complexity at check。

Another issue is semantic actions basically when you have atomic blocks that are nested with each other。

 what are the semantics related to that I'm not going to talk about that but this is more of a language and programming research topic and finally the key question a big key questions that transactional memory actually increase programmer productivity basically the basic goal was to reduce the burden of the programmer in writing both correct programs and high performance programs and does this actually happen and this is a difficult question to answer because they're in huge chunks of programs that are actually converted to transactional memory but a related key question does the programmers still need to optimize the transactions optimize their sizes and try to minimize the rate of conflict and the answer is likely yes but to what extent do they need to optimize as much as locks is less likely because locks have no latency tolerance it' blocking synchronization but this question is an open。

Quion even though it's not a computer architecture class question where it's very hard to do a research project relates to this。

 but I'd be very interested in listening to your opinions about what kind of potential projects you may want to do on a transactional memory and speak of law。

So that brings us to the end of our lectures on speculation and parallel machines。

 we've covered a lot in speculation， we've talked about thread levelvel speculation and we've covered different approaches to parallellyzing a single instruction stream like dual core execution for example。

 slipstream processing was another example， and then we moved into using using speculation to improve the performance of parallel program we talked about speculative lo collision we talked about transactional memory and remember the four concepts of speculative parallelization that still exist。

 for example multiscalear is an example that shows those four concepts and I'd encourage you to think about potentially different ways of actually using speculation to improve performance as well as efficiency as well as productivity in parallel machines this's another fascinating area in computer architecture。



![](img/8c764c83ba795ad9ea62ac75a09d1ed1_15.png)

![](img/8c764c83ba795ad9ea62ac75a09d1ed1_16.png)