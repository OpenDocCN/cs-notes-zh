# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P2：Chapter 1 (Deep Learning Ecosystem).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

![](img/c37b4ae812326667dccc6866281d1214_0.png)

So now we're going to go into a little bit about the deep learning ecosystem right now。

 So obviously this is not going to be up to date in five years。

 so just you know take us with a grain of salt， this is not this is not everything。

 This is just what I found interesting to look at and focus on and to be aware of in the ecosystem and how you can sort of interconnect things and understand what's going on。

So this doesn't actually go over anything highly technical with Kuda。

 but I thought it's better to show you the ecosystem rather than just entering technical details blindly。

 like if we just dump straight into Kuda kernels， you won't know how to connect the dots later on。

So when we when we're actually building out good algorithms， it's like， okay。

 now you have the skills to do this， where do you apply that？So this is。

 this is what that aims to give you just a bit of background。

 Understand the ecosystem will help you map out everything properly。

 and it provides that initial motivation to learn。 So some parts are going to get really hard。

 And when you have that higher level of motivation to see like， okay。

 this is what I can actually build once I learn how to do this instead of just。

 let's learn Kuta blindly， that that seems a little naive。

 So going into it with like understanding what to do later on or what you can do。

 I think is really important。Again， don't feel free don't feel binded to just watch。

Watch me talk about a subject for 20 hours。 You may limit your learning if you just force yourself to sit down and just just watch and listen to what I'm saying。

 I do encourage you to go down rabbit holes。 So if you find something that interests you in this section or other ones。

 just totally just go down there。 That's where you learn a ton， right But anyways。

 I' organize this into several sections。 So research， production。Low level。Infer for edge computing。

Ease of use。Compilrs and miscellaneous。

![](img/c37b4ae812326667dccc6866281d1214_2.png)

So。We start up at the top here with the easy ones。 We have pieytorrch。 We have Penorflow。

 We have jacks， and Fireship has videos and all these。 these are very well documented。 I'll let you。

 you know， you can kind of just like read through these。

 I'm not going to go over every single bullet point because it's already here。 But yeah， you have。

You have MLX developed by Apple for Apple Silicon， open source for Apple devices。

Pytororch lightning is like pytororch， but reduces boiler plate code。

 So there's a Reddit poster here， which was interesting when you do like when you sets like your TF 32 precision to do tensor core computations in in Pytororch。

 like that's boilerp coat。 So Pytorch lightning is actually going to reduce that。

 and it's going to remove that boilerplate So you don't have to worry about like including all those little optimizations and and and hacks。

So。When it comes to production this is there's typically two things that fall in here so you have training and inference and some of these will support two of them together。

 some of them will just support one or the other so in here we have VLM which is quite interesting。



![](img/c37b4ae812326667dccc6866281d1214_4.png)

嗯。

![](img/c37b4ae812326667dccc6866281d1214_6.png)

Search a BLM on Gitthub。Actually go down we can see。Wherere it go， Yeah， LM Inprint and serving。

And then。Vertico performance， yeah， so performance benchmark against Tensor RT LM。

 which is the next one that I'll actually talk about here。

 but they implement a bunch of like very essentially hardware GP optimizations that we may talk about later on but VLM is great Tensor RT is pretty much Tensor runtime by NVIDdia。

And they have a tensor R T LLM。 So it's for like inferencing language models with all of these。

 you know， all these different optimizations。嗯。Specifically for LM imprints。Now。

Triton is Triton is something we're actually going to cover a bit more。



![](img/c37b4ae812326667dccc6866281d1214_8.png)

Trine was developed by open eye。 We go here and see this。

Tlls you about like what the heck Triton is like what the motivation was， where it came from。

 but if we look at this paper from Harvard， this is actually where Triton originated from so。

Try an intermediate language in a compiler for a child neural net computations。

Tiled neural net computations is the key here。 This is where a lot of the performance comes from。

 And you'll see this later on when we build fast algorithms。

 Tling is where you have like a giant problem where you where you have to do linear algebra operations like on tensors。

And you have to do them fast on parallel parallel processors like GPUs。

 And so what you can do is you can tile the matrix into a bunch of little like squares。

 like sub squares。And you can you can multiply them together。

 So this way you don't have to do like an entire thing at once and then reserve it and worry about all that stuff。

 you can literally just select blocks and the parallel processors and couta are extremely good at processing those blocks because of the coa architecture。

 which we will talk about later。But trying is interesting， this is a whole paper。

 which I'm not going to dig into in this course， but a lot of interesting both compiler and you speedups that you get from approaching things with a tiled philosophy。

Now。Just some other optimizations we'll get in performance is torchdt compile。

 So you do torchd compile and then open bracket， model， close bracket。

 and this will literally just increase performance 30% out of the box itll take that dynamic graph that Pitorrch builds and it'll static it'll snap it into a static representation for production because we're using it for production and it'll just apply optimization all around which we will dig more into this course like that example would be like kernel fusion。

 where instead of doing a separate function for each for each step。

 you're like combining two or three operations into one single function and that like reduces some overhead computation that you have to do there。

 So just a bunch of these little optimizations that torcht compile does extremely recommend for production。

Torch script is a little older， but there is an article here on Torch script。Tort script。

I haven't actually used， but there are some more discussions here that you can follow。

 I know it's a little older， so I typically just resort to more so pile for most things。

 but it's it's here in case you want that。 And then Onx runtime is also interesting。

 I should probably should have put onx before Onx runtime， but it is what it is。

 Onyx runtime is pretty much。

![](img/c37b4ae812326667dccc6866281d1214_10.png)

On top of Onyx。 So you have this thing called Onyx which exports a model from either Pytorch or Tensorflow。

 whatever you want down to this Onyx format that's intercompatible。

 So I don't have to just export like some tensors from Pytorch and then like I can't use them in Tensorflow right because it's like a different file type serialization might be different。

 And so Onyx is like this universally know optimize supported It's like a do Onyx file extension that you use for storing neural net weights and tensors。

 So Onyx runtime essentially takes that and allows you to just run it faster so。

That was built by Microsoft。And then a cool little project I came across。

 and that chat JBT recommended I put into this course was the Tron2。 So it's， it's interesting。

 You might find it useful， but。嗯。Developed by Facebook。

And it's essentially a computer vision library that uses。Image detection and segmentation algorithms。

Just a bunch of like really cool computer vision stuff that it has。

 a bunch of different neural net architectures and hats that it employs。

 And it's just one of those fun things that you might want to mess around with。

Then we go to low level， which is what this course is based on。

In case you haven't read the title it's on Kudos。Kuta is compute unified device architecture。

 programming language， programming platform rather for NviIdia GPUs。

And there's a bunch of stuff which we'll dig into later。Rock N include equivalent for AMD GPUs。

 and then you have open CL， so this is more general built for CPUs， GPUs， DSPs。

 other types of hardware， so just like a general purpose computing language， open open source。嗯。

And then we have edge computing and embed systems。 So what heck does edge computing mean， Elliot。

 what does edge computing。Think of the Tesla fleet that Tesla has。 So there's a bunch of cars。

That are maybe running into accidents occasionally。

 And so they want to report this back to the Tesla data center to train on and improve the models。

 So you'll have a bunch of these this essentially this fleet and the purpose of edge computing is to have them own doing their each of them doing their own local computation。

And then whenever you do an update， you're just going to send that back。

 and you're able to have like this centralized entity that。

I guess the centralized data center is our entity here。

 and that's just going to do some training on all of those and all that new data and。

That's pretty much what it is， it's just like a decentralized computing， if you will。So， you know。

 you have you have like Tensorflowlow light， which is like a light version。

 a lightweight version of Tensorflow， and then Pyhor mobile the same thing。

W I mean there's always optimizations you can do in Kuta and like just plain Pytorrch that'll just make stuff run fast either way。

 but there is Pytorrch mobile for that。 Then you have coreml， which is for Apple products。

 So like the Mac OS watch TV Alvis。Then you have ease of use， which isn't like entirely coa related。

 but I thought I'd still mention this because some of these are really awesome。

 so you have you have fast AI， which I'm not going to talk about a lot， but you can you can look。

 you can look into this maybe separately。So they have their own， they have their own thing here。But。

Yeah， I'm I'm not going to go over fast AI， but they have some interesting stuff。Onx。

 which we talked about before， stands for open neural network Exchange。 So the X is capital。

 And that's where the X comes from。 Liter used do Torsal Onyx or export model。And then。Dummy input。

 and then is whatever the file name is。 so you can look more into the H dos and Onyx as to how to do this on both Pitor and Tensorflow and whatever else you want。

 But this is how you would export an onx format。嗯。And then this is the Tensorflow equivalent。

So this is essentially this like nice little image that I got where like it kind of binds with everything。

 so Pytorch tend a flow careass a cafe which was initially what Pytororch was using。

 Cafe was one of Cafe was one of those original parts in the Pytor Gva system。From a while back。

So that just kind of shows how they can interconnect together。

 so you like export in one of these and then you can import back into any one of these plus onx runtime。

 which runs faster。And then you have weights and biases so I got a little snippet from the internet as to like what this looks like。

 but pretty much allows you to track your training runs and a bunch of different charts and statistics about how your models are performing so what I'm doing like when I want to train like a a clothing recognition model I can literally have all of these different ones so accuracy on sandals。

 shirts， trousers， pullovers boots right boots is like kind of chaotic and pullovers just kind of worked fast。

And then this one too， so you can kind of just track a bunch of things and understand what how your models are performing and then show that to like maybe your maybe your employer。

 whatever or whoever's， maybe your manager。And just kind of get things done that way and document things easily without having to use same mat plotlib。

 It's all just kind of tracked and imported and taken care of for you。And then cloud providers。

 these are actually quite important to know not necessarily on the low level part of like Kuda。

 but these are still good to know because they play a major role in the ecosystem。

 you have AWS so AWS is a major one。 I personally use AWS as products and prefer them I'm not endorsing like not sponsoring them that。

Not sponsored by them， but I do use AWS products。And the two main things here for MLl stuff is EC2 instances。

 So these are like used universally。 you just fire up like a remote machine and you can SS into it and then do whatever you want and you can use all the specs like it's literally command line access and you can do whatever you want。

And then you have sage maker， so it's a little bit easier and more ML focused。

 but you can run Jupyter notebooks on a cluster。 So instead of worrying about a command line and having to fire things up in like。

In VS code， like VS code SSH。You just run a Jupyter notebook literally like in a browser or you can just SSH into the SageMake notebook。

 I believe。嗯。And then you have the data labeling part which is very big in the world today。

 So where does all the data come from that we're training models on Well。

 this is exactly where it is if you go AWS SageMaker and then you find like the labeling part or mechanical Turk I believe believe is what it's called that's where all of the labeling on AWS takes place so。

You know， big stuff there typically costs like a decent amount of money for people to label your stuff。

 but that's that's where you find it。And then model training and deployments that's also supported by SageMaker so you want to like deploy your own Lama3 variant it's like oh there you go sageMaker。

Then Google Cloud， I don't use as much， They have vertex AI and their VM machines。

 which are like EC2 equivalents。Then you have Microsoft Azure。

 which I haven't actually used that much。 So it's just like another top three like either of the top three players in the ecosystem and then you kind of break down to open AI fast AI and Lambda Las。

 So Open AI provides their own like fine tuning services and you can everyone knows open AI you can literally go on the website and just navigate around there and figure out what you want to do with models。

UmB A Iye。

![](img/c37b4ae812326667dccc6866281d1214_12.png)

So I haven't entirely gotten a picture here yet， but I go to。



![](img/c37b4ae812326667dccc6866281d1214_14.png)

Baas said AI。Then go to the console。Hopefully it doesn't expose anything bad。 but like， yeah。

 I can select any of these。It's just like a bunch of rigs that I can rent for an hourly right。

 gives all the specs on them everything。 And it's great， so。You know。I set R T X 3070s。

 which is like my graphics card and mine costs about， you know，1 cent per hour。

 which is which is embarrassingly cheap， but。Yeah， this one is more expensive。But yeah。

 so sobas is awesome you can use these looking any GPU you can pretty much select it and just use it on the fly and it's like hosted by someone else in the world that you SSH into and do stuff from。

嗯。Then you have Lambda Las， which I start set up。

![](img/c37b4ae812326667dccc6866281d1214_16.png)

![](img/c37b4ae812326667dccc6866281d1214_17.png)

And should find Lambda here， Lambda cloud， yep。

![](img/c37b4ae812326667dccc6866281d1214_19.png)

So。Data center， DGX systems。Like literally you have the blackwell GPUs， you have the H100s。Yeah。

 just。Pretty much GPU infrastructure specifically， and it's like。

I believe a bit cheaper than the big three providers like AW S， Google and Microsoft。

 So Lambda labbs is commonly used， but typically you would rent things in a cluster。

 So you're paying like multiple hundreds or thousands or tens of thousands of dollars per hour for these。



![](img/c37b4ae812326667dccc6866281d1214_21.png)

So if you're in a company and you're trying to get cheap GPs that are data center quality。

 you might want to look at Lambda。

![](img/c37b4ae812326667dccc6866281d1214_23.png)

And then compilers。 So I'm not like a compiler expert， but。Mainly。

 you're going to have things like XLA。 So this is what is powering JX。 You're going to have L VM。

 which I'm not an expert I even build compiler， so。I'll let you look into that。

 there's a ton of resources on LLVM。It is is it stands for low level virtual machine， I believe。



![](img/c37b4ae812326667dccc6866281d1214_25.png)

![](img/c37b4ae812326667dccc6866281d1214_26.png)

Go to LPM project。嗯。A toolkit for the construction of highly optimized compilers。

 optimizers and runtime environments。嗯。Multiple components。Component compiles C。

 C++ objective C and objective C plus+ code into LVM bit code and then into object files。

 so essentially used for developing stuff in C C++ and compilers in general。And then you have MLIR。

 which is MLIR。

![](img/c37b4ae812326667dccc6866281d1214_28.png)

我来的是间。

![](img/c37b4ae812326667dccc6866281d1214_30.png)

Multi labell intermediate representation。This was。MLIR and LVM were mainly developed by Chris Laner。

 which I also have a course on the programming language that his company built called modular。

 the programming language is called Mojo， you can search that up on freecodec and go learn Mojo too。

 but it's like a pretty much an AI programming language for doing fast Tensor operations。嗯。

So this was moved。As part of the LVM project。 And there's some interesting stuff there。 It's。

 it's somewhat newer。 So there's， you know。Interesting， interesting changes。

 not it's not like super ancient。But。The main ones that I'll be able to talk about are like NVCC。

 so that's like the ACUa compiler NV akuuda compiler。And you know。

 there's an architecture here which I haven't like fully memorized yet。

 but the NviDIA coudtic compiler is what we're going to be using to essentially compile our kudos scripts and kernels and have them you know。

 into bin so that we can run them fast so。

![](img/c37b4ae812326667dccc6866281d1214_32.png)

You know， these are interesting， interesting compiler infrastructure。

 I'll probably add to this with some better descriptions on like what these are。

 but this is like the general overview。

![](img/c37b4ae812326667dccc6866281d1214_34.png)

And then for miscellaneous I had， I could not leave that hugging pace。

 so last but not least it's like hugging pace right， you probably already know what it is but。



![](img/c37b4ae812326667dccc6866281d1214_36.png)

![](img/c37b4ae812326667dccc6866281d1214_37.png)

I'll look at just in case。 So on hugging face， you have a bunch of things。 You have models。

 data sets， and then spaces。 And that's like pretty much all you need to know。

 So if you go to models， you can。

![](img/c37b4ae812326667dccc6866281d1214_39.png)

嗯。And be able to take a second load。Here。We have multimodal， computer vision， N LP。

 audio tabular reinforcement learning， and then graph machine learning。

 So there's a bunch of cool stuff you can do here。 But most of it is language models right now。

 I know like flux recently released some of their。I believe it's like image。

 maybe video generation stuff。 I can't remember specifically。

 but this is where you'll see all like the new open source models that you can just pretty much download and run in run in pieytor like that。

 You just need enough hardware。 You just need good enough hardware to run these， and it'll just。

 it'll just work。And then you have the actual data sets for these models that that you train them on。

 So you know you can go like 3D data sets， which is interesting。

 A lot of it is just going to be text so。嗯。R fast。Yeah， vision data， awesome auto math text。

 So just all these， all these data sets are here that the models are trained on。

 And then you have spaces which is where you can actually use models。

 This is where people will like host things or get sponsors with custom hardware setups and they'll be able to just essentially host these models and you can try them out and use them。

 So hiring phase is awesome。 It's a major player in the whole ecosystem。

 and I could not leave it out。 but。😊，啊。

![](img/c37b4ae812326667dccc6866281d1214_41.png)

Yeah，' that's pretty much it for the deep learning ecosystem， I'll see you in the next part。

