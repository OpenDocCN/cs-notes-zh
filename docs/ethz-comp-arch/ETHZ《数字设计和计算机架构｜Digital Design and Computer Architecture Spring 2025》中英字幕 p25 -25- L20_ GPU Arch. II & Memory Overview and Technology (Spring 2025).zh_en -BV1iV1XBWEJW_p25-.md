# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p25 -25- L20_ GPU Arch. II & Memory Overview and Technology (Spring 2025).zh_en -BV1iV1XBWEJW_p25-

![](img/244e499aeadcbdb776d009928a3d53ca_0.png)

No， yes to。Even in theater than yesterday yesterday comparative。你喺那边咁嗱。😊，他什么没。Yeah。家。Yeah。这是明er。你。啊。

그。Please。嗯。Is it good。Okay。Yeah。All right。新的。看。Oh。🎼。对啊。这是。Okay， let's get started as usual。

 we have fewer people on Friday。They're the most dedicated folks。Okay。

 so today I plan to finish GPU architectures， we started yesterday。😊，And we finished most of it。

 and before that we covered Cdy array and vector processors。We'll finish that。

 and then we'll move to memory。 So the remaining。I think five plus one， six lectures。

 five and a half lectures are going to be on memory if we had a 2026 lecture which we don't this semester that would also be on memory。

And I will motivate why we were going to study memory because it's really the most important bottlealtneck today。

Okay， but before we get ahead of ourselves， let's do the GPU architecture as part and this is an important part because。

呃。For people who really care about the exam， some of you might。

We have actually questions on GPUs on the exam， and I like a particular style of question which I will show here。

 which you will have on your exercise also。😊，Okay so GPUs are graphics processinging units initially they were designed for graphics。

 there were a lot of GPU graphics libraries that were created in the 19 even early as early as 1980s and the 1990s and then people started saying oh there is this graphics processor that I have in my system can I do something with it can I do some computation with it so they started tweaking the graphics libraries they started actually trying to accelerate programs and they figured out how to use the GPUs to accelerate things。

😊，That are more massively parallel that are similar to that basically fit this sort of programming model that we discussed yesterday as PMd and over time this movement。

 let's say kind of gu and grewru and people said， okay we can use GPUus for general purpose programs there were papers written there were people actually demonstrating that you can actually do a lot of scientific computation on GPUus that exist on in your laptop or in your desktop and over time people said basically oh we could use this hardware to be more general purpose and over time also at the same time GPU vendors figured out that oh。

 we can actually make this more general purpose because people are using our hardware for general purpose stuff。

 not just graphics right So over time GPU hardware became more and more parallel as well and less and less specialized in the sense that there are clearly graphics oriented things that we didn't talk about inside the GPUus for textures etc there are specialized course special functional units for graphics computations those。

😊，Not being used as much， but the general purpose core that we've been discussing have become used by a lot of people and GPU vendors also started making those more general purpose easier to program etcter。

 And as a result GPUus became very popular and as we discussed in an earlier lecture some folks started using GPUs for machine learning training at some point and also inference and they figured out that these are very capable and that enabled deep neural networks to be actually quite sustainable today with general purpose hardware。

 And that's what really enabled GPUus to take off over time。

 So you can see this an example of a specialized more or less specialized hardware that is available for accelerating graphics over time being adopted to become more general purpose And today it's quite general purpose actually GPs are quite general purpose as long as you can write programs nicely using this SPMD model So that gives me a nice segue into what we discussed yesterday as we discussed。

😊，be a programming model and execution model and GPUs are programmed using SPMD programming model。

 single procedure or program multiple data， and essentially I gave you the example of， for example。

 counting the characters in a book right I'm not going to give you the same example。

 but that's a very good example， you divide the program into many threads and each thread counts 10 pages and each thread actually does essentially the same thing it executes the same program on different pages right。

So basically multiple instruction streams， threads that execute the same program。

 but they work on different data and they can execute a different control flow path at runtime。

 so we're going to see that different control flow path yesterday I gave the example that maybe one thread has only A's right only character As character A in 10 pages which is a rear page of course。

 but another thread may have actually all types of characters in 10 pages so these are clearly update different locations in the histograms that they're updating and as a result they take different paths right。

😊，Okay， and as we discussed， many scientific applications are programmed using this SPMD model。

 and usually especially in the past， people used multiprocess， multiple processors， MIMD hardware。

 multiple instruction， multiple data for accelerating large scale scientific applications。😊。

So you can actually have as many， many core， many， many general purpose processors。😡。

Executing the same thread at the same time。 GPUs make it much better in the sense that if threads are doing exactly the same thing。

 why decode the same instruction many times right if you're using multiprocessors。

 they're executing the same threads theyre all each of them is decoding the same instruction scalar threads each of them is decoding the same instruction many。

 many times the number of threads times essentially whereas as GPUs， as we discussed。

 it's programmed on Sd hardware， it's an SPMD programming model And if threads are at the same program counter。

 you take that instruction， decoded only once fetch it only once。

 execute only once and perform the operation on many different data that is specified by the different threads So that's the benefit of the C hardware to execute the SPMD model。

Okay we also distinguished yesterday between SD and Sti a little bit basically if you have SD each instruction is a vector instruction。

 we got rid of that with the ST model you have multiple instructions themes of scalar instructions now in GPUs essentially this is a scalar set of instructions if you remember the code we went over yesterday it had four instructions and then you specified number of threads you don't need to deal with vector length of hardware。

😊，And we discussed yesterday that you can actually treat each thread separately。

 meaning you can do MID processing and you can do fine grain multithreading of wars。

 so if you remember that we discussed that yesterday I'm not going to discuss it again。

 but today I'm going to show you some things that you can do if you have this sort of execution model meaning if you have different scalar threads and you have the capability of grouping threads that are at the same program counter together into a warp。

😊，So that you can actually improve your utilization in the hardware。So let's take look at an example。

 let's take a let's assume that this is our threat。

 we see some blocks over here that need to be executed and you can see that clearly there's some conditional control flow。

 meaning sometimes after A you go to B， sometimes you go to F depending on how the branch calculates。

 let's say。😊，And here when you execute the threads can execute different control flow paths。

 for example， thread one starts from the same program counter。

 all threads start from the same program counter， which is the beginning of this block A。

 there may be multiple instructions in a， but the block ends with a branch， as you can see。

 there' is a control flow graph as we have seen in the past。😊。

That two may take a slightly different path， mostly they're taking the same path T one and thread two。

 but at some point they diverge as you can see， which is after B T3 takes the same path as threat two as you can see so that's good T four takes a mostly different path as you can see it goes through AFG。

😊，Now assume that at the beginning they are a part of the same warp because they're at the same program counter。

 how would you execute something like this on GPU hardware， GPUs that can actually execute this。

 except they're not extremely efficient， they're going to depending on which PC a threat is in。😡。



![](img/244e499aeadcbdb776d009928a3d53ca_2.png)