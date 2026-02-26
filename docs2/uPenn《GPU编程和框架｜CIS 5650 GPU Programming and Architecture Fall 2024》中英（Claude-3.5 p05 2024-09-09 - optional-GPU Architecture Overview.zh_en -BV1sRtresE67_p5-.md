# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p05 2024-09-09 - optional-GPU Architecture Overview.zh_en -BV1sRtresE67_p5-

![](img/aa62caa0e4818d45a2e236d0a73eeaed_0.png)

Hi everyone welcome to the class today unfortunately i'm not able to be there in person because I've had some emergency travel come up so what I'm going to do is I'm going to record this lecture and we'll watch it in the class you know the teas will hosters。

The kind of the happy mistake here is that this lecture makes for a really good recording because it's very theoretical we don't necessarily discuss Quda and stuff in this lecture。

 what we're going to be doing is looking at the history of how CPU architecture worked and how that has influenced how GPUs work and we're kind of going to build our own CIS 565 GPU in this lecture。

So let's take a look at how all of it plays together。



![](img/aa62caa0e4818d45a2e236d0a73eeaed_2.png)

Starting off with a couple of aments。

![](img/aa62caa0e4818d45a2e236d0a73eeaed_4.png)

And then， so。This wall of GPU history that was done at Microsoft I came across this。

 I believe on either Twitter or LinkedIn and it really showed how graphic standards have evolved to the left is everything in the 90s and what's in focus closest to the closest to the camera is GPUs in 2008 and you can see the 8400 Gs from Android are kind of highlighted there。

And that's really where Kuda started that was one of the first coa GPUs and of course we've seen evolutionvolution since about how GPUs have grown so gives you a sense of。

GPUs are not just modern technology， they've come a very。

 very long way and have been inspired from many generations of architecture and redesign。

So a couple of things to look at first， so GPs and CPUs the performance。

 the compute performance at least is measured in what is known as flops。

 floating point operations per second。So this is。Essentially what you're measuring as。As。

The amount of multiplication and addition operations that you can do in the GPU。So。

So this is calculated using how many gigab flops that teraf flops we have at least today back in the day would have been megaflps before that probably we just flops or kiloofflps so modern day GPUs certainly operate in the Terafflop range supercomputers operate in the petflps if not the Xflps so one of Intel's big goals is to make an extraop extraflop supercomputer so that's essentially10 to the power 18 gigap flops per second。

 which is absolutely incredible that would be like the amount of compute power at our fingertips would be incredible。

So let's take a look at some modern hardware and how many teleflps they have so the slides are a couple of years older so you you may not see the most modern Intel N Vdia AMD hardware but it's still representative of how much of what the trends are essentially so an AMD rise in 9 3900 x was one and halfterafflps and Intel line9 199 100k which was top of the line CPU about two generations ago was 1。

22 teleflps。And then a GPU。Again， a couple of years old， and Rxtp was 16。

3 to tariffaf that's almost 12 times10 to 12 times about what the intel and emD CPUs are producing Again。

 remember that this is in terms of compute for performance if you take the。

Take the standard work that CPUs do in terms of running the operating system and stuff you're not going to be able to get that same performance。

 but if you do algorithms that are reallyly driven for parallel computing。

 then you're going to be able to maximize all the gigabs post on the CPU and the GPU。

 but you're going to see a bigger gain on the GPU。Similarly。

 this kind of scaling is happening on system Mon chip hardware as well， so whether it's the TeGRA。

 the Jetsons or the Drive VX that NVD is building， we are seeing the same kind of scaling happening where GPUs are able to provide a lot more compute performance。

While I don't have it in these slides， I'm pretty sure that's the same with Apple's arm architectures where they have the CPU and the GP on the same chip。

You're going to see the same numbers out in the same trends on there too。

So if you look at the way these trends are happening。

 you can see that there's been an explosion since around 2008。

 2011 when GPUs really started taking off compared to the CPU you can see how single precision and double precision performance for Intel CPUs are in the blue and then with NRdia GPUs it's just keeping rising up of because the data here probably ends around 2016。

 but even then the trends have certainly continued to expand there。

And on the theoretical bandwidth side you can still see how the bandwidth rate is increasing as well with CPUs we are seeing DDR4 DDR 5 kind of memories coming into play on the CPUU side but GPUs are already on DDR5 DDR 5 high bandwidth you know stacking multiple memory vertically and all of those things are giving GPUs really high bandwidth as well and with PCIE expanding so PCIE4 is kind of standard now PCIE5 we'll probably see in the next year or two and PCIE6 is essentially getting standardized as we speak so those are essentially with each generation are doubling the amount of bandwidth you get from copying data from CPUU to the GPU so what that means is if you had PCIE3 bus between the CPU and the GP。

いう？That would have given you somewhere around 16 gigabytes per second of overall bandwidth to copy your CPU data to the GPU。

Whereas with PCE4， you essentially double that bandwidth， so now you can copy CPU to GPU faster。

Which means the overhead of using GPUs for improving your compute is becoming lower and lower every day。

So flops is。Great but we also have to put it into context one of the main things that we have to think about is power and heat limits we can especially in today's world we have to be conscious of how much energy we are using in terms of the hardware we run and what algorithms we are running on that hardware。

Single core performance if you measure it has kind of been while the number is increasing it's kind of been slowing down given how power and heat limits are changing。

 you have an ultra ultra thin laptop that needss heat dissipation you're probably getting a slower clock rate on your CPUU so just examples like that and then GPUs also we are starting to see how the die size or how big your chips are how much power they use what it costs especially over the last couple of years has really changed the dynamic of what the cost benefit analysis of GPU performance also is。

The other thing to think about is how this works in mobile。

When you have a mobile phone and a battery installed。

 that's when performance for what becomes really important。

 where optimizing it for saving battery and doing proper compute and using it efficiently becomes really。

 really important。对。So let's take a look at what are the major components of a CPU more in theoretical terms。

 but essentially understanding how a CPU is divided。

 what are the considerations that go into making a CPU。

 and this kind of gets into computer architecture class。

 but we try to keep it brief and at a high level， but essentially all leading into how GPUs are developed。

So in a lightly threaded desktop application， you know some of the most common ones are VIM。

 which is my favorite editor， LS is essentially the list of files commands in on Linux。

What you're going to see is a lot of these commands and operations are likely ted they likely have a lot of branches and they access a lot of memory。

 so these are some numbers that were run by one sample back in the day about how how much memory access how many branches and how much actual compute these kind of commands are doing so if you look at this vector instructions which is kind of the instructions that GPUs are really good at is 1% or less than1% of the overall compute。

And that's really interesting because what that says is。

The job of running a command on the CPU is not necessarily always about。The highest performance。

 it's also about how do you manage all the branching。

 memory access and other things that you have to do。

So a simple CPU core probably at its fundamental looks something like this。

You have five stages which are fetch Decode， execute memory at write back for anybody who's done computer architecture this probably looks very familiar to you and what happens is all of these steps occur in one clock period so once the clock updates you're going to get all of these instructions happening at once。

So just to go a quick overview of what each of these means。

 fetch is fetching the next instruction that is to be executed。

 so this can be an ad a multiply a read operation a write operation， so those are all fetches。

Decode is taking the assembly and decoding it into an actual instruction that the hardware can understand。

Executed is actually executing that instruction memory is writing that result into a register。

And then right back is anything that needs to go back and then to the program counter for the next itration。

Essentially what this simple architecture shows is really bad utilization where you have all of this running for one command in one clock cycle。

Until this entire thing finishes for one command， you cannot update the clock cycle so it gives really bad clock utilization essentially。

So one of the solutions to this。It's kind of breaking this apart where。

You break the pipeline into different segments， so you have a memory segment， a register file。

 an AL use segment， a data and memory segment and a register file segment and what this allows you to do is have instruction devil parallelism so each part of this pipeline can be executing a different instruction at a different pro cycle so if something is in the dataman site circle。

There can be another instruction that's in the ALU part and another instruction that's in a rech file part。

 so this essentially gives you pipelining where as soon as one instruction is done everything moves to the next step。

So what this provides is essentially an instruction level parallelism that improves significantly improves the clock speed。

It reduces。It reduceuces how much time。Any instructions waiting so at all times you know you can have multiple instructions running at once it does however increase latency so sometimes if instructions are taking too long to execute something's going to be waiting you know before it can get executed。

It also increases the number of transistors and gates you need。

 and it also increases your chip size because now you have different control structures in place and now you need to dedicate transistors to those control structures。

The other thing that this can cause is an issue with dependent instructions so what happens if an instruction that's getting executed depends on an instruction that may happen before or may have happened a lot earlier how do you take care of that that's one thing the other thing is branches。

While it's all good that we can execute multiple instructions in line。

 what is the next instruction depends on an if condition where you have to pick which branch you want to execute so that makes a lot of difference here。

So to give you some sense of how many stages there are， Intel Co2 CPU had 14 stages back in the day。

 so I'm talking a long time ago， a pentium 4 had 20 stages。

And modern architectures probably have somewhere in between that。

So essentially this kind of pipelining， and I'm showing you a very simple version of it here is what allows for very。

 very high clock cycles these days。😊，嗯。So now if you take a look at branches and how they might execute。

 we don't know what instructions will execute after the branch until the branch is executed so you don't know which instruction is next until you actually hit the FN part or if equals part so J equals is kind of that equal checking on the loop so we could。

We could either stall it and not execute any instructions until that branch is executed。

Or we can speculate and try to decide which one is。Likely to exclude。

And then if something fails then we just throw all of that information away and start again so a very common way of thinking about this is if you have a for loop that's going from zero to00 okay？

1undd times the branch prediction is going to go one way where it's going to be like， okay。

 continue follow loop， continue follow loop， increment， continue follow loop， right？

But on the10th iteration， it's going to fail， but to if we are trying to optimize our performance on on a CPU。

 it's better to。Tdict correctly 100 times and fail once then it is to wait install every single time for 100 times so that's kind of what we get here because of branch prediction。

So modern day CPUs are actually very， very good at this most of the time you get 90% accuracy this is held by both compilers and hardware level logic this improves performance as well as energy efficiency。

How the downside is that now the chips are bigger you're dedicating more and more transistors into being better hardware branch predictors。

 so now the efficiency of compute per transistor is probably decreased。

It also probably increases the F stage latency because now you're in different branch predictors and you're trying to do different things。

嗯。AndThen lastly is security concerns， a few of you may have been either probably in your freshman year or a little before that。

When Specttor and Melan were the talk of the town about how at a very core hardware level。

 these issues existed where they could provide hackers the ability to get in by reading memory that they shouldn't have access to and how that happened is essentially because of branch prediction where at the hardware level。

 the chips were executing instructions that were kind of in the future。

 that is they were executing instructions based on branch prediction。

Assuming that they would just throw away the results later on。

But what that allowed potential hackers or security loopholes is。

You could write a branch prediction that went one way all the time。

And then when the CPU trusted it enough， then you tried to access bad memory through it。

 So of course I'm doing a very bad job of explaining the the core part of the security。

 I'm not necessarily a security person， but essentially that's what LED to the hardware level issues and weren't fixed by any operating system intellectually had to build。

It into the new chip so that you know these kind of issues didn't happen in the future。Yeah。

So looking at。Looking at memory hierarchies， so some of this we've discussed in the class from a Qa perspective。

 but let's look at it from the CPU perspective as well essentially the philosophy is as the memory gets larger it also gets slower。

So in rough numbers， if you had SRAM， which is our L1L2 L3 cache on the CPU。

You're going to have very， very fast bandwidth because it's literally located near the CPU。

 but you're going to get very， very small size， even even more than day CPUs have somewhere between 1 to 20 megabytes of L1L to L3 cash。

Now from there， if you go into DRAM， which is your regular 16 GB 32 GB memory that you have in your laptop。

 that's going to be somewhere between 15 to 40 depending on whether you have DDR 3， DDR 4， etc。

 so you get more memory about almost  a thousand times more memory。

But you're also reducing how fast you can access it。And then from there。

 if you keep increasing a flash or a solid state drive。

 even NVM is slightly faster but not reflected here。

 you're going to get significantly more sizes where it's。

 you know anywhere from 256 gb these days to  four terabytes。

And your speed is probably going to be in the hundreds of megabytes if you're on a regular SSD and if you have an NVME that's running over PCI。

 then you're probably getting into the one terabyte or sorry one gigabyte or up to four gigabytes per second。

And finally， if you're on a traditional spinning hard disk which are still very very much used these days you're going to get you know somewhere in the low 100 megabytes per second read and write speed so essentially the larger you get the more time you're spending on actually trying to find where the memory exists's that's where the latency happens it's not in actually reading the memory but it's in the memory bus about how the actual physical architecture how fast can it read the memory and it's also in finding where the memory exists so if you're building up a cache and stuff you're going to access it faster if you don't have that cache you actually need to physically spin this in the case of hard disk it's going to be a lot slower。

So in the case of caching what we are essentially doing is keeping the most important data as close as we need so so that the the most frequently accessed data is is the fastest to get so what we are essentially doing is exploiting temporal locality which is。

If if your data is likely to be used again， so for example， again。

 if we go back to the fall loop example， if you're doing the same operations over and over。

 it's best to catch that those results。And then you're also doing spatial locality again using that follow loop example if you're trying to add two arrays。

😊，The CPU and the compiler can predict that after index I the next ittration is going to access I+1 and the next itration is going to access I+2 and so on。

 so what it can do is predictably it can fetch all of that continuous memory into a cache and store it so now you don't have to copy it each time into the cache。

So taking a look at the cache hierarchy， what you're going to see is something like this where L1 is the actual instruction and taking the cache。

 so in QDa this would essentially be the same as registers。

 L2 would be unified cash and L3 would be slightly bigger unified cash but probably distributed across the course。

And then away from the chip itself， you get main memory and of course， hard disk drives。

So let's take a look at what some CPU architectures actually look like so this is an actual image of an internal CPU conceptually now you can probably identify some parts and others。

 but let's see what it actually breaks up into if you have any predictions put that in your mind so that when I go to the next screen short let's compare about how it comes out。

So this is how the chip actually breaks up， you have this huge L3 cashier and that's where。😊。

That's where you know how CPUs and GPUs are different。

 you have about six to eight cores here depending on how many they're going to enable。

And then you have a lot of Io controllers and memory controllers along with them。

So what I want to really highlight here is the ratio of the transistors that are dedicated to compute。

 which is the core parts。And the amount of transistors dedicated to memory and memory controllers。

So it's a huge percentage， so only about 25% of the die is just in the L3 cash。

And once we go a little further， I'm going to show you how it looks on GPUs。

So this is on a more modern CPU that's a I9 19900 again。

 we are going to see something very similar here。Where you have a lot of this dedicated to CPU cores and a lot of it in the M3 caches and then you have some transistors dedicated to GPU and media。

 the reason it's written GP and media because a lot of the transistors here are also dedicated to things like video decoding and video editing and those kind of things so those are built on a hardware as well。

So now let's see how we can go about improving the pipeline that we had。

So we spoke about how you can have。You can add different stages to the pipeline so that you can exploit instruction level parallelyism。

But there's another type of parallel that we can extract。

 which is Scalar or superscalealar in the way where you're not just doing the same pipeline。

 but you're kind of making two pipelines that derive from the same instruction register so now if you have one pipeline that's running in the top half you can have another one running in the bottom half so this way you're increasing the pipeline width essentially。

So this can get into something like scheduling and reordering so let's take this example okay we have full registerants here or full instructions sorry exc add subtract and add increment。

Notice that。Addd is dependent on XR， so it's called read after write so essentially the XR always needs to happen before the add before the add here。

 so XR r1 plus r2 you give you get r3 and then the result of R3 is used in the add。

Subtraction and and I are dependent so they are read after write again。

 so subtraction r5 minus r2 you get r3 and then r3 is red here。And finally， XR and sub。

 so this XR and this sub。Are not dependent at all， but theyre right after right。

 so depending on what order you do them in you could potentially be getting into race conditions but they are not necessarily dependent on each other。

So let's see how we can optimize this。So how might we change this so that we are using a few more registers？

So it consider this so XR P1 and P2 goes into p6 and p6 is still used in the add and you get p6 p4 into P7 so XR and add are still dependent。

But for subRA we change it， we do p5 and P2 again same as before。

 but we now write it into P8 instead of writing into the same register as the XR result。

 we write it into a new register。And then that register gets used in addI so you can have P81 into P9。

 so now what we are essentially doing is XR and sub can execute in parallel and then add and add I can execute in parallel so the first two instructions and the second two instructions are completely independent of each other。

So that's essentially what is called out of order execution where you're giving the CPU and the compiler permission to。

Reorder the instructions based on the order that you're providing so that's why it's always important even in QUDa to have memory operations and computer operations kind of next to each other so that the GPU can optimize them if needed。

So。ThisThis workflow is kind of the way that reordering happens and there's a reorder buffer to keep track of status of the infed instructions because we can't just freehand modify things as we want。

 we actually have to keep track of the results and which instructions I've executed and which have not。

So that also drives into having an actual issue queue and a scheduler which choose the next instruction。

 so it needs to have some smarts about how it predicts which operations are dependent and independent and picking the next schedule next instruction to put on the schedule。

So on the CPU now getting into going from CPU from one pipeline into actually parallelzing the CPU。

 we've covered instruction level parallelism where you can have superscaler and out of order and then you can have data level parallelism so that's vectors and we'll get to that on the next slide and finally we'll have T level parallelism so we'll have simultaneous multitraing which we are all very used to in modern modern day CPUs and we also get multico that's essentially what Intel and AMD have thrived on more recently。

So let's take a look at better。So if you take a look at this for loop。

 what we see is this is going from int I equals0 i list than n i++ right。

 and it's doing the same operation and over and over。If you imagine this in an assembly language。

 what you're going to see is something like execute the for loop。Or I execute the assignment。

 execute the condition。Execute the statement， execute the increment， execute the condition。

Then you execute the statement again。Then increment， then condition and then the statement again。

 so these these three steps kind of keep repeating each other。

But what if you were able to take advantage of something that we've spoken about in GPU land essentially and that's Cindy so single instruction multiple data so what if you changed your follow be something like this where you implementcrement by four。

But you add more instructions explicitly， so now you know that this n is not in maybe a multiple four or four or you're not going to have invalid memory accesses。

 so now you can explicitly write these instructions as shown in red so that you're doing more compute and less condition checking so now it can execute faster without the overhead of that increment and checks for every single fall loop pration。

So that essentially allows us to have more ALU computation and also needs more memory。

 but eventually makes our performance faster。So some examples of vector instruction in modern architectures are SSE2 where you have four white packed floats and packed in P instructions。

 so these are essentially things like operating on V4s and vector3s that can be really optimized because you're not doing it as a vector operation。

AVX is the modern version of SSE tube， so now you can do eight white packed floats and integer instructions and that's in the more modern inand AMD hardware。

So that's about vector instructions where you are essentially taking。The same instruction。

 but multiple data and executing it within the same clock cycle。

And then we have thread level parallel where you can have in your program。

 you can define multiple threads and what they should do and this is more on the software level so it's more controlled by the developers and the programmers who are writing the code so we have to manage about how which instructions to execute what the algorithms are and stuff like that。

And then on simultaneous multi threading， these instructions can be issued from multiple threads and they require partitioning of the Riorder buffer。

 so you have different parts of the Riorder buffer working on different threads and what they allow you to do is not necessarily duplicate the hardware。

But they take up more cash and execution resources because now they have to track different things from different threads simultaneously。

 so while it reduces single side of performance， it can really improve much side of performance because of that additional hardware that's there to optimize it。

And finally on multicore what we are seeing is especially since AN these threadrapper CPUs came out。

 there's a huge increase in the number of cores that the hardware companies are putting into the CPUs。

 so for example in latest architecture they come with that big little architecture where they have。

 let's say four to six efficient CPUs so these are CPUs that are going to run under low performance loads but be really amazing with battery life。

 so essentially performance for what is really really good。

And then you have four to six bit cores where the performance is really good。

 but you don't care as much about how much power you're consuming。

 so for example in gaming workloads or high performance computing workloads。

 it's going to take the same thing that you are doing it's going to realize quickly all my program needs to run on the higher performance CPUs。

 so it's going to take that move it from the efficient course onto the high performance course and that's going to use a more battery life。

 but you'll get your results faster as well。So in these course。

 what you're essentially getting is full course you know duplicating the hardware essentially and no resource sharing other than the L3 cache at most points。

 it's easier to take advantage of that and moves up because you can essentially kind of copy paste each core any number of times on the chip as long as you can control the chip size。

What you decrease or don't get so much off is the utilization because you have all of this independent course now they can't always talk to each other in the most efficient way。

 so you get a little bit less utilization。So concluding the CPU part you so CPUs are essentially optimized for sequential programming and of course a little bit for multi threadreaded programming。

 but they're essentially programmed for multi threaded versions of sequential programming where you have pipelines。

 branch predictions， superscale are out of order execution， you know lots of。

Human controlled work essentially。And。To reduce that execution time。

 we are increasing the clock speed and trying to increase the utilization memory is always a problem because you're going to have different levels of cache and different levels of memory。

 but always that bus weight and the speed is going to be a limitation to how much parallel and compute we can extract from that。

😊，So for modern day architectures， modern day CPUs。

 you're going to get anywhere from four to 12 to 16。

 maybe 32 threads on the highest end architectures。But how do you get to 32，000 thread or 64。

000 thread that modern day GPs are able to execute？So let's take a look at that。So essentially。

 going back to this chart from before， we are asking how did this happen？

How are we going from in 2005 and 2007， GPs and CDs being relatively close to each other in terms of performance to this huge gap that we see today？

So let's take a look at what kind of workloads GPs handle， you know。

 both in terms of algorithms and the use cases to make this kind of scaling possible。

So the first and very common use case is， of course， rendering of triangles and pixels。Very。

 very pad you have millions of triangles and you're generally applying the same operation to them the same world coordinate transformations。

 the same normal maps and other things so again single instruction multiple data really applies for pixels and fragments you know rendering things on the screen again if you have you know your rationalization algorithm is going to be very similar for all the pixels if you're applying different filters different shaders that's going to have you know again that the the single instructions but you're applying them to many。

 many， many pixels at the same time so very very parallel workloads。

So let's take a look at how GPUs have essentially evolved in rendering triangles and vertices since the early days of gaming。



![](img/aa62caa0e4818d45a2e236d0a73eeaed_6.png)

So one of the first and biggest computer games so it our first 13 3D and then do one bought by its software。

This was all CPU all software rent there was nothing like a GPU back then it was all you know very very primitive CPUs and using software record to make sure that we are able to render the same the right things at the right time so for Wolf 3D it's all a 2。

5 d gain there's no actual 3D here there's no ceiling or flow if you notice it's all great。

There's no height changes， it's all on the same floor， there's no rolling walls， there's no lighting。

 it's all flattding and the other thing you notice which you may or may not have until today is the enemies。

 the agents that you kill。or always facing you they're never facing away from you so that's why things like ray casting and precomp text coordinates work in the skin。

Of course with doom one now you had this built on the PSP3 by Rose Naer。

 you have texture maps on all the surfaces so including the floor and the ceiling you have lighting so you can see how the light from the top is it's showing on the floor you have different floors so you can go up and down you have rolling walls so you can see even within the span of a year of how how the game evolved and if you want to read more about its software and how the early days of gaming really evolved and how they came up with these algorithms I recommend you read the book called Masters of Doom it's an amazing book especially if you love gaming you get a lot of history of its software and other games and I definitely recommend it。



![](img/aa62caa0e4818d45a2e236d0a73eeaed_8.png)

So。So why GPU so we are definitely seeing the workloads that are abasingly parallel right both in terms of data parallelism as well as pipeline parallelism and then also CPUs and GPs being different chips and being asynchronous to each other。

 they can also execute in parallel。However， not everything is improved by making GPUs software programmable。

 so when we are programming Qar core， they are essentially software programmable cores where you can write code to execute on them。

There is still space on our chips for hardware level fixed function hardware essentially as it's called。

 so these are for texture filtering， therefore aization where you can change the states and change the different parameters that are fed into these algorithms。

 but you can't necessarily program the algorithm， you can't program the fixed function units of these fixed function hardware essentially。

So that's why you're still going to have some compute that's fixed function and has dedicated transistors that are not programmable。

 but they provide significant performance improvements without necessarily giving access to the whole algorithm to the user。



![](img/aa62caa0e4818d45a2e236d0a73eeaed_10.png)

And then beyond graphics you get you know a lot of different things we can do we've already looked at matrix multiplied the first classes。

 you can do cloudt simulation head simulation， particle systems。

 nowadays you can do machine learning and computer vision and other thing so。😊。

GPUs are used for a lot more than just graphics and simulation。



![](img/aa62caa0e4818d45a2e236d0a73eeaed_12.png)

So。Let's start now building what I call the CIS 565 GPU and in reality it's theBeyond program and dual Shading course GPU from SigGft 2011。

 but let's say we are building the  p65 GPU inspired by that。

So here's a very simple shader those of you who've done Cs 460。

461 should be very familiar with this the specific。😊，Code that's here is not very important。

 What I want to share is that this code。Applies to millions of pixels at the same time。

 so if you let's say you have a  fourK screen that is 38 40 by by 2160 you get probably about 8 million pixels somewhere around that so these same operations literally these four lines of code are being applied to 8 million pixels at the same time。

 so now you can see how this kind of become similar to a kernel that we write in QudDa where you have let's say your matrix and you're doing the same operations for the entire matrix。

So let's see how this works。The first thing we have to do is take the shader and compile it it to assembly language something that the GPU can understand and the input to that is going to be one unshaded fragment or a pixel and then the output is going to be after applying all the operations you're going to get a shaded fragment you know it's going to be colored or it's going to have transparency and other things but essentially that's the function where you have one pixel you run the shader and you get one pixel out。

And to execute this， what you're going to have is this kind of very simple ALU fetchDcode and execution context。

 so the fetchHD code essentially gets the instruction the ALU executes it and the execution context stores all the memory。

So we can go through the different lines and stuff， so line by line it's going to execute that。

So if you take a look at the CPU before the multi Correra。

 so essentially in the generation of single cores。What you had was this， you know， you had the FedD。

 you had a small ALU unit， you had some execution contact。

 and you had a huge data cache and we've seen L1 L23 because not all of them existed back then。

 maybe you had L1 and L2 but they were still very， very large。Compared to how much compute you had。

 how much A you had so the and then you had， you know， the out of all the logic。

 the fancy branch predictor， the memory three fetch so that you're able to do。

All the optimizations around a single instruction rather than parallellyze multiple instruction at the same time。

So keep this in mind， I want you to keep this this kind of。呃，是。

This kind of a high level diagram about what a single core pre multichora CPU kind of looked like and how the components were essentially divided。

So let's take this and let's start working on it because this is essentially what they had in the 90s right and we want to take what they had in the 90s and build a GPU out of it so let's take this and change a few ideas here。

So the first idea is that we want to increase transistor count。You know。

 make the make the chip essentially bigger so that we can add more。

Course to it so rather than using transistors to increase the branch predictors and the out of order execution。

 let's add more more earlier units， essentially。So that's the first idea and this is essentially within a core so if you get two cores。

 this is what it looks like you have the F A and execution context but you have two of those now so you can produce two fragments at parallel。

Why stop at two let's go to four you let's say now you can produce four four pixelxels in parallel again。

 no need to stop there let's go to 16 now now you see how。Having。

A lot of ALUs with execution context and their own instruction fetch decode is essentially going to help produce multiple fragments at parel。

But。😡，Many fragments should be able to share the same instructions to you， so if I go back here。

 maybe one step back。All of these units have their own fetchanty code。😡。

But what we discussed is that all of these pixels and fragments are essentially executing the same instruction。

 so we should ask ourselves is there a need for a fixed for all。😊。

Of them to have it independently or can we combine them into one？😡，So essentially。

 that's what this slide gets to is instead of。Suggesting that we have French Decode per ALU。

 why not combine a bunch of ALUs and have one French deccode， so let's see how that might work。

So you have a simple processing core， but let's change this a little bit。

 so we said we want to have fetchD for one but have many ill use right？😊。

So that's what our idea too is we have。We have one French report， in this case， eight tail use。

And then the context is now subdivided， we have eight contexts for each of the ALUs。

 and then we have a shared context。What does this start looking like， you know。

 especially the shared part of it？It starts looking like how we have blocks in Kuda。

 where if you think about the threads， each thread has its own registers that are private to each so its own context。

And then there's shared memory， so there's a shared context that all the threads can access。

So now you start getting the picture of how these things relate。So this is the idea too。

 let's see how we modify the shade in this。So we can take。

The same instruction from our shader bring it into F code and all the areass now execute the same instruction on different inputs and then produce different outputs the instructions remain the same the memory and the context changes okay。

So now we have。What is essentially one core， but it has eight AUs in it， okay？

So let's see how we can pick this a step further。How about we do 128 in parallel？Where you can have。

Taking this concept essentially where you have ALs。And one core and you make 16 cores out of them。

 so now you can do 16 times8 is 128， you can do 128 fragments in parallel。So now again。

 we start seeing how this is leading up to code architectures essentially。

So in terms of doing you know， our traditional workflows of rendering vertices fragments， primitives。

 and even compute work items， I wrote openC work items but they can be certainly any form of parallel compute。

 you can divide these up into different cores。Remember that within each core。

 you want to be the same instructions。But different courses can be executing different kinds of instructions。

 so that's where you can grow the parallelism。😊，SoNow。

 given what we designed about these GPUs here or the GPU cores here where we have these 16 cores and each of them have ALUs。

What we do about branches， you know， this kind of foreshadowing what we what we already spoke about in Ka。

 but it's well worth repeating it here。嗯。So let's say we have our AL used within TH4 and we are going to execute this shadow of code that has a branch in it。

So the first evaluation is to check if。Each of those eight codes has a true or false statement in it。

 and some can have true and some can have false。And in that case。

Those three threads that are two are going to execute while the fault shapes weight。

And then the false statements are going to execute what the two one way two one ways。

 so just like we spoke about Eda， this is not ideal。

 but sometimes it may need to be done and we should try to minimize this case the worst case scenario is that each core takes a different path。

And now you get one8， the peak performance and you have all the core all the AUs executing the same operation。

 you get all the AUs executing different operations。

 so that's the worst case scenario we don't want to do that。So simply processing。

 just for a clarification， does not necessarily imply C instructions。

With explicit vector instruction， so SSE AVX， you get what is essentially vector instructions？

But the second way， which is more of what the GPU is is scale on instructions and hardware vectorization where you where the cores essentially create the parallelism that you need。

 it's kind of like what we discussed in matrix multiply where the fall loops disappear and become implicit within the threads and the blocks we launch。

So the other thing we should discuss along with branch divergence is stalls。

 which is also something we discussed in the Quda lectures is about how memory is read and what happens when we wait。

So what we want to do along with our course， again， back to designing the GPU， right？

So let's take our course and add an L1 cache that's small but super high speed。

 an L2 cache that's slightly larger but slower speed and a big L3 cache that is shared with all of them that might be more larger but slower than L1L but still faster than the memory。

And then you have a bus between the memory and the GP itself and when I say memory it's more on the CPU side。

 so this bus kind of becomes the PCIE etc。Yeah。So。😊，Now。

 we always have to discuss about how we reduce that latency in the Quda lectures and matrix multiply。

 we've seen how we should have different we should have more threads to cover that performance essentially。

So。To do that what we want to do is interleave the processing of fragments in our GPU in our building the GPU example。

 we want to interleave the processing of fragments into a single core so that it avoids stalls and we get high and we get low latency essentially so the way to do that is to take our fragment shader and divide it into parts of groups of heads kind of like this is essentially where we get to the idea of wars so if we take our warp and have eight areas execute the first part until it hits a stall。

We are going to make it。What we essentially want is if this hits a stall。

 we want the next batch of threadreads to be able to run right away with zero latency between the switch。

 so we get a stall， we launched the next next group of threads。

Of course because we are executing the same instructions now batch two is going to hit a stall and same with batch here batch four but what we want is that once batch batch four hits a stall another the batch should be able to run in this case it would be batch one because batch one has finished its stall it's ready to run and as soon as batch four hits a stall batch one is ready to run so in this way what we essentially get is instead of one starting here stalling becoming runable then runs again and then two instead of starting here starts down here。

Instead of doing that， we get a more waterfall approach to it。

 so we are saving a lot of latency that's happening in between these stalls。

So essentially while it may slightly increase the runtime of one group because you see how it becomes runnable。

 but it may have to wait a little bit。But the overall runtime of all of these different wars is much faster because now they can all execute in this waterfall model instead of all having to execute sequentially。

So now what we've changed is。😊，Instead spite of each core with eight ALUs executing eight fragments each。

 so they had eight contacts at eight they were running eight fragments。

 now we want them to run 32 fragments on the same eight ALUs。What do we need for that。

 we need more memory so that we can stroll all of those contacts and they become very very fast to switch。

So this is the change we are making now， we have the Fe sea code。

 we have the ALU and we make our storage much larger。

But we don't make the storage much larger by you simple mechanism。

 what we want to do is we want a subdivder。So we subdivided by this。

 we create these subpaths through it where each group has its own context and shared memory and now you can have different context and shared memory so when one goes out of out for a stall another one is ready to switch in directly so in this case you can have 18 big 18 very small context you can have in this case 12 medium context or you can have four very large context with the same amount of memory you can kind of swap them in and out。

So we go back through something like this。What we're essentially seeing from， let's say。

 coming from the QUDa perspective is how you have the stretch Decode， you have your ALUs。

 which are the actual execution units， and then you have the memory that's sitting in the SM and what it's providing for that zero zero overhead switching of different ws。

So now in our example chip， what I want to do is before I get to the math that's on the left side。

 I want to show you how this relates to our code architecture。

 so if you imagine each of these essentially becomes a streaming multiprocessor so where you have each SM had its own scheduler and instruction controller it have many。

 many cores while in our example we may only have8LLs an SM can have 128 or 192 cores within each so that's how many threads it can run at the same time and then the memory that's within each SM。

Is essentially allowing us to swap out those wars and blocks as needed so that the compute of that SM is always occupied。

So that's essentially how it relates to the Quda side of things and that's also why shared memory is shared only within the block and not across all the cores。

 all the SMs because the shared memory is going to be living inside these memory banks that don't necessarily communicate across the SMs so we have SM we have the instruction and French thecode。

 we have the memory and that's allowing us to switch context really fast and then we have the AluUs and the cores which are actually doing the instruction。

So now if this is our CIS 565 GPUs。We have 16 cores， or in the case of KUa， we would call these Ss。

We would have eight multip ad units per course， so 128 total。

And we can have 16 simultaneous instruction streams because we have  16 cores here。And with that。

 if we have， let's say four watts per per core， we can have 64 concurrent but interleaved instruction streams。

 so how we have that waterfall waterfall model， if each if each SMm can house four context so you have the four purple memory banks here。

 if they can each handle four that means we can have，Four contact circuits switch right away。

 so four times 16 is 64 concurrent instruction streams。And a total of that is 512 fragments。

 so you can have 64 times eight fragments running at any given time。嗯。So， overall。

If you're running 512 fragments。That leads to 256 gigah flops if your clock rate is one gigahertz。

 the way to calculate this is you take 500 concurrent fragments。

Multiply that by the cycle in each plot cycle you can essentially do。

You can do one floating point operation。So you multiply that and then you multiply the clock rate。

 so depending on that and how many clock cycles it needs， you get to 256 Gco floats。

So that's the kind of map， so that's how we've designed our 565 GPU。

So if we compare the CPU and GPU memory architectures on the CPUU we can have。

 you know we have different cores with ALUs， but on the GPU well have very。

 very large cores but they have a lot more ALUs and probably slightly more execution context and some fixed function memory as well。

 and then you have an N2 cache and then you have a huge memory bus to our GPU memory whereas on the CPUU you have this DDR3 that's about 20 to 30 GP but on GPUs this is 177 architectures all slideed from 2014 modern day GPUs can get anywhere from 600 to 700 gigabytes per second。

 so you get this huge bus between the global memory and the caches on the GPU。

So as a thought experiment。If our job was to do element wise multiplication of two vectors。

The the way to do this is for each element we are going to be doing read a， read B。

 compute a times B and store the resultancy， so those four instructions with 3 memory operations 12 bytes and GTx 480 could to 400 multi 480 multiplications per clock at 1。

4 gigahHtz so that's you have 1。 1。4 billion essentially。

Times 480 multiplications that can happen per second。But to make that possible you need 7。

5 terabytes of bandwidth to keep all the cores busy again this goes back to the concept of matrix multip how we hit latency and stuff because of more compute so if you wanted to get this maximum compute rate of 480 multiplies per clock cycle you would need 7。

5 terabytes of bandwidth to keep up that and that's practically possible for GTX48 he had about 177 gigabytes。

So that's only 2% efficiency。😊，But it's still eight times faster than the CPU。

So even though we may or may not be using the GPU to its fullest incredible capability because other hardware limits。

 it's still going to be very much faster than the CPU so this this thought experiment where the problem is not limited by how much compute we have it's limited by the speed of the memory itself。

And if the memory for faster， we could compute it faster is known as a bandwidth limited problem。

If the。If the problem essentially is not with compute it's with how fast we can read with memory and the memory system cannot keep up。

 that's what is known as a bandwidth limited problem。

 you can have a compute limited problem as well where the compute can't keep up and the bandwidth is perfectly fine reading the data。

 there are different algorithms that are compute limited and bandwidth limited so we'll certainly touch on some of those as we progress in the semester。

So ultimately what is a GPU right we've designed this this GPU that you know for65 GPU essentially but。

At its core， compared to the CPU diagram we did earlier。GPU has a bunch of shader and compute cores。

 it has some fixed function for texture and rasterization。

 and it probably has some you know other things like video decoding and other things that can also use parallelddleism。

 and then you can have a scheduler that is able to schedule tasks to all of these many。

 many cores at different hardware or software levels。So that's the idea of a GPU。

So now the last slide here is essentially the summary of how we go from CPUU to GPU the first idea is that we slim down the course。

 we take out all the bulk around it and we have we pack it with many， many ALUs。

This allows for explicit CD instructions， it also allows for sharing managed by the hardware。

 so kind of like the matrix multiply implicit hardware implicitly in the hardware because we are launching so many different threads。

And the last idea is to have so much execution that the latency of stalls like memory reads and stuff is hidden by groups of fragments。

 essentially in Ka called warps， who can which can zero overhead。

 switch in when a group of threads hits a stall and the cores need swapping out。

 so that those three big ideas are essentially what are the core of GPUs today。

So that's it for this lecture， thank you for watching and more than happy to take questions as we come up in future classes and certainly looking back to get back to more on the parallel algorithms and performance side of things and then next class which will be Wednesday will be our Project three Paraer recitation。

The entire class will be dedicated to that because it's a much longer recitation we like to dive deep into it。

 but certainly looking forward to it the Pa raceer is by far one of the favorite projects that everybody does in this class and we really love to see great results coming from that so thank you for joining and I'll see you all on Wednesday。



![](img/aa62caa0e4818d45a2e236d0a73eeaed_14.png)