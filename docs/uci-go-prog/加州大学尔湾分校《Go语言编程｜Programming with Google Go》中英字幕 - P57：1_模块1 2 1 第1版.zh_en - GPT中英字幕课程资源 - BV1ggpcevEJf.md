# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P57：1_模块1 2 1 第1版.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

![](img/7cdef3da47dc3200d25347f96e45c476_0.png)

Module1， why use concurrency， topic 2。1， concurrent versus parallel。

So I've been talking about parallel execution now I'm going to use this term concurrent。

 parallel and concurrent or related ideas， but concurrent programming is really what we're going to do and they're slightly different this parallel versus concurrent。

Concurrent execution is not necessarily executing at the same time。 It could be， you know。

 but it not it's not necessarily。 so concurrent。You can call two task concurrent and by task， I mean。

 let's think of a program for a second， we'll get more specific about what a task is later。

But you say two tasks are concurrent if the start time and the end time of the tasks overlap so that range of time between start and end for these two tasks。

 if they overlap， then you say that it is concurrent。

 That does not mean that they are literally executing at the same time where with parallel。

 they have to literally be literally be executing at the same time。

 So if you look at the picture on the left， you got task 1 test2 this timeline time is going。

 time is increasing down so there's a start， if you look at task1， it starts early。

Then it executes where you see that black line， that black vertical line under task one。

 it's executing so and then there's that blue dashed line where task one stops executing。

 task two starts executing。Then test2 execute， it starts to end， and then when it's done。

Task one continues to execute until it's end。 so notices start one and end one for task one and start two and2 for task2 Now these these regions of time between the start and the end of task one starting the end of task two on the left。

 they overlap in time so task two start an end time over task one start n time So you would say these two are executing concurrently。

Now， they are not executing in parallel because if you look at any one time instance。

 either task1 is executing or task two is executing。 So they are not parallel。

 but they are concurrent。 Now， on the right hand side， we're showing actual concurrency sorry。

 actual parallelism。 So you got the two tasks and again。

 they have the different start and end times that overlap， So they are definitely concurrent。

 but also you can see in that middle middle region of time。

 when task1 test2 is executing task1 is actually executing at the same time。 So on the right。

 we're seeing actual parallel execution。 Well on the left， we're seeing concurrent execution。

 So times overlap， but they are not actually executing the same time。

 Now one thing is that one thing the note is that on the left， the concurrent execution。

 the completion time for both tasks is longer than on the right the completion time when they're working in parallel。

 So parallelism gives you that gives you a better an improved completion time right we already talked about that。

 So one might ask you know why。😊，Do concurrent execution if you're not executing at the same time。

 if it's not actually parallel， you know， maybe concurrent execution isn't that beneficial， right。

 I mean， why not just do test one and then do test two right after it。

 Forget the concurrent execution， and the end time would still be the same。Well， there is a benefit。

 and we'll talk about that。Okay， so just again to reinforce this difference between concurrent and parallel。

 parallel tasks need to be executed， parallel tasks must be executed on different hardware in order to execute in parallel。

 you need different hardware， different cores typically。

Concurrent tasks may be executed on the same hardware。

 but may not right have you could have them on the one process of core and since they're actually alternating right like we saw in the last slide。

 you can execute them on one piece of hardware， one core。

 and you can still say this is concurrent execution。😡，But only one task executed at a time。

So this idea， this process of mapping the tasks to hardware。

Is not directly controlled by the programmer。 So when I say mapping the test of the hardware。

 you've got these you've got these tasks， test1， test 2 that you need to perform on some hardware。

 corere 1， core 2。And determining which core is performing which task， that's what I'm talking。

 that's what I'm calling hardware mapping that is not not directly controlled by the programmer and certainly not in go。

 Now there exist languages where the programmer directly controls that sort of thing。

 Those are generally considered I'll call them exotic。 They're not commonly used， put it like that。

 but that's a complicated thing and it's not part a go。😡，And it's not part of most languages either。

So most of the time in a language I go when you program， when you do concurrent programming。

 the programmer and doing their concurrent programming。

 they are determining which tasks can be executed in parallel Also。

 they're determining a few other things like what kind of communication there is between the tasks。

 maybe one sense data to the other。 also synchronization events will' get until all these details later。

 but maybe so for instance， maybe this test has to do some stuff before this test does its other stuff。

 So they have to synchronize on a certain time。 know this must be finished before this time。

 This must can finish after the time， something like that。

 We'll talk about that but that's what the programmer does。

 the programmer describes what can what can be executed in parallel。

 not what will be executed in parallel。 So what will be executed in parallel depends on how the tasks are mapped to hardware。

Now how the test map to hardware that is not directly in the control of the programmer that's left to the operating system Also the go runtime scheduler that does part of the task too。

 we'll talk about that too That's part of part of the go language actually it gets compiled into your code and it handles some of that too。

 but concurrent programming is where the programmer。Defins the possible concurrency。

 what can be done in parallel， what can't be， but what actually is done in parallel and what is not depends on the mapping to hardware。

 and that's not under the control of the programmer。Now， let's say let's say you're doing this。

 say you have one core okay so you're doing concurrent programming， but you have only got one core。

 so you can't actually get parallelism。 So one might say， look。

 you know why bother why go to all that effort of concurrent programming if I'm only going to get get concurrency anyway。

 everything's happening one at instruction at a time。

 these tests can't actually run together at the same time So even though you can't get parallelism。

 maybe you can't get parallel because you don't have concurrent you have multiple processes。

 multiple cores， you can still get significant performance improvement just from using concurrency。



![](img/7cdef3da47dc3200d25347f96e45c476_2.png)

So the reason why this happens is because typically tasks have to periodically wait for some event。

 some slow event。Now， there are many of these slow events， typical input output things。

So the idea is that in a machine， there's a CPU， a processor and that runs fast。

 But when the processor has to communicate with other things that are not on that are other chips on the same board。

 that is slow So for instance， I got my processor and it needs to talk to external some memory。

 some memory card that is far away on the board when I say far away。 I mean this far。

 but that's far in terms of signal transmission that's far。

 So it's got a communicate with a memory to grab some data from memory or and memories are slow。

 right So you typically have to wait for that maybe it wants to send data on the network。

 So it's got to communicate with this ethernet card， a wifi card and the w-fi card is slow。

 it takes a certain amount of time to handle the communication to receive a send。

So anytime the CPU wants to do， maybe you want to put something on screen， right。

 you got to go to a video card。 So the CPU is communicating with a video card and that has a certain delay。

 So when you have these I O activities where the CPU is communicating with something else on the board。

 but separate from it。 those are slow。 And often， the code has to wait until those things are done。

 So， for instance here。😊，Got this really simple instruction x equals y plus z。

So in order to do this instruction， youve got to read Y and Z from memory and then compute。

 then you can compute the addition and then you can put the result back in memory in X these memory accesses reading Y and Z from memory can take you know over 100 clock cycles。

 just waiting on memory to grab the data from memory So you can way the ad instruction itself takes you one clock cycle。

 but you might be waiting 100 clock cycles just to read the data from memory。

 So when these type of delays， these pauses happen， they don't happen often。

 hopefully depends on how your codes written， hopefully it don't happen too often， but they can。

 depending on how you access memory， memory access path， that sort of thing。 when they happen。😊。

You would rather not have your process of just waiting there for 100 clock cycles。

 waiting for memory。It would be better if the task that's doing this x plus y x equals y plus Z。

 That task， it has to wait for 100 cycles。 But in the meantime。

 you would like to have that processor or core executing some code， some useful code。

 So if you have multiple tasks that all can execute when task 1 is waiting for memory。

 task 2 can execute And then when task 2， maybe it hits the memory access。

 then task 3 can execute while while the other guys are waiting right So that that's called hiding latency。

 That's generally what you' refer to with hiding latency。

 So there's a latency like wait time latency。 So say I'm going to memory， I need to wait 100 cycles。

 You can hide that latency by just taking another task that's ready to run and execute that while you're waiting on the first event。

 So even without having having parallel hardware， having multiple cores say。😊。

Just writing concurrent code can give you this significant advantage in performance because your program no longer has to wait on IO input output accesses。

 whatever type of input output accesses， no longer has to wait。

 It can just run a program that's ready and so things can still get done faster。

 So concurrent programming is useful even without parallel hardware。

Now what I'm showing here is a picture of that hardware mapping。

 I was talking about this hardware mapping concept。In the top。

 I'm showing what parallel execution might look like。

 bottom I'm showing what concurrent execution might look like。

 So the idea here is if say look at the parallel execution one first， you got task one， task2。

 So these are imagine these as blocks of code written in whatever language， go or whatever it is。

And at the bottom， you got Co1 and core2， so these are two cores in a two core system。

This hardware mapping is a task of saying this task runs on this core。

 so you can see with the parallel execution， I've got mapping these two tasks to run in two different courses。

 test one and core one， test2 and core2， so they can execute in parallel at the same time。

In the bottom， you do a different hardware mapping and you say， look。

 I got two tasks and they are both performing， executing on the same core that would be concurrent execution。

But key thing here is that this hardware mapping task from the task to the core。

 that is not directly under the control of the programmer in go or any other sort of standard language。

so。Just to give you an example why that's not， you might actually argue， well， look， why not。

 Why not let the programmer do it， That is a hard problem。 It is a difficult problem。

 And programmers generally don't want to do that。 It would slow you down。 Okay。

 in writing your code it makes your coding a lot harder if you actually perform the hardware mapping。

And there's a lot of research in doing this hardware mapping and automatic techniques for doing it。

 it's a hard task。 The reason why is because these hardware architectures can be complicated。

And there are a lot of things that need to be considered when you're deciding which core is going to perform which task。

 and it would be it would be a really big burden on the programmer to have to consider all these factors。

 And the program would have to be completely aware of the hardware of the underlying hardware architecture。

 One good thing about traditional programming languages。 you know like go， but also Python C。

 whatever is that when you're writing code in these languages。

 you are not directly aware of the hardware of the underlying hardware architecture。 You don't know。

 is this an you know I 7 or is this an I3 or whatever you don't know that。 and you don't care。

 and you don't know exactly what the architecture looks like。 And you don't generally care。 Now。

 to some extent， you care a little， you might want to know look， I have at least this much memory。

 Maybe you care sort of at a broad level。 But the details of the hardware architecture。

 your coding is not dependent on that。 And you really don't want it to be because it is complicated。

 So what I've drawn here。Is a picture of a relatively simple arbitrary multi corere system。

 And this multi core system has got these four cores。 those blue cores around the edges。

 It's got four caches， Local caches for each ch， which is extremely common。 Actually。

 this is a simplification of what you would expect to see。 But each one's got its local cache。

 And then in the middle is a shared memory that all of them share and can read from and dump into the caches and so on。

😊，So when you're figuring out this hardware mapping saying， look this threat。

 this task should be performed on this core， this on this core。

 One big consideration is where is the data。 So what I mean by that is if a particular core core one。

 let's say， So core 1 is going to perform this particular task then it needs to access the data that the task uses So where is the data located。

 the data you want it to be in the local cache for that core。

 but say the data is in the shared memory or in the cache for another core， something like that。

 if the data is not where you want it， then if core1， So for instance， the core ones form in a task。

 but all of this data is on core is to cache Co2 is cache。

 then you got to do these memory transfers and remember the von Neman Bonik memory is slow So doing transfers from memory to memory doing reads of memory can slow you down。

 So when you do this hardware mapping test， you got to think okay where are where is the data。

 which memory have the data which don't。And you basically want to put the task near the data。Also。

 what are the communication costs。 So maybe I'm just doing maybe a cash to cash transfer is pretty fast because caches are fast。

 But if I could do cash to shared memory， shared memory is slower right So what you would have to consider which transfer which communications are fast versus slow So it can get to be a very complicated problem。

 And I know that because I've seen plenty of research papers on that subject。

 it is a complicated problem。 It is not something that generally a programmer wants to have to consider。

 So it is intentionally left out of traditional languages like go。 So go。

 we are doing concurrent programming。 So we gonna we can define which tasks can be performed in parallel。

 but which tests are performed in parallel， is left up to operating system go runtime。

 something else。 The programmer doesn't have to have to consider that。😊，Thank you。

