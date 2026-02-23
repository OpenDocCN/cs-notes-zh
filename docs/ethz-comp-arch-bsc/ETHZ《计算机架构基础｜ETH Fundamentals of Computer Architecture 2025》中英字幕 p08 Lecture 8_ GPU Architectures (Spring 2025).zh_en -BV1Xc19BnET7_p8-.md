# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p08 Lecture 8_ GPU Architectures (Spring 2025).zh_en -BV1Xc19BnET7_p8-

![](img/5b1db4a762d97151785ae527645e87f1_0.png)

。这面。不在。I this。好的。系咪。Okay， the video we can point already mut am I audioudible， Can you hear me。しだ。

Go far。I should be。Yeah。对先走一点。Okay。どランのます。not but the epi。Yeah。

 we don't have probably very issue with this one。Yeah。And they are easy。嗯。There。咁快。is。对。This is。What。

变更。二。我没什么消息。Do for。是。まさ。这个事所不行。不行。对。🎼That。🎼，🎼，Okay， let's get us started。Good afternoon everyone。

 welcome to another lecture in fundamentalamentals of Comp architectureitecture， Le 8。I'm Muhammad。

 I'm an official co instructoror of this course and today we're going to talk about GP architectures。

We're going to build on a lot on the topics that we covered during premiere last week on SIMD execution use。

Aine， vector processor and aic processor to be quite powerful in this domain。

And I have worked a lot on GPR architectures is actually quite close to my heart， my PhD he。

All about GP architecture， how to optimize energy efficiency and register it。

So it's actually I'm quite excited that I'm teaching my first lecture in FoA and also GP architectures。

Okay， so。We have covered a lot of different execution paradigm in this course。

 I think we haven't covered yet cito areas。Probably we will cover it later in later lectures。

But last week we started talking about CD processing vector and array。

 and today we're going to talk about graphics processing Uni or GPUs but before that these are also some readings for today's lecture this week。

But I want to basically to jog your memory， I'm going to quickly go over some of the slide。

 some of the important concepts that we covered last week。To remind you。

 so remember that CD processing is all about to exploit data paralleles that we have in many important applications。

 which is also called as regular paralleles when you think about doing operations on vectors on arrays like you want to add to vectors based element by so that's the application that we can benefit from CD so you remember that we cover this fleeing taxonomy of computers and we saw that say that CDs single instruction multiple data is a great way to exploit data level paralleles and array processors and vector processor are a very good example of how we can implement them CMD in our hardwares。

And simply is very efficient because you can amortize the fetch over billions of upprints。

 so you fetch one instruction， you decocodete an instruction and then you're going to execute that instructions on many。

 many ups and that' you can provide a lot of efficiency and parallelise。

So we talk a lot about a processor and vector processor in a processor we know that we have multiple processing elements and each of them are quite heavy I mean they can do a lot of operations and essentially in your vector you can assign your instruction to each of these processing elements so at in each time because you can do load operations in different places on different processing elements and then at the next cycle next cycle you can go to another instruction and so on and so forth so you have basically same operations at the same time。

And like this， and then you have also different operation at the same as space because your processinging elements are powerful and they can do a lot of operations。

On the other hand， we have also vector processors that in order to reduce the cost that's one of the good way to do it。

 so you kind of you have different processing functional units that they are specified for doing some operations like load addition multiplication in store and then you do pipeline so on this load operation you can pipeline load instructions across different array elements in con time。

And so when you have your pipeline full you can see that you' are basically executing different operations at the same time and that provides you parallels and performance so that's the difference between array and vector processor and in order to make them effective you really need to fit the pipeline with the data so that's why these array processors and vector processor they're relying on high parallel memory。

Memory banking and so and basically you need quite bandwidth in order to access your memory and that's not only your off cheap memory access it does it also needs you also need high bandwidth for your register life when you want to access register and bring them to your pipeline。

So we talk about this memory banking and we're going to also learn a lot about memory system later。

 you're going to see that this is one of the most important parts of our memory system。

 basically our computer system， nowadays。And this is a very good example how we can combine this paradigm。

 how we can combine a processing and vector processingor here we have an example for vector processor that you have a processinging element and then you have basically different elements of your arrays and you're feeding them to your pipeline。

 but then what you can do is you can multiply and you have different of these processinging elements。

 different instances of them and have it in the space。

And then you can basically categorize your data and map them elements that they are corresponding to each of these processing elements and with that you can have kind of array processor and each of them is a vector processor and with that you can combine these two paradigms nicely together I'm actually skiping these aside relatively quickly because they are kind of reminders for you。

嗯。😊，And yeah， and actually you're going to see all these slides today again。

 in fact this one we're going to see a lot when we want to use GPUs and say how we GPU are running these operations。

 so I'm not going to repeat that again。And we talked about a lot about advantages of these architectures in the a process and vector processor。

 but it's also good to know what are the issues and the main problem is that these architectures they work only in the sense of to be effective because these processors are also general purpose so you can do you can run any application if you want。

 but if you want to have good speed of and good efficiency you really need to have an application that have quite good data parallel like for example matrix matrix multiplication if that can provide very good performance for you。

 but if not basically your performance will be limited。

 meaning that for example most of the time you are instead of having a vector with a lot of active lanes and active elements you're doing operation only on one element which is not really useful。

For such architecture， so basically they are very inefficient if farless is irregular like for example。

 very good example of that is in pointer changing for example in link is when you are searching for a key and you can actually read this note from Fisher from this VAW paper。

😊，And also we say that if if the application is regular then actually we can automate these data level priorities and basically see the instruction generation can be automated and we work on this example that you can see that from this code everything is so simple so you can easily。

Do same the instruction because。You have a for loop and then you want to do addition across this two vector。

And so that's perfectly paralyzable， essentially。Okay， and yeah。

 we talk about vector and CMD machines that they are good at exploit regular data parallel。

 but also we discussed about performance improvement limited by vectorizability and of the code。

 and we brought up again this handle law which in the end your performance might be limited by the serial portion of your application。

😊，We're going to actually learn a lot today about many existing ISA that they include in the operation that's actually one of the things that I'm going to cover in more detail and this is for our Am law just as a reminder so we should not really forget Am law when we are designing architectures and when we are programming essentially。

Okay， so let's say now the how these safety operations are happening in modern United States。So。

The Is that we had in the past they were handling basically scalar operations and during the basic decades like 1980s or so people realized that we do need these kind of CD instructions in order to for example。

 accelerate applications like graphics and then the idea was that for example。

 using our current scalar operations like you already have， for example。

 instruction that you can do addition of two， for example， 32 bit register。

 so you add these two 32 bit register and then store the result on the third register for example。

Then they just come up with this a nice idea that they can chunk this array。

 for example here they are chunking this vector not vector， this register to four elements。

 now we can actually call it as vector register because you can consider that you have four elements in your register。

And then you just do addition， and the only thing you really need to do is you don't propagate the carry。

😊，From the first element to the second element， if you don't do that。

 then basically you have an element wise addition of these two array right so you can easily extend the Ia that you have in order to support vector operations and and people have have been also doing that in many for some other operations like I don't know if you know。

 for example， BCD when you want to。😊，嗯。Yeah binary decimal code when you when you for example decimal code like 89 the number 89 you just you don't binary code you just encode the first eight to four bit and the nine also in four bit and when you want to do operations on these encoding you do need。

s also support you don't need to necessarily propagate caries for example or you may need to propagate Car in a different way。

 so people have been doing that a lot and I think that kind of experience also help people to build on quickly on such stuff as well。

Okay， so this example is set four8 bit numbers。Yeah， and I said that basically we need to modify A。

 but that's not very big modification for sure。So Intel actually was one of the。

 I guess the first one that started doing that and they described this IA extension。

 they call it MMX， multimedia extension， if I'm not mistaken。Later on。

 they also changed the name for。Many reason for marketing reason as well。

But this is actually one of the very interesting extensions that they have done it so in their normal scalar operation they have registers of 64 bits so you can do addition multiplication or such operations on a scalar when you have 64 bits。

 but you have this possibility that you chunk these 64 bit into two chunks and then you have a word of 32 bits or in other words you can say that now I have a vector register that have only two elements。

You can even go further， you can chunk it to four or you can chunk it to eight and in this actually having eight beats chunks are actually quite good when you are doing image processing for example。

 because pixels are usually eight beats for example and then you can use it nicely in order to do graphics operations。

Interestingly， they didn't need vector links register so different vector length or how do you chunk it is actually specified by the by the up of that instructions so basic output that determines data type and as I said you could have8 bit bys four and so on and so forth and when you are accessing memory stride is always equal to one so if you remember from our last lecture。

When you want to fetch the when you want to load you basically you need to provide effective address right effective address for each load operation so in a vector you also need to consider your stride so strideide is set to one here so you cannot change this right yes it is the strip because of the eight bits within that one。

Oh chunk course is it because of the next chunk next year？No， no， it's not related to that。

 so you have a load imagine that you have a load operation here。And so that load operation。

So you calculated your effective address for this one and then you want to go for the next one。

 you just increment the address what you want， for example。Okay。

 and you can learn more about this I from this paper。So they they actually also， yeah， okay。

Yeah here's an example of this Ia that the call this packed compare greater and than were this is the the way of showing this instruction you can see that the pack compare equal or greater than and so in this example we are showing that for example we are having four。

16 beats of elements， and then you can do this operation。Another interesting support was。

 for example， supporting multiply Ed。Wwhichch is quite useful when you want to do dot product so in thatt product you need to multiply and then you need to do reduction sum and in this I they actually provided this support that for example here you can do multiplication where these two vector register and then you have the multiplication of element wise and then you have reduction sum in two basically position here。

Yeah。And you can see how we can use that for for example。

 doing basically dotpo if you're interested you can check more。

 but that's not really magic easy once you know the instruction and how they map it。

It is also an interesting example that they provided。Unfortunately， they didn't。

Provide the picture you know colorful， so we just give you some color here。😊。

So there's a lady here and the background here is blue and we have another image which is a bsome background and essentially you want to put this background for that lady such that that lady has a better background。

😊，So if you want to write it in a C in a scal array。

 you can just say that you have these four and then you checked。The picture of。

Each pixel of this image。If it's blue or not， if it's blue， you just replace it with this new image。

And if not， you just replace， you just you don't do anything and in the end you have a picture that you know you have a different background。

And then we can easily implement this with this MX the way you can do it， for example。

 is that you have a register that you initialize with blue。That's a pixel for blue color。

 essentially。And then another register that's。Basically yeah MMm3 that you load it with your be data with your this image X。

 and then you essentially you need to compare if it is equals to blue or not and then you generate a mask based on that right and this mask can be retord in MMmM1 here。

So doing that， then you can actually manipulate over this MMm bond。

 so in MMml4 you have this background。Basically image right which is Bluesome background so in MMmm4 imagine that you have that bluesome background and then in MMmm1 you have the mask that you just do and oppress pack and oppression across these two and then you got to this basically output which on the position that you don't want to have that background we have zero value and on the position that you want to have that background you have basically your bsome pixels right and you also do the for that for your image as well for your original image but for that you need to basically do the and oppression on negate of your mask that's why you're doing and oppress negate here。

And then as a result of that， you get to the basically。Another MMmm1。

 which you have your original pixel on those places that you don't want to place with the background and then zero and places that you do need background。

And then you just need to order these two together， right， and you get to this MMmM4。

 which is your new picture。😊，And this is the code you can check it if you are interested with these IA extension。

 but of course your picture might have。Thououssands of pixels right and this architecture only provides eight basically pixels so you're you also need to have a move have a loop here and go over all the pixels and make sure to you know finalize your picture。

Does it make sense？对。😡，So yeah and you can read this also note about this Intel Pentium MX operation that they say that Intel plans to implement MMX technology on future Pentium and Intel architecture processors and they are still also they are supporting such extensions I mean of course with different names which I'm showing here with you so MMX is a 64 bit MMX register for Integer later on they name it SSE streaming SD extensions。

And they also provide different generation of SSE like the first generation was 128 with XMM register for integers and single precision floating point and later on they also provide a double precision floating point and so on and so forth。

After that also they provided AVs， advanced vector extensions， which they provided， for example。

 tune 256 beat floating point， and also they provide this support which is FMA fued multiply at。

Which really quite important when you want to do that product is so you do multiply an addition and fuse operation basically you don't need to do it。

So you dont there is no intermediate step that you need to store。

That's actually a very nice terminology with fus it when you fuse the two function or two steps together。

 that means that the output of that step will consume immediately with the next step so you're fusing these two operation or you're fus two kernels together so if you see some kind of terminology like kernelel fusion for example。

 in GPUs or in some machine learning that's actually you need to bring remember this kind of idea that。

The main idea is that the intermediate result that one step produce。

I want we consume that immediately for the next system step。

Yes this is for saving consumption of for a storage and also not it's not only about for storage of space。

 but also for time because you need to store and then you need to recall again like invoke another curtain for example。

 so when you fuse yeah and you can pipeline it nicely you know。

 when you have this fuse operation you can pipeline the whole thing nicely。Okay。

 and after that they also provided MAX advanced Ma extension because they wanted to provide a matrix multiply unit tied the Ma multipier unit。

 so you can also check if you're interested， but I just wanted to bring you know overview for you。

But basically SD operations are also using a lot in modern machine learning accelerators I'm not going to detail of that there are many。

 many different accelerators for machine learning that they use SiMD but I'm going to highlight some of them this might have you seen already like in prior lecture Serbrass that they come up with this design of vfair scale engine so these are like we have different dies and instead of chopping all these dies and package each of them they keep them on a vfair and these dies are interconnect through some switches and then you can use the whole vfre for your computation it's actually quite exciting I'm going to show you this picture so this is your chip in Serbrass that you need for sure you need a lot of power to cover up this but this also quite efficient in the sense that you lose a lot of power and efficiency when you want to go outside the chip。

Because of packaging overhead， but here because dyes are actually connected with thinner metals and thinner connections。

 you consume less power and also much much faster in your data movement yes。

Some people are saying that， yeah。It's not hard to imagine right yeah yeah I mean if you're actually I' going to show you a slide that。

😊，We had a safari live seminar that we invited some people from Serbras that they gave a talk so you can also watch that if you're interested。

 but of course power up this cheap and also cooling down is actually so hard and。The thing is that。诶。

So the thing is that this chip is so powerful， so if you want to， for example。

 do computation comparable。😊，To what you can do here with for example GPUs and some other you also need to use a lot of GPs and for those also a lot of GPU you need to also spend a lot of power。

 but the main difference is that that might be a bit more distributed so maybe cooling down is easier but here you really need to have a very sophisticated process yes so here we have everything on one way if we have manufacturinguring defect we lose a lot of。

Of our surface area， that's true because we have to deactivate a lot of stuff。

 wouldn't it be better if you do something similar to what Apple does with connecting chiplets and then package the whole thing。

So the thing is that what Apple is doing which is also is a knownte thing that other companies are doing。

 but in that we are much limited in the number of dies that you can pack them together and you know interconnect together so the idea about these flavorafers case is that you can connect several dies together many dies actually so yeah I think these are not really comparable to each other but as what you clearly mentioned that's one of the issue that some of these dies may not work at all because of the。

Gield and many other issues so and one but one exciting thing about this architecture is that you can actuallyconfigure switches nicely and then just bypass faulty notes。

But then of course， the power of your wafor is reduced when you don't have many of them active。

 of course。Yeah。But why I'm showing this because this architecture is actually kind of considered as MIMD。

 which is multiple instruction， multiple data， because each tile and each die is actually doing computation on different layers of neural network。

 but underneath each of these elements are actually seen the in。😊。

So you have a MID machine which is distributed memory and you are connecting them with a 2D machine interconnection fabric。

 but essentially you have a MID machine with CD processors so each of these small dyes they are actually CD machines。

Which is quite exciting。 So if you want to learn more， I would suggest you watch this。

Saffari life seminar。It happened sometime ago in 2022。Okay。Any question？

So now I'm going to jump to graphics Per unit and we're going to see a lot that how GPUs combine A and vector processor and what the nice tweak that they made in order to make the programming much easier。

So but I want to first start with some motivational slides。

 so this is kind of evolution of recent GPUs and we are showing here actually from Volta。

 which is the architecture release in 2017 or so if I'm not mistaken。Throughrue Blackville。

 which is the most recent architecture of Nvidia， which I guess introduce。Around this time。

 actually last year in March also， I guess。And the。So these GPUs， as you can see。

 they are integrating more and more transistors， so like in this black here we have more than 200 billion transistors。

And they are getting B here and also big gear and a lot more powerful in doing computation。

 but the problem is that for today's applications that we one GPU is not enough。Because。

for two main reasons， one of them is that you need much more memory capacity。

 which one GPU cannot provide that， so people combine several GPUs together to provide that memory capacity that they really need。

And at the same time when you provide that memory capacity you also need to provide the computation power for that so as a result of that people and videoDdia also and other industry。

 they try to combine GPUs and together and interconnect them nicely to provide performance so they actually improve a lot and also the way that they can connect GPUs this is the architecture they provide in Uper that they use envylink generation3 and then in Hooper and then Blackfield so basically you can see that you don't need to know a lot but what they are showing here is that their interconnection is less and provide better bandwidth as they grow。

And this is what I already said， like we need basically multi GPU system to interfere a sat。😊。

And also different interconnection network， but the thing is that fundamentally all GPUs are the same。

And I want to now to go into the fundamental way， so GPUs are Cdy engine gene underneath。

The instruction pipeline operates like a CD pipeline。Like every processor vector processoror。

But the main difference is that the programming is not done using tricks， not simply instructions。

 and that makes a lot of difference here。So to understand this。

 we will check our parallelizable code example that we have seen also before。

 but before that I like to distinguish a bit between programming model。

 which is at the software level and also versus execution model which is happening at the hardware。

So program model refers to how the programmer express the code。

Like sequential following fun human model data parallel using SD or data flow or multi traded BD SmD and so on so forth。

 so that's a programming model that you might have used how many of you have have already programmed parallel。

quoteote。Yeah， so that's a kind of program model that you can， you know。

 use when you want to prioritize your code。But execution model refers to how the hardware executes the code underneath。

😊，It can be， for example， out of order execution， which we have seen in last lectures。

 vector processor a processor， data flow processor， multi processorces。

 multi traded processor and so on and so forth。So execution model can be very different from the program model。

 for example， you can have a phone U model that you write your program following phone new model completely sequential。

But then you can run it on an out of order processor。

 which underneath this code is actually executing out of order of if you still need to commit and retire instruction in the programming order。

 but that provides a lot of parallellysis for you。Or for example， spMD model。

 which is single program multiple data， meaning that you run one single program on different data elements。

For example， your program is。Addition of two arrays for example。

 so that's your program and then you run this program on multiple billions of data elements so that's the program we call it SPMD which is more or less actually on the program model it's not actually exact SPMD model implemented by can be implemented by the CD processor which is exactly what GPP does。

So GPU is basically hardware which implements SPMD model on a C hardware。😊，So。

Let's elaborate more with this example， we have this vectorizable loop that we use also in our last slides。

So we want to examine three programming options to exploit instruction level parallels that we have here。

 so by looking at this code you can see that we have very good parallels right we have several iteration of this loop and in each and all these iterations are completely independent right？

😊，So we will examine three ways， one is a sequential code SISD， the other one is data parallel。

 for example， using SD and then multit it like MD or SMD。So if you start with a sequential code。

 you can execute this on a pipeline processor， an out of order execution processor。

 which independent instruction can be executed when ready。

And differents are present in the instruction window and can execute in parallel in multiple functional units because all these its are completely independent and it's actually one of the very good example that your out of order processor can easily you know provide parallels for you。

So basically this loop is dynamically unrolled by the hardware so that's once you use out of order execution in that instruction window you're you know fetching your fetching instruction your decoding and you have a lot of these operations of addition right so all these addition instruction are coming load an addition you have in your instruction window and you can just your or。

In the sense that you're kind of enrolling this loop， you know， in your heart。

So you can also use super skater or real W for example for running these application。

 so you can see that I'm seeing all these examples to justify the difference between program model and execution model essentially。

Another way is that so we have a realization that each iteration is independent。

 so we can actually have a programmer or compiler to generate SD instruction for us so because it's actually automated it' quite easy to vectorize it。

And then you can basically execute the same instruction from all iterations across different data using SD programming。

 essentially。😊，So I'm skipping because it's not already available these and this can be executed by a SD processor。

 for example， like Victor and RA。😊，Another way would be。

 I realize that each iteration is independent， so I'm going to assign each iteration to a trick。

So programmer compiler generates a thread to execute each iteration。

 and each thread does the same thing but on different data。This can be executed on a Mindi machine。

So this particular model is also called spMD because your T is actually the whole program。😊。

You don't have a basically in some kind of model for example you have a program and then you make some trades。

 they do something and some of these threads are also doing something differently you know they don't do the same thing and then you merge them and then you continue so that's general multitras for example per but here all of your trade are doing exactly the same thing addition operation。

load and addition。That's why we call it single program multiple data。

And this can be executed on a Cdy machine， which。m I don't want to confuse Mo more。

 but this is also called S team machine， this is terminology that NVDdia use， single instruction。

 multiple trait。😊，And CinT is actually a quite nice terminology， in my opinion。

 that NviDdia is NviDdiaA users。😊，Sorry， yeah， yeah like it's it actually reflects to when you do spmD on a Cdi machine。

😊，You can call it ST so basically S T is a terminology that's specify kind of program model and execution model to get so that's why it's actually quite nice to have this terminology。

😊，Okay， so a GPU is a SD or SI team machine， except it's not programmed using SMD instructions。

 it's programmed using Treads， a CMD program model。

 and each thread executes the same code but operates a different piece of data。

So each trade has its own also context， can be treated， restarted， execute independently。

 so when you write a GPU code you actually think that you' are writing a scalar code。

Because you're writing a quote for the trade and you don't need to worry about many different threads that you have because all of them are going to be the same。

😊，In some part of your code， you might also break the rule a bit you know， because you can do。

 for example， you want to do reduction and you want to do reduction some。

And you have a lot of threads， but then at some point your number of threads is reducing as you want to reduce to reduction sum。

SoThen you need to have some trades that you do some operation and some trades that you are not doing operation。

But overall， these threads are basically execute the same code。

And a set of trades executing the same instruction， so you have a all trades have the same code。

 like you have a one kernel that you call， you're going to invoke or launch it for all trades。

But then in that kernelel code there are many instructions right so there are given a time there are some trades that they are running exactly the same instruction because they are exactly at the same program counter for example。

So those instruction， those threads are dynamically grouped into a warp or wavefront。

 Vp is a terminology from NviDdia， wavefront is for AMD by hardware。

So that's exactly like how hardware is making Sdi operation dynamically for you。😊。

So you're writing a quote for threads and then dynamically in the hardware， the hardware is mapping。

 grouping these threads together to form a vb and that's where we actually essentially seen the operation that's happening。

😊，Makes sense。So this hardware， is this complicated。So it can be if you want to be super。

 super flexible and efficient， it can be very， very complicated and people have looked to it a lot in the research。

😊，But industry N VDdia and AMD， they try to be not that much complicated。

 so I'm going to show some slide related to that， so they made some trade off to make it simple and still effective。

Very good question。Any other question。Yes， so multiple wars during different sites and instructions is all considered as one day then yeah。

Yeah， we so our GPU kernel has， I'm going to show it later， but is。

We have many threads that we grouped them at the software layer。

 we grouped them in a block so we call it block of threads and the program just assigned block of threads to the GPU and then hardware tries to make these warbs actually out of those blocks so programming does not need to deal with warp at all。

😊，But in order to do a to program it nicely and more efficiently。

 actually programming needs to be the bars。Because that can provide much better performance。

That's why actually programming GPU is easy if you want just to implement and get some。

But if you want to implement and get the very good speed of。

 and I'm not going to say the best speed of because that's a very strong word。

 but as much as you want to improve your code， you really need to be more expert and think deeply you know and also at some point you need to come up with better algorithm。

😊，To priorize your code。Okay， so going back to our example。

 we have this SPMD on symptom machine and the work is a set of threads that execute the same instruction at the same or meaning they at the same program counter。

So in this example， for example， we can have warp0 at PCx and then that warp can go to the next V to the next PC and the next PC。

 and then you can have many of these warps that they are doing your operation with。Any question？Good。

Okay， so you already know that。😊，And so let's also a bit compare what is a CD versus CT execution model。

So CinD single sequential instruction stream sorry a single sequential instruction stream of CID instructions。

So in S operation you have one single instruction and you are assumed that instruction over many。

 many data elements and each instruction specify multiple data inputs。

 for example you have vector load vector addition vector restore and then you also need to specify vector links or somehow specify with your op code essentially but basically the programmer needs to deal with all of this programmer or compiler need to deal but not many applications are easily vectorizable so sometimes programmer really sometimes they need to do a lot of effort to vectorize data。

😊，But in Sti， we have multiple instruction streams of scalar instructions。

So basically then you have just a scalar reion like load addition and store。

 and you just need to specify the number of threads that you need。So when you are programming。

 you just program for one trade， you are basically writing a scalar code and that makes the whole easy。

There are two major S advantages， which we're going to cover it actually today。

First one is that we can treat each thread separately。

 meaning that we can execute each thread independently on any type of scale pipeline program so it can be MID processing。

So really each thread can be separate。Even though。In order to be efficient and provide very good performance。

 you want to have as many as possible traits。That they are doing the same thing。

 exactly the same thing such that you can have your ver full active and then you provide a lot of performance。

😊，But it's also quite easy and you can do it and it's also， I would say。

 essential for some application at some point that you need to treat each thread separately。

That basically not all trades。Needs to run together at the same time and also not all trade needs to run the exact same code at the same time so and that provides a lot of efficiency and I will say programming ease for you。

And another important Cia advantage is that we can group threadreads into warbs flexibly。

 we're going to see a lot about that later also。But let's first start with the first one。

So the thing is that the idea of GPUs， the way that they treat warps is actually you have seen this idea before fine grain multi tradinging right I think in lecture 6C。

 we cover fine grain multi tradinging of warps， not Vps， but fine grain multi trading essentially。

 so the main idea of fine grain multi trading is that whenever I have a stall in my pipeline。

 I don't try to fix， I don't try to eliminate that install I just try to do something else。😊。

And you have a lot of threads。😊，And you can quickly context switch across these threads。

And in order to have fast context switching you really you need to have context of all threads on cheap available。

 so that's why in fine grain multitrading we usually need a big registerify because you need to have registers for all threads available such that you can quickly switch across between them GPUs are essentially doing the same。

So they have many vps available and whenever a vp encounters， for example， a load stall， you know。

 waiting for memory access， you just switch another vb and then with that you can keep your pipeline full without stlic。

That might not work all the time because as you can imagine。

 we might not have enough number of eligible valve we might you know have quite long gltency access memory and that's why also NviDdia。

Do not in video does not only you know rely on these funra multiting or multiting of varbs。

 they also added caches， you know they try to， for example。

 have a deeper cache hierarchy in order to reduce memory access latency。

But the main focus is actually fixing installs by using fine grain multi。But for example。

 in Fermi architecture that they announced in 2009， I guess， they added， for example， L2 cache。

 they didn't have L2 cache before in 2009 they realized that they do need L2 cache。

And then as of now they actually keep L2 cash and they make it bigger and bigger like I think in the recent architecture。

 they have something 60 megabyte of L2 cash， for example。😊，Okay。😊。

So now let's see what is fun multi warps with better example。

 like assume if warp consists of 32 threads， if you have 32 k iterations。

 then meaning that you need 1，000 warps， for example， where you're running your application。

Warps can be interleave on the same pipeline， which is fine grain multi tradinging of warps。

 so here as an example Warp0 can be add PCx and then warp1 can be sometime later can be at this PC。

And。😊，Varb 20 can be at PCx plus two， for example， sometimes so we are basically running them in different way。

And the thing is that all threads in a vp are independent of each other I mean that's what we really want sometimes that's not the case and that's why Nvidia also tries to add some instructions that threads in a verb can communicate each other they add an instruction like shuffel exchange that threads in a verb can communicate but the main way or the main idea is that we want all trades in a verb to be completely independent and vps also they want we want them to be completely independent such that we can run them in any order。

Let me yeah so if twos a problem large agency that means conflict such as the War one and continues。

Yeah， so yeah， but that's not necessary for requirement we have a workRP scheduler that yeah。

 but yeah in this example yeah yeah exactly， yeah， yes cost that。Yes， actually。

 because of memory access。Whether I really like so War two context， which is the work one yes。

 work one then hos the GP for as long as it requires doest ever have a problem that War two sufflicates now。

Oh， okay。Oh I see so youre you're thinking about fairness of our scheduling that's true actually so in people that you are doing research on warp scheduling。

 they try to make it fair and also have performance because sometimes when you when you when you are acting too greedy you know you try to run instruction from one board as much as possible then you actually get to very bad situations yeah exactly so there are a lot of research going on in that also warp schedule。

Yeah。So this is just a reminder for you about fine grain multi trading。

This is a lecture we had actually in FoOA and if you are interested。

 you can also check this one from our DDA course in 2022。Okay。Let's have a break。But not。

For the whole time。Let's let's be written back at 310 for nine minutes break。Thank you。Yeah，没事。Yes。

Yes。Yes。电细心。Can hear me。YesCan you hear me yes，'s。Goodっち。O嗯。I think it's not 310。 It's almost。

So let's get this started again。Okay， we were discussing about warps warp is set of threads that execute the same instruction we can have many warps and then we need to schedule across them and basically you run your warp on a。

CD pipeline and in that you have a scalealar trade execution essentially so so you're the back end of your execution in GPU is actually。

Salar。In a vector， so you have a scard。Functional unit。

Which it can be also pipeline so that's why we have it like a vector processor。

 but then we have several of them， which is similar to every processor。

 so that's why how we combine these two together。Its a high level view of GPU。

 it's actually quite old this version， but a lot of fundamentals are still the same。

You have several cores， they call it Sha their core。

 which is actually coming from graphics terminology。

 those cores that they were doing shading for graphics applications。

This is actually part of a story that I didn't cover much today， but NVdia， like people in the past。

 we didn't have this possibility to use GPUs for running。You know。

 our high performance computing applications。Around the years of 2000 or so。

 there were some intelligent people that they realized that， okay。

 if they just make a nice analogy between their application and also graphics application。

 they can use GP。them and also some researcher in the GPU in N videoo。

 apparently they were also following the same thing。

And but then basically NVIo also realized that okay。

 that's a very cool idea and then try to extend their IA and also this they provided this kudDa support。

Suchuch that they make it more automated so nowadays that we are working on GPU we don't need to deal with graphics pipeline essentially。

 but in the past like in 2001 or two there are some papers that the people actually use graphics library。

In order to do for example matrix operation。Okay， so this shader core interconnection network and then you have memory controllers and access to your option and in a shader core we have basically some you know the front end which is the program counter mask in caches。

You're decoding so decod instruction and your CM execution model， we're going to see more about that。

And I discussed already about latency hiding， which is happening in work level fine grain multi trading。

 which NVDdia actually relies on that a lot。😊，GPUs essentially， they rely on that a lot。Okay。

And in order to accelerate these， make it possible so you're need to have register values of all trays available on cheap in the register file and that's why GPU registerifies are actually very big。

Like for example， we have 256 kilobytes of registerify per GPU core。Which is 64K。

32 beat register per core。And during my PhD， actually， I realized that even that is not enough。

And I work a lot to you design a register which is eight times larger， like two megabytes per GPU。

 you can check that paper in as 2018 LTRF。Okay。We already shown this picture and now we want to see how does it look like when you have warp。

 so essentially you have your warp and different threads。I'm going to show here actually better here。

So this is your recall for you。But then you can have a Vp0 that doing load operation and at some point another Vp。

 V one， for example， doing accessing your multiply unit in your vector processor unit。

 and then Vp2 can be an addition unit and thenp zero Vp 3， for example， in load unit。

Andb four v five， so this is how you can， for example。

 do interly these warps and they are doing different operations。

And here you can see that if your cdy engine is， for example， eight lanes wide。Your v is 32 bit。

 not 32 bit， like 32 threads。You assign a traits。And then you run them in parallel in that processing element。

 like in eight processing elements， but then you need to pipeline。

The rest of it so you need to run four iterations of 132 bit warp， 32 trade warp in order to finish。

 for example， the execution of warp zero。So that's the part that you are combining Eric processoror and vector processoror together。

Does it make sense each one of theseangle？A single thread， not process。不清楚。Yeah。

 but you don't have enough number of processors。🎼You don't have as many as trades number of processors in your GPU so you need to interleave them and run them concurrently yes yeah not all of them like you can see that like eight trays are running in parallel completely because this is the time right so all of these eight trades are running in parallel because you have eight parallelyin genes but then。

After that， you need to pipe， you know， next cycle， next cycle。Makes sense。Good。Okay。

 and for memory access same instruction in different threads uses a thread ID to index and access different data elements。

 for example， here you have considered you have a。There are two arrays that each each of them is 16 elements and you want to run them on four warps and each bararb has four traits。

 for example， so you have vp zero to warp  three。And then essentially each of them。

 each of these verps has a trade trade ID， so in Vp0， we have trade ID0，1， two and three。

And if Vp one also we have trade I 0，1，23， and then if you combine the trade I with your Vp ID。

 then you can get to the。Unique I and based on that ID， you can actually access your memory。

And thats that's the way that your address calculation the hardware is quite easy and that's why actually it's actually coming from Cindy so in Cindy also you don't need to pay a lot when you want to calculate your next address of the memory so most of the time we are calculating address with this right easily so here also you can see that it's just using thread ID。

😊，Okay so for maximum performance， memory should provide enough bandwidth as we know also for C。

 and that's why actually GPUs are integrating high bandwidth memory nowadays， HM HM2 now HM3。

 for example， that for example， I think in Max not Max in Black Blackve architecture。

 they have8 terytes per second。Memory bandwidths per GPU core。And again。

 that's not only also of cheap memory or the GPU memory is also the register file should be also high bandits。

 so because of the register file GPUs are actually quite banked there are several register banks and there are multiple up collectors that they are fetching register values preparing them in the up collectors and then to fit to the pipeline。

So we need high bandwidthlist everywhere in the GPU because if you don't have that bandwidth list。

 fun multi trading is not going to work well for you。Okay。So Vps， as I said。

 they are not exposed to the GPU programmer。When you you want to run a like a GPU program。

 you actually have a mixture of CPU threads and GPU kernels。

 the parts of your program which is sequentially or modestly parallel section you write them for CPU and there is massively parallel sections on GP like blocks of threads so for example in this show that you can have a serial code that run on a CPU host and then you have a parallel kernel device that this is the notation for N video for example in Kuda when you want to invoke a kernelner you just name the mention the name of the kernel and then specify the number of blocks and the number of threads per block if I'm not mistaken and then some argument that basically you need to pass through that block。

And this can to be looked like something like this each of these is a block。

And we have many of these block and another terminology is that we call it a grid。And when it's done。

 basically we do another， for example， serial code。

And then we can invoke in other can and sort of yes s。A scheduling of。

Bris and ss out I can see if you heard。Um。Yeah， you mean， okay， like to figure out which。

 which Freds require you want and how many Fred is。

No this one is actually should be calculated by the program so program needs to yeah needs to realize how many threads。

 how many blocks for example do you need but these are GPU threads， these are not CPUU threads。

So in your GPU program you have a actually CPU code which you actually start with in main for example。

 you know like as you write， but then in that code you invoke a K and the GPU can and for that you need to first。

Do allocate some memory in your GPU memory device and then to move data from CPU memory to GPU memory and then invoke the care now。

But that invoke can be blocking or can be non blocking as well。

So sometimes you can invoke a canon and then see if you can keep going。

Because you are not dependent on that you can do， but at some point youre dependent on the result。

 then you can add some barriers that you weight and then you do yeah， for example。So sample。

 for example， GP code， this is your CPU code for example， and this is your Kuda code。

 which actually quite simplified here， but essentially you need to calculate trade ID。

 which you can calculate your unique trade ID using a block dimension and block ID and trade ID that you have。

😊，AndUsing this， you're going to get the unique number of ID。

And then you just need to do this operation， like if you load from your RAA and B based on your thread ID。

And then the output R ID would be some of these two。And that's your GPU code。

And this is less simplified， which this is your GPU program which has in the main part which is the CPU parts that needs to be run on CPU and this is the part that basically is your kernel here you are defining some your basically block and grid of threads。

And then you need to call this GPU program add the matrix and then you mention this grid and also the dimension of your block。

And these are the arguments that you send to your GPU program。



![](img/5b1db4a762d97151785ae527645e87f1_2.png)

Of course I'm not covering detail of programming， so if you want to you know get your hands a bit dirty with GPU programming。

 I would recommend you watching this lecture。And we also had a。

Pianist course in the past on hetero system course。

That we provide a lot about how to do GPU programming one of my former colleagues Juan that he's now in video actually he deliver study this course and I know many people in all the world actually they are watching these lectures to learn how to start with GPU programming and how to get actually advanced and we expert programming so this course is actually quite exciting I also wish to be honest and I learned a lot。

Okay。Yeah so from B suburbbs， let's see， so this is our SMm architecture。

 this shown from Fermi architecture in 2009 and we have basically blocks。

But the thing is that the programmer sees the blocks and assigns blocks through the execution。

 but in the execution we GPUs needs to assign these blocks into warps so blocks are divided into warps and so warp size for example it can be 32 threads which is usually。

More or less the case， there are some GPUs with different number of threads per war。

 but 32 is the common number。And the different vers are belonging to different blocks。

 and that's actually very important when which you should know。

The hardware should make sure that basically do not。Interleave。

Not inter do not share information across these blocks。

 so basically when the hardware is grouping threads to make a war。

Those threads should belong to the same block。So for example。

 the hardware should not select the thread from block one and group it with threads in block zero to make an instruction to make it work because that can violate some program model No no no。

 there might be actually the same program。But the thing is that there are some。

So what I'm also saying is that it's also very dependent on how we design， you know。

 and in order to keep things simple and also some of the in order to obey some rules that we have at the program model。

For example， we have a shared memory in GPUs， which thread that they are in the same block。

 they can use that shared memory to share data to each other。

So if you basically group thread that they are in these different warps， different blocks。

 then meaning that these can be， I mean， GPU should really understand that these threads they should not share。

Location in the block because they are from different blocks so that adds a lot another complexity to the GP hardware so it's the same program but they have which are independent parts exactly yeah yeah yeah yeah yeah yeah yeah exactly for a long time actually GPU was not supporting synchronization lot across across blocks so when program wanted to communicate across blocks most of the time they had to do course green synchronization like。

Shut the kernel， finish the kernelel， then make them synchronized and then start another kernel。

But now in recent GPU， they're also providing some support such that blogs can also share information and communicate。

Why would you make one box。There is the limit public。好的。

There is a limit there is a limit there is a limit and also GPU scheduler assigns several blocks to one SMm。

 which is in each streaming multiproces or each core， so if you have only one block。

That means that GP only assign that block to one Sm and the rest of SMs， which can be hundreds。

 they are useless。But yeah you're right， actually， I mean these all these are happening because of some of the decision that we are making at the Harvard and at the program model。

 so none of them， in my opinion are really fundamental。😊，Okay。Okay。

 so I think we already covered this traditional CD contains a single thread。Again。

 comparing between workplaceplace Cdy and traditional Cdy。And ISA contains vector SID instruction。

 but in verar based SMD， we consists on multiple scalar threads。

And this does not have to be lock step， meaning that threads that they are in the same work。

 they can actually execute independently， they don't need to be completely at the same。

 they don't need to execute instruction in lock step manner。

Meaning that there might be the cases that some trades， for example， they access cash， you know。

 they access memory and some trades actually hitting in the cache。So they get their data quickly。

 but some other trait in that verb they may miss in their cache and they need to access object memory。

 so they are expressing longer latency。😊，If we consider locker manner。

 meaning that that work is going to be installed until all threads get their data， right。

 which usually actually the case for NVD GPs。And I know that in recent version。

 they also tried to relax this also a little bit。But again， in order to make it simpler。

 they consider that warps need to be locus step。But。This does not have to be。

 so in the paradigm we can actually be more flexible。Okay。And again。

 you know that software does not need to know vector length。

 and that enables multitra and flexible dynamic grouping of trades。And I say is the scare。Okay。

So SPMD， we already covered it just a summary， single program multiple data。

 and this is a program model rather than a computer organization。

And each processing element executes the same procedure， except on different data elements。

Essentially， in multiple instructions， teams execute the same program。ok。Yeah。

And this is also I want to emphasize that each program procedure works on different data and can execute different control flow paths。

 which at run time， so trades that they are in the verb so you can have a controlflow graph whenever time to time you have some branch instructions that the result of that branch can be taken and not taken right and that decision can be related to your T ID related to that threadread data。

 so for some of the trades in that verb you may want to take the take pass for some of them you you need to take and not take and pass and then they divertge。

And we're going to see that that can actually how we can handle this。Okay。

So we kind of finished the first part， but now I want to talk about how we can group trends into wars flexibly so this is what I was discussing this。

Control flow graph of your one of an example application and you have several threads。

But different threads， even though they have the same kernel code。

 they might take the different passes because they are working on different data。

And this can cause a basically reduction in your Varp efficiency。

 so GPpU uses Cd pipeline to save area， as you know。And this can cause branch divergence。

 which we call it that so you have a vp that all trays are active and then you reach the branch instruction。

And then some trades wants to take pass A， some of them wants to take pass B。

And then this full active work diverged to two。AndBa less full active or partially active ver。

And then after some point， this needs to be recoveredged again。So GPU hardware is dealing with that。

 which is also not that easy and thats the fact that GPU hardware handles that makes the programming very。

 very easy otherwise one of the reason that CD programming is very hard is actually dealing with branches。

Because you need to deal with a lot of these masks， you know as a programmer。

 but GP hardware is doing that for you。But of course， if you don't。

 if you do it without thinking about the hardware， then your program is going to be super super slow and efficientient because in the end。

 this is not a good thing。Because you want to have your work fully active。

In order to have you know quite good paraise， but now you are not saturating or utilizing your performance as much as you should or you could。

Okay。So let's see we can how we can do these group threads into warp flexibly。

 so if we have many threads， we can find individual threads that are at the same PC。

 even though these threads might belong to different warps。But as long as they are the same PC。

 meaning that they are executing the same instruction。

 this paradigm should lead me to you group them。To another work so I can make a new work。

 which is now fully active。So let's see with that can improve s utilizationization。

 let's see with an example， so this technique actually called dynamic verarp formation or merging that essentially you have two。

 for example， different verbs， verp x and verb y and then you can say okay。

 these two verbs are executing the same instruction， but most of them are partially active。

So I can combine them and make a new verb verRP Z。With this and this verp Z。

 I'm going to run this only at verp x and y， and this is more active。

 so you are increasing your S utilization。But in this example， another example at some point。

 you can see that you couldn't combine them nicely together， why is that because？

The threads that they were active， some of them， they actually were on the same link。

And in that you cannot easily combine why is that because the registerify access as I said again。

 in order to be simple， when you want to access registerify your T ID specify on which register you're getting your data。

So when these two are on the same trade ID。You need to。At least permute some of them one of them。

 right， so then you need to change the idea of one of them。

And changing the idea is a lot of complexity in the hardware。

 which usually hardware does not support that， even though this is a。

I'm not sure if it's still active， but people in the past were working a lot on it， how they can。

 for example people suggest that we can do。Rotation， sometimes by one rotation。

 you can try to reduce conflicts。or sometimes by doing some some odd tricks because so once there are some tricks。

 then you can make your hardware at least a bit of those tweaks。

 but if you want to flexibly just change the trade ID。

 then that might not really work because the hardware going to be super super complex。😊。

If you have four more doing two different things but then they happen to go have the same PC No they are actually doing the same application sorry they're in the same yeah yeah they're in the same block actually yeah and then instead having underutilized two processes use merge into one process yes not processed to the same warp the same so you make a new warp and then you combine these two verps together。

They call it warp compaction， something like that so this is like yes。

 this is kind of the new warp formation that's why we call it dynamic warp formation so you make a new warp compaction yes。

But again， so its actually considered that these warps are on the same tread block。没有。

Because if that's not the case， then。Your program might violate your benefit is because of lockstep because what works being instep。

 right？The only benefit of what so the only benefit of merging the two x and Y into Z is because of block stuff because of the x would have to wait for its other no no。

 no， no， not at all。No， actually GPU hardware does not do that when when you have divergence。

 when divergence happen GPU。Consider that you have two verbs now。

And then try to execute these two vers separately and then merge them at some point。

 but then your graph actually can go to more if and its you know so that's yeah exactly that reconvergence point can be actually quite late and there are many works they have tried to predict that or reduce that but here that's not loster actually Loive is coming from the fact that in one verb the exact instruction of the instruction that you are doing all of them needs to finish that instruction。

Yeah， but but they already finished that branch instruction。

 so that that's not related to yeah that left be exactly exactly exactly。Okay。

But then if you're lucky and you have another ver， then you can try to you know combine this and then make it again more active and then you can so this is an idea that has been proposed in this work。

In 2007。And I already provide you the idea， essentially。That's。

You can try to merge them as much as possible， but you should not。

Forget about this issue so there are some cases that you cannot do so there are there are there are actually。

 I would say three important constraints when you want to do this one of that is that these two warps that they want to compact threads together they should be at the same PC。

Which makes sense and other one is that trade should not overlap trade I should not overlap and the third one is that they should belong to the same trade block because otherwise this can cause some。

Basically correctness issues and actually later on this team we actually published paper in 2011 that they tried to。

Tackle the third。Isue that they call it thread block compaction technique that youre try to do compaction at the thread block level to make sure that this does not violate that。

Important。Basific concentratetry。And here is an example that you can plate。

Maybe at home if you're interested。It's a bit quite as slow but。Nicely done animation， I guess here。

I's it baseline codes that would run like these， but with dynamic ver formation you can。对。Okay。

 I should play so in dynamic word formation， you can actually do， you know。

 you can combine them and make you。But there are in some cases you are not basically， yeah。

 these two， for example， you can combine them， these two， you can combine them。And then。Yeah。

 in this E and this F， this two E can combine， but then you have an E which is， you know。

 you have only one active thread。And basically that would save some cycles for no yeah。

 unfortunately， yeah because one of the trades actually。conflictlics so。Yeah。Okay， but yeah。

 this basic that's exactly what I talking can you move any thread flexibly to any lane in order to fix this issue that for example here you cannot combine them。

😊，Well， you can， but that would cause a lot of complexity， so people don't do it。O。

So analyzing GPUs is very fun。😊，We actually use this concept for exam question a lot。😊。

This is an example and I'm not going to solve you， you can actually check the solution。

 but you're going to also probably see。😊，In August or so some it's a very nice。

 you know exam question for me， I really like this question to be honest。

 and I usually I used to design them a lot。😊，I'm not sure of this time because hopefully Ts will design。

Okay。Yeah， I don't have much time， but I'm also going to cover a little bit some more concept very quickly。

So。We already talk about branch divergence。😊，We also have another issue which is long latency operations。

That we know that fine grain multi trading in general， you want to use context switching。

 fast context switching in order to hide latency for long lant separationions。

But that's why our VRP scheduler needs to be really intelligent。

So because here you have your warp based fine grain multi trading so this work Professor Mulu。

 he has also worked a lot on GPUs actually。When I started contacting Professor Muu in 2016 or so。

 you know to start collaborating with him， back then I was working a lot on GPUs and I was excited about the works that he has been doing a lot on GPU and I have read a lot from him and then I contacted him and then our collaboration starts。

So I have a very good memory actually from this paper， actually。

 because it's one of the paper I read and I enjoyed a lot。😊。

So I'm going to quickly go over this paper， but not into a lot of detail because we don't have time。

😊，But essentially， if you are greedy in your scheduling that you try to you know。

 try to schedule wars a lot and they compute a lot of instructions。

 and then they reach to the long latency instruction all at the same time。

Then you don't have to do anything， you know， basically you're going to have long start time。

So that's why in this paper they provided these two level round rubbin scheduling。

 this work actually has been done with collaboration with NVDdia。I kind of。

 I think that they are using this。In many GPUs as well， using this two level round Robbin。😊。

That basically you try to schedule barbs and they compute， but then you don't。

You want to have another group that the so you schedule a group of work。

 they compute and then you reach to a position that you have long latency operations。

 but the good thing is that you have state and another group。😊。

That they are in the compute instruction so you can schedule that。And with that。

 you can basically reduce the st time a lot。So this two level bar s is very interesting and it is very effective if you're interested you can actually check this paper。

😊，Also in this paper， they discuss how we can reduce branch divergence as well by providing these large warp definition so they find that they can have a if we have a large warps。

 then you can large warps meaning that much larger than 32 traits， then you can actually flexibly。

Try to make subbarbs out of this big large bar and keep your Cdy active。And basically do competition。

I don't really have time to go into detail of it， but if you're interested， you can check this paper。

Okay， question。I'm going to quickly also show some case studies， some of their GPUs。

 I'm going to show a lot of marketing numbers， but I'm not from Ninvidia so。😊，嗯。

This is one of the GPUs that they provided。Very long time ago。

G4 GTx 285 and this GPU actually the numbers that we are seeing here is actually quite like a joke compared to what we have now。

 but even then it was actually super powerful so they had 240 stream processors and video also called them Kuda Co。

Or they sometimes you can see that as SP， you know， SP is actually acro for stream processors。

And but。Another terminology is course， also a streaming multiprocessor or SM。

So you should be careful So like in GPU we have， for example in this GPU we have 30 cores and in each core we have some amount of stream processor。

 So basically the amount of sp per core you need to divide 240 by 30 essentially to calculate。

 I think it's gonna be8 right so you have eight sp per essentially one block stream one block or some or several blocks one streaming one no no no Yeah one of the cores。

Okay， and this is the architecture of it， which is actually a bit old in that sense。Again， I mean。

 today's architecture are also not that different fundamentally。

So for here we have 64 kilobots of storage for registers。

And we have decocode a step and also basically functional units for doing CinD operations like multiply ad。

 multiply and so so。Okay， and varp size is 32 and basically up to 32 verps are interleaved in a fine grain manner in each SM。

 meaning that the maximum number of threads that you can have and you can schedule per SM is actually 1。

000 in this architecture because you can have up to 32 verps and each varp is 32 threads。

So that's the maximum number of traits that this architecture had later on actually more distant architecture。

 I think we have maximum 2000 trades。😊，Two， I mean， two to the power。嗯。To the power 11。

A number of threats， first。Okay。As a structure architecture of the whole。

 the number of cores that you have and the number of trades， so in total you can have run 31。

000 something along that trade on your GPU。Okay， but。Basically， we are way。

Advance compared to that basically architecture in 2009 and you can see that GPUs get B fear and B fair so he can you can see that the number of functional units。

And here we have egogo flops。And I'm going to show you， for example， Volar architecture in 2017。

That in Volta， we have a 5，000 stream processor in total， and we have 1880 Ss。And in each S。

 we have 64 Sdi functional units per core or 64， basically SP per core。

Interesting thing that they added in NVIDdia Volta is that they added Tensor course specifically to support machine learning applications so at some point NVDA actually focused a lot on machine learning and that's why they are now quite successful and they are making a lot of money so they started adding some a even though GPU in general their model theyre actually very good for machine learning because in machine learning you do a lot of metrics matrix multiplication matrix vector。

😊，But if you want to even that GPU is not enough for that， if you want to make much better。

 you need to design accelerators and GP and video， for example。

 design Tensor course for that specific operation for matrixx matrix multiplication in order to accelerate specifically that kind of operations that we have a lot in our machine learning。

Tor courses are the。They are no， still they are stilldy， minddy， they are also shad， but yeah yeah。

So this architecture of V100 which we have ATSMs and you can see these L2 cache。

 I think we didn't have， for example， l2 cache in that the first architecture that I showed you。

 you can check later with。Okay， and these are some numbers about you know the performance。

 how much performance you can get， like for example， with single precision， you can get 15。

7 traillos， which is。Quite a lot。And for if you use tensor cores for operation like deep learning。

 you can， for example， you can get 125 trolops specifically for deep learning operation and tensor cores are essentially are optimized for doing this operation。

So you have two metrics that they are in this architecture， they should be floating 。

16 and then you multiply them and then you add them。Basically。

 you need to accumulate in order to do this multiply an accumulation。

 and then you have the result in 32 floating points。Yeah， and this is the same thing。

Some people actually try to domesticmystify the tensor core exact architecture that we have in Nvidia。

 this paper is actually from Toroot's group。😊，And they show for example that each vp。

 this is the architecture of tensor courses micro architectureitect in Volta。

 I'm not going into detail of that， you don't also need to know that for the interest of this course。

 but if you're interested to work on this topic you can of course check this paper so each vp utilizes two tensor cores。

So meaning that each tensor core contains basically each tensor core can work on 16 threads。

So warp is 32 threads， so basically each warp works on two tensor cores。

And each tensor core contains two octs， so called octs。And 16 cd units per tensor core。

 meaning that eight per octa。And we can do， for example。

 four by four metrics multiply and accumulate each cycle per tensor core。And if you look into it。

 basically the main functional unit that you have is these rectangles and it essentially this operation。

 you do multiplication and then you have a reduction sum a tree for reduction sum。

 which is why is that because you want to do dot product essentially each of these elements processinging element is doing reduction dot product for you。

 and you can use it。😊，It's also quite interesting here that unlike conventional CD。

 registered contents are not private to each thread。

But shared insight of because that's needed when you want to do that project。Otherwise。

 you have to repeat a lot of data and you need to have many， many repeated data elements。

 but here you can actually load registered values and you can share them a lot through these buffers。

And essentially， they can work together to execute。But。

Other companies also they designed Tensor core like this one is from Google。

 Google Edge Tensor processing units， but this is actually coming from a little bit different paradigm。

 which is system areas。😊，And we're going to also hopefully learn about s later。But。

It's actually from one of our research we have done with Google on understanding Google HPU。

 what are the shortcomings of them and how we can improve them essentially。Okay。

If you're interested about this work you can check this one and if you want to learn about systematic array you can watch this lecture。

 but probably we will also cover systematic array in later lectures。Okay。

 so after Volta we can we have this oper and video a 100 is one of the flagship。

Basically GPA device like then。And so we have something six。Thou900， the same processor。

We have 108 Ss and a lot of and you again 64 Cd functional units per core。

The interesting thing about NVDN 100 that I want to emphasize is support for sparsity。

So these tensor cores that I showed they are actually designed for dense matrix matrix multiplication and people have said that okay。

 for many of these machine learning we do we specify you in order to be more efficient。

 we don't need to do a lot of operations so we prune the network and we have a lot of e sparsity in our matrixes。

😊，And if you run them you can see that the performance of Volta is not good so in this work in this generation onper they try to support for provide better support for e sparsity once your matrix is a bit sparse you can still get better performance。

 but i'm going to show a number which you can see that is not that great so the。



![](img/5b1db4a762d97151785ae527645e87f1_4.png)

For deep learning， if you have dense metrics， this is the 30012 trolops that you can get。

But if you have some esperity。You can just get the double of that。You know。

 but in many works they actually show that we have 90% sparse values or 95 or 99 so youre really。

 for example， if you have 90% sparse you really want to have I'm losing my voice weight you need for example 10 times the speed of right because you have。

But because of irregularity and also many， many other reasons。

 they cannot get that much performance improvement， but still。😊。

They are trying to do better when they are a sparse。

And here is the architecture that they have for basically tensor course。Later on in 2022。

 we have Hooper architecture that has 144 Ss on the full architecture and 60 megabyte of L2 cache。

Interesting point about this architecture is that they added a lot of different basically precision for data。

Why is that because they realize that for many of these machine learning training， for example。

 we don't need。16 B， 32 B， 64 bit data， so we can do operation on8 bit data。

And that can provide a lot of efficiency and。Also， you can reduce youre getting how much you're consuming memory benefits for that。

月人 time。Yeah， so yeah， this is I want to basically underscore here that they added different precision to their design。



![](img/5b1db4a762d97151785ae527645e87f1_6.png)

And this is the most recent one in video Blackville that they announced it last year。

I'm not sure if it's already released， I think maybe some of them in G4 because N video has different category。

 there are some GPUs that they are coming from for graphics I mean you can still use those GPUs for doing computation as well。

You may know it like。T0 AD TI， I don't know 40 and 90 something， so you can do use them for game。

 of course， but you can also use them for doing high performance computing。

I think some of them they already released， but I'm not fully sure， but this is for example。

 one of the architecture that they pronoun， they announced that they they call it I guess super cheap。

 that they have two blackwell cheap。So I believe they are B200， B200 version。

 and also a CPUG that they have it on this and this is quite powerful and they can combine these super cheap in a cluster and make a super competing adult。



![](img/5b1db4a762d97151785ae527645e87f1_8.png)

So this is a picture of this N video。Blackfe architecture。

 I don't think this one is for B200 it's actually it's very hard to find the picture for now because it's not already released that much and there are a lot of marketing information you know that's very hard to interfere filter marketing information and get the information that you can rely you know。

 this is not that easy but is one of the architecture of Blackfe。😊，So in B200。

 which I think is the most powerful chip of this architecture， they have 160 Ss or 160 cores。

And they have80abyte per second memory， which HVM3。And you can have up to 192 gigabytes of data。

And you can see that the performance they get for， for example。

 32 floating point is 180 and for 64 floating point is 90 trough flos。Is it exciting？Yeah。嗯。

Is it even more exciting if you know the history？That people around 2000 so they were trying to。

See how they can make a supercomputer of vlops。And then very soon， actually， in video， you know。

Comes with this architecture and then we have trolos in our pocket nowadays。😊。

Between the last couple graphic cards that it just look like the image。

 they just grew the amount of like。This is die， no， this is only the die。

 this is the die of GP or the chip。对。A charge。Yeah exactly the fundamental are the same but yeah。

 but they're also adding some accelerator like tensor cores as we discussed and also support for lower precision。

 I believe in Blackfield they also provide support for4B data。

Forbi precision so yeah these are the changes that they are making They are not fundamental in my opinion。

 but they are doing I think they are doing the way to keep up with the performance。

 but there might be。Fundamental different way to do computation， of course。

 which we're going to also see later lectures， for example， with memory center computing。

 story center computing。You may not need to have that many GP to do computation we already actually this last week when we were in asplOS we presented two papers related that that you can do a large language model by using memory sensor computing。

😊，And get the better performance， which if you want to get that performance。

 you need to combine many， many GPPs to get that so that shows the maybe we need to rethink about if what we are doing is a good thing or not。



![](img/5b1db4a762d97151785ae527645e87f1_10.png)

Okay。So I'm showing you these pictures again because I want to。

Share some takeaway with you that essentially each GPU is quite powerful and it's getting powerful and powerful。

 but then today's applications are they need a lot of memory capacity and at the same time they need a lot of computation power so people combine many GPUs several GPUs in a cluster to basically provide collectively higher memory capacity and higher computation power。

😊，And that's why the interconnection network is going to be fundamental problem as we go also in the future。

 it was really fundamental and hard problem to solve in the past。

But is also getting harder and harder is the demand outpacing？Will be。

I couldn't follow the question so is the demand feeling the AI processing such as that outperforming the actual demand between？

Well， it also depends so。I would say that it also depends on the models。

 so as you make your models also more intelligent， you may not need to be also that huge。

Which actually we have seen recently that by， you know， by making some model more。Optimize。

 you don't need to， for example， have that sophisticated hardware to run it， you know？

Yeah general trend is that people just train more and then make the model bigger and bigger yeah exactly。

 but but I think that's also going to be one of the important research problem as we also go to the future how we can make our models much smarter and less compute hungry because。

😊，Maybe you don't need that because our bring， I don't think is that power hungry。Okay。

 and these are some interconnection network that people propose in video in different generation to combine。

So this architecture they combine， they provide all to old connection among envylink domain of 72 GPUs。

Which actually for Blackwell， so they combine 72 blackwell GPUs in this cluster using this interconnection network essentially。

Okay， so there are some food for thoughts， so we haven't covered cito areass。

But we're going to hopefully cover it， but there is also a lecture that you can check if you're interested。

 but essentially there are some question that which one is better for machine learning because there are companies that they are using sto areas like Google TpU for example。

🎼And the GPU that they are still GPU more GPU to be that systematically。

 so which one is better for machine learning， which one is better for image vision processing。

 which tys parallel， which one exploit and what are the tradeoffs。

If you're interested in such questions and more， I would recommend that you take this course。

 some of you I know you already。嗯。You are already taking this course， but yeah， if you're interested。

 you can take this seminar in computer architecture course。😊。

And our master level course for computer architecture that we go into。

Cutting edge research more deeply。To learn more about GPUs， I would recommend these courses again。

And with that， I will conclude to this。Okay。

![](img/5b1db4a762d97151785ae527645e87f1_12.png)

No question， I guess， right。