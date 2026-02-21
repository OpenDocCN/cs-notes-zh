# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P5：Chapter 4 (Intro to GPUs).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

videoio。

![](img/40ddbd75155d34594326f494dc087cdc_1.png)

Okay， we can finally take a breather now。 That was a lot。

 But I really hope that this is gonna sort of just ease that。

 This is designed to be a more passive part where you can kind of just sit around and listen and watch and just kind of enjoy it。

 there's no coding involved here at all。 So I thought I'd provide some context on different types of hardware what the whole purpose of GPUs are。

 I mean， you probably already know what they are。 But I just want to provide that background just so that we're on the same page entirely。

 And just to provide some kind of internal I guess preparation for the next part。

 It's good to have these breaks just to， you know， slow your mind a little bit。

 And give yourself some time。😊，But。First off。We have these CPUs， okay。

 you already know a CPU is it's general purpose。 high clock speed per core。 Very few number of cores。

 The on chip memory is very large。 So maybe you didn't know that the caches on the chip are actually quite large compared to the GP。

 This is because you know the memory bandwidth from the CPU to the Ram slots on your computer。

 Those are going to be like that transfer speed is going to be very slow。

 You have to move the electrons all the way from this part of the motherboard to this one。

 and that takes time right you constantly waiting for data to arrive。

 and that's like what takes up most of your time， right。

So you have these big caches for purposely like preloading things on that they're ready to use。嗯。

You have。Lower latency， So the whole idea of the CPU is to just complete this task as quickly as possible and just return the value。

 just complete complete it fast。And then they have low throughput as well。

 so low throughput means it can't do as much comparatively。

 it can't do as as much operations per second as a GPU can if you're talking about simple instructions。

 if the' more complex ones like managing and loading data and doing like file reads and writes like that'll be faster。

 but if you're talking like math and matrix multiplication， it is going to be significantly slower。

Theput is more talked about as like operations per second。 So if I have a bunch of cores running at。

 say， 2 billion clocks per second， and I have 6000 of them versus 6 cores that are running at 5 billion clocks per second。

 do the math， right， How many operations are you going to do on this one versus that one。

 That's the whole point of a GP。 Way more cores， A little bit lower clock speed。 But way more cores。

' just completely outnumb CPU。 And that's why it's faster。嗯。And on GPUs。

We have the 1590 hasn't been released yet， but I thought it was funny to put there。

GPs are very specialized， so。They can accomplish simpler instructions， easier to handle ones。

 hence why they have smaller controllers on them， which you'll see in a second。

 They have a lower clock speed。 Like I said， waymar cores and a lower cache。

So because you have that on shit memory， because you actually have this V Ram that you can access that is on the GPU and that this all of the NVIdia hardware engineers has essentially optimized for accessing that you're able to get a lot higher memory bandwidth that way up in the like a。

High 100 gigabyte per second range。 so it's like it's it's in the hundreds for sure。

You have higher latency on this。 remember it's not for you know minimize the amount of time it takes to complete this task and then just done right its it's more optimized for throughput。

 So we already talked about this。 but then you have these TPUus which came across recently and these are for modern deep learning applications So TPUus are for literally just processing tensors like you do fast matrix multiplication and fast linear algebra that's what it is。

 Tensor is tensor operations is linear algebra and it's just specialized for doing that。

So TPUs are faster， but way more expensive and specialized and typically not consumer grade hardware。

 so that's why we learn how to build on top of infrastructure with GPUs because you can actually afford it you can have one at your house。

And we're fairly low cost。嗯。And then you have these FBchas。

 which I don't expect you know what these are， but these field programmable gate arrays are very specialized pieces of hardware that essentially say instead of having to write like or build a custom hardware configuration like for a certain task for making something that you need to run really。

 really fast you can just program these， you can just program the actual chips to do something more。

More fine grain on what you want。 So there's more control over it。 very expensive， very low latency。

 very high throughput， high per all of this， right， these are， these are more expensive， but。



![](img/40ddbd75155d34594326f494dc087cdc_3.png)

They allow for modularity， if you will。And then just for some background on GPU history。

 so you know back in 1993 when Jensen started NviIDdia， they had the you know the Gfor cards。

 all of these， I wasn't alive during this time。

![](img/40ddbd75155d34594326f494dc087cdc_5.png)

But。You have then you start getting into， you know after after the G47。

 you start getting into these these better ones， so like the Tesla cards， the Fermi， the Kepller。

 Maxwell， Pascal， and then Volta is when things really started taking off the Pascal and the Volta cards。



![](img/40ddbd75155d34594326f494dc087cdc_7.png)

And then you have tiring， and then ammppire， which is what my card is based on。

 And then you have Hopper， which in case you didn't know Hopper cards are really， really fast。

 like the8100s and the H 200s。 And even the recently released Nvidia blackwell chips。 Yeah。

 those are ridiculous。 This is this is a little bit outdated， of course。

 So there are actually like chips on here。 I just got like an outdated screenshot。

 But you get the idea。 This is how it progressed。And then you have like the relative clock speed per core on here。

So， you know， some of these were like really， really high。

 but didn't have very many cores and then NviIDdia kind of figured out like， okay。

 we should just put more and more cores on these things， right？嗯。And then you get the， the overall。

I think floating point performance is what this is。So。Yeah， once you get to vol。

 it's starting to get， it's starting to get really high。

 So I think this is a double precision gigaplops。So。You know， six。

 essentially six teraf flops of compute on the Volta architecture， which is pretty good。

And then it gets better and better from there On mine， I think I have right now。

 it runs at a high of around 23 23 teroflops on Kublos。

 So Kubloss is the fast linear algebra library that multiplies matrices really quickly。

 and'm on there I'm going to get pretty much like 20 20 gigaplops of single precision compute。

So that's that's that's， that's quite good。嗯。What makes these things so fast for deep learning。

 I didn't actually cover this。On this CPU， you have very little course。

 You have these big control units that are taking up a ton of space。

 You have all these caches everywhere that are flooding the thing。嗯。

And like you you you're not giving that much leverage to the course， right。

 like the course can do advanced， complex instructions， but there aren't that many of them。

 So you can only do so much。Whereas if you have this other architecture where you have simpler instructions。

 simpler controller， simpler registers， smaller ones。But a ton of core。

 like see most of this is taken up by cores and then just caches and Ram。's that's ideal for GP。

 So in here you're able to essentially the the idea here is you're trying to put together a puzzle。

 I try to put together a jigsaw puzzle。 And the point is is it doesn't matter which order you do it in。

 So you don't have to do like this row and then this column， this column like it doesn't matter。

 you do this piece here， this piece there， do like a block like a chunk there。

 it doesn't matter as long as it's all assembled together properly in the end。

 that's what you care about。 And that's what the GPU is really good at。

So typically you'll do things as like you know one like multiple puzzle pieces at a time or multiple blocks of puzzle pieces at a time。

 so you'll have like a two by two or like a four by four thing of jigsaw pieces that you'll maybe do at a time that's like the that's the intuition behind Kuda and how how now you program GPUs to run fast and solve these problems quickly on the CPU you might be able to only do like see there's only four course here So you might be able to only do four given pieces of that puzzle out of say at once。

Whereas GPU， you know， let's say you have like 6000 cores right if this， if this puzzle has like。

I don't know， say like 12000 if if it has 12000 pieces， well。

 you can effectively do that in two operations because you're able to do the first 6001 and then the other 6000 in the second。

 So it's effectively two operations that you do it in。But if you divide 12，000 by4。

For meaning number of CPUU course， you actually get 3000 operations so you can see how that can be drastically fed up。

 that's that's why GPUs are so fast because you can because you can do that。

Now there there are some there are some common terms that we refer to these things through。

 So CPU is the host， you're going to see this in Kudo Once we start writing kernels。

 the CPU is called the host， which is pretty obvious and then it just kind of just kind of makes sense for that to be named that way。

 And then the GPU is the device。 So you have the host CPU and then GPU， which is the device。嗯。

The CPU is going to。Mainly the performance there is going to be latency in second。

 So you're looking at latency。 How quick can I do a given task and the GPU is throughput and task per second。

 So for example， if you're doing a rendering task， it's like how many pixels can I render per second or how many I don't know how many pixels can I can I Yeah sure。

 render per second， that's fine。In a typical coUuda program。

You're going to allocate some memory on CPU memory。 So it's going to be a classical like C Malck。

 That's what you're going to do。And then。Once it's allocated on CPU or host。

 you're going to copy from host to device or CPUU to GPU， and then once it's on the GPU。

 you can actually launch a kernel， which is what these parallel functions are essentially so on a CPUU you have a function then a GPU you have a kernel。

 which is the GPU function that can be parallelzed。嗯。

And that's that's the main intuition there is you start off with CPU， move everything。

 do everything really fast on GP And then once you're done with the results you move them back and then do whatever you want with them from there。

 you might even continue to just feed it more into into more and more kernels until the whole thing is done right but that's likes that's the ideal workflow is you have to CPU and then this GP thing is like an intermediary。

 which you have to convert back to CPU to do if something useful with。嗯。



![](img/40ddbd75155d34594326f494dc087cdc_9.png)

The kernel looks like a serial program。 So if you， we're going to look at these in a second here when we jump into actually writing these。

 But it's， it's going to be a very simple function。And it's gonna， it's going to have very few lines。

It's it's gonna to look like this basic serial script。

 except it's going to have some key terms in it。 These are mainly threads， blocks and grids。

 don't even worry about those terms right now。 We're gonna get into those。

 I'm going to explain the philosophy behind them I'm going to explain pretty much the whole coud architecture for you and just help you understand what the heck these things are for。

 Now some common terms to remember before we actually start jumpmping into this stuff are Well。

 first of all， kernels。 So kernels is like a weird term you might have thought like popcorn kernels like like this is what I thought I was like what popcorn kernels。

 while we're using those on on computers。 that doesn't make sense。

And then I jumped over to convolution kernels， which is like when you do like a convolution operation。

 you might have seen this in like CNNs if you've done a lot of stuff in like maybe pietorch and you've like looked through the intuition on that it's like a sliding kernel that does that does like an image processing thing on yeah just images filter that slides and does calculations that's called a kernel So I was like is it that no no it's not it's not a convolution kernel it's also not a Linux kernel either there's lots of different kernels we have there's actually four kernels popcorn kernels convolution kernels Linux kernels but the best one is GPU kernels So that's the ones we're gonna be working with there's actually a little keyword that you highlight you go underscore underscore global underscore underscore and that defines a kernel on the GPU So there's actually a way we can explicitly say that。

And yeah， not not an external story。I thought the same thing too， it's like which one is it？But yeah。

 so we're going to go into threads， blocks and grids。

 That's going to be one of the main things in the next chapter。 and then。

Two more like sort of just lingo terms are G。 So G E M M。

 this stands for general matrix multiplication。 So what this generally means is。啊。You have。

 it's not just multiplying like a and a times B equals C。 It's not， it's not a mammal entirely。

 You actually do a mammal， and then you have this alpha you have this alpha parameter。

 which you scale the result of that by。And then you add it to this beta scalar times as times a matrix c。

 which is the shape of the output matrix， so that's like a lot of linear algebra。

 which I'm not going to cover right now， but in case that's like in case that makes sense to you。

 it's essentially this alpha times times maximmal of A and B。

 and then you add that to a scalar B times C， which is the shape of the output matrix。嗯。

That that's what a gem is。 So it's， it's a mamal， but with more。And then you have S gemm。

 So that's just。General mamal， but with， but with single precision。

 So it's explicitly single precision。 You can do a half mammals like an FP 16。

 You can do a double mammal。 You typically don't。 though。 It's like FP 64。But yeah， so。

Generally speaking。Jem asked Jem， those are important。Then you have the CPU。

 which is also called the host， which runs functions。Versus the GPU， which is called the device。

 and it runs kernels。嗯。And that that's pretty much it。I hope， I hope that wasn't too hard。

 We're gonna dig into some kernels。 Now。 this， this part's gonna be a little bit is gonna be a little bit intensive。

 You'll need to pay attention a little bit， but it's going to be fun。 And I promised by the end。

 you're gonna be really enlightened。 you're gonna。😊。

Like the first part of Kuda isn't actually that hard， we're just going to cover very。

 very basic kernels like vector edition， it's not going to be that bad at all。

 but just to introduce you to the philosophy and the whole design principles of like basic kuda C programming。

