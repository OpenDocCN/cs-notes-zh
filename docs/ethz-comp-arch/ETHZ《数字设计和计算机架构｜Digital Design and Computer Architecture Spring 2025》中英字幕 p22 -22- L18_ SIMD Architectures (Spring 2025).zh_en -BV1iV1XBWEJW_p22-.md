# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p22 -22- L18_ SIMD Architectures (Spring 2025).zh_en -BV1iV1XBWEJW_p22-

![](img/ca9d27128950c72627cdfa3aab4be15b_0.png)

来。三个人。仓佢系嘅时候。是的。Can you hear me？あれ。然。Oh还。好。你。查了酒。しますさ。没。Yeah。我か。Yes。ます。啊时间。So。Okay。当。不是。其他部问。Okay。

Yes。你。No他。可以。主要我。去。It。Yeah。Okay。Yeah。Okay。ました？はい。还有一个。我问见。ませう。我多。そが。そそうすね。怎么点出。Yes。在这。は有。Yes。没打过。他可下。

那个。我意思。是。还有没有。Yeah。是这个。Yeah。Okay。Yeah。That。Okay， let's get this started。But afternoon， everyone。

Welcome to Lecture 18th。After。Quite long break。 I hope you all enjoy the break。

Today we're going to learn about CMD architecture， single instruction， multiple data。

It's another very， very fundamental topics in computer architecture that many many important architectures that we have today。

Is it a bit loud， I'm feeling some echo？Many important architectures that we have today they are actually implementing CD paradigmine。

 think about GPUs that they are one of the most important and backgroundbone of executing machine learning applications。

And you're going to learn about GPUs later in this course。

 and essentially GPUs are implementing CID in a very interesting way。

So just to remind you about where we were in the brandy scheme of things。

We have covered most of these everything that they are in gray， data of flow。

 spray scalar architecture， realideW stolic arrayt。We haven't covered decoupd access execute。

But we're going to actually premiere an optional lecture right after today's lecture so you can watch it today or later if you're interested。

But this is quite， I mean， very optional。 I mean， it's optional， not very optional。 It's optional。

And is it also very short， I wanted to say very short is only I guess 12 minutes or so。

 so feel free and I recommend you to watch it actually is's very interesting。😊。

ButToday we're going to cover CinD architectures， Victorian A processors are actually very good examples of how to implement CD paradigm。

And then later on in this course， we're going to also learn about GPUs。

These are some readings that you can also check。And this is the optional lecture that I already talk about it。

 about decoupled access execute so that you can watch it later。

But let me first wrap up our systolic arrays lecture。

It's been a while from the lecture that we covered， I hope you still remember Sytoic Car。😊。

Remember that we were discussing about how we can use these architectures in order to implement accelerators and we look into。

 as an example， we look into how we can do， for example， matrix multiplication。

 which is one of the most important kernels in machine learning。And in systolic array。

 we essentially there is a memory that memory pulse data provides data。

 so there is no instruction that we say that okay， I'm loading from memory， so memory provides data。

😊，As in a scheduled manner， and then these data is passes through functional units。

And each functional unit need do some computation on that data and then pass the data to the next and then so on and so forth。

 and with that with this model you can actually implement many important accelerators。

So we cover it in detail， you can also check again this lecture， which I provided the link here。

 but let's conclude systolic array by going over some advantages and disadvantages of this architecture。

So the good thing is that Callig raises， I mean， it a spatial purpose。

 so it provides very good efficiency so we have high efficiency in these architectures。😊。

And also it makes multiple users of each data item。That reduce need for fetching and refing。

 which better use of memory bandwidths。 So when you fetch data from memory。

 when you load data from your memory， you want to do as much as computation as possible on that data。

 and that makes your design much more balanced， essentially， which is very good。😊。

And also provides very good concurrency and also rigorous design。

 which is very important for ease of implementation。But of course， it has also some disadvantages。

 like not good at exploiting irregular priorities。The kind of parallellysis that we have seen。

 for example， in。In out of order processors and also later on in real I value that we wanted to exploit that irregular parallel at the compile time so ss array are not very good at that and also。

The fact that they are special purpose can be actually advantageous or disadvantageous depending the way of yourre looking。

😊，So if you have some very important applications， like machine learning today。

 and you know that this machine learning。So the kernel of matrix。

matic multiplication is one of the most important parts of that。😊。

And this application has effect on many， many other applications。

 so you might want to have a specialized accelerator for that application。😊。

But this architecture cannot be used for other applications。

 so you always need to be cautious about designing general purpose and specialized papers。

 and many of the time you need to find a very good middle way between how much you want to be specialized and how much you want to be general purpose。

So the fact that it's special purpose， it means that it needs software programming software legal programming support to become more general purpose。

And it's also difficult to program if problem does not fit well， of course。Yeah。

This is an example kind of all the systolic array that's designed by HKung in CMU。HD K。

 I think you remember the one that actually also introduced the paradigm。

 he also designed this architecture which is a linear area of 10 cells and each cell provide 10 meggalops programmable processor。

 I mean basically the performance was not that big， but the idea was much more important。

And these basically a linear area of cells can attach to a general purpose host machine。

 so there should be a host machine that controlled your sc architecture。

 just as were also doing today。And they also design high level language support and optimizing compiler to program this historic array。

 and it's used extensively to accelerate vision and robotic tasks。

Which also today also we are using systolic array， as I'm going to show for many of these similar tasks in machine learning。

So this is they call it Warp Comp and this is the picture of it。

 which there is a host and interface you need that actually。

 and here you can see your systo area that I mean， it can have n cells。

 but in one of the version they had ten cells。And you can also check each warp cell if you're interested in data。

But。Later on， more recently， actually， Google has started using also for proposing systolic array for machine learning tasks。

And this more modern modern ci， so they I think they have started this project around the year of 2000。

😊，14，15 or so， and they had this， but later on in 2017 they actually talked about this architecture in this paper that you can check。

But essentially this is the systolic array and when you' are checking this。

 it's very similar to what we also showed so have you are using this systolic array to do matrix matrix multiplication。

 so systolic data flow of the matrix multipier unit。😊。

Sfter has the illusion that each 256 pipe input is read at once and they instantly update one location of each of 256 accumulator Rams。

 so that's the illusion of the software， but the way that they implemented in the hardware is actually using this s array which。

Is essentially doing similar thing， as we already discussed。Yeah， so but this tensor processing unit。

 TPU， you also need to add other units in order to make it work essentially。

 so there is this matrix multipplly unit which is the ssli array that you input weights and also the data to it。

 but there should be also other interface and the controller and processor in order to manage the execution of these matrix multi multiplication。

So later on they also improve this architecture， this is TU2 that they add they have four TU chips versus one chip in TU1 that they had。

 and they provided a higher bandwidth memory and they also provided floating point operations。

And in the end， also they provide a better performance and this is designed for training and inference in TU2。

 which in the past in TU1， they only use it for inference of machine learning。And also。

 you can also learn more from this architecture， from this picture than also the link if you're interested。

I'm not going over detail of this because we don't have time just flashing this architecture just to give you this insight that systolic areas actually has been used in many of today's modern computer architecture。

And TPU3 is the new version of it which they increase the memory and also memory bandwidths and they also provide higher performance。

 TPUV is another version of it which in the end they also basically provide support for more sophisticated applications。

😊，And there are a lot of documents actually going over TPUs， which you are interested， you can check。

 there are not， of course they haven't shared all details of it。

 part of it is actually still not clear， but they have also shared enough such that we can understand the idea of such architectures。

And this is also more recent on TPU V4， and now you can see that we are in this TPU V5 and then trillium。

 which they change the name for some probably marketing reasons。But in Safari。

 we also have done a project， we wanted to understand the efficiency of these TPUs。

 HTPU for running edge， Google neural network models for edge devices。

 so we have done this work together with Google， and we observed that even though these architecture are very effective for doing matrixmatic multiplication。

But still since you are you need to read provide a lot of data from memory to this hardware and that caused a lot of energy inefficiency。

 So more than 90% of the total system energy is spent on memory in large M models and this is one of the plots that we showed in this paper that for some。

Some of these neural network model like LSTM and transduccer。

 we have seen that more than 90% energy spend on Off chip Interconnect and D。

 which in the end that shows you why we need to work more also on the memory style in order to improve energy efficiency of the system。

 we're going to discuss a lot in future lectures about memory system and how we can improve the performance of memory system。

 but later on we're going to hopefully also get to the fact the paradigm of memory centric computing。

Such that we want to essentially we want to do computation where it makes sense where data resides so in today's architecture we are very much processor sent so there are memory there are storage but all of them they are just moving data to the processor in order to do computation and then we need to store back everything to the memory or storage so essentially you are moving a lot of data and you are doing computation only at one place and that one place can be processor CPU can be GPU can be accelerators but in the end you are not using the whole system for doing computation so and as a result your design is not balance。

Which if you remember having balanced design is one of the most important principle that we always need to consider so in memory centric design or story centric or I would say data centric design。

 data centric computing we want to use essentially all parts of the system to do computation so if you have you have sensors that they are capturing some data so you can do computation near the sensors and you have storage。

That stores some of your application data。 so you use the storage to do computation。

You do also computation your memory， your main memory， you do computation， your caches。

 you do computation also in processorces， so essentially the whole system should work together to execute and this is a completely different paradigm and different way of looking at like you' are looking into every component of the system more active instead of being more passive like the CPU the memory and storage they don't need to only say you know answer requests from the CPU or GPU and then just provide data they can also be active and do computation so that's a paradigm that we're gonna also look into hopefully later to give you some insight but such paradigm can actually help a lot you can see that as a result of processor centric design that we have have we have had today more than 90% of energy spend on upstream interconning and D and that's one of the main reason that our design are not energy efficient。

But I should also say that there are other machine learning accelerators that they use。

Some a little different from Sstoic Gare。 cebras is one of them， which。I think we haven't。

 maybe we also covered it a bit in the past in some， I think we did in some lectures。

 but essentially in Cebbros， they have this large is actually the largest ML accelerator chip。

So this is the size of cerebras in 2019 compared to the largest GP at the time。

 and you can just compare the number of transistors in this architecture compared to the largest GP at the time。

And this is a more。😊，Recent version of it and then in 2023 they have this cerebras vfer scale engine gene thats basically provide much more performance and this is the size of this chip essentially which normally when you design you you have design many of these all these dies on a vf but then you need to chop all these dye and then package each die to send right but in vfer scale computing you can actually use all these dies and then you can use communication that's happening across these dies at a vfer scale in order to computation。

Then of course you need to provide a lot to cover it up so that's one of the main challenge here and also some of these dies may not work as a result of a reliability issue that we have right building or fabricating our system so then there should be some ways also to bypass faulty dies in order to do computation。

 but overall this is a very interesting way of also looking at how we can design systems。

We're going to get back to this cerebross design in this CMdy lecture as well later。😊。

If you want to learn more you can actually check this talk from CTO of cerebbras that we have invited him for one of our Safari life seminar in the past this talk was actually very inspiring so I would recommend everyone to check it。

Microsoft also have using a Fiji acceleration for machine learning。

 they have this design that they call it brainba and internally they have a way of data mapping。

 which Im not going into detail of it。😊，But they also provide basically。嗯。

An accelerator as a core as CPUU， a core functional unit。

 soft functional unit in order to do computation internally inside the Fiji as very similar to what you are also doing your lab。

 so you're implementing a MIPS processor as a soft processor on top of your FGA here also they are adding this soft processor in order to do a FiGel in order to do machine learning accelerationcc。

But you can also check this paper if you're more interested。Okay。

 so now I want to switch a little bit the gear and then get to these Sdi architectures， which is。

Exploiting data parallellysis。ItO。嗯。Yeah。对。Okay。嗯。嗯。Okay， any question， by the way， from Systoika？

Okay， Gary。So yeah so SD is actually exploiting data parallellysis SD stands for single instruction multiple data and you're going to see that how GPU is actually benefit from this and S processing is exploiting you can also call it regular parallellysis which。

Using data parallellysis is actually one way of looking at having regular parallellysis in our system。

😊，But before that，'d like to talk about taxonomy of computers using this seminal paper from Fln。

 Mike Flynn。That essentially， Mike Flynn。cateategorize different computers in terms of how many instructions do what to how many pieces of data。

 so you can actually consider two x axis and y axis in X axis。

 you can have instructions and y axis pieces of data。So the simplest version is SISD。

 which is single instruction operates on single data elements。

Which is similar to a scalar processor that we have also seen。

 so there like essentially each instruction that you load and you fetch is operating on single element of data。

On the other hand， you can also have CD， which single instruction operateys on multiple data elements。

And this is what we're going to actually learn a lot today array processor and vector processors are a very good example of how to implement SD in our hardwares。

But when you want to， if you think about it， C is very similar。

Like whenever you want to do operation on vectors， so you have two vectors。

 you have two vectors and you want to add these two vectors element twice。

 so essentially you have one single instruction which is addition and then you want to do this addition across billions of data。

Assuming your vector has billions of pieces of data。

 but we're going to see more and learn a lot of detailing about SD。Another category is MID， MID。

 which is multiple instructions operate on single data element。

 so you have multiple instructions or multiple instruction streams that they operate on single data element。

😊，Any thoughts which kind of computer is similar to Mity？我去。As a hint， I have already covered it。

So systolic array processor or an streaming processor very closest form of MiD so in systolic array you read data from memory and then you do some computation and that pieces of piece of data and then move that part of that data to the next functional unit and then the next functional unit also does something on that data and then send it to next so systolic array actually the closest form of MiD。

And another version is MIMD， which is multiple instruction streams operate on multiple data dilemas。

😊，And that can be multi processor and multi traded processor。

And all these actually categories can be combined， in fact， today's systems like Apple Le Mont。

 for example， is combining all of these when you want to if you think of SOCs like SOC you have system on chip。

 you have processor like CPU which each CPU can have SISD operation and also someMD there might be also some accelerators that they are using MISD and also you can have multiple cores and these multiple processor course can also you know from these MIMD operations so in fact todays architecture are combining all these paradigms together。

😊，And you can check thismicfil paper later if you're interested。Any question？Okay。

So this is MID example from Fllen， which is as we discussed iss very similar to systolic area as we already discussed。

 so this is a data stretch that you read data and then you pass it through execution unit and then you basically pass this data to the next execution unit and the next and the next and then after some time you have your final result which is as you basically generalize systolic area architecture you' are getting to this MID form essentially。

😊，So yeah， this is just a reminder for you that you can check our cisalligary architecture in our previous lecture。

And Cdy from Flint， which we're gonna to actually talk about it today， you have Op storage。

 but then you also have a instruction unit which this instruction that you fetch from instruction unit is shared across all these ops well for example you are fetching an instruction which is addition and then you send this addition instruction to all these different op brandss and that's where your efficiency is coming from essentially so you' are not spending a lot of time on fetching different instruction and also decoding so you only fetch and decocode one instruction so you know what you want to do but then you use this fetched and decoded instruction across。

As many off as possible， like billions of data。So here is actually showing array processor that we're going to see。

 but we can also have implemented in a vector processor that we're going to also see later。Okay。

 so we're going to learn more about Cdi。 So Sdi is actually when you want to basically parallellyze your computer。

 you should be have。😊，you should way of exploiting concurrency。So in data parallellysis。

 the concurrency arises from performing the same operation on different pieces of data， as I said。

 think about adding two vectors together or doing that product of two vectors， for example。😊。

So that's a program of single instruction， multiple data。You can easily contrast the data flow that。

 for example， concurrency rises for executing different operation in a parallel in a data driven manner。

 which is the way that we， for example， exploited parallels mean out of order the processor source or also via a later video at the compile time。

😊，And contrast with trade or control parallels， that concurrency rises from executing different trades of control in parallel。

 so these trades can be very， very different from each other。

And then you can actually parallellyze these threads， for example。

 if you are how many of you have taken parallel programming course？Great。

 so when I'm talking about threat parallel， I think you'll know what I mean basically。

 but we're going to also see later on about GPUs that GPUs actually combined thread level thread parallelities with CD basically paradigm in a very。

 very specific way and that's also possibly the most one of the best reasons that why GPUs are very successful at this moment。

😊，So SIMD explores operation level parallellysis on different data。

 so you can also think of CMD as another form of ILP， which is instruction level parallellysis。😊。

So when you want to when I talk about this vector addition。

 so you have two vector and you want to add， so each of your vectors has billions of elements。

So instead of having volumes of addition instruction。

 which then you actually have a very good instruction level parallelities that you can actually improve performance。

 you can think of having only one instruction as addition and then run this instruction on all these data elements so that's basically you should always also consider that Cindy is not very different of instruction level paras。

 but the difference is that。😊，The instruction that you have and your code is paralyzed is actually only the same one similar instruction。

So same processing paradigm， single instruction operates on multiple data elements。

 this can be in time already in space。Meaning that actually we're going to see very soon what does it mean and multiple processing elements and execution units that you can have in order to around this instruction basically operate on。

Different data elements in time or in space。So here you actually have time and space duality which we we can also think of this duality in other parts of this other paradigm。

 but here is very interesting so the way that you implement CMD in hardware you can think of doing it in array processor that instruction operates on multiple data elements at the same time using different spaces which is processing elements so you have multiple instances of processing elements and each of these processing element are BDP processing element that they are capable of doing everything essentially and like all the instructions that you have。

And then you can parallellyze your instruction across these processing elements。

 which that comes here saying that executing multiple data elements at the same time。

But then you can also think of vector processor that instruction operates on multiple data elements。

In consecutive time steps， in a pipeline manner， using the same space。So you here you don't have。

Processing elements， multiple instances of processing element， you have probably。

 for example one processing element， but these processing elements has some functional units。😊。

And then you can essentially pipeline your execution across these functional units。😊。

We're going to see with a very good example later on， but here basically。😊。

The way that you are getting parallel is actually through time。

 so in consti time you are actually executing different multiple data elements。

Before showing the example of adding and vector processor I like to also talk about vector data register because it's very important。

 so so far when we talk about the scalar processor we also know the importance of having registers right but these registers are essentially scalar but now that we want to do operation on vectors in C manner so we need to have vector data register that each vector data register for example can hold。

 for example n elements of MB values。And so these vector registers here in this figure。

 they are passing basically inserting data to the two your processing element。

So each of these rectangle can be， for example， M bit so these two embit are passing through this crossing element you do computation and then you store it in another vector register and then in the next cycle you are fetching the the next element of these vector registers so you also need to change。

You registerify when you want to support vector processing essentially。

So in this example I'm showing how A and vector processorces looks like actually。

 so in A processor we have， as I said， multiple instances of processing elements and each processing element is capable of doing all instructions。

And in vector processor， we have different functional units。Which。Each unit is basically is。

Is customized or assigned to a specific corporation。So this is our instruction stream。

Wwhichch consider them as a load like vector instruction so this the first one is vector load so you're loading four elements of data from RAA to the vector register and then you add the vector register VR by1。

And then you multiply VR by two， I mean all these are element voice。

 so each element of VR needs to be incremented by one。

 and then each element needs to be multiply by two。

And then you store the results at VR to the same array that you had so this is your instruction stream which is written in the vector basically ISA we're going to also see about the ISA of vector instructions later。

So when you want to run it on array processor， since all these processing elements are capable of doing everything。

 and here we are considered that the number of processing elements here for is also equals to the number of elements that we have。

 which is4 again。So you load the element zero， element one， two， and three。

 all at the same time because you have different processing elements。And then at the next cycle。

 you'll going into the next instruction， which is addition。

And the next cycle you go to the next instruction， which is multiplication。

 and then the next cycle you go to the store。So everything is completely paraise。

But an vector processor， you basically you can in the first circuit。

 you can do load operation for the first element。But you cannot at the same cycle。

 you cannot do load operation for other LMSs because you only have one load functional unit essentially。

So then you need to make a pipeline here， so the next cycle you can do the load operation of the second element。

 and then you can do the addition operation for the first element that you have already loaded。

And if you know about pipeline， it's actually very easy to reason about。

 so essentially you load more and consecutive elements and then you do addition multiplication and at some point you also need to finish the story。

😊，So that's the vector processor that we have。So when you look at array processor。

 you can see that the same operation is happening at the same time。

But in vectorex processor you have different operations at a given time。

And for every processor in a space， so you are doing different operation at the same space。

That's why your processing elements are capable of doing everything。

But in vector processor at each space， you are doing the same operation。

So you can actually see that vector processors are。Much simpler to implement。

 And that's why they were actually very， they were more basically。😊。

Interesting in the beginning because of the you know limitation in hardware resources。

 so people started building vector processors。And also the performance of vector processor for such a small code is you can see is not great。

 but if your code is bigger and then your pipeline basically you are loading more data so your vector lace is also longer at some point your steady state throughput is going to be okay right so here you are finishing for instruction at the time。

😊，At the given time， we are finishing for instruction in our processor in vector processor also at the state state。

You are running for instruction， right， so the state of state throughput is actually good。

But later on， by advancement in integration， array processor becomes more basically interesting and people implement array processor more and more。

 and today actually we are implementing， we are using both of them。

So we're going to see actually about GPUus， that GPU is actually nicely combined。

I processor and vector processor together。 So essentially you have several processing elements。

But each processing element is also fully pipeline。

And then I'm going to actually show you the picture at the end of today's lecture thats how we can combine these two paradigm together。

Any question？Okay。So since you know about VIW it's also interesting to see the difference between CD array processing and BLIW so in VLIW we are running multiple independent operations that they pack together in a long instruction。

 so these instructions are different。And VLIW compiler makes sure that these instruction are completely independent。

 so you don't need to do dependency checking， and then you are sending this instruction to your processing elements。

However， in Cdi。You have single operation on multiple different data elements。You have here。

 you have your addition。Assuming your vector links is also four。

 then you are passing through this additional operation to different frosting elements。

So if you compare these two， actually， it's similar that， for example， if we want to。In real I W。

 if you consider that all of these operations are the same， like all of them are addition operation。

 you're going to get to。Similar to this Sdiary processing right。

 but then the thing is that with Sdi processing you are fetching only one instruction so your bandwidth usage is actually much less and then you are also decoding only one instruction。

And then you are using that instruction so that part is actually much simpler compared to BLIW here you need to actually load all these instructions and all these instructions are different。

 meaning that you also need to decode them。😊，But here人呢。SyMD execution here。

 you load one instruction and then you can amortize the overhead of loading。

 fetching and decoding across many elements of data。So。

Although real that seems more general purpose because these instruction are different。😊。

But the way that VLIW is getting parallel is actually very。

 very hard to exploit it at the compile time， so that's why。😊。

SMD processing actually are today are much more successful for the specific type of computation that they are focusing。

 So this is more a specialized purpose if you think about it because you are considering that you have one single instruction that you want to run on many。

 many data elements， but for those applications。😊，That for example。

 you are doing operation on vectors like machine learning， matrix， matrix multiplication。

 so this type of execution is very very useful and that's why CD processing is very useful these days。

😊，But later on， I'm going to actually show a picture from a V light Le paper from Josh Fisher that he actually talk about why Cindy is not a good。

Approach because of the programming， which is actually true。

 but at the same time as I said for the application that you are looking into and you are interested for CD like vector processor an application that you're operating on vectors。

 these type of computation is a very good fitat and then you can get performance out of it。😊。

And this is the lecture that we taught about VLA that you can check Okay， any question？

So now let's learn more about vector processors in a bit more detail。

 So a vector is a one dimension on array of numbers， which is a mass definition。

And many scientific commercial programs use vectors， here is an example that we have a loop。

That you're operating on 50 elements of data。And you have two vectors that you are basically get calculating the average of each two elements and it stored on the vector C。

 essentially， we're going to actually use this code in order to compare later on the performance of vector processing。

😊，So a vector processor is one whose instructions operate on vectors rather than scalar or single data values。

But there are some basic requirements， so you need to load and store vectors。

 so that's why we need vector registers that contain vectors。

 we've already talked about vector registers。You also need to operate on vectors of different length。

 so here， for example， my vector is 50。There there might be a code that vector length is 10。

 there might be a code that vector length is I don't know，1000。

 so you should be able to operate on different length， so that's why we have vector length register。

 There is a register that you can set in order to know your vector length。

And also we have these elements。So there should be a way to understand how we can get each data from memory。

 like how we can calculate the memory address。So elements of a vector might be stored apart from each other in memory。

 so when you want to load the vector。You're loading element by right so each element might be exactly the same location in your memory which meaning that you which means your stride is one so we call it a stride so you have the address for the first element and then in order to load the second element you just increment the address by one and then you load it and then you increment by one and then you load the second one so now your stride is one but you're going to actually see I guess very soon that that might not be always the case so you need to have a support for different stride in fact I think yeah you're going to see example immediately。

So I assume that we have two mattresses， A and B， and these two mattresses are restored in memory in row major order。

Anyone？You guys know what is bro major order？So row major order means that when you want to store a matrix elements that they are consecutivesive in a row。

 they are also consecutivesive in the memory， in the address。So here is an example。

 you have these two mattresses， A and B， and these elements0，1， two， three， four45。

 these are in the row of the mattress right。So when you store them in the linear memory。

 you actually in a row major order， you essentially store zero。

 and then immediately after that you store the second element in the row and then second and next and next and next。

while in other way of storing which his column major out there。

 basic elements that they are consative in a column， they are also consative in the memory。😊。

Which this actually has a lot of effect on locality cache prefiing。

 which we're going to actually see later on in our memory system lectures。

 but here I just want to talk about different right。😊，So you essentially here。😊。

When you want to do this operation， you want to multiply matrix a， which is 4 by 6 to matrix B。

 which is 6 by 10 and then get to the matrix C， which is 4 by 10。

So we need to essentially do this dot for a of each row of matrix A with each column of matrix B。

 right？So you first need to load the row of a to a vector register， which we can call it vbon。

So so far so good， right， because your straight is one。

So you calculate your increment by using a straight one and then you load。

But then when you want to load the column of here， for example， column zero of matrix B。

 you need to increment your addresses by 10。Because you are starting in a row major order。

So now you need support for the strike of 10， so that's why we need support for different strides in order to implement CD operations。

 essentially。And this can also have effect on。Memory。

 the efficiency of memory that we're going to actually see later on today。😊，Any question about this？

It makes sense， right？Okay。So a vector instruction performs an operation on each element in consecutive cycles。

 vector function units are pipeline and each pipeline stage operates on different data elements vector instruction that allow deeper pipelines because there is no intra vector dependencies。

So in each vector， all these elements are operating on the same instruction and so there should not be any dependency so we don't know hardware interlocking needed within a vector there might be some dependency across different instructions as we have seen in our example。

 that for example we are loading and then。We were adding that vector by 1。

 and then we were multiplying that vector by 2， so there is a dependency across elements。

Across different instructions that we are doing on this vector。

 but while you are operating on a vector instruction， there should not be an dependency。

And no control flow within a vector because everything is regular。And then the fact that we know our。

This makes it easy to address calculation for all vector elements。😊。

Like having a stride of on makes everything so easy。

 so there is a logic in processor in order to calculate the next the effective memory address。

 essentially the address that you need to access by that， you can access memory and get your data。😊。

So the fact that you know your is right here， you can easily， get your data from memory。In fact。

 sooner than the moment that you needed using prefeing technique that we're going to actually also see later on in this course。

 but this knowing a stride makes it easy for loading and address calculation。

🎼Let me conclude with some advantage and disadvantage and then we will get break。

So vector processor advantages， of course， there is no dependency within a vector。

 which is great and each instruction generates a lot of work。

Which one of the reasons that why these architectures are very efficient。

 so you amortize the overhead of fetching and decoding and instruction by over many data。

 which leads to high energy efficiency error production is probably one of the reason that why GPUs today are energy efficient。

And no need to explicitly code loops， so whenever you have a loop in your program actually such loops can be vectorized and then you just vectorize that loop and then you might have you will have much fewer branches in the instruction sequence。

 which is very good for pipeline， I think by now you really know that branches are not very good for pipeing as we already also discussed。

And it's also highly regular memory access pattern， which is good for designing your memory system。

But of course， it has disadvantages。So this simply actually works if parallellysis is regular。

 like vector operations。😊，But it's actually very， very inefficient if paralysis is irregra。

 for example， when you want to search a key in a linked list。

 then your paralysis is actually very irregular and these single architectures are not very good at it。

😊，So this is the quote from。AFisher realized value。

 which I actually preface it earlier in this lecture。😊。

That he's saying that to program a vector machine， the compiler or hand codeder must make the data structure in the code fit nearly exactly the regular structure beat into the hardware so basically programmers should really know how we have these C structure in our code and then map your elements of your data nicely in the memory banks or in memory such that you can basically read your data and fit data to your hardware nicely and you basically have very good efficiency。

So that's hard to do in first place and just as hard to change。

 So one tweak and the low level code has to be really written by a very。

 very smart and dedicated program who knows the hardware and often。Subsidize of the application area。

So this is one of the reason that this architecture had some issue basically。

Any like difficulties in order to program。But people are also looking to by how we can actually make it more easily programmable。

 which we also hopefully see later in GPUs and this a recommended paper or realW that you can check。

And I want to say that we should not forget about Amdo's law。 So I think by now。

 you all know about Amdo's law， we already covered it before。 So in Amdo's law， basically our。

Speed up that we are gl from parallelization is actually bonded by the parallellyizzable fraction of a program so the part that is paralyzable。

😊，Assuming that you are running on end processor so you can actually reduce it by F over N。

 which is very idealized assumption， we actually go into a lot of details that why is not why it might not be the case in our advanced computer architecture course。

Wwhich I'm going to actually show some slides about that also later。

 but essentially assuming that everything is idealized in the paralyizzable fraction and you have infinite number of cores。

 then this fraction will lead to zero right and then your of would be1 over1 minus f so if parallelizable fraction of a program is 50% then your of would be up to2。

😊，Which is very sad， assuming you use billions of course and then you get only two speed up。

If your paraizable fraction is 99%， then you can get up to 100 speed of if it is 99。

9% then you can get 1000 the speed of so we should not never forget about this part and this serial portion might be only distributing task over all these threats or all these basically a course so that's why actually Amzo is very fundamental you cannot get rid of serial portion completely but there should be a serial portion of the program at least to distribute task across many of these course。

Okay， so you can also check this under law and if you're interested。

 you can also check these lectures that we are teaching in our advanced computer architecture to learn more about this topic。

Okay， so I'm going to stop here。Let's get back when the ring builds。

And then we're going to continue with this part。I think there is an also announcement。嗯。

From some of your friends， yes。

![](img/ca9d27128950c72627cdfa3aab4be15b_2.png)

![](img/ca9d27128950c72627cdfa3aab4be15b_3.png)

![](img/ca9d27128950c72627cdfa3aab4be15b_4.png)

I'm sorry。So don maybe twice。So the other way like this yes like this。Oh yeah， good。 Okay， perfect。

If you thisOkay。Hello hello hello can you hear me okay I'm sorry to disturb your well deserved break but just give me like one two minutes of your time would be greatly appreciated I am from the ET Enpreneur Club and in cooperation with Star Global we are organizing a AI hackathon。

😊，And i'm just here to briefly talk about this yes perfect so we' are partnering up with the ETH AI Center and with Hoshi and these two will provide the challenges for the hackathon。

And there is a big prize to win and it's free tickets to the race summit happening in Paris。

 it's a big AI summit where the CEO of Intel there will be there。

 the CEO of Sta overflow will be there and a lot of other big guys will have talks will be a big event。

 so yeah。Definitely something to keep an eye out for。

And if you're interested we'll be very happy to see you apply the date is the 9th of May to the 11th May and it's happening in Zurich there will be free food yeah we'll be happy to see you there so that's it thank you very much for your time and then hopefully see you there。

Okayty。Yeah。Yeah。当时把固去。大k大。Okay。Of。This是。

![](img/ca9d27128950c72627cdfa3aab4be15b_6.png)

Yes。I can just leave right。fThank you very much。嗯。喂也。Oh。actually sacrifice。就那。嗯。Yeah。他说。你错。是否。です。

OkayYeah。呢个钱。他这个使少。行。So。过来那我。Okay。我把我的。报。自。かす。这刚才。We。ですよ。有啲么。Okay。这个好也是。ど。你出得内啊。え違番。Yeah后。问系。啥就是那啊。

てて要す。我只道就是。よ。W。手收。你非常。才。ますね。要啊。呢个。Yeah。只有。Oh。你咯。Okay。什。谢。这白法。我。嗰个啊。我正到。我我。做没下。唔系个。Yeah。到。把意服。あす。你给他。

Good luck， thank you。Okay。こ。Yeah。Okay。Thank。把身。我们。是万的。不可以。不对。我时。Okay。そ分さ。好作。そこど。杨说。被告公司。知道。それまで。9点前。

这有。原告单。四気。你点个他直。对这个。丈で。系唔知道个。啊。我。Yeah。回打号。这个情况呢。啊そ。我这度こ。反只有问题。那是。贵。系。嗯。🎼，我的。Okay， let's continue。

Is everything everything okay？违法。Okay， so we were discussing about these advantages of this architecture。

 We already discussed about。And the fact that these architectures are very good when you have data level parallels。

😊，But they are not very good when you want to exploit irregular paralleles， or for example。

 as a very kind of extreme example。😊，Think about searching a key in a linked list so that this architecture might not be really efficient for it。

But as another also very important limitation of this architecture is that memory bandwidth can easily become a bottleneck in this architecture。

 especially if compute and memory operation balance is not maintained。

 which unfortunately is more or less the case for today's computer system。😊。

And the data is not mapped appropriately to memory banks we're going to see about these memory banks also later on very soon。

But I should just I want to just give you some insight here that why memory brandies can be an issue here。

So in this kind of architecture， when you run when you execute a load operation。

 this load operation is not， you don't want to load a scalar element right。

 so your operation is vector load and you want to execute this instruction across billions of data。

So immediately by executing this instruction， you're going to send a lot of like billions of memory accesses to your memory。

😊，And then your memory should be able to sustain enough bandwidths to feed all these data elements to your pipeline。

 to your processor。Otherwise， you pressing elements they're going to be waitingiting to get data such that they can continue。

 So that's why actually why memory bandwidth is a very。

 very big issue for such kind of paradigm that we are considering single instruction multiple data there are。

 of course ways to you know to mitigate this problem， but。😊。

But I should say I should say that still we have this issue， and that's why。

That's why I talk about the importance of using memory centery computing， for example。

 that we remove computation at least partly to our memory。

 such that we have much more bandwidth there。Okay， so let's look into vector processinging more depths。

 so we already talk about vector registers， each vector data register holds NM bit values。

We have different kind of also control registers like vector length that shows the length of vector operation that we are operating on。

Also the vector strip， which shows the stride， basically that you need to use when you want to load in data from memory。

And also another very important register which we call it Vmask。😊。

And this register is used in order to masking operation across some of your elements。

So in part of your execution， we're going to also see an example。

 you may not want to do operation across all data elements that you have in your vector。😊。

For example， you have two vectors。And you want to basically do addition。

Only for elements that you're staying at the odd position， like we want to add basically element one。

 element three， five， seven， and so on and so forth。And other elements， you don't want to touch them。

Then you can actually use this vector mask， and then you can initialize vector mask nicely such that you do this operation only for those elements that you want to do and for other elements you basically you ignore and you don't do anything。

😊，We will see about how we can also implement VMS and also with more examples later on。

So there should be maximum vector lengths。So you cannot set vector length to any anything basically the designer should make a decision that what would be the maximum for example it can be 64 like then you can house up to 64 registers like the elements in your vector register。

 but there might be some some moments in your code that you need to set vector length to a lower amount so if you don't initialize or set vector lengths then you're going to use the basically the。

The value that you have default value， which is the maximum， but then you can also during your code。

 you can change the vector length value， which of course。

 comes at the price of some inefficiency but。Sometimes you have to do it in order to be correct。

And the vector mask register are already discussed about it， for example。

 here is one way of basically， for example， calculating vector mask。😊，So you want to。

For those elements of vector k that equal to zero， you want to have this vector mass equals to 1。

 so essentially you are saying that V mass I equals to vector K if it's equals to zero essentially so that's where you can set V mass and then later on you can operate on V mask is actually if you know it's very similar how we implement predicated instructions。

So in our normal programming， we， for example， use if and Ls。And then when you compile it， you use。

 for example， branches， you know， to implement if Ls and lu pencil， but with vector mask。

 you can actually consider that。Is a way of implementing， which we call it predicated instruction。

 so you always execute。😊，But then with the control bit。

 you sometimes you disregard or ignore that instruction if you should not execute it。

 we're going to see。Later。Okay， so this is a vector functional unit has another I mean here an example that you have two vector register and then you can feed data to your basically functional unit your functional unit can be pipeline we discussed that actually we can easily do it because these functional units you don't need any interlocking in your pipeline across data elements within vector。

So you can easily pipeline it and that's why actually vector processor are heavily， heavily pipeline。

So this is actually one of the first supercomputer designed for benefiting from Cindy。

Crarayvo that you might have seen actually a version of Cray in the cap building。

 How many of you have seen that actually。In inflow。Of cap building。The yellow thing。

I'm gonna show you the picture。But I I。I remember the first time actually。

 I came to ETH actually I also， and not the first day， but in the very， very first days。

 I visited that Cray XMP architecture in Cap。😊，So the interesting decision of Cray was that they have both scalar and vector modes。

 so remember about Amd's Da I said that the speedup that you're getting is very much bonded by your serial parazable portion of your program so you should be able also to run scalar part of your program or sequential part of your program fast enough。

 so that's why Cray actually was quite innovative at the time and they designed one of the fastest vector processor at the time。

 but they also designed the fastest scalar engine at the time。

So together these vector instruction and vector functional unit， and also this part。

 which is a scalar。Creray actually was able to provide a very good performance at the time。

 which is was。I think one of the highest performers at the time。



![](img/ca9d27128950c72627cdfa3aab4be15b_8.png)

And you can also read this article about Cavvoon。And this is a picture that I promised。

Now you remember that we have seen it。😊，So next time you can actually also read information about this architecture when you visit this。

 I'm not over detail of it， but。😊。

![](img/ca9d27128950c72627cdfa3aab4be15b_10.png)

In the end you can see that Cray actually combines vector instructions and vector functional unit and a scalar functional unit together in order to provide good performance one thing that I wanted also to mention that they forgot is actually the memory part so as I said memory actually needs to provide very good bandwidth to your vector functional units and that's so in this architecture for example they have 16 memory banks and that's one way of providing very good throughput out of your memory to feed data to your pipeline。

Okay， so you can check all this information about Craig and if you're interested。

 but essentially Se or Kere which is leader of supercomputer design。

 he was a very principle architect and he actually made this very interesting question。

If you were cloing a field， which you would rather use to strong oxuxen。Or。1000 chickens。

Any take care。Yes。😊，It difficult to if youd find a way to them， accordingly。一 strong嗯。你喂要。Our。そ这。

Thatた。Yeah， very， very interesting respond so essentially。😊，So this is also a trade off between。

A few beefy cores that they are very effective on provide very high performance。

But there are only a few or thousand of VP cores that they are not very strong。

 but they provide basically performance should if you are able to distribute your execution nicely across all these thousand chickens or thousand VimpP cores。

And then you might be able to basically for very good performance by such design。😊，But if you're not。

 for example this kind of application， which is ping a field probably as your colleague actually correctly mentioned it's very hard to coordinate thousand chickens to clone a field but there might be some applications that for example。

 it's easy to coordinate thousand chickens or thousand0 VP cores so basically that's why I actually see more gray and also other people that they were designing supercomputers at the time they basically get to this decision that we need to combine both pipelines so we need vector processors as well as vector functional unit as well as scale their functional units and there should be a way to basically when you have both then you can hopefully provide good performance。

But my answer to this question is actually it depends。As always。😊，Okay。

 so we talk about these memory banks， let's see a little bit more why we need to bank memory。😊。

So essentially in vector Pro， we have these loading and storing vectors from our two memory。

 so that requires loading and storing multiple elements。

And elements separated from each other by a constant distance， which we already discussed about it。

 which is a strike。So we can， for now， we can assume a straight is one。

So elements can be loaded in consecutive cycles if we can start the load of one element per cycle。

So that's the key here， so if you can start loading basically each element in a consecutive cycles。

 then you can basically also loading one element per cycle and then feed that element to your pipeline and then have your pipeline for。

 otherwise you're going to get to this situation that your pipeline is installed because you don't have data to fit to it。

So meaning that we need to sustain a throughput of one element per cycle。And of course。

 the question is that how do we achieve these with a memory that takes more than than one cycle to access So if your memory is monolothic and your access latency is one cycle。

😊，So you。Basically， the issue of one load instruction to your memory。

 And then if the latency is one cycle， you get your data and then the next cycle。

 you get you issue the second one and then so on and so forth。

 So you are getting everything and then you can sustain this throughput。But of course。

 the problem is more interesting or challenging if you consider that your memory is I mean。

 has longer access latency， which usually the case。

 our memory are not that fast so we cannot get data of one cycle。😊，So one way， for example。

 would be to basically provide more ports。So if you， for example， your your vector links is 64。

 then you can consider that， okay， I'm going to add 64 memory ports。😊。

To my memory such that I can issue all these memory instruction at the time， for example。

 at the same time， but that actually comes at a very huge cost。😊，And people came up with this。

let's cost this solution which they bank the memory and they interleave the elements across the banks we're going to also revisit this concept of banking and interleing when we get to our memory system lectures。

 but here I will also provide some basically information about it。😊，So by banking。

 what I mean is that this is your。Basically， memory chip。

The direct tank is that I'm basically drawing here virtually。And then internally， in your memory。

 you can see that， for example， here， 16 banks。😊，And for each bank。

 you can have a memory data register and memory address register that you can use to access each of these banks and then get the data。

However， your data bus and address response is shared。

So you don't have basically still your your memory is single port。

 you don't have multiple ports for your memory， So your memory has one data bus。

Which means that you have one data port， which here we are considering that we are using that port for both writing and reading and then we also have one address box which we can use to address our memory but internally inside your memory you have this banking so you can have several banks and each bank can be accessed separately。

So memory is divided into banks that can be accessed independently。

 banks share address and data buses to reduce memory chip pins。

So that's what I'm exactly talking about it so these database and address was are shared so you don't need to increase the number of cheap pins in order to support this architecture。

And we can start and complete one bank access per cycle， hopefully。

And this can sustain n concurrent accesses if all N go to different banks， so if your request。

 for example， the first one goes to bank zero。Then the second one goes to Mac1。

 the third one goes to Mag 2 and so on and so forth。

 then you can actually sustain inconcurrent excesses。However。

 you might run into bank conflicts that consecutive accesses can conflict in the same bank。

 and then that comes at the price of basically s execution of that bank。

 which we like to avoid that situation as much as possible with some techniques that I'm going to also provide very。

 very quickly， but essentially that's a problem that still we have。

 like in GPUs in modern GPUs when when you are using memory， you are observing some bank conflicts。

 which actually reduce your efficiency a lot。Okay， so in a vector memory system so the next address is previous address plus a strip so this is we already talked about it right so we have a base address which for example from the element zero so you have a base address and then when you want to calculate the next address you basically add this base address with the strip。

And then you calculate your next address and then you write this next address to your base register and then you keep adding this strike to calculate the next addresses so that we already discussed about it so hopefully if your base address goes for example to0 address zero and then your is one then the next one goes to address one the next one goes to address23 and so so on and so forth so this can actually you can sustain all these 16 memory accesses at the time。

So here is basically conditions that if you met， you can basically get this throughput of getting one memory access per cycle。

 so if a stride equals to one and consecutive elements interly across banks。

 and also number of banks greater oral bank latency。

 then you can sustain one element per cycle throughput。So assuming that your bank latency。

 for example， is 11。😊，Then you can having 16 banks meet this condition， but if your bank latency is。

 for example， 32 and you are using 16 banks， then you cannot sustain。Why is that because？

So you're sending basically the first。Element zero to this bank zero and then1 and two and then so until reached this bank 15。

You are not done still with this operation of Bank zero because your memorial access latency is more than 16。

Then you actually， when you want to fetch or load the memory address 16。

 you need to access this bank again， right if you interleave like this。

So then the memory axis 16 needs to wait for 16 additional 16 cycles such that this can be done。

So that's why it's very important that your number of banks should be greater than bank latency。Any。

Question here。Does it make sense， yes， yes。Yes， they are implements in the hardware failure。Well。

 I could imagine if we went to fetch different disruptions at the same time。

 than we probably disagree。望到。あ。Yeah that。So in this example， in our C。

 we are not fetching different instructions， we are fetching different data elements。

Because we have single instruction， but yeah， those data should be actually inter leave across all these banks especially that we don't get to bank conflict as much as possible。

😊，But that's not enough， so your number of banks should be also greater than bank latency such that you can get this to this throughput。

So if I want to give you some clue here， GPUs。That you're going to see that they are also S engine underneath。

 They are using high bandwidth disk memory today， and high bandwidth dis memory are heavily banked。

 So those of the memory GPU memory that they call it device memory。Has a lot of banks。

 and that one of the reasons for that many banks is actually to sustain good throughput for the execution。

Yes， there's no reasonable possibility to judge the banks。When it's wrong， because we might have。

Different applications where we use the same memory， but。Yeah。

 I guess the different data elementscur yeah so basically your question is that if we can change the design of bank like having a memory with four banks and then we customize it like eight banks and 16 and so on and so forth right so problem would make more sense the data。

So yeah relocating data is possible， but if you want to change the number of banks at runtime。

 you can of course do it， but you need to basically consider some harder for it essentially right because when you want to when you have 16 banks。

But then for some reason you want to make it to eight banks。

 then these every two banks should be combined together to make it one single bank right so that hardware needs to be there。

 so there should be a way that you select across these like using multiplexer for example can be a good solution here。

Any other questions？O。So， now， let's。See the performance of this kind of architecture by going over this example。

 so this is the for loop that we have seen in the previous slides。

And this is a scalar code if we want to implement this in assembly。Basically。

 we move initialized registers 0 to 50， which is going of control the number of iterations that we need to do here。

And then we need to move the address of RAA， the base address to register1。

 the base address of RAB or vector B to register2， and the base address of RA vector C to register 3。

Then in a loop， which we have this flag X here， we load two basically memory of elements， r4 and R5。

 which is basically AI and BI。And then we add these two registers and then we shift the result of this register to by one to the right in order to divide it by two。

 and then we can store it。And after that， you basically need to branch back to X and then repeat this operation for 50 times to get the final result。

Are you all happy with this scalar implementation？I hope so。Christian。Okay。So， let's。

I wanted to ask this question， but I showed it actually， So how many dynamic instructions do we have。

304。Why is that because so here we have four instructions？

Dynamic instructions actually mean that the number of instructions that you actually execute so in your assembly code here you aesthetically you have in your loop you have one。

 two， three， four， five， six instruction right but these six instructions actually are going to be executed 50 times。

So dynamically you're going to execute  300 instructions for this loop。

 and then you also had these four instruction in the beginning。

 so in total 304 dynamic instructions in order to execute this scalar code。

So they scalealar execution time on an in order processor with one bank。So， we first。Two loads。

 so assuming our memory is instead also 11 cycles。So these two loads is going to be 11 cycles。

I actually put the latency of。Every instruction here， So these move instruction。

 we assume that the latency is one。And then your load instruction is 11， so you have 2 11。

And your addition instruction， the latencyencies four cycles， for example。

 your shift instruction latency is one。Story is again 11， and then your branch instruction is two。

So if you basically。Calculates， you're going to get to these 2004 cycle execution cycles for this code。

But you can actually make it better if you consider a scar execution time on an in order processor with one bank。

 however with two memory port， so now you have two different memory accesses can be serviced concurrently。

 or we can also consider that we have two banks where R is B and C are restored in different bank。

Essentially， you can now you can basically do these two load operation。In。In a pipeline manner。

So the first two loads in the loop can be pipeline。Which in the end。

 you're going to get to 12 cycles。And then if you get back to the。Example。

 you're going to get to this 15001，504 cycles to execute this scalar。quoteote。

But now this is not very interesting， we want to see how much we can improve the performance of it by using SD instructions。

So first the question we be ask is that if the loop is vectorizable， so a loop is vectorizable。

 if each iteration is independent of any other， so that's the key that we can use for SMD instructions。

 remember that we don't want to have basic dependency across elements within vector so that's why different iterations of this loop should be completely independent such that we can vectorize this codity。

Which essentially is the case here。 So every iteration is independent of every other。

So vectorized loop can each instruction and its latency。So here is a vectorized version of this code。

Assuming that our vector length can be 50。At least can support up to 50 so we set vector length to 50 and also we set straight register vector stride register to bondn。

Then we can we should load a to vector 0 and B to vector 1。

And then we do addition for these two vectors， v0 and v1， and we store to vector2。

And then we shift element wise to write vector V2 and get V3， and then we store V3。Okay。

 so this is our vector version， so how many instructions， dynamic instruction do we have here？😊。

And thank you。Yes。😊，我都晒觉。そ。11 instructions and how did you calculate that？我们就。なか。

But assignment those statements are。So these are a SD instruction， right。

 so each instruction is going to be executed across 50 elements。And there is also no loop here。

So the number of dynamic instructions equals the number of static instruction here。Which is one，2，3。

 four，5，6，7。So we have seven dynamic instructions here。So that's part also， as I said。

 why Cdy execution model is very efficient because you don't need to deal with。

304 dynamic instruction that we' already seen because all these instruction need to be fetch and decod here you only fetch and decode seven instructions。

So the latency of each of them， so this move vector length， the latency is one。嗯。

I should also say that in this example， we are considering vector processor and not a processor。

And so this move for stride registry is also latency on for load instruction for the first element。

 you need to spendd 11 cycles， but after that since is completely pipelined。

You get every element per cycle， so in total you need to spend 11 plus vn minus one to get get your load instruction to get it done。

And for this second load instruction is also 11 plus billion minus1 for addition instruction for the first element the latency is4 but then it pipeline so it's going to be the total billion4 plus billion minus1 and so on and so forth。

 so this is also the calculation of latency for each of these operations。😊。

So assuming that we have no chaining， which we're going to also see what is chaining very soon。

In fact， actually we have the definition here so output of a vector functional unit cannot be used as the direct input of another we're going to see is a very interesting way of increasing the throughput of vector processor。

😊，So the entire vector register needs to be ready before any element of it can be used as part of another operation。

And also assume that we have only one memo report， meaning that also one address generator per bank。

And our memory is 16 banks and we have this word interleaved consecutive elements of an array are restoreord in consecutive banks。

So with that， you can actually sustain good throughput here， right， one element per cycle。

So this is a timeline for the execution we have two one second and then here。

You need to expand first 11 cycles for the first load of element and then the rest is 49 cycles to load everything of vector a and then the second vector 11 cycle and then 49 and then this is addition which is four cycle and then 49 and then shift one cycle and then 49 which is really and minus1。

😊，And then your store which is 11 and then 49， so if you summyW is going to you get to 285 cycles。😊。

So basically improve performance from 1，504 to 285 cycles by doing this。

So why we have 16 banks here because our memory access latency is 11 cycle。

And we usually in computer architecture， we usually want to have the number of banks to be two to the power of something。

 because with that， you can easily basically do this address encoding and decoding。😊。

So also the above assumes a unity is right， which is right bond。

Which is correct for our example program。But what if strike is greater than one。

 how do you ensure we can access 111 per cycle when memory latencies 11 cycles？Yeah。

So this is what we already discussed about it。We're going to see that later when the stride is bigger than one by considering at least of some condition。

That this is right and the number of memory banks are primed together， are prime numbers。

 then you can actually still sustain one opprint per cycle。Okay。Okay。

 so vector chaining that we already discussed with。

 I want to see how the performance changes by using vector chain。😊。

So you can do data forward wording from one vector functional unit to another。

Meaning that when you are loading Vvo， you can while youre loading elements of Vvon。

 you don't need to wait until you load all the elements of Vvo so you can。

As long as you have one element loaded， you can actually move it to the next step。

 to the next instruction or to the next functional unit。😊。

And then here also as soon as you have the results for V3 at least for one element。

 you move the instruction data or forward it to the basically next instruction it's very similar to data forward wording that you have seen in pipelineing but in vector processor they call it vector chain so as you produce your data you also try to consume it immediately such that you don't waste time essentially so your pipeline is going to be much deeper essentially。

So here we can see we can chain our basically load unit to multiplication unit。

 and then you can chain it to also addition unit and with that you can actually increase depth of your pipeline。

So by using vectors chaining， you can actually improve the performance of this code。

You can so you cannot steal basically pipeline， you cannot do this the first two load together。

 I'm going to ask you the reason。But the moment that you have at least two elements。

So here you have the first element of basically vector A。

 and here you have the first element of vector B。So this moment。

 you can actually send the data forward the data to the addition functional unit to do the addition for this two first element of A and B。

Here also， you have the addition for the first two elements so you can move to the result of the shift functional unit。

And after some time， you can do also the store operation。So now you get to 1882 cycles。

 but then the question is that why these two vector loads cannot be pipelined。

And why this load and its cannot be pipeline also。So we had to wait。

Even though we have the result that we want to start by this moment。

 but we cannot immediately store it， we need to wait until this time such that we can start the story so any idea why we cannot do that yes。

Same port， yes， because we partly our assumption， so we assume that our memory is single portrait。

So we have only one port going to use that port for reading and writing data so that's our strict assumption that each memory bank has a single port。

 which is our memory band with Bona here， so if we do chaining and also consider that we have two load ports and one store port in each bank then you can actually pipeline your first two loads and then you can also start the store operation immediately after you have the data so with that you get to 79 cycles which equivalentvalence to 19 times performance improvement compared to the scalar code that we had before。

Which is not that bad。Gian。Okay。So now I'm going to discuss about some of these issues。

Like what if number of data elements is greater than number of elements in vector register？

So our idea is to break loops so that each iteration operates a number of elements in a vector register。

So as an example， we can have considered 527 data elements and our vector register is 64 element。

 then we need to do8 iteration where vector length is 64。😊。

And for the last iteration you need to change vector lengths to 15 such that you finish the whole execution so that's how we are doing that and once you want to change the vector length actually that comes at the price of some overhead you need to basically is going to comes at the price of some stalls in your pipeline if you if you will this actually a technique called the vector stream mining which actually coming from。

Mining terminology。That sometimes so when you want to get the gold。

You need to get rid of soil and rock overlaying the mineral deposit。

 which is your your goal is actually iterations that you have full vector lengths。

And these are your soil and stones that they are not very great。😊。

So people were creative in making coming up with this terminalology with this naming， essentially。

So another question， what if vector data is not stored in a strideed fashion in memory。

 which we call it irgular memory access to vector？😊。

So then you need to use indirect to combine and pack elements into vector registers。

 which we call it scatter and gather operations I'm going to show with some example here。

So this look at this code， we have this for loop and then in each tradition we want to do this addition element of vector B and then element of vector C。

 but the address of vector C is calculated by another vector。

 so now you have these indirect memory accesses。So first the question it would be is this code vectorizable。

 the answer is yes， because every iteration is actually independent from each other。

 but the problem is that your access is not very regular。😊，So in order to run this code。

 you need to do index load instruction to gather data elements that you want to operate on in your vector register。

 so how we are doing that。We basically load inds in the D vector， so this is the D vector。

 so we need to load it in the。To register D and then we need to load indirect from basically register C。

 which is your vector C So with that we load vector but indirectly using the base。

And also the index that we have read， so R C is the base。

And VD is your basically index of your data and with that you can get your basically data that you wanted。

 you're gathering data from vector C to your vector register。

 and after that you can load vector B and then do addition and then your store。So essentially。

 the process of gathering data from different location in your memory to your vector register is actually called Gaer。

And which is very useful for operating on sparse vectors or mattresses， so in your matrix。

 you might have many， many zeros。😊，And which is the case usually also in a machine learning application。

 so you don't want to operate on zeros， you just want to operate on non-zero operation。

 so there should be a way to gather data from your matrixes that they are non-zero and pack them in an array in your vector register and then operate on it。

 and once you have the result you might also want to write these basically values in your memory but not necessarily consly。

 which we it as a scattered operation。So here is an example for a scatter。

 so you have index vector0267， and you have your data vector。

 so here mean that assuming you have a base address。This value 3。14 should be stored in base plus0。

 so you store it in this location， the second one which is 6。5 you need to store it in base plus2。

The third one in base plus6 and the first one in base plus7。

And that's how you scatter your store into your memory and other location you basically don't touch。

So that's about how we do gathering and scattering。Any question？は。Thanks。

It me also quickly also go over a conditional operation， which I already actually covered it。

So what if some operation should not be executed on vector based on dynamically determined condition。

 so here is four and based on this if operation you want to do something so our idea is to use mass operation using vector mask。

 which we already also discussed about it。So if you load these to vectors A and B。

 and then you calculate your V maskask， so Vmask is actually has a default value which is considered for all of these instructions but once you want to change it。

 you need to have the instruction to change your vector mass and the rest of instructions is actually operating on vector mass based on vector mass and once we are done。

 we need to initialize back vector mask again。So here our basically if is that if AI does not equal to zero。

 then we do this multiplication， so we calculate vmask which is vmask v0。

 not equal0 and for those elements that basically these condition is made we do multiplication and also we do a store and for the rest of elements we basically do not touch anything。

And as I said， this is called predicated execution。

 which has been used a lot and actually introduced first for Cdi architectures。

 but later on people also use it for other architectures as well。😊。

Here is also another example that you can compare A and B to get your mask。

And then you do this mask sort of A into C。And then you complement your rem。

 and then your mask is sort of B into C。So you can actually do a lot of tricks using your V mask in order to implement these operations。

So now the question is that how we can implement mass vector instructions。😊。

So one way is that we basically execute all N operations。

But we just turn off results right back according to the mask。

 So you are doing operation for all these elements。 But， when you want to write back。

 you check the mask value。 And if it's0， basically， you don't write it。So of course。

 it can comes at the price of basically a lot of unnecessary execution。

Let me finish this and we will conclude。But another way would be density density time implementation that US scan mask vector and only execute elements with non zero mask。

So basically first check your mass operation and then you fetch those data elements that you want to operate on your vector register。

 and then basically you do the computation。Now you're doing computation only for those elements that you really want to do computation。

 So of course now the question is that which one is better。😊，And the answer again is it depends。

Because this simple implementation is simpler， of course， so if your mask is mostly actually v。

 but there are also some zero so there you might prefer to use this one right but if your mask register is mostly zero and there are only a few ones then you might prefer to use this kind of implementation。

😊，Because you're not wasting a lot of execution of doing unnecessary execution。

So I think I will stop here and we will basically continue next week about some other issues about this Cdy architecture and then we start about GPU architectures。

 so have a nice weekend and see you all next week。看。Yeah。



![](img/ca9d27128950c72627cdfa3aab4be15b_12.png)